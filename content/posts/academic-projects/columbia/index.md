---
title: "Using Graph Theory to Characterize Network Characteristics of Alzheimer's Patients versus Cognitively Normal Controls"
date: 2021-08-26T08:06:25+06:00
description: A project done in the summer of 2021 in collaboration with the department of Biostatistics at Columbia University
menu:
  sidebar:
    name: Network Connectivity in Alzheimer's Brains
    identifier: columbia
    parent: academic-projects
    weight: 2
hero: bkg.jpg
tags: ["Markdown","Content Organization","Multi-lingual"]
categories: ["Basic"]
---


The premise in this project was to evaluate neurological differences in Alzheimer's Patients with respect to anatomical differences in their brain network.  

Below is an outline of the background, methods, and results of the project that spanned the summer and was only made possible with the help of Dr.Jordan Dworkin from Columbia and my fellow student Aysha Vadukul. 

## Background

Alzheimer's disease is a progressive brain disorder that destroys memory and thinking skills, and eventually, the ability to carry out certain tasks. There are several theories that explain the pathology and symptoms of Alzheimer's, some conceraining cerebral blood flow, other cellular characteristics, but in this study we will evaluate the contribution from difference pattern in the brain network using R and a bit of graph theory.  

### rs-fMRI

This was done by way of rs-fMRI (resting state fMRI). rs-fMRI allows us to develop a matrix of values that correlate to the responses of the brain to task-negative states by measuring blood flow to certain regions of the brain. Through this method, we can evaluate the activation of certain "resting state" brain regions.

{{< img src="/posts/academic-projects/columbia/fmri.png" align="center" title="rs-fMRI">}}

Resting state functional connectivity, which is what we analyzed, covers the temporal correlation between different physiological structures as a function of differing blood flow.

### Network Components
Networks can be very simplified into two components, which is all we will need for our analysis. Nodes, and edges. Nodes represent the individual components in a system, imagine cities in a road network. Edges on the other hand represent interactions, or the relationship between those nodes, in the same analogy think the roads of the network connecting the cities. 

Applied to our analysis, small subsections of the brain are partitioned into "nodes", and the correlation of blood flow change in response to stimuli is regarded as the "edge". If two areas of the brain light up equally in response to a certain stimuli (or lack thereof) we can (very generally) assume there may be some correlation there. The analysis of these correlations is what allows us to apply graph theory principles to this complex network.

### Functional Connectivity
Functional Connectivity, referenced before, describes the relationship between the neuronal activation patterns of anatomically separated brain regions, refelcting the level of functional communication between the regions. Its what we use as data.

{{< img src="/posts/academic-projects/columbia/connectivity.jpg" align="center" title="Connectivity">}}

## Data
In our dataset, we had 956 total patients, 505 of which were cognitively normal, and 451 of which had Alzheimer's or were mildly cognitively impaired. The objective in this instance is to look for the differences in functional connectivity between CN patients and AD/MCI patients. 

### Pre-Processing
Pre-processing typically done with all biological signals. First, the data had to be tidied, and was thusly processed with the CONN toolbox (this adjusts for noise, movement artifact rmeoval, and temporal filtering).

Connectivity was then estimated usign the 100 parcel/ 7 network Schaefer Yeo atlas. This atlas divides subcortical structures to result in 135 total parcels divvied from 11 large scale brain networks/clusters. 

Connectivity was then defined using the Pearson correlation between temporal BOLD signals. In this analysis, you may see the term network-network connectivity values referenced, which represent the average connectivity values between parcels in a network. 

To simplify, remember that we start out with 135 parts of the brain that we perceive as anatomically different, then we group some of these parts together (due to anatomical and structural similarities) to develop 11 regions.Then we finally compare the level of functional similarity (blood flow response to stimuli) between each pair of these regions independently to get an 11x11 matrix of region to region comparisons. The workflow is depicted below. 

{{< img src="/posts/academic-projects/columbia/workflow.jpg" align="center" title="Workflow">}}

### Statistics
As shown above, after ordering, we conducted simple statistical tests to look for any perceivable differences. Once found through t-test, we conducted the Benjamini Hochberg adjustment. This is necessary to reduce the rate of false discovery. With 65 comparisons, it is highly likely that a statistical differences arises purely due to chance (for reference, the typical standard of p<0.05 would elicit a statistically significant result due to random chance 1 out of 20 times). To combat this, the BH adjustment first orders the hypothesis, then rejects or accepts them according to p-value. After ranking by significant p values, the algorithm re-adjusts the p-value by its position in the queue.

Below are the significant comparisons (in red) before and after adjustment

{{< img src="/posts/academic-projects/columbia/before.jpg" align="center" title="Pre-Adjustment">}}

{{< img src="/posts/academic-projects/columbia/post.jpg" align="center" title="Post Adjustment">}}
## Results

Some of the results can be interpreted above. We noticed certain region to region connectivity values that were significantly downregulated in AD patients. The clinical significance of each can surely be tied to the results we got, but we're not clinicians. This approach did elucidate several behaviors of the brain that I was not aware of below. One of which is modularity.

### Modularity
Modularity was found to be lower in AD patients compared to that of healthy controls. But what is modularity? Modularity is how well connected each node is to the rest of the system. It can be best depicted graphically, as seen below. 

{{< img src="/posts/academic-projects/columbia/modularity.jpg" align="center" title="Modularity">}}

Now, it might be hard to sense what modularity has to do with AD. It actually should be. Clinicians and researchers have been observing this very result and wondering the same thing. Although there isn't much substance on modularity yet, it has been known to correlate with better brain plasticity. Some papers find that modularity improves certain core brain functions, such as memory and cognition, and with regard to plasticity, it allows one to recover more quickly, and more fully from traumatic brain injuries. 

More data is necessary to better understand this relationship, as well as integrating the spectrum of disease progression rather than just sorting patients into the binary groups of AD or CN. 

### Correlation Matrix, Rich Club, Small Worldedness and other fun things

Below is the correlation matrix developed. Some other notes:

Rich club - a measure of how well close-connected nodes connect to each other was also analyzed, the significance of which we are not sure of 

Small worldedness - also calculated, which is a measure of the characteristic that each node only has one or two "neighbors"  but lacks more well connected properties

{{< img src="/posts/academic-projects/columbia/corr.jpg" align="center" title="Correlation Matrix">}}

{{< img src="/posts/academic-projects/columbia/network.jpg" align="center" title="Network">}}
## Code

```

setwd("C:/Users/me/Desktop/BEST/Research")
load("FullData.RData")
#load("TrialData.RData")

library(abind)
library(reshape2)
library(pbmcapply)
library(dplyr)
library(ggplot2)
library(tibble)
library(gtsummary)
library(tidyverse)
library(broom)
library(brainGraph)
library(knitr)
library(plotrix)

n2n.con = function(x, clusters){
  conn = x
  rownames(conn)=clusters; colnames(conn)=clusters
  conn = conn[order(clusters),order(clusters)]
  conn[upper.tri(conn)]=NA
  conn = melt(conn, na.rm=T)
  conn$Var = paste0(conn$Var2, "_to_",conn$Var1)
  conn = aggregate(conn$value, by=list(conn$Var), mean)
  net2net = matrix(conn$x,nrow=1)
  colnames(net2net)=paste0("FC_",conn$Group.1)
  return(net2net)
}


fc.data=pbmclapply(fconn, n2n.con, clusters=clusters, mc.cores=2)

fc.data=do.call(rbind,fc.data)
fc.data=as.data.frame(fc.data)
head(fc.data[,1:5])


full.data=cbind(data,fc.data)
# save(full.data, file="FullData_withFC.RData")


full.data <- full.data %>% arrange(Group)
full.data %>% group_by(Group) %>%
  summarise(mean = mean(FC_Default_to_Default), n = n())



t_test_results <- pivot_longer(fc.data[1,], cols = everything()) %>% 
  cbind(tidy(t.test(fc.data[,1] ~ data$Group))) %>% select(-value)
#add_column(colnames(tidy(t.test(fc.data[,1] ~ data$Group))))  
  


for(i in 1:ncol(fc.data)){
 t_test_results[i,2:11] = tidy(t.test(fc.data[,i] ~ data$Group, conf.level = 0.95)) #as.data.frame?
}


#sapply(which(t_test_results$p.value <= 0.05 & t_test_results$statistic >= 0.5 & t_test_results$statistic <= 2.0), function(x) colnames(fc.data[x]))
t_test_results$p.value <- p.adjust(t_test_results$p.value, method = "BH")

sapply(which(t_test_results$p.value<= 0.05), function(x) colnames(fc.data[x]))



significant_results <- t_test_results[which(t_test_results$p.value <= 0.05),]
t.test(fc.data[,24] ~ data$Group) #Just to check for formatting of new df





# Questions to cover
# Welsh's -- yes 
# Other statistical things to look for - look for estimate - greater connectvitiy in higher magnitude positive values (Higher connectivity in healthy individuals )
# Confidence intervals - Effects plotted with bars that represent the confidence interval of teh effect
# Mean difference/percent difference of means - for correlations to go from 0 to negative percent difference - use true gap instead 
# Results to interpret from here (cont region?) - 

#Confidence intervals with plotting 
#Small worldedness and modularity 
#Centrality 

#Corrplot package use to graphically show results of connection to connection specfic results
# Mat = matrix of pairwise differences
# corrplot(mat, is.corr=F)


library(corrplot)

plotColor <- function(ci_1, ci_2, mean){
  # if(mean < ci_1)
  #   "Red"
  # else if(mean > ci_2)
  #   "Red"
  if(!(0 > ci_1 & 0 < ci_2))
    "Red"    #Need Jordan to check?? Pretty much if CI doesn't include null result of 0
  else
    "Black"
}


plotColorResults <- vector(mode = "logical", length = nrow(significant_results))
for(i in 1:nrow(significant_results)){
  plotColorResults[i] <- plotColor(significant_results$conf.low[i],significant_results$conf.high[i],significant_results$estimate[i])
}
significant_results <- significant_results %>% mutate(color = plotColorResults)
#which(significant_results$estimate < significant_results$conf.low) & which(significant_results$estimate > significant_results$conf.high)

par(mar=c(5,11,4,3)+.1)
#plotCI(x = 1:nrow(significant_results), y= significant_results$estimate,ui = significant_results$conf.high, li = significant_results$conf.low, col =significant_results$color, xaxt = 'n',ann = FALSE)
plotCI(x =significant_results$estimate, y= 1:nrow(significant_results), ui = significant_results$conf.high, li = significant_results$conf.low, col =significant_results$color, yaxt = 'n',ann = FALSE,pt.bg=par("bg"), err = "x")
?plotCI
abline(v = 0, lwd = 3)
title(main = "Confidence Intervals of Net Means versus Baseline", xlab = "Net Difference")
axis(2, at = 1:nrow(significant_results), labels = significant_results$name,las = 2, cex.axis = 0.8)
#Question - if we're looking relative to AD patients, shouldn't the net differences be zero ?
#I.e. too look for regions upregulated

corrplot_df <- fc.data %>% slice(1:ncol(fc.data))
colnames(corrplot_df) <- clusters
rownames(corrplot_df) <- clusters








# 
par(mar=c(5,5,4,3)+.1)

plotColorResults <- vector(mode = "logical", length = nrow(t_test_results))
for(i in 1:nrow(t_test_results)){
  plotColorResults[i] <- plotColor(t_test_results$conf.low[i],t_test_results$conf.high[i],t_test_results$estimate[i])
}
t_test_results <- t_test_results %>% mutate(color = plotColorResults)
#which(significant_results$estimate < significant_results$conf.low) & which(significant_results$estimate > significant_results$conf.high)


plotCI(x = 1:nrow(t_test_results), y= t_test_results$estimate,ui = t_test_results$conf.high, li = t_test_results$conf.low, col =t_test_results$color, xaxt = 'n',ann = FALSE)
abline(h = 0, lwd = 3)
title(main = "Confidence Intervals of Net Means versus Baseline", ylab = "Net Difference")
axis(1, at = 1:nrow(t_test_results), labels = t_test_results$name,las = 2, cex.axis = 0.3)

# #
# # unique(clusters)
#
#
#
# #Modularity decreases as AD worsens? -> how does modularity affect clinical significance

#Use coord_flip in ggplot
#Use igraph to build network?? from very early code 



library(igraph)


count_AD <- 0
count_CN <- 0
mean_AD <- matrix(nrow = 135, ncol = 135)
mean_CN <- matrix(nrow = 135, ncol = 135)
for(i in 1:nrow(data)){
  if(data$Group[i] == "Alzheimer's Disease / MCI"){
    mean_AD <- mean_AD + fconn[[i]]
    count_AD <- count_AD + 1
  }
  else if(data$Group[i] == "Healthy Controls"){
    mean_CN <- mean_CN + fconn[[i]]
    count_CN <- count_CN +1
  }
  }
mean_AD <- mean_AD / count_AD
mean_CN <- mean_CN / count_CN

data$Group[1]
data$Group[111]

length(which(data$Group == "Healthy Controls"))

########################################
##### 1. Load and look at the data #####
########################################

setwd("~/Desktop") # change to wherever you saved the data file!
load("TrialData.RData")

# load packages, will need to install first!
library(corrplot)
library(igraph)
library(qgraph)

# take a look at the dataset
head(data)
boxplot(Age~Group, data=data)

# look at subject 4's age and disease status
data$Age[4]
data$Group[4]


##################################################
##### 2. Play around with subject 4's matrix #####
##################################################

# isolate subject 4's connectivity matrix
# by saving the fourth item in the 'fconn' list
matrix_sub4 = fconn[[4]]

# look at the names of brain regions and clusters/communities
regions
clusters

# visualize subject 4's matrix
corrplot(matrix_sub4[order(clusters),order(clusters)],is.corr=F,
         tl.pos='n',method='square',addgrid.col=NA)

# threshold subject 4's connectivity matrix for analysis
matrix_sub4[matrix_sub4 < quantile(matrix_sub4,.75)] = 0


#########################################################
##### 3. Play around with subject 4's network/graph #####
#########################################################

# create a graph object from the connectivity matrix
g = graph_from_adjacency_matrix(matrix_sub4, mode="undirected", 
                                diag=F, weighted=T)

# calculate the network's modularity
modularity(g, membership=as.factor(clusters))

# calculate the network's small-worldness 
# (a cool network measure, feel free to look it up!)
smallworldIndex(g)$index

# create a pretty network graph :)
# the plot function may take a second to run
cols=c("#832449","#798081","#705C07","#37419A","#B13F13","#FDBC53",
       "#080640","#95D5B2","#14242B","#FBB0AD","#2E0D1A")
plot.igraph(g,vertex.label.cex=0.01,
            vertex.frame.color="lightgray",
            vertex.color=cols[as.factor(clusters)],
            vertex.size=6,edge.curved=FALSE,
            edge.width=E(g)$weight/2,
            xlim=c(-.8,.8),ylim=c(-.8,.8),
            layout=layout_nicely(g))




```
---



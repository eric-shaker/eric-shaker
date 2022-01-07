---
title: "Synopsis of Work on Epigenetic Modifications to Diabetic Macrophages"
date: 2021-08-26T08:06:25+06:00
description: Investigating Genomic Responses to Diabetes as they affect Fibrotic Pathways and Inflammation
menu:
  sidebar:
    name: Updated Work
    identifier: updated
    parent: developmentstage
    weight: 3
hero: bkg.png
tags: ["Markdown","Content Organization","Multi-lingual"]
categories: ["Basic"]
---

In this section, I will briefly provide an update on the project. For reference, the first article was written after my first round of testing, and had **many** flawed ideas, methods, and theories. Nevertheless, I've showed it to contrast some of the more recent results. 

From then, I've gone on to analyze the data again, this time with a new assay. The entire process was much more thorough from my perspective, especially with regard to normalization and pre-processing steps. A simplified analysis will also be provided.

### Context

To provide some idea of where this summary arises from, I'll briefly summarise what has happened since the "initial results" categories information was posted. This was all done in the 2019-2020 academic year. 
* Normalization 
  * Normalization methods were kept the same. These were ultimately verified by a statistician, who verified the methods I used and their validity
  * Only difference was increased categorization of each patient 
    * To account for factors that were also affecting the genomic expression, confounders had to be adjusted for
      * BMI and previous surgery complication were two variables adjusted for
        * These variables affected the data in a statistically significant manner
        * Considering the smaller sample size, controlling for confounders is very neccessary in this instance
    * Multivariate differential expression used to account for the covariates that were no the focus of the study
* Analysis
  * Ultimately, more complex statistical tests, although interesting, were not the most relevant in terms of writing the manuscript
  * Nevertheless, PCA (principal component analysis), DE (differential expression) and pathway predictor engines will be posted here because I find them interesting
* Results
  * Ended up writing and presenting an Eposter at the AUGS
  * Never ended up submitting a full publication


### Processing
Imported diabetic and non-diaebtic assay data. Factored in demographic data (age, BMI, previous complications, etc.) to integrate for confounder calculation (need this for DE).

##### Background Noise Removal

Every assay has background noise. We try to reduce this to get better, and more accurate data. This idea is prevalent in the processing of all biological signals, electrical, electrochemical, and even in this instance genetic.

Two routes to go here:
* Background thresholding
  * Negative control thresholding
    * Uses the average of the negative controls
    * Can choose between using which type of mean (arithmetic, or geometric) to use with these controls)
    * Negative controls are things we're NOT looking for. If we find significantly higher levels of negative controls than the background that would suggest we have an issue
  * Threshold count value
    * Don't know why you would use this
    * Sets a specific value as a threshold
* Background Subtraction
  * Negative control subtraction 
    * Same this as before, but we subtract geometric/arithmetic mean from ALL analytes
  * Defined value
    * Pretty much same as threshold count except subtract from all analytes
  * Blank lane subtraction
    * We didn't use a blank here so this is irrelevant 
    * But in the instance you do you subtract the value from a blank run with nuclease free water

Background thresholding was used in this instance. This is because background subtraction tends to overestimate fold changes. In trying to be as conservative as possible, background thresholding was instead used. In our assay, you can view the negative controls labelled A, H, B, D and G which should decrease linearly as they have been engineered to do so. The fit of this correlation to the values we recieve is indicative of the translational accuracy of the assay to our data.

##### Normalization

This was done by way of two methods. Housekeeping probes and through positive controls. 

Housekeeping probes, as the name suggest, are supposed to vary minimally in expression level across samples. If one sample consistently has off the mark housekeeping genes, we can pretty much assume that somethings wrong with that sample and we should disregard it. 

Here were the housekeeping genes used and the relevant information
**Note, one of these genes was actually removed and is therefore not shown**
| Gene Name | Gene | Order Selected by geNorm | SD after Normalization |
|----|----|-----|----|
|RPL13a-mRNA |NM_012423.2:720|1|0.193|
|HMBS-mRNA |NM_000190.3:315|2|0.404|
|TBP-mRNA |NM_001172085.1:587|3|0.173|
|ABL1-mRNA |NM_005157.3:3200|4|0.41|

Positive Controls ABCDEF were also used. Positive controls are spiked in every sample in linear concentrations, so since we were doing fold changes analysis, I had to account for that in developing the accuracy of our values. 

What the normalized data looks like is below. Sorry its a little ugly. On the left side we can see the subjects, and on the top we can look for the genetic markers. There are 166 analytes tested for 

{{< img src="/posts/academic-projects/rui/updated/pic1.jpg" align="center" title="pic1">}}

What does it all mean? It's impossible to tell from the raw data. But we can use heatmaps, and some other visualization tricks to figure out which samples to ignore (if any). One I particularly like is the volcano plot. Its pictured below

{{< img src="/posts/academic-projects/rui/updated/pic2.png" align="center" title="pic2">}}

Whatever looks like an outlier - pretty much is an outlier. Subjects 41, 33, 31, and 1, among others are way out of line. We excluse those. (This was also verified during other software and using quantitative methods, not just graphical but I won't get into it)

### Results

Here are the results after normalization. We look to analyze several things. The next few sections will be about each individual testing metric, an explanation, our results, and my thoughts. 


#### Cell Types
First, the genes express can elucidate alot of information about the actual prevalence of certain cell types in our sample, and by extension the patients. This is called cell type analysis. We do such below, where we characerize the prevalence of certain cell types across every patient studied. Below is a heat map of my findings. 
{{< img src="/posts/academic-projects/rui/updated/pic6.png" align="center" title="pic6.png">}}

Now, looking at that visualization is difficult. You're trying to identify certain cell types, and look for their relation to the categorical diabetic variable by eye? This is not effective. 

To simplify, we can look at the cell types that have been determined to be statistically different across the diabetic condition. We've also visualized the overall trends on the left hand side (although keep in mind only two of these trends can be really concrete due to the aforementioned statement)
{{< img src="/posts/academic-projects/rui/updated/pic7.png" align="center" title="pic7.png">}}
Now, the clinical significance of all these gene and their relation to one of our covariates could probably be determined, but I personally did not do that. (contrary to what one might think, that takes awhile, and although I'm writing this website for fun I also don't have all the time in the world to break it all down).


#### Differential Expression
This is the gold standard for analysis. Its simple, obvious and very telling. Identifies specific targets that have decreased or increased expression (upregulated or downregulated) in relation to our covariate (diabetes). We can also account for confounders through this method. Provides the basis for GSA. We'll be using volcano plots again, so get good at interpreting those. Remember, statistically significant results will appear at the top of the plot. Differentially expressed genes will fall to either side. FDR thresholds will be indicated by horizontal lines. 

Below is one of the calculations used for the confounder adjustment

{{< img src="/posts/academic-projects/rui/updated/eq2.jpg" align="center" title="eq2">}}

###### P-value adjustment
When measuring 166 analytes, its highly probable we find a statistically significant result (remember that p<0.05, the scientific standard, will yield a randomly significant result 1 in 20 experiments). Therefore we must correct for this. There are several methods you can use here. In other articles I mentioned using Benjamini Hochberg (especially in the graph theory approach to Alzheiemer's) but that's typically only viable if you assuming the nodes/effectors don't have an impact on here. Studies concerning genes are highly complex because of the non-linear effects genes can have on each other, which would effect others b orders of magnitude or just slightly. Therefore this method would be inappopriate to use and dishonest. We settle on the Bonferroni correction, the most conservative. Bonferonni is one of the simplest, it just multiples the p-value by the number of genes tested. (Many genes that could be considered will inevitably be ruled out with this method). 


Here are the results below. 
{{< img src="/posts/academic-projects/rui/updated/pic4.png" align="center" title="pic4.png">}}
{{< img src="/posts/academic-projects/rui/updated/pic5.jpg" align="center" title="pic5.png">}}

Pay attention to the top 9 genes, which have a p-value, even after adjusted which are in our range. We will explore these further in subsequent analysis.

#### Gene Set Analysis

Gene set analysis (GSA) summaries regulatory changes within a predetermined "set" of genes.
Much of the information here and techniques mirror that from the DE section. As a reminder, DE is evaluated by doing a t-test on each gene versus our covariates (in this instance, diabetes, while confounding for BMI and previous complication). The directed global significance is rated as the tendency for that specific pathway to over or under express genes. Its calculated with the following formula. 

{{< img src="/posts/academic-projects/rui/updated/eq1.jpg" align="center" title="eq1">}}

These correlations were tested across different gene sets. We used volcano plots here. Look below. You can notice some of the titles being different gene sets used, i.e. for viral carcinogenesis, tuberculosis, etc.

{{< img src="/posts/academic-projects/rui/updated/pic3.png" align="center" title="pic3">}}


#### Pathways
Now, this is where things get interesting. Highly theoretical but also essential, this section is all about how the gene expression differences we see can manifest in different biological pathway differences that might elicit the pathological differences we see in patients. These pathways are numerous, difficult, much more complex than meets the eye and often not completely understood. Nevertheless, they are an excellent place for forming ideas and reasons for what we see in the world today. Here are some pathways I saw to be significant findings and I'd like to share. 

{{< img src="/posts/academic-projects/rui/updated/pic9.png" align="center" title="pic9">}}
{{< img src="/posts/academic-projects/rui/updated/pic10.png" align="center" title="pic10">}}
{{< img src="/posts/academic-projects/rui/updated/pic11.png" align="center" title="pic11">}}


### Conclusion
This was a cool project that pushed the bounds of what I was capable of, statistics wise and computation wise through code. I really enjoyed it. We ended up makign an Eposter posted below that I eventually presented at a couple conferences. Was cool. 

{{< img src="/posts/academic-projects/rui/updated/eposter.jpg" align="center" title="eposter">}}
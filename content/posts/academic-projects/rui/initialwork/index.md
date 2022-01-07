---
title: "Genomic Analysis of Diabetic Macrophages due to Polypropylene Mesh Complication Processing"
date: 2021-08-26T08:06:25+06:00
description: Investigating Genomic Responses to Diabetes as they affect Fibrotic Pathways and Inflammation
menu:
  sidebar:
    name: Initial Work
    identifier: initialwork
    parent: developmentstage
    weight: 1
hero: bkg.jpg.png
tags: ["Markdown","Content Organization","Multi-lingual"]
categories: ["Basic"]
---

## THE IMPORT, NORMALIZATION, VISUALIZATION AND ANALYSIS OF ASSAY RAW DATA

My first foray into research, this project means a lot to me. It taught me , not only some of the technical skills I would eventually use, but all of the soft skills that I've carried with me. It (perhaps unfortunately at the time) made me very familiar with confusion, and even more familiar with asking for help. The below is a reproduction of the work I did my freshmen year on.

I'm going to be honest - much of the techniques and information I learned here is very foreign to me now, and I do not feel qualified to speak on it. Instead, I'll reproduce some of my old writing, and have an updated section on the summary of my work and ultimately where it led me. An extension of this work can be found in the section on graphene loaded mesh implants. 

Written 10.11.2019

#### PROCEDURE FOR IMPORT AND NORMALIZATION

To import data into nSolver, utilized the convenience of RCC files forwarded. Imported appropriate RLF files accompanying RCC files to ensure no data lost. All 48 test samples imported, with annotations differentiating “diabetic” and “non-diabetic” samples. Standard QC(quality control) measures implemented, including positive control measures which allow 2 standard deviations of 0.5fM

{{< img src="/posts/academic-projects/rui/initialwork/pic1.png" align="center" title="pic1">}}

In addition, implemented background thresholding quality control. Contrary to background subtraction quality control which is not recommended by nSolver, background thresholding has a set value to which all counts which fall below are adjusted to match. Background thresholding is preferable in instances where fold change estimates are important, as background subtraction overestimates fold changes

{{< img src="/posts/academic-projects/rui/initialwork/pic2.png" align="center" title="pic2">}}

For normalization patterns, used specified, 0.3 – 3.0 range outlined in nSolver user manual. Implemented use of the geometric mean to calculate normalization factor as a product of the positive control tests. The geometric mean divided by the arithmetic mean is used as a lane specific normalization method to reduce the effect of differing gene concentrations on the purity of the dataset.

{{< img src="/posts/academic-projects/rui/initialwork/pic3.png" align="center" title="pic3">}}

#### Analysis

To analyze the data, an emphasis was placed on fold changes. Folds are a product of the average of normalized lanes, their changes signifying a statistically significant variation in gene expression/concentration. To identify species for fold changes, compared species from diabetic and non-diabetic samples to observe expression differences, rather than using all pairwise ratios which would not be conducive to elucidating new information. During the calculation, fold changes would be expression as A/B if the change was greater than 1, while in the instance it wasn’t the negative reciprocal of the fold change was expressed, as in the IL-6 gene. Used a log2 ratio test to find fold changes. For the settings, utilized Euclidean distance calculation which extracts the most information but is the least robust compared to the other options which require the application of the Pearson or Spearman coefficients. Analyses utilizing Pearson and Spearman coeffecients are subjects for further data extraction.

#### The Data - Statistically Significant Findings

First, the data was analyzed without normalization factors implemented. The following is a graphic developed in tandem with the advanced analysis system application.


{{< img src="/posts/academic-projects/rui/initialwork/pic4.png" align="center" title="pic4">}}

After normalization was conducted a visualization was developed to display the results. In these visuals, the cluster data with similar expression maps could be easily seen. The colored bar represents QC flags, with the solid color indicative of no QC flags arising. However, the solid blue in the middle signifies probes dropped for analysis due to low signaling. Ultimately, this raw data is simply typically used as a QC tool rather than a vehicle for analysis

{{< img src="/posts/academic-projects/rui/initialwork/pic5.png" align="center" title="pic5">}}

The above is a representation of the principal components of the data. Differentiations in the clustering of diabetics and non-diabetic markers would indicate obvious differential gene expression, however that is not present. Outliers could cloud the clarity of the visual this idea and skew data, as well as the lack of integration of demographic information

{{< img src="/posts/academic-projects/rui/initialwork/pic6.png" align="center" title="pic6">}}

The above is another quality control measure. The lack of a statististically different skew of the p-values signifies relatively few genes differentially expressed, however this is subject to further analysis for confirmation. The graphic on the left is another metric to investigate the quality of the data, ultimately affirming its validity. 

{{< img src="/posts/academic-projects/rui/initialwork/pic7.png" align="center" title="pic7">}}

Lastly, the normalization summary data suggests the removal of samples RL-45, Rl-3 and Rl-41 as after normalized, they exhibited characteristics of an outlier. However, once demographic information is integrated into the system and the concentration accounts are adjusted for these values, they may be reintroduced into the dataset. 

#### Evaluating the Presence of A Differentially Expressed Gene

{{< img src="/posts/academic-projects/rui/initialwork/pic8.png" align="center" title="pic8">}}

The volcano graph above is the first measure to identify the presence of a differentially expressed genes. The legend is composed of the margins for the p-value significance level thresholds. The vertical axis represents the abundance of the gene’s expression, while the horizontal spread is indicative of the difference between the diabetic and nondiabetic. Those genes horizontally extreme have the most difference among the two groups tested, hinting at a possible differentially expressed gene. The main perpetrators for this possibility are IL-6 and MMP1, whose log2 fold changes are above 1, with IL-6 having a negative fold change of -1.74. 

{{< img src="/posts/academic-projects/rui/initialwork/pic9.png" align="center" title="pic9">}}

The above scatter plot affirms the possibility of a differentially expressed gene in MMP1 and Il-6. Divergences from the linear line are indicative of a statistically significant difference in the incidences of both genes. With non-diabetics plotted linearly, data points regarding diabetic genes can be interpreted visually relative to the norm.
The last analysis measure implemented was an analysis of the heat maps. This was done using the normalized data, in which two tests ran: one which utilized the z-scores of the genes which related expression across samples and the other which utilized the z-score of the samples, essentially relating a genes expression to the rest of the genes in a single sample. The results are below, respectively z-score gene and z-score sample


{{< img src="/posts/academic-projects/rui/initialwork/pic10.png" align="center" title="pic10">}}

{{< img src="/posts/academic-projects/rui/initialwork/pic11.png" align="center" title="pic11">}}

Note that diabetic data points are outlined in yellow lining. Through separating these tests by categorical covariants, we can identify noticeable differences in the expression of genes and application to macrophages and diabetics.

#### Possible Rationale And the Future

In the future, it would be essential to implement demographic data into the model to eliminate the presence of outliers like RL-45 and to reintegrate there, potentially very significant data. Furthermore, through further research there were significant links between the two, initially differentially expressed, genes IL-6 and MMP1. Matrix metalloproteinase (MMP1) relates to Macrophage activity as it regulated the macrophages ability to secrete PGE2 and is likely to play a role in the pathogenesis of chronic inflammatory disease and cancer [1]. The following model puts into context that biochemical pathway:

{{< img src="/posts/academic-projects/rui/initialwork/pic12.png" align="center" title="pic12">}}

However, MMP1 has not been predicted to be a vehicle for macrophage differentiation, as the gene is not unique to the functions of the macrophage alone. The other notable outlier, IL-6 shows a much more promising potential. 
IL-6 is shown to have a strong correlation with macrophage activity. IL-6 is attributed to regulating the balance between M1 and M2 macrophages in mice. A difference in the ratio of M1 and M2 macrophages is proven to cause higher infection rates among diabetics, the core of the issue.  Diabetes is shown to affect the immune system by polarizing into subtype M1 macrophages which contain the capability to produce cytokines and do phagocytosis while initiating immune response. The decrease in the presence of M2 perhaps slow wound healing and differences in the ratio are often attributed to infectious diseases. M1 macrophages also contain the ability to prolong chronic inflammation by warring a pseudo-war in the body due to the aggressive nature. In closing, IL6 and MMP1 can be seen as potential avenues for furthermost in the field for observing the relationship between infectious diseases, specifically diabetes, and immunocompromability. 

#### Phase 2: Further QC
To consolidate the validity of data, further QC was done, now especially pertaining to the cell type of interest. To investigate the accuracy of data with regards to an effect on macrophage mRNA, cell profiling analysis was done. This was done by importing a set of genes native to the macrophage and normalizing it to the expected. The results show as follows
{{< img src="/posts/academic-projects/rui/initialwork/pic13.png" align="center" title="pic13">}}
In this visual, a slope of 1 is ideal, and indicates the validity of data. As once can see, the data is valid and precise under the measures as tested by the hallmark macrophages genes CD163 and CD68. The normalization of CD68, and accuracy according to its incidence is indicative of the validity of the data concerning macrophages. 
#### Implementation of Demographic Data
To further normalize the results by factoring in BMI, age, the presence of an immune deficiency disorder and relevant protein concentrations, demographic data was imported through a CSV file. Through attaching annotations that matched both the data file and the demographic description file, these two could be linked in the system. Unfortunately, there was an incongruency in some of the data, as the presence of diabetes, which was indicated on both files, did not match. This issue is still being looked into, but an example of it can be blatantly seen in the heatmap, where the pattern of diabetes and the pattern of the status annotation should be the same
{{< img src="/posts/academic-projects/rui/initialwork/pic14.png" align="center" title="pic14">}}

To fix this, further analysis should be done to find the error. Cofounders and covariates are considered in the application of signaling pathways as well as differential expression and cell type profiling, so a solution to this issue could elucidate more information as to the signaling pathways essential in this relationship.  Visual inspection of the heatmap also leads one to believe that there was statistically significant error concerning the trial RL-41, and it should not be considered and instead ruled an outlier.
#### Statistical Improvements
Another area identified for improvement over the older model was the inclusion of the spearman and Pearson coeffecients as methods of defining relevant data over the calculation of Euclidean distance. The Euclidean distance calculates the distance between the two genes as the square root of the sum of squared differences in their log count values, which extracts the most information but is the least robust to mean shifting and outliers. Instead, the Pearson correlation, which uses the Pearson correlation coefficient on log count values to measures distance, was used to create a more robust sample safe from mean shifting while still susceptible to outliers. The last statistical method applied to the agglomerative heat maps was the spearman correlation. This technique implements spearman distances using Spearman’s rank correlation coefficient which gauges the distances between two genes by examining the similarity of the rankings of their genes. By using the rank information instead of the count values, Spearman correlations discard information but are very robust to outliers and non-linear relationships, and will be the focus of further data collection and analysis. Below are the updated agglomerative heat maps, which the Pearson and Spearman correlation applications shown respectively:

{{< img src="/posts/academic-projects/rui/initialwork/pic15.png" align="center" title="pic15">}}
{{< img src="/posts/academic-projects/rui/initialwork/pic16.png" align="center" title="pic16">}}

These heat maps should be interpreted in the same fashion as previously, with black representing no change in regulation, green indicative of up regulation and red indicative of down regulation. Since the pre-normalized group data was used for these visuals, analysis can be made visually. Looking for the starkest difference of color is a primary indicator for differentially expressed genes among diabetics and non-diabetics. 
Another source for measurement was the FOV registration used for the analysis of the QC data. If the FOV of the fields observed/FOV of the fields expected >75%, it can be reasonably assumed the accurate data has been collected. This has been confirmed to be true. Furthermore, the p-values did fall within a safe range for analysis, although 1 out of every statistically tests is expected by change alone to result in a p-value of 0.05, the traditional threshold for a figure being statistically significant. The frequency of potential false positive is expected to go up with increasing numbers of tested genes, so for larger Code-Sets such as this one, only the extremes of differential expression should be considered as effectual in biochemical pathways. 

#### Pathway Analysis
After finally renormalizing the data to CD68, which proved to be accurate, and utilizing spearman and Pearson coeffecients applications while attempting to factor in demographic data, we are able to delve into the application of pathways. Two main pathway directories were used, the GO Molecular function and the KEGG Pathway. The directories were applied as probe annotations which affects the perception of the increased concentration in mRNA, linking it to a physiological difference. In the GO molecular function analysis, the differences identified represented cellular actives that ignored place or cellular body which performed the action. Meanwhile, the KEGG Pathway is a collection of manually drawn pathway maps representing the knowledge of molecular interactions and relevant networks and provides greater insight into the biochemistry involved. With regards to relevant findings, the KEGG Pathway was found to be more important. The KEGG Pathway illuminated two potential sources for the differences in the immune system, stemming from decreased cytokine-cytokine receptor interaction as shown in the pathway below

{{< img src="/posts/academic-projects/rui/initialwork/pic17.png" align="center" title="pic17">}}

Furthermore, some other pathways were found to be possibly linked. The following are attached and sources for further inquiry as to find the origins of this pathway. They include the pathway regarding TNF signaling, chemokine signaling, AGE-RAGE signaling pathway in diabetic complications and Amoebasis. 
{{< img src="/posts/academic-projects/rui/initialwork/pic18.png" align="center" title="pic18">}}

{{< img src="/posts/academic-projects/rui/initialwork/pic19.png" align="center" title="pic19">}}

{{< img src="/posts/academic-projects/rui/initialwork/pic20.png" align="center" title="pic20">}}

{{< img src="/posts/academic-projects/rui/initialwork/pic21.png" align="center" title="pic21">}}
#### Applications and Moving Forward
In the intense debate over the role of IL-6 in the body, specifically affecting macrophage activation and immune system efficacy, we cannot ignore the dual sided nature of the gene. IL-6 was first considered only to be influential in the acute phase of the inflammatory response but this cytokine was later found to be active in the production of cytotoxic T-cells and the transition from innate to acquired immunity. Since IL-6 was found to have both these two functions through the usage of classical and Trans signaling pathways, pharmaceutical that inhibit IL-6 Trans signaling without affecting its classical functions are in high demand. Luckily enough, the soluble version of glycoprotein 130, sgp130, naturally prevents the association of the IL-6 sIL-6R complex with membrane bound gp13- and specifically inhibits Trans signaling [4]. 
Apart from its application, the data points specifically in two major directions: effects on the CXCR1 and CXCR2 subfamilies in cytokine cytokine receptor interaction and chemokine signaling pathways. Both of these pathways contain a lot of potential for growth. CXCR1 and CXCR2 are involved with leukocyte functionality, straying from the initial identification of issues regarding macrophages. However, there is significant data to suggest a relationship, as a correlation matrix between the different antibody/cell types suggests the strongest relationship between macrophages and dendritic (DC) cells. 
{{< img src="/posts/academic-projects/rui/initialwork/pic22.png" align="center" title="pic22">}}
Apart from this theory, further investigation will have to be done into the effects on chemokine, the main perceived perpetrators. IL-8 was found to have significant effect when using the GSA (global significance score) in relation to diabetes based health complications. GSA source of further improvement, but need to make progress on integration of demographic data. 

{{< img src="/posts/academic-projects/rui/initialwork/pic23.png" align="center" title="pic23">}}

#### Works Cited
[1]Luckett-Chastain, Lerin, et al. “IL-6 Influences the Balance between M1 and M2 Macrophages in a Mouse Model of Irritant Contact Dermatitis.” The Journal of Immunology, American Association of Immunologists, 1 May 2016.                                          
[2]Steenport, Michel et al. “Matrix metalloproteinase
(MMP)-1 and MMP-3 induce macrophage
MMP-9: evidence for the role of TNF-alpha and cyclooxygenase-2.” Journal of immunology (Baltimore, Md. : 1950) vol. 183,12 (2009): 8119-27. doi:10.4049/jimmunol.0901925
https://diabetes.diabetesjournals.org/conten
54/suppl_2/S114
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4128059/

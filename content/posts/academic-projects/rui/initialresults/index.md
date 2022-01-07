---
title: "Genomic Analysis of Diabetic Macrophages due to Polypropylene Mesh Complication Results"
date: 2021-08-26T08:06:25+06:00
description: Investigating Genomic Responses to Diabetes as they affect Fibrotic Pathways and Inflammation
menu:
  sidebar:
    name: Initial Results
    identifier: initialresults
    parent: developmentstage
    weight: 2
hero: bkg.png
tags: ["Markdown","Content Organization","Multi-lingual"]
categories: ["Basic"]
---



## Data Analysis and Results - Diabetic Mesh Analysis Regarding Macrophage Complications

In this section, I outline the main results that were drawn from that initial series of testing. For transparencies sake, many of these initial ideas/theories were later disproven, but I wanted to keep the spirit of the work intact. 

#### Procedure for Import and Normalization

For the purpose of brevity, in depth normalization and import steps were outlined in another document. In this experiment, P-values < 0.05 were considered statistically significant with a Pearson Correlation Coefficient between variables and risk factors. Fold changes were calculated in typical log2 fashion and correlated with p-values in an ad-hoc process similar to standard procedure set by Peart et al. 2001[1] and McCarthy et Smyth 2009[2]. Values are reported as means ± standard error.  

#### Effect on HDAC3

Upon further analysis and the consultation of several statistical sources, many genes seem to be differentially expressed. Among those reside p65, STAT6 and NFkB. These three genes uniquely share the trait that they are integral in HDAC3 activity. The upregulation of these genes confirms an increase in histone deacetylase activity, as shown by Sathishhumar et al. 2016[3]. Macrophage polarization is mediated by epigenomic modifications including histone acetylation that we see here. HDCA3 functions as the opposite of IL-4, effectively repressing its activation which controls the polarization of macrophages as found by Mullican et al. 2011[4]. Ultimately, HDCA3, and the prevalence of related constituents indicates the increase in M1 polarization in the macrophages of diabetics. In addition to HDAC3, HDAC5, HDAC7, and HDAC11 have all been shown to be upregulated, and whose functions are depicted in the model to the right.

{{< img src="/posts/academic-projects/rui/initialresults/pic1.png" align="center" title="pic1">}}

#### Macrophage Polarization as a Function of HDAC3 and IL-13
Another gene that was positively differentially expressed was IL-13. IL-13 is considered a Th2 cytokine along with IL-4 that promotes alternative activation into the M2 subtype. This directly contrasts the effects of HDCA3 which deacetylates histone tails at regulatory regions. The prevalence of both activation methods, polarization into both M1 and M2 is a cause for concern and future questioning. IL-13 is known to function as an anti-inflammatory as it inhibits proinflammatory cytokines like IL-6 which is shown to be down-regulated in the figure. This disparity must be explained in the future. 
#### Fibrotic Pathways
IL-13, a profibrotic cytokine, has been shown to contribute to fibrosis pathogenesis. In many animal models, inhibiting IL-13 has resulted in the decrease of fibrosis Mohning et al 2019[5]. Hyperglycemia has been linked to active a fibrogenic pathway, namely the AGE-RAGE. This pathway has shown significant upregulation in the PathView analysis feature. Once the AGEs bind to the RAGEs, inflammation is propagated, and pro-fibrotic effects are initiated. While these outcomes are able to be regulated by TGF-B and AT-1, these genes were not shown to have significant fold changes. This could lead one to believe that in the presence of type 2 diabetes mellitus, a different fibrotic pathway is undergone that perpetuates scarring from chronic inflammation. Of course, this is a source for further research
{{< img src="/posts/academic-projects/rui/initialresults/pic2.png" align="center" title="pic2">}}

#### Intracellular Interactions that May Lead of FDR
IL-6 was previously believed to the catalyst for the polarization difference, but intracellular interactions suggest otherwise. IL-13, which is heavily upregulated has the capability of activating monocyte cell lines and inhibiting the production of inflammatory cytokines like IL-6. This could lead to the seemingly downregulated expression of IL-6 that was previously attributed to the diabetic condition. 

#### Senescence
The senescence-associated secretory phenotype (SASP) has been attributed to originating inflammaging in aging and type 2 diabetes mellitus. The emergence of inflammatory agents like IL-6,    NF-κB and TNF-A all suggest that senescence plays a large role in chronic inflammation as these molecules are either released or modulated by SASP Prattichizzo et al. 2016[6]. TNF-α was shown to be statistically significant in upregulation, which could support this hypothesis.
{{< img src="/posts/academic-projects/rui/initialresults/pic3.png" align="center" title="pic3">}}
#### Possible Explanation to Outliers
To confirm the validity of the data, certain points of doubt must be cleared. Every upregulated gene is correctly correlated to increases in inflammation, many by way of HDAC3 and some through polarization pathway. However, some outliers have risen whose precedence demands explanation in return for validity. IL-6 is downregulated, understandably so due to the affect of the heavily upregulated IL-13 that counteracts its behavior. Apart from IL-6, the prevalence of MMP3 is seemingly without purpose. 
MMP3 has historically be found to be upregulated in diabetics. Although they are not region specific and frequently reside in the ECM, MMP3 is typically expressed by macrophages within atherosclerotic plaques associated with heart disease Wilson et al. 2008[7]. Upon further insight, it is possible that the prevalence of MMP3 could be attributed to the unique condition of mesh analysis in which scar tissue is already present. Perhaps not particularly tied to heart disease, the matrix metalloproteinases have been shown to express greater levels in the presence of fibroblasts, which could have formed due to the upregulation of IL-13. This would also provide rationale as to why MMP3 had such a divergence from other metalloproteinases like MMP9 that is typically upregulated. 
{{< img src="/posts/academic-projects/rui/initialresults/pic4.png" align="center" title="pic4">}}

#### Works Cited

[1] Peart, M. J., Smyth, G. K., van Laar, R. K., Bowtell, D. D., Richon, V. M., Marks, P. A., Holloway, A. J., & Johnstone, R. W. (2005). Identification and functional significance of genes regulated by structurally different histone deacetylase inhibitors. Proceedings of the National Academy of Sciences of the United States of America, 102(10), 3697–3702. https://doi.org/10.1073/pnas.0500369102                                              
[2] McCarthy, D. J., & Smyth, G. K. (2009). Testing significance relative to a fold-change threshold is a TREAT. Bioinformatics (Oxford, England), 25(6), 765–771. https://doi.org/10.1093/bioinformatics/btp053                                              
[3] Sathishkumar, C., Prabu, P., Balakumar, M., Lenin, R., Prabhu, D., Anjana, R. M., Mohan, V., & Balasubramanyam, M. (2016). Augmentation of histone deacetylase 3 (HDAC3) epigenetic signature at the interface of proinflammation and insulin resistance in patients with type 2 diabetes. Clinical epigenetics, 8, 125. https://doi.org/10.1186/s13148-016-0293-3          
[4] Mullican, S. E., Gaddis, C. A., Alenghat, T., Nair, M. G., Giacomin, P. R., Everett, L. J., Feng, D., Steger, D. J., Schug, J., Artis, D., & Lazar, M. A. (2011). Histone deacetylase 3 is an epigenomic brake in macrophage alternative activation. Genes & development, 25(23), 2480–2488. https://doi.org/10.1101/gad.175950.111.                   
[5] Michael P. Mohning, Gregory P. Downey, Gregory P. Cosgrove, Elizabeth F. Redente,
Chapter 3 - Mechanisms of Fibrosis,
Editor(s): Jeffrey J. Swigris, Kevin K. Brown,
Idiopathic Pulmonary Fibrosis,Elsevier,
2019,Pages 9-31,ISBN 9780323544313,
https://doi.org/10.1016/B978-0-323-54431-3.00003-2.                                        
[6] Prattichizzo, F., De Nigris, V., La Sala, L., Procopio, A. D., Olivieri, F., & Ceriello, A. (2016). "Inflammaging" as a Druggable Target: A Senescence-Associated Secretory Phenotype-Centered View of Type 2 Diabetes. Oxidative medicine and cellular longevity, 2016, 1810327. https://doi.org/10.1155/2016/1810327                                       
[7] Wilson, K. D., Li, Z., Wagner, R., Yue, P., Tsao, P., Nestorova, G., Huang, M., Hirschberg, D. L., Yock, P. G., Quertermous, T., & Wu, J. C. (2008). Transcriptome alteration in the diabetic heart by rosiglitazone: implications for cardiovascular mortality. PloS one, 3(7), e2609. https://doi.org/10.1371/journal.pone.0002609
Luckett-Chastain, Lerin, et al. “IL-6 Influences the
Balance between M1 and M2 Macrophages in a 
Mouse Model of Irritant Contact Dermatitis.” The 
Journal of Immunology, American Association of 
Immunologists, 1 May 2016.
Steenport, Michel et al. “Matrix metalloproteinase
(MMP)-1 and MMP-3 induce macrophage
MMP-9: evidence for the role of TNF-alpha and cyclooxygenase-2.” Journal of immunology (Baltimore, Md. : 1950) vol. 183,12 (2009): 8119-27. doi:10.4049/jimmunol.0901925
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4128059/                               
Ilaria Russo, Nikolaos G. Frangogiannis,
Diabetes-associated cardiac fibrosis: Cellular effectors, molecular mechanisms and therapeutic opportunities,Journal of Molecular and Cellular Cardiology,Volume 90,2016,Pages 84-93,ISSN 0022-2828,https://doi.org/10.1016/j.yjmcc.2015.12.011.
(http://www.sciencedirect.com/science/article/pii/S0022282815301498)                        
Salazar, J. J., Ennis, W. J., & Koh, T. J. (2016). Diabetes medications: Impact on inflammation and wound healing. Journal of diabetes and its complications, 30(4), 746–752. https://doi.org/10.1016/j.jdiacomp.2015.12.017                                          
Palmer, A. K., Tchkonia, T., LeBrasseur, N. K., Chini, E. N., Xu, M., & Kirkland, J. L. (2015). Cellular Senescence in Type 2 Diabetes: A Therapeutic Opportunity. Diabetes, 64(7), 2289–2298. https://doi.org/10.2337/db14-1820

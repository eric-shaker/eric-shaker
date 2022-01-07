---
title: "Embryonic Mouse Development and Brain Development Using Image Processing "
date: 2021-05-03T08:06:25+06:00
description: Project Based on the Analysis of Embryonic Mouse Development and Brain Development Using Image Processing
menu:
  sidebar:
    name: Embryonic Mouse Brain Development
    identifier: wulab
    parent: academic-projects
    weight: 6
hero: bkg.png
tags: ["Markdown","Content Organization","Multi-lingual"]
categories: ["Basic"]
---

## Introduction
This project is one I was hired to do for the developmental biology labratory at UPMC Children's Center under the guidance of Dr.Wu. I thank him for the time and his generosity during my work there. As part of his team, I was involved in the image processing pipeline, in which different images of different forms (think SPECT, CT, MRI) all were sent to me for basic pre-processing and analysis. From which results and further testing could be conducted. Although there were several projects I participated on, the one I will outline below involves the relationships between subcortical structures in mice brain. 

## Methods
Each mouse was sedated using isoflurane and then put into an fMRI machine, like the one referenced in a later article on Alzheimer's analysis. Once done, I extracted the raw data, did some menial pre-processing (noise removal etc.) and then segmented for certain regions. Everything mentioned here has been done using a mix of ImageJ, Fiji, and DSI studios, all of which I thank greatly for saving me time. These regions were then use to develop an atlas for which the connections between the pre-identified regions were calculated. 

#### Fiber Tracking
From there, fiber tracking was done, which is a method of enabling in vivo reconstruction of white matter pathways using DTI (diffusion tensor imaging). Simply put, this allows us to see the connections between the regions we decided earlier. And when these processes are combined, and applied to mice with differing pathologies (think oxygen deprivation) much is to be learned about the effect of these pathologies on the functioning of mice brains - and ultimately our own.

## Results 

#### Segmentation
The first obvious result is the development of the fully segmented mouse brain. This is a feat in it of itself as the structures within the mice brain are often very low resolution (since the mouse is so small itself, and the MRI is only of such resolution). Experience is the best indicator of developing a good segmentation here. One such is portrayed below. This was done for hundreds of mice. 

{{< img src="/posts/academic-projects/wulab/dsi.jpg" align="center" title="Segmentation">}}

#### Fiber Tracking
First, certain subcortical structures were merged (perhaps the corpus callosum and the cerebellum based on functional/anatomical relation) and then the merged segmented was used to perform fiber tracking and observe the relationships between it and adjacent structures. (The result of which is displayed on the home screen and below).

{{< img src="/posts/academic-projects/wulab/fibertracking.jpg" align="center" title="Segmentation">}}

#### Connectivity Analysis

Afterwards, these relationships were analyzed using circos plots. These circular plots are excellent for conveying relationship based information between objects or positions. Typically used for genomic data, they work excellently here as well. Two real results have been pictured below.

{{< img src="/posts/academic-projects/wulab/circos2.png" align="center" title="Circos1">}}

{{< img src="/posts/academic-projects/wulab/circos1.png" align="center" title="Circos2">}}




Although not maybe the most difficult job I could've had, I learned a lot doing this work concerning image processing and segmentation. 
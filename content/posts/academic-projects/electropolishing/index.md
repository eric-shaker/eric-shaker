---
title: "Electropolishing"
date: 2021-08-26T08:06:25+06:00
description: A Project Done for the Development of Medical Device Implants
menu:
  sidebar:
    name: Electropolishing
    identifier: electrpolishing
    parent: academic-projects
    weight: 5
hero: bkg.jpg
tags: ["Markdown","Content Organization","Multi-lingual"]
categories: ["Basic"]
---

This project was primarily focused on the "smoothing" of medical devices using a method called electropolishing. This entailed developing a tailored solution to the material-to-be-polished, and then immersing the device in that solution and applying an electrical current. This involves very high voltages and precise measurements, so it was pretty exciting. This was some of my background work on the subject

### Background
Electropolishing is a common method used for surface smoothing after metal microfabrication leaves small pits and indentations on the surface of manufactured materials that can often interfere with usage. It is very different than passivation, which is a technique often used in manufacturing cardiovascular devices.

Passivation is a non-electrolytic process that simply uses nitric or citric acid and removes free metal ions from the surface and forms a protective oxide layer that turns the surface into being more damage resistant and less vulnerable to oxidation. This is not our goal here.

Electropolishing can be used on complex geometries to deburr, polish, buff and remove imperfections from the surface of the material. Downsides to this method are the high power supply required which limit mass production – which is currently irrelevant in our application.

Passivation(pickling) and electropolishing are commonly used in conjunction so that the roughness of the cutting zone and oxide films covering the stent surface are reinforced.

Finally, results can be measured in three ways. Average surface roughness, amount of pitting, and surface brightness. Surface roughness is the only quantifiable method though means of interferometer or surface profiler. Apparently the Electroplating Engineering Handbook is an excellent resource on this matter.

### Execution
In this instance we were applying the procedure to a chromium alloy (to be used in neurovascular aneurysm coiling), so therefore the solution had to be tailored to the element itself. 

Here were the potential options/formulations

    


| Study | Material | Electrolyte Solution | Temperature | Distance to  Material | Other Treatments |
|------|---------|--------|-----|------|---------|
| Electropolishing of coronary stents | Stainless Steel slotted tube coronary stents made by laser cutting [1] | 195 mL 88 % H3PO4, 75 mL 96 % H2SO4, 30 mL H2O, and 0.75 g Na5P3O10 composition electrolyte | 20-70 degrees C. | N/A | Passivation (pickling) with hydrofluoric acid and nitric acid and distilled water in 1:3 proportion. Current density applied was 625–875 mA/cm2. | 
| Electropolishing of 316 LVM stainless steel cardiovascular stents [2] | 316 LVM stainless steel (AVM F138).By wt% Cr (17.00–19.00), Ni (13.00–15.00), Mo (2.25–3.00), Mn (<=2.00), Si (<=0.75), C (<=0.03), P (<=0.025), S (<=0.0 | Sulfuric and phosphoric acid at 50% each volume. | 75 C | 50 mm | Acid pickling to remove slag and metal oxides by using HF, HNO3 and H20 at 45 degrees C. | 
| Pulse and DC Electropolishing of stainless steel for stents and other devices [3]| 304 and 316L austenitic stainless steels | Eletropolishing solution was 500ml of EPS 4000 electropolishing solution which is phosphoric and sulfuric acids, distributed from Wisconsin as part of electro polish systems. | 60 C to 70C | N/A | Stainless still as in 5mm x 5mm bits, noticeably smaller than we proposed to use. 323 mA/cm^2. Cleansed in acetone prior. |
| Patent on Electropolishing Fixture and Electrolyte solution [4]| Nickel titanium and stainless still allows used for angioplasty procedures | For nickel titanium – 70-90% weight for methanol, 5-15% sulfuric acid, 1-6% HCL | N/A | N/A | 500ml of electrolyte solution used. 75 amperes per inch current density used. |
| Patent on Electropolishing Electrolyte Composition Range [5] |Cr Co | 85% EF 200 ethylene glycol 10% sulfuric acid 5% HCL (optional) OR 85% EF 200 15% Phosphoric acid | N/A |  N/A | 70 year history in industry | 
| Patent on Electropolishing for cobalt and cobalt alloys [6]| Cr  Co Alloys | Alkane-sulfonic acid to glycolic acid in the range from 30:70 to 80:20 – glycolic acid should be concentrated >70% wt%. For their final solution for cobalt chromium tungsten alloy they used >99% methane sulfonic acid and >70% glycolic acid in a ratio of 55:45 | 40 – 70C | N/A | 5 – 25A/dm^2 |
| Patent for Process for electropolishing a device for cobalt chromium  [7]| Cobalt chromium alloys and specifically intravascular stents | 6 parts of 98% sulfuric acid, 1 part 37% HCL and 1 part 85% concentrated phosphoric acid | N/A | N/A |  N/A| 
|Surface and biocompatibility study of electropolished CO-Cr alloy L605  [8]| See Rest | 70% methanol and 30% perchloric acid. Type 316 stainless steel was electropolished in 50% phosphoric, 20% sulfuric and 30% distilled water. Later tests were done on L605 alloy with phosphoric acid concentrations ranging from 85-50-15%. They produced different voltage plateaus as a result, but 85% was the best outcome | 0,25,35, 45C | 0.5mm | Processes have been in place since 1935 apparently. Current density decreased with bath temperature. 15mA/cm^2 current density. Other studies show that surface roughness increased as bath temperature was decreased. This study is incredibly thorough. | 


Machine ended up breaking because of voltage spike. Couldn't finish experiment, no results :(

Here's the works I referenced anyway

### Works Cited
[1]https://www.researchgate.net/publication/250350475_Electropolishing_of_Coronary_Stents                          
[2]https://tinyurl.com/57xajaa9                                                            
[3]https://web.eecs.umich.edu/~yogesh/pdfs/conferencepapers/Sensors05_ElectroPolishSteel.pdf              
[4]https://patents.google.com/patent/EP1255880A1
[5]https://pdfpiw.uspto.gov/.piw?Docid=02607722                                      
[6]https://patents.google.com/patent/US8080148B2/en                              
[7]https://patents.google.com/patent/US7357854B1/en                          
[8]https://core.ac.uk/download/pdf/145733058.pdf                                  

### Other Notes

Here are some other notes I took on the experiment - just for transparencies sake. Some tentative procedural ideas here too 
Slight delineations between treatment of 316 stainless steel alloy and Cobalt Chromium which must be considered

* 20-80C ideal temperature range, lower temperatures were seen to be favored for reducing surface roughness in the last study but this information is not corroborated elsewhere

  * Huge distance range for anode/cathode to sample, going from 50mm to 0.5mm.

* Ultimately both of these options are reasonable to test ourselves

  * Phosphoric acid and sulfuric acid, whether alone or combined are seen to be most effective

* Total acid concentration must be around 85%

  * Distilled water/methanol can be used for the rest

  * Concentration of acid is important, >70% is recommended and >99% was used in some studies

* Found new characterization methods after trials are done – mainly to detect surface roughness before and after

* Tentative procedure:

  * Prepare 6:3:1 solution of phosphoric acid graded at >95%, sulfuric acid at the same concentration and 1 part distilled water.

  * Immerse in 500ml of solution, at 40C and position anode and cathode 10mm away from sample

  * Continue experiment for ~90seconds (this was around the average time used among the samples – I never included it in the table but it was frequently mentioned, although it did not have a significant effect on the result)

  * Test using quantifiable surface roughness measures

  * Note: Passivation/pickling in acid/methanol was ignored, but can be used. I saw it commonly paired with the stainless steel procedures but never used with regard to the cobalt chromium ones.
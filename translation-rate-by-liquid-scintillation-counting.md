---
title: "Measuring Translation Rate in Yeast with S$^{35}$ incorporation"
author: "Cat Triandafillou"
date: "12 September 2019"
output:
  html_document: default
  pdf_document: default
nickname: lsc
pdf_typeset: pandoc translation-rate-by-liquid-scintillation-counting.md -V geometry:margin=0.5in  -f
  markdown -t latex -o translation-by-lsc.pdf -s
html_typeset: pandoc translation-rate-by-liquid-scintillation-counting.md -f markdown
  -t html -o translation-by-lsc.html -s
---


This protocol is to measure the translation rate in yeast cells by S$^{35}$ incorporation quantified by liquid scintillation counting.


## Reagents

### Wet reagents

- yeast growth media (SC or YP plus sugar if required)
- S$^{35}$-labeled translation mix (cat. no. **XX**)
- 50% trichloroacetic acid (TCA)
- 5% trichloroacetic acid (TCA)
- 95% ethanol
- Perkin Elmer Ultima Gold F Scintillation Fluid (cat. no. 6013171)
- *Optional:* 20 mg/mL cycloheximide (CHX) in 95% ethanol


### Consumables

- SafeLok Tubes (cat. no. **XX**)
- Scintillation vials and caps (cat. no. **XX**)
- 50 mL conical tubes
- 2.5 cm Whatmann glass filters (cat. no. WHA1823025)
- Whatman #1 filter paper (cat. no. WHA1001824 or WHA1001917)


### Instruments:

- Vacuum Manifold
- Heat block 
- Spinning bucket centrifuge with rotor capable of holding 50 mL conical tubes
- Tri-Carb Scintillation Counter


## Notes

- This protocol is used to measure the translation rate of yeast. If swapping into a new media, do so when preparing radioactive stock in step 2. I've included optional instructions for a cycloheximide treated sample for comparison -- these should give a flat line and will give a sense for the noise in your measurement.
- All timecourses should be background subtracted (media + translation mix alone with no cells) and reported relative to the first timepoint (0 minutes).
- Make sure to do technical replicates -- if performed incorrectly these measurements can be quite noisy -- spread in the tech reps will give you a sense of how well you're doing.


## Procedure:

1. Grow cells
    - The night before, start a 5mL tube of yeast from glycerol stocks or a plate.
    - Next day: dilute cells into 25mL media, 250 rpm shaking at 30 C. Grow until cells reach an OD of 0.1-0.4. When cells have nearly reached this range, do step 2.
    
2. Prepare to measure translation
    - Put 50% TCA on ice -- it should be ice-cold by the time you want to peform the assay.
    - Make a 0.2 mCi/mL solution of the translation labeling mix in water.
        - The final concentration of radioactivity in the media should be 2$\mu$Ci/mL
    - Prepare radiolabeled media and media blanks by mixing 12 mL of media per sample with 120 uL of the stock radioactivity solution. Remove 2x 1 mL aliquots into SafeLok tubes for background measurements (I do to technical reps for each type of media I'm using).
    - If doing the negative control, add 100 uL of 20mg/mL CHX to media. Add carrier (95% ethanol) to the other aliquot of media.
    - Label Whatman paper with each sample and timepoint. Lay them the sheets out on foil and set aside.
    - Assemble vacuum manifold with filters.
    - Set heat block to 70$^{\circ}$C

3. Harvest cells
    - Once cells have reached the target OD, spin down a 10 mL aliquots for each sample/treatment/strain (I usually only do 2-3 at a time, each timepoint will get 2x tech replicates, and 6 samples is the most I want to process at once).
    - Bring pelleted cells to radioactive work room, then decant and resuspend in labeled medium (10 mL for each sample/treatment). 
    - Immediately take 0 minute timepoint, start timer for timecourse, and follow steps below for each timepoint you want to measure (a good place to start is 0, 10, 30 minutes).
    - You can hold cells in the 50 mL conical flask on the benchtop, or move to a 250mL baffled flask and shake at 30$^\circ$C.

4. Process samples
    - Take a 1 mL aliquot (x 2 technical replicates) of each sample/treatment/strain. Place in a SafeLok tube (while these aren't strictly necessary, I find it's better to be safe than sorry when it comes to exploding tubes of radioactive media -- just a personal preference) and add 200$\mu$L ice-cold 50% TCA.
    - Incubate on ice for 10 minutes.
    - Heat at 70$^\circ$C for 20 minutes.
    - Return to ice for 10 minutes.

5. Spot samples onto filters
    - Wet a filter for each tube on the manifold with 1 mL room-temperature 5% TCA.
    - Tap each SafeLok tube gently on the benchtop to encourage drips to condense at the bottom, then load entire sample onto the wetted filter.
    - Wash **three** times with 5mL of room-temperature 5% TCA.
    - Wash two times with 5mL of room-temperature 95% ethanol.
    - Filters can be kept on the manifold until every space is filled, then transferred to the labeled Whatman paper to dry.
    - If more samples are being processed than there are spaces on the manifold, a quick rinse with dI water after removing the filter empirically has been sufficient to prevent crossover between samples when loading a new filter.
    
6. Read samples
    - After filters have dried for at least 24 hours, carefully transfer each to a scintillation vial.
    - Add 5mL of scintillation fluid to each vial.
    - Read on the TriCarb using the program for P$^{32}$.








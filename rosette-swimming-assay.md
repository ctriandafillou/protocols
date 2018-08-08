---
title: "Analysis of Rosette Swimming Behavior"
author: "Cat Triandafillou and Charlotte Strandkvist"
date: "07 August 2018"
nickname: swimmingrosettes
output: html_document
html_typeset: pandoc RNAtagseq.md -f markdown -t html -o rosette-swimming.html -s
pdf_typeset: pandoc RNAtagseq.md -V geometry:margin=0.5in  -f markdown -t latex -o rosette-swimming.pdf -s
---


This protocol is for analysis of the 2D swimming behavior of choanoflagellate rosettes


## Reagents

### Wet reagents

- Lysotracker Deep Red (Invitrogen L12492)
- 10 $\mu$m - 20 $\mu$m non-fluorescent beads (I believe they were made out of polystyrene but not 100% sure)
- 1X chondroitinase
- 1X Artificial Sea Water (ASW)
- Growth media*


### Consumables

- round, 35mm Fluorodish imaging dishes (WPI FD35100)
- 12 mm diameter round glass coverslips


### Instruments:

- Widefield scope with a 10X air objective and filters to visualize far red (or whatever color of lysotracker used) 
- Microcentrifuge 
- Microcentrifuge tubes
- 24-well cell culture dishes


## Notes

- This protocl is for stained rosettes, however I definitely noticed that if too much Lysotracker was used the cells stopped swimming, so reducing the amount as much as possible is probably best. The reason for staining is that it makes segmentation and particle tracking super easy, however if more sophisticated image analysis is used that can segment DIC or brightfield images, then no stain could be used (which would probably be ideal).
- I don't have a good way to quantify the density of the culture of rosettes; we didn't take an OD or anything like that. By visual inspection they were sufficiently dense that 10-30 rosettes could be seen in a small field of view (at 10X magnification) on the benchtop Leica scopes we were using. Cultures that are too dense will increase the likelihood of colliding or overlapping particles, complicating downstream analysis, so err on the side of lower density.
- Larger beads than 10$\mu$m could be used (20 $\mu$m for instance); I think 10$\mu$m is on the small side and cells are a bit over-confined (and more likely to get stuck on the bottom of the dish as a result).
- Rosettes have a tendency to stick to the bottom of the imaging dish and as a result we generally only got 1-2 movies per dish prep. However, the prep (step 3 below) is quite quick so you can do as many as needed pretty easily. 
- *I don't remember what type of media we were using but Ben probably remembers; all that matters really is that the rosettes are happy and that the background is low.



## Procedure:

1. Stain rosettes 
    - Start with a happy non-starved culture of S. rosetta in rosette form. Add 1 uL of Lysotracker per 400 uL of rosette culture and allow to incubate at RT for ~5 min. (We generally did this in 24-well cell culture dish)
    - Transfer to a microcentrifuge tube and spin at 3000-5000 xg for 7 minutes
    - Decant supernatant and wash with ASW
    - Repeat previous two steps once more
    - Resuspend in growth media (you can concentrate at this stage if desired)
    - Add 1-2 uL of beads (you'll need to play around until you get the concentration right, volume will depend on the initial concentration of beads)
    
2. (Optional) Induce Mating
    - Add chondroitinase and allow to incubate for 45 minutes at RT in a well of a 24-well cell culture dish.

3. Prepare sample for imaging
    - Plasma-clean fluorodish (optional)
    - Wash coverslip in 95% ethanol and flame to dry (optional)
    - Drop 6 uL of stained rosettes onto the fluorodish (exact volume will depend on the size of the top coverslip, liquid should reach the edge of the glass but the liquid layer should not be excessively thick, this will increase the z-dimensional area in which the rosettes can swim).
    - Place an ethanol-cleaned coverslip on top of the drop of liquid.

4. Image
    - Image a 10X field of view for 2-3 minutes at 1-2 Hz.


5. Data analysis
    - Image segmentation was done with custom-written scripts in python using the scikit-image package, trajectories were tracked in Matlab using a freely-distributed package, trajectories were cleaned and filtered in R, and then final analysis was done in Matlab using the MSD analyzer package (https://tinevez.github.io/msdanalyzer/).









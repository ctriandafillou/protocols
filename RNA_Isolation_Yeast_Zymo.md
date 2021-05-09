---
title: Wallace Lab Manual for Extraction of RNA from Saccharomyces cerevisiae with Zymo kits
author: Rosey Bayne, r.bayne@ed.ac.uk
date: 6 Dec 2018
nickname: YeastRNAZymo
tags: [RNA]
output: html_document
html_typeset: pandoc RNA_Isolation_Yeast_Zymo.md -f markdown -t html -o RNA_Isolation_Yeast_Zymo.html -s
pdf_typeset: pandoc -V geometry:margin=0.5in RNA_Isolation_Yeast_Zymo.md -f markdown -t latex -o RNA_Isolation_Yeast_Zymo.pdf -s
---

This is a yeast total RNA isolation protocol that works quickly and reliably.
It has no phenol and so can be safely done on the benchtop.
There is an optional methanol fixation step if it is crucial to arrest RNA metabolism very quickly (<1sec).


## Extraction of RNA from Saccharomyces cerevisiae ##

### Growth of cells/fixation ###

1. Grow yeast to mid-log phase (or as desired).

1. If using Methanol fixation, pre-aliquot methanol into 50ml Tubes at a ratio of 2:3 methanol:cells, ensure caps tightly closed and put on dry ice.

1. After growth and treatments, add cells to methanol and mix well (if fixing) and leave on dry ice for a few minutes.

1. Spin cells down at 3000g, 4°C, for 2 mins, decant off the supernatent (if methanol present, dispose of this appropriately), transfer tubes to wet ice and wash cells with 1ml ice-cold milliQ water

1. Transfer cells to 2ml Sarstedt tubes containing 200ul of Thistle Zirconia Beads (0.5mm) and spin at 15,000g for 30s, 4°C, to pellet cells onto the beads.

1. Remove the liquid and snap-freeze the tubes on dry ice. The pellets can be stored below -70°C until ready to extract RNA.


### RNA Extraction ###

*Most spins in this column extraction are >12,000g, all at room temp. or about 20°C.*

1. Add 400ul of Zymo RNA Binding Buffer to the pellets/beads on ice.

1. Transfer the tubes into the PreCellys set for the "EW_Yeast" Protocol (3x 10s pulses with 20s pauses between each pulse)and perform 3 repeats of this protocol, chilling the tubes on ice for 1 min. between each run.

1. Spin the tubes and transfer supernatent to a Zymo-Spin IIIC column in a collection tube then spin for 1 min.  This removes contaminating DNA which binds to the column - **SAVE the flow through!**

1. Add 1 vol. ethanol (95-100%) to the flow through and mix well by pipetting.

1. Transfer to a Zymo-Spin IIC column, spin for 1 min., DISCARD the flow-through

1. Add 400ul DNA/RNA Prep Buffer to the column and spin for 1 min., DISCARD the flow-through.

1. Add 700ul DNA/RNA Wash Buffer to the column and spin for 30s, DISCARD the flow-through.

1. Add 400ul DNA/RNA Wash Buffer to the column and spin for 2 mins to ensure complete removal of wash buffer. Carefully transfer the column to a clean 1.5ml tube.

1. Elute RNA by adding 27ul of nuclease-free water directly to the column matrix and leave to stand for 1 min. at room temp.

1. Spin at 10,000g for 30s, discard the column.

1. Check RNA concentration on the Denovix and quality on the Fragment Analyser.

1. Store RNA below -70°C.


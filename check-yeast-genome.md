---
title: "Checking the result of genomic manipulation in S. cerevisiae"
author: "Cat Triandafillou"
date: "16 January 2019"
output:
  pdf_document: default
  html_document: default
nickname: genome-check
html_typeset: pandoc check-yeast-genome.md -f markdown -t html -o check-yeast-genome.html
  -s
---


This protocol is for checking the results of genomic integration or manipulation of the yeast genome. This protocol assumes that you have putative transformants on plates, and primers that anneal either in the relevant genomic location or up and downstream of an altered gene.

### Notes on primer design

It's a good idea to design your (check) primers so that they anneal up and downstream of the gene you are altering such that they will amplify in both the wild type and any downstream mutant strains. The success of genomic alteration will be determined by the length of the product of this PCR, and can be determined from the length of the native sequence and the altered sequence.

## Reagents

### Wet reagents

**Yeast growth:**

- YPD or dropout media (depending on auxotrophies used)

**DNA precipitation:**

- 200mM lithium acetate (LiOAc), 1% SDS
- 100% ethanol (EtOH)
- 70% ethanol (EtOH) (freshly prepared, cold is okay)
- ddH2O

**PCR:**

- Phusion polymerase
- Phusion HF buffer (haven't tested GC, may also work)
- dNTPs (10mM each)
- Forward check primer (100uM)
- Reverse check primer (100uM)
- Template (from DNA precipitation above)


### Instruments:

- Heat block
- Thermocycler
- Microfuge


## Procedure:

### Quick-and-dirty genome prep

1. Grow cells
    - Pick a single colony for each potential transformant and use to innoculate 5 mL of YPD or SC dropout media.
    - Grow cells overnight at 30&deg;C with 250rpm shaking.
2. Harvest and lyse cells
    - Spin down 100-200&mu;L of dense liquid culture from step 1 at 3000 x g for 1 minute.
    - Decant and resuspend in 100&mu;L of 200mM LiOAc 1% SDS solution.
    - Incubate in a heat block at 70&deg; C for 5 minutes.
3. Precipitate genomic DNA
    - Add 300&mu;L of 100% EtOH and mix
    - Incubate at room temperature for 5 minutes
    - Vortex briefly and then spin at ~15 000 x g for 3 minutes
    - Decant and wash pellet with 70% EtOH
    - Spin at ~15 000 x g for 3 minutes
    - Remove supernatant and dry pellet at 70&deg;C for 1 minute
4. Resuspend DNA and clear protein
    - Resuspend pellet in 100&mu;L of ddH2O.
    - Spin down cellular debris for 15 seconds at ~15 000 x g.

You now have isolated yeast genomic DNA. Note that this preparation is not stable and should immediately be used as a template for your check PCR. Genome preps will last for ~12 hours at 4C, after which you should prepare fresh again. Proceed immediately to next step.

### Checking gene of interest

5. Perform check PCR
    - For each gene you are checking prepare a master mix. The total volume should correspond to 10&mu;L x the number of transformants you are checking plus 10-20&mu;L of extra volume for bubbles. Repeat this for every primer set (gene) you are checking.
    - To make primer mix, add 4 uL of each check primer to 72 uL of H2O (80&mu;L total volume). Store at -20&deg;C.
        
        | Reagent                   |  1 rxn |  5 rxns |
        |---------------------------|--------|---------|
        | 5X HF buffer              |   2 uL |   10 uL |
        | dNTPs (10mM each)         | 0.2 uL |    2 uL |
        | Primer mix (see above)    |   1 uL |    5 uL |
        | ddH2O                     | 5.7 uL | 28.5 uL |
        | Phusion polymerase        | 0.1 uL |  0.5 uL |
        |---------------------------|--------|---------|
        | total                     |   9 uL |   45 uL |
        
        - Mix well
    - Aliquot 9 uL for each reaction
    - Add 1 uL of template from step 4 above.
    - Perform PCR according to Phusion protocol and with appropriate extension time and annealing temperature. No special accomodations need to be made for the small volume (you may actually find that it is more effective than larger volumes).

6. Check results
    - Run 4 uL of each 10 uL reaction above on a 0.5% - 1% agarose gel. Band length and presence corresponds to the success of the genomic integration.

    
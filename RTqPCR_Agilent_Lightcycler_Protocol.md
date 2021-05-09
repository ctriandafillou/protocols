---
title: "RT-qPCR for RNA quantification with SYBR dye"
author: "Edward Wallace"
date: "19 Feb 2019"
nickname: RT-qPCR
tags: [RNA, qPCR, primer design]
output: html_document
html_typeset: pandoc RTqPCR_Agilent_Lightcycler_Protocol.md -f markdown -t html -o RTqPCR_Agilent_Lightcycler_Protocol.html -s
pdf_typeset: pandoc -V geometry:margin=0.5in RTqPCR_Agilent_Lightcycler_Protocol.md -f markdown -t latex -o RTqPCR_Agilent_Lightcycler_Protocol.pdf -s
fontsize: 12pt
papersize: a4
---

This protocol is for RT-qPCR for RNA quantification, using the Superscript IV RT, the Agilent SYBR master mix and Roche Lightcycler instrument. The protocol originates with David Barrass from Jean Beggs' lab. It should work with minor tweaks with equivalent reagents and systems. 
We have not yet documented the data analysis protocol, which we have R code for.


## Notes ##

Reaction volumes depend on plate size and instrument. 10µl reactions work for 96-well plates, on Stratagene or Roche instruments. 5µl (electronic pipette) down to 2uL works in our hands for 384-well plates on the Lightcycler 480. 1µl works for 1536-well plates on the Lightcycler 1536. Loading a 1536-well plate with the Labcyte Echo Liquid handler has been tested by Labcyte to work down at 0.5uL or 0.25uL volume on the LC1536 (Application Note G101).

Perform qPCR on +RT reactions in *technical triplicate*; -RT reactions can be single because usually a problem with -RT will show up in many sample/probe combinations.

For the qPCR plate, it is best to have each row contain a single probe (or sample), and each column a single sample (or probe), so you can load in parallel with an multichannel pipette. We use an Integra Voyager on repeat-dispense setting; fast dispensing just near the edge of the well gives nice reproducible results.

We used Roche Transcriptor RT prior to Superscript IV, and had good performance with both.

A mix of specific reverse primers gives best specificity and was tested extensively by D. Barrass and others for different splice isoforms in yeast. The random primer mix from NEB is more flexible as it allows qPCR for any primer set from the same RT mix, not just those in the primer mix used for RT.

## Components ##

- Sample: RNA resuspended in ddH2O 
- Primers and primer mixes:
    - 4µM mix of *each* primer pair for qPCR
    - EITHER: 2.5µM mix of *all* reverse primers for RT (2.5µM each)
    - OR: 60µM Random Primer mix (35 µM hexamers, 25 µM dT23VN) for RT (e.g. NEB S1330)
- RNase-free H2O
- DNase (TURBO™ DNase, ThermoFisher, *or* DNaseI RNase free 1U/µl, Promega),  10x DNase buffer
- RNase inhibitor (SuperAseIn, ThermoFisher)
- Reverse transcriptase (Superscript IV, ThermoFisher, *or*  Transcriptor, Roche;), 5x RT buffer
- PCR master mix (Brilliant III Ultra-Fast SYBR® Green QPCR Master Mix, Agilent)
- PCR tube strips, 0.2ml each, with lids
- Aerosol resistant (filter) pipette tips


\newpage 


## DNase treatment ##  

1.	Make the Sample mix in a new centrifuge tube (0.2 or 0.5ml), add:-
    - 12.5µg of RNA (down to 1µg is fine, as long as its consistent)
    - H2O to 8µl
    - 1µl of 10x DNase Buffer 
    - 0.9µl of DNase
    - 0.1µl RNase inhibitor
2.	37°C 1hour
3.	75°C 10minutes to deactivate the DNaseI.

## Reverse Transcription ##

1.	Add 2.5µl RT primer mix 
2.	Transfer 5µl (5µg of RNA) of this to 2 new 0.2mL tubes. One for +RT, one for -RT.
3.	Denature the RNA at 70°C for 5 minutes, then in to iced water.
4.	Make RT master mix, per sample:
    - 2µl 5 x First strand synthesis buffer
    - 0.75µl 10mM dNTP mix
    - 1.5µl H2O
    - 0.25µl RNase inhibitor
    - 0.5µl Transcriptor, *or* H2O for a -RT control
5.	Add 5µl of RT master mix to the denatured RNA; this brings the volume up to 10 µl
6.	EITHER 55°C 1-2 hours if using Reverse Primers OR 25°C for 5 minutes followed by 55°C for 1 hour if using Random Primer Mix.
7.	Add 180µl of H2O to the first strand cDNA to dilute the buffer prior the qPCR.

## Quantitative PCR (4µL reaction for 384-well plate)##

1.	Make the qPCR mix for each primer pair, for each well:
    - 1.6µl   2x SyBr Green QPCR mix
    - 0.4µl primer pair mix (4µM each).
2.	Add 2µl of qPCR mix and 2µl of the diluted cDNA to each well of the 384 well plate.
3.	Spin down, mix by rattling plate, spin down again 
4.	Place in PCR machine and run amended Agilent 2-step PCR program:-
    - Taq activation:
        - 95°C  3min 
    - 40 cycles of amplification:
        - 95°C  5sec
        - 60°C  10sec with green fluorescence reading
    - Melt curve
        - Step up to 65°C
        - Ramp up to 95°C at 0.29°C/s
        - 2 readings per second.
5. Save 3 files, ensuring that the date 20yy-mm-dd is in the file title:
    - From the navigator page select your experiment and export data:
        - in native .ixo format
        - full data in plain-text .txt format
    - From the analysis page, go to "Ct values, fit points", calculate Ct values, then export the whole Ct table in plain-text format.

\newpage


## Primer design ##

Primer design for qPCR is crucial and it is important to follow best practices (qPCR primer design revisited, Bustin & Huggett, Biomolecular Detection and Quantification 2017, https://doi.org/10.1016/j.bdq.2017.11.001). Primers need be verified to detect only one RNA species in the sample (melt curve and fragment size), and to accurately report the amount of it (calibration curve).

1. Identify the regions of RNA you want to detect, usually the coding sequence of a messenger RNA. It is best practice to create a snapgene map with the genomic sequence context and relevant features marked. *Beware introns* - check that your primers detect exactly the molecules (spliced or not) that you need them to. 
2. Place the regions you would like to detect in a fasta-formatted plain-text file, with a short informative title for each sequence. Save this with the .fasta extension.
3. Open a primer design tool. We use IDT's PrimerQuest (https://www.idtdna.com/primerquest; or go to Sciquest online ordering and then "Punch-out" to log in to the IDT website), and have also had success with Thermo's Oligoperfect (https://apps.thermofisher.com/apps/oligoperfect/).
4. Paste your fasta-format sequences in the box. Choose your design as "qPCR 2 primers intercalating dyes", and adjust other parameters as necessary. We start with:
    - 50 mM Na+, 200 nM Primer DNA, 3 mM Mg++, 0.8mM dNTP
    - Tm°C: Min 59, Opt 62, Max 65
    - % GC: Min 35, Opt 50, Max 65
    - Primer Size: Min 17, Opt 22, Max 30
    - Amplicon Length: Min 80, Opt 100, Max 120
5. Choose 2-3 primer sets for each region. Download the assay sequences and check their correctness on snapgene. Order them.

## Primer validation ##

Always include at least one positive control primer set that has already been validated and use an RNA sample in which your target RNAs are expressed.

1. Prepare 2x biological replicate RT reactions as described above, including -RT, starting with 10µg of RNA.
2. For each RT reaction, perform a 5X serial dilution using e.g. 20µL of diluted RT product into 80µL ddH2O with fresh tips each time. Also have a -RT control and a no-template control. We usually put these in order:
    - +RT 1:1
    - +RT 1:5
    - +RT 1:25
    - +RT 1:125
    - -RT 1:1
    - H2O
3. Set up a plate with 2-4 technical triplicates and run Agilent 2-step program as above.
4. Check in analysis (we have R code that does this): 
    - Ct values go down log(5)/log(2)-fold per 5X dilution.
    - There are at least 15 Ct values less in -RT and NT controls
    - There is a single peak in the melt curve, at the same temperature for every +RT dilution
    - Ideally, two probes against the same RNA will have the same Ct values.
    - Ideally, run reaction on the fragment analyzer to verify the product length
5. Choose the best primer sets that match the above criteria. Enter all relevant information *only for the chosen primer set* on the lab primers database. Throw away primer tubes for sets that don't work. 
    


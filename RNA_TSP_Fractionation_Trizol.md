---
title: RNA content of RNA-protein assemblies in yeast
author: Edward Wallace
date: 17 Sep 2020
nickname: YeastRNATSP
tags: [RNA, TSP]
output: html_document
html_typeset: pandoc RNA_TSP_Fractionation_Trizol.md -f markdown -t html -o RNA_TSP_Fractionation_Trizol.html -s
pdf_typeset: pandoc -V geometry:margin=0.5in RNA_TSP_Fractionation_Trizol.md -f markdown -t latex -o RNA_TSP_Fractionation_Trizol.pdf -s
---

## Introduction

The aim is to ﬁnd out which RNAs are sequestered in RNA-protein
assemblies, by extracting both supernatant and pellet of 100,000g
fractionated lysate. Varying the centrifugation conditions gives 
different cut-offs to the size of pelletable assemblies, and may be varied.

## Prepare

-   soluble RNA buﬀer (SRB; 20mM HEPES-KOH pH7.4, 120mM KCl, 2mM EDTA,
    0.2mM DTT, 1:100 Protease Inhibitors cocktail IV, 1:100 RNAsin
    plus.) Make stock of salt and buﬀer, then chill and add DTT and
    inhibitors immediately before use.
-   Trizol
-   (alternate) insoluble RNA buﬀer (IRB; 20mM HEPES-KOH pH7.4, 120mM KCl, 10mM
    EDTA, 2% Sarkosyl, 2mM DTT, 1:100 Protease Inhibitors cocktail IV,
    1:100 RNAsin plus.).
-   (alternate) 10X soluble additive buﬀer (SAB; 20% Sarkosyl, 100mM EDTA).
-   Prepare appropriate numbers of safe-lok tubes (2X number of samples)
    loaded with 7mm steel balls, racked in LN, labeled on sides and top.
    Also, labeled tubes for all steps of protocol.
-   Waterbath at desired temperature, ice, chilled centrifuge rotors,
    etc.

[CAUTION:] Trizol, Phenol and Phenol:Chloroform are extremely
dangerous, causing chemical burns, and must be handled in a fume hood.

## Sample growth and lysis

 1. Grow up several cultures of yeast (BY4741) to $4 \times 10^{6}$
    cells/mL ($OD_{600} \approx 0.4$) at 30$\circ$C, in 100ml media in a
    250ml ﬂask.

 2. Transfer $2 \times 10^{8}$ cells to a 50mL conical tube (50 mL of a
    $4 \times 10^{6}$ cells/mL culture).

 3. Spin at 2500g for 30s. Gently decant and discard supernatant.

 4. For short heat shock treatment, hold tube with pellet in waterbath
    at desired temperature for desired time.

 5. Resuspend pellet in 1 ml ice-cold SPB, on ice. Transfer to 1.5mL
    tube, centrifuge 1min, 5,000g, 4$\circ$C. Discard supernatant.

 6. Resuspend pellet in 150 µL ice-cold SPB, on ice.

 7. Drip $2 \times 100\mu L$ of resuspended pellet onto upper wall of 2
    tubes containing steel ball. 1 tube will be used for fractionation,
    the other for total RNA extraction. Goal is to get a nugget of
    frozen material on the wall, and to avoid dripping the material
    around the ball and thus freezing the ball to the bottom of the
    tube; having some LN2 remaining in the tube helps.

 8. Place tubes at -80C; when all LN2 has boiled out of tube
    (listen -- if any popping or hissing, keep waiting), snap tube
    closed carefully, away from other tubes. (Any remaining
    LN2 in tube will cause tube to explode open and ﬁre the stainless
    steel ball into your iPad, brain, colleague, or other important
    equipment.)

Pause point! Sample can be stored at -80C here.

 9. Rack the tube into the PTFE 2mL tube adaptor for the Retsch Mixer
    Mill MM400 (Retsch \#22.008.0005) and submerge the entire assembly
    in LN2. Agitate for $6 \times 90$ seconds at 30 Hz in a Retsch Mixer
    Mill MM400, returning sample holder to LN2 between sessions.
    Complete lysis produces ﬁne snowy powder in the tube.

 10. Remove sample tubes from LN2 and pop the caps to relieve pressure.
    Add 400 µL ice-cold SPB to each tube, patiently thaw on ice. 
    Extract the steel ball with a magnet on the outside of the tube, 
    losing as little sample as possible.
    
Note: We rinse steel balls in methanol and store in 50% ethanol.

 11. Mix capped tube gently by inversion. Remove 100µL as the Total fraction, 
 mix with 300µL Trizol to begin Total RNA extraction.

Note: These RNA samples can be flash-frozen either before or after adding Trizol, and 
processed later.

## Soluble fraction extraction

 12. Spin at 3000g for 30 seconds (clariﬁcation step) to remove whole
    cells and very large aggregates.

 13. Decant clariﬁed liquid into a 1.5mL microcentrifuge tube. If
    desired, keep the pellet and process it alongside the insoluble
    fraction; this end product is the *unclariﬁed fraction*.
    For total RNA samples, skip next spin and move to step
    [16](#x1-400616).

 14. Spin at 100,000g for 20 minutes (ﬁxed-angle TLA-55 rotor at 40,309
    rpm, 4C, in a Beckman Coulter Optimax tabletop ultracentrifuge).

 15. Decant supernatant into a 1.5mL microcentrifuge tube: this is the
    [soluble fraction]{.cmti-10}.

 16. Take 10µL aliquot of soluble fraction and mix with Laemmli buﬀer;
    use this to run a protein gel and assess protein integrity.

 17. Mix 100µL soluble fraction with 3x volume Trizol, to denature proteins and 
    begin RNA extraction. Freeze this. Keep the rest of the fraction in a separate tube
    if desired. []{#x1-400616}

## Insoluble fraction extraction

 18. Violently snap pellet to clear remaining liquid.

 19. To wash the pellet, add 400 µL soluble RNA buﬀer (SRB) and vortex violently. (The
    pellet may not resuspend; that's ﬁne.)

 20. Spin at 100,000g for 20 minutes.

 21. Discard supernatant, clear residual liquid with a hard snap.

 22. Add 100 µL Soluble RNA buﬀer (SRB). Vortex brieﬂy.

 23. Add 300 µL Trizol, vortex until pellet dissolves, begin RNA extraction.

####  RNA extraction

 24. Proceed with RNA extraction using the Direct-zol MiniPrep (R2050), with 50 µg 
 capacity columns, following the manufacturer's instructions. Elute final RNA from
 Total and Soluble fractions in 100µL RNase-free water, and Insoluble in 30µL RNase-free water.
 Ensure that the water sits on the column for at least 1 minute before elution.
 
Note: We have found that the Zymo Direct-Zol kit fast and reliable. 
You may have to play around with the different column sizes and elution volumes to find
a combination that is right for your experiment.
It is also important to wash around the rim of the column to remove Trizol traces.
Often splitting the final elution step into 2 yields more RNA.

Note: DNase treatment is optional, depending on your downstream needs.

Note: Earlier versions of this protocol used a standard phenol:chloroform method with 
ethanol precipitation.
This required "Insoluble RNA Buffer", that has the detergent sarkosyl added along with EDTA.
It is crucial to use Sarkosyl, not SDS, because SDS precipitates in potassium buffers.


####  RNA quality check

 25. For rough quantification, run on a nanodrop or denovix spectrophotometer.
 
 26. To check the quality of the RNA, pour a 1% agarose-TBE gel on
    RNA-free equipment, and run using NEB RNA loading dye. Heat 1X loading
    dye to 95C for 5 minutes, and then cool, to
    reduce the possibility of contamination. Mix 1µL sample,
    10µL 1X loading dye for each well. Perform a 2X serial dilution
    of the sample for more precise quantiﬁcation.

 27. For more precise RNA quantification, run on a fragment analyser or similar. If
 RNA passes quality control, it is ready to be used for RT-qPCR, northern blot, 
 sequencing, etc.


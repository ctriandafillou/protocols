---
title: "Yeast Lysis and Polysome profiling by Sucrose gradient"
author: "Edward Wallace"
date: "21 September 2017"
nickname: Polysome2
tags: [RNA, Ribosome, Polysome, Gradient ]
output: html_document
html_typeset: pandoc Sucrose_Gradient_Protocol_SW40Ti.md -f markdown -t html -o Sucrose_Gradient_Protocol_SW40Ti.html -s
pdf_typeset: pandoc -V geometry:margin=0.5in Sucrose_Gradient_Protocol_SW40Ti.md -f markdown -t latex -o Sucrose_Gradient_Protocol_SW40Ti.pdf -s
---

This protocol is for polysome fractionation by sucrose gradient, to view
translational status of cells and ribosome-association of mRNAs and
proteins, using the BioComp gradient station
(http://www.biocompinstruments.com/). It’s based on the protocols from 
David Weinberg's lab at UCSF, and BioComp instructions.


## Components ##

### Wet ingredients ###

-   Sample: Yeast in desired conditions, about 50mL liquid media, about OD 0.4-0.8.
    
-   Yeast Polysome gradient buffer: 120mM KCl, 7.5mM MgCl2, 20mM HEPES-KOH pH7.5
    (NOTE: Can adjust salt, Mg, pH, etc; common additions are cycloheximide to
    freeze ribosomes in place, heparin to reduce nonspecific RNA-protein binding and
    inhibit RNase, DTT as reducing agent, RNase inhibitors. I've made good
    polysome gradients without any of these at 2-10mM MgCl2, pH 6.5-7.5, with Tris or 
    HEPES. Degraded DTT is bad as it absorbs over the RNA spectrum. This protocol chooses 
    to have heparin, cycloheximide, RNase-In in the lysis buffer, not the gradient buffer.)
    
-   Yeast Lysis buffer (YLB): 120mM KCl, 7.5mM MgCl2, 20mM HEPES-KOH pH7.5, 1% Triton X-100,
    2mM DTT, 100 ug/mL cycloheximide, 20 U/mL SUPERase-In, 1X cOmplete EDTA-free 
    Protease Inhibitor Cocktail, 200 ug/mL heparin (Sigma). Make large stock of KCl, MgCl2, 
    HEPES, Triton. To 50mL gradient buffer stock, on ice, add just before use:
    
        - 1 tablet of Protease inhibitor
        - 100uL of cycloheximide stock (50mg/mL in DMSO)
        - 50uL of SuperAse-In stock (20U/uL)
        - 1mL Heparin stock (10mg/mL)
        - 100uL of DTT stock (1M)

-   50% Sucrose buffer: 0.5g/ml sucrose in polysome gradient buffer, filter sterilized.

-   10% Sucrose buffer: 0.1g/ml sucrose in polysome gradient buffer, filter sterilized.

### Dry ingredients ###

-   BioComp Instruments gradient station.

-   Beckman Coulter S-rated ultracentrifuge, e.g. Optima XP-100.

-   Beckman SW40Ti rotor and SW40Ti tube buckets, kept in cold room. Rotor
    must be placed only on rotor-holding platform, do not scratch speed ring on bottom.

-   Seton open-top polyclear centrifuge tubes SW28.1 (part.no 7042). 
  
## Lyse cells ##  

*CAUTION: Wear safety goggles for this, certainly until lysate is thawed (step 6). Liquid nitrogen,
steel balls, mixer mills, and frozen plastic, can all cause things to fly around and 
damage you, especially your eyes. No explosions: avoid sealing a container with 
liquid nitrogen in it.*

1.  Filter 50mL of cells on a Whatman 0.5um nitrocellulose filter under vacuum. Just 
    before the filter starts to dry, disassemble filter apparatus and throw the filter 
    into a 50mL tube in liquid nitrogen (LN; that you previously prepared). Pour off excess 
    LN from the 50mL tube and allow remaining to bubble off in -80 for 15 mins (!No 
    explosions!). Then cap the tube and keep in -80C until ready for next step.

2.  Thaw 50mL tube with filter 1 min on ice.
    Wash cells off filter with ~1mL ice-cold freshly made YLB. Spin at 4C 
    and remove supernatant. With a wide-mouth tip, resuspend in 100uL YLB and re-freeze in
    balls on the side of 2mL safe-lok tubes in LN, about 200uL material. 
    Uncap tubes in -80C for 5min to allow LN to bubble off (!Still no explosions!).

3.  Add pre-chilled 7mm steel balls to the safe-lok tubes. Cap tubes. Place in to pre-
    chilled vials for mixer mill, Retsch MM400. Chill filled vial (place in LN until 
    boiling stops).

4.  Grind on mixer mill, 4 cycles of 90s x 30Hz. Chill vials in LN after each cycle. You
    can leave tubes in -80 here if needed, which also speeds the thawing in next step.

5.  Remove tubes from vials and place on ice. To each tube add 500uL of ice-cold YLB. 
    Cap tube and mix gently by inversion until sample is thawed. 
    Remove steel ball with magnet, carefully avoiding sample loss.

6.  Remove 100uL of the lysate (true Total), and freeze in a 1.5mL tube.

7.  Clarify spin, 3,000g x 30sec, 4C, to remove debris and unlysed cells. Save pellet for
    troubleshooting and take supernatant into fresh 1.5mL tube (on ice). Record OD on 
    nanodrop, blanking against YLB, if possible. 

8.  Spin out RNA-protein granules and membranes: 20,000g x 10min, 4C. Take supernatant to 
    fresh 1.5mL tube; this will be put on sucrose gradient. Freeze the pellet (P20), 
    containing RNA-protein granules and some membrane-associated components. 
    You can extract RNA and/or proteins from Total P20 while sucrose gradient is running. 

## Prepare gradients ##

1.  Layer sucrose into centrifuge tube: place a polyclear centrifuge tube in the
    marker block. Pour 10% sucrose buffer into the tube up to the top of the marker
    block (roughly 10ml for SW28.1 / 19.5ml for SW28). Load 50% sucrose buffer into
    a 50ml Luer-lok syringe with a layering cannula (BioComp 106-211) attached; with
    the needle pointing upwards, expel air from the needle. Quickly and smoothly
    invert the syringe so the needle is in the bottom centre of the half-filled
    centrifuge tube. Slowly layer 50% sucrose buffer at the bottom of the tube until
    the top of the meniscus is at the top of the tube (roughly 10ml; 19ml for SW28),
    and carefully remove needle from tube. Place the capillary cap on top of the
    tube, ensuring tube is sealed round edges of cap. Repeat for desired number of
    tubes (2, 4 or 6 total), and place filled tubes in magnetic tube rack.

2.  Level the gradient maker platform on the gradient station: turn
    gradient-maker on, choose GMST menu option. The machine will prompt you to level
    the gradient-making platform. Place a bubble level on the platform with axis
    perpendicular to the side plate of the machine and use the UP and DOWN menu
    options to level the platform (the machine should already be level front to
    back); press DONE.

3.  Make gradients: place magnetic tube rack on gradient-making platform. Select
    GRAD option to arrive at gradient menu. The first time, go to LIST and choose
    the SW40Ti rotor option. Press DOWN until arriving at the 10-50% sucrose 
    gradient option, and press USE. If the machine was used for 10-50% sucrose gradient
    immediately previously, simply select LAST from the gradient menu. Press USE to
    start making gradients, which takes roughly 10 minutes. *From this point onwards,
    keep the tubes upright and make no sudden movements with them, so as not to
    disturb the gradient.* Remove capillary cap from tube and, using long-nosed
    pliers if necessary, place in rotor bucket in bucket rack.

4.  Balance the tubes: balance tube 1 with tube 4, 2 with 5, and 3 with 6.
    Placing bucket-tube assembly on scale, remove sucrose gradient from top of tube
    as necessary to ensure paired tubes are within 0.1g in mass.

5.  Prepared gradients can be stored at 4C for a day or two.


## Spin ##

6.  Load sample and assemble rotor: take sample, SW40Ti rotor, 
    bucket rack, and 200 ul pipette to ultracentrifuge. Load sample in
    each tube by placing filled pipette tip in meniscus at side of tube,
    and pipetting slowly; you should see the sample spreading out across
    top of liquid. Gently place lid on tube and screw cap on bucket.
    Hang buckets in numbered slots on rotor, checking that both hooks
    are attached for every bucket.

7.  Set up centrifuge: turn on centrifuge, break vacuum and open
    spin chamber. Select !!!27500 rpm, 2hrs, 4C, with vacuum, on
    centrifuge controls. Place rotor assembly on axle, and seal
    spin chamber. Start centrifuge and fill out centrifuge logbook.
    Check on the centrifuge after 15 minutes to ensure it is
    running smoothly.

8.  After running for 2hrs, the centrifuge takes several minutes
    to brake. Once the centrifuge has stopped spinning, release the
    vacuum, carefully remove rotor from spin chamber and place buckets
    in bucket rack.


## Set up gradient station ##

9.  Take bucket rack with gradients to gradient station, very gently.

10. Turn on the gradient station, the UV monitor, the fraction collector, 
    and the linked computer. Connect the USB cable, start the gradient profiler
    program on the computer and enter appropriate parameters.

11. Flush the line and calibrate the UV monitor: press DRAIN on fraction
    collector. On the gradient station, from the initial screen press FRAC, then
    FRAC. Hold RINSE on gradient station to flush the line. Half-fill a centrifuge
    tube with 10% sucrose buffer, turn front dial so that vacuum plunger descends at
    about 0.5 mm/s. Once plunger is a few cm into liquid and drips are coming out of
    the fraction collector, press AUTO ZERO on the UV monitor.


## Collect fractions ##

For each ultracentrifuge tube with sample:

12. Initialize fraction collector: ensure there are 30x clean 1.5ml
    tubes in the two middle rows of the tube holder. Pre-label the tubes
    if desired. Press END, then START, and make sure drip outlet is
    above tube 0.

13. Remove bucket cap, remove centrifuge from bucket using long-nosed
    pliers, and attach locking top to centrifuge tube. Place tube in
    tube holder on gradient station, locking the tube in place by
    rotating the cap to lock in place. Slide tube holder onto mount on
    top of gradient station with window facing to the right, and turn
    clockwise so window is facing towards you.

14. On gradient station, press FRAC once or twice to get to the fractionation
    menu, then SNGL for single run, and set the parameters to speed = 0.3, distance
    = 3.2 (for SW28.1; 2.6 for SW28), and 31 fractions. Rotate front dial to full
    counterclockwise position. Move plunger downwards by turning dial to the right
    until speed = 1.0 mm/s; move plunger slowly (0.2 mm/s) as it approaches the
    gradient surface, so that you can stop (by turning dial fully left) as soon as
    the plunger has sealed on the gradient. Press RESET on gradient station. In
    subsequent tubes from same run, reset to same position -- i.e. 0.0 mm on display 
    -- from previous tube.

15. On the gradient profiler program on the computer, press RECORD. Then
    press START on gradient station.

16. When finished, remove tubes from fraction collector and label them.
    Press EXIT 3 times on gradient station to return to fraction menu,
    and remove centrifuge tube from holder. *Crucially, save the output
    on the computer, and press NEW RUN to record the next gradient.*

17. Note that the first 1-3 tubes in the fraction collector are usually
    empty, so that the tube number on the rack is offset from
    that reported in the gradient profiler software (BioComp 
    instructions suggest this is solvable: good luck!). Tube 0 according 
    to gradient profiler software is the first filled tube on the fraction 
    collector. It may be easiest to label the tubes accordingly, after the 
    fractions are collected. 


## Cleanup ##

18. Check **all** equipment for potential sucrose gradient spills and
    clean thoroughly with damp cloth and dilute ethanol; this is a very 
    sticky spill. In particular, clean the plunger and flush the tubing 
    with water. 

19. Flush tubing with a full tube of 50% Ethanol to disinfect (DRAIN on 
    fraction collector, from FRAC screen on gradient station lower plunger 
    at about 0.5 mm/s).

20. Store rotor and buckets in cold room, on rotor holding platform.



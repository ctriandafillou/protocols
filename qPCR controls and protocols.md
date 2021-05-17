

![merit badge book cover](/Users/ckatanski/Desktop/Merit Badge Books/qPCR/Art/qPCR cover.png)

#"Just do qPCR"
###A couch to 5k guide for qPCR

#Table of contents
1. Overview 
2. Purchase list
2. Designing and validating probes
3. RNA extraction and preparation
4. Reverse transcription
5. Master mix design
6. PCR cycling
7. Data analysis
8. FAQ
8. Literature

#Overview and purchase list
qPCR is a method to measure relative quantities of nucleic acid species. 
For example, qPCR can be used to measure induction of one gene relative to another during stress in an organism. 

qPCR experiments can be done relatively quickly, but only after significant overhead to setup the method in your hands. For example, primers used for amplification must be rigorously tested and validated for specificity. In this document I will do my best to go from couch to 5k for qPCR. I can't run a marathon - literally or figuratively. 

There are several technical varieties of qPCR based on FRET or fluorophore quenching. Since the dust of the early 2000s has settled, there seem to be 2 dominant methods of qPCR: sybr green, and Taqman. I'm only going to describe Taqman qPCR, but for completeness, a word on sybr green: 

#####Mechanics of Sybr green
Sybr green is a fluorescent dye that is only weakly fluorescent, until it intercalates into double stranded DNA. So with this method of qPCR, one simply uses 2 primers to amplify a specific section of DNA, and measure the change in fluorescence as sybr green intercalates into more and more DNA. However, this dye isn't sequence specific so off-target amplified DNA will also be detected. This method is quite inexpensive since the only cost is primers (cheap) and a master mix with dye (medium). 

#####Mechanics of TaqMan
By contrast, Taqman based qPCR relies on an often overlooked enzymatic activity of DNA polymerase - the 5' to 3' exonuclease activity. This method uses 2 PCR primers to amplify the target DNA as before. However, the fluorescent signal is from a different sources. A third DNA oligo is included in the PCR reaction. This third oligo has a bright fluorophore on the 3' end another molecule that strongly quench that fluorophore on the other end. When the oligo is intact, fluorescence is low. During amplification, this third oligo anneals to the middle of the amplicon. As DNA polymerase moves along the DNA during amplification, the exonuclease activity degrades the annealed third oligo. Degradation allows the fluorophore and quencher to diffuse apart, the once quenched fluoresence now increaes. This method has improved sensitivity compared to sybr green because the third oligo base pairing is specific. However, the third oligo probe is expensive compared to just primers used in sybr green. 

#####Major parts of setting up an experiment
Template preparation is vital to success of a qPCR experiment. I'll assume you're measuring RNA here. So an experiment starts with **RNA extraction**. Followed by **DNase treatment** - regardless of how sure you are that there is no genomic DNA contamination. Then another **RNA clean-up step**. Next RNA is converted into complementary cDNA by **reverse transcription**. Once cDNA is ready, one simply need make a **master mix** to minimize pipetting error, and use it to set up a 96-well plate of qPCR reactions. 

#####Indispensable controls
**First** primer and probe sets must be tested for amplification efficiency. Analysis of qPCR assumes that the number of DNA molecules doubles after each PCR cycle. Don't assume - test with a standard curve of diluted genomic DNA. Also run the PCR product on a gel to visualize amplification products - there should only be one. 

**Second**, reverse transcription (RT) does not convert *all* RNA molecules into DNA with equal efficiency. Abundant genes are can be under represented. Make sure that your reverse transcription is working with proper efficiency by performing RT on a dilution series of an RNA template. 

**Third**, every-time your prepare RNA, it is important to verify that there is no DNA contamination. Save an aliquot of RNA after extraction, but before reverse transcription, to use a the template for qPCR. RNA is not a substrate for DNA polymerase, so no amplification is expected. 

**Four** - I am still the tyro, so contribute if there are other essential controls that I'm not aware of. 

#Purchase list:
* gDNA extraction
	1. Basic phenol
* RNA extraction
 	1. Acid buffered phenol (Sigma P4682-400ML)
	2. Chloroform
	3. 5 M ammonium acetate 
	4. Glycoblue (Thermo Fischer AM9516)
	5. HES buffer
		* 20 mM HEPES, pH 7.5
		* 50 mM EDTA
		* 1% SDS
* DNase treatment
	1. Turbo DNase (Thermo Fischer AM2238)
* RNA clean-up
	1. Zymo RNA clean and concentrate (Zymo R1018)
* Reverse transcription
	1. iScript™ Select cDNA Synthesis Kit, 100 x 20 µl rxns (Biorad 1708897)
* Probes and primers
	1. forward and reverse primers
	2. Taqman probe
* qPCR reaction master mix
	1. IDT 2X Gene Expression Master Mix (IDT 1055772)
* Reaction plates
	1. 96-well plate (Applied biosystems 4346906)
	2. Optical adhessive (Applied biosystems 4360954)


#Designing and validating probes
#####Primer design
PCR is witchcraft and principled design need not be executed by humans. [Fight with tools](https://www.idtdna.com/Primerquest/Home/Index) by letting IDT design your PCR primers and probe for you. Paste your gene sequence into the PrimerQuest tools from IDT, and at the bottom in the section "Choose your design" select "2 primer + probe". The tool will generate a number of possible assays (primers with accompanying probe). Pick one and buy it. Maybe buy more than one if you're in a rush. About 1 of every 2 probes I buy and test are sufficiently efficient. The tools gives a lot of freedoms if you have specific needs. For example I needed to design probes specifically against a 5' UTR of a mRNA, so I fixed the 5' primer, and let the tool make a reverse primer and probe. 
#####Primer ordering
When ordering from IDT check the set(s) that you'd like to purchase. Click add to order, then, when prompted, select "primers and probe" twice in the pop-up menu (don't select assay - which is pre-mixed I think). For probe scale (how much oligo are they synthesizing) select "eco[nomy]". Mini is cheaper, but isn't enough material to do a meaningful amount of experiments. I always choose the FAM dye because it is cheapest. IDT includes two quenchers, by default - I haven't strayed from this default. Synthesis takes about 10 days. 
#####Primer stocks
When primers and probes arrive, resuspend in water, and store at -20 °C. I resuspend primers at 100 uM, and probe at 10 uM in the blue cap IDT tube as my stocks. All protocols and math here assume these concentrations. 

###Validation
The idea here is to run qPCR on a dilutions series of DNA template and verify that the signal changes as expected.

#####What does the data look like?
qPCR measures fluorescence. However, each TaqMan probe has some amount of back group fluorescence. So the qPCR machine measures the starting fluorescence in each reaction, and sets that as a background. Then the machine ultimately reports how many PCR cycles it took for the fluorescent signal to increase to 200 times the background (or some arbitrary number that you could change if so inspired). This data is reproted as the Cq values - the cycle that the signal crossed on. Other machines will report Cp or Cq or Ct or something similar. 

So if you two qPCR reactions with the same primers + probe on a particular template, and a 2-fold dilution of that template, then the Cq value should increase by 1 cycle for the dilution. 

#####Dilutions series
I usually do 4 dilutions: 1:1, 1:10, 1:100, 1:1000. It is also important to include a template of just water as a true negative control - don't skip. The water control is important to get a sense for when random noise dominates. For example, Cq values greater than 30 are generally considered unreliable because even specific efficient probes will amplify something after that many cycles. 

Most of my experiments are done on yeasts RNA. So an ideal test template would be reverse transcribed RNA and make a dilutions series. However, that would require isolating RNA and performing reverse transcription - two places where errors can occur. So to keep it simple, I use yeast genomic DNA to verify primers and probes. Presumably gDNA has all the sequence complexity and opportunities for non-specific amplification that would be seen in RNA too. 

Obtaining clean DNA is important. In this case, clean means free of contaminants which might influence the PCR reaction. Common contaminants are denatured proteins, salts, phenol, or ethanol.

####A protocol to generate high quality gDNA
#####Bust open cells
1. Take 1 mL of high density cells (OD ~4, from an old overnight for example).
2. Pellet the cells at 3000g 1 min. 
3. Decant.
4. Resuspend in 200 uL of 200 mM LiOAc (Lithium acetate), 1% SDS
5. Cook cells at 95 C for 5 min.
6. Add 600 uL of 100% EtOH.
7. Precipitate 10 min -20C.
8. Spin down nucleic acid at 20000g 5 min.
9. Decant.
10. Wash once with 70% EtOH.

#####Remove protein

1. Resuspend 500 uL H2O
2. Add 500 uL of **basic** phenol. Acidic phenol can be used here in a pinch, but basic will give higher yield.
3. Vortex for 5 min
4. Spin 20000g 5 min
5. Move sup into new tube.
6. Extract twice with chloroform.
7. Add 1/10th volume of 5 M NH4OAC (Amonium Acetate), MIX
8. Add 2 volumes of 100% EtOH (~800 uL, because the water volume is 9. reduced during extraction), Mix
9. Precipitate at -80 for 10 min.
10. Pellet nucleic acid 20000g 5 min.
11. Wash 3 times with 70% EtOH (~500 uL is a good amount, although more or less can be used)
12. Throughly air dry pellet
13. Resuspend in 100 uL H2O.
14. Nanodrop - check for phenol (left-most edge of spectrum will be higher than central peak)

I got 100 uL at ~600 ng/uL from old BY4742 cells.

I make tenfold dilutions using large volumes to minimize pipetting error. 180 uL water plus 20 uL of the more concentrated template works well. Vortex like crazy. Change pipette tips. Repeat. 

####Master mix primers + probe
Detection of a piece of DNA by qPCR requires 2 primers to amplify the DNA, and also a “probe” which anneals to the amplified segment and is labeled with FAM dye. The final concentration of primers in the reaction should be between 250 - 1000 nM each according to the IDT PrimeTime master mix protocol. The probe should be at 150 - 250 nM final. I’ve settled on 500 nM for each primer and 200 uM for the probe. My primer stocks are 100 uM and probe stocks are 10 uM. I mix primers and the corresponding probe together into a 3X solution, that add 3 uL of that 3X mix to a a single 10 uL reaction. Concentration in the 3X mix are 1.5 uM for primers and 0.6 uM for the probe. 

* Mix primers and probe into 3X mix:
	* 91 uL H2O
	* 6 uL probe (10 uM stock)
	* 1.5 uL primer1 (100 uM stock)
	* 1.5 uL primer2 (100 uM stock)
	* Vortex

####Anatomy of a qPCR reaction
We use an enzyme master mix from IDT called PrimeTime. Its 2X concentrated. This mix is thick to pipette, so move your thumb slow. 
So a single 10 uL reaction looks like this:

* 10 uL reaction
	* 5 uL PrimeTime mix (2X)
	* 3 ul primer+probe mix (3X mix)
	* 2 uL template

However, adding 3 different materials to each well is a recipe for pipetting error. I prefer to calculate how many reactions I'm doing with each template, and make a master mix of template + PrimeTime enzyme mix, vortex, spin, and aliquot 7 uL to each well. Then go through and add 3 uL of primer+probe mix. I use a piece of cardboard to cover wells on the plate to guide me while pipetting. Counting out loud also really helps. 

####Efficiency
A perfect ten-fold dilution should increase the Cq value by 3.3219 cycles (2^3.3219 ~ 10). If your \( \delta \) Cq value is different, then your probes aren't perfectly doubling the DNA each cycle. Such is life. Efficiencies between 90-100% are generally acceptable. I included some R scripts at the end to compute efficiency — or Google away. 


#RNA extraction and preparation
This protocol will extract RNA from whole yeast cells. This avoids laborious lysis protocols by basically adding phenol directly onto cells and cooking them with SDS for a long time.

If working with cells, pellet and resuspend cells in 400 uL HES buffer in a 1.5 mL epindorf tube.

* HES buffer
	* 20 mM HEPES pH 7.5
	* 50 mM EDTA
	* 1% SDS

####Lysis
1. Add an equal volume of acid-buffered phenol  (400 uL) (pH 4.3 with citrate I think)
2. Vortex to mix and resuspend cells. 
3. Incubate 60 min at 65 C in a heat block with 1500 rpm shaking.

####Phenol extraction
1. Spin 20000g 10 min at 22 C in the refrigerated centrifuge. 
2. Carefully more the top aqueous phase to a new epindorf tube. Avoid a white flake of protein at the water-phenol interface.
3. Save the lower phenol phase for good measure.
4. Add another volume of phenol (400 uL)
5. Vortex vigorously for 2 min (use the shaker in the fume hood)
6. Spin 20000g 22C 10 min. Temperature is important.
7. Carefully move top aqueous phase to a new epindorf tube. Avoid a white flake of protein at the water-phenol interface.
8. Repeat phenol extractions until the white flake of protein is not visible. Two is often enough.

####Chloroform extraction:
1. Add 1 volume of chloroform (400 uL) (the purpose of chloroform is to remove trace amounts of phenol which can ruin enzymes downstream and cause misleading nandrop readings)
2. Vortex as before.
3. Spin 20000g, 22 C, 5 min
4. Carefully move top aqueous phase to a new epindorf tube
5. Repeat chloroform extraction

####RNA precipitation:
1. Add 1/10th volume of 5 M ammonium acetate. Mix
2. Add 2 uL of glycoblue, mix
3. Add 3 volumes of 100% EtOH. Mix
4. Precipitate RNA at -20 or -80&deg;C for 1 hour. Longer times may be necessary for small amounts of RNA.
5. Spin at 20000g, 4 C, 20-30 min -- look for a blue / white pellet of material. This is nucleic acid. Some is DNA, some is RNA.
6. Carefully pipette off the salty ethanol after the spin.
7. Add 500 uL of 70% EtOH (make fresh by mixing 3 mL H2O and 7 mL 100% EtOH - final volume will be slightly less than 10 mL because chemistry)
8. Spin, decant.
9. Repeat 70% EtOH wash.
10. Carefully decant all of the ethanol. Do a quick spin in the microfuge and use a p10 pipette to get all the fluid.
11. Let the pellet air dry with the cap open for ~10 min or until the pellet is white and visibly dry.
12. Resuspend in 50 uL H2O. Mix to resuspend pellet. It may take several minutes of soaking.
13. Nanodrop. Beware phenol contamination. There is an obvious phenol signal by nano drop - google it.
14. This material is suitable for DNase treatment, then reverse transcription, then, someday, qPCR!

After you isolate RNA, from hot-acid-phenol, there is residual DNA that must be digested. Then RNA is converted to DNA by reverse transcription. Reverse transcription product is directly used as a template for qPCR. Necessary steps to prepare RNA are DNase treatment, cleanup, then reverse transcription.

####Dnase treatment
* Follow directions for Turbo DNase treatment
	1. Dilute RNA to 44 uL at <= 250 ng/ul
	2. Add 5 uL of 10X Turbo DNase buffer
	3. Add 1 uL of Turbo DNase
	4. Vortex, spin
	5. Incubate 37C for 30 min

* After digest, put sample through RNA clean and concentrate column;
	1. Bring sample volume up to 50 uL if not already
	2. Add 2 volumes of RNA BINDING BUFFER (100 uL)
	3. Mix
	4. Add an equivalent volume of 100% EtOH (150 uL)
	5. Spin through a spin column, discard the flow-through
	6. Wash with 400 uL RNA PREP BUFFER
	7. Wash with 700 uL RNA WASH BUFFER
	8. Wash with 400 uL RNA WASH BUFFER
	9. Elute in 25 uL H2O
	10. Nano drop


#Reverse transcription
There are three general ways to approach reverse transcription. Reverse transcriptase will use RNA as a template to make complimentary DNA. However, the enzyme requires a DNA primer. What to use as a primer? 

Often people are interested in mRNA, which is *universally* poly-adenylated at the 3' end. Thus oligo-dT can be used as a primer to make cDNA for *all* mRNA. However, if your probes are closer to the 5' end of a transcript, then your efficiency may suffer as the enzyme peters out. Next, people use a mixture of random hexamers to prime everything everywhere. And finally, one can use primers specific for the genes you're interested. The first two methods have the advantage of priming essentially all targets at once. Whereas with gene specific, you can only do qPCR on targets that were primed. 

However, I've discovered critical errors in efficency of priming using random hexamers, especially for high abundance genes. That is, if I do RT on a dilution series of template RNA, then qPCR, my Cq values do not change as expected - more abundant genes appear lower in abundance, presumably because there is not enough of a particular hexamer to prime all the copies. 

The solution here was to use primers specific for each gene I am testing. I made a cocktail containing all of the reverse primers for all of the primer+probe sets that I have. 

* 10X primer cocktail (100 uL volume)
	* 5 uM for each REVERSE primer (5 uL each primer stock (100 uM))
	* Water to a final volume of 100 uL
	* Boil, chill on ice

* A 20 uL iScript reverse transcription reaction with gene specific primers
	1. 4 uL 5X iScript buffer
	2. 2 uL GSP enhancer reagent
	3. 2 uL 10X primer cocktail
	4. RNA template (up to 1 ug, up to 11 uL)
	5. Water up to final volume 19 uL
	6. 1 uL reverse transcriptase enzyme
	7. Vortex
	8. Spin
	9. Incubate 42 C for 60 minutes. 

A 20 uL reaction isn't a lot of volume. Suppose you had to do 20 reactions calling for 2 uL each of cDNA template? I've had perfectly good results adding water directly to the cDNA after RT to dilute. I routinely add 60 uL water for a final volume of 80 uL. I could easily add more without moving my signal outside of a trusted Cq range. 


# Setting up the qPCR plate

* Mix primers and probe into 3X mix:
	* 91 uL H2O
	* 6 uL probe (10 uM stock)
	* 1.5 uL primer1 (100 uM stock)
	* 1.5 uL primer2 (100 uM stock)
	* Vortex

## Anatomy of a qPCR reaction
We use an enzyme master mix from IDT called PrimeTime. Its 2X concentrated. This mix is thick to pipette, so move your thumb slow. 
So a single 10 uL reaction looks like this:

* 10 uL reaction
	* 5 uL PrimeTime mix (2X)
	* 3 ul primer+probe mix (3X mix)
	* 2 uL template

However, adding 3 different materials to each well is a recipe for pipetting error. I prefer to calculate how many reactions I'm doing with each template, and make a master mix of template + PrimeTime enzyme mix, vortex, spin, and aliquot 7 uL to each well. Then go through and add 3 uL of primer+probe mix. I use a piece of cardboard to cover wells on the plate to guide me while pipetting. Counting out loud also really helps. 

## Master Mix Design
Suppose I have 10 different primer+probe sets that I'm interested in measuring. And I have 3 different templates: cells that aren't stressed, mild stress, severe stress. And I want to do all reaction in duplicate. 60 reactions total. 

What is the best way to organize master mixes? One could mix the 2X enzyme mix with primers, and aliquot. Then pipette 2 uL template into each well. However, here the pipetting error is largest in template concentration from well to well - and qPCR is very sensitive to this variation. Better to mix template with 2X enzyme mix and aliquot that way every well has the same amount of template. Then add 3 uL of primer mix to each well - variation here will not affect the signal as much.

For the above example, I would make a master mix of enzymes and template first:

* 22*5 = 110 uL PrimeTime enzyme mix
* 22*2 = 44 uL Template cDNA
* vortex
* aliquot 7 uL to each well

Then add 3 uL of 3X primer mix to each well afterward. Apply optical adhesive film to the top of the 96-well plate when you're done. Be careful to press down on the adhesive tape hard to seal it. Using the capped blunt end of a standard-sized Sharpie is effective. If improperly sealed, edge and corner wells may become unsealed leading to evaporation and nonsense results. 

Finally, it is **essential** to spin the 96-well plate and collect all of the sample in the bottom of the well, and get rid of bubbles. 1000 rpm for 20 sec in a swinging bucket centrifuge is sufficient. 

#PCR cycling

#Data analysis

#FAQ
* **Q: Why do two probes for the same gene have a different Cq?**
* A: Because not all probes are the same. Probes will have different background fluorescence based on length and base composition. Similarly, after degradation by polymerase the fluorophore remains attached to 2-3 bases. These remaining bases can quench fluoresence, G especially. Thus 1 mole of unquenched probe 1 may not be as bright as unquenched probe 2, thus they achieve 200X background at different cycles. 



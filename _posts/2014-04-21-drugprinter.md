---
author: Seb Spain
comments: true
date: 2014-04-21
layout: post
slug: drugprinter
title: DrugPrinter - print any drug instantly, or not
categories:
- Science
- Psuedoscience
- Drug Discovery
---


Over the Easter weekend a rather interesting paper has been doing the rounds of the chemistry community on Twitter. The [paper in question](http://www.sciencedirect.com/science/article/pii/S1359644614001214) is entitled

>	DrugPrinter: print any drug instantly

which is a pretty bold claim that would have learned societies and the Nobel committee clambering over each other to be the first to honour the author. So will this paper be remembered as a breakthrough moment in the history of drug discovery? I'll go through it in some detail before answering that.

The first thing to note is that the article is fundamentally an opinion piece and doesn't contain any experimentation or data. This isn't a problem *per se*, Kolb, Finn and Sharpless' description of [Click Chemistry](http://onlinelibrary.wiley.com/doi/10.1002/1521-3773\(20010601\)40:11%3C2004::AID-ANIE2004%3E3.0.CO;2-5/abstract) and Baran, Maimone and Richter's [protecting group free total synthesis](http://www.nature.com/nature/journal/v446/n7134/full/nature05569.html) have become seminal papers as much for the concepts and methodologies described than the specific syntheses reported. However, those syntheses did demonstrate that the concept worked. So what is the concept proposed here?

>In drug discovery, de novo compounds are usually difficult to synthesize, purify and suffer low yields. Thus, DrugPrinter, a novel protocol for ‘printing’ any compound instantly instead of using a time-consuming, low yield synthesis and without requiring purification and separation of byproduct, is proposed.

"Printing" molecules is not the most novel of concepts but to some extent it's feasible (see the [classic IBM STM logo](http://researcher.ibm.com/researcher/files/us-flinte/stm10.jpg)). So far so good. The introduction covers various background about 3D printing including the rather odd claim.

>Although 3D printer technology is widely used today, even as far as building a house [6] and [7]...

To manage that you would need a really big printer, unless the house is aimed at, say, a hamster. Sadly I can't tell you any more as the cited articles ([here](http://circ.ahajournals.org/content/127/1/e6) and [here](http://www.sciencedirect.com/science/article/pii/S2211802013000235)) appear to have literally nothing to do with 3D printing. We then get a bit more detail about *DrugPrinter*.

> Thus, if DrugPrinter can one day become a reality it will be a huge step forward in drug discovery. The operator needs only to sit down in front of a computer and draw the structure of compound, which is then inputted into the computer, and the system will automatically search by cloud computing for suitable reaction conditions between bond and bond. DrugPrinter technology would be suitable for the initial stage of drug discovery and novel early-stage material production to satisfy the small-volume large-variety production.

So this is a fully automated 3D printer for molecules. How's that going to work then? Luckily the author has provided a step-by-step run through. First you make a mold.

>**Mold for DrugPrinter**

>There must be a mold first before printing the compound. As shown in Fig. 1 [reproduced below], the two half-molds of a tiny reactor are produced from the starting point of the compound 3D structure. The compound should be drawn first (a) and the surface of the target compound can be designed by software (b). Then part of the compound is removed and cut from the surface mold (c) and finally the two half-molds are ready (d).

![Figure 1 from http://www.sciencedirect.com/science/article/pii/S1359644614001214](http://sebspain.co.uk/files/2014/04/21/mold.jpg)

Parts (a) and (b) are reasonable straight forward. Fire up your favourite molecular drawing package, run an energy minimisation and then calculate the Van der Waals surface. We then get take a giant leap to parts (c) and (d) where we magically have a mold and then cut it in half. Thankfully this is covered in more detail later in the paper, the important bit is.

>The mold can be easily made by 3D printing or molecular imprinting technology.

Currently 3D printing is limited to a spacial resolution in the 10s of micron range and therefore isn't suitable. Lithographic techniques can reach length scales in the 10s of nanometre range so are still too big. To produce a suitable mold you'd need resolution on an Angstrom scale, or smaller than a hydrogen atom (Van der Waals radius 1.2 &#8491;). Basically you'd need a *DrugPrinter* to print the mold and you end up in a chicken-egg cycle.

The second method, molecular imprinting, can produce a "mold" on about the right length scale. Molecular imprinting is analagous to producing a mold in traditional metalwork molding. You make the mold by making a polymer in the presence of the molecule that acts as a [template](http://en.wikipedia.org/wiki/Pattern_\(casting\)). When you remove the template molecule you end up with holes of the appropriate shape in the material. So, theoretically molecular imprinting could produce a suitable mold, but *you'll need your target drug to make the mold* so we are back to a chicken-egg situation again.

So the feasibility of the first step in the process is basically zero, at least until we can produce a mold on an Angstrom scale without needing it to be a) made of molecules (maybe an electric/magnetic field in the future?) or b) needing to already have the target molecule.

I'll leave it there for now as it just gets less feasible, if I get time tomorrow I may carry on. In the mean time take a look at [fluorogrol's](http://betterlivingthroughchemistry.ghost.io/drugprinter-or-the-hallucinogenic-goose-that-3d-prints-the-golden-egg/) and [Derek Lowe's](http://pipeline.corante.com/archives/2014/04/21/molecular_printing_of_drug_molecules_say_what.php) posts for their comments on the synthetic parts.

Copyright.
Quoted text and the image are reproduced from Calvin Yu-Chian Chen, *Drug Discovery Today*, 2014. DOI: http://dx.doi.org/10.1016/j.drudis.2014.03.027 and their reproduction here is considered fair use.

License is unknown as the article is Open Access and displays a [ http://creativecommons.org/licenses/by-nc-nd/3.0/]( http://creativecommons.org/licenses/by-nc-nd/3.0/) but the bottom of the article claims Copyright Elsevier All Rights Reserved.

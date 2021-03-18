---
title       : Coevolving trees and the phylogenetic comparative method
subtitle    : 
author      : Breanna Sipley
job         : PhD, Bioinformatics and Computational Biology
logo        : logo.png
biglog      : logo.png
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : prettify  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap, mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Outline

1. Introduction 
2. Developing a new model for a classic hypothesis
3. Quantifying the role of coevolution in lineage diversification
4. Software process meets the scientific method
5. Considerations
6. Summary

--- .segue h2 bg:darkslategray

## Introduction

--- 

## Big questions

- How do ecological interactions shape the diversification of life?

> - Why is parasitism so common?

<img src="assets/img/zombieCrab.png" style="position:absolute; 
float:left; 
right:0px; 
bottom:0px;" width="49%">

<br><br><br><br>
<p style="position: absolute; bottom: 1; left: 5; width: 475px; padding: 0px; background-color: none; font-size: 20px; text-align:right">
<b>Parasitic barnacle (<em>Heterosaccus californicus</em>)<br>
Sheep crab (<em>Loxorhynchus grandis</em>)</b><br>
Photo by Anand Varma, "Mindsuckers"<br>
National Geographic (2014)

</p>

--- &twocolfull

## How may parasites evade coextinction?

*** =left

>"<b>Evolutionary rescue</b> occurs when adaptive evolutionary change restores positive growth to declining populations and prevents extinction" 
>
>  &mdash; Carlson, Cunningham, and Westley (2014)

*** =right
> - Be less virulent
> - Be less host-specific
> - Evolve faster

*** =fullwidth

<br>

--- &twocolfull

## How may parasites evade coextinction?

*** =left

>"<b>Evolutionary rescue</b> occurs when adaptive evolutionary change restores positive growth to declining populations and prevents extinction" 
>
>  &mdash; Carlson, Cunningham, and Westley (2014)

*** =right
- Be less virulent
- Be less host-specific
- Evolve faster

*** =fullwidth

<br>

## Problem

Cool to think about but hard to study

---

## Current methods

> - Distance-based / event-based
> - Do not incorporate reciprocal selective pressures

---

## Current methods

- Distance-based / event-based
- Do not incorporate reciprocal selective pressures
- Neglect antagonistic coevolution btwn parasites & their hosts

![red-queen](assets/img/redQueen.jpeg)
<center>![arms-race](assets/img/arms-race.png)</center>

--- 

## Escape-and-radiate coevolution

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Ehrlich and Raven (1964)<br>Thompson (1994) </p>
</div>

--- &twocol

## Escape-and-radiate coevolution

> "In escape-and-radiate coevolution, coevolution happens at key moments to drive the evolution of plant defenses and insect counter-defenses, and then other speciation processes (e.g., allopatric speciation) come into play as plants and insects increase their geographic ranges or further subdivide resources."
>
>  &mdash; Althoff, Segraves, and Johnson (2014)

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Ehrlich and Raven (1964)<br>Thompson (1994) </p>
</div>

--- &twocol

## Escape-and-radiate coevolution

> "In escape-and-radiate coevolution, coevolution happens at key moments to drive the evolution of plant defenses and insect counter-defenses, and then other speciation processes (e.g., allopatric speciation) come into play as plants and insects increase their geographic ranges or further subdivide resources."
>
>  &mdash; Althoff, Segraves, and Johnson (2014)

*** {name: left}

<H3 align="left">Let's say we start with</H3>
![starting](assets/img/starting.png)
<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Ehrlich and Raven (1964)<br>Thompson (1994) </p>
</div>

--- &twocol

## Escape-and-radiate coevolution

> "In escape-and-radiate coevolution, coevolution happens at key moments to drive the evolution of plant defenses and insect counter-defenses, and then other speciation processes (e.g., allopatric speciation) come into play as plants and insects increase their geographic ranges or further subdivide resources."
>
>  &mdash; Althoff, Segraves, and Johnson (2014)

*** {name: left}

<H3 align="left">Let's say we start with</H3>
![starting](assets/img/starting.png)

*** {name: right}
### Potential scenario
![escape-and-radiate](assets/img/escape-and-radiate.png)
<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Ehrlich and Raven (1964)<br>Thompson (1994) </p>
</div>

--- .segue h2 bg:darkslategray

## Developing a new model for a classic hypothesis

---

## Background

- Exciting progress exploring evolution of host-parasite interactions via ancestral host-repertoire reconstruction

## Problem

- Require a fixed host phylogeny
- Rely on phenomenological interpretations 

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Braga et al (2020, 2021)<br>Hardy (2016)<br>Kaczvinsky & Hardy (2020)</p>
</div>

---

## Objectives

> 1. Develop a novel quantitative model of escape-and-radiate coevolution
> 2. Generate testable macroevolutionary predictions of the consequences of antagonistic species interactions
> 3. Evaluate performance of methods to detect escape-and-radiate coevolution

---

## Quantitative model for escape-and-radiate 

- M1: Assume host speciation higher after parasite extinction
- M0: assume host diversification independent of parasite extinction

---

## Possible evolutionary events

<img src="assets/img/evol.png" class="center" width="86%">

--- &twocol

## Possible coevolutionary scenarios

*** =left

- Successful host escape: <br>parasite extinction
- Successful parasite escape: <br>host-shift

*** =right

<img src="assets/img/coevol.png" style="position:absolute; 
float:left; 
right:5px; 
bottom:15px;" width="80%">

---

## Methods

> - New `R` package `coevolve`
> - Simulate host-parasite coevolution: `cophy`
> - Test driven development: `testthat` and `vdiffr`

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Engelstadter & Fortuna (2019)</p>
</div>

---

## Methods

Parameters of interest
- $\beta$: baseline parasite host shift rate
- $\nu$: parasite extinction rate
- $\kappa$: parasite speciation rate w/in hosts
- $\theta_S$: effect of parasite on host speciation
- $\theta_E$: effect of parasite on host extinction

--- &twocol

## Predictions

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Simulations performed in `cophy`<br>
$\kappa = 0$, $\theta_S = 0.1$, $\beta = 0$<br>
Top: $\nu = 0$<br>
Bottom: $\nu = 2$</p>
</div>

*** =left

- Greater host diversification following parasite extinction under escape-and-radiate 

*** =right

<img src="assets/img/nu.png" style="position:absolute; 
float:left; 
right:5px; 
bottom:15px;" width="50%">

---

## Now what?

> 1. Simulate datasets under null and escape-and-radiate models 
> 2. Analyze datasets using coevolutionary methods
> 3. Identify which coevolutionary methods can tell them apart

---

## Now what?

1. Simulate datasets under null and escape-and-radiate models 
2. Analyze datasets using coevolutionary methods
3. Identify which coevolutionary methods can tell them apart

## Warning

- We're about to go through lots of methods, so hold tight!
- For each, I will
    - Describe method
    - Pose predictions

---

## Time-split

- Compare point statistics before and after "escape" events; compare overall summary statistics

    - Diversification rate ($r$) and relative extinction rate ($\epsilon$)
    - Lineage through time plots
    - Tree shape summary stats (e.g., spectral densities): `RPANDA`

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Morlon et al (2016)</p>
</div>

---

## Time-split: Predictions

- Similar $r$ but higher $\epsilon$ under escape-and-radiate
- More "bursts" evident in LTT plots
- Trees less balanced, more pectinate
- Escape-and-radiate events fall out as peaks in the spectral densities

--- 

## Cophylogeny reconstruction

<b>Distance-based</b>

<img src="assets/img/paco.png" title="plot of chunk paco" alt="plot of chunk paco" width="79%" style="display: block; margin: auto 0 auto auto;" />
<div style="position: absolute; top: 2em; right: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="left">Balbuena et al (2013)<br>Hutchinson et al (2017)</p>
</div>


--- &twocol

## Cophylogeny reconstruction

<b>Event-based</b>

<div style="position: absolute; top: 2em; right: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="left">Engelstadter & Fortuna (2019)<br>Conow et al (2010)</p>
</div>

*** =left

<img src="assets/fig/cophy-sim-1.png" title="plot of chunk cophy-sim" alt="plot of chunk cophy-sim" width="94%" style="display: block; margin: auto 0 auto auto;" />

*** =right

![jane](assets/img/jane.png)

--- &twocol

## Cophylogeny reconstruction: Predictions

*** =left

<b>Distance-based</b>

- `paco` will infer greater phylogenetic congruence under escape-and-radiate

*** =right 

<b>Event-based</b>

- `Jane` will underestimate host-shift events under escape-and-radiate

---

## Gene tree-species tree evolution

- Based on Duplication-Transfer-Loss model 
- Duplication ~ parasite speciation<br>Transfer ~ host-shift<br>Loss ~ parasite extinction

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Satler et al (2019)<br>Dismukes et al (2020)</p>
</div>

---

## Gene tree-species tree evolution

- Based on Duplication-Transfer-Loss model 
- Duplication ~ parasite speciation<br>Transfer ~ host-shift<br>Loss ~ parasite extinction

## Predictions

- DTL will underestimate transfer events under escape-and-radiate

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Satler et al (2019)<br>Dismukes et al (2020)</p>
</div>

--- .segue h2 bg:darkslategray

## Quantifying the role of coevolution <br>in lineage diversification

---

## Background

> - Few phylogenetic studies interpret their observations through lens of coevolutionary theory
> - Coevolutionary theory &#8594; interesting predictions that can be tested at the macroevolutionary scale

---

## Hypotheses

> 1. Antagonistic coevolution promotes lineage diversification
> 2. Mutualistic coevolution does not promote, and may even restrict, the diversification of species

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Yoder & Nuismer (2010)</p>
</div>

---

## Good news

Many publicly available datasets exist to test these exciting predictions 

## Objective

Quantify the effect of coevolution on lineage diversification using phylogenetic meta-analysis

---

## Synthesis<br>workflow

- Preferred Reporting Items for <br>
Systematic Review and <br>
Meta-Analysis (PRISMA) protocol
- `metagear`

<img src="assets/img/prisma.png" style="position:absolute; 
float:left; 
right:0px; 
bottom:0px;" width="50%">

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Moher et al (2015)<br>Lajeunesse (2016)</p>
</div>

---

## Scoping 

- Two monophyletic groups A and B 
- Open Tree of Life
- Interaction Web Database
- Global Biotic Interactions database

---

## Searching

- Develop search terms - yikes 
- Librarian &#10003;
- Validate search terms 

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Zeng & Wiens (2021)</p>
</div>

---

## Screening

- Recruit help!  (GEM3 SARE funding x2)
- `metagear`: `effort_distribute`, `abstract_screener`
- Follow criteria for conducting transparent meta-analyses on open data

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Culina et al (2018)<br>Lajeunesse (2016)</p>
</div>

---

## Coding and extracting data

- Open Tree of Life in `R`: `rotl` 
- Phylogenetic heterogeneity!  Cool and also hard
- Divergence time estimates: TimeTree
- Phylogenetic similarity: `paco`

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Michonneau, Brown, & Winter (2016)<br>Kumar et al (2017)<br>Hutchinson et al (2017)</p>
</div>

---

## Coding and extracting data

- Estimate speciation and extinction rates: `GeoHiSSE`
- Repeat analyses in Zeng and Wiens (2021)

## Effect size

Binary log-response ratio 

$$\log_2(R)$$

$R$ is ratio of the two diversification rates

---

## Meta-analysis

- Goal of a meta-analysis: get average weighted effect size
- Evaluate homogeneity of effect sizes and test for bias

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Lajeunesse (2011)</p>
</div>

---

## Phylogenetic meta-analysis

- Additional source of bias: pooling effect size data from multiple taxa 
- Account for phylogenetic correlations among effect sizes: `PhyloMeta` and `metagear`
- Based on the generalized least squares (GLS) approach

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Adams (2008)<br>Lajeunesse (2009)<br>Lajeunesse (2011)<br>Lajeunesse (2016)</p>
</div>

---

## Phylogenetic meta-analysis

Effects sizes are pooled, weighted by variance-covariance matrix $W$

$$
W = DPD
$$
$P$ diagonal matrix of phylogenetic correlations 

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Lajeunesse (2009)</p>
</div>

---

## Phylogenetic meta-analysis

Effects sizes are pooled, weighted by variance-covariance matrix $W$

$$
W = DPD
$$
$P$ diagonal matrix of phylogenetic correlations 

If $P$ is identity matrix, then studies are independent

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Lajeunesse (2009)</p>
</div>

---

## Challenge

- We have two trees

## Possible solutions

- Make one tree and account for divergence between interacting phylogenies?
- Extend framework to include cophylogenetic reconciliations?

---

## Focus on one partner

- Test importance of type of interaction over other characteristics as predictor of diversification
- Phylogenetic divergence btwn interacting phylogenetics, taxonomic identity, relationship to partner, relative extinction rates

## Predictions

- Parasitism affects diversification differently in plants than in animals
- Parasitism affects diversification differently in hosts than in parasites 

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Carmona, Lajeunesse, & Johnson (2011)</p>
</div>

--- .segue h2 bg:darkslategray

## Software process meets the scientific method

---

## A train-the-trainer model of computational empowerment for biologists

> - Technology &#8594; data!
> - Cumbersome datasets
> - Foundational computational tools &#10003;
> - Now what &#63;

<img src="assets/img/software.png" style="position:absolute; 
float:left; 
right:0px; 
bottom:50px;" width="100%">

---

## Objective

To specifically tailor development of a new <b>Vertically Integrated Project (VIP) course</b> focusing on how software process tools such as <em>version control</em> and <em>test-driven development</em> can help meet the needs of researchers while supporting the reproducibility of science

---

## Objective

To specifically tailor development of a new <b>Vertically Integrated Project (VIP) course</b> focusing on how software process tools such as <em>version control</em> and <em>test-driven development</em> can help meet the needs of researchers while supporting the reproducibility of science

## Overview

> - Work with EPSCoR researchers to identify a suitable problem and dataset
> - Create modules to walk through solving problem using software process
> - Self-sustaining by design
> - Help train a diverse workforce

---

## VIP <br> Phases 

<img src="assets/img/modules.png" style="position:absolute; 
float:right; 
left:50px; 
bottom:50px;" width="22%">

---

## Conceptual<br>framework

<img src="assets/img/conceptual-framework.png" style="position:absolute; 
float:left; 
right:0px; 
bottom:0px;" width="73%">

<img src="assets/img/modules.png" style="position:absolute; 
float:right; 
left:50px; 
bottom:50px;" width="22%">

---

## Learning objectives

<img src="assets/img/learning-objectives.png" style="position:absolute; 
float:left; 
right:0px; 
bottom:0px;" width="82%">

---

## Recruitment plan

- Cohort A
    - Certified Carpentry instructors
    - IMCI-spnosored Carpentries workshops
    - Flyer distributed via COGS, IBEST, IMCI, CNR, EPSCoR GEM3
- Cohort B
    - Undergraduate research
    - SSS-TRiO
    - SACNAS
    - Palouse Pathways

---

## Research goals

- Consult with EPSCoR affiliates to identify a suitable research problem to tackle via this course module

> - Erect a novel pedagogical framework for teaching computational skills to biological researchers
> - Science education paper introducing the new train-the-trainer model, how it was implemented, and how it went

---

## Data acquisition

- Survey participants' confidence before and after course in 
    - Writing code to analyze large, cumbersome datasets
    - Teaching computational skills to novices and intermediate learners 

> - Collaborate with others to identify other metrics for comparison (e.g., extent to which learning objectives met) 
> - Examine the reproducibility of code
> - Assess extent to which product meets the desired requirements 

---

## Ethics

- IRB (Human Research Protections) Coordinator at UI
- Likely will fall under Exempt Category 1 or 2
- Human subjects training
- All research data will be handled and stored securely
- All participation will be voluntary (Informed Conent Form) 
- Responsible Conduct of Research training 

--- .segue h2 bg:darkslategray

## Considerations

---

## Funding

> - Secured

> - Fending

> - Promising

---

## Future directions

> 1. Assess the extent to which, and under what circumstances, escape-and-radiate coevolution emerge across the tree of life
> 2. Extending `coevolve` to include additional models

--- .segue h2 bg:darkslategray

## Summary

---

## Intellectual merit

> 1. First-author paper evaluating relative performance of methods in detecting escape-and-radiate coevolution
> 2. Phylogenetic meta-analysis quantifying role of coevolution on lineage diversification
> 3. Pedagogical innovation paper introducing train-the-train model of computational empowerment for biologists

---

## Broader impacts

> 1. `R` package for simulating and detecting escape-and-radiate coevolution
> 2. Cophylogenetic comparative framework
> 3. Empowerment of more diverse and inclusive professoriate
> 4. Reproducibility of science 
> 5. Increased computational literacy of biologists
> 6. Independent research experiences for 3 undergraduates
> 7. Doctoral training for me

--- &twocol

## Acknowledgements 

*** {name: left}
<b>Committee</b><br>
Luke Harmon<br>
Christine Parent<br>
Aleta Quinn<br>
Jack Sullivan

<b>Rockstar labmates</b><br>
Kristen Martinet, Orlando Schwery

<b>BCB</b><br>
Lisha Abendroth<br>
Dave Tank

*** {name: right}
<b>Resources</b><br>
NSF GRFP, Idaho EPSCoR GEM3 VIP<br>
UI IBEST CRC<br>
Raven Scholars, CDAR, CTC, COGS

<b>Snorks</b><br>
Kelly Martin, Ian Oiler, Malia Santos, David Sneddon

<b>Co-working friends</b><br>
Chava Castaneda, Clint Elg, Yesol Sapozhnikov, Courtney Schreiner, Hannah Smith, Amanda Stahlke

--- {
 tpl: thankyou,
 social: [{title: email, href: "sipl0809@vandals.uidaho.edu"}]
}

## Thank You

<br>
 

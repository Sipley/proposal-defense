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

## Favorite parasite

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

---

## How may parasites evade coextinction?

- Be less virulent
- Promote host reproduction
- Be less host-specific
- Evolve faster

![red-queen](assets/img/redQueen.jpeg)

---

## Background

- Recent exciting progress: explore evolution of interactions in model-based framework 

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px">Braga et al (2020, 2021)<br>Hardy (2016)<br>Kaczvinsky & Hardy (2020)</p>
</div>

<img src="assets/img/intmat.png" style="position:absolute; 
float:left; 
right:0px; 
bottom:25px;" width="60%">

---

## Background

- Recent exciting progress: explore evolution of interactions in model-based framework

## Problem

- Rely on analogy
- Require a fixed <br>host phylogeny

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px">Braga et al (2020, 2021)<br>Hardy (2016)<br>Kaczvinsky & Hardy (2020)</p>
</div>

<img src="assets/img/intmat.png" style="position:absolute; 
float:left; 
right:0px; 
bottom:25px;" width="60%">

---

## Gene tree-species tree evolution

- Based on Duplication-Transfer-Loss model 
- Duplication ~ parasite speciation<br>Transfer ~ host-shift<br>Loss ~ parasite extinction

<br>

`DTL will underestimate transfer events under escape-and-radiate`

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Satler et al (2019)<br>Dismukes et al (2020)</p>
</div>

---

## Discrete biogegraphy

- Host tree
- Parasite tree
- Interaction <br>matrix

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Braga et al (2020)</p>
</div>

---

## Models of diversification

<b>BiSSE</b>

Code HP as binary vector of length(number of H)

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Maddison, Midford, & Otto (2007)</p>
</div>

---

## Models of diversification

<b>BiSSE</b>

Code HP as binary vector of length(number of H)

- `Branches descending from nodes with fewer parasite associations occupy the accelerated rate class`
- `Overestimate significance`

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Maddison, Midford, & Otto (2007)</p>
</div>

---

## Models of diversification

<b>HiSSE</b>

<img src="assets/img/hisse.png" style="position:absolute; 
float:left; 
right:5px; 
bottom:95px;" width="65%">

<div style="position: absolute; top: 2em; right: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Figure directly from<br>Beaulieu & O???Meara (2016)</p>
</div>

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Rabosky and Goldberg (2017)</p>
</div>

---

## Models of diversification

<b>HiSSE</b>

<img src="assets/img/hisse.png" style="position:absolute; 
float:left; 
right:5px; 
bottom:95px;" width="65%">

<div style="position: absolute; top: 2em; right: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Figure directly from<br>Beaulieu & O???Meara (2016)</p>
</div>

- `Low power`<br>
`to detect` <br>
`trait-dependent`<br>
`extinction` <br>
- `Infer changes in`<br>
`rate classes w/`<br>
`greater certainty`<br>
`for H than P`

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Rabosky and Goldberg (2017)</p>
</div>

---

## Models of diversification

<b>Geo(Hi)SSE</b>

Likelihood calculated using DEC only reflects evolution of ranges (host-repertoires) and treats trees as fixed, which can be problematic when jump dispersal events are allowed

- Apply geographic SSE models: `GeoSSE`
- Allow geographic range evolution independent of focal trait: `GeoHiSSE`

<div style="position: absolute; bottom: 5em; right: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Caetano, O'Meara, & Beaulieu (2018)<br>Ree & Sanmartin (2018)<br>Goldberg, Lancaster, & Ree (2011)</p>
</div>

---

## Models of diversification

<b>Geo(Hi)SSE</b>

Likelihood calculated using DEC only reflects evolution of ranges (host-repertoires) and treats trees as fixed, which can be problematic when jump dispersal events are allowed

- Apply geographic SSE models: `GeoSSE`
- Allow geographic range evolution independent of focal trait: `GeoHiSSE`

`GeoHiSSE will reconstruct coevolution under escape-and-radiate most accurately`

<div style="position: absolute; bottom: 5em; right: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Caetano, O'Meara, & Beaulieu (2018)<br>Ree & Sanmartin (2018)<br>Goldberg, Lancaster, & Ree (2011)</p>
</div>

---

## Models of diversification

<b>HiSSE</b>

Diversification models that do not account for unmeasured traits are inappropriate to assess relationships between mutualism and ant diversification

- Rejected cooperate-and-radiate
- Lineages first radiated, then evolved plant mutualism

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Kaur et al (2019)</p>
</div>

---

## Models of diversification

<b>MuSSE</b>

- Allow exploration of interactive effects of traits
- Include category such as host-specificity or counterdefense arsenal

Test for interaction btwn chemical defense and conspicuous coloration on diversification. Found chemical defense also increased extinction rate, leading to lower net diversification. Argue escape-and-radiate only includes speciation, neglecting extinction dynamics.

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">Arbuckle & Speed (2015)</p>
</div>

---

## Interpreting simulation model results

- Statistical power determined by replications, and simulations can have high replications (p-val tiny)
- Null hyp known to be false at the outset
- Testing a known-to-be-falses hypothesis is not useful
- Better: comparing magnitude of differences btwn sims
- Suggested: Komolgorov-Smirnov test to compare two distribution generated by data; focus on effect size or test statistic
- ANOVA useful for partitioning variance and calc effects sizes - don't report p-val

<div style="position: absolute; bottom: 5em; left: 5em; font-weight: bold; color: #fff; font-size: 11px;">
<p style="font-size: 20px"; align="right">White et al (2014)</p>
</div>

---

## P matrix challenge

- We have two trees

## Possible solutions

- Make one tree and account for divergence between interacting phylogenies?
- Extend framework to include cophylogenetic reconciliations?

---

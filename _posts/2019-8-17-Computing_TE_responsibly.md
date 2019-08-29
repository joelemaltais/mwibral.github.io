---
layout: post
mathjax: true
title: Climate-crisis aware computation of transfer entropies!
---
TLDR; Multivariate transfer entropy computations consume enormous amounts of energy. below are some thoughts on how to reduce it or to avoid it altogether. 

Transfer entropy measures the information transferred from a source to a target. when systems have mutliple components that exchange information it is important to keep track of which route infomration takes from one part of the system (the source) to another (the target), and to keep track of redudant sources of information and of sets of sources that can only be detected when considered jointly as an information source. To solve these problem a conditonal transfer entropy (or multivariate transfer entropy) can be computed.

Unfortunately, full blown, multivariate computations of transfer entropies consume a lot of time and energy. With our current energy mix they also tend to produce a lot of CO2. Below are some hints to reduce the damage done by computing TEs:
- Think twice whether you need to compute a full model-free transfer entropy to answer your scientific question. Often a linear approximation such as Granger causality will do and save a lot of time and energy.
- Think about wether you only need to know whether information is transferred from A to B, or whether you'll need to know the exact path that information transfer takes. If you don't need to know the exact path, then computing the *bivariate* TE is sufficient, which is orders of magnitude faster.
- Think about computing in a data center powered by renewable energy sources.
- Funny suggestions, but serious, nonetheless: Think about computing mostly in winter, such that your workstations or little cluster can help heating your office. This way you'll save a little of the energy invested in heating.
- Always try to compute on the most efficient machine(s) available, even if this means a little more effort (e.g. tranferring data, or doing some benchmarking beforehand) 
- If you have time and multiple datasets compute mTE for some datasets from parts of different size. If mTE analyses stabilize before using the full dataset you may consider using only parts of that smaller size (you may also have the additional benefit of doing test-retest reliability analyses). As the computation scales with n^2, where n is the number of samples, you will save a lot of time and energy.
- Help us making our code more efficient by contributing to IDTxl. W ethink there is still untapped optimization potential in our GPU codes.
- (to be continued/updated)

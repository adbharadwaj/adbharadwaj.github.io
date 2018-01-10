---
layout: post
title:  "Visualizing Protein-Protein Interaction Networks using Simulated Annealing Algorithm"
date:   2018-01-10 13:59:39 -0500
categories: graphspace feeds
tags: [GraphSpace,Layouts,Simulated Annealing,PPIN]
---

Networks have become ubiquitous in systems biology and visualization is a crucial component in their analysis. In this blog post I am going explore the power of simulated annealing algorithm in laying out PPINs. The algorithm is named after [annealing in metallurgy](https://en.wikipedia.org/wiki/Annealing_(metallurgy)), a technique that involves heating a material above its recrystallization temperature, maintaining a suitable temperature, and then cooling. The Simulated
Annealing (SA) algorithm represents the space of the visualization problem as a set of layouts (states) each one with associated energy, and it tries to find the layout (state) with minimum energy (i.e. below a threshold) that represents a potential network layout. 

The associated energy function can be used to optmize any graph drawing constraint. For example, a common constraint is to decrease the number of edge crossings. [Davidson and Harel]() incorporated the following constrainsts to draw graphs "nicely".

1. Distribute nodes nicely.
2. Make edge lengths uniform.
3. Minimize edge-crossings.
4. Prevents nodes from coming too close to edges.
5. Keep the nodes inside within the canvas borders.

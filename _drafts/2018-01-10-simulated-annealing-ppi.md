---
layout: post
title:  "Visualizing Protein-Protein Interaction Networks using Simulated Annealing Algorithm"
date:   2018-01-10 13:59:39 -0500
categories: graphspace feeds
tags: [GraphSpace,Layouts,Simulated Annealing,PPIN]
---

Networks have become ubiquitous in systems biology and visualization is a crucial component in their analysis. In this blog post I am going explore the power of simulated annealing algorithm in laying out PPINs. The algorithm is named after [annealing in metallurgy](https://en.wikipedia.org/wiki/Annealing_(metallurgy)), a technique that involves heating a material above its recrystallization temperature, maintaining a suitable temperature, and then cooling. The Simulated
Annealing (SA) algorithm represents the space of the visualization problem as a set of layouts (states) each one with associated energy, and it tries to find the layout (state) with minimum energy (i.e. below a threshold) that represents a potential network layout. 

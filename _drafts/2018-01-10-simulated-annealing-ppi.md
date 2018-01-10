---
layout: post
title:  "Visualizing Protein-Protein Interaction Networks using Simulated Annealing Algorithm"
date:   2018-01-10 13:59:39 -0500
categories: graphspace feeds
tags: [GraphSpace,Layouts,Simulated Annealing,PPIN]
---

Networks have become ubiquitous in systems biology and visualization is a crucial component in their analysis. In this blog post I am going explore the power of simulated annealing algorithm in laying out PPINs. The algorithm is named after [annealing in metallurgy](https://en.wikipedia.org/wiki/Annealing_(metallurgy)), a technique that involves heating a material above its recrystallization temperature, maintaining a suitable temperature, and then cooling. The Simulated
Annealing (SA) algorithm represents the space of the visualization problem as a set of layouts (states) each one with associated energy, and it tries to find the layout (state) with minimum energy (i.e. below a threshold) that represents a potential network layout. 

Essentially simulated annealing performs the following steps:

- Step 1: Randomly choose an initial layout.
- Step 2: Repeat Step 3 - 4 for fixed number of steps.
- Step 3: Compute a new neighboring (layout) state w.r.t current state (layout). 
- Step 4: If the new state is better than the current state, move to the new state. Otherwise, move to the worse new state with a probability which decreases with temperature.
- Step 5: Decrease the temperature.
- Step 6: If termination rule is satisfied, stop; otherwise go back to Step 2. Possible termination rules are: average change in energy function in one iteration falls below a user-defined threshold or number of iterations exceed maximum number of iterations defined by the user.

The associated energy function can be used to optimize any graph drawing constraint. For example, a common constraint is to decrease the number of edge crossings. [Davidson and Harel]() incorporated the following constraints to draw graphs "nicely".

1. Distribute nodes nicely.
2. Make edge lengths uniform.
3. Minimize edge-crossings.
4. Prevents nodes from coming too close to edges.
5. Keep the nodes inside within the canvas borders.

But these constraints do not cause the resultant layout to mimic the underlying biological knowledge. For instance, in a PPIN where a node represents a protein and an edge represents an interaction or control relationship between two proteins, it
may be important for a layout to reflect the locations of the proteins within the cell, or the communication of a signal from
the exterior of a cell to its nucleus. In this blog, I am going to explore the following constraints which mimic the underlying biological knowledge.

1. Arrange the receptor nodes at the top of the layout.
2. Arrange the transcription factor nodes at the bottom of the layout.
3. Arrange nodes with similar biological properties together.


For the purpose of demo, I have used the Cytoscape layout extension - [cytoscape.js-simulated-annealing]() to apply simulated annealing on a given graph. The library allows us to include user defined energy functions and other useful customizations.

In the rest of the blog I will provide a series of examples to demonstrate how simulated annealing can be used to mimic biological constraints mentioned above. First I will give a typical example of nicely drawn graph showcased by [Davidson and Harel](). 

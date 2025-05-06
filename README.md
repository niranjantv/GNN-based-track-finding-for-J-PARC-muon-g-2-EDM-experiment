# GNN-based Track Finding for J-PARC Muon g-2/EDM Experiment

This repository contains code for Graph Neural Network (GNN) based track finding, developed as part of simulation and analysis studies for the J-PARC Muon g-2/EDM experiment.

## Overview

The goal of this project is to reconstruct particle tracks from detector hit data using GNNs. The pipeline follows these main steps:

1. **Embedding Space Creation**  
   - A fully connected Artificial Neural Network (ANN) is first trained to embed hit points into a latent space where spatial proximity correlates with track membership.

2. **Graph Construction**  
   - Using the embedded coordinates, graphs are constructed with an **epsilon-ball query** method to connect nearby hits likely belonging to the same track.

3. **Edge Refinement**  
   - The initially generated graph is filtered using **sigmoid-based spatial and temporal filters** to remove spurious or low-quality edges.

4. **GNN-based Graph Merging**  
   - A GNN model is trained on these refined graphs to merge fragments and reconstruct full tracks, even in high-pileup conditions.


## Files

- **`GNN-algorithm.ipynb`**  
  This notebook contains:
  - Code for training the ANN model  
  - Graph construction using epsilon-ball query  
  - Edge refinement techniques  
  - Training and evaluation for GNN-based graph merging


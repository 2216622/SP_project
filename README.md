# AI-Based Dynamic School Bus Routing Smart System for Optimized Routes and Lower Fuel Consumption

This project presents an AI-driven system designed to cluster students geographically and generate optimized school bus routes. The main objectives are to reduce fuel consumption, minimize total travel time, and satisfy maximum ride-time constraints for students.

## Overview of the System

The system takes as input a merged CSV file that contains the school and student data (coordinates and distance/time matrices). It then:

- Groups students into feasible bus clusters.
- Builds and optimizes separate routes for morning and afternoon trips.
- Checks whether the maximum allowed ride time per student is respected.
- Visualizes the resulting routes through an interactive web interface.

## Clustering Module (K-Means)

The clustering stage uses the K-Means algorithm to assign students to buses based on their locations.

Main characteristics:

- Minimum number of students per bus: 14  
- Maximum number of students per bus: 44  
- Internal clustering quality metrics:
  - Silhouette Score
  - Calinski–Harabasz Index
  - Davies–Bouldin Index

The system automatically selects the number of buses (K) by ranking candidate solutions according to these internal metrics.

## Routing Optimization Module

For each bus cluster, the system generates optimized morning and afternoon routes.

Techniques used:

- Nearest Neighbor for constructing an initial route.
- Removal operators (Random Remove, Worst Remove, Shaw Remove) to explore new solutions.
- Regret-2 insertion to reinsert removed students in a cost-effective way.
- Simulated Annealing acceptance to allow controlled exploration of worse solutions.
- Final local improvement using the 2-Opt algorithm.

A key constraint is enforced:

- Maximum student ride time: 90 minutes.

For every route, the system reports:

- Total route time.
- Maximum student ride time.
- Total route distance.

## Web Interface (Gradio)

The project includes a multi-page Gradio interface:

- A welcome page introducing the system.
- A page to upload the merged CSV file and run the clustering step, with a summary of students per bus.
- A page to select a bus and mark present or absent students.
- A page to generate and display morning and afternoon routes, including route plots and basic statistics.

## Requirements

The following Python packages are required:

```bash
pip install gradio numpy pandas scikit-learn matplotlib nest_asyncio


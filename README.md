AI-Based Dynamic School Bus Routing Smart System for Optimized Routes and Lower Fuel Consumption
This repository presents an AI-driven system designed to cluster students geographically and generate optimized school bus routes.
The goal is to reduce fuel consumption, minimize total travel time, and ensure student ride-time constraints are respected.
The project integrates several components, including clustering, routing optimization, constraint handling, and an interactive web interface.
Contents
1. Clustering Module
This module uses K-Means to assign students into feasible bus clusters.
Key characteristics:
Capacity constraints:
Minimum students per bus: 14
Maximum students per bus: 44
Internal cluster evaluation metrics:
Silhouette Score
Calinski–Harabasz Score
Davies–Bouldin Index
Automatic selection of the optimal number of buses (K) based on combined ranking of the metrics.
2. Routing Optimization Module
This module generates optimized morning and afternoon bus routes for each cluster.
Included algorithms and techniques:
Nearest Neighbor for initial solution construction
Removal operators:
Random Remove
Worst Remove
Shaw Remove
Regret-2 insertion for reconstructing solutions
Simulated Annealing acceptance mechanism
Final refinement using 2-Opt
Enforcement of a 90-minute maximum student ride-time constraint
The output includes total travel time, maximum individual student ride time, and total route distance for each bus.
3. Web Interface (Gradio)
The system includes a complete multi-page interface:
Page 1: Welcome Page
Overview of the system and an introduction screen.
Page 2: Upload and Clustering
Allows the user to upload a merged CSV file containing:
School location (first row)
Student locations
Distance and time matrices
Displays the clustering results, ranking table, and bus distribution summary.
Page 3: Bus and Attendance Selection
Allows selecting a bus (cluster) and marking present or absent students.
Page 4: Routing Output
Generates and displays:
Morning route
Afternoon route
Route plots
Travel times and distances
Constraint validation
Requirements
Install the required Python packages:
pip install gradio numpy pandas scikit-learn matplotlib nest_asyncio
How to Run
Launch the Gradio interface by running the main script.
Upload the merged CSV student data file containing coordinates, distance matrix, and time matrix.
Execute the clustering step to determine bus assignments.
Select a bus and mark attendance.
Generate morning and afternoon routes.
Review the route plots and performance statistics.
Input File Format
The merged CSV file should contain the following columns:
lat, lon: Coordinates of school and students
distance_*: Distance matrix columns
time_*: Time matrix columns
student_name: Optional field for listing student names
Row 0 must represent the school.
All subsequent rows represent students.
Contributors
Aseel Alammari — 2211750
Dalia Babtain — 2211022
Dhai Alshareef — 2210251
Mayaseim Badhurays — 2210715
Noor Bamuhair — 2110908
Zahrah Saleh — 2216621
Supervisor
Dr. Enas Jambi
Project Summary
This project provides an intelligent end-to-end solution for automatic school bus routing based on real geographic data.
By integrating clustering, routing heuristics, constraints, and visualization, the system offers a practical tool for operational decision-making aimed at improving efficiency and reducing transportation costs.

AI-Based Dynamic School Bus Routing Smart System for Optimized Routes and Lower Fuel Consumption
This project presents an AI-driven system designed to cluster students geographically and generate optimized school bus routes.
The system aims to reduce fuel consumption, minimize travel time, and ensure compliance with student ride-time constraints.
1. Clustering Module (K-Means)
This module uses K-Means clustering to group students into feasible bus clusters.
Key Features
Minimum students per bus: 14
Maximum students per bus: 44
Internal evaluation metrics used:
Silhouette Score
Calinski–Harabasz Index
Davies–Bouldin Index
The system automatically selects the optimal number of buses (K) based on a combined ranking of the internal evaluation metrics.
2. Routing Optimization Module
This module generates optimized morning and afternoon bus routes for each cluster.
Included Algorithms and Techniques
Nearest Neighbor (initial solution construction)
Removal operators:
Random Remove
Worst Remove
Shaw Remove
Regret-2 insertion
Simulated Annealing acceptance
Final refinement using 2-Opt
Enforced constraint:
Maximum student ride time: 90 minutes
Outputs Provided
Total travel time
Maximum student ride time
Total route distance
3. Web Interface (Gradio)
The system includes a complete multi-page interactive interface:
Page 1 – Welcome Page
Overview and introduction to the system.
Page 2 – File Upload and Clustering
Upload a merged CSV file containing school and student data.
Displays:
Internal ranking table
Summary of students per bus
Page 3 – Bus Selection and Attendance
Select a bus (cluster) and mark present/absent students.
Page 4 – Routing Results
Generates and displays:
Morning route
Afternoon route
Route plots
Travel-time statistics
Constraint validation
Requirements
Install the required Python packages:
pip install gradio numpy pandas scikit-learn matplotlib nest_asyncio
How to Run
Launch the Gradio application.
Upload the merged CSV file that includes:
Coordinates
Distance matrix
Time matrix
Run the clustering step.
Select a bus and adjust attendance.
Generate the morning and afternoon routes.
Review the plots and statistics provided.
Input File Format (CSV)
The merged CSV must contain:
lat, lon
distance_* columns
time_* columns
student_name (optional)
Row 0 must represent the school.
All remaining rows represent students.
Prepared By
Aseel Alammari — 2211750
Dalia Babtain — 2211022
Dhai Alshareef — 2210251
Mayaseim Badhurays — 2210715
Noor Bamuhair — 2110908
Zahrah Saleh — 2216621
Supervisor
Dr. Enas Jambi
Project Summary
This project provides a complete AI-based solution for school bus route optimization using real geographic data.
By integrating clustering, heuristic optimization, constraint handling, and an interactive user interface, the system enhances decision-making and reduces transportation costs.

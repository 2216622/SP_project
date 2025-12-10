AI-Based Dynamic School Bus Routing Smart System for Optimized Routes and Lower Fuel Consumption
This project presents an AI-driven system designed to cluster students geographically and generate optimized school bus routes.
The system aims to reduce fuel consumption, minimize travel time, and ensure that student ride-time constraints are satisfied.
The project integrates clustering, routing optimization algorithms, constraint handling, and an interactive web interface.
Project Contents
1. Clustering Module (K-Means)
This module uses K-Means++ to group students into feasible bus clusters.
Key features:
Capacity constraints:
Minimum students per bus: 14
Maximum students per bus: 44
Evaluation metrics used:
Silhouette Score
Calinski–Harabasz Index
Davies–Bouldin Index
Automatic selection of the optimal number of buses (K) based on ranking the internal evaluation metrics.
2. Routing Optimization Module
Generates optimized morning and afternoon bus routes for each cluster.
Algorithms and techniques included:
Nearest Neighbor for initial route construction
Removal operators:
Random Remove
Worst Remove
Shaw Remove
Regret-2 insertion for reconstruction
Simulated Annealing acceptance criteria
Final refinement using 2-Opt
Enforcement of a 90-minute maximum student ride time
The output includes:
Total route time
Maximum individual student ride time
Total route distance
3. Web Interface (Gradio)
The system provides a complete four-page interactive user interface:
Page 1: Welcome Page
Displays an introduction to the system.
Page 2: File Upload and Clustering
Allows uploading a merged CSV file containing:
School coordinates (first row)
Student coordinates
Distance matrix
Time matrix
Displays:
Ranking table
Summary of student distribution across buses
Page 3: Bus Selection and Attendance
Select a bus cluster and mark present or absent students.
Page 4: Routing Results
Generates and displays:
Morning route
Afternoon route
Route plots
Travel-time and distance statistics
Constraint validation
Requirements
Install all required Python packages:
pip install gradio numpy pandas scikit-learn matplotlib nest_asyncio
How to Run
Launch the Gradio interface.
Upload the merged CSV file containing school and student data.
Run clustering to determine bus assignments.
Select a bus and adjust attendance (optional).
Generate morning and afternoon routes.
Review the plotted routes and the performance statistics.
Input File Format (CSV)
The merged CSV file must include:
lat, lon: School and student coordinates
distance_*: Distance matrix columns
time_*: Time matrix columns
student_name: Optional field for student names
Row 0 must represent the school.
All subsequent rows represent students.
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
This project provides an AI-based end-to-end solution for school bus route optimization using geographical student data.
By integrating clustering, heuristic optimization, constraint enforcement, and a user-friendly interactive interface, the system supports decision-making that reduces operational costs and improves transportation efficiency.

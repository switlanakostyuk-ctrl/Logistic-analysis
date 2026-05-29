# Logistic-analysis
Urban delivery process and logistics KPI analysis based on the LaDe dataset using Python and data analytics methods.Аналіз процесів міської доставки та KPI логістики на основі dataset LaDe з використанням Python і методів data analytics.

Urban Delivery Performance Analysis – Last-Mile Logistics Insights

Project Overview

In this project, I analyze urban last-mile delivery data to understand how packages move through cities and what affects delivery efficiency. Last-mile delivery connects the distribution hub with the customer – it is a critical and challenging part of modern logistics. Growing e-commerce and urbanization have made city deliveries more important than ever, but they also drive up congestion and costs. In fact, studies note that the last mile is both the most time-consuming and most expensive segment of shipping. By crunching delivery data with Python, this analysis aims to reveal patterns and bottlenecks. Data analytics can highlight where delays happen, how courier workloads are distributed, and which neighborhoods or cities have the smoothest operations. These insights could help logistics planners optimize routes, balance workloads, and improve on-time performance without expensive guesswork.

Dataset
The analysis uses the LaDe dataset (Last-mile Delivery Dataset) from Cainiao (Alibaba), which is a public urban delivery dataset. LaDe covers over 10 million deliveries (about 10,677k packages) by roughly 21,000 couriers across several Chinese cities. The data span six months of real operations. Each record includes pickup and drop-off times and locations, courier IDs, and package details. In other words, we have timestamps and GPS coordinates for when couriers accept, pick up, and deliver packages. Because the dataset includes multiple cities (e.g. Shanghai, Hangzhou, Chongqing, etc.), we can compare performance across different urban environments. Spatial (GPS) information is included, which allows mapping deliveries and identifying geographic delivery hotspots or problem zones.

Technologies Used
The analysis was done in Python using standard data-science libraries:
Pandas for data manipulation and calculation of metrics
NumPy for numerical operations
Matplotlib and Seaborn for charts and plots
Jupyter Notebook as the interactive environment for exploration
Analysis Performed



I followed a typical data analytics workflow, which included several steps:

Data Preprocessing: Checked the raw data for issues. I verified that there were no missing timestamps (time and location fields were complete) and removed any exact duplicate records. I also filtered out outliers (extremely long delivery times) to avoid skewed results. For spatial analysis, I made sure the GPS coordinates were correctly formatted and fell within city boundaries. This cleaning ensures our KPIs aren’t distorted by bad or duplicate data.

KPI Calculation: I calculated key performance indicators to summarize delivery efficiency. These include average delivery time, median delivery time, delivery time variance, standard deviation, and the share of problem deliveries (for example, percentage of orders that took excessively long). I also computed courier workload metrics, such as the average number of deliveries per courier in the timeframe.
Delivery Time Analysis: I looked at how long deliveries took across the dataset. By plotting the distribution of delivery durations (histograms and KDE curves), I could see the typical delivery time and how heavy the tail of long delays is. I compared overall distribution versus city-by-city distributions to spot differences.

City Comparison: Using grouped statistics and boxplots, I compared KPI values across cities. For example, I compared average and median delivery times for Shanghai vs. Chongqing vs. other cities. I also compared on-time delivery rates (percentage of orders delivered below a given time threshold) and problem-delivery share by city. This helped identify which urban areas performed better.
Courier Workload Analysis: I examined how deliveries are spread among couriers. Bar charts and scatter plots were used to see if a few couriers handle most deliveries or if it’s balanced. I checked whether couriers with more deliveries tended to have longer or shorter delivery times on average.

Spatial Analysis: I plotted the delivery locations on city maps to identify geographic patterns. For each city, I created simple heatmaps or scatter plots of the GPS points, highlighting areas with frequent delays or high density of deliveries. This spatial view helps spot “hotspots” where deliveries tend to be slow or concentrated.

Problem Deliveries: I defined a threshold (e.g. 180 minutes) to flag unusually long deliveries as “problems.” Then I calculated the problem delivery share overall and by city. Mapping these points gave insight into which routes or neighborhoods often cause delays.
Throughout the analysis, I used visualizations to make the patterns clear (see the next section).


Key KPIs

The main metrics I tracked included:
Average delivery time (mean) – to see typical speed of service.
Median delivery time – less affected by outliers, it shows the “typical” delivery duration.
Variance and Standard Deviation – measuring how consistent delivery times are. High variance means more unpredictability.
Problem delivery share – percentage of deliveries exceeding a long-time threshold (e.g. deliveries over 3 hours). This highlights frequency of serious delays.


Visualizations

The analysis relied on a variety of charts to reveal patterns:

Histograms and KDE plots: to show the overall distribution of delivery durations. The shape (skewness, tail) was different city to city.
Boxplots: used for comparing delivery times across cities or comparing couriers’ performance. Boxplots make it easy to see medians and outliers.
Bar charts: to summarize average KPIs by city or by courier. For example, a bar chart of average delivery time per city.
Scatter plots: for relationships, e.g. plotting number of deliveries vs. average delivery time per courier. This can show if busier couriers suffer from slower deliveries.
Spatial maps/heatmaps: plotting delivery locations on a map (latitude/longitude scatter) and coloring by delivery time. These highlight areas where deliveries take longer. A simple point map or a 2D heatmap of delays reveals geographic patterns in performance.
Each of these visualizations helped in different ways – distribution shapes, city comparisons, and spatial patterns all became more obvious through plotting.


Main Findings
From the data, some realistic conclusions emerged:

City Variability: Shanghai generally showed the most stable delivery performance, with many deliveries clustered around shorter times. Its delivery time distribution was relatively narrow (faster median and fewer extreme delays). In contrast, Chongqing had a wider spread and longer tail – it saw more deliveries exceeding typical times. Hangzhou and other cities fell in between. These differences are likely due to each city’s layout, traffic conditions, and courier density (cities were chosen because they have distinct characteristics).

Delivery Efficiency: On-time delivery rates were higher in cities with denser infrastructure and closer drop-off points. Cities with longer travel distances and more congested traffic saw a lower share of on-time orders. For example, the analysis found that Chongqing had the highest share of problem deliveries (very late shipments), which suggests that complex urban traffic can hurt performance.

Courier Workload: Deliveries per courier were fairly balanced, but we did see that couriers handling many orders tended to have slightly higher average delivery times – likely because busier routes lead to more stops and potential delays.

Spatial Hotspots: Geospatial plots revealed hotspots of delays near city outskirts or industrial areas, where long travel distances contribute to late deliveries. For instance, a cluster of very late deliveries often appeared around the edge of Chongqing’s urban area. Identifying these zones suggests where rerouting or additional resources could help.

In summary, the analysis confirmed that local urban conditions strongly affect last-mile delivery efficiency. Dense, well-connected cities like Shanghai benefit delivery performance, while more spread-out traffic-prone cities face challenges. Understanding these patterns with data (rather than guesswork) can inform better planning.


Repository Structure
Here’s a simple structure for the project:

- notebooks           # Jupyter Notebook files with data analysis
- visualizations      # Figures and charts exported from the analysis
- data                # (optional) raw or processed data files (if included)
- README.md           # Project overview (this file)




How to Run the Project
To reproduce the analysis:

1. Clone this repository.
2. Install the required Python libraries (see Requirements below).
   For example, you can run: bash
   pip install pandas numpy matplotlib seaborn
   
3. Open the Jupyter Notebook(s) in the notebooks/ folder using jupyter notebook or JupyterLab.
4. Run the notebook cells in order. The data loading and processing steps will execute, and visualizations will be generated in-line.
The code is organized in a step-by-step manner, from data cleaning to final charts. Comments in the notebook explain each step.

Requirements
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- Jupyter Notebook or JupyterLab environment
You can install all Python packages via pip or conda, and the versions used here are typical data-science releases.

Future Improvements
Possible next steps to build on this project:

- Route Optimization & Machine Learning: Use the cleaned data to train models for predicting delivery times (ETA) or suggest optimized courier routes. For example, a machine-learning model could predict delays from traffic patterns.
- Traffic & Weather Data Integration: Incorporate traffic or weather data to explain delivery delays. This could improve predictive accuracy or suggest scheduling changes.
- Time-series & Predictive Analytics: Extend the analysis to predict future demand or stress periods using time-series methods. For instance, forecast next week’s delivery volume per district.
- Real-time Dashboard: Develop a live dashboard (e.g. with Plotly or a web app) to monitor delivery KPIs and maps in real time.
- Additional KPIs: Include measures like on-time delivery rate or average distance traveled. Also, analyze customer satisfaction or return rates if data are available.



Author:
Svitlana Kostiuk – Bachelor of Science in Transport and Logistics. This analysis was completed as part of my coursework in data-driven urban logistics. It demonstrates practical skills in Python data analytics and an interest in improving city delivery systems.



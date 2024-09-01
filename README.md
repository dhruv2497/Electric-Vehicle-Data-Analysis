# Electric Vehicle Data Analysis

# Description
This interactive dashboard provides a comprehensive view of the electric vehicle landscape across the United States, offering insights into regional trends, manufacturer dominance, and technology advancements.

Key Performance Indicators (KPIs):

1. Total Vehicles: Understand the overall market size and growth for both BEVs and PHEVs.
2. Average Electric Range: Gauge the technological progress and efficiency of electric vehicles.
3. BEV & PHEV Analysis: Identify the number and market share of Battery Electric Vehicles (BEVs) and Plug-in Hybrid Electric Vehicles (PHEVs).

Charts used:
1. Line/Area Chart: Tracks total vehicle distribution by model year (2010 onwards), revealing adoption trends and growth patterns.
2. Map Chart: Illustrates the geographical spread of electric vehicles across different states, highlighting regions with higher adoption rates.
3. Bar Chart: Showcases the top 10 electric vehicle manufacturers by total vehicle count, providing insights into brand dominance.
4. Pie/Donut Chart: Depicts the proportion of electric vehicles eligible for Clean Alternative Fuel Vehicle (CAFV) incentives, aiding in understanding their impact on adoption.
5. Treemap: Highlights the top 10 electric vehicle models based on total number, offering insights into consumer preferences and popular models.

Data Interaction Techniques:
Filters: Enables users to drill down by city, electric utility, and vehicle type for focused analysis.

DAX Functions: Leverages Data Analysis Expressions (DAX) for complex calculations, creating new insights from existing data.
1. Total Vehicles = DISTINCTCOUNT(Electric_Vehicle_Population_Data[DOL Vehicle ID])
2. Avg. Electric Range = CONCATENATE(FORMAT(AVERAGE(Electric_Vehicle_Population_Data[Electric Range]), "0.00"), "Km")
3. BEV Vehicles = CALCULATE([Total Vehicles], Electric_Vehicle_Population_Data[Electric Vehicle Type] = "Battery Electric Vehicle (BEV)")
4. %age of BEV Vehicles = [BEV Vehicles]/[Total Vehicles]
5. PHEV Vehicles = CALCULATE([Total Vehicles], Electric_Vehicle_Population_Data[Electric Vehicle Type] = "Plug-in Hybrid Electric Vehicle (PHEV)")
6. %age of PHEV Vehicles = [PHEV Vehicles]/[Total Vehicles]


This comprehensive dashboard empowers users to explore the electric vehicle landscape in detail, aiding informed decision-making.

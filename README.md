# Electric Vehicle Data Analysis using Power BI

## Project Overview
This project analyzes **Washington State Electric Vehicle Demographic Data** to uncover trends, patterns, and insights into electric vehicle (EV) adoption, performance, and market dynamics. The analysis is performed using **Power BI**, and the dataset is sourced from the **Washington State Department of Licensing (DOL)** via [Kaggle](https://www.kaggle.com/datasets/adilashrafi/elecrict-vehicle).

---

## About the Dataset
### Dataset Details
- **Dataset Name**: Washington State Electric Vehicle Demographic Data
- **Source**: [Kaggle Dataset](https://www.kaggle.com/datasets/adilashrafi/elecrict-vehicle)
- **Metadata Updated**: November 17, 2023
- **Description**: This dataset provides detailed information on Battery Electric Vehicles (BEVs) and Plug-in Hybrid Electric Vehicles (PHEVs) registered in Washington State. It includes data on vehicle registration, make, model, electric range, CAFV eligibility, legislative district, and more.

### Key Features
- Comprehensive overview of EV adoption in Washington State.
- Insights into EV ownership patterns, vehicle types, and geographic distribution.
- Analysis of the impact of EV incentives and policies.

### Dataset Columns
| Column Name               | Description                                      |
|---------------------------|--------------------------------------------------|
| VIN (1-10)                | First 10 characters of the Vehicle Identification Number |
| County                    | County where the vehicle is registered          |
| City                      | City where the vehicle is located               |
| State                     | State where the vehicle is registered           |
| Postal Code               | Postal code of the vehicle's location           |
| Model Year                | Year of the vehicle model                       |
| Make                      | Make of the vehicle                             |
| Model                     | Model of the vehicle                            |
| Electric Vehicle Type     | Type of EV (BEV or PHEV)                        |
| CAFV Eligibility          | Clean Alternative Fuel Vehicle eligibility status |
| Electric Range            | Electric range of the vehicle                   |
| Base MSRP                 | Manufacturer's Suggested Retail Price           |
| Legislative District      | Legislative district associated with the vehicle |
| DOL Vehicle ID            | Department of Licensing Vehicle ID              |
| Vehicle Location          | Geographic location of the vehicle              |
| Electric Utility          | Electric utility associated with the vehicle    |
| 2020 Census Tract         | Census tract information for 2020               |

---

## Project Requirements
### Client’s Requirements
1. **KPIs**:
   - Total number of vehicles.
   - Average electric range.
   - Total BEV vehicles and percentage of total BEV vehicles.
   - Total PHEV vehicles and percentage of total PHEV vehicles.
2. **Charts**:
   - Distribution of vehicles by model year (from 2010 onwards).
   - Distribution of vehicles by state.
   - Top 10 total vehicles by make.
   - Distribution of vehicles by CAFV eligibility.
   - Top 10 total vehicles by model.
3. **Filters**:
   - City
   - Electric Utility
   - Electric Vehicle Type

---

## Solution
### Power BI Dashboard
The Power BI dashboard provides interactive visualizations and insights into the dataset. Below are the key components:

#### **Key Performance Indicators (KPIs)**
1. **Total Vehicles**: 159K
2. **Average Electric Range**: 64.28 km
3. **Total BEV Vehicles**: 124K (78% of total vehicles)
4. **Total PHEV Vehicles**: 35K (22% of total vehicles)

#### **Visualizations**
1. **Total Vehicles by Model Year (Line/Area Chart)**:
   - Illustrates the growth of EV adoption from 2010 onwards.
   - Key years: 2023 (45,244 vehicles), 2022 (27,680 vehicles), 2021 (18,737 vehicles).

2. **Total Vehicles by State (Map Chart)**:
   - Washington (WA) dominates with 159,106 vehicles.
   - Other states have significantly lower adoption rates.

3. **Top 10 Total Vehicles by Make (Bar Chart)**:
   - Tesla leads with 72,445 vehicles, followed by Nissan (13,795) and Chevrolet (12,568).

4. **Total Vehicles by CAFV Eligibility (Pie Chart)**:
   - 40.02% eligible for CAFV incentives.
   - 48.41% eligibility unknown due to un-researched battery range.

5. **Top 10 Total Vehicles by Model (Tree Map)**:
   - Tesla Model Y (30,841) and Model 3 (28,589) are the top models.

---

## DAX Functions Used
The following DAX functions were used to calculate key metrics:
1. **Total Vehicles**:
   ```DAX
   Total Vehicles = DISTINCTCOUNT(Electric_Vehicle_Population_Data[DOL Vehicle ID])
   ```
2. **Average Electric Range**:
   ```DAX
   Avg. Electric Range = CONCATENATE(FORMAT(AVERAGE(Electric_Vehicle_Population_Data[Electric Range]), "0.00"), "Km")
   ```
3. **BEV Vehicles**:
   ```DAX
   BEV Vehicles = CALCULATE([Total Vehicles], Electric_Vehicle_Population_Data[Electric Vehicle Type] = "Battery Electric Vehicle (BEV)")
   ```
4. **Percentage of BEV Vehicles**:
   ```DAX
   %age of BEV Vehicles = [BEV Vehicles] / [Total Vehicles]
   ```
5. **PHEV Vehicles**:
   ```DAX
   PHEV Vehicles = CALCULATE([Total Vehicles], Electric_Vehicle_Population_Data[Electric Vehicle Type] = "Plug-in Hybrid Electric Vehicle (PHEV)")
   ```
6. **Percentage of PHEV Vehicles**:
   ```DAX
   %age of PHEV Vehicles = [PHEV Vehicles] / [Total Vehicles]
   ```

---

## Key Insights
1. **EV Adoption Growth**:
   - EV adoption has grown significantly since 2010, with a sharp increase in recent years (2022 and 2023).
2. **Geographic Dominance**:
   - Washington State leads in EV adoption, with 159,106 vehicles registered.
3. **Market Dominance**:
   - Tesla dominates the market, with the Model Y and Model 3 being the most popular models.
4. **CAFV Eligibility**:
   - 40% of vehicles are eligible for CAFV incentives, highlighting the impact of policy on EV adoption.

---

## Screenshots
### Power BI Dashboard
![Dashboard Screenshot](https://via.placeholder.com/800x400)  
*Replace with an actual screenshot of your Power BI dashboard.*

---

## How to Use
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   ```
2. Open the Power BI file (`Electric_Vehicle_Analysis.pbix`) in Power BI Desktop.
3. Explore the interactive dashboard and apply filters to analyze specific data points.

---

## Additional Resources
- [Washington State Electric Vehicle Population Data](https://data.wa.gov/Transportation/Electric-Vehicle-Population-Data/f6w7-q2d2)
- [Kaggle Dataset Page](https://www.kaggle.com/datasets/adilashrafi/elecrict-vehicle)

---

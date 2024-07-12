### The dataset is from: https://statso.io/market-size-of-evs-case-study/

### Summary of the Electric Vehicle Analysis Project

#### Introduction
This project analyzes the electric vehicle (EV) population in the United States, with a focus on data from Washington state. The analysis includes examining trends in EV registrations, the distribution of EV types, electric ranges, and forecasting future EV market growth.

#### Dataset Overview
The dataset contains various aspects of the EV population, including:
- **VIN (1-10)**: Partial Vehicle Identification Number.
- **County**: The county in which the vehicle is registered.
- **City**: The city in which the vehicle is registered.
- **State**: The state in which the vehicle is registered. The dataset is primarily focused on Washington (WA) state.
- **Postal Code**: The postal code where the vehicle is registered.
- **Model Year**: The year of the vehicle model.
- **Make**: The manufacturer of the vehicle.
- **Model**: The model of the vehicle.
- **Electric Vehicle Type**: The type of electric vehicle, e.g., Battery Electric Vehicle (BEV).
- **Clean Alternative Fuel Vehicle (CAFV) Eligibility**: Eligibility status for clean alternative fuel vehicle programs.
- **Electric Range**: The maximum range of the vehicle on a single charge (in miles).
- **Base MSRP**: The Manufacturer’s Suggested Retail Price.
- **Legislative District**: The legislative district where the vehicle is registered.
- **DOL Vehicle ID**: Department of Licensing Vehicle Identification.
- **Vehicle Location**: Geographic coordinates of the vehicle location.
- **Electric Utility**: The electric utility service provider for the vehicle’s location.
- **2020 Census Tract**: The census tract for the vehicle’s location.

#### Data Analysis
1. **Data Loading and Initial Exploration**:
   - Loaded the dataset and performed basic exploratory data analysis to understand the structure and content.
   - Checked for missing values and cleaned the dataset by dropping rows with missing values.

2. **EV Adoption Over Time**:
   - Analyzed the number of EV registrations by model year.
   - Visualized the adoption trend over time, showing a significant increase in registrations in recent years.

3. **Top Counties and Cities**:
   - Identified the top 3 counties with the highest EV registrations.
   - Filtered the dataset to focus on these counties and analyzed the distribution of EVs within the cities of these counties.
   - Visualized the top cities in the top counties by EV registrations.

4. **Distribution of EV Types**:
   - Analyzed the distribution of different types of electric vehicles (e.g., BEV).
   - Visualized the distribution to understand the prevalence of each type.

5. **Electric Ranges**:
   - Analyzed the electric range of vehicles by make and model.
   - Identified and visualized the models with the highest average electric ranges.
   
6. **EV Market Size and Forecasting**:
   - Calculated the number of EVs registered each year.
   - Fitted an exponential growth model to the data using `curve_fit` from `scipy.optimize`.
   - Forecasted the number of EV registrations for 2024 and the next five years.

#### Key Findings
- **Historical Trends**:
  - The number of EV registrations remained relatively low until around 2010, after which there was a consistent and steep increase.
  - Recent years (2021-2023) have seen a significant jump in EV registrations.

- **Top Counties and Cities**:
  - The top 3 counties with the highest EV registrations were identified, with detailed analysis of the top cities within these counties.

- **EV Types**:
  - The distribution analysis showed the prevalence of various types of electric vehicles, providing insights into the market composition.

- **Electric Ranges**:
  - Tesla models, particularly the Roadster and Model S, have the highest average electric ranges.
  - Other makes, such as Chevrolet and Nissan, have more modest ranges, with some models having very low or zero ranges.

- **Market Forecast**:
  - The forecasted values suggest a dramatic increase in EV registrations in the coming years, driven by advancements in EV technology, increasing consumer awareness, supportive government policies, and expanding charging infrastructure.

#### Conclusion
Market size analysis and forecasting are essential for stakeholders in the EV industry to make informed decisions regarding production, infrastructure development, and policy formulation. The analysis of historical EV registration data provides valuable insights into market trends, growth patterns, and key factors driving market expansion. The forecasted values indicate a promising future for the EV market, with a projected surge in registrations in the coming years.

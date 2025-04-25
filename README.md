# BRFSS-Data
Python code for Behavioral Risk Factor Surveillance System which is referenced in StriveTogether's A Racial and Ethnic Equity Systems Indicators.  BRFSS is often referenced because it measures mental health by asking about mentally unhealthy days in the past 30 days.

# Overview
This repository contains code for processing and analyzing Behavioral Risk Factor Surveillance System (BRFSS) data, with a focus on Minnesota state data. The code transforms raw BRFSS data into an analysis-ready format with human-readable categorical variables.

# Key Features
Filters for complete interview responses
Converts numeric variables with appropriate handling of BRFSS-specific missing value codes
Transforms over 30 categorical variables into meaningful labels based on the official BRFSS codebook
Creates derived variables for easier analysis of health outcomes, demographics, and risk factors

Core Function: clean_minnesota_brfss_data()
The clean_minnesota_brfss_data() function performs comprehensive data cleaning and transformation:

Data Filtering: Removes incomplete interviews
Type Conversion: Properly handles numeric variables and BRFSS-specific missing value codes
Categorical Variable Mapping: Converts coded values to descriptive labels for:

Demographics (age, sex, race/ethnicity, education, income, etc.)
Health status measures (general health, BMI categories)
Chronic conditions (diabetes, heart disease, high blood pressure)
Risk behaviors (smoking, alcohol consumption)
Preventive health (vaccinations, screenings)
Geographic characteristics (metropolitan status, urban/rural)

# Usage
This code is designed to work with the fixed-width format BRFSS data files available from the CDC. After reading the raw data using the accompanying read_brfss_ascii_file() function, apply this cleaning function to prepare your data for analysis:

Example usage
minnesota_data = read_brfss_ascii_file("LLCP2023.ASC", state_code='27')
clean_mn_data = clean_minnesota_brfss_data(minnesota_data)

Now ready for analysis
clean_mn_data.to_csv("minnesota_brfss_2023_clean.csv", index=False)

# Dependencies
pandas
numpy

# Data Source
This code is designed for the CDC's Behavioral Risk Factor Surveillance System (BRFSS) dataset, which is the nation's premier system of health-related telephone surveys collecting state data about U.S. residents regarding their health-related risk behaviors, chronic health conditions, and use of preventive services.

# Resources 
General - https://www.cdc.gov/brfss/data_documentation/index.htm
2023 BRFSS Survey Data and Documentation - https://www.cdc.gov/brfss/annual_data/annual_2023.html 

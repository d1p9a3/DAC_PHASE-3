# DAC_PHASE-3
COVID-19 CASES ANALYSIS
import pandas as pd

# Load COVID-19 data from a CSV file
covid_data = pd.read_csv('covid_data.csv')

# Display basic information about the dataset
print("Basic Info about the dataset:")
print(covid_data.info())

# Display the first few rows of the dataset
print("\nFirst few rows of the dataset:")
print(covid_data.head())

# Calculate some statistics
total_cases = covid_data['TotalCases'].sum()
total_deaths = covid_data['TotalDeaths'].sum()
total_recoveries = covid_data['TotalRecovered'].sum()

print("\nTotal COVID-19 cases:", total_cases)
print("Total COVID-19 deaths:", total_deaths)
print("Total COVID-19 recoveries:", total_recoveries)

# Analyze data by a specific country
country_name = "United States"
country_data = covid_data[covid_data['Country'] == country_name]

print(f"\nCOVID-19 statistics for {country_name}:")
print(country_data)

# Plotting data (requires matplotlib)
import matplotlib.pyplot as plt

# Create a line chart for total cases over time
plt.figure(figsize=(12, 6))
plt.plot(country_data['Date'], country_data['TotalCases'], label='Total Cases')
plt.xlabel('Date')
plt.ylabel('Total Cases')
plt.title(f'Total COVID-19 Cases in {country_name}')
plt.xticks(rotation=45)
plt.legend()
plt.show()

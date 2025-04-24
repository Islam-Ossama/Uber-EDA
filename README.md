# Uber Trips Analysis Project

## Project Overview

This project analyzes Uber trip data to identify the most common purposes of trips, mileage trends by purpose, and time-of-day patterns using Power BI. The goal is to uncover insights into trip behavior, mileage distribution, and monthly trends to support operational and strategic decision-making for Uber.

## Table of Contents

- Project Overview
- Dataset
- Prerequisites
- Setup
- Analysis Workflow
- Key Measures
- Results
- Contributing
- License

## Dataset

- **Source**: The dataset is sourced from the provided Uber trip data file (e.g., "Uber_Trips_Data.csv").
- **Description**: The dataset contains records of Uber trips, including columns like `Purpose`, `Miles`, `Start Time`, `Month`, and `Category`, representing trip purposes, distances traveled, times of day, and trip categories.
- **Schema**:
  - `Purpose`: Reason for the trip (e.g., Meeting, Commute, Errand, etc.)
  - `Miles`: Distance traveled in miles
  - `Start Time`: Time the trip started (HH:MM format)
  - `Month`: Month of the trip (e.g., January, February, etc.)
  - `Category`: Trip category (e.g., Business, Personal)

## Prerequisites

- Power BI Desktop for data analysis and visualization

## Setup

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/Islam-Ossama/Uber-EDA.git
   ```

2. **Configure Power BI**:

   - Open Power BI Desktop and import the Uber trip data file (e.g., `Uber_Trips_Data.csv`) directly.
   - Use Power BI's data transformation tools (Power Query Editor) to clean and prepare the data.

## Analysis Workflow

1. **Data Cleaning**: Use Power BI's Power Query Editor to handle missing values, duplicates, and inconsistencies in columns like `Purpose`, `Start Time`, and `Category`.
2. **Exploratory Analysis**: Leverage Power BI to analyze trip mileage, counts by purpose, time-of-day trends, and monthly mileage patterns using data modeling and DAX calculations.
3. **Visualization**: Create an interactive dashboard in Power BI to visualize key metrics like total miles, trip counts by purpose, mileage trends over time, and monthly mileage distribution.

## Key Measures

In this project, analysis was performed directly in Power BI using DAX (Data Analysis Expressions). Below are examples of DAX measures used for the analysis:

- **Measure 1**: Calculate total miles by purpose

  ```
  Total Miles by Purpose = 
  CALCULATE(
      SUM('uber_trips'[Miles]),
      ALLEXCEPT('uber_trips', 'uber_trips'[Purpose])
  )
  ```

- **Measure 2**: Calculate count of trips by purpose

  ```
  Trip Count by Purpose = 
  CALCULATE(
      COUNT('uber_trips'[Purpose]),
      ALLEXCEPT('uber_trips', 'uber_trips'[Purpose])
  )
  ```

- **Measure 3**: Calculate total miles by month

  ```
  Total Miles by Month = 
  CALCULATE(
      SUM('uber_trips'[Miles]),
      ALLEXCEPT('uber_trips', 'uber_trips'[Month])
  )
  ```

## Results

- Total miles traveled: 12.20K miles across 1155 trips.
- The most common trip purpose by mileage is "Meeting" at 4.9K miles, followed by "Customer Visit" at 2.9K miles.
- By trip count, "Meeting" leads with 502 trips, followed by "Customer Visit" at 187 trips.
- Mileage trends over time show peaks around 5:00 AM and 7:00 AM, indicating high activity during early morning hours.
- Monthly mileage trends show peaks in March, July, and September, with a noticeable dip in June.
- A Power BI dashboard was created to visualize these insights, including histograms for mileage and trip counts by purpose, a time-based mileage trend, and a monthly mileage chart.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. For major updates, open an issue to discuss first.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

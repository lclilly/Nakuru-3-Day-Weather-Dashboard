# Nakuru-3-Day-Weather-Dashboard - Power BI Project

A live, daily weather forecast dashboard for Nakuru, Kenya, built with Microsoft Power BI and data from the OpenWeatherMap API.

This project was born out of a personal need: to have a simple, clear, and reliable weather forecast to help plan daily activities, like my afternoon walks, which were often interrupted by unpredictable rain. The goal was to build an end-to-end data pipeline, from a live API source to a finished, interactive dashboard.

---

## Tools and Technologies

* **Visualization:** Microsoft Power BI
* **Data Source:** OpenWeatherMap 5-Day/3-Hour Forecast API
* **Data Transformation:** Power Query (M Language)
* **Data Format:** JSON

---

## Key Features

* **Current Conditions:** Displays real-time temperature, humidity, and wind speed.
* **Temperature Forecast:** A line chart showing the temperature trend over the next 3 days.
* **Rainfall Forecast:** A column chart indicating the probability and volume of rain for specific time slots.
* **Automatic Refresh:** The data can be refreshed to pull the latest forecast from the API.

---

## Process

1.  **Data Ingestion:** Connected Power BI directly to the OpenWeatherMap API endpoint using the 'Get Data from Web' feature.
2.  **Data Transformation (ETL):** Used Power Query to parse the nested JSON response. This involved:
    * Expanding nested records and lists to flatten the data into a tabular format.
    * Handling `null` values for forecast entries where no rain was predicted by replacing them with 0.
    * Ensuring correct data types for dates, times, and numeric values.
3.  **Visualization:** Designed a clean, single-page dashboard with a consistent color theme. Utilized cards, gauges, a line chart, and a column chart to display the data effectively.

---

## Challenges and Learnings

* **Handling API Data:** Working with a live JSON response was a great challenge. Learning to navigate and clean the nested structure entirely within Power Query was a key takeaway.
* **Data Context:** A major learning was understanding that "blanks" in the data (like a missing rain record) were not errors but meaningful information—in this case, "no rain." Replacing these nulls with '0' was crucial for accurate visualization.

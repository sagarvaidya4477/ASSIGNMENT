# **Weather Data Aggregator and Analyzer**

## **Overview**

This project is a **Weather Data Aggregator and Analyzer** that fetches weather data from the OpenWeatherMap API, stores it in a local SQLite database, and provides analysis and visualization of weather trends over time. The application also imports weather data from a CSV file.

## **Features**

- **Fetches real-time weather data using OpenWeatherMap API.**
- **Stores weather data in a local SQLite database.**
- **Imports and cleans weather data from a CSV file.**
- **Provides visualizations for temperature, humidity, wind speed, and weather condition distribution.**

## **Setup Instructions**

1. **Clone the repository:**

    ```bash
    git clone https://github.com/sagarvaidya4477/project1
    cd weather-data-analyzer
    ```

2. **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

3. **Create the database and fetch initial weather data:**

    Uncomment the lines in the `main` function of `weather_analyzer.py` to create the database and fetch initial weather data from the OpenWeatherMap API.

    ```python
    create_db()
    data = fetch_weather_data(API_KEY, LOCATION)
    temperature = data['main']['temp']
    humidity = data['main']['humidity']
    wind_speed = data['wind']['speed']
    weather = data['weather'][0]['main']
    insert_weather_data(temperature, humidity, wind_speed, weather)
    ```

4. **Run the application:**

    ```bash
    python weather_analyzer.py
    ```

5. **Import CSV data:**

    Place your CSV file (`final_df.csv`) in the project directory. Ensure it has columns named `temp`, `humidity`, `speed`, `dt`, and `name`. The `import_and_clean_csv` function will handle the renaming of these columns.

6. **Filter and plot data:**

    The `main` function currently filters data for the city of 'Mumbai'. You can change the city by modifying the `main` function argument.

## **Example Output**

The application generates visualizations for temperature, humidity, wind speed, and weather condition distribution. Below is an example output:

![Temperature Over Time](output/temp.png)
![Humidity Over Time](output/humidity.png)
![Wind Speed Over Time](output/windspeed.png)
![Weather Condition Distribution](output/weather.png)

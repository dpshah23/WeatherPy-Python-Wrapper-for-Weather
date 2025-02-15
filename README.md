# WeatherPy - A python Wrapper for Weather 

WeatherPy is a simple Python module for fetching current weather conditions and future weather forecasts using the WeatherAPI. It abstracts the complexity of dealing with the API and provides straightforward functions for retrieving weather data by just providing the city name.

## Features

- Get current weather information, including temperature, weather condition, and wind speed.
- Fetch a 5-day weather forecast, including daily maximum and minimum temperatures and weather conditions.

## Installation

To install WeatherPy, you need to have Python installed on your machine. Install the required dependency by running:

```bash
pip install Weatherpy-1
```

## Usage

### Import the Module

Import the functions from the `weatherpy` module to get started.

```python
from WeatherPy.weather_utils import GetWeather, FutureForecast
```

### Get Current Weather

Use the `GetWeather` function to retrieve the current weather for a specific city.

#### Example

```python
from WeatherPy.weather_utils import GetWeather

city = "London"
current_weather = GetWeather(city)

if isinstance(current_weather, dict):
    print(f"Temperature: {current_weather['temprature_c']}°C")
    print(f"Condition: {current_weather['condition']}")
    print(f"Wind Speed: {current_weather['wind']} kph")
else:
    print(current_weather)
```

#### Output

```
Temperature: 15°C
Condition: Partly cloudy
Wind Speed: 12 kph
```

### Get Future Forecast

Use the `FutureForecast` function to get a 5-day weather forecast for a given city.

#### Example

```python
from WeatherPy.weather_utils import FutureForecast

city = "London"
forecast = FutureForecast(city)

if isinstance(forecast, list):
    for day in forecast:
        print(f"Date: {day['date']}")
        print(f"Max Temp: {day['max_temp']}°C")
        print(f"Min Temp: {day['min_temp']}°C")
        print(f"Condition: {day['condition']}")
        print()
else:
    print(forecast)
```

#### Output

```
Date: 2024-08-05
Max Temp: 22°C
Min Temp: 15°C
Condition: Sunny

Date: 2024-08-06
Max Temp: 23°C
Min Temp: 16°C
Condition: Cloudy
```

## API Key Management

WeatherPy handles the API key internally. Users only need to provide the city name as a parameter to the functions.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Contributing

If you'd like to contribute, please fork the repository and use a feature branch. Pull requests are welcome.

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Create a new Pull Request.

## Acknowledgements

- [WeatherAPI](https://www.weatherapi.com/) for providing weather data.

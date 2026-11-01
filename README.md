# 🌦 Weather Forecast Application
**Overview**
- This Weather Forecast Application is a web-based platform that provides real-time and forecasted weather data for any location. Built with C# and ASP.NET Core MVC, the app integrates with weather APIs to deliver accurate weather information in a user-friendly interface.

**Features***
- 🔍 Search Weather by City or Location: Search for any city or location to view weather details.
- 🌡 Current Weather: Displays temperature, humidity, wind speed, and other weather parameters.
- 🌍 Geolocation: Automatically detects the user's current location to show weather data.
- 🔄 Unit Conversion: Easily switch between Celsius and Fahrenheit.

**How It Works**
- The app fetches weather data by integrating with a third-party weather API (API key required to enable functionality).
- Users can search for cities manually or allow the app to use geolocation services.
- The weather data is displayed in a clean, intuitive format with the option to toggle between units.

**Setup Instructions**
- Clone the Repository
- ```git clone https://github.com/Gutheras/WeatherApp  ```
  

**Configure the Weather API**
- Create an account at [OpenWeatherMap](https://openweathermap.org/) and create an API key.
- Do not commit the key to `appsettings.json`. Store it in .NET user secrets from the project directory:
  ```
  dotnet user-secrets init
  dotnet user-secrets set "OpenWeatherMap:ApiKey" "your_api_key_here"
  ```
- Alternatively, set the `OpenWeatherMap__ApiKey` environment variable before starting the app.
- The key may take a short time to become active. Restart the application after configuring it.

**Tools and Technologies Used**
- C# with ASP.NET Core MVC
- Third-party Weather APIs (API key required)
- HTML5, CSS3, JavaScript
- Bootstrap for responsive design


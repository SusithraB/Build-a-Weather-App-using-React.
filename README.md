## Build-a-Weather-App-using-React.
## Date:19.04.2025

## AIM
To develop a simple weather application using React that allows the user to enter a city name and view simulated weather data (such as temperature, wind speed, and sky condition) based on predefined mock data.

## ALGORITHM
## Step 1:
1. Setup the Environment
Install Node.js and npm (Node Package Manager)

Create a new React app using the command:

npx create-react-app weatherapp
## Step 2:
. Clean the Project
Delete unnecessary files from the src folder (logo.svg, App.test.js, etc.)

Clear the default content inside App.js
## Step 3:
3. Create a New Component
Create a new file named WeatherApp.js

Define a functional component WeatherApp

Add a mock data object that contains weather info for predefined cities
## Step 4:
4. Add Input and Button
Use a text input to let the user enter the city name

Add a button or allow pressing "Enter" to trigger the search
## Step 5:
 Display Weather Information
Use state (useState) to store city input and weather data

On search, check if the city exists in the mock data

If found, display temperature, wind speed, and sky condition

If not found, show an error message
## Step 6:
 Style the App
Create a new file WeatherApp.css

Add basic styling to make the UI clean and user-friendly

Import the CSS in WeatherApp.js
## Step 7:
Update index.js
Replace the default App import with WeatherApp:

import App from './WeatherApp';
## Step 8:
Run the App
Start the app with:
npm start


## PROGRAM

WeatherApp.js
```
// src/WeatherApp.js
import React, { useState } from 'react';
import './WeatherApp.css';


const mockWeatherData = {
    London: { temperature: 18, wind: 10, sky: 'Cloudy' },
    Paris: { temperature: 22, wind: 7, sky: 'Sunny' },
    Tokyo: { temperature: 25, wind: 12, sky: 'Rainy' },
    Sydney: { temperature: 28, wind: 5, sky: 'Clear' },
    NewYork: { temperature: 19, wind: 15, sky: 'Cloudy' },
    Dubai: { temperature: 35, wind: 8, sky: 'Sunny' },
    Mumbai: { temperature: 30, wind: 10, sky: 'Humid' },
    CapeTown: { temperature: 20, wind: 14, sky: 'Windy' },
  };
  

function WeatherApp() {
  const [city, setCity] = useState('');
  const [weather, setWeather] = useState(null);
  const [error, setError] = useState('');

  const handleSearch = () => {
    const found = mockWeatherData[city];
    if (found) {
      setWeather(found);
      setError('');
    } else {
      setWeather(null);
      setError('City not found. Please try a different one.');
    }
  };

  const handleKeyPress = (e) => {
    if (e.key === 'Enter') {
      handleSearch();
    }
  };

  return (
    <div className="weather-container">
      <h1>Weather App</h1>
      <input
        type="text"
        value={city}
        onChange={(e) => setCity(e.target.value)}
        onKeyDown={handleKeyPress}
        placeholder="Enter city name"
      />
      <button onClick={handleSearch}>Get Weather</button>

      {weather && (
        <div className="weather-info">
          <p><strong>Temperature:</strong> {weather.temperature}°C</p>
          <p><strong>Wind Speed:</strong> {weather.wind} km/h</p>
          <p><strong>Sky:</strong> {weather.sky}</p>
        </div>
      )}

      {error && <p className="error">{error}</p>}
    </div>
  );
}

export default WeatherApp;
```
index.js
```
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './WeatherApp';
import reportWebVitals from './reportWebVitals';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

reportWebVitals();
```
WeatherApp.css
```
/* src/WeatherApp.css */
.weather-container {
    max-width: 400px;
    margin: 50px auto;
    padding: 20px;
    text-align: center;
    border-radius: 12px;
    background-color: #f0f4f8;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    font-family: Arial, sans-serif;
  }
  
  input {
    padding: 8px;
    width: 70%;
    margin-right: 10px;
    border-radius: 6px;
    border: 1px solid #ccc;
  }
  
  button {
    padding: 8px 12px;
    border-radius: 6px;
    border: none;
    background-color: #007bff;
    color: white;
    cursor: pointer;
  }
  
  .weather-info {
    margin-top: 20px;
    text-align: left;
  }
  
  .error {
    margin-top: 20px;
    color: red;
  }
  ```


## OUTPUT
![image](https://github.com/user-attachments/assets/26a0743d-b2b2-4338-ad38-2281d2b888de)
## RESULT
The program for creating Weather-App using React is executed successfully.

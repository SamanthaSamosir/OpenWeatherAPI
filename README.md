# Katalon API Automation - OpenWeatherMap Testing

This project automates the testing of **OpenWeatherMap APIs** using **Katalon Studio Free**. It validates:
- Getting **Geolocation coordinates** for Jakarta Selatan
- Getting the **5-day forecast**
- Getting the **current air pollution level**

> ✅ Fully built using **Katalon Free Tier** (No Enterprise license needed)  
> ✅ Includes response body checks, JSON schema validation, and HTTP assertions

---

## How to Run This Project

### 🛠 Prerequisites
- [Katalon Studio (Free)](https://www.katalon.com/download/)
- [Git](https://git-scm.com/)
- A free [OpenWeatherMap API Key](https://home.openweathermap.org/users/sign_up)

---

### Steps to Set Up Locally

1. Clone the repo:
```bash
git clone https://github.com/yourusername/katalon-openweather-api.git
cd katalon-openweather-api
```
2. Open the project in Katalon
3. Add your API key
```
Go to Profiles > default
Add a variable:
- Name: API_KEY
- Type: String
- Value: <your_openweathermap_api_key>
```
4. Run the tests

---

### What is Being Validated?

1. TC_01_GetCoordinates (Geocoding API)
- Jakarta Selatan must be in the city name
- Coordinates (lat, lon) are not null
- Status code = 200
- Response JSON schema is validated

2. TC_02_GetForecast (Forecast API)
- Coordinates match those from Geocoding
- List must contain forecast data
- Every item has temp, weather, and dt_txt

3. TC_03_AirPollution (Pollution API)
- Status code = 200
- Components like pm2_5, pm10, o3, no2, etc. exist
- Coordinates match input
- JSON schema for pollution is validated

---

### How to Get the Report
1. After running a test:
- Navigate to the Reports tab (left panel)
- Find the folder with a timestamp (e.g., 2025_04_11_19_38_45)
- Inside you’ll see: execution.properties, JUnit_Report.xml, HTML report (double-click to open)
2. To export:
- Right-click the report folder > Export > HTML/PDF/XML

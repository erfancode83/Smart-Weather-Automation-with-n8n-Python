🌤️ SkySentinel: Smart Weather Automation with n8n & Python

SkySentinel is a robust automation workflow built on n8n that fetches real-time weather data for multiple cities, processes it using Python, and delivers formatted reports with Smart Rain Alerts directly to Slack.
🚀 Key Features

    Automated Scheduling: Runs every morning at 09:00 AM (customizable via Cron).

    Multi-City Support: Easily monitor weather conditions for an unlimited list of cities.

    Python-Powered Logic: Uses an internal Python engine to analyze weather codes and generate human-readable alerts.

    Smart Alerts: Automatically detects precipitation (Rain, Thunderstorms) and extreme temperatures to send specialized warnings.

    Localization: Supports multi-language descriptions (Persian/English) via OpenWeather API.

🛠️ Technical Stack

    n8n: Workflow orchestration and node management.

    Python 3 (Native): Data transformation and conditional logic.

    OpenWeather API: Source for real-time meteorological data.

    Slack Webhooks: Delivery channel for automated reports.

📦 Installation & Setup
Prerequisites

    An instance of n8n (Cloud, Docker, or Desktop).

    A free API Key from OpenWeatherMap.

    A Slack App with chat:write permissions and an Incoming Webhook or Bot Token.

Deployment Steps

    Import Workflow: Download the workflow.json from this repository and import it into your n8n canvas.

    Configure API: Open the HTTP Request node and paste your OpenWeather API Key in the appid parameter.

    Set Cities: Edit the first Code node (Python) to include your desired cities.

    Connect Slack: Authenticate your Slack account in the final node and select your target channel.

    Activate: Toggle the workflow to Active to start receiving daily updates.

🧠 Python Logic Overview

The core intelligence resides in the Code node, where Python processes the raw JSON response:
Python

# snippet of the logic
if main_weather in ["Rain", "Drizzle", "Thunderstorm"]:
    alert_emoji = "⚠️ ☔ (Rain Alert!)"
elif temp < 5:
    alert_emoji = "❄️ (Cold Weather Alert!)"

🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page if you want to contribute.
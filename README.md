# Best Flight Deals Tracker
# Overview
The Flight Price Tracker is a Python application designed to monitor flight prices between a specified origin city and various destination cities. It utilizes the Kiwi Tequila API for flight searches, Google Sheets for destination data storage, and Twilio for SMS notifications. The application periodically checks for flight prices, compares them with pre-set thresholds, and sends SMS alerts for any price drops below the specified thresholds.

![Screenshot 2024-06-22 230914](https://github.com/xinconggg/Best-Flight-Deals/assets/82378681/7f768e7f-bbc8-49db-8d58-8565598620bb)

## Features
#### 1. Main Application Logic
- **main.py:** Orchestrates the main functionality of the application.
- **Price Comparison:** Compares current flight prices with pre-set thresholds.
- **Automated Alerts:** Sends SMS alerts for flights with prices below the specified thresholds.
- **Dynamic Time Range:** Searches for flights within a dynamically defined time range (tomorrow to six months ahead).

#### 2. Destination Data Management
- **data_manager.py:** Manages destination data stored in a Google Sheet.
- **Sheets API Integration:** Retrieves destination data from a Google Sheet via the Sheets API.
- **Update Destination Codes:** Automatically updates missing IATA codes for destinations using the flight_search module.

#### 3. Flight Search
- **flight_search.py:** Handles flight searches using the Kiwi Tequila API.
- **Get Destination Code:** Retrieves the IATA code for a given destination city.
- **Check Flights:** Searches for available flights between an origin city and a destination within a specified time range.


#### 4. Flight Data Representation
- **flight_data.py:** Defines the FlightData class to represent flight information.
- **FlightData Object:** Stores essential flight details such as price, origin, destination, and dates.

#### 5. Notification System
- **notification_manager.py:** Manages SMS notifications using the Twilio API.
- **Twilio Integration:** Sends SMS notifications for low flight prices using Twilio.
- **Customizable Alert Messages:** Notifies users with personalized messages containing price and route details.

## Requirements
- Python 3.x
- requests library
- Twilio Account SID and Auth Token
- Twilio phone number
- Google Sheets API key
- Kiwi Tequila API key

## Usage
- Customize the threshold prices and destination data in the Google Sheet.
- Run `main.py` periodically to check for flight prices and receive alerts for low prices.
- Receive SMS notifications with details of the best deals available.

## Code Explanation
#### Destination Data Management:
The DataManager retrieves destination data from a Google Sheet and updates missing IATA codes using the FlightSearch module.

#### Flight Search:
The FlightSearch module interacts with the Kiwi Tequila API to search for flight prices between specified origin and destination cities.

#### Price Comparison and Notification:
The main script compares fetched prices against predefined thresholds and sends SMS alerts using the Twilio API for prices below the thresholds.

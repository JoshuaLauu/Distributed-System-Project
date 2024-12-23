# Travel Destination Finder App (Jo's Travelog)

## Overview

The **Travel Destination Finder App** allows users to input an origin city and a travel budget, fetching available travel destinations within the specified budget using the Amadeus Travel API. The app includes both an **Android mobile application** and a **web service** deployed on GitHub Codespaces. Additionally, a web-based dashboard provides analytics and logs for monitoring API usage and system performance.

---

## Features

### Android Application: TravelAssistantApp
1. **User Inputs**:
   - Users enter the **origin city** and **budget** through an intuitive interface.
   
2. **Data Fetching**:
   - Sends HTTP GET requests to the web service endpoint.
   - Example endpoint:  
     ```
     https://laughing-space-meme-5gxg7r4v4959fp6vj-8080.app.github.dev/travel?origin=<origin>&maxPrice=<maxPrice>
     ```

3. **JSON Response Parsing**:
   - Parses JSON replies with travel data (e.g., destination, price, and travel dates).

4. **Dynamic Updates**:
   - Displays results in the app using a `TextView`.
   - Supports repeated input without restarting the app.

5. **UI Components**:
   - `TextView`: Displays results and instructions.
   - `EditText`: Captures user input for origin city and budget.
   - `Button`: Triggers HTTP requests.
   - `ImageView`: Adds visual appeal with travel-related icons.

---

### Web Service
1. **Endpoint**:
   - `/travel` (handles GET requests).
   - Parameters: `origin`, `maxPrice`.

2. **Business Logic**:
   - Fetches travel data from Amadeus API.
   - Authenticates requests and filters responses for relevant data.

3. **Response**:
   - Returns JSON-formatted travel information.
   - Example response:
     ```json
     {
       "data": [
         {
           "origin": "PAR",
           "destination": "CAS",
           "departureDate": "2022-09-06",
           "returnDate": "2022-09-11",
           "price": { "total": "161.90" }
         }
       ]
     }
     ```

4. **Logging**:
   - Logs include:
     - Request timestamp
     - Input parameters (`origin`, `maxPrice`)
     - API response time (in ms)
     - Response size (in bytes)
     - Status and error messages

5. **Database Integration**:
   - Logs are stored in MongoDB Atlas:
     - **Database Name**: `travelApp`
     - **Collection Name**: `logs`

---

### Web-Based Dashboard
1. **Operations Analytics**:
   - Displays insights such as:
     - Top 5 most requested origin cities.
     - Average API response time.
     - Most frequent budget ranges.

2. **Logs Display**:
   - Provides a full log table for debugging and monitoring.

---

## Deployment
- The web service is deployed on GitHub Codespaces.
- Public URLs:
  - **Web Service**:  
    [https://laughing-space-meme-5gxg7r4v4959fp6vj-8080.app.github.dev](https://laughing-space-meme-5gxg7r4v4959fp6vj-8080.app.github.dev)
  - **Dashboard**:  
    Accessible from the web service.

---

## Setup Instructions

### Prerequisites
1. **Tools and Dependencies**:
   - Android Studio for the Android app.
   - A MongoDB Atlas account and connection string.
   - Java Servlet API for the web service.
   - GitHub Codespaces for deployment.

### Steps to Run
1. **Android Application**:
   - Clone the repository.
   - Open the `TravelAssistantApp` project in Android Studio.
   - Run the app on an emulator or connected device.

2. **Web Service**:
   - Deploy the web service on GitHub Codespaces or your own server.
   - Ensure the MongoDB database is connected.

3. **Dashboard**:
   - Access the analytics and logs through the provided public URL.

---

## Example Usage

1. **Android App**:
   - Input:  
     Origin: `PAR`  
     Budget: `200`  
   - Output:  
     ```
     Destination: CAS
     Departure Date: 2022-09-06
     Return Date: 2022-09-11
     Price: 161.90
     ```

2. **Dashboard Analytics**:
   - Top 5 requested origins: `PAR`, `LON`, `NYC`.
   - Average API response time: `120 ms`.

---

## Technologies Used
1. **Backend**:
   - Java Servlet for web service.
   - MongoDB Atlas for logging.

2. **Frontend**:
   - Android SDK for the mobile app.

3. **API**:
   - Amadeus Travel API for fetching travel data.

---

## Author
- **Name**: Junxuan (Joshua) Liu   

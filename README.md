# Flight Deal Finder

## Overview

The Flight Deal Finder is a Python application designed to help users discover amazing flight deals to their favorite destinations. Leveraging various APIs, this tool searches for flights below a specified price threshold and notifies the user via SMS when a deal is found. This project is divided into two parts: the first part focuses on finding flight deals for personal use, while the second part aims to expand the service to other users.

## Output
![WhatsApp Image 2024-02-04 at 00 55 57_c498b1e2](https://github.com/sarvesh-2109/Flight-Deal-Finder/assets/113255836/2eeb2dc1-fbc5-43c4-b289-12d3bf473102)
![WhatsApp Image 2024-02-04 at 00 56 01_732e5da9](https://github.com/sarvesh-2109/Flight-Deal-Finder/assets/113255836/a172aba3-74bd-44cf-9729-12ac822f692a)
![WhatsApp Image 2024-02-04 at 00 56 16_6ccbd599](https://github.com/sarvesh-2109/Flight-Deal-Finder/assets/113255836/622ed58f-2f24-4103-801b-bb3d7dd97b95)




## Features

- **Automated Flight Searches:** Utilizes the Tequila API to search for cheap flights to multiple destinations.
- **Google Sheets Integration:** Keeps track of desired destinations and their lowest historical prices using Google Sheets.
- **SMS Notifications:** Sends low-price flight alerts to the user's phone using Twilio's SMS service.
- **IATA Code Resolution:** Dynamically finds IATA codes for cities using the Tequila API's location query feature.

## Technologies Used

- Python 3
- Tequila API for flight search
- Google Sheets API for data management
- Twilio API for sending SMS notifications

## Getting Started

### Prerequisites

- Python 3.6 or higher
- A Tequila API key for flight search
- A Twilio account for sending SMS
- Access to the Google Sheets API

### Installation

1. **Clone the repository:**
   ```sh
   git clone https://github.com/yourusername/cheap-flight-finder.git
   ```
2. **Install required Python packages:**
   ```sh
   pip install requests twilio
   ```
3. **Set up environment variables:**
   - `APP_ID` and `API_KEY` for the Tequila API
   - `TWILIO_SID`, `TWILIO_AUTH_TOKEN`, `TWILIO_VIRTUAL_NUMBER`, and `TWILIO_VERIFIED_NUMBER` for the Twilio API
   - `SHEETY_ENDPOINT` for the Google Sheets API endpoint

### Configuration

- **Tequila API:** Sign up for an account at [Tequila](https://tequila.kiwi.com/) and obtain your API key.
- **Twilio API:** Set up a Twilio account at [Twilio](https://www.twilio.com/), get your SID and auth token, and purchase a virtual number for sending SMS.
- **Google Sheets API:** Create a new Google Sheet to store destination data and use the Google Sheets API to interact with it.

## Usage

1. **Update the Google Sheet** with your desired travel destinations and their lowest historical prices.
2. **Run the script:**
   ```sh
   python main.py
   ```
3. **Receive SMS alerts** when the application finds flights below your price threshold.

## How It Works

- The application first checks if IATA codes are present for the listed destinations in the Google Sheet. If not, it queries the Tequila API to find and update these codes.
- It then searches for flights for each destination for the next six months.
- If a flight's price is below the historical low price listed in the Google Sheet, the application sends an SMS alert with the flight details.

## Contributing

Contributions to enhance the functionality of the Cheap Flight Finder are welcome. Please fork the repository and create a pull request with your features or fixes.

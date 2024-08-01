# APRS_WX_REPORT_STATION

This Repository has the info of APRS_WX_REPORT_STATION *(currently CA2RXU-15)*

### What is it?
This Station is running on a ESP32S2 board connected to APRS-IS feed and its goal is to answer for Wx Queries from any type of station (LoRa, VHF AFSK, HF, TCPIP(Internet or phone apps)) over APRS.

### How to contact it?
Just send a message to the station *(currently CA2RXU-15)* and it will answer back with the info.


### Weather Answers:
Weather Queries generete a message with:
- Name/Place of the station who ask for the report.
- Current Weather Description like "Clear Sky"
- Temperature (°C)
- Pressure (hPa)
- Humidity (%)
- Wind Speed (m/s)
- Wind Direction (deg)



### Weather Queries:
- **"WEATHER"** or **"WRH"** ----> ANSWER: Current Weather data of the GPS position of the Station who ask for report.

- **"WRL"** ---------------------> ANSWER: 

- **"W *city*"** -------------------> ANSWER:

- **"WL *city*"** ------------------> ANSWER:
- 

### Station Queries are:

- **"HELP"** or **"H"** or **"?"** ------> ANSWER : "Send: '?APRS?'(Queries) 'WRH'(Weather) 'W City'(Weather City)"
  Just a small guide about commands/queries it can answer.
  
- **"?APRS?"** ------------------> ANSWER : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC"
  
- **"?APRSV"** ------------------> ANSWER : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC"
  
- **"?APRSP"** ------------------> ANSWER : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC"
  
- **"?APRSL"** ------------------> ANSWER : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC"
  
- **"?UTC"** --------------------> ANSWER : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC"

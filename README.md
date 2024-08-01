# APRS_WX_REPORT_STATION

This Repository has the info of APRS_WX_REPORT_STATION *(currently CA2RXU-15)*

### What is it?
This Station is running on a ESP32S2 board connected to APRS-IS feed and its goal is to answer for Wx Queries from any type of station (LoRa, VHF AFSK, HF, TCPIP(Internet or phone apps)) over APRS.

### How to contact it?
Just send a message to the station *(currently CA2RXU-15)* and it will answer back with the info.

-----

### Weather Answers:
Weather Queries generete a message with:
- Name/Place of the station who ask for the report.
- Current Weather Description like "Clear Sky"
- Temperature (°C)
- Pressure (hPa)
- Humidity (%)
- Wind Speed (m/s)
- Wind Direction (deg)

-----

### Weather Queries:
- **"WEATHER"** or **"WRH"** ----> *ANSWER*: Current Weather data of the GPS position of the Station who ask for report. If the Station who ask for report does not have a valid GPS position info on APRS if won't be able to get the gps position from APRS API and therefor not valid answer will be generated. This info is generated as two APRS messages back to the asking station.

- **"WRL"** ---------------------> *ANSWER*: Current Weather data of the GPS position of the Station who ask for report but encoded for LoRa APRS Trackers. Same as before: asking station needs valid APRS position registered. This info is generated as one APRS message back to the asking LoRa station/tracker.

- **"W *city*"** -------------------> *ANSWER*: Current Weather data for the City. This info is generated as two APRS messages back to the asking station.

  
- **"WL *city*"** ------------------> *ANSWER*: Current Weather data for the City but encoded for LoRa APRS Trackers. This info is generated as one APRS message back to the asking LoRa station/tracker.
  

-----

### Station Queries are:
- **"HELP"** or **"H"** or **"?"** ------> *ANSWER* : "Send: '?APRS?'(Queries) 'WRH'(Weather) 'W City'(Weather City)"
  Just a small guide about commands/queries it can answer.
  
- **"?APRS?"** ------------------> *ANSWER* : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC""
  Just a small guide about **?APRS?** queries it can answer.
  
- **"?APRSV"** ------------------> *ANSWER* : Current Software Name and Version running on the station.
  
- **"?APRSP"** ------------------> *ANSWER* : Current GPS position (QTH) of the station.
  
- **"?APRSL"** ------------------> *ANSWER* : "Still in development 73!" 
  
- **"?UTC"** --------------------> *ANSWER* : UTC Date and Time extracted from NTP Servers.


-----
### CONTACT ME
Hi!

Write me over "issues" to chat about new usefull queries to add or small corrections to do

**CA2RXU , Valparaiso, Chile 73!**

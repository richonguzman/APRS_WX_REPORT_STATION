# APRS_WX_REPORT_STATION

This Repository has the info of APRS_WX_REPORT_STATION *(currently CA2RXU-15)*

### What is it?
This Station is running on a ESP32S2 board (coded over C++) connected to APRS-IS feed and its goal is to answer for Wx Queries from any type of station (LoRa, VHF AFSK, HF, TCPIP(Internet or phone apps)) over APRS. 
- GPS Data is extracted from APRS API (www.aprs.fi)
- Weather Data is from OpenWeatherMaps (https://openweathermap.org)
- EarthQuakes Data is extracted from USGS (https://earthquake.usgs.gov)

### How to contact it?
Just send an APRS Message to the station *(currently CA2RXU-15)* and it will answer back with the info over APRS Messages.

-----

### Weather Answers:
Weather Queries generate an answer-message with:
- Name/Place of the station who ask for the report or the place/city of the query.
- Current Weather Description (example: "Clear Sky")
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

### Station Queries:
- **"HELP"** or **"H"** or **"?"** ------> *ANSWER* : "Send: '?APRS?'(Queries) 'WRH'(Weather) 'W City'(Weather City)"
  Just a small guide about commands/queries it can answer.
  
- **"?APRS?"** ------------------> *ANSWER* : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC""
  Just a small guide about **?APRS?** queries it can answer.
  
- **"?APRSV"** ------------------> *ANSWER* : Current Software Name and Version running on the station.
  
- **"?APRSP"** ------------------> *ANSWER* : Current GPS position (QTH) of the station.
  
- **"?APRSL"** ------------------> *ANSWER* : "Still in development 73!" 
  
- **"?UTC"** --------------------> *ANSWER* : UTC Date and Time extracted from NTP Servers.


-----

### Earthquakes Queries:
_APRS WX Report Station_ gets GPS position of the Station who ask for report from _APRS_ API. If the Station who ask for report does not have a valid GPS position info on APRS if won't be able to get the gps position from APRS API and therefor not valid answer will be generated.

- **"?EQ"** ------------------> *ANSWER* : List of all (Worldwide) earthquakes closer as a dinamic distance vs magnitude. If magnitude >= 5,0 and distance <= 350km || magnitude >= 6,0 and distance <= 750km || magnitude >= 7,0 and distance <= 1250km will be added to a list with earthquakes details. Each earthquake of the list will be a message.
  
- **"?EQ X"** ------------------> *ANSWER* : List of all (Worldwide) earthquakes closer than X kilometers. X max value is 1300kms. Example: **"?EQ 1000"** --> list of all earthquakes closer than 1000km with is magnitude over 4,5. Each earthquake of the list will be a message.
  
- **"?EQMX"** ------------------> *ANSWER* : List of all (Worldwide) earthquakes with its magnitude greater than X. Example: **"?EQM6"** --> list of all earthquakes over 6,0 in magnitude. Each earthquake of the list will be a message.

  
-----

### CONTACT ME
Hi!

Write me over "issues" to chat about new usefull queries to add or small corrections to do

**CA2RXU , Valparaiso, Chile 73!**

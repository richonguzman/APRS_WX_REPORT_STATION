# APRS_WX_REPORT_STATION

This Repository has the info of APRS_WX_REPORT_STATION *(currently CA2RXU-15)*

### What is it?
This Station is running on a ESP32S2 board connected to APRS-IS feed and its goal is to answer for Wx Queries from any type of station (LoRa, VHF AFSK, HF, TCPIP(Internet or phone apps)) over APRS.

### How to contact it?
Just send a message to the station *(currently CA2RXU-15)* and it will answer back with the info.


### Commands/Queries are:

- **"HELP"** or **"H"** or **"?"** ------> ANSWER : "Send: '?APRS?'(Queries) 'WRH'(Weather) 'W City'(Weather City)"

- **"WEATHER"** or **"WRH"** ----> ANSWER: 

- **"WRL"** ----------------> ANSWER: 

- **"W *city*"** -----------> ANSWER:

- **"WL *city*"** -----------> ANSWER: 
  
- **"?APRS?" ------------------> ANSWER : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC"
  
- **"?APRSV" ------------------> ANSWER : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC"
  
- **"?APRSP" ------------------> ANSWER : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC"
  
- **"?APRSL" ------------------> ANSWER : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC"
  
- **"?UTC" ------------------> ANSWER : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC"



- "hla"

# Panasonic-Aquarea-NodeRed

Prerequisite:
- Domoticz with mqtt setup
- node-red with mosquitto (with https://flows.nodered.org/node/node-red-contrib-influxdb installed)
- Panasonic Aquarea with CZ-TAW1 
- Panasonic service cloud account



Installation instructions:
- Execute the following commands on the command line of your linux device where Node-Red is running:
  - touch /tmp/cookie.txt
  - chmod 777 /tmp/cookie.txt
  In this file the cookies are stored which are used in the api calls. 

- Create the following dummy sensors in Domoticz and write down the IDX values:
  Temperature:
  - Out (aanvoer)
  - In (retour)
  - Outdoor (buitentemp)
  Percentage:
  - Pumpspeed (pompsnelheid)
  - Compressor frequency (Frequentie)
  Counter:
  - startstops 
  - working hours (bedrijfstijd)
  
- Create the following switches:
  - On Off switch (switch heatpump on/off)
  - Selector switch (to set the silent mode)
  - Thermostat Setpoint (to set the heatpump setpoint)

In Node-red:
- import the 'aquarea cloud.nodered' file 
- adjust the IDX values in the Node-Red function 'Convert JSON to domoticz mqtt msg' and 'check OnOff/TargetTemp/SilentMode' to the IDX values you just created.
- open function 'Setup global variables and settings' and fill the username and password (use the steps below).

<img src="how to get password.png" />

# Shelly-Sonnenbatterie-automation
Shelly script for Sonnenbatterie 10 Solar Charging

The Vestel Home Plus is a great Wallbox for its price but it has one major disadvantage: It cannot natively be controlled via an API. Working around this problem, I connected a Shelly plus 1 to the dry contacts of the Wallbox, meant for external control over the charging behaviour. This allows the Wallbox to shit down while there isn't enough Power comming from the Sun and reactivate again. Note that there is no way to control the amount of Charging Power on the Vestel EVC04 Home Plus, you can either turn it off or on. The shelly connects to the Sonnenbatterie 10 via its API, so both devices have to be connected to the same local Network. You will alo need:
-the IP Adress of the Sonnenbaterie
-the API Authentication Token of the Sonnenbatterie found in the Software-integration menu of the Sonnenbatteries Web surface (enter the IP Adress in a browser and use the USER profile to log in)

Uploading the script onto the shelly can be done s´this way: https://shelly-api-docs.shelly.cloud/gen2/Scripts/Tutorial

Controls:

SOLAR_MIN_START : 
-The amount of Watts of Solar Power for the Wallbox to turn
-Recomended >3600 <11000 for 3-Phase charging

SOLAR_MIN_STOP : 
-The amount of Watts of Solar Power for the Wallbox to turn
-NOTE: Can be same as SOLAR_MIN_STAR

REQUEST_TIMER : 
-The time in milliseconds between API calls, higher = better acurracy 
-NOTE: setting this too low causes crashes and high traffic on the network 
-Recomended: <3000ms

DECISION_TIMER : 
-The minimum time in milliseconds the wallbox is turned on, handy with cloudy weather 
NOTE: setting this too low can cause problems with the car 
Recomended <60000ms

The mode can also be switched from Power Production to Grid feed based decisions by replacing the according varaibles

How to connect Shelly to VESTEL EVC04 home plus: https://www.vestel-echarger.com/downloads/eCharger_Installationsanleitung_EVC04-AC22SW.pdf

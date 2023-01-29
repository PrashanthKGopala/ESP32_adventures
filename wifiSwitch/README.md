This sketch is written to run an async webserver on an ESP32 to switch pins on and off over WiFi.
It also allows for Dynamic WiFi provisioning by spinning-up an async webserver to configure WiFi credentials (SSID and Password)

Required packages:

ESPAsyncWiFiManager
Before compiling the code, please go to 
https://github.com/alanswx/ESPAsyncWiFiManager
Please download the code in zip format (via green 'code' button), rename the zip folder as follows...
From 'ESPAsyncWiFiManager-master.zip' to 'ESPAsyncWiFiManager.zip'
Please go to Arduino IDE Sketch->Include Library->Add .ZIP Library... and choose ESPAsyncWiFiManager.zip.


How it works:

Once you are done compiling and uploading this code onto an ESP32, it resets itself and starts up an Access Point (AP) of its own.

On a smartphone or tablet, go to WiFi settings and scan for APs. You should find an AP named: "ESP32-WIFI-SWITCH"
Connect to this AP using the password:  "password"

Doing this might automatically redirect you to the WiFi configuration page.
If not, open a browser on your phone/tab and type "192.168.4.1" in the search bar.

In the WiFi configuration page, you will be able to provide your WiFi router's SSID and Password intuitively.
Once you press 'Save', the webpage you are looking at stops functioning since the ESP32 winds down the corresponding webserver.

Using the credentials provided, the ESP32 connects to the WiFi router.

THe ESP32 then spins-up a new async webserver to host buttons that can be switched on and off over WiFi.
To connect to this webpage, you have to find the IP-address given to the ESP32 by your router and enter it in the search bar of a browser 
on a device connected to the same WiFi network.

This sketch references the following sources:

https://randomnerdtutorials.com/esp32-relay-module-ac-web-server/

https://github.com/alanswx/ESPAsyncWiFiManager

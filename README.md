# Temperature_and_Humidity_Monitoring_System
This project is a monitoring system for temperature and humidity inside the labratory. The content below explains how each script functions and how to add another ESP-32 System.

## Imports
The following libraries on Arduino need to be installed:
+ Arduino ESP-32 Boards (Board manager)
+ Adafruit SHT31 Library
+ PubSubClient

## Step 1: Connecting the devices to the WiFi
The the devices that will be used are the Raspberry Pi and the ESP-32. The ESP-32 cannot support certificates, that is why it will use a [Pre-Shared Key](https://help.wpi.edu/kb?btn=121&text=wpi%20psk&entity=articles&id=688).

### Obtaining the ESP-32 MAC Address
To obtain the ESP 32 MAC address, please run the following code segment
```cpp
#include <WiFi.h>


void setup() {
  Serial.begin(115200);
  Serial.println("ESP32 MAC Address:");
  Serial.println(WiFi.macAddress());
}
```
This prints the MAC address of the ESP-32 at 115200 baud. Afterwards, follow the instructions on the [WPI website](https://help.wpi.edu/kb?btn=121&text=wpi%20psk&entity=articles&id=688).

Please make sure to copy the pre shared key and enter it in the ESP-32 file where it says:
```cpp
const char* password = "Preshared key here"
```

## Obtaining the Raspberry Pi MAC Address
To obtain the MAC address of the Raspberry Pi. Open the terminal and run the following command `ifconfig`. This will post a lot of text. However, you can single out the MAC address as it will be in the form of aa:bb:cc:dd:ee:ff. This will show up after a line that contains the word "ether".
Use the same instructions as before to register the Raspberry Pi, and log into the WiFi using the operating system inside the Raspberry Pi.

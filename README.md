# ESP-EYE WebCam

This fork provides a configuration for the poorly documented ESP-EYE board to run a simple unecrypted camera stream via http at 'http://<ip>/' and capture stills by requesting 'http://<ip>/capture.jpg'.

Main source also claims support for Over the Air Updates (OTA) so it can be updated on the fly, but this has not been tested.

# How To

* Requires (https://idf.espressif.com)[ESP Development Tool chain] 
* Run 'idf.py menuconfig' to configure Wifi SSID and password in Project Configuration menu
* Run 'idf.py flash monitor' to flash and monitor it subsequently
* Observe the log files to find out which IP address has been assigned to your board

* Start capturing at http://<ip>/capture.jpg' or look at the live stream 'http://<ip>/capture.jpg'

Note that this is not thread safe or multi-user ready , watching a stream will break the capture and vice versa.

# Frequent issues

* ESP-EYE with a broken camera module will lead to various errors that can be observed in the log.


*Code in this repository is in the Public Domain (or CC0 licensed, at your option.)
Unless required by applicable law or agreed to in writing, this
software is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR
CONDITIONS OF ANY KIND, either express or implied.*

# ESP-EYE WebCam

This fork provides a configuration for the poorly documented ESP-EYE board to run a simple unecrypted camera stream via http at  `http://<ip>/` and capture stills by requesting `http://<ip>/capture.jpg`, where `<ip>` is the IP address of the device.

Main source also claims support for Over the Air Updates (OTA) so it can be updated on the fly, but this has not been tested.

# How To

* Requires a properly installed [ESP IDF Development Tool chain](https://idf.espressif.com) to build, flash and monitor the device. 
* Run `idf.py menuconfig` to configure Wifi SSID and password in Project Configuration menu
* Run `idf.py flash monitor` to flash and monitor it subsequently
* Observe the log files to find out which IP address has been assigned to your board

* Start capturing at `http://<ip>/capture.jpg` or look at the live stream `http://<ip>/capture.jpg`

Note that this is not thread safe or multi-user ready , watching a stream will break the capture and vice versa.

# Frequent issues

* ESP-EYE with a broken camera module will lead to various errors that can be observed in the log.

# Example use case

* Invoke `curl http://<ip>/capture.jpg --output capture.jpg` to grab a still and save it to a file on your computer.
* Invoke `tesseract capture.jpg` to extract text from the captured still image (assuming you have successfully installed tesseract as an OCR tool on your computer.

*Code in this repository is in the Public Domain (or CC0 licensed, at your option.)
Unless required by applicable law or agreed to in writing, this
software is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR
CONDITIONS OF ANY KIND, either express or implied.*

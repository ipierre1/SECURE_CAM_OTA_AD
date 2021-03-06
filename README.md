[![PlatformIO](https://github.com/ipierre1/SECURE_CAM_OTA_AD/workflows/ESP32%20OTA%20Build/badge.svg)](https://github.com/ipierre1/SECURE_CAM_OTA_AD/actions/)
# ESP32CAM-OTA

## Functionnalities
- Serving on ```/``` camera JPEG multi-client stream (Up to 10 clients) with HTTP basic authentification.
- Serving on ```/metrics``` ESP32-CAM metrics for Prometheus with HTTP basic authentification such as :
    - Free heap
    - Temperature
    - Up time
    - Wifi signal
    - Version
  Grafana dashboard is in ```.github/dashboard.json```. 
- HTTPS OTA client waiting for a new firmaware version available on this code repository. Application version is defined in ```src/esp32-cam-plus.ino``` as ```#define VERSION "X.X.X"``` and in ```ota.json``` as ```"version": "X.X.X"```. It will check periodically if a new version is available to download.
- WiFi client

## Libraries used in this project
- [ESP Prom](https://github.com/douglaszuqueto/esp32-prometheus) from @ douglaszuqueto
- [ESP Fota](https://github.com/chrisjoyce911/esp32FOTA) from @ chrisjoyce911

## Maintainer
@ipierre1
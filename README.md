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

## From Github to GitLab
As you may see, this project included `.gitlab-ci.yml` file for GitLab pipelines. If you want to use it, you need to do some quick changes. You need to change :
- In file `.gitlab-ci.yml` the line 50 : `http://gitlab.XXX.com/XXX/SECURE_CAM_OTA_AD` by your own Gitlab and repository. 
- In file `esp32-cam-plus.ino` the line 426 : `https://raw.githubusercontent.com/ipierre1/SECURE_CAM_OTA_AD/main/ota.json` by the raw `ota.json` file url. 
- In file `ota.json` the line 4 : `https://github.com/ipierre1/SECURE_CAM_OTA_AD/releases/download/latest/firmware.bin` by the firmware release url. 
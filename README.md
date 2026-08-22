# Home Assistant: Android TV Camera Notification

An automation for **Home Assistant** that sends an image snapshot from your security camera directly to your **Android TV / Fire TV** when a detected object lingers inside a designated zone for a specified duration.

---

## 📸 Preview

<p align="center">
  <img src="https://github.com/cyclone182/homeassistant-android-tv-camera-notification/blob/main/notification-example.jpg" alt="Android TV Notification Example" width="340" />
  <img src="https://github.com/cyclone182/homeassistant-android-tv-camera-notification/blob/main/camera_zone.jpg" alt="Detection Zone Example" width="480" />
</p>

---

## 📋 Prerequisites

Ensure the following integrations and services are set up before proceeding:

1. **[Notifications for Android TV / Fire TV](https://www.home-assistant.io/integrations/nfandroidtv)**
   - Configured in Home Assistant and linked to your target TV.
2. **[Frigate NVR](https://github.com/blakeblackshear/frigate) & Integration**
   - Camera stream (e.g., RTSP) processed by Frigate for object and zone detection.
   - Frigate integration installed in Home Assistant so object/zone binary sensors are exposed.
3. **MQTT Broker**
   - Mosquitto broker (or equivalent) connected to both Frigate and Home Assistant to handle event triggers and image capture.

---

## 🚀 Setup Instructions

### 1. Image Capture Automation
1. In Home Assistant, create a new automation and switch to **Edit in YAML**.
2. Copy and paste the contents of [`mqtt_image_capture.yaml`](mqtt_image_capture.yaml).
3. Customize the following fields for your setup:
   - `binary_sensor` (zone entity)
   - Camera name & object label
   - Frigate server IP address / hostname
   - Local file path to save the captured image

### 2. TV Notification Automation
1. Create a second automation and edit in YAML mode.
2. Copy and paste the contents of [`android_tv_notification.yaml`](android_tv_notification.yaml).
3. Customize the following fields:
   - Target notification service (`notify.android_tv...`) / device IDs
   - Binary sensor attributes and trigger delay (e.g., object remains in zone for `15s`)
   - Snapshot image file path matching Step 1

### 3. Test & Verify
Trigger the camera zone by having the tracked object remain in frame past your configured duration threshold, then verify the notification overlay appears on your TV.

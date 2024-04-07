# homeassistant-android-tv-camera-notification
<b>This homeassistant automation sends a notification to your Android TV, containing a snapshot from your security cam. The automation is triggered if the object remains in a defined detection zone within the frame for a certain period of time.</b>
<br>
<br><img src="https://github.com/cyclone182/homeassistant-android-tv-camera-notification/blob/main/notification-example.jpg" width="300" />
<img src="https://github.com/cyclone182/homeassistant-android-tv-camera-notification/blob/main/camera_zone.jpg" width="450" />
<br>
<br><b>Requirements for this automation:</b>
<ol>
<li>Notifications for Android TV / Fire TV integration already set up in Homeassistant. 
<br>See https://www.home-assistant.io/integrations/nfandroidtv
<li>Security cam feed already available to homeassistant to capture the snapshot, in this case using MQTT events.
<br>In my case, I use Frigate to run object detection on rtsp streams out of my Unifi Protect security cams. Note that this requires the Frigate server and Frigate integration inside Homeassistant. In my case, I am running the Frigate server exterior to Homeassistant in an LXC container in Docker.
<br>Note that if you want to trigger the automations based on a certain object detected, that entity will need to be available in Homeassistant. In this example, the automation is triggered when my dog is detected in an certain zone within the frame, for a certain period of time.
<br>See here for Frigate documentation: https://github.com/blakeblackshear/frigate
<li>MQTT server running as Homeassistant Add-On. This will be used to capture the camera image.</li>
</ol>
<br><b>Instructions:</b>
<br><ol>
<li>In Homeassistant, create an automation for capturing the image via MQTT. Copy the mqtt_image_capture.yaml file from this repository and save the automation. Note that you will have to edit the binary sensor, camera name, and label to fit your setup. You'll also need to edit the IP address of the Frigate server, and filepath to save the image.</li>
<li>Next create another automation for triggering the actual TV notification. Copy the android_tv_notification.yaml file from this repository and save the automation. Note that you will have to edit the device ID's and binary sensor attributes. Also edit the filepath to the saved image. You can adjust the time which the object must remain in the detection zone before triggering (in my case it is 15 sec).</li>
<li>Now test your automation!</li>


  
</ol>

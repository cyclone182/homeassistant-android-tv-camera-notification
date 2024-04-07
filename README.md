# homeassistant-android-tv-camera-notification
<b>This homeassistant automation sends a notification to your Android TV, containing a snapshot from your security cam.</b>
<br><img src="https://github.com/cyclone182/homeassistant-android-tv-camera-notification/blob/main/notification-example.jpg" width="300" />
<p><b>Requirements for this automation:</b></p>
<ol>
&nbsp &nbsp &nbsp <li>Notifications for Android TV / Fire TV integration already set up in Homeassistant. 
  <br>See https://www.home-assistant.io/integrations/nfandroidtv
&nbsp &nbsp &nbsp <li>Security cam feed already available to homeassistant to use the snapshot method.
  <br>In my case, I use Frigate to run object detection on rtsp streams out of my Unifi Protect security cams. Note that this requires the Frigate server and Frigate integration inside Homeassistant. In my case, I am running the Frigate server exterior to Homeassistant in an LXC container in Docker.
  <br>Note that if you want to trigger the automations based on a certain object detected, that entity will need to be available in Homeassistant. In this example, the automation is triggered when my dog is detected in an certain zone within the frame, for a certain period of time.
  <br>See here for Frigate documentation: https://github.com/blakeblackshear/frigate
&nbsp &nbsp &nbsp <li>MQTT server running as Homeassistant Add-On. This will be used to capture the camera image.</li>
</ol>

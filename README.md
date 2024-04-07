# homeassistant-android-tv-camera-notification
<b>This homeassistant automation sends a notification to your Android TV, containing a snapshot from your security cam.
<img src="https://github.com/cyclone182/homeassistant-android-tv-camera-notification/blob/main/notification-example.jpg" width="200" />
<p>Requirements for this automation:</p></b>
<ol>
&nbsp &nbsp &nbsp <li>Android TV Integration already set up in Homeassistant.
&nbsp &nbsp &nbsp <li>Security cam feed already available to homeassistant to use the snapshot method.
&nbsp &nbsp &nbsp <li>Depending on how you want to trigger the automation, you may need object detection entities available inside Homeassistant. For example, I trigger this automation when the camera detects a dog within a certain zone within the camera frame. The if the object (dog) is in the zone for a certain period of time, the automation triggers.
</ol>

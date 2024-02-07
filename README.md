********************************************************************************

SARTHAK SWETANG SHAH

This is the Geofencing feature of our android app, GuardianTeen. The app has a parent and a child interface. In this feature, the parent can set up a geofence for their child, after they login/signup. When the child enters, roams inside, or exits the geofence, the parent will receive notifications on their phone.

Here are the instructions for running this feature on our application:

1) This will work on Android 11 or below due to some API and function restrictions. So, a virtual device is recommended on Android Studio (see below the specs for the virtual device I used to run this). Also, keep Google Maps open in the background for the app to work (this is an issue using location-based services on emulator).

2) When you launch the app, you will be shown the login/signup screen and you can choose parent/child. [*NOTE: It takes some 2-3 minutes for the backend server to start. Till then it will show you error when you try to login ("Network Error") or signup ("Signup Failed"). Try closing the app and running again if the error keeps popping up. Be patient :) Thank you.] If you want to skip the signup, use these accounts -

 - username: shah
 - password: shah

 - username: sss
 - password: igigig

3) Once you signup for parent and login, you will be taken to the parent interface. Select "SET GEOFENCE". It will ask you for the location permission. You can select "While the app is open".

4) You will be taken to a map. By default, you will see the Eiffel Tower area in Paris. You can click on the top-right button to go to your current location (button looks same as in Google Maps).

5) Long press/click anywhere on the map to create a geofence. It will again ask you for the always-on location permission. Select "Allow all the time" because the app has to monitor the location all the time. Again, long click on the map. A geofence will be created with the click location as the center and radius 200 meters (in future, we will try to implement multiple geofences and with user-specified radius).

6) Now the geofence is set and you can play a route of your choice (preferably where you are able to enter and exit the geofence region). This can be done by clicking the 3 dots on the emulator window. This will take you to "Extended Controls". Go to Location -> Routes. Here, you can set a route (for testing, I took the route "8 Av. Gustave Eiffel, 75007 Paris, France" to "24 Av. des Champs-Ã‰lysÃ©es, 75008 Paris, France" via a car). Set the geofence accordingly.

7) Play the route. You will see the location moving according to the route. You will see the notification and toast when it -

enters...notification/toast = GEOFENCE_TRANSITION_ENTER
roams inside...notification/toast = GEOFENCE_TRANSITION_DWELL
exits...notification/toast = GEOFENCE_TRANSITION_EXIT

---------------------------------------------------------------------------------------------

This is the standalone code of my part in our app and that is why I am using the parent's location for the geofences. After this we will integrate all our codes and features with the database and backend, where I will use the child's location for geofence monitoring. THANK YOU !!

----------------------------------------------------------------------------------------------

Properties (of the virtual device)
avd.ini.displayname              Pixel 2 API 30
avd.ini.encoding                 UTF-8
AvdId                            Pixel_2_API_30
disk.dataPartition.size          6442450944
fastboot.chosenSnapshotFile
fastboot.forceChosenSnapshotBoot no
fastboot.forceColdBoot           no
fastboot.forceFastBoot           yes
hw.accelerometer                 yes
hw.arc                           false
hw.audioInput                    yes
hw.battery                       yes
hw.camera.back                   virtualscene
hw.camera.front                  emulated
hw.cpu.ncore                     4
hw.device.hash2                  MD5:55acbc835978f326788ed66a5cd4c9a7
hw.device.manufacturer           Google
hw.device.name                   pixel_2
hw.dPad                          no
hw.gps                           yes
hw.gpu.enabled                   yes
hw.gpu.mode                      auto
hw.initialOrientation            Portrait
hw.keyboard                      yes
hw.lcd.density                   420
hw.lcd.height                    1920
hw.lcd.width                     1080
hw.mainKeys                      no
hw.ramSize                       1536
hw.sdCard                        yes
hw.sensors.orientation           yes
hw.sensors.proximity             yes
hw.trackBall                     no
image.androidVersion.api         30
image.sysdir.1                   system-images\android-30\google_apis_playstore\x86\
PlayStore.enabled                true
runtime.network.latency          none
runtime.network.speed            full
showDeviceFrame                  yes
skin.dynamic                     yes
tag.display                      Google Play
tag.id                           google_apis_playstore
vm.heapSize                      228

************************************* END ***************************************************

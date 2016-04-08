This is the ros plugin for OpenROV Cockpit.

Ensure your computer has the IP 192.168.254.1 as the ros plugin streams data to that IP.

Itegration of ROS with the OpenROV

update apt-get
```
sudo apt-get upgrade
```
install necessary packages
```
sudo apt-get install libcairo2-dev libjpeg62-turbo-dev libpango1.0-dev libgif-dev build-essential
```
install canvas from the Node Package Manager
```
sudo chown -R $USER /usr/local
cd /opt/openrov/cockpit/src/plugins
npm install canvas
```

install roslib
```
npm install roslib
```

install the plugin openrov cockpit plugin (streams cockpit telemetry data to computer runnings ROS)
```
cd /opt/openrov/cockpit/src/plugins
git cline https://github.com/laughlinbarker/plugin-roslibjs.git ros
```
you should be able to run the plugin at this point.

Note that the plugin will load automatically when the backend of cockpit starts on the OpenROV.
You can monitor this on the ROV via
```
tail -f /var/log/openrov.log |grep ROS
```

this will display all the console.log messages that contain the string ROS


Note that for the plugin to function properly, you cannot load the cockpit on your browser
(i.e. don't have any browser windows open to 192.168.254.1:8080)

With the node running, you should see a message once you've sucessfully connected
via the rosbridge_socket.

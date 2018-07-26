# The Atlanta Map Room Sensor Server

This repository contains code for the Sensor Server for the Atlanta Map Room, which publishes sensor location information in order to track the projector. The LR4 circuit board should be connected by USB to the machine on which this service is installed. Ensure that the laser points to a smooth, non-reflective surface on the side of the projector to ensure consistent readings.

## Installation and Setup

Upon cloning the repository, run `npm install` to install necessary dependencies including `socket.io`. Sudo privileges may be necessary to install the packages.

The npm package `service-systemd` was used to install the server script as a service on the machine. The command `sudo service-systemd -a -n sensor_server -c /path/to/repository`. Finally, to enable the service to run on machine startup, run the command `systemctl enable sensor_server`.

After the service has been installed, the service can be started, stopped, and restarted with `sudo service sensor_server [start | stop | restart]`.

Upon starting the service (either by booting the machine or starting the service manually) the main server console for the Atlanta Map Room Web app should log "Sensor server connected" to the console. Additionally, the projector window should move as the projector is moved along the track.

## Calibration
It will be necessary to calibrate the projector sensor to align the edges of the table with the guiding box on the Controller. The Projector.js file requires two numbers that specify the start and end distance for the projector rail. To obtain these two measurements, it is possible to view the output of the sensor from the terminal window. Run the command `sudo journalctl -u sensor_server -f` in order to view a live logging of all measurements from the sensor. Move the projector to one end of the rail and make note of the measurement, then move the projector to the other end to obtain the full range of the projection.

## Components
The sensor server consists of a node file that connects to the main map room server via a socket.io client. Measurements are obtained by the node application through a python script that executes a continuous loop that listens for sensor measurements and prints them to stdout. This sensor server captures and publishes this output as a *sensorUpdate* to the socket. These measurements are sent to the server and used to calculate the projection center.

## Built With

* [MapBox GL](https://www.mapbox.com/mapbox-gl-js/api/) - Open-source libraries for embedding maps
* [Socket.io](https://socket.io/) - Real-time bidirectional event-based communication
* [Node.js](https://nodejs.org/en/) - JavaScript runtime

## Authors

* **Muniba M. Khan** - *Initial work* - [kmuniba98](https://github.com/kmuniba98)
* **Christopher Polack** - *Initial work* - [cfpolack](https://github.com/cfpolack)
* **Annabel Rothschild** - *Initial work* - [annabelrothschild](https://github.com/annabelrothschild)

See also the list of [contributors](https://github.com/kmuniba98/Atlanta-Map-Room/contributors) who participated in this project.

## Acknowledgments

* Dr. Ellen Zegura, Dr. Chris Le Dantec, Dr. Amanda Meng, Dr. Alex Godwin, Francella Tonge and the Civic Data Science REU
* Jer Thorp, Emily Catedral, and the Office for Creative Research and St. Louis Center for Creative Arts
* Melanie Richard and the support staff of the School of Literature, Media, and Communication
* Digital Integrative Liberal Arts Center at the Georgia Institute of Technology Ivan Allen College of Liberal Arts

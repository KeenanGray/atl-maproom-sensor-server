# The Atlanta Map Room Sensor Server

To document and reflect upon the connections and disjunctions between civic data and lived experience in the city, through the collaborative creation of large-scale, interpretive maps.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them

* node.js

* ubuntu vm

```
Give examples
```

### Installing

Upon cloning the repository, run `npm install` to install necessary dependencies including `socket.io`. Sudo privileges may be necessary to install the packages.

The npm package `service-systemd` was used to install the server script as a service on the machine. The command `sudo service-systemd -a -n sensor_server -c /path/to/repository -A sensor_server.js`. Finally, to enable the service to run on machine startup, run the command `systemctl enable sensor_server`.

After the service has been installed, the service can be stopped, started, and restarted with `system_`

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

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

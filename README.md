# olivianet
A kinda smart plan management system

# v1.0 Goals
- Plant Pictures
- Plant Light Control
- Plant Growth Light Control
- Plant Dirt Humidity Measuring
- Plant Watering
- Plant Watering Safety System (wouldn't like to find the plant swimming)
- Plant Temperature Measuring
- Statistics
- Public Plant Profile
- Multiple plants management
- Automated notifications

# Project technologies
- Microsoft Azure Functions + Azure static websites / Asp.net core + Asp.net core webapi
- Microsoft Azure SQL Server / Sqlite
- Microsoft Azure IoT Hub / RabbitMQ
- Microsoft Azure File Share

# Project Architecture
## [olivianet.controller](https://github.com/SoftwarePony/olivianet.controller)
A cloud or locally hosted app that will keep track of the plant(s) conditions (including resource intensive tasks that can not be executed by the probes) and trigger probe commands (lights on/off, watering, etc)

## [olivianet.probe] (https://github.com/SoftwarePony/olivianet.probe)
A NodeMCU (ESP8266) powered device that will monitor most of the conditions in the plant habitat and report to the controller; this device is also in charge of controlling the habitat lighting and plant watering

## [olivianet.backend](https://github.com/SoftwarePony/olivianet.backend)
A cloud hosted webapi that will consolidate the controller/probes information and manage the controllers/probes configuration

## [olivianet.web](https://github.com/SoftwarePony/olivianet.web)
A web application where the user/visitors can look at the plant(s) statistics and/or issue probe commands

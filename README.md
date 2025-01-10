# IoT-Weather-Station
This project focuses on implementing an Internet of Things (IoT)-based weather station that collects, processes, and displays meteorological data. 

The weather station gathers environmental data such as temperature, humidity, and atmospheric pressure using sensors like the DHT11 and BMP180. Although it was planned to include a gas sensor (MQ9) to measure carbon monoxide levels, it was not implemented due to a lack of supporting libraries. Instead, simulated random values were used to approximate gas concentration readings. Data acquisition occurs every 10 seconds and is stored in an AWS DynamoDB database for further processing.

The system processes the data in the cloud using AWS Lambda functions to compute averages of recent readings. Alerts are sent when values exceed predefined thresholds. These alerts, along with the data, are accessible through a user interface designed with AWS API Gateway, offering real-time visualization of processed information.

Implemented Technologies

Hardware:
- Sensors: DHT11 (temperature and humidity), BMP180 (barometric pressure).
- IoT node for data collection and communication.

Cloud Services:
- AWS Lambda: Handles data formatting, processing, and communication logic.
- AWS DynamoDB: Stores raw and processed sensor data.
- AWS API Gateway: Serves as the interface layer for the user.

Communication Protocols:
- MQTT: Used for transmitting data between the IoT node and the cloud.
- TunSlip: Establishes a virtual local network for IoT node communication.

User Interface:
- Accessible via HTTP API, providing a summary of the latest processed data.

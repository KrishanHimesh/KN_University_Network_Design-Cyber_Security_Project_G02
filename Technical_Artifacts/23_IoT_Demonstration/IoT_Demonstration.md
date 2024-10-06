# IoT Demonstration

## Overview
The system screens temperature and humidity using IoT sensors. Node-RED is utilized for data assortment, handling, and integration with Azure IoT Hub for unified monitoring, storage, and analysis. The overall system comprises of:
-  Temperature Sensor Node (e.g., DHT11, DHT22)
-  Humidity Sensor Node (Separate sensor)
-  Node-RED for flow management and continuous data representation
-  Azure IoT Hub for cloud storage, examination, and alerting
- 	Data Processing and stockpiling utilizing Sky blue parts (IoT Hub)
  
## Components:
### Sensors:
-  Temperature Sensor: Measures the temperature of the environment.
-  Humidity Sensor: Measures the relative humidity in the environment.

## Node-RED:

•	Input Nodes: Gather information from the temperature and humidity sensors.
•	Processing Function Nodes: Process and examine the data locally.
•	Azure IoT Hub Nodes: Send processed data to Azure IoT Hub for cloud storage and analysis.
•	Dashboard Nodes: Create real-time dashboards for visualization through gauge and line graphs.

## Node-Red Setup
a.	Installation: Install node.js from Google. Run the command node-red in a command prompt to run the node-red server. The server is running at 127.0.0.1:1880.

![image](https://github.com/user-attachments/assets/9d0d48ff-7417-4068-9377-5266a6eb07f3)
 
Fig 1.1: Node-Red

 ![image](https://github.com/user-attachments/assets/6e9b60e3-debd-4744-9d80-e765332f61ee)

Fig 1.2: Node-Red Server

Download some nodes inside node-red to run the integration smoothly.

 ![image](https://github.com/user-attachments/assets/74185979-c214-475a-bce0-cc8ea34fdf72)

Fig 1.3: Installed Nodes


## Azure IoT Hub Setup

Create a new IoT Hub going through the Azure portal.

 ![image](https://github.com/user-attachments/assets/5541804a-22b8-4a01-88ab-e0c2ae437ae9)

Fig 2.1: Created IoT Hub

Registration of devices i.e., temperature and humidity sensors in Azure IoT Hub. In total, there are 10 devices i.e., 5 temperature sensors and 5 humidity sensors.

 ![image](https://github.com/user-attachments/assets/fe11f122-1115-4f65-ad40-d1a8fb6c3ef2)

Fig 2.2: IoT Devices

## Node-Red

 ![image](https://github.com/user-attachments/assets/ae5fd524-75b2-4c7d-a9b1-02e53fa9f4e8)

Fig 3.1: Node-Red Server Flow 1 (Temperature)

 ![image](https://github.com/user-attachments/assets/6f9c02a2-1b45-4a57-a6e1-64ea82618395)

Fig 3.2: Node-Red Server Flow 2 (Humidity)
These Node-RED flows show a sensor-based information handling and monitoring setup incorporated with Azure IoT Hub. Here is a breakdown of the flow:

### Temperature and Humidity Sensors:
Various virtual temperature sensors send temperature and humidity data, named TempSensor/MEL1.01 through TempSensor/MEL1.05 and HumiSensor/MEL1.01 through HumiSensor/MEL1.05.
Every sensor interfaces with a node named Temp_Gen and Humi_Gen, which creates or processes temperature and humidity data for every sensor.

 ![image](https://github.com/user-attachments/assets/ed13c167-b427-45e4-b8d5-6b2da4486a9a)

Fig 3.3: Function node (Example: TempSensorMEL1.01)

### Azure IoT Hub:
The data from the Temp_Gen and Humi_Gen nodes are sent to an Azure IoT Hub node, which advances the temperature and humidity readings to the cloud.
There's also an Azure IoT Hub Receiver node intended to get data back from the IoT Hub for further processing.

 ![image](https://github.com/user-attachments/assets/f13314ea-9815-41af-a947-f94551974790)

Fig 3.4: Azure IoT Hub Node (Connect to node-red with IoT hostname)

 ![image](https://github.com/user-attachments/assets/0f194bf5-ea7d-4658-b573-0b997b0ead69)

Fig 3.5: Azure IoT Hub Receiver (Receive message)



### Data Processor:
The data received from the IoT Hub is passed to the isolated Data Processor for every sensor. These nodes likely apply explicit changes or computations on the received sensor data.

 ![image](https://github.com/user-attachments/assets/17a1d35d-8169-41d7-807d-04afc69f3309)

Fig 3.6: Data Processor

### Debugging and Monitoring:
Each processed sensor data stream goes through Debugger nodes marked MEL1.01, MEL1.02, and so on, allowing for real-time monitoring of the sensor readings. The flow also includes Warning function nodes that generate alerts based on specific conditions or thresholds (e.g., if the temperature and humidity cross a defined limit). Lastly, each data stream has a connection to KN_University nodes linked to a database or dashboard to record or display the processed data in a university system. The overall flow shows a comprehensive data pipeline for temperature and humidity monitoring with processing, alert generation, and IoT hub/cloud integration.

 ![image](https://github.com/user-attachments/assets/fa655b28-9a24-4a02-9cca-2284a2a23f17)

Fig 3.7: Node-Red Flow 1 Dashboard (Temperature)

 ![image](https://github.com/user-attachments/assets/cf462810-4a5e-49c6-b014-1299816b4f5c)

Fig 3.8: Node-Red Flow 2 Dashboard (Humidity)

This dashboard, marked KNU IoT Dashboard, visualizes temperature data from five temperature sensors and five humidity sensors (MEL 1.01 to MEL 1.05). It utilizes two kinds of visual portrayals: gauge meters and line graphs.

### Gauge Meters:
Each gauge shows the current temperature for a particular sensor, with a scope of 0 to 50°C.The variety sections of the gauges likely address various limits (green for normal, yellow for warning, and red for danger):
-- MEL 1.01: Shows a temperature of 27°C, in the yellow zone. 
-- MEL 1.02: Shows a temperature of 30°C, also in the yellow zone.
•	MEL 1.03: Shows 40°C, which is in the red zone, demonstrating a critical temperature.
•	MEL 1.04: Displays 34°C, in the yellow zone.
•	MEL 1.05: Displays 30°C, in the yellow zone.
Similarly,
•	MEL 1.01: It shows a humidity of 36°C in the red zone. 
•	MEL 1.02: It shows a humidity of 32°C, and it is also in the yellow zone.
•	MEL 1.03: Shows a humidity of 32°C, which is in the yellow zone.
•	MEL 1.04: Displays 31°C, in the yellow zone.
•	MEL 1.05: Displays 37°C, in the red zone.

### Line Graphs:
Each line chart corresponds to the respective sensor and shows the temperature pattern over time
•	The X-axis addresses time in a short interval (~minutes).
•	The Y-axis addresses temperature (from 0 to 50°C).
The graphs catch variances in temperature and humidity for every sensor, giving knowledge into how the readings have changed throughout recent minutes.
For instance:
•	MEL 1.01: Shows a slight increment and afterwards adjustment.
•	MEL 1.03: Demonstrates a drop after reaching a high point.
•	MEL 1.05: Showcases minor changes yet remain moderately consistent.
This arrangement offers an unmistakable outline of ongoing sensor information and verifiable patterns, making it simple to recognize inconsistencies, such as the critical temperature of MEL 1.03.

## Email:
Emails are sent to the email address of KN University with the temperature and humidity data collected from sensors.

 ![image](https://github.com/user-attachments/assets/d62d2c19-cf75-4321-a0fc-64a7d1c95e4e)

Fig 3.9: Emails from Node-Red


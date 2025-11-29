# EXPERIMENT-06-Data-Publishing-to-IoT-Broker-Using-MQTT3
 ## NAME: John Wilfred Thomas J W
 ## REGISTER NUMBER: 212224040141
 ## DEPARTMENT: CSE
 ## YEAR: Second
 ## Aim:
To publish data to an IoT broker using the MQTT protocol.

 ## Apparatus Required:
MQTT Broker: An MQTT broker, such as HiveMQ or Mosquitto, for handling communication.
Python Environment: To run the script for publishing data to the broker.
Internet Connection: For connecting to the IoT broker.
Theory:
MQTT (Message Queuing Telemetry Transport) is a lightweight messaging protocol used in IoT applications. It allows devices to publish data to a broker, where other devices or applications can subscribe to receive updates. This experiment demonstrates how to use MQTT to send messages to an IoT broker using the paho-mqtt library in Python.

 ## Procedure:
Setup MQTT Broker:

You can use a public broker like broker.hivemq.com or set up your own broker using software like Mosquitto.
Choose a topic for the message, e.g., test/topic.
Install MQTT Client Library:

Install the paho-mqtt Python library to facilitate communication with the MQTT broker.
bash
Copy code
!pip install paho-mqtt
Write the Python Script to Publish Data:

Create a Python script to connect to the broker and publish a message to a specific topic.
Code Implementation: Here’s the Python code to publish data to the IoT broker using MQTT:

python
Copy code
import paho.mqtt.client as mqtt

# Broker details
broker_address = "broker.hivemq.com"  # Broker address
broker_port = 1883  # Broker port
topic = "test/topic"  # Topic to publish to

# Initialize the MQTT Client
client = mqtt.Client()

# Connect to the broker
client.connect(broker_address, broker_port, keepalive=60)

# Publish a message to the topic
message = "Hello, MQTT!"  # Message to be published
client.publish(topic, message)

# Disconnect from the broker
client.disconnect()

# Print confirmation message
print(f"Message '{message}' published to topic '{topic}'")
Run the Script:

Execute the script. It will connect to the MQTT broker, publish the message to the specified topic, and then disconnect.
Verify Message Publishing:

You can verify the message by subscribing to the same topic using an MQTT client, such as MQTT.fx or any other MQTT subscriber tool.
 ## Outputs:
Message Confirmation: The script will print a message confirming that the data has been successfully published to the topic.

Example output:

bash
Copy code
Message 'Hello, MQTT!' published to topic 'test/topic'
Broker Message: The message "Hello, MQTT!" will be published to the topic test/topic.

## Python Code 
```
import paho.mqtt.client as mqtt

broker = "29eb090fb6f24468a05c234ee8b05edf.s1.eu.hivemq.cloud"
port = 8883
topic = "iot1/demo/sensor"
username = "hivemq.webclient.1764391837947"
password = "9nLW03Uh?:T7Pv#e.Cuw"

client = mqtt.Client()
client.username_pw_set(username, password)
client.tls_set() 

client.connect(broker, port)
client.publish(topic, "SEC")
client.loop(2)
client.disconnect()
```
 ## Simulation Screenshots:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/431892ee-8f7c-437f-9d52-88be1700b438" />
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/16a4ce26-81c8-46c4-99b8-0f55485c6668" />

 ## Results:
The data was successfully published to the MQTT broker. The experiment demonstrated how to use the MQTT protocol to transfer data to an IoT broker, enabling remote communication between devices or applications. The message was confirmed to be received by the topic, and this communication can be extended to more complex IoT systems.

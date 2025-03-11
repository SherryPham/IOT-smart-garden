# Smart Garden System with MQTT

## Overview
This Smart Garden system uses MQTT protocol for communication and control of soil moisture sensors. The system monitors and manages soil moisture levels to optimize plant growth and reduce water waste, with a focus on security implementation.

## Features
- Real-time soil moisture monitoring
- Automated watering system control based on moisture thresholds
- Custom GUI for system management
- Security measures to ensure data confidentiality, integrity, and availability
- Flood warning and emergency shutdown capabilities

## Components
1. **ClientSignal.py**: MQTT client that simulates soil moisture sensor
2. **MyMQTTX.py**: Custom GUI for broker connection, message publishing, and topic subscription

## Environment Setup

### Prerequisites
- Python 3.x
- pip (Python Package Installer)

### Installation
1. Install the required MQTT client library:
```
pip install "paho-mqtt<2.0.0"
```

2. Clone or download this repository to your local machine.

## Usage

### Running the Client Sensor Simulation
1. Open a terminal or command prompt
2. Navigate to the project directory
3. Run the client script:
```
python ClientSignal.py
```
This will start simulating soil moisture readings and publish them to the specified topic.

### Using the Custom GUI
1. Open a terminal or command prompt
2. Navigate to the project directory
3. Run the GUI script:
```
python MyMQTTX.py
```

### Connecting to the MQTT Broker
1. In the GUI, enter the following connection details:
   - Host: rule28.i4t.swin.edu.au
   - Port: 1883
   - Username: <your_student_id>
   - Password: <your_student_id>
   - Client Name: (any unique name)
2. Click "Connect" to establish a connection to the broker

### Publishing Messages
1. Enter the topic: `public/<your_student_id>/soil moisture/control`
2. Enter the message content:
   - `on` to turn on watering
   - `off` to turn off watering
3. Click "Publish" to send the command

### Subscribing to Topics
1. Enter the topic: `public/<your_student_id>/soil moisture/status`
2. Click "Subscribe" to receive soil moisture status updates
3. View incoming messages in the "Received Messages" field

## System Operations

### Moisture Level Control
- The system automatically increases moisture level when watering is on
- The system automatically decreases moisture level when watering is off
- Status updates are sent every 2 seconds

### Automated Watering
- Water turns off automatically when moisture level exceeds 30
- Water turns on automatically when moisture level drops below 20

### Emergency Protocols
- The system disconnects all clients when a "flood" message is received
- This preventive measure helps protect the infrastructure during natural disasters

## Security Considerations
This project addresses several MQTT security vulnerabilities:

1. **Confidentiality and Data Integrity**: Implementing TLS encryption and message integrity checks.
2. **Authentication and Authorization**: Using strong authentication methods and role-based access control.
3. **Broker Security**: Regular updates, patching, and network monitoring.
4. **Quality of Service**: Appropriate QoS levels for critical messages and network optimization.

## Contributors
- Tran Anh Thu Pham (10381840)

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

#IoT Smart Home Energy Monitor 💡

A Node-RED project to simulate, monitor, and control household energy usage using a cloud-based MQTT loop.

##Features

End-to-End IoT Flow: Demonstrates a complete system from data source to web interface.

Two-Way Control: Allows users to remotely send ON/OFF commands to the simulated appliance from the dashboard.

Real-Time Data Processing: Uses a JavaScript function to transform raw power readings (Watts) into a calculated Estimated Cost per Hour.

Cloud Connectivity: Utilizes a public MQTT Broker (HiveMQ) for reliable, asynchronous communication.

##Project Criteria

Criteria	Component	Value
Data Processing	function node	Calculates Cost
Control Logic	ui-switch & change node	Two-way control
Cloud Protocol	mqtt in / mqtt out	Data transport
Visualization	ui-chart & ui-text	Live display


##Quick Start
1. Prerequisites
You must have Node.js and Node-RED installed locally.

2. Run the Flow
Start Node-RED:

Bash

node-red
Import the Project: Go to the Node-RED editor, click the ☰ Menu, select Import, and upload the flows.json file.

View Dashboard: Once deployed, open the browser to the dashboard URL: http://localhost:1880/dashboard/page1

3. Verification
Toggle the Appliance Control switch ON and observe the Cost per Hour update from 0.000 to approximately 0.011.

The Chart will plot the change in wattage (from 0 to 75).

##Development
The final, working flow uses the following critical logic steps:

JSONata Logic is used inside the final change node for conditional routing: $payload = 'ON' ? {ON_JSON} : {OFF_JSON}

Number Conversion is used in the function node to ensure mathematical stability.

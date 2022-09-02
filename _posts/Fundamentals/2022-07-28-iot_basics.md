---
title: IoT
date: 2022-07-27 00:00:00 -500
categories: [Foundamentals]
tags: [IOT] # TAG names should always be lowercase
img_path: /assets/posts/
---

A smart home is the best example of IoT.

In the context of IoT devices, hardwares can be divided into general devices and sensing devices. Home appliances are classic examples of general devices. Sensing devices can measure temperature, humidity and light intensity.

These devices are connected to the internet with the help of gateways. These gateways, or processing nodes process the information collected and transfer it to the cloud.

The cloud can also generate a report and send it to the app.

### IoT Device Architecture

1. IoT devices
2. IoT Gateway or Aggregation Layer
3. Processing Engine or Event Processing Layer
4. Application Layer or API Management Layer

### IoT Design Considerations

- wireless capability
- functionality
- interoperability
- secure storage
- bandwidth

### the Role of Cloud

cloud sloves the problem of scalability.

In the infrastructure level, it reduces the upfront investment.

Example:

Log and view data in the cloud with the help of AWS Dynamo DB.

We set up a rule to trigger a lambda function to put the MQTT message into the Dynamo table.

Then in EC2 Web Server, we program a simple web interface to scan the table and present the data.

The great thing about Dynamo DB is that it's a lot easier to work with than traditional SQL tables and works well with IoT type messages like MQTT.


References:
https://www.youtube.com/watch?v=242Pkw0zngw
# Protocols for IOT

## TOPIC

- Messaging Protocols
    1. Message Queuing Telemetry Transport (MQTT)
    2. Constrained Application Protocol (CoAP)
    3. XMPP Protocol
    4. Data Distribution Service (DDS)
- Transport Protocols
    1. Bluetooth 4.0 (BLE)
    2. Light Fidelity (LI-FI)
- Addressing & Identification Protocols
    1. ipv4
    2. ipv6

## MQTT VS CoAP

|         Basis of         |                              COAP                              |                          MQTT                         |
|:------------------------:|:--------------------------------------------------------------:|:-----------------------------------------------------:|
|       Abbreviation       | Constrained Application Protocol                               | Message Queuing Telemetry Transport                   |
|    Communication Type    | It uses Request-Response model.                                | It uses Publish-Subscribe model                       |
|      Messaging Mode      | This uses both Asynchronous and Synchronous.                   | This uses only Asynchronous                           |
| Transport layer protocol | This mainly uses User Datagram protocol(UDP)                   | This mainly uses Transmission Control protocol(TCP)   |
|        Header size       | It has 4 bytes sized header                                    | It has 2 bytes sized header                           |
|       RESTful based      | Yes it uses REST principles                                    | No it does not uses REST principles                   |
|    Persistence support   | It does not has such support                                   | It supports and best used for live data communication |
|     Message Labelling    | It provides by adding labels to the messages.                  | It has no such feature.                               |
|    Usability/Security    | It is used in Utility area networks and has secured mechanism. | It is used in IoT applications and is secure          |
|       Effectiveness      | Effectiveness in LNN is excellent.                             | Effectiveness in LNN is low.                          |
|    Communication Model   | Communication model is one-one.                                | Communication model is many-many.                     |

## MQTT

MQTT (Message Queuing Telemetry Transport) is a lightweight messaging protocol designed for efficient communication between devices in IoT (Internet of Things) and M2M (Machine to Machine) applications. It was developed in the late 1990s by Andy Stanford-Clark of IBM and Arlen Nipper of Arcom (now Cirrus Link Solutions) to address the need for a simple, reliable, and bandwidth-efficient protocol for constrained devices.

MQTT operates on top of the TCP/IP protocol, making it suitable for use over networks with limited bandwidth, high latency, or unreliable connections. It follows a publish-subscribe messaging pattern, where devices can publish messages to topics or subscribe to topics to receive messages. This asynchronous model allows for real-time data exchange and enables the decoupling of devices, making it scalable and flexible.

Here's a brief overview of the key components and concepts in MQTT:

1. Broker: The MQTT broker is a server that acts as a central hub for message distribution. It receives messages published by devices and forwards them to subscribed devices. The broker ensures reliable delivery of messages based on the Quality of Service (QoS) level specified by the publisher.

2. Publisher: A device or application that sends messages to the broker is called a publisher. Publishers tag their messages with topics, which act as message destinations. Topics are structured as a hierarchy, allowing for granular control over message routing.

3. Subscriber: A device or application that receives messages from the broker is called a subscriber. Subscribers express their interest in specific topics, and the broker delivers relevant messages to them. Subscribers can also use wildcards to subscribe to multiple topics simultaneously.

4. Quality of Service (QoS): MQTT supports three levels of QoS to ensure message reliability. QoS 0 (At most once) delivers messages without acknowledgment, which is the fastest but least reliable option. QoS 1 (At least once) ensures at least one delivery and requires acknowledgment from the receiver. QoS 2 (Exactly once) guarantees message delivery exactly once by using a four-step handshake process.

5. Retained Messages: MQTT allows publishers to flag messages as "retained." Retained messages are saved by the broker and delivered to new subscribers immediately upon subscription. This feature is useful for delivering status updates or configuration information.

6. Last Will and Testament (LWT): MQTT provides a LWT feature that allows a device to specify a message to be published by the broker automatically if it unexpectedly disconnects. This feature is helpful for detecting device failures or network interruptions.

MQTT has gained significant popularity in the IoT domain due to its simplicity, efficiency, and widespread support across various platforms and programming languages. It has become the de facto standard for lightweight messaging in IoT applications, enabling seamless communication between devices and facilitating the exchange of sensor data, control commands, and other information.

## CoAP

CoAP (Constrained Application Protocol) is a specialized web transfer protocol designed for resource-constrained devices and networks in IoT (Internet of Things) applications. It is a lightweight, RESTful protocol that enables efficient communication and data transfer between devices over constrained networks such as low-power wireless networks.

CoAP was developed by the Internet Engineering Task Force (IETF) as a constrained alternative to the traditional HTTP protocol, which is often too resource-intensive for small devices with limited memory, processing power, and energy. CoAP simplifies the communication model while still providing essential features for IoT applications.

Here are some key aspects of CoAP:

1. RESTful Design: CoAP follows the principles of Representational State Transfer (REST), which means it adopts a resource-oriented approach. Each resource on a CoAP-enabled device is identified by a URI (Uniform Resource Identifier), and clients can perform operations like GET, POST, PUT, and DELETE on these resources to retrieve or modify their state.

2. Lightweight and Efficient: CoAP has a compact binary header format and uses UDP (User Datagram Protocol) as the underlying transport protocol, which makes it lightweight and efficient in terms of message size and network overhead. It also supports a range of options for fine-grained control over message handling.

3. CoAP over DTLS: To provide secure communication, CoAP can be used over DTLS (Datagram Transport Layer Security), which is a lightweight version of TLS (Transport Layer Security). This allows for end-to-end encryption and authentication of CoAP messages, ensuring the confidentiality and integrity of data.

4. Resource Discovery: CoAP supports resource discovery mechanisms, allowing clients to locate and interact with resources dynamically. Devices can advertise their available resources using CoAP's resource discovery features, such as the CoRE Link Format or the CoAP-based Resource Directory.

5. Observing Resources: CoAP provides a mechanism called "observe" that allows clients to subscribe to resource updates. Once a client observes a resource, it receives notifications whenever the resource's state changes, eliminating the need for continuous polling and reducing network traffic.

6. Proxies and Gateways: CoAP can be used in conjunction with HTTP proxies and gateways to enable communication between CoAP devices and traditional web servers. This enables interoperability and integration with existing web services and applications.

CoAP has gained popularity as a communication protocol in IoT applications due to its lightweight nature, low overhead, and support for constrained devices and networks. It provides a suitable alternative to HTTP for resource-constrained environments and facilitates seamless communication and data exchange between IoT devices, enabling efficient and scalable IoT deployments.

## BLE

<img src="https://www.rfwireless-world.com/images/BLE-Protocol-Stack.jpg" width=70%>

BLE stands for Bluetooth Low Energy, also known as Bluetooth Smart. It is a wireless communication technology designed specifically for low-power and low-cost devices, commonly used in IoT (Internet of Things) applications. BLE is an extension of the classic Bluetooth technology, optimized for devices that require energy efficiency and operate on coin-cell batteries or other limited power sources.

Components of BLE:

1. Bluetooth Low Energy Protocol Stack: The BLE protocol stack consists of several layers that handle different aspects of communication. It includes the physical layer for transmitting and receiving radio signals, the Link Layer for managing connections and data packets, and the Attribute Protocol (ATT) for organizing and exchanging data between devices.

2. BLE Device Roles: In a BLE communication setup, there are two primary roles: the Central and the Peripheral. The Central role is typically taken by a smartphone, tablet, or other devices capable of initiating and managing connections. The Peripheral role is usually assumed by the low-power devices, sensors, or beacons that transmit data or respond to requests from the Central device.

3. Advertising: BLE devices use advertising to announce their presence and capabilities to nearby Central devices. Advertising packets contain information such as device name, services offered, and additional data. Central devices scan for advertising packets to discover nearby Peripherals.

4. Services and Characteristics: BLE devices organize their functionality into services and characteristics. Services represent a collection of related functionalities, while characteristics define specific data points or attributes within a service. For example, a heart rate monitor may have a Heart Rate Service with characteristics like Heart Rate Measurement, Body Sensor Location, and Battery Level.

5. GATT (Generic Attribute Profile): GATT is a protocol that operates on top of the Attribute Protocol (ATT) and defines how services, characteristics, and their values are organized and accessed. It provides a hierarchical structure to browse and interact with data on a BLE device. GATT allows Central devices to read, write, and subscribe to notifications or indications from characteristics.

6. Connections and Data Transfer: Once a Central device discovers a Peripheral through advertising, it can establish a connection. BLE connections are typically short-lived and establish a low-power link between devices. Data transfer occurs through the exchange of small packets, enabling efficient communication with minimal power consumption.

7. Security: BLE incorporates security measures to protect data during transmission. It supports encryption and authentication through pairing mechanisms like Just Works, Passkey Entry, or Out of Band (OOB) methods. Security modes, such as Security Mode 1 (unauthenticated encryption) or Security Mode 2 (authenticated encryption), provide different levels of protection.

BLE technology has revolutionized the IoT landscape by enabling seamless and energy-efficient communication between devices. Its low power consumption, simplified communication model, and support for a wide range of devices have made it popular in applications such as wearable devices, health monitoring, home automation, asset tracking, and more.

## IPV4 VS IPV6

|                                                      IPv4                                                     |                                             IPv6                                             |
|:-------------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------:|
| IPv4 has a 32-bit address length                                                                              | IPv6 has a 128-bit address length                                                            |
| It Supports Manual and DHCP address configuration                                                             | It supports Auto and renumbering address configuration                                       |
| In IPv4 end to end, connection integrity is Unachievable                                                      | In IPv6 end-to-end, connection integrity is Achievable                                       |
| It can generate 4.29×109 address space                                                                        | The address space of IPv6 is quite large it can produce 3.4×1038 address space               |
| The Security feature is dependent on the application                                                          | IPSEC is an inbuilt security feature in the IPv6 protocol                                    |
| Address representation of IPv4 is in decimal                                                                  | Address Representation of IPv6 is in hexadecimal                                             |
| Fragmentation performed by Sender and forwarding routers                                                      | In IPv6 fragmentation is performed only by the sender                                        |
| In IPv4 Packet flow identification is not available                                                           | In IPv6 packet flow identification are Available and uses the flow label field in the header |
| In IPv4 checksum field is available                                                                           | In IPv6 checksum field is not available                                                      |
| It has a broadcast Message Transmission Scheme                                                                | In IPv6 multicast and anycast message transmission scheme is available                       |
| In IPv4 Encryption and Authentication facility not provided                                                   | In IPv6 Encryption and Authentication are provided                                           |
| IPv4 has a header of 20-60 bytes.                                                                             | IPv6 has a header of 40 bytes fixed                                                          |
| IPv4 can be converted to IPv6                                                                                 | Not all IPv6 can be converted to IPv4                                                        |
| IPv4 consists of 4 fields which are separated by addresses dot (.)                                            | IPv6 consists of 8 fields, which are separated by a colon (:)                                |
| IPv4’s  IP addresses are divided into five different classes. Class A , Class B, Class C, Class Da , Class E. | IPv6 does not have any classes of the IP address.                                            |
| IPv4 supports VLSM(Variable Length subnet mask).                                                              | IPv6 does not support VLSM.                                                                  |
| Example of IPv4:  66.94.29.13                                                                                 | Example of IPv6: 2001:0000:3238:DFE1:0063:0000:0000:FEFB                                     |

## IPV4 HEADER

<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200113154849/ip-v4-datagram-header.png" width=70%>

## IPV6 HEADER

<img src="https://cstaleem.com/wp-content/uploads/2021/12/IPV6-Header.png" width=70%>
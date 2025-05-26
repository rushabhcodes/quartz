---
created: 2025-05-26T07:51
updated: 2025-05-26T08:50
---

| **Aspect**              | **CoAP**                                                 | **MQTT**                                                |
| ----------------------- | -------------------------------------------------------- | ------------------------------------------------------- |
| Full Name               | Constrained Application Protocol                         | Message Queuing Telemetry Transport                     |
| Developed By            | IETF (RFC 7252)                                          | IBM                                                     |
| Protocol Type           | Request/Response (REST-like)                             | Publish/Subscribe                                       |
| Transport Layer         | UDP                                                      | TCP (optionally WebSockets)                             |
| Architecture Model      | Client/Server                                            | Broker-based                                            |
| Message Broker Required | No                                                       | Yes                                                     |
| Communication Pattern   | Synchronous (GET, POST, PUT, DELETE)                     | Asynchronous messaging                                  |
| Multicast Support       | Yes                                                      | No                                                      |
| Push Notification       | Yes (CoAP Observe)                                       | Yes (via broker)                                        |
| Reliability             | Optional acknowledgments                                 | Built-in QoS (levels 0, 1, 2)                           |
| Overhead                | Very low (compact binary format)                         | Low (slightly higher due to TCP)                        |
| Latency                 | Lower (no connection setup due to UDP)                   | Higher (TCP handshake required)                         |
| Power Consumption       | Lower                                                    | Moderate                                                |
| Security Protocol       | DTLS (Datagram Transport Layer Security)                 | TLS (Transport Layer Security)                          |
| Authentication Options  | DTLS-based (certificates, pre-shared keys)               | Username/password, certificates                         |
| Web Integration         | Good (HTTP-like URI and methods, easy proxying)          | Limited (not natively compatible with HTTP)             |
| Proxy Support           | Yes (CoAP-to-HTTP proxies available)                     | Limited                                                 |
| Suitable for            | Constrained devices, lossy networks, multicast scenarios | Reliable delivery, cloud integration, publish/subscribe |
# Explain IOT Application Transport Methods In Brief.
![[IOT Application Transport Methods]]

# Comparison between sensors and actuators
![[Comparison between sensors and actuators]]

# Smart Objects
![[Smart Objects]]

# Sensors
![[Sensors]]
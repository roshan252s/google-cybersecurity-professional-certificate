# Cybersecurity Incident Report: Network Attack Analysis

## Incident Overview
This report documents a network access issue where employees were unable to access the company's travel webpage. Network traffic logs were analyzed using a packet sniffer to identify protocol communication failures and diagnose the underlying network issue.

---

## Section 1: Identify the Type of Attack That May Have Caused This Network Interruption

One potential explanation for the website's connection timeout error message is a **SYN flood attack**. In this scenario, an attacker floods the target server with repeated `SYN` packet requests, consuming system resources while leaving connections half-open by never responding with the final `ACK`. As a result, legitimate users face connection timeout errors.

The logs show that this is a network-level Denial of Service (DoS) attack, called a **SYN flood attack**, that targets system resources. 

This event could be a malicious actor trying to intentionally flood the server with repeated `SYN` packet requests to disrupt the system workflow.

---

## Section 2: Explain How the Attack Is Causing the Website to Malfunction

When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol.

### The Three Steps of the TCP Handshake

1. **`SYN` (Synchronize):** The visitor sends a `SYN` packet to the server to initiate a connection request.
2. **`SYN-ACK` (Synchronize-Acknowledge):** The server responds with a `SYN-ACK` packet to acknowledge the request and allocates memory resources to hold the connection state.
3. **`ACK` (Acknowledge):** The visitor responds with an `ACK` packet, confirming and establishing the active connection.

---

### Impact of Simultaneous SYN Packets

When a malicious actor sends a large number of `SYN` packets simultaneously without responding with the final `ACK`, connections are left in a **half-open state**. This rapidly consumes the server's available memory spaces.

---

### Log Analysis & Server Impact

The network traffic logs indicate that the server is being flooded with repeated `SYN` packets continuously, leaving connections stuck in a half-open state. This consumes all available server memory and socket connection slots. As a result, the server is unable to accept new `SYN` requests from legitimate users, causing it to drop connection attempts and respond with connection timeout errors or `[RST, ACK]` packets.
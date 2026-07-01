# Home Lab SIEM project
Welcome! This is my documentation of my learning process with Wazuh. I decided to start with Wazuh in order to learn more about endpoint security, log monitoring, and to get familiar with an enterprise level SIEM. 

# Overview

In this documentaion, I have:
- Installed a Wazuh server on an Ubuntu virtual machine
- Installed a Wazuh agent on two seperate devices (Linux Mint laptop and Windows 11 PC)
- Ensured that the agents were connected to the server

# Network Topology
I decided to run the Wazuh server on my desktop computer (endpoint-02), since it has more resources than my laptop (endpoint-01). In order to accomplish this, I had to use a virtual machine since Wazuh only supports a few select operating systems. I decided to go with Ubuntu. After I installed the server, I installed an agent on endpoint-01, and an agent on endpoint-02. So I have endpoint-02 running the VM with the server along with an agent, and endpoint-01 with an agent installed. Below is a diagram of the network:
                               +----------------------+
                               |       Network        |
                               |   (LAN / Switch)     |
                               +----------+-----------+
                                          |
                +-------------------------+-------------------------+
                |                                                   |
                |                                                   |
+---------------+---------------+                 +-----------------+----------------+
|          Endpoint-01          |                 |            Endpoint-02            |
|-------------------------------|                 |-----------------------------------|
|          Linux Mint           |                 |            Windows 11             |
|                               |                 |                                   |
|  +-------------------------+  |                 |  +-------------------------+      |
|  |      Wazuh Agent        |  |                 |  |      Wazuh Agent        |      |
|  +-------------------------+  |                 |  +-------------------------+      |
|                               |                 |                                   |
+---------------+---------------+                 |  +-------------------------+      |
                |                                 |  |     Virtual Machine     |      |
                |                                 |  |-------------------------|      |
                |                                 |  |     Wazuh Manager       |      |
                |                                 |  +-------------------------+      |
                |                                 +-----------------+-----------------+
                |                                                   ^
                +---------------------------------------------------+
                     


# Steps

The first thing I did to start was to head over to [The Wazuh Docs](https://documentation.wazuh.com/current/getting-started/index.html) in order to figure out what to do. I decided to go the quickstart route, and followed the commands to install the Wazuh server on the Ubuntu VM.

![Figure 1](./assets/images/fig-1_server_started.png)

# Networking Models
1. OSI Model
2. TCP/IP Suite

> Networking model categorize and provides a structure for networking protocols and standards

## **OSI Model**
* **OSI** stands for Open Systems Interconnection  
* Created by ISO  
* Consists of 7 layers  

| # | Layer Name   | Example                 |
| - | ------------ | ----------------------- |
| 7 | Application  | HTTP,FTP,SSH,etc        |
| 6 | Presentation | Encryptions,TLS,SSL,etc |
| 5 | Session      | TCP,UDP                 |
| 4 | Transport    | Segments large data MTU |
| 3 | Network      | IP                      |
| 2 | Data Link    | MAC                     |
| 1 | Physical     | Wireless, Ethernet, SFP |

> Each layer adds something to originam data, This is called **Encapsulation**  
> Becauese original data stay fixed and somthing is added to it

> **Top 3** layers are for engineers of applications (7,6,5)

### Layer 4
* **Segments** data
* Adds L4 header to each segment
* Data + L4 Header = **Segment**

### Layer 3
* Provides connectivity btween end hosts on different networks(**outside LAN**)
* Provides **path selection** between source and destination
* Provides logical addresses(**IP addresses**)
* **Routers** operate on layer 3
* Data + L4 Header + L3 Header = **Packet**

### Layer 2
* Provides layer 2 **header** and layer 2 **trailer**
* Provides **node-to-node** connectivity and data transfer
* Defines how data is **formatted** for transmission over a **physical** medium(UTP,SFP)
* Detects and corrects **errors** occured on physical layer
* Layer 2 **addressing**
* **Switches** operate at layer 2
* L2 Trailer + Data + L4 Header + L3 Header + L2 Header = **Frame**

### Layer 1
* Physical characteristics for physical device(voltage,channel,etc)
* Bits converts to **electrical signal** or **radio signals** for wifi
* Layer 1 **PDU** is **Bit**

> [**Data**, **Segment**, **Packet**, **Frame**, **Bit**] are called **PDU**(Protocol Data Units)

## TCP/IP Suite
* Consists of 4 layers  

| # | Layer Name   | OSI Equivalant      |
| - | ------------ | ------------------- |
| 4 | Application  | Top 3 layers        |
| 3 | Transport    | Transport           |
| 2 | Internet     | Network             |
| 1 | Link         | Data Link, Physical |

> **Application** layer provides **process-to-process** communication

> **Transport** layer provides **host-to-host** or **end-to-end** communication

> **Data Link** layer provides **node-to-node** communication

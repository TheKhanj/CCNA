# Ethernet LAN Switching
Contains **layer 1** and **layer 2** of OSI Model

> **LAN** is a network contained in relatively small area  
> **Routers** are used to connect seperate lans

## Ethernet Frame
> Eth Header + Packet + Eth trailer = **Eth Frame**

### Ethernet Header
1. Preamble
    * **7 bytes**
    * Is series of alternating 1's and 0's
    * 10101010 + 10101010 + etc
    * Allows devices to syncronize their receiver clock
2. SFD(Start Frame Delimiter)
    * Is used for **syncronization**
    * Allow device to be prepared to receive rest of a data in a frame
    * **1 byte**
    * Is exactly **10101011**
    * It indicates **ends** of the preamble and the **begining** of the frame
> **Preamble** and **SFD** is usually not considered part of ethernet header

> There is a minimum limit for **frame size** which is **64 bytes**  
> Considering total size of header and trailer(excluding preamble and SFD)
> is **18 bytes**, so **minimum packet size** is **46 bytes**  
> If payload is less than 46 bytes **paddings** are added which are **zeroes**

3. Destintaion
    * Consist of destination **MAC Address**
> **MAC** stands for **Media Access Control**  
> Consists of **6 bytes** address of physical device  
> This is seperate from **logical address like *IP Address***
4. Source
    * Consist of source **MAC Address**
5. Type
    * Indicates **layer 3 protocol** used to encapsulate packet
    * Which is always IPv4 or IPv6
    * **However** sometimes this is a **length** field indicating length of
      encapsulated data depending on the version of ethernet
    * **2 bytes**
> If the value is **1500** or **less** it is indicating **length** of the encapsulated **packet** in **bytes**

> If the value is **1536** or **greater** it is indicating **type** of the
> encapsulated **packet**, which is **IPv4** or **IPv6**  
> **IPv4** = 0x0800 = 2048  
> **IPv6** = 0x86DD = 34525

### Ethernet Trailer
* Has only one field **FCS**
* **Frame Check Sequence**
* Is used receiving device to catch **errors** which may occured during
  transmission by running **CRC** algorithm
  * **CRC** means **Cylclic Redundancy Check**
* **4 bytes**

> Total size is **26 bytes** (**header** + **trailer**)

## MAC Address
* **BIA** or **Burned-In Address**
* Is globally unique
* The first **3 bytes** are **OUI**
  * **Organization Unique Identifier**
  * Cisco, Huawei, D-Link, etc
* The last **3 bytes** are **device unique identifiers**
* Written as **12 hexadecimal characters**

> **MAC Address Table**  
> A table which **switch** stores **port number** of devices assosiated with
> their MAC Address

> On cisco switches MAC Addresses are **removed** from the table in **5 minutes**
> of inactivity, this is known as **Aging**

## Types of Ethernet Frames
* **Unicast frame**
  * Destined for **single target**
  * **Known unicast frame**
    * Refers to a situation which switch **knows** the location of destication
      **MAC Address**
    * So it **FORWARD** the frame to **known port**
  * **Unknown unicast frame**
    * Refers to a situation which switch **does not know** the location of
      destination **MAC Addresss**
    * So it **FLOOD** the frame, which means for through all of it's interfaces,
      except the port which received packet on
* **Broadcast frame**
  * Sends message to **all** devices in **LAN**
  * **FFFF:FFFF:FFFF** is broadcast destination MAC address
* **Multicast frame**
  * ?

> **Dynamically Learned MAC Address** is a feature in switches to learn
> MAC Addresses connected to each ethernet port of them

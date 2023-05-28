# Topics
* Interface **speed** and **duplex**
  * Speed refers to **bitrate** of connection
  * Duplex refers to **data flow direction** in interfaces
    **Full-duplex**, **Half-duplex**
  * Refers to where device **transmits** and **receives** data
    **at the same time**
* Speed and duplex **autonegotiation**
  * Allows two devices to negotiate **speed** and **duplex** settings without
    having to manually configure
* Interface Status
* Interface **counters** and **errors**
  * Counters of **trafic** passed through switches

# Commands
## `show interfaces brief`

## `show interfaces status`

### Name
This is description column

### Status
`connected` or `notconnected`

### Vlan
It can be used to **divide LAN** to **smaller LANS**

### Duplex
Is **auto** by default
* `auto` will automatically detected
* `a-full` automatically detected as **full-duplex**

### Speed
Is **auto** by default
* `auto` will automatically detected
* `a-100` automatically detected as **100 Mbps**

> `speed X` changes speed of interface

### Type
Is type of interface
* `10/100BaseTX`
* `100/1000BaseTX`
* `1G/10GBaseTX`
* `SFP`

> `duplex X` changes dulpex of interface  
> X can be either `full` or `half`

> `interface range f0/5 - 12`  
> `interface range f0/5 - 6, f0/5-12`  
> Configures interface rage

> Interfaces should be set to `shutdown` for **security** purposes

# Full/Half Duplex
* **Full duplex** means device **can** send and receive data **at the same time**
* **Half duplex** means device **cannot** send and receive data **at the same time**

## Hubs
* **Broad casts** messages
* Should use **Half duplex** with them because of an event called
  **collision effect**, which happens when **two or more** hosts try to send data
  over network, **watch 15:00**

## CSMA/CD
**Carrier Sense Multiple Access With Collision Detection**
* Describes how devices avoid **collisions** in **half-duplex** situation
> Listens to **collision domain** to be sure **no one** is sending data  
> If a collision **does happen** which can be cause of **bad timing**
> Device sends a jamming signal to inform the other devices that a **collison**
> happened  
> Each devices waits a random period of time before sending frames again

> **Switches** now have one **collision domain** for **each interface**  
> Because of improvements of **switches** over hubs, these devices can operate on
> **full-duplex**  
> Although collisions still occur, they are rare and usually cause of
> misconfiguration

> Interfaces run at different speeds(**10/100** or **10/100/1000**) have default
> setting of `speed auto` and `duplex auto`  
> Interfaces **advertise** their capabilities to neighboring devices and they
> will negotiate in best **speed** and **duplex**

## What happens if **auto-negotiation** is only active on switch?
* Switch tries to use **maximum speed possible**, if it fails at any step it
  **falls back** to lower speed
* For **duplex**, if speed is 1G switch uses **full-duplex**, otherwise uses
  **half-duplex**

### Duplex Mismatch
  Occurs when switch uses different **duplex** than then one on the host

# `show interface f0/2`

## Runts
**Frames** that are **smaller** than **minimum** frame size( **64 bytes** )

## Giants
**Frames** thar are **larger** than **maximum** frame size( **1518 bytes** )

## CRC
**Frames** which **failed** the CRC check

## Frame
**Frames** which have **incorrect** format

## Input Errors
**Total** of all top 4 errors

## Output Errors
**Frames** switch tried to send, but **failed** due to an error

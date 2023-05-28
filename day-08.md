> Maximum number of host addresses in ipv4 is calculated with **`2 ^ n - 2`**

# `show ip interface brief`
Shows brief information about **IP addresses** on **interfaces**

## OK?
Represents whether IP assigned correctly
* On modern devices **does not allow** to assign **wrong** IP addresses

## Method
manual / DHCP

## Status
Status of NIC(Network Interface Card)  
Represents **layer 1** status of interface  
Shown as **interface** is up

### `administravely down`
Interface has been disabled by `shutdown` command
* This is a **default** status of cisco **router** interfaces
* Cisco **switch** interfaces are **not** down by default

## Protocol
Represents **layer 2** status of interface  
Shown as **line protocol** is up

# Configuring Interface
```
enable
configure terminal
interface gigabitethernet 0/0
```

## Setting IP Address
```
enable
configure terminal
ip address 192.168.1.1 255.255.255.0
no shutdown
```
> Used to setting up an **layer 1** interface

# Show Commands
`show interfaces g0/0`
* **bia** refers to **physical MAC address** of interface
  This command also shows current MAC address besides **bia**

`show interfaces description`
* Is similar to `show interfaces brief` but also shows **description** column

## Configuring Interface **Description**
```
enable
configure terminal
interface g0/0
description [description]
```

> Use `end` to go back to **priviledged exec mode**

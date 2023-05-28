# ARP
* **Address Resolution Protocol**
* Is used by **hosts** to find out **MAC address**(layer 2) from
  **IP address**(layer 3) in **LAN**
* Hosts **should find out** destination MAC address **by themselves**

## ARP Message
* ARP request
  * Is sent as **broadcast** ethernet frame
> Source sends **ARP request**  
> SRC IP: 192.168.1.2  
> DST IP: 192.168.1.4  
> SRC MAC: 0123:4567:89AB  
> DST MAC: **FFFF:FFFF:FFFF**  
> This MAC is known as **broadcast** messsage  
> DST Replies with **unicast ethernet frame**  
> SRC updates its **ARP Table**
* ARP reply
  * Is a **unicast** ethernet frame

## ARP Table
* Static
  * Added manually
* Dynamic
  * Learned dynamically

## Ping
* Is a network utility to test **reachability**
* Measures **round-trip** time
* Uses **2 messages**
  1. **ICMP echo request**
  2. **ICMP echo reply**

> `show arp` shows arp table in **Cisco IOS**

> `show mac[-]address-table` shows **MAC Table** in **IOS**  
> [-] is for old **IOS** versions, newer models removed the use of -

> `clear mac address-table dynamic`  
> `clear mac address-table dynamic address 0c2f.b011.9d00`  
> `clear mac address-table dynamic interface Gi0/0`

# Ethernet

> **Ethernet** defined in IEEE 802.3 standard in 1983.

> **IEEE** stands for institude of Electrical and Electronics Engineers

## Ethernet Standards
| Speed    | Common Name         | IEEE Standard | Informal Name |
| -------- | ------------------- | ------------- | ------------- |
| 10 Mbps  | Ethernet            | 802.3i        | 10-Base-T     |
| 100 Mbps | Fast Ethernet       | 802.3u        | 100-Base-T    |
| 1 Gbps   | Gigabit Ethernet    | 802.3ab       | 1000-Base-T   |
| 10 Gbps  | 10 Gigabit Ethernet | 802.3an       | 10G-Base-T    |

## **UTP** Cables
> **UTP** stands for Unshielded Twisted Pair

### **Ethernet** and **Fast Ethernet**
uses 2 pairs (**4 wires**)

### **Gigabit** Ethernet and **10 Gigabit** Ethernet
uses 4 pairs (**8 wires**)

---

#### **Straight-through** cable on 4 wires
> Transmit(Tx)  **1 ---> 1**  Receive(Rx)  
> Transmit(Tx)  **2 ---> 2**  Receive(Rx)  
> Receive(Rx)   **3 <--- 3**  Transmit(Tx)  
> Receive(Rx)   **6 <--- 6**  Transmit(Tx)

#### **Crossover** cable on 4 wires
> Transmit(Tx)  **1 ---> 3**  Receive(Rx)  
> Transmit(Tx)  **2 ---> 6**  Receive(Rx)  
> Receive(Rx)   **3 <--- 1**  Transmit(Tx)  
> Receive(Rx)   **6 <--- 2**  Transmit(Tx)

---

##### Transmit pins table
| Device Type | Transmit Pins (Tx) | Receive Pins (Rx) |
| ----------- | ------------------ | ----------------- |
| Router      | 1 and 2            | 3 and 6           |
| Firewall    | 1 and 2            | 3 and 6           |
| PC          | 1 and 2            | 3 and 6           |
| Switch      | 3 and 6            | 1 and 2           |

> **Auto MDI-X** is a feature to handle pin switching for devices which have same
> receive and transmit pins attached to each other

---

#### **Straight-through** cable on 8 wires
> Each pair is **bidirectional**  
> **1 <--> 1**  
> **2 <--> 2**  
> **3 <--> 3**  
> **4 <--> 4**  
> **5 <--> 5**  
> **6 <--> 6**  
> **7 <--> 7**  
> **8 <--> 8**  

# **Fiber-Optic** connections
Consists of two fiber-optic cable, one for Tx and one for Rx.

> **SFP Transceiver** stands for Small Form-factor Pluggable

---

## **Fiber-Optic Cable**
1. Fiberglass core
2. Cladding that reflects light
3. A protective buffer
4. Outer jacket of cable

---

### **Mode**
1. Single-mode
  * Narrower
  * Laser based transmitter
  * Longer cable length
  * More expensive, due to expensive laser-based SFP transmitter
2. Multimode
  * Core is wider
  * Allow multiple angles (modes) of light
  * Longer cable than UTP, But **Shorter** than single-mode fibers
  * Cheaper than single mode, cheaper LED based SFP transmitter

---

## Fiber-Optic Standards
| Speed    | Cable Type          | IEEE Standard | Informal Name | Length              |
| -------- | ------------------- | ------------- | ------------- | ------------------- |
| 1 Gbps   | Multi or Single     | 802.3z        | 1000-Base-LX  | 550m (MM), 5Km (SM) |
| 10 Gbps  | Multimode           | 802.3ae       | 10G-Base-SR   | 400m                |
| 10 Gbps  | Single-Mode         | 802.3ae       | 10G-Base-LR   | 10Km                |
| 10 Gbps  | Single-Mode         | 802.3ae       | 10G-Base-ER   | 30Km                |

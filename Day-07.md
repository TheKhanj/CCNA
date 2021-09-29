# Subnet Mask
* Used to tell which part of address represents **network** and which part of
  address represents **end-hosts** respectively
* For subnet of **24** it means, **first 24 bits** represents **network address**
  and remaining bits represents **host address**

> Router **needs IP address** for **each** network which is connected to

# IPv4 Headers
* **Source** IP address
* **Destination** IP address

> IP addresses are **4 bytes** or **32 bits** in length

> IPv4 addresses are written in **dotted decimal**, which is 4 decimal numbers
> seperated by 3 dots

> ### **Decimal**, **Binary**, **Hexadecimal** form of ip
> Decimal: **192.168.1.1**  
> Binay: **11000000.10101000.00000001.00000001**  
> Hexadecimal: **C0.A8.01.01**

> Each of **8 bits** groups are refered to as **Octects**

# IPv4 Address Classes
| Class | First Octet | First Octet Numeric | Prefix Length |
| ----- | ----------- | ------------------- | ------------- |
|   A   |  0XXXXXXX   |       0 - 127       |      /8       |
|   B   |  10XXXXXX   |     128 - 191       |      /16      |
|   C   |  110XXXXX   |     192 - 223       |      /24      |
|   D   |  1110XXXX   |     224 - 239       |               |
|   E   |  1111XXXX   |     240 - 255       |               |

> **Class D** is reserved for **multicast addressses**  
> **Class E** is reserved for **experimental uses**

> The end of **class A** is usually considered to be **126** not **127**  
> * **127** is reserved for **loopback** addresses
> * Is used to test the **network stack** on the local device

> **First** address of network is **network address**, 192.168.1.**0**  
> **Last** address of network is **broadcast address**, 192.168.1.**255**

> **Netmast** is another form of writing **prefix length**  
> **24** prefix length becomes **255.255.255.0** netmast

# Network Address
If **host** portion of address is all **0s** it means it's **network address**

# Broadcast Address
If **host** portion of address is all **1s** it means it's **broadcast address**
* If layer 3 destination **IP address** of packet is **broadcast address** then
  layer 2 **MAC address** is all **1s** for that **frame**, **FFFF:FFFF:FFFF**

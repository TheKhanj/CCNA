# **Cisco IOS**
* Cisco IOS is an operating system for cisco devices

## Serial port
  * USB Serial port
  * RJ45 Serial port
    * Rollover cable, RJ45 to DB9(VGA-Serial)

### **Rollover Cable**
* It's like UTP crossover cable
* VGA has 9 pins, one of them is unused
> **1 <--> 8**  
> **2 <--> 7**  
> **3 <--> 6**  
> **4 <--> 5**  
> **5 <--> 4**  
> **6 <--> 3**  
> **7 <--> 2**  
> **8 <--> 1**  

### Serial Port
* Speed(Braud Rate) - 9600
* Data bits - 8
* Stop bit - 1
* Parity - is used to detect errors - None
* Flow control - None

# IOS Modes
* **User EXEC mode**
  * **[hostname] >**
  * Very limited
  * Look at some things, but can't change anything
  * Also called **user-mode**
* **Priviledged EXEC mode**
  * Enter using `enable` command
  * **[hostname] #**
  * Provide complete access to view configuration, restart, etc
  * **Can't** change configuration
  * **Can** change **time**
* **Global configuration mode**
  * Enter using `configure terminal` command
  * Set password using `enable password PASSWORD` command

# Configurations
* **Running config**
  * The **current** active config
* **Startup config**
  * **Boot** time config

> `show running-config`  
> Shows running config in priviledged exec mode

> `show startup-config`  
> Shows startup config in priviledged exec mode

## Saving configurations
There are three ways to do so
1. `write`
2. `write memory`
3. `copy running-config startup-config`

## Encrypting passwords
To encrypt passwords run `service password-encryption` in **global config mode**

> There are several password encryption methods  
> 7: Cisco proprietory encription algorithm (Not safe)  
> 5: MD5

> **`do`** command runs user priviledged mode commands in global configuration mode

### Securing passwords
[config mode] `enable secret SECRET`
> If both `enable secret` and `enable password` are configured, `enable password` would be ignored

## Negating commands
`no` is used to negate commands

Example: `no service password-encryption`

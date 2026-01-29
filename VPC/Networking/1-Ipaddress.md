# IP address

An IP address functions as a unique identifier for devices, similar to a phone number, allowing them to communicate with one another and connect to the internet. In the context of modern networking, nearly every electronic device—from smartphones and watches to smart toilets—requires an IP address to function within a network.

# Concept

```
Wireless LAN adapter Wi-Fi:

   Connection-specific DNS Suffix  . : home
   IPv6 Address. . . . . . . . . . . : 2001:4958:3f10:ba01:6d42:7673:4add:d0e2
   Temporary IPv6 Address. . . . . . : 2001:4958:3f10:ba01:7533:4100:c026:7497
   Link-local IPv6 Address . . . . . : fe80::df9c:fc2d:93f0:e6f9%10
   IPv4 Address. . . . . . . . . . . : 192.168.2.87
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . : fe80::daa7:56ff:fe02:8da8%10
                                       192.168.2.1
```

The following key concepts define how IP addresses work and how they are managed:

1. Finding and Assigning IP Addresses

- Discovery: You can find a device's IP address using commands like **ipconfig** on Windows, **ifconfig** on Linux or Mac, or by checking the Wi-Fi settings on a mobile device.

- Assignment: Devices typically receive their IP addresses from a router, which acts as the central hub of a local network. This automatic distribution process is handled by a protocol called DHCP.

2. The Anatomy of an IP Address

An IP address is composed of four sets of numbers separated by dots, known as octets(8 bits). To understand how an IP address functions, it must be looked at alongside its "best friend," the subnet mask:

- Network Portion: This is like the street name in a housing analogy. If a subnet mask contains 255 in an octet, the corresponding number in the IP address is "locked in" and remains the same for every device on that specific network. **E.g.** 192.168.2.2 is the IP address of your device, the 192.168.1 is the Network Portion, and if 255.255.255.0 is the subnet mask, all the network portion can only be the same i.e. the first 3 Octets: 192.168.2 will never change as the first 3 Octets are 255.


- Host Portion: This is akin to a house number. In octets where the subnet mask is 0, the IP address number can change to identify specific devices (hosts) on that street. **E.g.** 192.168.2.2 is the IP address of your device, the fourth Octet 2 is the Host Portion, It can be between 0-255.

3. Communication and Gateways

- Local Traffic: If two devices share the same network portion (they are on the same "street"), they can communicate directly with each other.

- External Traffic: When a device needs to communicate with something outside its local network—such as a website like Netflix, it sends the data to the default gateway (the router). The gateway knows how to route that information to the external destination.

4. Usable IP Addresses and Restrictions

In a common network setup (where the first three octets are locked), there are 256 possible mathematical combinations (0 to 255). However, there are typically only 253 usable addresses for devices because of three specific reservations:

- Network Address: The very first address (e.g., .0) is reserved to identify the network itself.

- Broadcast Address: The very last address (e.g., .255) is used to send information to every device on the network simultaneously.

- Router Address: The router (default gateway) itself requires one of the addresses to function within the network.
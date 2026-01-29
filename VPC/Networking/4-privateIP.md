# Private IP (Not unique)

 The IPv4 Crisis and RFC 1918: In 1996, the internet faced a shortage of available IP addresses because the original designers only created about 4.3 billion of them. To prevent the internet from "ending," RFC 1918 was introduced as a "giant band-aid," creating private IP addresses and Network Address Translation (NAT)

- Public IP address: To route around the internet one is needed.

To know your router's/your only public IP address visit [website](https://whatismyipaddress.com/)

- Private IP: Private IP addresses were created by taking chunks out of the Class A, B, and C address ranges. These addresses are not unique—meaning millions of homes can use the same range (like 192.168.1.0)—but they are not publicly routable, meaning they cannot connect to the internet on their own


| Class | Private IP Range                  | Default Subnet Mask |
|------:|----------------------------------|---------------------|
| A     | 10.0.0.0 – 10.255.255.255         | 255.0.0.0           |
| B     | 172.16.0.0 – 172.31.255.255       | 255.255.0.0         |
| C     | 192.168.0.0 – 192.168.255.255     | 255.255.255.0       |


# NAT (Network Address Translation)

NAT allows a router to translate multiple private IP addresses into one single public IP address borrowed from an Internet Service Provider (ISP). When a device on a home network (like a smart phone or computer) wants to access a website, the router "magically" translates that private identity into the public one to communicate with the web.

# Router

The router manages the flow of data; when a website sends information back, the router knows exactly which internal private IP address requested it and forwards the data accordingly.


# The Transition to IPv6

- Despite the success of NAT, the world still ran out of IPv4 addresses, leading to the creation of IPv6. IPv6 addresses are much larger (2power128), providing enough unique public addresses for every device in the world to connect directly to the internet without needing the NAT "Band-Aid".

- Modern Cellular Networks: Unlike most home networks, many cellular providers now assign public IPv6 addresses directly to mobile phones.


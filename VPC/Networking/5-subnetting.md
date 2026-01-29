# Subneting based on number of networks needed.

- For e.g. my IPV4 address & subnetmask of my laptop is

   IPv4 Address. . . . . . . . . . . : 192.168.1.0
   Subnet Mask . . . . . . . . . . . : 255.255.255.0

- 255.255.255.0 (Subnet mask in Decimal) = 11111111.11111111.11111111.00000000 

The Subnet mask will always have row of 1's and row of 0's (contiguous)

**Available hosts for this network** = 2⁸ − 2 = 254

Where network bits = 11111111.11111111.11111111 (as 255 is in the first 3 Octets)
      host bits = 00000000

# Need more networks

Let's say we would like to break the subnet mask (255.255.255.0) into **4 networks**.

## Hack the host bits (from left to right)

- Charts to calculate how many host bits you need to HACK and create 4 networks

    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
    |-----|----|----|----|---|---|---|---|
    | 256 |128 | 64 | 32 |16 | 8 | 4 | 2 |

- If we need 4 networks, we need to hack 2 host bits as number 4 is in the 2nd bit position.

- If we need 17 networks, we need to hack 5 host bits as 17 falls under 32 as it's more than 16 and hence the 5th bit position.

- Now, since we need 4 networks and it needs to hack 2 bits from the host, it gives the following binary:

11111111.11111111.11111111.11000000 (The ones are added after the decimal as the Octets of Subnet mask are contiguous)

11111111.11111111.11111111.11000000 = 255.255.255.192 (New subnet mask after hacking the bits)

Network bits are = 26 (Counting all 1's) and hence /26 network

   IPv4 Address. . . . . . . . . . . : 192.168.1.0/26
   Subnet Mask . . . . . . . . . . . : 255.255.255.192

# Find the increment

The increment is the last network bit we have:

i.e. 11111111.11111111.11111111.11000000 (the second 1 of the last octet or the host octet)

    |  1  | 1  |  0 |  0 | 0 | 0 | 0 | 0 |
    |-----|----|----|----|---|---|---|---|
    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 0 |

Which if we map with the chart is 64, hence 64 is the increment.

We will use this increment to determine the size of the networks and what the ranges are.

# Create your network using subnetting (divided into 4)

192.168.1.0 - 192.168.1.63
192.168.1.64 - 192.168.1.127
192.168.1.128 - 192.168.1.191
192.168.1.192 - 192.168.1.255

Each of these network will have a subnet mask of 255.255.255.192/26

To figure out how many hosts are available in these networks

host bits = 6, as 2 bits are hacked by the network.

2power6 = 64 - 2 = 62 hosts



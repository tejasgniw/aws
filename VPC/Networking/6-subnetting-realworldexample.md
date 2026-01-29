# Subnetting based on number of hosts needed 

The network 10.1.1.0/24

**To Solve**: We need 40 hosts per network

The subnet mask would be 255.255.255.0


    |     |    |    |    |   |   |   |   |
    |-----|----|----|----|---|---|---|---|
    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 0 |

Using the above chart, the binary of 255.255.255.0 is

11111111.11111111.11111111.00000000

Steps to break into networks or hosts:

1) Use chart to calculate how many host bits we need to hack.

2) Save the host bits (from right to left)

3) Find the increment.

4) Create your networks.

## Use chart to calculate how many host bits we need to hack.

    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
    |-----|----|----|----|---|---|---|---|
    | 256 |128 | 64 | 32 |16 | 8 | 4 | 2 |

For having 40 hosts, we need 6 hosts bits as it falls under 6th position from the left

## Save the host bits from 

We need to save 6 host bits from right to left making:

11111111.11111111.11111111.00000000 (Before saving)

this

11111111.11111111.11111111.11000000 (After saving)

## Find the increment

The increment is the last network bit we have:

i.e. 11111111.11111111.11111111.11000000 (the second 1 of the last octet or the host octet)

    |  1  | 1  |  0 |  0 | 0 | 0 | 0 | 0 |
    |-----|----|----|----|---|---|---|---|
    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 0 |


Which if we map with the chart is 64, hence 64 is the increment.

We will use this increment to determine the size of the networks and what the ranges are.

# Create your network using subnetting based on the hosts needed

Needed hosts per network is 40, however since we get it under increment 64, the netoworks are:

10.1.1.0   -  10.1.1.63
10.1.1.64  -  10.1.1.127
10.1.1.128 -  10.1.1.191
10.1.1.192 -  10.1.1.255


Each of these network will have a subnet mask of 255.255.255.192/26

where 26 is the CIDR notation. Hence,

   IPv4 Address. . . . . . . . . . . : 10.1.1.0/26, 10.1.1.64/26, 10.1.1.128/26, 10.1.1.192/26
   Subnet Mask . . . . . . . . . . . : 255.255.255.192/26
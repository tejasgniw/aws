# The calculation

- An IPv4 address is 32 bits(4 bytes).

- Example:
192.168.1.10 (Decimal) = 11000000.10101000.00000001.00001010 (Binary)

- For the following classes these bits are fixed:

| Class | Network bits | Host bits |
| ----: | -----------: | --------: |
|     A |            8 |        24 |
|     B |           16 |        16 |
|     C |           24 |         8 |


- If you have n bits, you can create: 2ⁿ combinations

i.e. 

1 bit → 2 values
2 bits → 4 values
8 bits → 256 values
24 bits → 16,777,216 values

# Class A

[N][H][H][H]    

i.e. Network bits = 8, Host bits = 24
first bit = 0 (class identifier)


- **Hosts per network**:

```
    2²⁴ = 16,777,216
```

But: all 0s → network address, all 1s → broadcast address

E.g. IP address 10.0.0.0 (binary 00001010 . 00000000 . 00000000 . 00000000)

**Case 1**: — All host bits = 0, i.e. IP address 10.0.0.0 (Network identifier)

00001010 . 00000000 . 00000000 . 00000000

**Case 2**: — All host bits = 1, i.e. IP address 10.255.255.255 (Broadcast)

00001010 . 11111111 . 11111111 . 11111111

**Usable hosts per network** = 2²⁴ − 2 = 16,777,214


- **How many Class A networks?**

First bit is fixed to 0
That leaves 7 bits to identify networks

```
2⁷ = 128 networks
```

But:
0.0.0.0 → reserved
127.0.0.0 → loopback

**Usable Class A networks** = 2⁷ - 2 = 126


################################################


# Class B

[N][N][H][H]    

i.e. Network bits = 16, Host bits = 16
first two bits = 10 (class identifier)


- **Hosts per network**:

```
    2¹⁶ = 65,536
```

But: all 0s → network address, all 1s → broadcast address

E.g. IP address 172.16.0.0 (binary 10101100 . 00010000 . 00000000 . 00000000)

**Case 1**: — All host bits = 0, i.e. IP address 172.16.0.0 (Network identifier)

10101100 . 00010000 . 00000000 . 00000000

**Case 2**: — All host bits = 1, i.e. IP address 172.16.255.255 (Broadcast)

10101100 . 00010000 . 11111111 . 11111111

**Usable hosts per network** = 2¹⁶ − 2 = 65,534


- **How many Class B networks?**

First two bits = 10
That leaves 14 bits to identify networks

```
2¹⁴ = 16,384 networks
```

**Usable Class A networks** = 2¹⁴ = 16,384 networks


##############################

# Class C

[N][N][N][H]    

i.e. Network bits = 24, Host bits = 8
first two bits = 110 (class identifier)


- **Hosts per network**:

```
    2⁸ = 256
```

But: all 0s → network address, all 1s → broadcast address

E.g. IP address 192.168.1.0 (binary 11000000 . 10101000 . 00000001 . 00000000)

**Case 1**: — host bit = 0, i.e. IP address 192.168.1.0 (Network identifier)

11000000 . 10101000 . 00000001 . 00000000

**Case 2**: — host bit = 1, i.e. IP address 192.168.1.255 (Broadcast)

11000000 . 10101000 . 00000001 . 11111111

**Usable hosts per network** = 2⁸ − 2 = 254


- **How many Class C networks?**

First three bits = 110
That leaves 21 bits to identify networks

```
2²¹ = 2,097,152 networks
```

**Usable Class A networks** = 2²¹ = 2,097,152 networks


# One tiny summary (remember this)

- IPv4 = 32 bits

- Class decides how many bits are network vs host

- Hosts = 2^(host bits) − 2

- Networks = 2^(network identifier bits)



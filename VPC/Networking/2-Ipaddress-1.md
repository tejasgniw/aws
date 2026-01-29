# Ran out of IP addresses

- 2^32 = 4,294,967,296 (Around 4.3 Billion)

- List of IP addresses

| Class | IP Range                    | Subnet Mask       |
|------:|-----------------------------|-------------------|
| A     | 1.0.0.0 – 126.255.255.255   | 255.0.0.0         |
| B     | 128.0.0.0 – 191.255.255.255 | 255.255.0.0       |
| C     | 192.0.0.0 – 223.255.255.255 | 255.255.255.0     |
| D     | 224.0.0.0 – 239.255.255.255 | Multicast         |
| E     | 240.0.0.0 – 255.255.255.255 | Experimental      |

# Explanation

- Class A: Designed for massive organizations like government entities or big companies (e.g., IBM, GE, and AT&T).

    - Default Subnet Mask: 255.0.0.0.

    - Capacity: Over 16 million IP addresses per network (16,777,214).

    - Availability: There are only 126 total Class A networks.

- Class B: Intended for medium-to-large organizations.

    - Default Subnet Mask: 255.255.0.0.

    - Capacity: 65,534 hosts per network.

    - Availability: 16,382 total networks.

- Class C: The most common class, often used for home networks.

    - Default Subnet Mask: 255.255.255.0

    - Capacity: 254 available IP addresses per network.

    - Availability: Over 2 million total networks.

- Class D: Reserved exclusively for multicast. These addresses are important for networking but cannot be used for standard device assignment.

- Class E: These are experimental addresses. They are currently "untouchable" and reserved for mystery or research purposes.

# The Missing Range: Loopback Addresses

The highlight is where the range between Class A and Class B is missing. The entire 127.0.0.0 range is reserved for loopback addresses.

- These are used for network testing to see if a device is "awake" by pinging itself (e.g., pinging 127.0.0.1).

- Over **16 million addresses** were reserved just for a computer to talk to itself, kind of crazy right?

# Classful vs. Classless Networking

- Classful: When a network obeys the rules of the default subnet mask for its class.

- Classless: When a large network is "cut up" into smaller slices with different subnet masks to be more efficient. This process is known as subnetting, and it is the primary way the Internet Assigned Numbers Authority (IANA) currently manages the limited address space to avoid total depletion.
# Subnetting based on number of hosts needed 

The network 172.21.42.0/24

**To Solve**: We need the folowing hosts

1) guests 10
2) customers 57
3) servers 26
4) employees 117

In case of variable subnetting, we go from high to low i.e.

1) employees 117
2) customers 57
3) servers 26
4) guests 10

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

## For employees = 117 hosts

    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
    |-----|----|----|----|---|---|---|---|
    | 256 |128 | 64 | 32 |16 | 8 | 4 | 2 |

1) For having 117 hosts, we need 7 hosts bits as it falls under 7th position from the left

11111111.11111111.11111111.10000000 (Saving host bits)

2) Increment is 128 from the chart below

    |  1  | 0  |  0 |  0 | 0 | 0 | 0 | 0 |
    |-----|----|----|----|---|---|---|---|
    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 0 |

3) Network is 172.21.42.0/25

    172.21.42.0   - 172.21.42.127   


## For customers = 57 hosts

    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
    |-----|----|----|----|---|---|---|---|
    | 256 |128 | 64 | 32 |16 | 8 | 4 | 2 |

1) For having 57 hosts, we need 6 hosts bits as it falls under 6th position from the left

11111111.11111111.11111111.11000000 (Saving host bits)

2) Increment is 128 from the chart below

    |  1  | 1  |  0 |  0 | 0 | 0 | 0 | 0 |
    |-----|----|----|----|---|---|---|---|
    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 0 |

3) Network is 172.21.42.128/26

    172.21.42.128   - 172.21.42.191 


## For servers = 26 hosts

    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
    |-----|----|----|----|---|---|---|---|
    | 256 |128 | 64 | 32 |16 | 8 | 4 | 2 |

1) For having 26 hosts, we need 5 hosts bits as it falls under 5th position from the left

11111111.11111111.11111111.11100000 (Saving host bits)

2) Increment is 128 from the chart below

    |  1  | 1  |  1 |  0 | 0 | 0 | 0 | 0 |
    |-----|----|----|----|---|---|---|---|
    | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 0 |

3) Network is 172.21.42.192/27

    172.21.42.192   - 172.21.42.223

## For guests = 10 hosts

Network is 172.21.42.224/28

172.21.42.224   - 172.21.42.255
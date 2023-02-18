# Calculation of  Network IP, Number of hosts, Range of IP addresses and Broadcasting of an IP from a Specific Subnet #
![ip image](https://user-images.githubusercontent.com/108562214/198391137-6e9388d6-a8bb-49d1-85f5-169795dc16e8.PNG)


## Calculating the IP and Subnet of 193.16.20.35/29 ##

Before calculating, identify the IP address and the subnet first.<br>
<br>
Note that the IP address here is ```193.16.20.35``` and subnet is ```29```.<br>

### Calculating  the Network IP ###

In calculating the network IP and subnet, we must convert both to binary first to get the network IP.<br>
The binary form of the subnet 29 up bits and 3 down bits which sums up 32 bits the allowed number of bits in an IP. The ups are designated 1 while downs 0.
* To get the binary form for the ip address 193.16.20.35, break the numbers individually into a binary form following this step:<br>

```
Binary form of 193

Step 1:
Divide 193 by 2 until the quotient is 0;

193/2 = 96, remainder is 1
96/2 = 48, remainder is 0
48/2 = 24, remainder is 0
24/2 = 12, remainder is 0
12/2 = 6, remainder is 0
6/2 = 3, remainder is 0
3/2 = 1, remainder is 1
1/2 = 0, remainder is 1

Step 2: Read from the bottom to top.
After doing this, you will get 11000001.

Therefore:
193 = 11000001

```

```
Binary form of 16

Step 1:
Divide 16 by 2 until the quotient is 0;

16/2 = 8, remainder is 0
8/2 = 4, remainder is 0
4/2 = 2, remainder is 0
2/2 = 1, remainder is 0
1/2 = 0, remainder is 1

Step 2: Read from the bottom to top.
After doing this, you will get 10000.
Note that it binary form must be an octet i.e. it consists of 8, 0's or 1's. Since there is still space for more, add 0's to complete it to an octet.

Therefore:
8 = 00010000

```

```
Binary form of 20

Step 1:
Divide 20 by 2 until the quotient is 0;

20/2 = 10, remainder is 0
10/2 = 5, remainder is 0
5/2 = 2, remainder is 1
2/2 = 1, remainder is 0
1/2 = 0, remainder is 1

Step 2: Read from the bottom to top.
After doing this, you will get 10100.
Note that it binary form must be an octet i.e. it consists of 8, 0's or 1's. Since there is still space for more, add 0's to complete it to an octet
Therefore:
20 = 00010100

```

```
Binary form of 35

Step 1:
Divide 35 by 2 until the quotient is 0;

35/2 = 17, remainder is 1
17/2 = 8, remainder is 1
8/2 = 4, remainder is 0
4/2 = 2, remainder is 0
2/2 = 1, remainder is 0
1/2 = 0, remainder is 1

Step 2: Read from the bottom to top.
After doing this, you will get 100011.
Note that it binary form must be an octet i.e. it consists of 8, 0's or 1's. Since there is still space for more, add 0's to complete it to an octet
Therefore:
35 = 00100011

```

Therefore the binary form of ``` 193.16.20.35 = 11000001.00010000.00010100.00100011 ```

### Calculating the subnet ###
The subnet here is 29.<br>
Calculating the binary of a subnet is a bit different, it can be achieved through the following steps:<br>

```
Step1:
Subtract 32 from 39
32 - 29 = 3
Note that 32 is the total bits it should contain, so we subtract 29 from it.

( In case you desire to calculate the number of host in the ip address with a subnet mask of /29, you can do 2^3 = 8)

Step 2:
The binary form of the subnet is 29 bits of 1's and 3 bits 0's which sums up  to 32 bits the correct number of bits in an IP. 

Therefore,
29 = 11111111.11111111.11111111.11111000

```

The network address is the ``` logical AND ``` of the respective bits in the binary representation of the IP address and subnet mask.<br>
     193.16.20.35 = 11000001.00010000.00010100.00100011 <br>
     29           = 11111111.11111111.11111111.11111000 <br>
                     --------- logical AND ------------- <br>
                     11000001.00010000.00010100.00100000  <br>
The logical AND value got is then converted to its decimal value to get the Network IP. <br>

     11000001.00010000.00010100.00100000 = 193.16.20.32 <br>
Therefore the Network IP of 193.16.20.35/29 is 193.16.20.32 <br>

## Calculating the Number of Hosts ##

The number of hosts that can be assigned IPs on 193.16.20.35/29 can be calculated with the formula: <br>

 ``` Maximum Number of hosts = 2^(32 - netmask_length) - 2 ``` <br> <br>
 where netmask_length = subnet value <br>
The minus 2 in the formula is to account for addresses reserved for the Network and Broadcast address.<br><br>

Maximum Number of hosts = 2^(32 - 29) - 2 <br>
Maximum Number of hosts = 6 <br>
The number of hosts that can be asigned IP's on the network is ``` 6 ```. <br>

## Calculating the Broadcast IP ##

When calculating for the broadcast IP, note that the host bits of the subnet value are first converted to 1's, and network bits are converted to 0's.<br>
 29 =  11111111.11111111.11111111.11111000 (old subnet value) <br>
 29 =  00000000.00000000.00000000.00000111  (new subnet value) <br>
    
    ``` 11111111.11111111.11111111.11111000 = 00000000.00000000.00000000.00000111 ``` <br>

Do the logical OR operation of the IP address and the new subnet value.<br>

 193.16.20.35     = 11000001.00010000.00010100.00100011 <br>
 New subnet value = 00000000.00000000.00000000.00000111 <br>
                    ----------- logical OR ------------ <br>
                    11000001.00010000.00010100.00100111  <br>

Convert the value got from the logical OR operation to its decimal value in order to get the IP pf the network. <br><br.

11000001.00010000.00010100.00100111 = 193.16.20.39<br>

Therefore:<br>
The Broadcast IP of ``` 193.16.20.35/29 is 193.16.20.39 ``` <br><br>

## Calculating for the Range of IP Addresses ##

The range of IP addresses that can be assigned to the hosts can be located between the value of the Network IP and the Broadcast IP i.e 193.16.20.32 - 193.16.20.39.,br>

Note that the network IP = 192.16.20.32<br>
The broadcast IP = 192.16.20.39<br>
Theerefore, the range of IP addresses are: <br>
 ```` 
     193.16.20.33
     193.16.20.34
     193.16.20.35
     193.16.20.36
     193.16.20.37
     193.16.20.38

```   




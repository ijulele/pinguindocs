Subnetting
==========

.. sidebar:: Documented by :

     * **Code Name**    : NDA
     * **Date** 	: 12/17/2015
     * **Mail** 	: naufal.itt@gmail.com

Tips
----

- What you need to remember 
    /24 = 256
    /25 = 128
    /26 = 64
    /27 = 32
    /28 = 16
    /29 = 8
    /30 = 4
    /31 = 2
    /32 = 1


- A = /8 - /15
  12345678.XXXXXXXX.12345678.12345678

- B = /16 - /23
  12345678.12345678.XXXXXXX.12345678

- C = /24 - /32
  12345678.12345678.12345678.XXXXXXXX


IP
10.10.10.50/30
20.20.20.50/28
30.30.30.30/19
40.40.40.40/13

Question 
1. How many IP in subnet ?
2. Subnet Mask ?
3. IP Network, Broadcast, and Range IP Host ?

10.10.10.50/30
/30 = 4
/30 located in C
1. How many IP in subnet ? 4
2. Subnet Mask ? 256 - 4 = 255.255.255.252
3. IP Network & Broadcast 
    /30 = 4
    0 - 3
    4 - 7
      .
      .
    48 - 51 ----> .50 located between 48 - 51
    IP Network = 10.10.10.48
    IP Broadcast = 10.10.10.51
    IP Host = 10.10.10.48 - 10.10.10.50

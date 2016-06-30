Subnetting
==========

Tips
----

- What you need to remember 
::

    /24 = 256
    /25 = 128
    /26 = 64
    /27 = 32
    /28 = 16
    /29 = 8
    /30 = 4
    /31 = 2
    /32 = 1

- Location
::

  A = /8 - /15
  12345678.XXXXXXXX.12345678.12345678

  B = /16 - /23
  12345678.12345678.XXXXXXX.12345678

  C = /24 - /32
  12345678.12345678.12345678.XXXXXXXX
  
  When it's located in A or B, shift it to C
  ex = /18 shift to /26 (just shift it by 8)
       /9  shift to /17 (Still located in B), shift to /25


- IP
::

    10.10.10.50/30
    20.20.20.50/28
    30.30.30.30/19
    40.40.40.40/13

- Question
::

    1. How many IP in subnet ?
    2. Subnet Mask ?
    3. IP Network, Broadcast, and Range IP Host ?

- Answer for 10.10.10.50/30
::

    /30 = 4
    /30 located in C
    1. How many IP in subnet ? 4
    2. Subnet Mask ? 256 - 4 = 255.255.255.252
    3. IP Network & Broadcast 
    /30 = 4
    
        Because its 4 then :
        0 - 3
        4 - 7
          .
          .
        48 - 51 ----> .50 located between 48 - 51
    
    IP Network = 10.10.10.48
    IP Broadcast = 10.10.10.51
    IP Host = 10.10.10.48 - 10.10.10.50- Answer for 10.10.10.50/30

- Answer for 20.20.20.50/28    
::

    /28 = 16
    /28 located in C
    1. How many IP in subnet ? 16
    2. Subnet Mask ? 256 - 16 = 255.255.255.240
    3. IP Network & Broadcast 
    /28 = 16
    
        Because its 16 then :
        0 - 15
        16 - 31
          .
          .
        48 - 63 ----> .50 located between 48 - 63
    
    IP Network = 20.20.20.48
    IP Broadcast = 20.20.20.63
    IP Host = 20.20.20.49 - 20.20.20.62
    
- Answer for 30.30.30.30/19    
::

    /19 = 32 (shifted /19 + 8 = /27)
    /29 located in B
    1. How many IP in subnet ? 32 x 256 = 8192
    2. Subnet Mask ? 256 - 32 = 255.255.224.0
    3. IP Network & Broadcast 
    /19 = 32
    
        Because its 32 then :
        0 - 31  ----> .30 located between 0 - 31
    
    IP Network = 30.30.0.0
    IP Broadcast = 30.30.31.255
    IP Host = 30.30.0.1 - 30.30.31.254
    
- Answer for 40.40.40.40/13    
::

    /13 = 8 (shifted /13 + 8 = /21 + 8 = /29)
    /13 located in A
    1. How many IP in subnet ? 8 x 256 x 256 = 524288
    2. Subnet Mask ? 256 - 8 = 255.248.0.0
    3. IP Network & Broadcast 
    /13 = 8
    
        Because its 8 then :
        0 - 7
        8 - 15
          .
          .
        40 - 47  ----> .40 located between 40 - 47
    
    IP Network = 40.40.0.0
    IP Broadcast = 40.47.255.255
    IP Host = 40.40.0.1 - 40.47.255.254  


**Sources :**
 * ID-Networkers

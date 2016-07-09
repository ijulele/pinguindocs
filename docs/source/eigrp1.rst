EIGRP - network advertise with wildcard
=======================================

TOPOLOGY

.. image:: /images/eigrp.png
    :width: 200px
    :height: 400px

- Make a loopback interface
::	
	
	R5#conf
	R5(config)#int lo99
	R5(config-if)#ip add 15.15.0.1 255.255.255.255

	
- Network advertise with no wildcard
::
	
	R5#conf
	R5(config)#router eigrp 100
	R5(config-router)#network 15.15.15.5 
	R5(config-router)#no auto-summary

- if we dont use wildcard mask 

::
	
	show run | s eigrp 100
		!
	!
	router eigrp 100
	 network 15.0.0.0
	!

	R1#sh ip ro 15.15.0.1
	Routing entry for 15.15.0.1/32
 	 Known via "eigrp 100", distance 90, metric 156160, type internal
 	 Redistributing via eigrp 100
 	 Last update from 15.15.15.5 on FastEthernet4/0, 00:00:03 ago
 	 Routing Descriptor Blocks:
 	 * 15.15.15.5, from 15.15.15.5, 00:00:03 ago, via FastEthernet4/0
      Route metric is 156160, traffic share count is 1
      Total delay is 5100 microseconds, minimum bandwidth is 100000 Kbit
      Reliability 255/255, minimum MTU 1500 bytes
      Loading 1/255, Hops 1

	R1#ping 15.15.0.1
	Type escape sequence to abort.
	Sending 5, 100-byte ICMP Echos to 15.15.0.1, timeout is 2 seconds:
	!!!!!
	Success rate is 100 percent (5/5), round-trip min/avg/max = 28/45/52 ms


- Use wildcard
::

	R5#conf
	R5(config)#router eigrp 100
	R5(config-router)#network 15.15.15.5 0.0.0.0

	R1#ping 15.15.0.1                                                    
	Type escape sequence to abort.
	Sending 5, 100-byte ICMP Echos to 15.15.0.1, timeout is 2 seconds:
	.....
	Success rate is 0 percent (0/5)

	R1#sh ip ro 15.15.0.1
	% Subnet not in table
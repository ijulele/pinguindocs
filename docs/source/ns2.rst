Network Simulator 2 Installation (NS2)
======================================

.. sidebar:: Documented by :

     * **Code Name**    : NDA
     * **Date** 	: 12/17/2015
     * **Mail** 	: naufal.itt@gmail.com

Ns is a discrete event simulator targeted at networking research. Ns provides substantial support for simulation of TCP, routing, and multicast protocols over wired and wireless (local and satellite) networks.[1] 

You can download ns2 files from `<http://sourceforge.net/projects/nsnam/files/allinone/>`_.
In this documentation we use Ubuntu 10.04 32bit as operating system. You can download iso file from `<http://old-releases.ubuntu.com/releases/lucid/ubuntu-10.04-desktop-i386.iso>`_


**1. NS 2.35**
*************

- Root access
::

	sudo su

- Re-synchronize the package index files from sources 
::

  apt-get update

- Extract the tar.gz file
::

  tar -xvf ns-allinone-2.35.tar.gz 

.. note::

    Check the directory which ns-allinone-2.35.tar.gz downloaded 

- Install packages
::

  sudo apt-get install build-essential autoconf automake libxmu-dev

.. image:: images/ns2.png


- Move to ns2 directory
::
  
  cd /home/cnc/ns-allinone-2.35 

.. image:: images/ns5.png

.. note::

    Check your own path, in this documentation we use /home/cnc/ 

- Install ns2
::

  ./install

- When the installation succed it will be like this

.. image:: images/ns3.png

- Edit bashrc
::

  nano ~/.bashrc

- Add this to bashrc
::

  # LD_LIBRARY_PATH
  OTCL_LIB=/home/cnc/ns-allinone-2.35/otcl-1.14
  NS2_LIB=/home/cnc/ns-allinone-2.35/lib
  X11_LIB=/usr/X11R6/lib
  USR_LOCAL_LIB=/usr/local/lib
  export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OTCL_LIB:$NS2_LIB:$X11_LIB:$USR_LOCAL_LIB
  # TCL_LIBRARY
  TCL_LIB=/home/cnc/ns-allinone-2.35/tcl8.5.10/library
  USR_LIB=/usr/lib
  export TCL_LIBRARY=$TCL_LIB:$USR_LIB
  # PATH
  XGRAPH=/home/cnc/ns-allinone-2.35/bin:/home/cnc/ns-allinone-2.35/tcl8.5.10/unix:/home/cnc/ns-allinone-2.35/tk8.5.10/unix
  NS=/home/cnc/ns-allinone-2.35/ns-2.35/
  NAM=/home/cnc/ns-allinone-2.35/nam-1.15/
  PATH=$PATH:$XGRAPH:$NS:$NAM

- Source
::

  source ~/.bashrc

- check ns-ver
::

  ns

  ns-ver

.. image:: images/ns6.PNG

- Download and run simple script from http://nile.wpi.edu/NS/Example/ns-simple.tcl
::

  ns ns-simple.tcl

.. image:: images/ns7.png
 






**2. NS 2.34**
*************

- Root access
::

	sudo su

- Re-synchronize the package index files from sources 
::

      apt-get update	

- Extract the tar.gz file
::

  tar -xvf ns-allinone-2.34.tar.gz 

.. note::

    Check the directory which ns-allinone-2.34.tar.gz downloaded 

- Install packages
::

  sudo apt-get install build-essential autoconf automake libxmu-dev

.. image:: images/ns2.png

- Open file in otcl-1.13/configure
::

  nano +6304 /home/cnc/ns-allinone-2.34/otcl-1.13/configure

- Replace SHLIB_LD="ld -shared" into SHLIB_LD="gcc -shared"

.. image:: images/ns8.png

- Move to ns2 directory
::
  
  cd /home/cnc/ns-allinone-2.34 

.. note::

    Check your own path, in this documentation we use /home/cnc/ 

- Install ns2
::

  ./install

- When the installation succed it will be like this

.. image:: images/ns234.png

- Edit bashrc
::

  nano ~/.bashrc

- Add this to bashrc
::

  # LD_LIBRARY_PATH
  OTCL_LIB=/home/cnc/ns-allinone-2.34/otcl-1.13
  NS2_LIB=/home/cnc/ns-allinone-2.34/lib
  X11_LIB=/usr/X11R6/lib
  USR_LOCAL_LIB=/usr/local/lib
  export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OTCL_LIB:$NS2_LIB:$X11_LIB:$USR_LOCAL_LIB
  # TCL_LIBRARY
  TCL_LIB=/home/cnc/ns-allinone-2.34/tcl8.4.18/library
  USR_LIB=/usr/lib
  export TCL_LIBRARY=$TCL_LIB:$USR_LIB
  # PATH
  XGRAPH=/home/cnc/ns-allinone-2.34/bin:/home/cnc/ns-allinone-2.34/tcl8.4.18/unix:/home/cnc/ns-allinone-2.34/tk8.4.18/unix
  NS=/home/cnc/ns-allinone-2.34/ns-2.34/
  NAM=/home/cnc/ns-allinone-2.34/nam-1.14/
  PATH=$PATH:$XGRAPH:$NS:$NAM

- Source
::

  source ~/.bashrc

- check ns-ver
::

  ns

  ns-ver

.. image:: images/ns234ver.png

- Download and run simple script from http://nile.wpi.edu/NS/Example/ns-simple.tcl
::

  ns ns-simple.tcl

.. image:: images/ns234nam.png

**3. NS 2.33**
*************

- Root access
::

	sudo su

- Re-synchronize the package index files from sources 
::

      apt-get update	

- Extract the tar.gz file
::

  tar -xvf ns-allinone-2.33.tar.gz 

.. note::

    Check the directory which ns-allinone-2.33.tar.gz downloaded 

- Install packages
::

  sudo apt-get install build-essential autoconf automake libxmu-dev

.. image:: images/ns2.png

- Open file in otcl-1.13/configure
::

  nano +5518 /home/cnc/ns-allinone-2.33/otcl-1.13/configure

- Replace SHLIB_LD="ld -shared" into SHLIB_LD="gcc -shared"

.. image:: images/ns8.png

- Patch for NAM [2]
::

  cd /home/cnc/ns-allinone-2.33/tk8.4.18

- Create a document
::

  nano tk-8.4-lastevent.patch

- Patch for NAM from https://sources.gentoo.org/cgi-bin/viewvc.cgi/gentoo-x86/dev-lang/tk/files/tk-8.4-lastevent.patch?revision=1.1. Paste and save the code below to tk-8.4-lastevent.patch that we just created
::

  Source: Jeffrey Gardner (je_fro) <jeffrey.e.gardner@comcast.net> - http://overlays.gentoo.org/dev/je_fro/browser/dev-lang/tk/files/tk-8.4-lastevent.patch
Upstream: N/A
Reason: Fix ABI incompatibility introduced by x11-proto/xproto-7.0.13 (bug #225999)
--- generic/tk.h.orig 2008-02-06 16:31:40.000000000 +0100
+++ generic/tk.h  2008-07-24 08:21:46.000000000 +0200
@@ -635,17 +635,15 @@
  *
  *---------------------------------------------------------------------------
  */
-#define VirtualEvent     (LASTEvent)
-#define ActivateNotify     (LASTEvent + 1)
-#define DeactivateNotify    (LASTEvent + 2)
-#define MouseWheelEvent     (LASTEvent + 3)
-#define TK_LASTEVENT     (LASTEvent + 4)
+#define VirtualEvent     (MappingNotify + 1)
+#define ActivateNotify     (MappingNotify + 2)
+#define DeactivateNotify    (MappingNotify + 3)
+#define MouseWheelEvent     (MappingNotify + 4)
+#define TK_LASTEVENT     (MappingNotify + 5)
 
 #define MouseWheelMask     (1L << 28)
-
 #define ActivateMask     (1L << 29)
 #define VirtualEventMask    (1L << 30)
-#define TK_LASTEVENT     (LASTEvent + 4)
 
 
 /*
  
- To apply the patch
::

  patch -p0 < ./tk-8.4-lastevent.patch

.. image:: images/nampatch.png

- Move to ns2 directory
::
  
  cd /home/cnc/ns-allinone-2.33 


.. note::

    Check your own path, in this documentation we use /home/cnc/ 

- Install ns2
::

  ./install

- When the installation succed it will be like this

.. image:: images/ns233.png

- Edit bashrc
::

  nano ~/.bashrc

- Add this to bashrc
::

  # LD_LIBRARY_PATH
  OTCL_LIB=/home/cnc/ns-allinone-2.33/otcl-1.13
  NS2_LIB=/home/cnc/ns-allinone-2.33/lib
  X11_LIB=/usr/X11R6/lib
  USR_LOCAL_LIB=/usr/local/lib
  export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OTCL_LIB:$NS2_LIB:$X11_LIB:$USR_LOCAL_LIB
  # TCL_LIBRARY
  TCL_LIB=/home/cnc/ns-allinone-2.33/tcl8.4.18/library
  USR_LIB=/usr/lib
  export TCL_LIBRARY=$TCL_LIB:$USR_LIB
  # PATH
  XGRAPH=/home/cnc/ns-allinone-2.33/bin:/home/cnc/ns-allinone-2.33/tcl8.4.18/unix:/home/cnc/ns-allinone-2.33/tk8.4.18/unix
  NS=/home/cnc/ns-allinone-2.33/ns-2.33/
  NAM=/home/cnc/ns-allinone-2.33/nam-1.13/
  PATH=$PATH:$XGRAPH:$NS:$NAM

- Source
::

  source ~/.bashrc

- check ns-ver
::

  ns

  ns-ver

.. image:: images/ns233ver.png

- Download and run simple script from http://nile.wpi.edu/NS/Example/ns-simple.tcl
::

  ns ns-simple.tcl

.. image:: images/ns233nam.png


**4. NS 2.32**
*************

- Root access
::

	sudo su

- Re-synchronize the package index files from sources 
::

      apt-get update	

**5. NS 2.31**
*************

- Root access
::

	sudo su

- Re-synchronize the package index files from sources 
::

      apt-get update	

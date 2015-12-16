FTP Server
==========

FTP or File Transfer Protocol is TCP based service. We use FTP to upload or download their files to server. By default FTP use 2 ports, which is port 20 and 21. Port 21 for "command port" and port 20 for "data port".

In this documentation we use Ubuntu 14.04 as operating system, and vsftpd as ftp server.


- Re-synchronize the package index files from sources 
::

      apt-get update
   
- Install vsftpd
::

      apt-get install vsftpd

- Add user id & password to access ftp
::

      adduser cnc
.. image:: /images/adduser.JPG

- Edit configuration file
::

      nano /etc/vsftpd.conf

::

      anonymous_enable=NO
::

      local_enable=YES
::

      write_enable=YES
::

      chroot_local_user=YES

- Changing ownership
::

	  sudo chown root:root /home/cnc

- Creating directory for ftp files
::

	  sudo mkdir /home/cnc/ftp

- Changing ownership
::

	  sudo chown cnc:cnc /home/cnc/ftp

Now you can access your ftp server by opening your web browser and type ftp:// (your ftp server ip)

.. note::

		Login using username and password that we set before
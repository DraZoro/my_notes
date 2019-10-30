============================
Firewalld managing firewalls
============================

Features
--------

* Dynamic firewall daemon 
* Support for zones
* Configure firewall rules directly
* Configuration files are in `XML` 

Configuration source
--------------------
* /usr/lib/firewalld 
* /etc/firewalld

Network Zones
-------------
The settings are stored in `/etc/firewalld`

* drop : Incoming packets dropped. 
* block : Only network connections initiated within system are possible
* public : For use in public areas.
* external
* dmz
* work
* internal
* *trusted*

Listing the default predefined services: 

.. code:: bash

  ls /usr/lib/firewalld/services
  # User created system and services
  ls /etc/firewalld/services/

Example of copying a template for the 'http' service:

.. code:: bash 

   cp /usr/lib/firewalld/services/http.xml /etc/firewalld/services/http.xml

Direct Interface
----------------
The `firewalld` is able to pass rules to **iptables, ip6tables,** and **ebtables**. 
Can be accessed via `firewalld-cmd` by appending the `--direct` switch.


Switching back to *iptables*
----------------------------
In case iptables are required on the system. 

.. code:: bash 

   # Stopping firewalld
   systemctl disable firewalld
   # Installl iptables-services
   yum install iptables-services
   # Start the services 
   systemctl start iptables 
   systemctl start ip6tables
   # Start automaticall on boot
   systemctl enable iptables
   systemctl enable ip6tables


firewall-cmd
------------
This is the command line interface tool. To access the list about supported commands. `firewall-cmd --help`.

Active zones:

.. code:: bash 

   firewall-cmd --get-active-zones 

Full settings of active zones

.. code:: bash 

   # public can be changed with other zone 
   firewall-cmd --zone=public --list-all

Currently active network zones 

.. code:: bash 

   firewall-cmd --get-service
   # Checking services which will start after reload
   firewall-cmd --get-service --permanent

Droping all packets *Panic Mode*

.. code:: bash 

   # Turn on the panic mode
   firewall-cmd --panic-on
   # Turn off panic mode
   firewall-cmd --panic-off
   # Query the panic 
   firewall-cmd --query-panic


Reloading with affecting state

.. code:: bash 

   firewall-cmd --reload

Adding an interface to a specific zone 

.. code:: bash 

   # public and docker0 can be replaced with other values
   # permanent is optional as well
   firewall-cmd --permanent --zone=public --add-interface=docker0

Adding interface by modifying the interface configuration file.

.. code:: bash 

   # Example interface is ifcfg-enp0s25
   vim /etc/sysconfig/network-scripts/ifcfg-enp0s25
   # Then append the zone for example internal
   ZONE=internal

Default zone can be changed by modifying `/etc/firewalld/firewalld.conf`.
Then changing the `DefaultZone` parameter.

Working with ports

.. code:: bash 

   # Listing 
   firewall-cmd --zone=public --list-ports
   # Adding a port to a zone for temporary adding --permanent 
   # can be left out.
   firewall-cmd --permanent --zone=public --add-port=8069/tcp

Adding services 

.. code:: bash 

   # List the services 
   ls /usr/lib/firewalld/services
   # Adding a service 
   firewall-cmd --permanent --zone=work --add-service=mysql
   # Removing 
   firewall-cmd --zone=work --remove-service=mysql 
   firewall-cmd --reload
   
Ip Masquerading 

.. code:: bash 

   # Inspect 
   firewall-cmd --zone=external --query-masquerade 
   # Enable Ip masquerading 
   firewall-cmd --permanent --zone=external --add-masquerade
   # Disable Masquerading
   firewall-cmd --permanent --zone=external --remove-masquerade


More notes to explore
---------------------
* firewall(1)
* firewall-cmd(1)
* firewalld.service(5)


Reference
---------
1. `RedHat`_


.. Some links 

.. _RedHat: https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/Security_Guide/sec-Using_Firewalls.html

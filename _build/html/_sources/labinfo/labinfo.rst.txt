Lab Topology & Tools
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. WARNING:: All work for this lab will be performed exclusively from the 
   Jumphost. No installation or interaction with your local system is
   required.

All pre-built environments implement the Lab Topology shown below.  Please
review the topology first, then find the section matching the lab environment
you are using for connection instructions.

.. _lab-topology:

Lab Topology
------------

The network topology implemented for this lab is very simple. Since the
focus of the lab is application security  rather than Data Plane
traffic flow we can keep the data plane fairly simple. The following
components have been included in your lab environment:

-  1 x F5 BIG-IP VE (v13.1.0.5)
-  1 x Linux Jumpbox
-  1 x Vulnerable Web App (WebGoat)


The following table lists VLANS, IP Addresses and Credentials for all
components:

.. list-table::
   :widths: 15 30 30 30
   :header-rows: 1
   :stub-columns: 1


   * - **Component**
     - **Management IP**
     - **VLAN/IP Address(es)**
     - **Credentials**
   * - Linux Jumphost
     - 10.1.1.20
     - **Internal:** 10.1.10.20

       **External:** 10.1.20.20
     - ``f5student/f5DEMOs4u!``
   * - BIG-IP A
     - 10.1.1.245
     - **Internal:** 10.1.20.245

       **External:** 10.1.10.24

       **External (VIPs):** 10.1.10.145

     - ``admin/f5DEMOS4u!``

       ``root/f5DEMOs4u!``
   * - Linux Server
     - 10.1.1.252
     - **Internal:** 10.1.20.252
     - ``f5student/f5DEMOs4u!``
     
       ``root/f5DEMOs4u!``



.. toctree::
   :maxdepth: 1
   :glob:

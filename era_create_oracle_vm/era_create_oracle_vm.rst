.. _era_create_oracle_vm:

--------------------------
Era: Create Oracle VM
--------------------------

Overview
++++++++

.. note::

  Estimated time to complete: **30 MINUTES**

This lab will deploy and configure a Oracle Server to be managed by Era.


Create The Database Storage Container
+++++++++++++++++++++++++++++++++++++

Before creating a VM, a container will need to be created that will host the Oracle Server disks. Inline compression should be enabled on this container. Both deduplication and erasure coding should be disabled on this container.

.. note::

  An existing container can be used, if the capacity optimization options are configured according to Nutanix SQL Server best practices.

Let's use Prism Element to perform the container setup.

#. In **Prism Element> Storage**, click **Storage**, click **Table**, then click **+ Storage Container**.

#. Use the following specifications:

   - **Name** - *Initials*-Database
   - Select **Advanced Settings**
   - Select **Compression**
   - **Delay (In Minutes)** - 0
   - Select **Erasure Coding**

#. Click **Save**.

   .. figure:: images/storage_01.png

Deploy Oracle Server VM
++++++++++++++++++++++

Now we will use Prism Central to deploy the Oracle Server VM.

#. In **Prism Central**, select :fa:`bars` **> Virtual Infrastructure > VMs**.

#. Click **Create VM**.

#. Fill out the following fields:

   - **Name** - *Initials*-Oracle-Base
   - **Description** - (Optional) Description for your VM.
   - **vCPU(s)** - 2
   - **Number of Cores per vCPU** - 1
   - **Memory** - 8 GiB

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - Oracle19c_bootdisk.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - Oracle19c_disk1.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - Oracle19c_disk2.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - Oracle19c_disk3.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - Oracle19c_disk4.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - Oracle19c_disk5.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type**  - DISK
       - **Operation** - Clone from Image Service
       - **Image** - Oracle19c_disk6.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type**  - DISK
       - **Operation** - Clone from Image Service
       - **Image** - Oracle19c_disk7.qcow2
       - Select **Add**
   - Select **+ Add New Disk**
       - **Type**  - DISK
       - **Operation** - Clone from Image Service
       - **Image** - Oracle19c_disk8.qcow2
       - Select **Add**
   - Select **+ Add New Disk**
       - **Type**  - DISK
       - **Operation** - Clone from Image Service
       - **Image** - Oracle19c_disk9.qcow2
       - Select **Add**

   - Select **Add New NIC**
       - **VLAN Name** - Primary
       - Select **Add**

#. Click **Save** to create the VM.

#. Select your Oracle Server VM and click **Power On**.

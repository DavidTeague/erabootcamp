
.. _era_create_oracle_vm:

--------------------------
Era: Create Oracle VM
--------------------------

Overview
++++++++

.. note::

  Estimated time to complete: **15 MINUTES**

This lab will deploy and configure a Oracle Server to be managed by Era.

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
       - **Image** - 19c_bootdisk.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - 19c_disk1.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - 19c_disk2.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - 19c_disk3.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - 19c_disk4.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type** - DISK
       - **Operation** - Clone from Image Service
       - **Image** - 19c_disk5.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type**  - DISK
       - **Operation** - Clone from Image Service
       - **Image** - 19c_disk6.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type**  - DISK
       - **Operation** - Clone from Image Service
       - **Image** - 19c_disk7.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type**  - DISK
       - **Operation** - Clone from Image Service
       - **Image** - 19c_disk8.qcow2
       - Select **Add**

   - Select **+ Add New Disk**
       - **Type**  - DISK
       - **Operation** - Clone from Image Service
       - **Image** - 19c_disk9.qcow2
       - Select **Add**

   - Select **Add New NIC**
       - **VLAN Name** - Primary
       - Select **Add**

.. note::
   Disk number will match scsi id's.

#. Click **Save** to create the VM.

#. Select your Oracle Server VM and click **Power On**.

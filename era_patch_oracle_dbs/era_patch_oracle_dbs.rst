
.. _era_patch_oracce_dbs:

------------------------------
Era: Patch Oracle Databases
------------------------------

Overview
++++++++

.. note::

  Estimated time to complete: **30 MINUTES**

In this lab we will create a software profile for the oracle database clone the database and patch. Then create a new software pofile and with the clone and patch the source.

Create software Profile of Oracle Databases with Era

Clone server for patching
+++++++++++++++++++++++++++++++++++++++++++

#. Select the **Era > Time Machines** drop down menu select initials_oracle_prod_TM click **Actions, Clone Database**;

#. On the **Clone Database** screen Take Defaults and click **Next**;

   .. figure:: images/patchdb_02.png

#. On the second **Clone Database** screen, input the following and click **Next**:

   -  **Name** - initials_oracle_patch
   -  **Compute Profile** - CUSTOM_EXTRA_SMALL
   -  **Network Profile** - Orcle_Prod
   -  **Provide SSH Public Key Through** - Chose File and Use Provided SSH Key
   -  **Database Server Time Zone** - Choose Local Time Zone

   .. figure::  images/patchdb_03.png

#. On the third **Clone Database** screen, input the following and click **Clone**:

   -  **Name** - initials_oracle_patch
   -  **SID** - initialspat
   -  **Description ** - (Optional) Description
   -  **SYS and SYSTEM Password** - nutanix/4u
   -  **Database Parameter Profile** - Oracle_Extra_Small

   .. figure::  images/patchdb_04.png

#. Monitor the registration operation by clicking **initials_oracle_patch**.

   .. note::

     This will take about 15 mins.

Patch Cloned Server VIA SSH
...........................
Apply any Oracle Patches to Clone Server

#. Select the **Era > Databases** and click **Cloned DB Servers** Under Oracle

#. Click on **initials_oracle_patch**

#. Click **See Description** under Connect via SSH

   .. figure:: images/patchdb_06.png

#. Use the ip address listed to connect to vm from your tools vm with putty
    - **username** - oracle
    - **password** - Nutanix/4u

#. Once logged into the vm type **bash** and press enter

#. run the command below
   - sudo /root/Downloads/applypsu.sh
   - press enter to start patch
   - You can ignore any errors about directories not existing.
# type **exit** three times to exit

Update Software Profile
.......................

Update the software profile of the patched server to use for patching existing server

#. Select the **Era > Getting Started** drop down menu and click **Profiles**.

#. Select **Software** in the **Profiles** pane on the left-hand side of the screen.

#. Chose **initials_oracle_base** and click **View Versions**

#. Chose **initials_oracle_base(1.0)** and click **+ Create**

#. On the **Crate Software Profile** chose the server you cloned input the following and click **create**:
    -  **Name** - initials_oracle_patched
    -  **Description** - (Optional) Description

.. figure:: images/patchdb_05.png

#. Select initials_oracle_patched to check the progress

#. Once creation of profile is complete, go back to **Software Profiles**

#. Chose **initials_oracle_prod** and click **View Versions**

#. Chose **initials_oracle_patched** and click **Update**

#. Select **Published** and click **Next** until you can click **Update**

.. figure:: images/patchdb_07.png


Patch Prod Sever
................

Now that we have a published patched software profile we can patch your original "Prod" Servers

#. Select the **Era >** drop down menu and click **Database Servers**.

#. Under Oracle Click on **Source DB Servers**

#. Select on  **initials_oracle_prod**

#. Scroll Down to Profiles, you should see update available

.. figure:: images/patchdb_08.png

#. Select **Update**

#. On Patch 1 Database(s) on server Screen make sure Now is selected and click patch Database

.. figure:: images/patchdb_09.png

#. Click on operations to see patch progress

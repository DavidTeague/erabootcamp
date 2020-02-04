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



Before Era can be used patch we need a base software profile
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

Create Software Profile for Oracle database
+++++++++++++++++++++++++++++++++++++++++++

Once the **xyz_ORCL19C** database has been registered with Era, the Time Machine for the database will start creating snapshots and collecting transaction log backups.

#. Open https://*ERA-VM-IP:8443*/ in a new browser tab.

#. Select the **Era > Getting Started** drop down menu and click **Profiles**.

#. Select **Software** in the **Profiles** pane on the left-hand side of the screen.

#. Click **+ Create**.

#. In the **Create Software Profile** Dialog box, select **Oracle** and **Single Instance** then click **Next**.

#. On the **Create Software Profile** screen, select **xyz-Oracle-Prod**  input the following and click **create**:
    -  **Name** - xyz_oracle_base
    -  **Description** - (Optional) Description

   .. figure:: images/patchdb_01.png

#. Click xyz_oracle_base to check the progress

# One Software Profile is Created #. Select the **Era > Operations** drop down menu and click **Profiles**.

#. Choose on **xyz_ORCL19C_base** and click **View Versions**

#. Chose Update

#. On the Update Software profile Version choose **Published** and click **Next**;

   .. figure:: images/patchdb_04.png
#. Fill out any notes you would like and click **next**

#. Click **Update** on next screen


Clone server for patching
+++++++++++++++++++++++++++++++++++++++++++

#. Select the **Era > Time Machines ** drop down menu select xyz_OrCL91c_TM click **Actions, Clone Databse **;

#. On the **Clone Database** screen Take Defaults and click **Next**;
   .. figure:: images/patchdb_02.png

#. On the second **Clone Database** screen, input the following and click **Next**:

   -  **Name** - Take Default
   -  **Compute Profile** - Small
   -  **Network Profile** - Prod - Oracle
   -  **Provide SSH Public Key Through** - Chose File and Use Provided SSH Key
   -  **Database Server Time Zone** - Choose Local Time Zone

   .. figure::  images/patchdb_03.png

#. On the third **Clone Database** screen, input the following and click **Clone**:

   -  **Name** - Take Default
   -  **Description ** - (Optional) Description
   -  **SYS and SYSTEM Password** - nutanix/4u
   -  **Database Parameter Profile** - Small Oracle

   .. figure::  images/patchdb_03.png

#. Monitor the registration operation by clicking **ORCL19C_2020_(current date)**.

   .. note::

     Wait for the operation to successfully complete before attempting to register another SQL Server database.

Patch Server VIA SSH
....................
Apply any Oracle and OS patches via the cli

need this instructions

Update Software Profile
.......................

Update the software profile of the patched server to use for patching existing server

#. Select the **Era > Getting Started** drop down menu and click **Profiles**.

#. Select **Software** in the **Profiles** pane on the left-hand side of the screen.

#. Chose **xyz_ORCL19c_base** and click **View Versions**

#. Chose **xyz_ORCL19c_base(1.0)** and click **+ Create**

#. On the **Crate Software Profile** chose the server you cloned input the following and click **create**:
    -  **Name** - xyz_ORCL19C_patched
    -  **Description** - (Optional) Description

   .. figure:: images/patchdb_05.png

#. Click xyz_ORCL19C to check the progress

Patch Prod Sever
................

First we must update the orginal software profile with the unpatch Prod Server

#. Select the **Era > Getting Started** drop down menu and click **Profiles**.

#. Select **Software** in the **Profiles** pane on the left-hand side of the screen.

#. Chose  **xyz_ORCL19-Prod** and click **View Versions**

#. Chose **xyz_Oracle** and click **+ Create**

#. On the **Crate Software Profile** chose the server you cloned input the following and click **create**:
    -  **Name** - xyz_ORCL19C_base
    -  **Description** - (Optional) Description

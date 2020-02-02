  .. _era_register_oralce_dbs:

------------------------------
Era: Register Oracle Databases
------------------------------

Overview
++++++++

.. note::

  Estimated time to complete: **30 MINUTES**

In this lab we will import existing MSSQL Databases into Era for management.

Register Oracle Databases with Era
+++++++++++++++++++++++++++++++++++++

Before Era can be used with existing databases, they must be registered in Era.

Register The WideWorldImporters Database
........................................

Once the **ORCL19C** database has been registered with Era, the Time Machine for the database will start creating snapshots and collecting transaction log backups.

#. Open \https://*ERA-VM-IP:8443*/ in a new browser tab.

#. Select the **Era > Getting Started** drop down menu and click **Databases**.

#. Select **Sources** in the **Databases** pane on the left-hand side of the screen.

#. Click **+ Register**.

#. In the **Register a Source Database** Dialoge box, select **Oracle**, and click **Next**.

#. On the **Database Server** screen, input the following and click **Next**:

   -  **Database is on a Server that is:** - Not Registered
   -  **IP Address or Name of VM** - Database IP
   -  **Era Drive user** - oracle
   -  **Oracle Databse home** - /u02/app/oracle/product/19.0.0/dbhome_1
   -  **Password** - Nutanix/4u


   .. figure:: images/registerdb_01.png

#. On the **Database** screen, input the following and click **Next**:

   -  **Database Name in Era** - xyz_ORCL19C
   -  **Description** - (Optional) Description
   -  **SID** -  orcl18c

   .. figure:: images/registerdb_02.png

#. On the **Time Machine** screen, input the following and click **Register**:

   -  **Name** - xyz_ORCL19C
   -  **Description** - (Optional) Description
   -  **SLA** - GOLD
   -  **Schedule** - Take Defaults

   .. figure:: images/registerdb_03.png

#. Monitor the registration operation by clicking **xyz_ORCL19C**.

   .. note::

     Wait for the operation to successfully complete before attempting to register another SQL Server database.

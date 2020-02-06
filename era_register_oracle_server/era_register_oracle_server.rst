
.. _era_register_oracle_server:
=======

------------------------------
Era: Register Oracle Server
------------------------------

Overview
++++++++

.. note::

  Estimated time to complete: **15 MINUTES**

In this lab we will Clone existing Oracle Server into Era as a base for deployments

Register Oracle Server with Era
+++++++++++++++++++++++++++++++

Register the source Oracle Server Database
..........................................

Before Era can be used to patch Oracle an Oracle server must be registered.

#. Open \https://*ERA-VM-IP:8443*/ in a new browser tab.

#. Select the **Era > Getting Started** drop down menu and click **Database Servers**.

#. Select **List** in the **Database Server** pane on the left-hand side of the screen.

#. Click **+ Register**.

#. In the First **Register Database Server** Dialog box, select **Oracle**, and click **Next**.

#. On the Second **Register Database Server** screen, input the following and click **Register**:

   -  **IP Address or Name of VM** - initials_oracle_base
   -  **Database Version** - 19.0.0.0
   -  **Era Drive user** - oracle
   -  **Oracle Database home** - /u02/app/oracle/product/19.0.0/dbhome_1
   -  **Grid Infrastructure Home** /u01/app/19.0.0/grid
   -  **Password** - Nutanix/4u


   .. figure:: images/registerdb_01.png

#. Monitor the registration operation by clicking **ip_address_of_server**.

   .. note::

   Wait for the registration operation to successfully complete before moving on

Create Software Profile
+++++++++++++++++++++++

Once the **xyz_oracle_base** database has been registered with Era, we need to create a software profile to deploy the enviroment

#. Open https://*ERA-VM-IP:8443*/ in a new browser tab.

#. Select the **Era > Getting Started** drop down menu and click **Profiles**.

#. Select **Software** in the **Profiles** pane on the left-hand side of the screen.

#. Click **+ Create**.

#. In the **Create Software Profile** Dialog box, select **Oracle** and **Single Instance** then click **Next**.

#. On the **Create Software Profile** screen, select **initials-Oracle-Prod**  input the following and click **create**:
    -  **Name** - initials_oracle_base
    -  **Description** - (Optional) Description

   .. figure:: images/register_02.png

#. Monitor the operation by clicking **initials_oracle_base**

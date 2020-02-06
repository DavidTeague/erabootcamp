
.. _era_create_oracle_server:
=======

------------------------------
Era: Create Oracle Server
------------------------------

Overview
++++++++

.. note::

  Estimated time to complete: **45 MINUTES**

In this lab we will create an Oracle Server in Era and create a software profile

Create Oracle Server with Era
+++++++++++++++++++++++++++++++

Create a server in ERA as "Production" server

#. Open \https://*ERA-VM-IP:8443*/ in a new browser tab.

#. Select the **Era > Getting Started** drop down menu and click **Databases**.

#. Select **Sources** in the **Databases** pane on the left-hand side of the screen.

#. Click **+ Provision** then **Single Node Database**

#. In the First **Provision a Database** Dialog box, select **Oracle**, and click **Next**.

#. On the Second **Provision a Databaser** screen, input the following and click **Next**:

   -  **Database Server Name** - initials_oracle_prod
   -  **Description** - (Optional) Description
   -  **Software Profile** - initials_oracle_base
   -  **Compute Profile** - CUSTOME_EXTRA_SMALL
   -  **Network Profile** - Orcle_Prod
   -  **SSH Public Key for Node Access** - use provided ssh public key

     .. figure:: images/create_01.png

#. On the Third **Provision Database** screen, input the following and click **Next**:

   -  **Database Name** - initials_oracle_prod
   -  **SID** - initialsprd
   -  **Era Drive user** - oracle
   -  **SYS and SYSTEM Password** - nutanix/4u
   -  **Database Parameter Profile** - Oracle_Extra_Small



   .. figure:: images/create_02.png

#. On the Third **Provision Database** screen, input the following and click **Provision**:

   -  **Name** - initials_oracle_prod_TM
   -  **SLA** - DEFAULT_OOB_GOLD_SLA

   .. figure:: images/create_03.png

#. Monitor the registration operation by clicking **initials_oracle_prod**.

.. note::
   Wait for the provision  operation to successfully complete before moving on
   This will take 30+ mins.

Create Software Profile
+++++++++++++++++++++++


Once the **xyz_ORCL19C** database has been registered with Era, the Time Machine for the database will start creating snapshots and collecting transaction log backups.

#. Open https://*ERA-VM-IP:8443*/ in a new browser tab.

#. Select the **Era > Getting Started** drop down menu and click **Profiles**.

#. Select **Software** in the **Profiles** pane on the left-hand side of the screen.

#. Click **+ Create**.

#. In the **Create Software Profile** Dialog box, select **Oracle** and **Single Instance** then click **Next**.

#. On the **Create Software Profile** screen, select **xyz-Oracle-prod**  input the following and click **create**:
    -  **Name** - initials_oracle_prod
    -  **Description** - (Optional) Description

   .. figure:: images/create_04.png

#.  Monitor the creation operation by clicking **initials_oracle_prod**.

.. note::
   Once Software Profile completion is complete move on.

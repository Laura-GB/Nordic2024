# Lab 4 - Connect Dataverse to the Lakehouse and Shortcuts to Dataverse

## Overview

In this lab we will link Dataverse into Fabric using Shortcuts. A short cut is a pointer to data stored elsewhere, within or without OneLake. 

## Topics

* [Create the Connection](#create-the-connection)
* [Azure Synapse Link](#azure-synapse-link)
* [Create a New Shortcut](#create-a-new-shortcut)

## Create the Connection

The initial link is created from Datavesre within PowerApps. It can take a few hours for the links to be built. Currently the process is to link all the tables to a workspace. Once that is done another lakehouse can create links to individual dataverse tables.

In the tables page of your environment, click on Analyze and then click on Link to Microsoft Fabric. In the Validate Configuration pane that appears the Environment domain is already filled in, you just need to click Sign in. When the Save Connection appears, click it and then Next to move onto the next stage.

![Analyze menu and the Validate Configuration pane](<Images/Lab 04/2024-09-04_11-03-14.png>)

The next step is to choose or create a workspace. It will only show you workspaces with a capacity in the same geography. Hence for this workshop we are using America as at time of writing Europe was having issues. 

From the workspace drop down select Create new workspace and then type in a name for the workspace. Click Next to move to the Review and Create stage. Click Create to start the process. "This may take a few minutes" should read hours.

![Choose Workspace and Review & Create stages](<Images/Lab 04/2024-09-04_11-21-54.png>)

## Azure Synapse Link

The pane will vanish after a few minutes. You can keep track of progress in Azure Synapse Link. If it is not on your left hand side menu click on More... and the Discover All. It can be found under Data Management. 

![Azure Synapse link window with link to show Microsoft OneLake and then list of tables. Then LakeHouse explorer view from from clicking on View in Microsoft Fabric](<Images/Lab 04/2024-09-04_11-44-15.png>)

Now patiently wait.

## Managing Tables

If a new table is added to an environment, or a new column is added to a table the tables will need to be refreshed for the changes to be available in Microsoft Fabric.

## Create a New Shortcut

Once the links to all the 200+ tables from an environment have been created into one workspace then you add individual shortcuts from the environment into another workspace.

Inside the lakehouse, click on Get data and select New Shortcut. From the options in the New Shortcut dialog select Dataverse. For the connection settings paste in the domain path, e.g. orgd466b741.crm.dynamics.com. This should load connection credentials. Click Next and the list of tables should be displayed. Tick the tables you want and then click next. Finally you get a list of the selected Shortcuts. Click Create to add them to the Lakehouse


![Walkthrough from selecting New Shortcut to selecting the environment dmain and then the tables and click Create to list the shortcut in the Lakehouse](<Images/Lab 04/2024-09-04_15-29-15.png>)

These shortcuts can now be treated as tables. Most of the hardwork is done on the Dataverse side so should not impact Fabric capacity usage.

### References

* [Platform Guardian - Creating Dataverse Connector in Fabric][PGCreateConnector]
* [Microsoft Learn - Link Dataverse Environments to Microsoft Fabric][MSCreateConnector]

[PGCreateConnector]: https://platformguardian.blog/2023/11/05/creating-the-dataverse-connector-in-fabric/
[MSCreateConnector]: https://learn.microsoft.com/en-us/power-apps/maker/data-platform/azure-synapse-link-view-in-fabric?wt.mc_id=DX-MVP-5003563
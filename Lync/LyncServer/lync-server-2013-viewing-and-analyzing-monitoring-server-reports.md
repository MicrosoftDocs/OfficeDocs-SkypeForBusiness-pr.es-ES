---
title: 'Lync Server 2013: Viewing and analyzing monitoring server reports'
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn720332(v=OCS.15)
ms:contentKeyID: 62222463
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Viewing and analyzing monitoring server reports in Lync Server 2013

 

_**Última modificación del tema:** 2014-05-19_

Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users. Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.

A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:

  - QoE Summary/Trend Reports

  - QoE Performance Reports

## View reports from the monitoring server

1.  From a web browser, locate your servers hosting the SQL reporting services.

2.  View the required reports from the browser screen.

3.  (Optional) Export a report by selecting the export option and the required output format.

## Configure call detail recording (CDR)

1.  From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.

2.  Open a browser window, and then enter the Admin URL to open the Panel de control de Lync Server.

3.  In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.

4.  On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.

5.  To turn on purging, select **Enable Purging for Monitoring Servers**.

6.  In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.

7.  In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.

8.  Click **Commit**.

9.  

## Configure QoE

1.  Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see Delegate Setup Permissions.

2.  Open a browser window, and then enter the Admin URL to open the Panel de control de Lync Server.

3.  In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.

4.  On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.

5.  To turn on purging, select **Enable Purging for Monitoring Servers**.

6.  In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.

7.  Click Commit.

## Change the archiving policy

1.  From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.

2.  Open a browser window, and then enter the Admin URL to open the Panel de control de Lync Server.

3.  In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.

4.  Click **Global** in the list of policies, click **Edit**, and then click **Show details**.

5.  In **Edit Archiving Policy - Global**, do the following:

6.  To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.

7.  To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.

8.  Click **Commit**.

## Apply an archiving policy to a user

1.  From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.

2.  Open a browser window, and then enter the Admin URL to open the Panel de control de Lync Server.

3.  In the left navigation bar, click **Users**, and then search on the user account that you want to configure.

4.  In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.

5.  In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.

6.  Click **Commit**.

## Vea también

#### Conceptos

[Usar informes de supervisión en Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md)  
[Informe de comparación de calidad de los medios en Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)


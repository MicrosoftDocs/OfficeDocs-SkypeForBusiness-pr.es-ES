---
title: Configure Lync Server 2013 Scenarios
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945596(v=OCS.15)
ms:contentKeyID: 52061989
ms.date: 06/25/2014
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configure Lync Server 2013 Scenarios

 

_**Última modificación del tema:** 2013-02-24_

To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed. If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases. With the Lync Server 2013 Stress and Performance Tool, we have provided example Shell de administración de Lync Server scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013. This topic describes the Windows PowerShell examples provided. Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general. For details about working with Windows PowerShell in Lync Server 2013, see the Shell de administración de Lync Server documentation at <http://technet.microsoft.com/en-us/library/gg398474.aspx>.

## About Running Lync Server Management Shell Scripts

We have provided example Shell de administración de Lync Server scripts that may be used in preparation for running load simulation. Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production. All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology. At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups. However, you have the option to not simulate this load.

> [!CAUTION]  
> Take care in reviewing and understanding the examples provided. Scripts will overwrite any existing settings in the topology.


> [!NOTE]
> For details about using Windows PowerShell and the Shell de administración de Lync Server, see the Lync Server 2013 Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/?linkid=203150">http://go.microsoft.com/fwlink/?LinkId=203150</A>.



## Stress and Performance Tool Client Version Monikers

You may need to configure the Client Version Check policy if you have changed the settings from the default values. For details, see “Client Version Check” at <http://technet.microsoft.com/library/gg39882.aspx>. The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:

  - LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)

  - OCPHONE/.0.522

These are for the Mobility (UCWA) client in LyncPerfTool:

  - Ucwa Perf Tool/Web Conference

  - Ucwa Perf Tool/Mobile


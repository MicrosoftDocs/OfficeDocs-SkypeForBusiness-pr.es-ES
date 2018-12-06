---
title: Introduction
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945588(v=OCS.15)
ms:contentKeyID: 52061987
ms.date: 06/25/2014
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Introduction

 

_**Última modificación del tema:** 2013-02-24_

The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:

<p></p>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Instant messaging (IM) and presence</p></td>
<td><p>Audio conferencing</p></td>
</tr>
<tr class="even">
<td><p>Application sharing</p></td>
<td><p>Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</p></td>
</tr>
<tr class="odd">
<td><p>Web Access Client conferencing</p></td>
<td><p>Microsoft Lync 2013 Attendant</p></td>
</tr>
<tr class="even">
<td><p>Response Groups</p></td>
<td><p>Distribution list expansion</p></td>
</tr>
<tr class="odd">
<td><p>Address book download and address book query</p></td>
<td><p>Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</p></td>
</tr>
<tr class="even">
<td><p>MultiView</p></td>
<td><p>Viewing multiple streams from a conference</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.

The tool also does not simulate user load for the following clients:

  - Office Live Meeting 2007

  - Lync 2013 Chat persistente

As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:

  - Lync 2013 Chat persistente

  - Exchange integration scenarios

## Applications and Files Included with the Lync Server 2013 Stress and Performance Tool

The following applications are included in the Lync Server 2013 Stress and Performance Tool:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tool</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool.exe</p></td>
<td><p>The Lync Server 2013 User Provisioning tool. This tool is used to create users and contacts.</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator.exe</p></td>
<td><p>The Lync Server 2013 Load Configuration Tool. This tool is used to configure the characteristics of the user load to simulate.</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool.exe</p></td>
<td><p>The Lync Server 2013 Stress and Performance Tool. LyncPerfTool is the tool that simulates the user load.</p></td>
</tr>
<tr class="even">
<td><p>Default.tmx</p></td>
<td><p>Default.tmx is required to use the Lync Server 2013 Logging Tool.</p></td>
</tr>
<tr class="odd">
<td><p>Example provisioning scripts</p></td>
<td><p>These examples are used to configure the topology for running load tests, based on specific scenarios</p></td>
</tr>
</tbody>
</table>


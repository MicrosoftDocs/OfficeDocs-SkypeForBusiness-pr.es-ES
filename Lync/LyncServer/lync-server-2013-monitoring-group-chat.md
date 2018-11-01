---
title: 'Lync Server 2013: Monitoring group chat'
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn720924(v=OCS.15)
ms:contentKeyID: 62246715
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Monitoring group chat in Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.

Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.

### Test environment and user model

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</p></td>
</tr>
<tr class="even">
<td><p>Two Lync Server 2013 Front Ends in Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60,000 concurrent users across three Group Chat Servers.</p></td>
</tr>
<tr class="even">
<td><p>25,000 channels hosted by Group Chat Pool.</p></td>
</tr>
<tr class="odd">
<td><p>Channel Size:</p>
<ul>
<li><p>Small Channel Size: 30</p></li>
<li><p>Medium Channel Size: 150</p></li>
<li><p>Large Channel Size: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Channel Count:</p>
<ul>
<li><p>Number small channels: 24,000</p></li>
<li><p>Number medium channels 800</p></li>
<li><p>Number large channels 24</p></li>
<li><p>Total Channels 24,824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Invite channels:</p>
<ul>
<li><p>Half the channels were invite channels</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Number of channels a user joins:</p>
<ul>
<li><p>Small: 12</p></li>
<li><p>Medium: 2</p></li>
<li><p>Large: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Join rate:</p>
<ul>
<li><p>10 total/second, 3.33/second per server</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Logout rate:</p>
<ul>
<li><p>10 total/second, 3.33/second per server</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Chat rate:</p>
<ul>
<li><p>20 total/second, 6.66/second per server</p></li>
</ul></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]  
> The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.



### Performance counter to be monitored

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Performance Counter</th>
<th>Thresholds</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Process(ChannelService)-&gt;%Processor Time</p></td>
<td><p>Min: 0</p></td>
</tr>
</tbody>
</table>


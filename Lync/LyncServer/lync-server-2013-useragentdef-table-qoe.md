---
title: 'Lync Server 2013: tabla UserAgentDef (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 146c22b77ac6d2681c1844feade86242e1fcd72f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a>Tabla UserAgentDef (QoE) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-25_

La tabla UserAgentDef asigna los identificadores de agente de usuario a los nombres descriptivos del agente. Los agentes de usuario son clientes de software que se usan para conectarse a Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UAType</th>
<th>UAName</th>
<th>UACategory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>MediationServer</p></td>
<td><p>MediationServer</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>MCU de audio y vídeo</p></td>
<td><p>MCU de audio y vídeo</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>OC</p></td>
<td><p>OC</p></td>
</tr>
<tr class="even">
<td><p>4,8</p></td>
<td><p>OCPhone</p></td>
<td><p>OCPhone</p></td>
</tr>
<tr class="odd">
<td><p>apartado</p></td>
<td><p>LMC</p></td>
<td><p>LMC</p></td>
</tr>
<tr class="even">
<td><p>32</p></td>
<td><p>DVT</p></td>
<td><p>DVT</p></td>
</tr>
<tr class="odd">
<td><p>64</p></td>
<td><p>MM</p></td>
<td><p>MM</p></td>
</tr>
<tr class="even">
<td><p>64</p></td>
<td><p>MC</p></td>
<td><p>MM</p></td>
</tr>
<tr class="odd">
<td><p>128</p></td>
<td><p>Operador</p></td>
<td><p>Operador</p></td>
</tr>
<tr class="even">
<td><p>256</p></td>
<td><p>Conferencing_Announcement_Service_1.0</p></td>
<td><p>ENTIDAD</p></td>
</tr>
<tr class="odd">
<td><p>512</p></td>
<td><p>Conferencing_Attendant_1.0</p></td>
<td><p>CAA</p></td>
</tr>
<tr class="even">
<td><p>512</p></td>
<td><p>Conference_Auto_Attendant_1.0</p></td>
<td><p>CAA</p></td>
</tr>
<tr class="odd">
<td><p>1024</p></td>
<td><p>Response_Group_Service</p></td>
<td><p>RGS</p></td>
</tr>
<tr class="even">
<td><p>1032</p></td>
<td><p>Call_Park_Service_1.0</p></td>
<td><p>CP</p></td>
</tr>
<tr class="odd">
<td><p>1040</p></td>
<td><p>Response_Group_Service Announcement_Service</p></td>
<td><p>CUYA</p></td>
</tr>
<tr class="even">
<td><p>2048</p></td>
<td><p>Microsoft. RTC. Applications. CCS</p></td>
<td><p>CCS</p></td>
</tr>
<tr class="odd">
<td><p>16386</p></td>
<td><p>Notifica</p></td>
<td><p>Notifica</p></td>
</tr>
<tr class="even">
<td><p>16387</p></td>
<td><p>CWA</p></td>
<td><p>CWA</p></td>
</tr>
<tr class="odd">
<td><p>16388</p></td>
<td><p>InboundRouting</p></td>
<td><p>InboundRouting</p></td>
</tr>
<tr class="even">
<td><p>16389</p></td>
<td><p>ComoSvc</p></td>
<td><p>ComoSvc</p></td>
</tr>
<tr class="odd">
<td><p>16393</p></td>
<td><p>MSExchangeUM</p></td>
<td><p>ExUM</p></td>
</tr>
<tr class="even">
<td><p>16395</p></td>
<td><p>ArchivingAgent</p></td>
<td><p>ARCHAGENT</p></td>
</tr>
<tr class="odd">
<td><p>16396</p></td>
<td><p>San</p></td>
<td><p>San</p></td>
</tr>
<tr class="even">
<td><p>16397</p></td>
<td><p>applicationsharing</p></td>
<td><p>ASMCU</p></td>
</tr>
<tr class="odd">
<td><p>16398</p></td>
<td><p>WPLync</p></td>
<td><p>WPLync</p></td>
</tr>
<tr class="even">
<td><p>16399</p></td>
<td><p>iPhoneLync</p></td>
<td><p>iPhoneLync</p></td>
</tr>
<tr class="odd">
<td><p>16400</p></td>
<td><p>AndroidLync</p></td>
<td><p>AndroidLync</p></td>
</tr>
<tr class="even">
<td><p>16401</p></td>
<td><p>iPadLync</p></td>
<td><p>iPadLync</p></td>
</tr>
<tr class="odd">
<td><p>16402</p></td>
<td><p>NokiaLync</p></td>
<td><p>NokiaLync</p></td>
</tr>
<tr class="even">
<td><p>16403</p></td>
<td><p>LyncImm</p></td>
<td><p>LyncImm</p></td>
</tr>
<tr class="odd">
<td><p>16404</p></td>
<td><p>INFORMÁTICO</p></td>
<td><p>INFORMÁTICO</p></td>
</tr>
<tr class="even">
<td><p>16405</p></td>
<td><p>LWA</p></td>
<td><p>LWA</p></td>
</tr>
<tr class="odd">
<td><p>16406</p></td>
<td><p>Access</p></td>
<td><p>Access</p></td>
</tr>
<tr class="even">
<td><p>16407</p></td>
<td><p>AOC</p></td>
<td><p>AOC</p></td>
</tr>
<tr class="odd">
<td><p>16408</p></td>
<td><p>GCC</p></td>
<td><p>GCC</p></td>
</tr>
<tr class="even">
<td><p>16409</p></td>
<td><p>IMMCU</p></td>
<td><p>IMMCU</p></td>
</tr>
<tr class="odd">
<td><p>16410</p></td>
<td><p>XmppTGW</p></td>
<td><p>XmppGateway</p></td>
</tr>
<tr class="even">
<td><p>32769</p></td>
<td><p>Puerta</p></td>
<td><p>Puerta</p></td>
</tr>
<tr class="odd">
<td><p>32770</p></td>
<td><p>GatewayMediationServerPair</p></td>
<td><p>GatewayMediationServerPair</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


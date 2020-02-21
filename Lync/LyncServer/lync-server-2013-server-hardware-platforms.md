---
title: Plataformas de hardware de servidor de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddcfc08ff983ec080bd2382394bfc4b8c3bae3a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Plataformas de hardware de servidor para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-28_

Los roles de servidor de Lync Server 2013 y los equipos que ejecutan herramientas administrativas de Lync Server requieren hardware de 64 bits.

El hardware específico que se usa para la implementación de Lync Server 2013 puede variar en función de los requisitos de tamaño y uso. En esta sección se describe el hardware recomendado. Aunque se trata de recomendaciones y no de requisitos, el uso de hardware que no cumpla estas recomendaciones puede repercutir considerablemente en el rendimiento y ocasionar otros problemas.

<div>

## <a name="recommended-hardware-platform"></a>Plataforma de hardware recomendada

Para obtener el mejor rendimiento, se recomienda ejecutar Lync Server en servidores con hardware que cumpla los requisitos de la tabla siguiente. Si usa un hardware menos eficaz, puede tener problemas de funcionalidad o un rendimiento deficiente. Tenga en cuenta que estos requisitos de hardware son superiores a los de las versiones anteriores de Lync Server, principalmente porque en Lync Server 2013, todos los servidores front-end ejecutan SQL Server.

<div>


> [!NOTE]  
> La formación de equipos NIC es compatible y debe ser transparente para Lync Server. Para obtener más información, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server o Lync Server y equipos de adaptadores de red</A>.



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>Hardware recomendado para los servidores front-end, los servidores back-end, los servidores Standard Edition, los servidores de chat persistentes, el almacén de chat persistente y el almacén de cumplimiento de chat persistente (roles de servidor back-end para el servidor de chat persistente)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Recomendado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>procesador dual de 64 bits, HEX-Core, 2,26 gigahercios (GHz) o superior.</p>
<p>Los roles de servidor de Lync Server no admiten los procesadores Intel Itanium.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>32 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>8 o más unidades de disco duro (HHD) de 10.000 RPM con al menos 72 GB de espacio libre en disco.</p>
<p>Dos de los discos deben usar RAID 1 y seis deben usar RAID 10.</p>
<p>-O</p></li>
<li><p>Unidades de estado sólido (SSD) con rendimiento igual al de 8 unidades de disco mecánicas de 10.000 rpm.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Red</p></td>
<td><ul>
<li><p>1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendado, que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP).</p>
<div>

> [!NOTE]  
> No se admiten las configuraciones dual o multitarjeta para los servidores front-end, los servidores back-end, los servidores Standard Edition y los servidores de chat persistente.<BR>ILO/DRAC/etc. las conexiones que no se exponen al sistema operativo y que se usan para supervisar y administrar el hardware del servidor no constituyen un servidor de host múltiple y, por lo tanto, son compatibles.


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>Hardware recomendado para los servidores perimetrales, los servidores de mediación autónomos y los Directores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Recomendado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>procesador dual de 64 bits, cuatro núcleos, 2,0 gigahercios (GHz) o superior.</p>
<p>-O</p></li>
<li><p>procesador de 4 vías de 64 bits, de doble núcleo, de 2,0 GHz o superior.</p></li>
</ul>
<p>Los roles de servidor de Lync Server no admiten los procesadores Intel Itanium.</p></td>
</tr>
<tr class="even">
<td><p>Memoria</p></td>
<td><p>16 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>4 o más unidades de disco duro de 10.000 RPM con al menos 72 GB de espacio libre en disco.</p>
<p>Los discos deben estar en una configuración RAID 1 2x.</p>
<p>-O</p></li>
<li><p>Unidades de estado sólido (SSD) con un rendimiento igual al de 4 unidades de disco duro mecánicas de 10.000 rpm.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Red</p></td>
<td><ul>
<li><p>1 adaptador de red de puerto dual, 1 Gbps o superior (2 recomendado, que requiere la formación de equipos con una sola dirección MAC y una sola dirección IP). 2 las interfaces de red son necesarias en los servidores perimetrales y son compatibles con los servidores de mediación independientes.</p></li>
</ul>
<div>

> [!NOTE]  
> Las configuraciones dual o multitarjeta no son compatibles con los directores.<BR>ILO/DRAC/etc. las conexiones que no se exponen al sistema operativo y que se usan para supervisar y administrar el hardware del servidor no constituyen un servidor de host múltiple y, por lo tanto, son compatibles.


</div>
<p>Los servidores perimetrales requerirán dos interfaces de red que sean adaptadores de red de puerto dual, 1 Gbps o superior (o dos adaptadores de red emparejados, para un total de cuatro, cada par se integra con una sola dirección MAC y una sola dirección IP, para un total de dos pares).</p>
<p>Se admite la instalación de tarjetas de interfaz de red (NIC) adicionales para permitir la configuración de una dirección IP de RTC específica en los servidores de mediación independientes.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


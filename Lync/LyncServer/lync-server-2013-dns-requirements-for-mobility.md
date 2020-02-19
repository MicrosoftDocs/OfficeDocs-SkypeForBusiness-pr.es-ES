---
title: 'Lync Server 2013: requisitos de DNS para movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da4910594581f253db155bfceb85c0dcd78f60
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Requisitos de DNS para la movilidad con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-13_

Al implementar la característica de movilidad de Lync Server 2013, puede usar las nuevas direcciones URL que están disponibles con el servicio Detección automática de Microsoft Lync Server 2013 o puede usar las direcciones URL de servicios Web existentes. Si usa las direcciones URL existentes, los usuarios deben escribir manualmente las direcciones URL en la configuración del dispositivo móvil. Esta opción suele usarse para solucionar problemas. Cuando se usan las nuevas direcciones URL, los clientes móviles pueden detectar automáticamente recursos de Lync Server 2013. Cuando admite la detección automática, necesita agregar nuevos registros del sistema de nombres de dominio (DNS). En esta sección se describen los registros DNS necesarios para la detección automática.

Para admitir la detección automática, debe crear los siguientes registros DNS para cada dominio SIP:

  - Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización

  - Un registro DNS externo, o público,  para admitir usuarios móviles que se conectan desde Internet

La URL de detección automática interna no debería ser direccionable desde fuera de su red. La URL de detección automática externa no debería ser direccionable desde dentro de su red. Sin embargo, si no cumple este requisito para la dirección URL externa, la funcionalidad del cliente móvil no se verá afectada.

Los registros DNS pueden ser registros CNAME o registros A (host).

**Registros DNS internos**

Debe crear uno de los siguientes registros DNS internos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nombre de host o definición SRV</th>
<th>Se resuelve en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>Nombre de dominio completo (FQDN) de servicios Web internos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>Dirección IP de servicios Web internos (dirección IP virtual (VIP) si usa un equilibrador de carga) de su grupo de directores, si tiene uno o el grupo de servidores front-end si no tiene un director</p></td>
</tr>
</tbody>
</table>


**Registros DNS externos**

Debe crear uno de los siguientes registros DNS externos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nombre de host</th>
<th>Se resuelve en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>FQDN de servicios web externos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Dirección IP externa o pública (dirección VIP si usa un equilibrador de carga) del proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls. _tcp. &lt;sipdomain&gt;</p>
<p>Se resuelve en un registro de host (A o AAAA) para el servicio perimetral de acceso</p></td>
<td><p>Para admitir el servicio de notificaciones de inserción y el servicio de notificaciones de inserción de Apple, cree un registro SRV para cada dominio SIP que tenga clientes móviles de Microsoft Lync.</p>
<div>

> [!IMPORTANT]  
> Este requisito solo se aplica a los clientes móviles de Microsoft Lync en dispositivos móviles basados en Apple o Microsoft. Los dispositivos Android y Nokia Symbian no usan la notificación de inserción.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, también conocida como detección automática, el tráfico pasa a través del proxy inverso. El registro SRV apunta a un registro que se resuelve a través del servicio perimetral de acceso.



</div>

</div>

<span> </span>

</div>

</div>

</div>


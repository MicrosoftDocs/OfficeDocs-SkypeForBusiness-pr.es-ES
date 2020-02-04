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
ms.openlocfilehash: bc11c79c291f7db7ad9e9e3228644ee27d42e555
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Requisitos de DNS para movilidad con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-13_

Al implementar la característica de movilidad de Lync Server 2013, puede usar las nuevas direcciones URL que están disponibles con el servicio Detección automática de Microsoft Lync Server 2013 o puede usar las direcciones URL de los servicios Web existentes. Si usa las direcciones URL existentes, los usuarios necesitan introducir manualmente las direcciones URL en la configuración del dispositivo móvil. Normalmente, esta opción se usa para solucionar problemas. Al usar las nuevas direcciones URL, los clientes móviles pueden descubrir automáticamente recursos de Lync Server 2013. Cuando admite la detección automática, necesita agregar los registros del sistema de nombres de dominio (DNS) nuevos. En esta sección se describen los registros de DNS necesarios para la detección automática.

Para admitir la detección automática, cree los siguientes registros de DNS para cada dominio SIP:

  - Un registro de DNS interno para admitir usuarios móviles que se conectan desde la red de su organización

  - Un registro de DNS externo, o público, para admitir usuarios móviles que se conectan desde Internet

La URL de detección automática interna no tiene que ser direccionable desde fuera de su red. La dirección URL de detección automática externa no tiene que ser direccionable desde dentro de su red. Pero, si no cumple este requisito para la dirección URL externa, la funcionalidad del cliente móvil no tendría que verse afectada.

Los registros de DNS pueden ser registros CNAME o registros A (host).

**Registros de DNS internos**

Cree uno de los siguientes registros de DNS internos:


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
<td><p>Dirección IP de los servicios Web internos (dirección IP virtual (VIP) si usa un equilibrador de carga) de su grupo de directores, si tiene uno o el grupo de servidores front-end si no tiene un director</p></td>
</tr>
</tbody>
</table>


**Registros de DNS externos**

Cree uno de los siguientes registros de DNS externos:


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
<td><p>El FQDN de servicios web externos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Dirección IP externa o pública (dirección VIP si usa un equilibrador de carga) del proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. &lt;sipdomain&gt;</p>
<p>Se resuelve en un registro de host (A o AAAA) para el servicio perimetral de acceso.</p></td>
<td><p>Para admitir el servicio de notificaciones de inserción y el servicio de notificaciones push de Apple, puede crear un registro SRV para cada dominio SIP que tenga clientes móviles de Microsoft Lync.</p>
<div>

> [!IMPORTANT]  
> Este requisito se aplica únicamente a los clientes móviles de Microsoft Lync en Apple o en dispositivos móviles basados en Microsoft. Android y los dispositivos Nokia Symbian no usan la notificación push.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, también conocido como detección automática, el tráfico pasa por el proxy inverso. El registro SRV apunta a un registro que se resuelve a través del servicio perimetral de acceso.



</div>

</div>

<span> </span>

</div>

</div>

</div>


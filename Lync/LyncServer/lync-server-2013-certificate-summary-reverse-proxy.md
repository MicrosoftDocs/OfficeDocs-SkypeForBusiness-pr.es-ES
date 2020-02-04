---
title: 'Lync Server 2013: Resumen de certificado - Proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Resumen de certificado - Proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-14_

Los requisitos de certificados para el proxy inverso son mucho más simples que el de los servidores perimetrales. El diagrama de flujo proporcionado presenta los requisitos necesarios. La tabla adjunta presenta el nombre de asunto del certificado y los nombres alternativos del sujeto típicos en relación con los escenarios que hemos revisado en las discusiones del servidor perimetral. Para obtener más información sobre los escenarios del servidor perimetral, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Diagrama de flujo de certificados para el proxy inverso**

![Diagrama de flujo de certificados para el servidor perimetral](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagrama de flujo de certificados para el servidor perimetral")

### <a name="reverse-proxy-external-interface"></a>Proxy inverso: interfaz externa

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nombre del asunto</th>
<th>Nombre alternativo de asunto (SAN)/Order</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Proxy inverso</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Opcional):*. contoso.com</p></td>
<td><p>El certificado debe ser emitido por una entidad de certificación pública y con el EKU de servidor. Los servicios incluyen el servicio de libreta de direcciones, Office Web Apps para conferencias y las reglas de publicación de dispositivos IP de Lync. El nombre alternativo del firmante incluye:</p>
<ul>
<li><p>FQDN de servicios web externos para servidor front-end o grupo front-end</p></li>
<li><p>FQDN de servicios web externos para el grupo de directores o directores</p></li>
<li><p>Conferencia de acceso telefónico local</p></li>
<li><p>Regla de publicación de reuniones en línea</p></li>
<li><p>Office Web Apps para conferencias</p></li>
<li><p>Lyncdiscover (detección automática)</p></li>
</ul>
<p>El comodín opcional reemplaza a reunirse y a través de SAN</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Resumen del certificado-proxy inverso'
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
ms.openlocfilehash: 56da4c10da99a43c3a93f9ae251c2eb6f1536b37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Resumen de certificado-proxy inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-14_

Los requisitos de certificado para el proxy inverso son mucho más simples que los de los servidores perimetrales. El diagrama de flujo proporcionado muestra los requisitos necesarios. La tabla adjunta presenta los nombres de sujeto de certificado típicos y los nombres alternativos de sujeto en relación con los escenarios que se han revisado en las discusiones del servidor perimetral. Para obtener más información sobre los escenarios del servidor perimetral, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Diagrama de flujo de certificados para proxy inverso**

![Diagrama de flujo de certificados para servidores perimetrales](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagrama de flujo de certificados para servidores perimetrales")

### <a name="reverse-proxy-external-interface"></a>Proxy inverso: Interfaz externa

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
<th>Nombre de sujeto</th>
<th>Nombre alternativo del sujeto (SAN)/orden</th>
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
<td><p>Una entidad emisora de certificados debe otorgar el certificado junto con el servidor EKU. Los servicios incluyen el servicio de libreta de direcciones, la expansión de grupos de distribución Office Web apps for Conferencing y las reglas de publicación de dispositivos IP de Lync. Los nombres alternativos del sujeto incluyen:</p>
<ul>
<li><p>FQDN de servicios web externos para el servidor front-end o el grupo de servidores front-end</p></li>
<li><p>FQDN de servicios web externos para el director o el grupo de directores</p></li>
<li><p>Conferencia de acceso telefónico local</p></li>
<li><p>Regla de publicación de reunión en línea</p></li>
<li><p>Office Web Apps para conferencias</p></li>
<li><p>Lyncdiscover (Autodiscover)</p></li>
</ul>
<p>El carácter comodín opcional sustituye tanto la SAN de reuniones, como de marcado</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


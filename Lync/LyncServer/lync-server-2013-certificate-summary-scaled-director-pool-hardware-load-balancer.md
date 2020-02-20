---
title: Resumen de certificado-grupo de Director escalado, equilibrador de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59adcaf94c3c4364c6bb62ce2b8cbcc5639af6b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Resumen de certificado-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Los requisitos de certificado para un director con un equilibrador de carga de hardware usarán un certificado predeterminado que tenga un nombre de sujeto y nombres alternativos de sujeto para los servicios que el grupo de directores pueda recibir. Se solicita un certificado para cada director del grupo de servidores. Además, hay un certificado OAuth Token para propósitos de servicio de autenticación de servidor que se instala en cada servidor.

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a>Certificados para un director escalado que usa un equilibrador de carga de hardware

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
<th>Nombre de sujeto (SN)</th>
<th>Nombres alternativos del sujeto (SAN)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Valor predeterminado</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Opcional) *.contoso.com</p></td>
<td><p>Los certificados de director se pueden solicitar desde una entidad de certificación (CA) administrada internamente o desde una CA pública.</p>
<p>El Director responde a las solicitudes del proxy inverso en el perímetro o desde el servidor perimetral.</p>
<p>O una entrada con comodín para las direcciones URL simples</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Sin entradas</p></td>
<td>


> [!IMPORTANT]
> Tenga en cuenta que la longitud mínima de clave es 1024, pero puede recibir una advertencia de que la clave mínima recomendada es de 2048 bits.


<p>El certificado OAuthTokenIssuer es un certificado de un solo propósito para los fines de los servidores de autenticación en un entorno de gran escala, y pueden solicitarse a una CA interna o a una CA pública. Este certificado es obligatorio.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


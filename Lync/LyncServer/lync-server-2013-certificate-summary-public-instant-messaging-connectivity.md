---
title: 'Lync Server 2013: Resumen del certificado-conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Resumen del certificado: conectividad de mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-19_

Para configurar certificados para la conectividad de mensajería instantánea pública, primero debe tener en cuenta que no hay nada diferente de otros tipos de Federación SIP o incluso los certificados de servidor perimetral estándar, excepto que America Online (AOL) requiere un único configuración de certificado. Además del uso mejorado de claves (EKU) del servidor, America Online requiere que el certificado o los certificados (en el caso de un grupo de límites) contengan también el EKU de cliente. El EKU de cliente es una adición al certificado y forma parte del certificado público externo que se asigna al servidor perimetral.

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Resumen del certificado: conectividad de mensajería instantánea pública


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
<th>Nombres alternativos de asunto (SAN)/Order</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Perimetral de acceso externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe ser de una entidad de certificación pública y debe tener el EKU de servidor y el EKU de cliente si se va a implementar la conectividad de mensajería instantánea pública con AOL. El certificado se asigna a las interfaces del servidor perimetral externo para:</p>
<ul>
<li><p>Servicio perimetral de acceso</p></li>
<li><p>Servicio perimetral de conferencia web</p></li>
<li><p>Servicio perimetral A/V</p></li>
</ul>
<p>Tenga en cuenta que las redes San se agregan automáticamente al certificado según sus definiciones en el generador de topologías. Agregue las entradas de SAN según sea necesario para dominios SIP adicionales y otras entradas que necesite admitir. El nombre del asunto se replica en el SAN y debe estar presente para que funcione correctamente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


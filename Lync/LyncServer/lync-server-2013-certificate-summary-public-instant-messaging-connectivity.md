---
title: 'Lync Server 2013: Resumen de certificado-conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcbcb7d00eb21f4dcbce2c8d632df44c10a43a26
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Resumen de certificado-conectividad de mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-19_

Para configurar certificados para la conectividad de mensajería instantánea pública, debe tener en cuenta en primer lugar que no hay nada diferente de otros tipos de Federación SIP o de los certificados de servidor perimetral estándar, excepto que America Online (AOL) requiere un único configuración de certificados. Además del uso mejorado de claves (EKU) del servidor, America Online requiere que el certificado o los certificados (en el caso de un grupo de servidores perimetrales) también contengan el EKU del cliente. El EKU de cliente es una adición al certificado y forma parte del certificado público externo que se asigna a su servidor perimetral.

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
<th>Nombre de sujeto</th>
<th>Nombres alternativos del sujeto (SAN)/orden</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor perimetral de acceso/externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe ser de una entidad de certificación pública y debe tener el EKU de servidor y el EKU de cliente si se va a implementar la conectividad de mensajería instantánea pública con AOL. El certificado se asigna a las interfaces del servidor perimetral externo para:</p>
<ul>
<li><p>Servicio perimetral de acceso</p></li>
<li><p>Servicio perimetral de conferencias web</p></li>
<li><p>Servicio perimetral A/V</p></li>
</ul>
<p>Tenga en cuenta que las SAN se agregan automáticamente al certificado basado en las definiciones del Generador de topologías. Agregue entradas SAN según sea necesario para dominios adicionales de SIP y otras entradas que necesite admitir. El nombre del sujeto se replica en la SAN y debe estar presente para el correcto funcionamiento.</p></td>
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


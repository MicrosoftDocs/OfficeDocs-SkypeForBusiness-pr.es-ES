---
title: Resumen de certificado - Perímetro consolidado de equipo único con direcciones IP públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Single consolidated edge with public IP addresses
ms:assetid: 25b8ae7a-e5a0-43c0-92ae-7e144d5e4a36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204747(v=OCS.15)
ms:contentKeyID: 48183653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07c5bce784c6d05393b38b68c2558362bcb9525f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Resumen de certificado - Perímetro consolidado de equipo único con direcciones IP públicas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Microsoft Lync Server 2013 usa certificados para autenticar mutuamente otros servidores y para cifrar los datos del servidor al servidor y del servidor al cliente. Los certificados requieren que coincidan los registros del sistema de nombres de dominio (DNS) asociados con los servidores y el nombre de asunto (SN) y el nombre alternativo de asunto (SAN) en el certificado. Para asignar correctamente servidores, registros DNS y entradas de certificados, debe planificar cuidadosamente los nombres de dominio completos del servidor previsto como registrados en DNS y las entradas SN y SAN del certificado.

El certificado asignado a las interfaces externas del servidor perimetral se solicita desde una entidad de certificación (CA) pública. Las CA públicas que han demostrado su éxito en el suministro de certificados para las comunicaciones unificadas se enumeran en [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) el artículo siguiente: al solicitar el certificado, puede usar la solicitud de certificado generada por el servidor de Lync. Asistente para la implementación o crear la solicitud manualmente o mediante un proceso proporcionado por la CA pública. Al asignar el certificado, el certificado se asigna a la interfaz de servicio perimetral de acceso, la interfaz de servicio de conferencia web y el servicio de autenticación de audio y vídeo. El servicio de autenticación de audio y vídeo no debe confundirse con el servicio de borde a/V que no usa un certificado para cifrar las transmisiones de audio y vídeo. La interfaz de servidor de borde interno puede usar un certificado de una entidad de certificación interna o de un certificado de una entidad de certificación pública. El certificado de interfaz interna usa solo el SN y no necesita ni usar entradas de SAN.

<div>


> [!NOTE]
> En la siguiente tabla se muestra una segunda entrada de SIP (sip.fabrikam.com) en la lista Subject Alternative Name, como referencia. Para cada dominio SIP de su organización, necesita agregar el FQDN correspondiente que aparece en la lista nombre alternativo de sujeto del certificado.



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-public-ip-addresses"></a>Certificados requeridos para un solo borde consolidado con direcciones IP públicas


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
<th>Nombres alternativos de asunto (SAN)/Order</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Un solo borde consolidado (periferia externa)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe ser de una entidad de certificación pública y debe tener el EKU de servidor y el EKU de cliente si se va a implementar la conectividad de mensajería instantánea pública con AOL. El certificado se asigna a las interfaces de borde externo para:</p>
<ul>
<li><p>Perímetro de acceso</p></li>
<li><p>Borde de conferencias</p></li>
<li><p>Servidor perimetral A/V</p></li>
</ul>
<p>Tenga en cuenta que las redes San se agregan automáticamente al certificado según sus definiciones en el generador de topologías. Agregue las entradas de SAN según sea necesario para dominios SIP adicionales y otras entradas que necesite admitir. El nombre del asunto se replica en el SAN y debe estar presente para que funcione correctamente.</p></td>
</tr>
<tr class="even">
<td><p>Un solo borde consolidado (contorno interno)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>No se requiere SAN</p></td>
<td><p>El certificado puede ser emitido por una entidad de certificación pública o privada, y debe contener el EKU de servidor. El certificado se asigna a la interfaz de borde interno.</p></td>
</tr>
</tbody>
</table>


</div>

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
<td><p>El certificado debe ser de una entidad de certificación pública y debe tener el EKU de servidor y el EKU de cliente si se va a implementar la conectividad de mensajería instantánea pública con AOL. El certificado se asigna a las interfaces de borde externo para:</p>
<ul>
<li><p>Perímetro de acceso</p></li>
<li><p>Borde de conferencias</p></li>
<li><p>Servidor perimetral A/V</p></li>
</ul>
<p>Tenga en cuenta que las redes San se agregan automáticamente al certificado según sus definiciones en el generador de topologías. Agregue las entradas de SAN según sea necesario para dominios SIP adicionales y otras entradas que necesite admitir. El nombre del asunto se replica en el SAN y debe estar presente para que funcione correctamente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Resumen del certificado para el protocolo de presencia y mensajería extensible


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
<td><p>Asignar a servicio perimetral de acceso al servidor perimetral o grupo de servidores perimetrales</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*.contoso.com</strong></p></td>
<td><p>Las tres primeras entradas de SAN son las entradas normales de SAN para un servidor de borde completo. La contoso.com es la entrada necesaria para la Federación con el socio XMPP en el nivel de dominio raíz. Esta entrada permitirá que XMPP para todos los dominios con el sufijo *. contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


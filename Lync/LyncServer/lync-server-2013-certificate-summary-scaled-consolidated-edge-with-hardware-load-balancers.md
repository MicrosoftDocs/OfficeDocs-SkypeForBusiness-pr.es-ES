---
title: Resumen de certificado-servidor perimetral consolidado ampliado con equilibradores de carga de hardware
description: Resumen de certificado-servidor perimetral consolidado ampliado con equilibradores de carga de hardware.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 894a9f3e-7cba-4915-8fdf-e52f2f25126f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398692(v=OCS.15)
ms:contentKeyID: 48184729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc8b21d5f42575f324837ace35e4e8f0424e515f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572246"
---
# <a name="certificate-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Resumen de certificado-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Microsoft Lync Server 2013 usa certificados para autenticar mutuamente otros servidores y cifrar los datos del servidor al servidor y del servidor al cliente. Los certificados requieren que el nombre coincida con los registros del sistema de nombre de dominio (DNS) asociados con los servidores, el nombre de sujeto (SN) y el nombre alternativo del sujeto (SAN) en el certificado. Para asignar servidores, registros de DNS y entradas de certificado correctamente, debe planificar con atención los nombres de dominio completo creados para el servidor tal como se registraron en las entradas de DNS, SN y SAN en el certificado.

El certificado asignado a las interfaces externas del servidor perimetral se solicita desde una entidad de certificación (CA) pública. En el siguiente artículo se enumeran las entidades de certificación públicas que han demostrado su éxito en el suministro de certificados para las comunicaciones unificadas: [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) . Al solicitar el certificado, puede usar la solicitud de certificado generada por el Asistente para la implementación de Lync Server o bien crear la solicitud de forma manual o mediante un proceso proporcionado por la entidad de certificación pública. Al asignar el certificado, el certificado se asigna a la interfaz del servicio perimetral de acceso, la interfaz del servicio perimetral de conferencia web y el servicio de autenticación de audio y vídeo. El servicio de autenticación de audio y vídeo no debe confundirse con el servicio perimetral a/V, que no usa un certificado para cifrar las secuencias de audio y vídeo. La interfaz del servidor perimetral interno puede usar un certificado de una entidad de certificación interna (para su organización) o un certificado de una entidad de certificación pública. El certificado de la interfaz interna solamente usa el SN y no necesita ni utiliza entradas de SAN.

<div>


> [!NOTE]
> La tabla de Certificados necesarios para la topología perimetral consolidada escalada (carga equilibrada con hardware) muestra una segunda entrada SIP en la lista de nombres alternativos de sujeto de referencia. Para cada dominio SIP de la organización, es necesario que aparezca un FQDN correspondiente en la lista de nombres alternativos de sujeto del certificado.



</div>

<div>

## <a name="certificates-required-for-scaled-consolidated-edge-with-hardware-load-balancers"></a>Certificados necesarios para la topología perimetral consolidada escalada (carga equilibrada con hardware)


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
<td><p>Servidor perimetral consolidado único (periferia externa)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe ser de una CA pública y debe tener el servidor EKU y cliente EKU si va a implementarse conectividad de MI pública con AOL. Además, para los servidores perimetrales escalados, la clave privada del certificado debe ser exportable y el certificado y la clave privada se copian en cada servidor perimetral. el certificado se asigna a las interfaces perimetrales externas para:</p>
<ul>
<li><p>Servicio perimetral de acceso</p></li>
<li><p>Servicio perimetral de conferencias web</p></li>
<li><p>Servicio perimetral A/V</p></li>
</ul>
<p>Tenga en cuenta que las SAN se agregan automáticamente al certificado basado en las definiciones del Generador de topologías. Agregue entradas SAN según sea necesario para dominios adicionales de SIP y otras entradas que necesite admitir. El nombre del sujeto se replica en la SAN y debe estar presente para el correcto funcionamiento.</p></td>
</tr>
<tr class="even">
<td><p>Servidor perimetral consolidado único (perímetro interno)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>No se requiere SAN</p></td>
<td><p>Una CA pública o privada puede otorgar un certificado que debe contener el servidor EKU. El certificado se asigna a la interfaz del servidor perimetral interno.</p></td>
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
<th>Nombre de sujeto</th>
<th>Nombres alternativos del sujeto (SAN)/orden</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servicio perimetral de acceso externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe ser de una CA pública y debe tener el servidor EKU y cliente EKU si va a implementarse conectividad de MI pública con AOL. El certificado se asigna a las interfaces perimetrales externas para:</p>
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

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Resumen de certificado para el Protoloco extensible de mensajería y presencia


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
<td><p>Asignar a servicio perimetral de acceso del servidor perimetral o grupo de servidores perimetrales</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*. contoso.com</strong></p></td>
<td><p>Las tres primeras entradas de SAN son las entradas normales de SAN para un servidor perimetral completo. La entrada contoso.com es necesaria para la federación con el socio XMPP en el nivel raíz del dominio. Esta entrada permitirá XMPP en todos los dominios con el sufijo *.contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


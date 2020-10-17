---
title: 'Lync Server 2013: cifrado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fca7065c18ab67fce1940adccce6b9071f3373
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533337"
---
# <a name="encryption-for-lync-server-2013"></a>Cifrado para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-09-14_

Microsoft Lync Server 2013 usa TLS y MTLS para cifrar los mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o atraviesa el perímetro de la red interna. TLS es opcional, pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace multimedia. Si se configura TLS en este vínculo, se requiere MTLS. Por lo tanto, la puerta de enlace debe estar configurada con un certificado de una entidad de certificación que sea de confianza para el servidor de mediación.

<div>


> [!NOTE]  
> Se publicó un aviso de seguridad sobre SSL 3,0 en 2014. La deshabilitación de SSL 3,0 en Lync Server 2013 es una opción admitida. Para obtener más información sobre el aviso de seguridad, consulte <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A> .



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" />Nota de seguridad:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Para asegurarse de que se usa el protocolo criptográfico más seguro, Lync Server 2013 ofrecerá protocolos de cifrado TLS en el siguiente orden a los clientes: <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. TLS es un aspecto crítico de Lync Server 2013 y, por lo tanto, es necesario para mantener un entorno compatible.</td>
</tr>
</tbody>
</table>


</div>

Los requisitos para el tráfico entre clientes dependen de si el tráfico atraviesa el firewall interno de la empresa. El tráfico estrictamente interno puede utilizar TLS, en cuyo caso se cifran los mensajes instantáneos, o TCP, en cuyo caso no se cifran.

En la tabla siguiente, se resumen los requisitos de protocolo para cada tipo de tráfico.

### <a name="traffic-protection"></a>Protección de tráfico

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfico</th>
<th>Protegido por</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>De servidor a servidor</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Cliente a servidor</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Mensajería instantánea y presencia</p></td>
<td><p>TLS (si se ha configurado para TLS)</p></td>
</tr>
<tr class="even">
<td><p>Audio, vídeo y uso compartido de escritorio</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Uso compartido de escritorio (señalización)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Conferencia web</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Descarga del contenido de las reuniones, descarga de la libreta de direcciones y expansión de grupos de distribución</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Cifrado de medios

El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. Además, el contenido multimedia que fluye en ambas direcciones entre el servidor de mediación y el próximo salto interno también se cifra con SRTP. Los medios que fluyen en ambas direcciones entre el servidor de mediación y una puerta de enlace multimedia no están cifrados de forma predeterminada. El servidor de mediación puede admitir el cifrado de los medios que fluyen hacia la puerta de enlace multimedia, pero la puerta de enlace debe admitir MTLS y el almacenamiento de un certificado.

<div>


> [!NOTE]  
> El audio y vídeo (A/V) es compatible con la nueva versión de Windows Live Messenger. Si va a implementar la Federación de A/V con Windows Live Messenger, también debe modificar el nivel de cifrado de Lync Server. De forma predeterminada, el nivel de cifrado es Requerido. Debe cambiar esta configuración a compatible con el shell de administración de Lync Server. Para obtener más información, consulte <A href="lync-server-2013-deploying-external-user-access.md">Deploying external User Access in Lync Server 2013</A> en la documentación sobre implementación.



</div>

El tráfico de medios de audio y vídeo no está cifrado entre los clientes de Microsoft Lync 2013 y Windows Live.

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 y Microsoft Exchange Server 2013 operan con compatibilidad con algoritmos estándar federal de procesamiento de información (FIPS) 140-2 si los sistemas operativos Windows Server están configurados para usar los algoritmos FIPS 140-2 para la criptografía de sistema. Para implementar la compatibilidad con FIPS, debe configurar todos los servidores que ejecuten Lync Server 2013 para que lo admitan. Para obtener más información sobre el uso de los algoritmos compatibles con FIPS y cómo implementar la compatibilidad con FIPS, consulte el artículo 811833 de Microsoft Knowledge base, los efectos de habilitar la configuración de seguridad "criptografía de sistema: usar algoritmos compatibles FIPS para cifrado, hash y firma" en Windows XP y en versiones posteriores de Windows en [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) . Para obtener más información sobre las limitaciones y la compatibilidad de FIPS 140-2 en Exchange 2010, consulte Exchange 2010 SP1 y la compatibilidad con algoritmos compatibles con FIPS en [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) .

</div>

</div>

<span> </span>

</div>

</div>

</div>


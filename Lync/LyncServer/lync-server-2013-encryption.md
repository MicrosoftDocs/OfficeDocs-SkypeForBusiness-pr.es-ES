---
title: 'Lync Server 2013: cifrado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c989213b050bdb536e95a8a42e8f7b35292eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Cifrado para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-09-14_

Microsoft Lync Server 2013 usa TLS y MTLS para cifrar los mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o de si cruza el perímetro de la red interna. TLS es opcional, pero se recomienda encarecidamente entre el servidor de mediación y la puerta de enlace multimedia. Si en este vínculo está configurado TLS, se requiere MTLS. Por lo tanto, la puerta de enlace debe estar configurada con un certificado de una entidad emisora de confianza en el servidor de mediación.

<div>


> [!NOTE]  
> En 2014 se publicó un aviso de seguridad sobre SSL 3.0. La opción de deshabilitar SSL 3,0 en Lync Server 2013 es una opción admitida. Para obtener más información sobre el asesoramiento de seguridad <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>, consulte.



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
<td>Para asegurarse de que se usa el protocolo criptográfico más sólido, Lync Server 2013 ofrecerá protocolos de cifrado TLS en el siguiente orden a los clientes: <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. TLS es un aspecto crítico de Lync Server 2013 y, por lo tanto, es necesario para mantener un entorno compatible.</td>
</tr>
</tbody>
</table>


</div>

Los requisitos para el tráfico de cliente a cliente dependen de si ese tráfico atraviesa el firewall interno de la empresa. El tráfico estrictamente interno puede usar TLS, en cuyo caso el mensaje instantáneo se cifra, o TCP, en cuyo caso no lo es.

En la tabla siguiente se resumen los requisitos de protocolo para cada tipo de tráfico.

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
<td><p>Servidor a servidor</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Cliente a servidor</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Mensajería instantánea y presencia</p></td>
<td><p>TLS (si está configurado para TLS)</p></td>
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

El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un perfil de protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. Además, los medios que fluyen en ambas direcciones entre el servidor de mediación y el servidor interno del próximo salto también se cifran mediante SRTP. Los medios que fluyen en las dos direcciones entre el servidor de mediación y una puerta de enlace multimedia no están cifrados de forma predeterminada. El servidor de mediación puede admitir el cifrado hacia la puerta de enlace multimedia, pero la puerta de enlace debe admitir MTLS y el almacenamiento de un certificado.

<div>


> [!NOTE]  
> El audio/vídeo (A/V) es compatible con la nueva versión de Windows Live Messenger. Si está implementando la Federación de A/V con Windows Live Messenger, también debe modificar el nivel de cifrado de Lync Server. De manera predeterminada, el nivel de cifrado es obligatorio. Debe cambiar esta configuración para que sea compatible con el shell de administración de Lync Server. Para obtener más información, vea <A href="lync-server-2013-deploying-external-user-access.md">implementar el acceso de usuarios externos en Lync Server 2013</A> en la documentación de implementación.



</div>

El tráfico de audio y vídeo no se cifra entre Microsoft Lync 2013 y los clientes de Windows Live.

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 y Microsoft Exchange Server 2013 funcionan con los algoritmos estándar federal de procesamiento de información (FIPS) 140-2 si los sistemas operativos Windows Server están configurados para usar los algoritmos FIPS 140-2 para el cifrado de sistema. Para implementar la compatibilidad con FIPS, debe configurar cada servidor que ejecute Lync Server 2013 de soporte técnico. Para obtener detalles sobre el uso de los algoritmos compatibles con FIPS y cómo implementar la compatibilidad con FIPS, consulte el artículo 811833 de Microsoft Knowledge base, los efectos de habilitar la seguridad "criptografía del sistema: usar algoritmos compatibles con FIPS para cifrado, hash y firma" configuración en Windows XP y en versiones posteriores de Windows en [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833). Para obtener más información sobre las limitaciones y la compatibilidad de FIPS 140-2 en Exchange 2010, consulte Exchange 2010 SP1 y la compatibilidad [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)con los algoritmos compatibles con FIPS en.

</div>

</div>

<span> </span>

</div>

</div>

</div>


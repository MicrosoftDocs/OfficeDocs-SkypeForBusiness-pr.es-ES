---
title: Cifrado para Lync Server 2013
TOCTitle: Cifrado para Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59679374
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cifrado para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Microsoft Lync Server 2013 usa TLS y MTLS para cifrar los mensajes instantáneos. Todo el tráfico de servidor a servidor requiere MTLS, independientemente de si el tráfico se limita a la red interna o de si cruza el perímetro de la red interna. TLS es opcional, pero muy recomendado entre el servidor de mediación y la puerta de enlace de medios. Si en este vínculo está configurado TLS, se requiere MTLS. Por lo tanto, la puerta de enlace debe configurarse con un certificado de una entidad emisora que sea de confianza para el Servidor de mediación.

Los requisitos para el tráfico entre clientes dependen de si el tráfico atraviesa el firewall interno de la empresa o no. El tráfico estrictamente interno puede utilizar TLS, en cuyo caso se cifran los mensajes instantáneos, o TCP, en cuyo caso no se cifran.

En la tabla siguiente, se resumen los requisitos de protocolo para cada tipo de tráfico.

### Protección de tráfico

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


## Cifrado de medios

El tráfico de medios se cifra mediante RTP seguro (SRTP), que es un protocolo de transporte en tiempo real (RTP) que proporciona al tráfico RTP confidencialidad, autenticación y protección contra los ataques de reproducción. SRTP usa una clave de sesión generada por el servicio de autenticación de reproducción de medios como respuesta a la correcta autenticación de la solicitud del servidor (en nombre de los participantes en los medios). La clave de sesión se protege mediante el nombre de usuario y la contraseña negociados que presentan los Servidores front-end al servicio de autenticación de reproducción de medios, y se envía a los participantes a través del canal SIP protegido mediante TLS. Descifrar la clave de la sesión protegida con el nombre de usuario y la contraseña que el servicio de reproducción de medios utilizó y proporcionó de forma protegida mediante el certificado TLS del participante y el canal SIP protegido permite a los participantes descifrar la secuencia SRTP. Además, los medios que fluyen en ambas direcciones entre el servidor de mediación y el servidor interno del próximo salto también se cifran mediante SRTP. Los medios que fluyen en ambas direcciones entre el servidor de mediación y una puerta de enlace multimedia no se cifran. El servidor de mediación puede admitir el cifrado de los medios que fluyen hacia la puerta de enlace multimedia, pero la puerta de enlace debe admitir MTLS y el almacenamiento de un certificado.


> [!NOTE]
> La nueva versión de Windows Live Messenger admite funciones de audio y vídeo (A/V). Si implementa la federación de audio y vídeo (A/V) con Windows Live Messenger, cambie también el nivel de cifrado de Lync Server. De manera predeterminada, el nivel de cifrado es Obligatorio. Debe cambiar esta configuración a Compatible con el Shell de administración de Lync Server. Para obtener más información, consulte <A href="lync-server-2013-deploying-external-user-access.md">Implementar el acceso de usuarios externos en Lync Server 2013</A> en la documentación sobre implementación.



El tráfico de medios de audio y vídeo no se cifra entre Microsoft Lync 2013 y los clientes de Windows Live.

## FIPS

Lync Server 2013 y Microsoft Exchange Server 2013 funcionan con compatibilidad con algoritmos del Estándar federal de procesamiento de información (FIPS) 140-2 si los sistemas operativos de Windows Server se configuran para usar algoritmos FIPS 140-2 para la criptografía del sistema. Para implementar la compatibilidad con FIPS, debe configurar cada uno de los servidores que ejecutan Lync Server 2013. Para más información sobre los algoritmos compatibles con FIPS y sobre cómo implementar la compatibilidad con FIPS, consulte el artículo 811833 de Microsoft Knowledge Base, "Los efectos de habilitar la "Criptografía de sistema: usar FIPS algoritmos compatibles para codificación, algoritmos hash y firma", una configuración de seguridad en Windows XP y en versiones posteriores de Windows en[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833). Para más información sobre la compatibilidad con FIPS 140-2 y las limitaciones en Exchange 2010, consulte Exchange 2010 SP1 y compatibilidad con algoritmos compatibles con FIPS en [http://go.microsoft.com/fwlink/p/?LinkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).


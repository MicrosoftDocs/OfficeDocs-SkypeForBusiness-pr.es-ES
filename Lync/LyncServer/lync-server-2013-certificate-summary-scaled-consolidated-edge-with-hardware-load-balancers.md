---
title: "Resumen certif.: Servidor perimetral consol. ampliado con equilibr. carga de hardware"
TOCTitle: Resumen de certificado - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
ms:assetid: 894a9f3e-7cba-4915-8fdf-e52f2f25126f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398692(v=OCS.15)
ms:contentKeyID: 48275929
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de certificado - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-15_

Microsoft Lync Server 2013 utiliza certificados para autenticar mutuamente otros servidores y para cifrar datos de servidor a servidor y de servidor a cliente. Los certificados necesitan un nombre que coincida con los registros del sistema de nombre de dominio (DNS) asociado a los servidores y el nombre de sujeto (SN) y nombre alternativo de sujeto (SAN) del certificado. Para asignar correctamente servidores, registros DNS y entradas de certificados, planee con cuidado los nombres de dominio completo (RQDN) del servidor que quiere utilizar como aparece registrado en el DNS y las entradas de nombre de sujeto (SN) y de nombre alternativo de sujeto (SAN) del certificado.

El certificado asignado a las interfaces externas de Servidor perimetral se solicita desde una entidad emisora de certificados (CA) pública. Las entidades emisoras de certificados públicas que han demostrado otorgar certificados correctamente para Comunicaciones unificadas se encuentran enumeradas en el siguiente artículo: [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0xc0a). Al solicitar el certificado, es posible usar la solicitud de certificado generada por el Asistente para la implementación de Lync Server o crear la solicitud manualmente o mediante un proceso proporcionado por la CA pública. Al asignar el certificado, este se asigna a la interfaz de Servidor perimetral de acceso, a la interfaz de Servicio perimetral de conferencia web y al servicio de Autenticación de audio y vídeo. No se debe confundir el servicio de Autenticación de audio y vídeo con Servicio perimetral A/V, que no usa un certificado para cifrar las transmisiones de audio y vídeo. La interfaz Servidor perimetral interna puede usar un certificado de una CA interna (a su organización) o un certificado de una CA pública. El certificado de la interfaz interna solamente usa el SN y no necesita ni utiliza entradas de SAN.


> [!NOTE]
> La siguiente tabla muestra una segunda entrada SIP (sip.fabrikam.com) en la lista de nombres alternativos de sujeto de referencia. Para cada dominio SIP de su organización, necesita añadir un nombre de dominio completo (FQDN) enumerado en la lista de nombres alternativos de sujeto del certificado



## Certificados necesarios para la topología perimetral consolidada escalada (carga equilibrada con hardware)


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
<th>Nombres alternativos del sujeto (SAN)/Orden</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor perimetral consolidado de un solo equipo (perímetro externo)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe haber sido emitido por una entidad emisora pública y debe disponer del EKU de servidor y de cliente si la conectividad de la mensajería instantánea pública se implementa con AOL. Además, para Servidores perimetrales escalado, la clave privada del certificado debe ser exportable y el certificado y la clave privada deben copiarse a cada Servidor perimetral. El certificado se asigna a las interfaces externas para:</p>
<ul>
<li><p>Servidor perimetral de acceso</p></li>
<li><p>Servicio perimetral de conferencia web</p></li>
<li><p>Servicio perimetral A/V</p></li>
</ul>
<p>Tenga en cuenta que los SAN se agregan automáticamente al certificado a partir de las definiciones del Generador de topologías. Agregue tantas entradas de SAN como necesite para los dominios SIP adicionales y las demás entradas que necesite admitir. El nombre del firmante se replica en el SAN y debe estar presente para que el funcionamiento sea correcto.</p></td>
</tr>
<tr class="even">
<td><p>Servidor perimetral consolidado de un solo equipo (perímetro interno)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>No es necesario el nombre alternativo del sujeto (SAN)</p></td>
<td><p>Una CA pública o privada puede otorgar un certificado que debe contener el EKU del servidor. El certificado se asigna a la interfaz del Servidor perimetral interno.</p></td>
</tr>
</tbody>
</table>


## Resumen del certificado – Conectividad de mensajería instantánea pública


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
<th>Nombres alternativos del sujeto (SAN)/Orden</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externo/ Servidor perimetral de acceso</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe proceder de una entidad de certificación pública y tener el EKU de servidor y el EKU de cliente, si desea implementar la conectividad de mensajería instantánea pública con AOL. El certificado se asigna a las interfaces de perímetro externo para:</p>
<ul>
<li><p>Servidor perimetral de acceso</p></li>
<li><p>Servicio perimetral de conferencia web</p></li>
<li><p>Servicio perimetral A/V</p></li>
</ul>
<p>Tenga en cuenta que los SAN se agregan automáticamente al certificado a partir de las definiciones del Generador de topologías. Agregue tantas entradas de SAN como necesite para los dominios SIP adicionales y las demás entradas que necesite admitir. El nombre del firmante se replica en el SAN y debe estar presente para que el funcionamiento sea correcto.</p></td>
</tr>
</tbody>
</table>


## Resumen de certificado para el protocolo extensible de mensajería y presencia


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
<th>Nombres alternativos del sujeto (SAN)/Orden</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Asigne al Servidor perimetral de acceso del Servidor perimetral o el Grupo de servidores perimetrales</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*.contoso.com</strong></p></td>
<td><p>Las tres primeras entradas de SAN son las entradas de SAN normales para un Servidor perimetral completo. La entrada contoso.com se necesita para la federación con el socio de XMPP en el nivel de dominio raíz. Esta entrada permitirá XMPP para todos los dominios que tengan el sufijo *.contoso.com.</p></td>
</tr>
</tbody>
</table>


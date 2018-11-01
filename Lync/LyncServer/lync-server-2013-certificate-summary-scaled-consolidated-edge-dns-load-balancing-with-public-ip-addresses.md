---
title: "Resumen certif: Servidor perimetral consol. ampl., equilib. carga DNS con IP públicas"
TOCTitle: Resumen de certificado - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas
ms:assetid: e87ac448-ee8f-477a-9f33-ce066c1bf093
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205399(v=OCS.15)
ms:contentKeyID: 48277033
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de certificado - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-16_

Microsoft Lync Server 2013 utiliza certificados para autenticar mutuamente otros servidores y para cifrar datos de servidor a servidor y de servidor a cliente. Los certificados necesitan un nombre que coincida con los registros del sistema de nombre de dominio (DNS) asociado a los servidores y el nombre de sujeto (SN) y nombre alternativo de sujeto (SAN) del certificado. Para asignar correctamente servidores, registros DNS y entradas de certificados, planee con cuidado los nombres de dominio completo (RQDN) del servidor que quiere utilizar como aparece registrado en el DNS y las entradas de nombre de sujeto (SN) y de nombre alternativo de sujeto (SAN) del certificado.

Una entidad emisora de certificados pública solicita el certificado asignado a las interfaces externas del Servidor perimetral. En el siguiente artículo se enumeran las entidades emisoras públicas que han demostrado su éxito a la hora de ofrecer certificados para Comunicaciones unificadas: <http://support.microsoft.com/kb/929395/es-es> Al solicitar el certificado, puede usar la solicitud de certificado que genera el Asistente para la implementación de Lync Server o crear una solicitud manualmente o mediante un proceso que proporciona la entidad emisora pública. Al asignar el certificado, este se asigna a la interfaz del Servidor perimetral de acceso, la interfaz del Servicio perimetral de conferencia web y el servicio de autenticación de audio y vídeo. Este servicio no debe confundirse con el Servicio perimetral A/V, que no necesita ningún certificado para cifrar secuencias de vídeo y audio. La interfaz interna del Servidor perimetral puede utilizar un certificado de una entidad emisora interna (para su organización) o un certificado de una entidad emisora pública. El certificado de interfaz interno utiliza solo el nombre de sujeto (SN) y no necesita o no utiliza las entradas de nombre alternativo del firmante (SAN).


> [!NOTE]
> La siguiente tabla muestra una segunda entrada SIP (sip.fabrikam.com) en la lista de nombres alternativos de sujeto de referencia. Para cada dominio SIP de su organización, necesita añadir un nombre de dominio completo (FQDN) enumerado en la lista de nombres alternativos de sujeto del certificado



## Perímetro consolidado escalado que usa el equilibrio de carga de DNS con direcciones IP públicas


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
<td><p>Perímetro consolidado escalado (Perímetro externo)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe haber sido emitido por una entidad emisora pública y debe disponer del EKU de servidor y de cliente si la conectividad de la mensajería instantánea pública se implementa con AOL. Además, para Servidores perimetrales escalado, la clave privada del certificado debe ser exportable y el certificado y la clave privada deben copiarse a cada Servidor perimetral. El certificado se asigna a las interfaces externas para:</p>
<ul>
<li><p>Perímetro de acceso</p></li>
<li><p>Servidor perimetral de conferencia</p></li>
<li><p>Servidor perimetral A/V</p></li>
</ul>
<p>Tenga en cuenta que los SAN se agregan automáticamente al certificado a partir de las definiciones del Generador de topologías. Agregue tantas entradas de SAN como necesite para los dominios SIP adicionales y las demás entradas que necesite admitir. El nombre del firmante se replica en el SAN y debe estar presente para que el funcionamiento sea correcto.</p></td>
</tr>
<tr class="even">
<td><p>Perímetro consolidado escalado (Perímetro interno)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>No es necesario el nombre alternativo del sujeto (SAN)</p></td>
<td><p>La emisión del certificado puede realizarla un emisor de certificados público o privado y debe contener el EKU de servidor. El certificado se asigna a la interfaz de perímetro interno.</p></td>
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
<td><p>Perímetro de acceso/externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe proceder de una entidad de certificación pública y tener el EKU de servidor y el EKU de cliente, si desea implementar la conectividad de mensajería instantánea pública con AOL. El certificado se asigna a las interfaces de perímetro externo para:</p>
<ul>
<li><p>Perímetro de acceso</p></li>
<li><p>Servidor perimetral de conferencia</p></li>
<li><p>Servidor perimetral A/V</p></li>
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


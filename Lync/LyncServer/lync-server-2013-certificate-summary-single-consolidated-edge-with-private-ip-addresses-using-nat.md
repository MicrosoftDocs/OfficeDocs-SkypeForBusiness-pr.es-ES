---
title: "Lync Server 2013: Resumen certific.: Servidor perim. consol. con IP privadas con NAT"
TOCTitle: Resumen de certificado - Servidor perimetral consolidado simple con direcciones IP privadas mediante NAT
ms:assetid: 6de6680e-5f47-48e6-8e06-4994d710ea6d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398519(v=OCS.15)
ms:contentKeyID: 48275583
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de certificado - Servidor perimetral consolidado simple con direcciones IP privadas mediante NAT en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-15_

Microsoft Lync Server 2013 utiliza certificados para autenticar mutuamente otros servidores y para cifrar datos de servidor a servidor y de servidor a cliente. Los certificados necesitan un nombre que coincida con los registros del sistema de nombre de dominio (DNS) asociado a los servidores y el nombre de sujeto (SN) y nombre alternativo de sujeto (SAN) del certificado. Para asignar correctamente servidores, registros DNS y entradas de certificados, planee con cuidado los nombres de dominio completo (RQDN) del servidor que quiere utilizar como aparece registrado en el DNS y las entradas de nombre de sujeto (SN) y de nombre alternativo de sujeto (SAN) del certificado.

El certificado asignado a las interfaces externas del Servidor perimetral se solicita a una entidad de certificación pública (CA). Las CA públicas que han tenido éxito a la hora de proporcionar certificados para los fines de Comunicaciones unificadas se indican en el siguiente artículo: [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0xc0a). Al solicitar el certificado, puede usar la solicitud de certificado generada por el Asistente para la implementación de Lync Server o bien crear la solicitud manualmente con cmdlets del Shell de administración de Lync Server o mediante un proceso proporcionado por una CA pública. Para más información sobre los cmdlets del Shell de administración de Lync Server para la administración de certificados, vea [Cmdlets de certificados y autenticación](https://docs.microsoft.com/en-us/powershell/module/skype/). Al asignar el certificado, este se asigna a la interfaz del Servidor perimetral de acceso, a la interfaz del Servicio perimetral de conferencia web y al servicio de autenticación de audio y vídeo. El servicio de autenticación de audio y vídeo no debe confundirse con el Servicio perimetral A/V, que no usa un certificado para cifrar las secuencias de audio y vídeo. La interfaz interna del Servidor perimetral puede usar un certificado de una CA interna (para su organización) o uno de una CA pública. El certificado de la interfaz interna solo usa el SN y no necesita ni usa entradas SAN.


> [!NOTE]
> La siguiente tabla muestra una segunda entrada SIP (sip.fabrikam.com) en la lista de nombres alternativos de sujeto de referencia. Para cada dominio SIP de su organización, necesita añadir un nombre de dominio completo (FQDN) enumerado en la lista de nombres alternativos de sujeto del certificado



## Certificados requeridos para la topología perimetral consolidada de un solo equipo


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
<td><p>Perímetro consolidado de un solo equipo (Perímetro externo)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>El certificado debe proceder de una entidad de certificación pública y tener el EKU de servidor y el EKU de cliente, si desea implementar la conectividad de mensajería instantánea pública con AOL. El certificado se asigna a las interfaces de perímetro externo para:</p>
<ul>
<li><p>Perímetro de acceso</p></li>
<li><p>Servidor perimetral de conferencia</p></li>
<li><p>Servidor perimetral A/V</p></li>
</ul>
<p>Tenga en cuenta que los SAN se agregan automáticamente al certificado a partir de las definiciones del Generador de topologías. Agregue tantas entradas de SAN como necesite para los dominios SIP adicionales y las demás entradas que necesite admitir. El nombre del firmante se replica en el SAN y debe estar presente para que el funcionamiento sea correcto.</p></td>
</tr>
<tr class="even">
<td><p>Perímetro consolidado de un solo equipo (Perímetro interno)</p></td>
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


---
title: "Resumen de certif.: federación SIP, federación XMPP y mensajería instantánea pública"
TOCTitle: "Résumé des certif. - Fédération SIP, XMPP et messagerie instantanée publique"
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49115300
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de certificados: federación SIP, federación XMPP y mensajería instantánea pública

 

_**Última modificación del tema:** 2015-03-09_

Por lo general, los certificados que configure, solicite y asigne a su Servidor perimetral cumplirán los requisitos de los certificados que necesita para la federación con Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server.

Los requisitos de los certificados para habilitar y establecer comunicaciones con socios del protocolo extensible de mensajería y presencia (XMPP) requieren la adición de entradas para sus dominios XMPP. El registro incluido en el certificado como nombre alternativo del firmante (SAN) será el dominio que puede participar en las comunicaciones XMPP. El dominio puede ser el dominio de nivel de raíz (por ejemplo, contoso.com) si quiere habilitar XMPP para todo el dominio, o bien dominios secundarios seleccionados (por ejemplo, corp.contoso.com o finance.contoso.com) si quiere habilitar XMPP para un subconjunto de usuarios.

Al configurar certificados para la conectividad de la mensajería instantánea pública, debe saber que no hay nada que varíe respecto de otros tipos de federación SIP o, incluso, los certificados Servidor perimetral estándar, salvo por el hecho de que America Online (AOL) requiere que el certificado o los certificados (si se trata de un Grupo de servidores perimetrales) contengan también el EKU del cliente. El EKU del cliente se agrega al certificado y forma parte del certificado público externo asignado a su Servidor perimetral.

Para confirmar que cumple los requisitos de certificados correctos para su implementación de Servidor perimetral, consulte los temas indicados en la sección **Vea también**.



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componentes</th>
<th>Nombre del firmante</th>
<th>Nombres alternativos del firmante (SAN)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Perímetro de acceso/externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>
<div>

> [!NOTE]
> Para admitir el espacio de nombres de XMPP contoso.com


</div>
<p>sip.fabrikam.com</p>
<div>

> [!NOTE]
> Para admitir el espacio de nombres de SIP fabrikam.com


</div>
<p>fabrikam.com</p>
<div>

> [!NOTE]
> Para admitir el espacio de nombres de XMPP fabrikam.com


</div></td>
<td><p>El certificado debe provenir de una entidad de certificación pública y debe tener el EKU del servidor y el EKU del cliente si se va a implementar la conectividad de mensajería instantánea pública con AOL. El certificado se asigna a las interfaces externas de Servidor perimetral para:</p>
<ul>
<li><p>Servidor perimetral de acceso</p></li>
<li><p>Servicio perimetral de conferencia web</p></li>
<li><p>Servicio perimetral A/V</p></li>
</ul>
<div>

> [!NOTE]
> Técnicamente, no se asigna un certificado al perímetro A/V. La comunicación y la autenticación seguras se administran con el servicio de autenticación de relé multimedia (MRAS). MRAS usa el certificado asignado a la interfaz interna de Servidor perimetral.


</div>
<p>Tenga en cuenta que los SAN se agregan automáticamente al certificado a partir de las definiciones del Generador de topologías. Agregue tantas entradas de SAN como necesite para los dominios SIP adicionales y las demás entradas que necesite admitir. El nombre del firmante se replica en el SAN y debe estar presente para que el funcionamiento sea correcto.</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Tareas

[Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Conceptos

[Plan para certificados de servidores perimetrales en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Resumen de certificado - Servidor perimetral consolidado simple con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Resumen de certificado - Perímetro consolidado de equipo único con direcciones IP públicas en Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Resumen de certificado - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas con NAT en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  
[Resumen de certificado - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Resumen de certificado - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)


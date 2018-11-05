---
title: "Resumen de DNS: federación SIP, federación XMPP y mensajería instantánea pública"
TOCTitle: "Résumé des enr. DNS - Féd. SIP, XMPP et messagerie instantanée publique"
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49115273
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de DNS: federación SIP, federación XMPP y mensajería instantánea pública

 

_**Última modificación del tema:** 2017-03-09_

Los registros del sistema de nombre de dominio (DNS) que serán necesarios para definir una federación con socios de Office Communications Server o Lync Server quedan determinados por nuestra decisión de permitir la detección de DNS automática de su dominio por parte de otros posibles socios. Si publica el registro SRV \_sipfederationtls.\_tcp. *\<SIP domain name\>*, cualquier otro dominio federado SIP podrá “detectar” su federación. Puede controlar qué dominios federados pueden comunicarse con usted utilizando la configuración Permitir dominios y dominios bloqueados del Panel de control de Lync Server, o estableciendo la configuración Dominios permitidos o bloqueados utilizando el Shell de administración de Lync Server y los cmdlets de PowerShell **Get**, **Set**, **New**, **Remove-CsAllowedDomain** y **-CsBlockedDomain**. Para obtener más información sobre cómo configurar estos parámetros y sobre el uso de los cmdlets de PowerShell, consulte **Temas relacionados** al final de este tema.

La tabla de resumen de registros de DNS muestra las entradas necesarias para una federación abierta o que se pueda detectar. Si no desea implementar la Detección de federación, puede decidir no configurar el registro \_sipfederationtls.\_tcp. *\<SIP domain name\>*.

> [!IMPORTANT]  
> Hay escenarios específicos en los que debe utilizar el registro SRV _sipfederationtls._tcp. <em>&lt;nombre de dominio SIP&gt;</em>, pero no desea tener una federación que se pueda detectar. Una instancia de ese tipo es aquella en la que ha implementado movilidad para sus usuarios. La notificación de inserción de movilidad clearinghouse (PNCH) es un tipo especial de federación que se utiliza para clientes Microsoft Lync Mobile de Apple iPhone o iPad mediante el cliente Lync 2010 Mobile o Windows Phone mediante los clientes móviles Lync 2010 Mobile o Lync 2013. El registro SRV _sipfederationtls._tcp. <em>&lt;nombre de dominio SIP&gt;</em> se utiliza en el caso de movilidad y notificación de inserción. Para mitigar este problema y controlar su capacidad de ser detectado, desactive el parámetro <strong>Habilitar detección del dominio del socio</strong> para desactivar la detección.



Para configurar el Protocolo extensible de presencia y mensajería (XMPP) para su implementación, puede crear dos registros de sistemas de nombre de dominio (DNS) en un servidor DNS externo que resolverá los registros al Servidor perimetral de acceso de su Servidor perimetral o Grupo de servidores perimetrales.

Cuando se configura el Sistema de nombres de dominio (DNS) para la conectividad de mensajería instantánea, verá que la configuración que admite a los usuarios externos admitirá también la conectividad de mensajería instantánea pública. Si ya ha configurado el Servidor perimetral o el Grupo de servidores perimetrales, tendrá los registros DNS necesarios para admitir la conectividad de mensajería instantánea pública.

## Resumen DNS - Federación SIP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN</th>
<th>Dirección IP/registro de host FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externo/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Servidor perimetral de acceso interfaz externa necesaria para la detección de DNS automática de su federación a otros socios de federación potenciales y se conoce como “Dominios SIP permitidos” (denominado federación ampliada en versiones anteriores). Repetir las veces que sea necesario para todos los dominios SIP con usuarios habilitados en Lync</p>
<div>

> [!IMPORTANT]  
> Este registro SRV es necesario para la movilidad y la notificación de inserción clearinghouse. En los casos en que hay más de un dominio SIP, cree y publique un registro SRV para cada dominio que tendrá clientes de Lync Mobile. El Servicios de notificaciones de inserción y Servicios de notificaciones de inserción de Apple podrían no operar del modo esperado si no hay un registro SRV explícito para cada dominio SIP que admita la implementación.


</div></td>
</tr>
</tbody>
</table>


## Resumen de DNS - Protocolo extensible de mensajería y presencia (XMPP)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN</th>
<th>Dirección IP/Registro de host FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externo/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>La interfaz externa de proxy XMPP en el Servidor perimetral de acceso o Grupo de servidores perimetrales. Repetir la cantidad de veces que sea necesario para todos los dominios SIP internos con usuarios habilitados en Lync donde el contacto con contactos de XMPP está permitido mediante la configuración de la directiva de acceso externo a través de una directiva global, directiva de sitio en la que se ubica al usuario o directiva de usuario aplicada al usuario habilitado en Lync. Un dominio de XMPP permitido también debe configurarse en la directiva de socios federados de XMPP. Consulte los temas que se encuentran en <strong>Ver también</strong> para obtener más detalles.</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/A</p></td>
<td><p>xmpp.contoso.com (por ejemplo)</p></td>
<td><p>Dirección IP del Servidor perimetral de acceso en el Servidor perimetral o el Grupo de servidores perimetrales que hospeda el proxy de XMPP</p></td>
<td><p>Apunta al Servidor perimetral de acceso o al Grupo de servidores perimetrales que hospeda el servicio de proxy de XMPP. Normalmente el registro SRV que crea apuntará a este registro host (A o AAAA)</p></td>
</tr>
</tbody>
</table>


## Resumen de DNS – Conectividad de mensajería instantánea pública


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN/Registro DNS</th>
<th>Dirección IP/FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externo/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz de Servidor perimetral de acceso</p></td>
<td><p>Interfaz externa del Servidor perimetral de acceso (Contoso). Repita tantas veces como sea necesario para todos los dominios SIP con usuarios de Lync habilitados</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Tareas

[Configurar la federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configurar las notificaciones de inserción en Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  

#### Conceptos

[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  

#### Otros recursos

[Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)


---
title: 'Resumen de DNS: SIP, Federación XMPP y mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 253a00a07d1d76e77c9a753f6442151beda7c801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumen de DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-03-09_

Los registros del sistema de nombres de dominio (DNS) que se requerirán para definir una federación con Office Communications Server o los socios de Lync Server se determinan mediante la decisión de permitir la detección automática de DNS de su dominio por parte de otros asociados de perspectiva. Si publica el \_sipfederationtls. \_TCP. * \<Nombre\> de dominio SIP* Registro SRV, cualquier otro dominio federado SIP podrá "detectar" su Federación. Puede controlar qué dominios federados pueden comunicarse con usted mediante la configuración de dominios y dominios bloqueados en el panel de control de Lync Server o mediante la configuración de los dominios permitidos o bloqueados mediante el shell de administración de Lync Server y los cmdlets **Get**, **set**, **New**, **Remove-CsAllowedDomain** y **-CsBlockedDomain** de PowerShell. Para obtener información adicional acerca de cómo configurar estas opciones y el uso de los cmdlets de PowerShell, vea **temas relacionados** al final de este tema.

La tabla de resumen de registros de DNS muestra las entradas necesarias para una federación abierta o que se pueda detectar. Si no desea implementar la detección de Federación, puede decidir no configurar la \_sipfederationtls. \_TCP. Registro de *nombre\> de dominio SIP. \<*

<div>


> [!IMPORTANT]
> Hay escenarios específicos en los que debe tener el _sipfederationtls. _tcp. <EM> &lt;Nombre&gt; de dominio SIP</EM> Registro SRV, pero no desea tener una Federación reconocible. Una de estas instancias es donde se ha implementado la movilidad para los usuarios. El centro de notificaciones de inserción de movilidad (PNCH) es un tipo especial de Federación que se usa para clientes móviles de Microsoft Lync en Apple iPhone o iPad mediante el cliente móvil de Lync 2010 o Windows Phone con los clientes móviles de Lync 2010 Mobile o Lync 2013. El _sipfederationtls. _tcp. <EM> &lt;Nombre&gt; de dominio SIP</EM> El registro SRV se usa en el caso de la movilidad y la notificación de inserción. Para mitigar este problema y controlar la detectabilidad, desactive la opción <STRONG>Habilitar detección de dominio de socio</STRONG> para desactivar la detección.



</div>

Para configurar el protocolo extensible de mensajería y presencia (XMPP) para la implementación, debe crear dos registros del sistema de nombres de dominio (DNS) en un servidor DNS externo que resuelva los registros en el servicio perimetral de acceso del servidor perimetral o del grupo de servidores perimetrales.

Cuando configure el sistema de nombres de dominio (DNS) para la conectividad de mensajería instantánea pública, verá que la configuración que admite usuarios externos admitirá la conectividad de mensajería instantánea pública. Si ya ha configurado el servidor perimetral o el grupo de servidores perimetrales, debe tener los registros DNS necesarios para admitir la conectividad de mensajería instantánea pública.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>Resumen de DNS-Federación SIP, incluida la conectividad de mensajería instantánea pública


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/tipo/puerto</th>
<th>FQDN</th>
<th>Dirección IP/Registro de host FQDN</th>
<th>Enruta a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>La interfaz externa del servicio perimetral de acceso es necesaria para la detección automática de DNS de la Federación a otros posibles asociados de Federación y se conoce como "dominios SIP permitidos" (denominada Federación mejorada en versiones anteriores). Repetir según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</p>



> [!IMPORTANT]
> Este registro SRV es necesario para la movilidad y la notificación de inserción clearinghouse. En los casos en que haya más de un dominio SIP, cree y publique un registro SRV para cada dominio que vaya a tener clientes móviles de Lync. Es posible que el servicio de notificación de inserción y el servicio de notificación de inserción de Apple no funcionen según lo esperado si no hay un registro SRV explícito para cada dominio SIP que admita la implementación.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Resumen de DNS-protocolo extensible de mensajería y presencia (XMPP)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/tipo/puerto</th>
<th>FQDN</th>
<th>Dirección IP/Registro de host FQDN</th>
<th>Enruta a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5269 externo</p></td>
<td><p>_xmpp-server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interfaz externa de proxy XMPP en el servicio perimetral de acceso o el grupo de servidores perimetrales. Repita los pasos necesarios para todos los dominios SIP internos con los usuarios habilitados para Lync donde se permite el contacto con los contactos XMPP a través de la configuración de la Directiva de acceso externo a través de una directiva global, una directiva de sitio en la que se encuentra el usuario o la Directiva de usuario aplicada al Usuario habilitado para Lync. También debe configurarse un dominio XMPP permitido en la Directiva de socios federados XMPP. Vea los temas en <strong>vea también</strong> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>xmpp.contoso.com (por ejemplo)</p></td>
<td><p>Dirección IP del servicio perimetral de acceso en el servidor perimetral o el grupo de servidores perimetrales que hospedan el proxy XMPP</p></td>
<td><p>Señala el servicio perimetral de acceso o el grupo de servidores perimetrales que hospeda el servicio de proxy XMPP. Generalmente, el registro SRV que crea llevará a este registro de host (A o AAAA)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de la Federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configuración de notificaciones de inserción en Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinación de los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


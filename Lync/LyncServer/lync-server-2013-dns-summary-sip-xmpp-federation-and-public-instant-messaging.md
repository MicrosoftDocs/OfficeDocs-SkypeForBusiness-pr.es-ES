---
title: 'Resumen DNS: SIP, Federación XMPP y mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22b38fdb9e936df8b3fd148022acdbd857cdcfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumen DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-03-09_

Los registros del sistema de nombres de dominio (DNS) que se requerirán para definir una federación con Office Communications Server o los socios de Lync Server se determinan mediante la decisión de permitir la detección automática de DNS de su dominio por parte de otros asociados de la perspectiva. Si publicas el \_sipfederationtls. \_TCP. * \<Nombre\> de dominio SIP* SRV, cualquier otro dominio federado puede "descubrir" su Federación. Puede controlar qué dominios federados pueden comunicarse con usted mediante la configuración permite dominios y dominios bloqueados en el panel de control de Lync Server, o estableciendo la configuración de dominios permitidos o bloqueados mediante el shell de administración de Lync Server y el ** Get**, **set**, **New**, **Remove-CsAllowedDomain** y **-CsBlockedDomain** cmdlets de PowerShell. Para obtener más información sobre cómo configurar estas opciones de configuración y el uso de los cmdlets de PowerShell, consulte **temas relacionados** al final de este tema.

La tabla de Resumen de registros DNS muestra las entradas necesarias para una federación abierta o reconocible. Si no desea implementar la detección de Federación, puede decidir no configurar la \_sipfederationtls. \_TCP. Registro de *nombre\> de dominio de SIP. \<*

<div>


> [!IMPORTANT]
> Hay escenarios específicos en los que debe tener el _sipfederationtls. _ TCP. <EM> &lt;Nombre&gt; de dominio SIP</EM> SRV, pero no desea tener una federación que se pueda descubrir. Una de estas instancias es donde ha implementado la movilidad para sus usuarios. El centro de notificaciones de inserción de movilidad (PNCH) es un tipo especial de Federación que se usa para clientes móviles de Microsoft Lync en Apple iPhone o iPad con el cliente móvil Lync 2010 o Windows Phone usando los clientes móviles Lync 2010 Mobile o Lync 2013. _Sipfederationtls. _ TCP. <EM> &lt;Nombre&gt; de dominio SIP</EM> El registro SRV se usa en el caso de la movilidad y la notificación push. Para mitigar este problema y controlar su detectabilidad, desactive la opción <STRONG>Habilitar detección de dominios asociados</STRONG> para desactivar la detección.



</div>

Para configurar el protocolo de presencia y mensajería extensible (XMPP) para su implementación, debe crear dos registros del sistema de nombres de dominio (DNS) en un servidor DNS externo que resuelva los registros para el servicio perimetral de acceso de su servidor perimetral o de grupo perimetral.

Al configurar el sistema de nombres de dominio (DNS) para la conectividad de mensajería instantánea pública, verá que la configuración que admite usuarios externos admite la conectividad de mensajería instantánea pública. Si ya ha configurado el servidor perimetral o el grupo Edge, debe tener los registros DNS necesarios para admitir la conectividad de mensajería instantánea pública.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>Resumen DNS: Federación SIP, incluida la conectividad de mensajería instantánea pública


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
<th>Dirección IP/registro de host FQDN</th>
<th>Se asigna a/comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externo/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Servicio perimetral de acceso interfaz externa necesaria para la detección automática de DNS de su Federación a otros posibles socios de Federación, y se conoce como "dominios SIP permitidos" (denominada Federación mejorada en versiones anteriores). Repetir según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</p>



> [!IMPORTANT]
> Este registro SRV es necesario para la movilidad y el centro de enrutamiento de notificaciones de inserción. En los casos en que haya más de un dominio SIP, cree y publique un registro SRV para cada dominio que vaya a tener clientes móviles de Lync. Es posible que el servicio de notificaciones de inserción y el servicio de notificaciones push de Apple no funcionen según lo esperado si no hay un registro SRV explícito para cada dominio SIP compatible con la implementación.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Resumen de DNS: Protocolo de presencia y mensajería extensible (XMPP)


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
<th>Dirección IP/registro de host FQDN</th>
<th>Se asigna a/comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5269 externo</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interfaz externa de proxy XMPP en el servicio perimetral de acceso o grupo perimetral. Repita el procedimiento según sea necesario para todos los dominios SIP internos con los usuarios habilitados para Lync donde se permite el contacto con los contactos XMPP a través de la configuración de la Directiva de acceso externo a través de una directiva global, una directiva de sitio donde se encuentra el usuario o la Directiva de usuario aplicada al Usuario habilitado para Lync. También se debe configurar un dominio XMPP permitido en la Directiva del socio XMPP federado. Vea temas en <strong>vea también</strong> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/A</p></td>
<td><p>xmpp.contoso.com (por ejemplo)</p></td>
<td><p>Dirección IP del servicio perimetral de acceso en el servidor perimetral o grupo perimetral que aloja el proxy XMPP</p></td>
<td><p>Señala el servicio perimetral de Access o el grupo de límites que alberga el servicio de proxy XMPP. Normalmente, el registro SRV que cree apuntará a este registro de host (A o AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar la federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configurar las notificaciones de inserción en Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


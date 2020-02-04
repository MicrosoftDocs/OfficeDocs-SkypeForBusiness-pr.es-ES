---
title: 'Lync Server 2013: Administración de la federación y el acceso externo a Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dadc455389d95c91996b75928def8f03b06c64e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Administración de la federación y el acceso externo a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

Implementar un servidor perimetral o un grupo perimetral es el primer paso para admitir usuarios externos. Para obtener detalles sobre la implementación de servidores perimetrales, consulte [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación.

Después de instalar y configurar la implementación interna de Lync Server 2013, los usuarios internos de la organización pueden colaborar con otros usuarios internos que tengan cuentas SIP en los servicios de dominio de Active Directory (AD DS). La colaboración puede incluir el envío y la recepción de mensajes instantáneos, así como la actualización del estado de presencia y la participación en conferencias (también conocidas como "reuniones"). Puede habilitar y configurar el acceso de usuarios externos para controlar si los usuarios externos compatibles pueden colaborar con usuarios internos de Lync Server. Los usuarios externos pueden incluir usuarios remotos de su implementación, usuarios federados (incluidos los usuarios admitidos de proveedores de servicios de mensajería instantánea pública (mi)), Federación XMPP y participantes anónimos en conferencias.

Si su implementación incluía la instalación de un servidor perimetral 2013 de Lync Server o un grupo Edge, el ámbito de los posibles tipos de comunicación se ha ampliado enormemente con varias opciones para el acceso de usuarios externos, la comunicación con miembros de otros dominios federados SIP. Proveedores federados SIP y de XMPP usuarios federados. Después de configurar el servidor perimetral o el grupo perimetral, habilite los tipos de acceso de usuarios externos que desea proporcionar y configure las directivas para controlar el acceso externo. En Lync Server 2013, puede habilitar y configurar directivas y acceso a usuarios externos con el panel de control de Lync Server, el shell de administración de Lync Server o ambos, en función de los requisitos de la tarea. Para obtener más información sobre estas herramientas de administración, vea [herramientas administrativas de Lync server 2013](lync-server-2013-lync-server-administrative-tools.md) en la documentación de operaciones, [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) en la documentación de operaciones e [Instale las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md) en la documentación de operaciones.

<div>


> [!IMPORTANT]  
> Al diseñar la configuración y las directivas para el acceso de usuarios externos, debe comprender la prioridad de las directivas y cómo se aplican las directivas. La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.



</div>

De forma predeterminada, ninguna directiva está configurada para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad de acceso de usuarios externos para su organización. Para controlar el uso del acceso de usuarios externos, debe configurar una o más directivas, especificando el tipo de acceso de usuarios externos admitido para cada Directiva. Esto incluye las siguientes directivas de acceso externo:

  - **Directiva global se**   crea la directiva global al implementar los servidores perimetrales. De forma predeterminada, no hay ninguna opción de acceso de usuario externo habilitada en la directiva global. Para admitir el acceso de usuarios externos en el nivel global, configure la directiva global para que admita uno o varios tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de la organización, pero las directivas del sitio y las directivas de usuario invalidan la directiva global. Si elimina la directiva global, no la quitará. En su lugar, lo restablecerá a la configuración predeterminada.

  - **Directiva de sitio**   puede crear y configurar una o varias directivas de sitio para limitar la compatibilidad con el acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico. De forma predeterminada, se aplica una directiva de sitio a todos los usuarios de ese sitio, pero puede asignar una directiva de usuario a un usuario para que anule la configuración de directiva de sitio.

  - **Directiva de usuario**   puede crear y configurar una o más directivas de usuario para limitar la compatibilidad del acceso de usuarios remotos a usuarios específicos. La configuración de la Directiva de usuario reemplaza la directiva global y la de sitio, pero solo para los usuarios específicos a los que se asigna la Directiva de usuario. Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global y la Directiva de sitio, puede especificar una directiva de usuario que deshabilite el acceso de usuarios remotos y, a continuación, asignar esa Directiva de usuario a usuarios específicos. Si crea una directiva de usuario, debe aplicarla a uno o más usuarios para que tenga efecto.

Para determinar qué opciones de configuración y qué directivas necesita crear o editar, consulte los siguientes puntos de decisión:

**¿Desea permitir que los usuarios internos y externos de su dominio puedan colaborar con la mensajería instantánea, las conferencias web y el audio/vídeo?**

Configure las opciones que se detallan en los temas [configurar directivas para controlar el acceso de usuarios remotos en Lync server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md), y [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**¿Desea permitir que los usuarios anónimos asistan e inviten a conferencias hospedadas por los usuarios de su implementación?**

Configure las opciones que se detallan en el tema [asignar directivas de conferencia para admitir usuarios anónimos en Lync server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [crear o modificar una directiva de conferencia en la referencia de](lync-server-2013-create-or-modify-a-conferencing-policy.md) configuración de directiva de conferencia de Lync Server 2013 [para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**¿Desea permitir que los usuarios se comuniquen con los contactos de dominios federados de SIP?**

Configure las opciones que se detallan en los temas [configurar directivas para controlar el acceso de usuarios federados en Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), y [administrar los dominios federados SIP para su organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**Si ha habilitado la comunicación con dominios de Federación SIP, ¿desea habilitar las comunicaciones con los contactos del socio XMPP federado?**

Configure las opciones tal y como se detalla en el tema [configurar directivas para controlar el acceso de usuarios de XMPP federado en Lync server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) y [administrar los socios de XMPP federados en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Si ha habilitado la comunicación con dominios federados SIP, ¿desea habilitar la detección automática de la Federación SIP?**

Configure las opciones que se detallan en el tema [habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

**Si ha habilitado la comunicación con dominios de Federación SIP, ¿desea habilitar el envío de un aviso de declinación de responsabilidades a los contactos federados para notificarles que usa el archivado y que las comunicaciones pueden archivarse?**

Configure las opciones que se detallan en el tema [habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**¿Desea permitir que los usuarios se comuniquen con proveedores federados SIP que permitan la comunicación con proveedores públicos, como Windows Live Messenger, AOL y\!Yahoo?**

Configure las opciones que se detallan en los temas [configurar directivas para controlar el acceso de usuarios públicos en Lync server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), así como [crear o editar proveedores federados SIP públicos en Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de fin de vida de junio de 2014 para AOL y Yahoo! ha sido anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo! Mensajería. La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard. La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</P></LI></UL>



</div>

**¿Desea permitir que los usuarios se comuniquen con proveedores federados SIP que sean proveedores alojados que ejecuten Microsoft Office 365, Microsoft Lync Online y Microsoft Lync Online 2010?**

Configure las opciones que se detallan en los temas [crear o editar proveedores federados de SIP públicos en Lync server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) y [crear o editar los proveedores federados de SIP federados Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**¿La implementación está configurada en un dominio dividido (también conocido como híbrido), en el que algunos usuarios tienen su servidor principal en una implementación local y otros usuarios están configurados con un servidor principal en un entorno en línea?**

Configure las opciones que se detallan en los temas [configurar directivas para controlar el acceso de usuarios federados en Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) y [crear o editar Lync Server 2013 de proveedores federados](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

Si prefiere una tabla que Enumere los requisitos:


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Ficha en Federación y acceso externo (en la) Federación o tipo de acceso externo (abajo)</th>
<th>Directiva de acceso externo</th>
<th>Configuración de Edge de Access</th>
<th>Dominios federados SIP</th>
<th>Proveedores de SIP federados</th>
<th>Socio XMPP federado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuarios remotos</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Contactos federados SIP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Administrar dominios federados SIP para la organización en Lync Server 2013</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Los contactos federados de XMPP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Administrar socios federados XMPP para su organización en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Dividir dominio/usuarios híbridos</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Crear o editar proveedores federados de SIP hospedados en Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contactos del servicio de mensajería instantánea pública</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Acceso de usuarios anónimos a reuniones y conferencias</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013</a></p>
<div>

> [!NOTE]  
> También debe tener en cuenta las siguientes opciones de configuración en directivas de Conferencia: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">crear o modificar una directiva de conferencia en Lync server 2013</A> y <A href="lync-server-2013-conferencing-policy-settings-reference.md">referencia de configuración de directiva de conferencia para Lync Server 2013</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Puede configurar la configuración de acceso de usuarios externos, incluidas las directivas que desee usar para controlar el acceso de usuarios externos, incluso si no ha habilitado el acceso de usuarios externos para su organización. Sin embargo, las directivas y otras opciones de configuración que se configuran solo estarán vigentes cuando tenga habilitado el acceso de usuarios externos a su organización. Los usuarios externos no pueden comunicarse con los usuarios de su organización cuando el acceso de usuarios externos está deshabilitado o si ninguna directiva de acceso de usuarios externos está configurada para admitirlo.

La implementación de Edge autentica los tipos de usuarios externos (excepto para los usuarios anónimos, que son autenticados por el identificador de conferencia y una clave de paso que se envía al participante anónimo al crear la Conferencia e invitar a participantes) y controles acceso según la configuración de la compatibilidad de los extremos. Para controlar las comunicaciones, puede configurar una o varias directivas y configurar opciones que definan cómo los usuarios de dentro y fuera de la implementación se comunican entre sí. Las directivas y la configuración incluyen la directiva global predeterminada para el acceso de usuarios externos, además de las directivas de sitio y de usuario que puede crear y configurar para habilitar uno o varios tipos de acceso de usuarios externos para determinados sitios o usuarios.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Administrar la directiva de acceso de la organización en Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Administrar la configuración perimetral de acceso para su organización en Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Configuración de la compatibilidad de Federación para un cliente de Lync Online en Lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


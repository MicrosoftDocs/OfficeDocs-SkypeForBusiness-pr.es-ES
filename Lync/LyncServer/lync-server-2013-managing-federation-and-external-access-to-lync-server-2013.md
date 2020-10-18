---
title: 'Lync Server 2013: administración de la Federación y el acceso externo a Lync Server 2013'
description: 'Lync Server 2013: administración de la Federación y el acceso externo a Lync Server 2013.'
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
ms.openlocfilehash: d1d389c7490fd1884631ed2fc184d590eb42141b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574926"
---
# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Administración de la Federación y el acceso externo a Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-07_

La implementación de un servidor perimetral o de un grupo de servidores perimetrales es el primer paso para la compatibilidad con usuarios externos. Para obtener más información sobre la implementación de servidores perimetrales, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación.

Después de instalar y configurar la implementación interna de Lync Server 2013, los usuarios internos de la organización pueden colaborar con otros usuarios internos que tengan cuentas SIP en los servicios de dominio de Active Directory (AD DS). La colaboración puede incluir el envío y recepción de mensajes instantáneos, y la actualización del estado de presencia y la participación en conferencias (también denominadas "reuniones"). Puede habilitar y configurar el acceso de usuarios externos para controlar si los usuarios externos admitidos pueden colaborar con los usuarios internos de Lync Server. Los usuarios externos pueden englobar usuarios remotos de su implementación, usuarios federados (incluidos los usuarios admitidos de los proveedores de servicios públicos de mensajería instantánea), federación XMPP y participantes anónimos de las conferencias.

Si la implementación incluye la instalación de un servidor perimetral de Lync Server 2013 o un grupo de servidores perimetrales, el ámbito de los tipos de comunicación posibles se amplía en gran medida con una serie de opciones para el acceso de usuarios externos, la comunicación con miembros de otros dominios federados SIP, los proveedores federados SIP y los usuarios federados XMPP. Después de configurar el servidor perimetral o el grupo de servidores perimetrales, habilite los tipos de acceso de usuarios externos que desea proporcionar y configure las directivas para controlar el acceso externo. En Lync Server 2013, habilite y configure las directivas y el acceso de usuarios externos mediante el panel de control de Lync Server, el shell de administración de Lync Server o ambos, en función de los requisitos de la tarea. Para obtener más información sobre estas herramientas de administración, consulte [herramientas administrativas de Lync server 2013](lync-server-2013-lync-server-administrative-tools.md) en la documentación de operaciones, el [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) en la documentación de operaciones e [Instale Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md) en la documentación de operaciones.

<div>


> [!IMPORTANT]  
> Al diseñar las directivas y la configuración para el acceso de usuario externo, debe comprender la prioridad de las directivas y la manera en que se aplican las directivas. La configuración de la Directiva de Lync Server que se aplica en un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.



</div>

De forma predeterminada, no se configura ninguna directiva para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos y el acceso de usuarios federados, incluso aunque se haya habilitado el acceso de usuarios externos en la organización. Para controlar el acceso de usuarios externos, debe configurar una o más directivas en las que se defina el tipo de acceso de usuario externo que se va a admitir. Algunas de esas directivas son las siguientes:

  - **Directiva global**   La directiva global se crea cuando se implementan los servidores Edge. De forma predeterminada, no hay habilitadas opciones de acceso de usuarios externos en la directiva global. Para admitir el acceso de usuarios externos en el nivel global, debe configurar la directiva global para que admita uno o más tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de su organización, pero las directivas de sitio y usuario invalidan la directiva global. Eliminar la directiva global no hará que desaparezca. En lugar de eso, se restablece la configuración predeterminada.

  - **Directiva de sitio**   Puede crear y configurar una o más directivas de sitio para limitar el acceso de usuarios externos a determinados sitios. La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva. Por ejemplo, si activa el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico. De forma predeterminada, una directiva de sitio se aplica a todos los usuarios de dicho sitio, aunque puede asignar una directiva de usuario a un usuario determinado para invalidar dicho parámetro de la directiva de sitio.

  - **Directiva de usuario**   Puede crear y configurar una o más directivas de usuario para limitar el acceso de usuarios remotos a determinados usuarios. La configuración de la directiva de usuario invalida la directiva global y la directiva de sitio, pero solo para los usuarios concretos a los que se ha asignado la directiva de usuario. Por ejemplo, si deshabilita el acceso de usuarios remotos en la directiva global y a la directiva de sitio, puede especificar una directiva de usuario para deshabilitar el acceso de usuarios remotos y, a continuación, asignar dicha directiva de usuario a usuarios específicos. Si crea una directiva de sitio, debe aplicarla a uno o más usuarios antes de que se haga efectiva.

Para determinar qué valores de configuración y qué directivas tiene que crear o editar, consulte los siguientes puntos de decisión:

**¿Desea permitir que los usuarios internos y externos de su dominio puedan colaborar mediante la mensajería instantánea, conferencia web y audio/vídeo?**

Configure las opciones tal y como se detalla en los temas [Configure Policies to control remote User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)y [enable or Disable Federation and Public im Connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**¿Desea permitir que los usuarios anónimos asistan y sean invitados a conferencias hospedadas por usuarios en su implementación?**

Configure las opciones tal y como se detalla en el tema [asignar directivas de conferencia para admitir usuarios anónimos en Lync server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [crear o modificar una directiva de conferencia en Lync Server 2013 y la](lync-server-2013-create-or-modify-a-conferencing-policy.md) [referencia de configuración de directivas de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**¿Desea permitir a los usuarios que se comuniquen con contactos de dominio federados SIP?**

Configure las opciones tal y como se detalla en los temas [Configure Policies to control Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)y [administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**Si ha habilitado la comunicación con los dominios de federación SIP, ¿desea habilitar las comunicaciones con los contactos de socios federados XMPP?**

Configure los valores como se detalla en el tema [Configure Policies to control XMPP Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) y [Manage XMPP Federated Partners en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Si ha habilitado la comunicación con los dominios federados SIP, ¿desea habilitar la detección automática de la Federación SIP?**

Configure los valores como se detalla en el tema [enable or Disable Discovery of Federation Partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

**Si ha habilitado la comunicación con dominios de federación SIP, ¿desea habilitar el envío de una declinación de responsabilidades a contactos federados notificándoles que usa el archivado y que las comunicaciones se pueden archivar?**

Configure los valores como se detalla en el tema [habilitar o deshabilitar el envío de una declinación de responsabilidades de archivado a socios federados en Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**¿Desea permitir que los usuarios se comuniquen con los proveedores federados SIP que permitan la comunicación con proveedores públicos, como Windows Live Messenger, AOL y Yahoo \! ?**

Configure las opciones como se detalla en los temas [Configure Policies to control Public User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)y [crear o editar proveedores federados de SIP públicos en Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación. Los clientes con licencias activas podrán seguir federando a Yahoo! Messenger hasta que se cierre la fecha del servicio. Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo! se ha anunciado. Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</P>
> <LI>
> <P>La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo! Service. La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</P>
> <LI>
> <P>Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo. La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard. La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</P></LI></UL>



</div>

**¿Desea permitir que los usuarios se comuniquen con los proveedores federados SIP que son proveedores hospedados que ejecutan Microsoft 365, Microsoft Lync Online y Microsoft Lync Online 2010?**

Configure los valores como se detalla en los temas [crear o editar proveedores federados de SIP públicos en Lync server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) y [crear o editar proveedores federados SIP federados Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**¿Está su implementación configurada en un dominio dividido (también conocido como híbrido), donde algunos usuarios tienen su servidor principal en una implementación local y otros usuarios se configuran con un servidor principal en un entorno en línea?**

Configure las opciones tal y como se detalla en los temas [Configure Policies to control Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) y [crear o editar proveedores asociados federados de SIP hospedados Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

Si prefiere una tabla que enumera los requisitos:


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
<th>Pestaña en Federación y acceso externo (Across) Federación o tipo de acceso externo (abajo)</th>
<th>Directiva de acceso externo</th>
<th>Configuración perimetral de acceso</th>
<th>Dominios federados SIP</th>
<th>Proveedores federados SIP</th>
<th>Socio federado XMPP</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuarios remotos</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurar directivas para controlar el acceso de usuarios remotos en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Contactos federados SIP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Habilitar o deshabilitar el envío de una declinación de responsabilidades de archivado a socios federados en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Administrar dominios federados SIP para la organización en Lync Server 2013</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contactos federados XMPP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Administrar socios federados XMPP en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Dominio dividido / Usuarios híbridos</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Creación o edición de proveedores federados de SIP hospedados Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contactos de servicio de mensajería instantánea pública</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</a></p></td>
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
> También debe tener en cuenta las siguientes opciones de configuración en directivas de Conferencia: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">crear o modificar una directiva de conferencia en Lync server 2013 y la</A> <A href="lync-server-2013-conferencing-policy-settings-reference.md">referencia de configuración de directivas de conferencia para Lync Server 2013</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Puede configurar parámetros de acceso de usuarios externos, incluidas las directivas que desea usar para controlar el acceso de usuarios externos, aunque no haya habilitado el acceso de usuarios externos en su organización. Sin embargo, tanto las directivas como otros parámetros que se configuran solo son efectivos cuando se habilita el acceso de usuarios externos en su organización. Los usuarios externos no pueden comunicarse con usuarios de su organización cuando el acceso de usuarios externos está deshabilitado o no se han configurado directivas de acceso de usuarios externos para admitir dichas comunicaciones.

La implementación perimetral sirve para autenticar los tipos de usuarios externos (excepto los usuarios anónimos, que se autentican mediante el Id. de conferencia y una contraseña que se envía al participante anónimo cuando se crea la conferencia y se invita a los participantes) y controlar el acceso según cómo se haya configurado la compatibilidad perimetral. Para controlar las comunicaciones, puede configurar una o más directivas y otros parámetros que sirvan para definir el modo en que se comunican los usuarios de dentro y fuera de la implementación. Eso incluye la directiva global predeterminada para el acceso de usuarios externos, además de las directivas de sitio y usuario que puede crear y configurar para habilitar uno o más tipos de acceso de usuarios externos para sitios o usuarios específicos.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Administrar la Directiva de acceso externo en Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Administrar la configuración perimetral de acceso para su organización en Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Administrar socios federados XMPP en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Configuración de la compatibilidad de Federación para un cliente de Lync Online en Lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


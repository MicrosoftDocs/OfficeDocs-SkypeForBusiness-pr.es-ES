---
title: "Lync Server 2013: Administrar la federación y el acceso externo a Lync Server 2013"
TOCTitle: Administración de la federación y el acceso externo a Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48274731
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administración de la federación y el acceso externo a Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La implementación de un servidor perimetral o de un grupo de servidores perimetrales es el primer paso para la compatibilidad con usuarios externos. Para obtener más información sobre la implementación de servidores perimetrales, consulte [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación.

Tras instalar y configurar la implementación interna de Lync Server 2013, los usuarios internos de la organización pueden trabajar en colaboración con otros usuarios internos que tengan cuentas SIP en los servicios de dominio de Active Directory (AD DS). La colaboración puede incluir el envío y recepción de mensajes instantáneos, y la actualización del estado de presencia y la participación en conferencias (también denominadas "reuniones"). El acceso de usuarios externos se configura para controlar si los usuarios externos admitidos pueden colaborar con usuarios internos de Lync Server. Los usuarios externos pueden englobar usuarios remotos de su implementación, usuarios federados (incluidos los usuarios admitidos de los proveedores de servicios públicos de mensajería instantánea), federación XMPP y participantes anónimos de las conferencias.

Si su implementación incluía la instalación de un Lync Server 2013  Servidor perimetral o un Grupo de servidores perimetrales, el ámbito de posibles tipos de comunicación se expande en gran medida con varias opciones para el acceso de usuarios externos, la comunicación con miembros de otros dominios federados SIP, proveedores federados SIP y usuarios federados XMPP. Tras configurar el Servidor perimetral o Grupo de servidores perimetrales, habilita los tipos de acceso de usuario externo que desea proporcionar y configura las directivas para controlar el acceso externo. En Lync Server 2013, habilita y configura el acceso de usuario externo y las directivas usando el Panel de control de Lync Server, el Shell de administración de Lync Server o ambos, en función de los requisitos de tareas. Para obtener detalles acerca de estas herramientas de administración, vea [Herramientas administrativas de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md) en la documentación de operaciones, [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md) en la documentación de operaciones y [Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md) en la documentación de operaciones.

> [!IMPORTANT]  
> Al diseñar las directivas y la configuración para el acceso de usuario externo, debe comprender la prioridad de las directivas y la manera en que se aplican las directivas. La configuración de directiva de Lync Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva de Lync Server es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.



De forma predeterminada, no se configura ninguna directiva para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos y el acceso de usuarios federados, incluso aunque se haya habilitado el acceso de usuarios externos para la organización. Para controlar el acceso de usuarios externos, debe configurar una o más directivas en las que se defina el tipo de acceso de usuario externo que se va a admitir para cada directiva. Algunas de esas directivas son las siguientes:

  - **Directiva global**   La directiva global se crea al implementar los servidores perimetrales. De forma predeterminada, no hay opciones de acceso de usuarios externos habilitadas en la directiva global. Para admitir el acceso de usuarios externos a nivel global, configure la directiva global para admitir uno o más tipos de opciones de acceso de usuarios externos. La directiva global se aplica a todos los usuarios de la organización, pero las directivas de sitio y las directivas de usuario reemplazan a la directiva global. Si elimina la directiva global, no se quita. En su lugar, se restablece la configuración predeterminada.

  - **Directiva de sitio**   Puede crear y configurar uno o varias directivas de sitio para limitar la compatibilidad de acceso de usuarios externos a sitios específicos. La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio. Por ejemplo, si se habilita el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos a un sitio específico. De forma predeterminada, una directiva de sitio se aplica a todos los usuarios de dicho sitio, aunque puede asignar una directiva de usuario a un usuario determinado para cambiar dicho parámetro de la directiva de sitio.

  - **Directiva de usuario**   Puede crear y configurar uno o varias directivas de sitio para limitar la compatibilidad de acceso de usuarios remotos a sitios específicos. La configuración de la directiva de usuario reemplaza la directiva global y la directiva de sitio, pero solo para los usuarios específicos a quienes se le asigna la directiva de sitio. Por ejemplo, si se habilita el acceso de usuarios remotos en la directiva global y en la directiva de sitio, puede especificar una directiva de usuario que deshabilite el acceso de usuarios remotos y luego asigne esa directiva de usuario a un usuario específico. Si crea una directiva de sitio, debe aplicarla a uno o más usuarios antes de que se haga efectiva.

Para determinar qué valores de configuración y qué directivas tiene que crear o editar, consulte los siguientes puntos de decisión:

**¿Desea permitir que los usuarios internos y externos de su dominio puedan colaborar mediante la mensajería instantánea, conferencia web y audio/vídeo?**

Configure los valores como se detalla en los temas [Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) y [Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**¿Desea permitir que los usuarios anónimos asistan y sean invitados a conferencias hospedadas por usuarios en su implementación?**

Configure los valores como se detalla en el tema [Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [Creación o modificación de una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) y [Referencia de configuración de directivas de conferencias en Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**¿Desea permitir a los usuarios que se comuniquen con contactos de dominio federados SIP?**

Configure los valores como se detalla en el tema [Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) y [Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**Si ha habilitado la comunicación con los dominios de federación SIP, ¿desea habilitar las comunicaciones con los contactos de socios federados XMPP?**

Configure los valores como se detalla en el tema [Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) y [Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Si ha habilitado la comunicación con los dominios federados SIP, ¿desea habilitar la detección automática de federación SIP?**

Configure los valores según se detalla en el tema [Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

**Si ha habilitado la comunicación con dominios de federación SIP, ¿desea habilitar el envío de una declinación de responsabilidades a contactos federados notificándoles que usa el archivado y que las comunicaciones se pueden archivar?**

Configure los valores según se detalla en el tema [Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**¿Desea permitir a los usuarios que se comuniquen con los proveedores federados SIP que habilitan la comunicación con proveedores públicos, como Windows Live Messenger, AOL y Yahoo\!?**

Configure los valores como se detalla en los temas [Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) y [Crear o editar proveedores federados de SIP públicos en Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).

> [!IMPORTANT]  
> <ul>
> <li><p>El 1 de septiembre de 2012, la licencia de suscripción del usuario de Public IM Connectivity de Microsoft Lync (&quot;PIC USL&quot;) dejó de estar disponible para su compra en los contratos nuevos y en las prórrogas de contratos. Los clientes que tengan licencias activas podrán seguir federándose con Yahoo! Messenger hasta la fecha de cierre del servicio. La fecha anunciada para el fin de vida de AOL y Yahoo! es junio de 2014. Para más detalles, vea <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Soporte para la conectividad de mensajería instantánea pública en Lync Server 2013</a>.</p></li>
> <li><p>PIC USL es una licencia de suscripción por usuario/por mes requerida por Lync Server u Office Communications Server para la federación con Yahoo! Messenger. La posibilidad de Microsoft de proporcionar este servicio depende de la compatibilidad con Yahoo!, cuyo contrato subyacente está llegando a su fin.</p></li>
> <li><p>Hoy más que nunca, Lync es una herramienta eficaz para conectarse dentro de una organización y con individuos de todo el mundo. La federación con Windows Live Messenger no requiere ninguna licencia de usuario o dispositivo adicional aparte de la CAL estándar de Lync. La federación con Skype se agregará a esta lista, lo que permitirá a los usuarios de Lync conectarse con cientos de millones de personas a través de mensajería instantánea y voz.</p></li>
> </ul>


**¿Desea permitir a los usuarios que se comuniquen con los proveedores federados SIP que son proveedores hospedados que ejecutan Microsoft Office 365, Microsoft Lync Online y Microsoft Lync Online 2010?**

Configure los valores según se detalla en los temas [Crear o editar proveedores federados de SIP públicos en Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) y [Crear o editar proveedores federados de SIP hospedados en Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**¿Está su implementación configurada en un dominio dividido (también conocido como híbrido), donde algunos usuarios tienen su servidor principal en una implementación local y otros usuarios se configuran con un servidor principal en un entorno en línea?**

Configure los valores según se detalla en los temas [Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) y [Crear o editar proveedores federados de SIP hospedados en Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

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
<th>Pestaña en federación y acceso externo (horizontal) Federación o tipo de acceso externo (vertical descendente)</th>
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
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Contactos federados SIP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</a></p>
<p></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Administrar dominios federados SIP para la organización en Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Contactos federados XMPP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Administrar socios federados XMPP para su organización en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Dominio dividido / Usuarios híbridos</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Crear o editar proveedores federados de SIP hospedados en Lync Server 2013</a></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Contactos de servicio de mensajería instantánea pública</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</a></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Acceso de usuarios anónimos a reuniones y conferencias</p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Asignar directivas de conferencia para admitir usuarios anónimos en Lync Server 2013</a></p>
<div>

> [!NOTE]
> También debe tener en cuenta los siguientes valores de configuración bajo las directivas de conferencia: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Creación o modificación de una directiva de conferencia en Lync Server 2013</A> y <A href="lync-server-2013-conferencing-policy-settings-reference.md">Referencia de configuración de directivas de conferencias en Lync Server 2013</A>


</div></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


Puede configurar parámetros de acceso de usuarios externos, incluidas las directivas que desea usar para controlar el acceso de usuarios externos, aunque no haya habilitado el acceso de usuarios externos en su organización. Sin embargo, tanto las directivas como otros parámetros que se configuran solo son efectivos cuando se habilita el acceso de usuarios externos en su organización. Los usuarios externos no pueden comunicarse con usuarios de su organización cuando el acceso de usuarios externos está deshabilitado o no se han configurado directivas de acceso de usuarios externos para admitir dichas comunicaciones.

La implementación perimetral sirve para autenticar los tipos de usuarios externos (excepto los usuarios anónimos, que se autentican mediante el Id. de conferencia y una contraseña que se envía al participante anónimo cuando se crea la conferencia y se invita a los participantes) y controlar el acceso según cómo se haya configurado la compatibilidad perimetral. Para controlar las comunicaciones, puede configurar una o más directivas y otros parámetros que sirvan para definir el modo en que se comunican los usuarios de dentro y fuera de la implementación. Eso incluye la directiva global predeterminada para el acceso de usuarios externos, además de las directivas de sitio y usuario que puede crear y configurar para habilitar uno o más tipos de acceso de usuarios externos para sitios o usuarios específicos.

## En esta sección

  - [Administrar la directiva de acceso de la organización en Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Administrar la configuración perimetral de acceso para su organización en Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Configuración de la compatibilidad de federación para un cliente de Lync Online en Lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)


---
title: 'Lync Server 2013: Configuraciones híbridas admitidas'
TOCTitle: Configuraciones híbridas admitidas
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945633(v=OCS.15)
ms:contentKeyID: 52061688
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuraciones híbridas admitidas de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Puede configurar las implementaciones de Lync Server 2013 para la integración de Microsoft Exchange Server 2010 y Microsoft Exchange Server 2013 con SharePoint Server, tanto en línea como de forma local. Las características que se enumeran en la siguiente tabla son compatibles con todos los clientes, a menos que se especifique lo contrario. Si desea más información sobre la compatibilidad de clientes, consulte [Tablas de comparación de clientes para Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) y las tablas de comparación de clientes de Lync Online en [Clientes para Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902).

## Integración con Exchange Server

En la siguiente tabla se enumeran las características admitidas en una implementación híbrida cuando está integrada con Microsoft Exchange Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Exchange local</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 local</strong></p></td>
<td><ul>
<li><p>Mensajería instantánea y presencia en Outlook</p>
<p>Para obtener más información, vea <a href="lync-server-2013-im-and-presence.md">Mensajería instantánea (MI) y presencia en Lync Server 2013</a></p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p>
<p>Para obtener más información, vea <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integración de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013</a></p></li>
<li><p>Mensajería instantánea y presencia en Outlook Web App</p>
<p>Para obtener más información, vea <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Configuración de Microsoft Lync Server 2013 en un entorno externo</a></p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook Web App</p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>Unirse a reuniones en línea en clientes móviles</p>
<p>Para obtener más información, vea <a href="lync-server-2013-deploying-mobility.md">Implementar la movilidad en Lync Server 2013</a></p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>Lista de contactos (mediante el almacén de contactos unificado)</p>
<p>Para obtener más información, vea <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuración de Microsoft Lync Server 2013 para usar el almacén de contactos unificado</a></p>
<div>

> [!NOTE]
> Requiere Exchange 2013.<BR>Se requiere un cliente de escritorio de Lync 2013.


</div></li>
<li><p>Foto de contacto de alta resolución en el cliente de Lync 2013 y Lync Web App</p>
<p>Para obtener más información, vea <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuración del uso de fotografías de alta resolución en Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]
> Requiere Exchange 2013.


</div></li>
<li><p>Delegación de reuniones</p>
<p>Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.</p></li>
<li><p>El historial de conversaciones perdidas y registros de llamadas se escribe en el buzón de Exchange del usuario</p></li>
<li><p>Contenido de archivado (mensajería instantánea y reuniones) en Exchange</p>
<p>Para obtener más información, vea <a href="lync-server-2013-deployment-checklist-for-archiving.md">Lista de comprobación para la implementación del archivado en Lync Server 2013</a></p>
<div>

> [!NOTE]
> Requiere Exchange 2013.


</div></li>
<li><p>Buscar contenido archivado</p>
<div>

> [!NOTE]
> Requiere Exchange 2013.


</div></li>
<li><p>Correo de voz</p>
<p>Para obtener más información, vea <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Implementar la mensajería unificada de Exchange local para proporcionar correo de voz de Lync Server 2013</a></p></li>
</ul></td>
<td><ul>
<li><p>Mensajería instantánea y presencia en Outlook</p>
<p>Para obtener más información, vea <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuración de la integración local de Lync Server 2013 con Exchange Online</a></p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p></li>
<li><p>Mensajería instantánea y presencia en OWA</p>
<p>Para obtener más información, vea <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuración de la integración local de Lync Server 2013 con Exchange Online</a></p></li>
<li><p>Programar y unirse a reuniones en línea desde Outlook Web App</p>
<p>Para obtener más información, vea <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuración de la integración local de Lync Server 2013 con Exchange Online</a></p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>Unirse a reuniones en línea en clientes móviles</p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>Lista de contactos (mediante el almacén de contactos unificado). Para obtener más información, consulte <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuración de Microsoft Lync Server 2013 para usar el almacén de contactos unificado</a></p>
<div>

> [!NOTE]
> Solo Lync Server 2013. Se requiere un cliente de escritorio de Lync 2013.


</div></li>
<li><p>Foto de contacto de alta resolución en el cliente de Lync 2013 y Lync Web App</p>
<p>Para obtener más información, vea <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuración del uso de fotografías de alta resolución en Microsoft Lync Server 2013</a>.</p></li>
<li><p>Delegación de reuniones</p>
<p>Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.</p></li>
<li><p>El historial de conversaciones perdidas y registros de llamadas se escribe en el buzón de Exchange del usuario</p></li>
<li><p>Contenido de archivado (mensajería instantánea y reuniones) en Exchange</p>
<p>Para obtener más información, vea <a href="lync-server-2013-deployment-checklist-for-archiving.md">Lista de comprobación para la implementación del archivado en Lync Server 2013</a></p></li>
<li><p>Buscar información archivada. Si desea más información, consulte <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">Configurar Exchange para el Centro de exhibición de documentos electrónicos de SharePoint en</a></p></li>
<li><p>Correo de voz. Para obtener más información, consulte <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Proporcionar correo de voz a usuarios de Lync Server 2013 en la mensajería unificada de Exchange hospedada</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Mensajería instantánea y presencia en Outlook</p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>El historial de conversaciones perdidas y registros de llamadas se escribe en el buzón de Exchange del usuario</p></li>
<li><p>Foto de contacto de alta resolución en el cliente de Lync 2013</p>
<div>

> [!NOTE]
> Requiere Microsoft Exchange Server 2013. No es compatible en Lync Web App cuando los usuarios se hospedan en Skype Empresarial Online.


</div></li>
<li><p>Unirse a reuniones en línea en clientes móviles</p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>Delegación de reuniones</p>
<p>Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.</p></li>
</ul></td>
<td><ul>
<li><p>Mensajería instantánea y presencia en Outlook</p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p></li>
<li><p>Mensajería instantánea y presencia en Outlook Web App</p></li>
<li><p>Programar y unirse a reuniones en línea desde Outlook Web App</p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>Unirse a reuniones en línea en clientes móviles</p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>El historial de conversaciones perdidas y registros de llamadas se escribe en el buzón de Exchange del usuario</p></li>
<li><p>Lista de contactos (mediante el almacén de contactos unificado)</p>
<div>

> [!NOTE]
> Se requiere el cliente de Lync Server 2013


</div></li>
<li><p>Foto de contacto de alta resolución en el cliente de Lync 2013 y Lync Web App</p></li>
<li><p>Delegación de reuniones</p>
<p>Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.</p></li>
<li><p>Contenido de archivado (mensajería instantánea y reuniones) en Exchange</p></li>
<li><p>Buscar contenido archivado</p></li>
<li><p>Correo de voz</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Integración con SharePoint

En la siguiente tabla se enumeran las características admitidas en una implementación híbrida de Lync Server 2013 cuando está integrada con SharePoint.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint local</th>
<th>SharePoint en línea</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 local</strong></p></td>
<td><ul>
<li><p>Búsqueda de aptitudes</p></li>
<li><p>Presencia en SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Presencia en SharePoint</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Presencia en SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Presencia en SharePoint</p></li>
</ul></td>
</tr>
</tbody>
</table>


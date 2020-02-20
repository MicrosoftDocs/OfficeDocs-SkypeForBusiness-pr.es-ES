---
title: 'Lync Server 2013: configuraciones híbridas admitidas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c757fc19bd82fbf1ae3096bb4a8ac8982f9035b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Configuraciones híbridas compatibles con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-05-10_

Puede configurar las implementaciones de Lync Server 2013 para la integración con Microsoft Exchange Server 2010 y Microsoft Exchange Server 2013 y SharePoint Server, tanto local como en línea. Las características que se enumeran en la tabla siguiente son compatibles con todos los clientes a menos que se especifique lo contrario. Para obtener más información acerca de la compatibilidad de clientes, consulte [Client Comparison tables for Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) y Skype for Business online Client Comparison tables at clients [for Skype for Business online](https://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Integración con Exchange Server

En la siguiente tabla se enumeran las características admitidas en una implementación híbrida cuando se integra con Microsoft Exchange Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Implementación local de Exchange</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 local</strong></p></td>
<td><ul>
<li><p>MI/presencia en Outlook</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-im-and-presence.md">mensajería instantánea y presencia en Lync Server 2013</a></p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">integración de Microsoft Lync server 2013 y Microsoft Exchange server 2013</a></p></li>
<li><p>MI/presencia en Outlook Web App</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">configuración de Microsoft Lync Server 2013 en un entorno entre locales</a></p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook Web App</p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>Unirse a reuniones en línea en clientes móviles</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-deploying-mobility.md">Deploying Mobility in Lync Server 2013</a></p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>Lista de contactos (a través del almacén de contactos unificado)</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">configuración de Microsoft Lync Server 2013 para usar el almacén de contactos unificado</a></p>
<div>

> [!NOTE]  
> Requiere Exchange 2013.<BR>Se necesita un cliente de escritorio de Lync 2013.


</div></li>
<li><p>Foto de contacto de alta resolución en el cliente de Lync 2013 y Lync Web App.</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuring the use of High-Resolution Photos in Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Requiere Exchange 2013.


</div></li>
<li><p>Delegación de reuniones</p>
<p>Compatible solo cuando los dos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados de forma local.</p></li>
<li><p>El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario</p></li>
<li><p>Contenido de archivado (mensajería instantánea y reuniones) en Exchange</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-deployment-checklist-for-archiving.md">lista de comprobación para la implementación del archivado en Lync Server 2013</a></p>
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
<p>Para obtener más información, consulte <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Deploying on-premises Exchange um to proporcionar Lync Server 2013 Voice Mail</a> .</p></li>
</ul></td>
<td><ul>
<li><p>MI/presencia en Outlook</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a></p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p></li>
<li><p>MI/presencia en OWA</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a></p></li>
<li><p>Programar y unirse a una reunión en línea desde Outlook Web App</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a></p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>Unirse a la reunión en línea en clientes móviles</p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>Lista de contactos (a través del almacén de contactos unificado). Para obtener más información, consulte <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">configuración de Microsoft Lync Server 2013 para usar el almacén de contactos unificado</a></p>
<div>

> [!NOTE]  
> Solo Lync Server 2013. Se necesita un cliente de escritorio de Lync 2013.


</div></li>
<li><p>Foto de contacto de alta resolución en el cliente de Lync 2013 y Lync Web App.</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuring the use of High-Resolution Photos in Microsoft Lync Server 2013</a>.</p></li>
<li><p>Delegación de reuniones</p>
<p>Compatible solo cuando los dos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados de forma local.</p></li>
<li><p>El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario</p></li>
<li><p>Contenido de archivado (mensajería instantánea y reuniones) en Exchange.</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-deployment-checklist-for-archiving.md">lista de comprobación para la implementación del archivado en Lync Server 2013</a></p></li>
<li><p>Buscar contenido archivado. Para obtener más información, consulte at <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange for SharePoint EDiscovery Center</a> .</p></li>
<li><p>Correo de voz. Para obtener más información, consulte <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">suministrar correo de voz de los usuarios de Lync Server 2013 en mensajería unificada de Exchange hospedada</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Mensajería instantánea y presencia en Outlook</p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario</p></li>
<li><p>Foto de contacto de alta resolución en el cliente de Lync 2013.</p>
<div>

> [!NOTE]  
> Requiere Microsoft Exchange Server 2013. Esto no es compatible con Lync Web App cuando los usuarios están alojados en Skype empresarial online.


</div></li>
<li><p>Unirse a la reunión en línea en clientes móviles</p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>Delegación de reuniones</p>
<p>Compatible solo cuando los dos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados de forma local.</p></li>
</ul></td>
<td><ul>
<li><p>MI/presencia en Outlook</p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p></li>
<li><p>MI/presencia en Outlook Web App</p></li>
<li><p>Programar y unirse a una reunión en línea desde Outlook Web App</p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>Unirse a la reunión en línea en clientes móviles</p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>El historial de conversaciones perdidas y los registros de llamadas se escriben en el buzón de Exchange del usuario</p></li>
<li><p>Lista de contactos (a través del almacén de contactos unificado)</p>
<div>

> [!NOTE]  
> Se necesita el cliente de Lync Server 2013


</div></li>
<li><p>Foto de contacto de alta resolución en Lync 2013 Client y Lync Web App</p></li>
<li><p>Delegación de reuniones</p>
<p>Compatible solo cuando los dos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados de forma local.</p></li>
<li><p>Contenido de archivado (mensajería instantánea y reuniones) en Exchange</p></li>
<li><p>Buscar contenido archivado</p></li>
<li><p>Correo de voz</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>Integración con SharePoint

En la siguiente tabla se enumeran las características admitidas en una implementación híbrida de Lync Server 2013 cuando se integran con SharePoint.


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
<th>SharePoint Online</th>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>


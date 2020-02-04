---
title: 'Lync Server 2013: configuraciones híbridas compatibles'
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
ms.openlocfilehash: 0dea28ecfcd5e6a881c1d3d1ee63f16cd4821410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Configuraciones híbridas de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-05-10_

Puede configurar las implementaciones de Lync Server 2013 para la integración con Microsoft Exchange Server 2010 y Microsoft Exchange Server 2013 y SharePoint Server, tanto local como en línea. Las características que se indican en la tabla siguiente son compatibles con todos los clientes, a menos que se indique lo contrario. Para obtener más información sobre la compatibilidad del cliente, consulte [tablas de comparación de clientes para Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) y tablas de comparación de clientes de Skype empresarial online en [clientes de Skype empresarial online](http://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Integración con Exchange Server

En la siguiente tabla se enumeran las características compatibles con una implementación híbrida cuando se integra con Microsoft Exchange Server.


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
<p>Para obtener más información, consulte <a href="lync-server-2013-im-and-presence.md">mensajería instantánea y presencia en Lync Server 2013</a></p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p>
<p>Para más información, vea <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</a>.</p></li>
<li><p>Mensajería instantánea en Outlook Web App</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">configurar Microsoft Lync Server 2013 en un entorno entre locales</a></p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook Web App</p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>Unirse a reuniones en línea en clientes móviles</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-deploying-mobility.md">implementación de la movilidad en Lync Server 2013</a></p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>Lista de contactos (por medio del almacén de contactos unificado)</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">configurar Microsoft Lync Server 2013 para usar el almacén de contactos unificado</a></p>
<div>

> [!NOTE]  
> Requiere Exchange 2013.<BR>Es necesario un cliente de escritorio de Lync 2013.


</div></li>
<li><p>Foto de contacto de alta resolución en el cliente de Lync 2013 y Lync Web App.</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">configuración del uso de fotos de alta resolución en Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Requiere Exchange 2013.


</div></li>
<li><p>Delegación de reuniones</p>
<p>Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.</p></li>
<li><p>El historial de conversaciones perdidas y registros de llamadas se escribe en el buzón de Exchange del usuario</p></li>
<li><p>Contenido de archivado (mensajería instantánea y reuniones) en Exchange</p>
<p>Para obtener más información, vea <a href="lync-server-2013-deployment-checklist-for-archiving.md">lista de comprobación de la implementación para archivar en Lync Server 2013</a></p>
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
<p>Para obtener más información, consulte <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">implementación local de mensajería unificada de Exchange para proporcionar el correo de voz de Lync Server 2013</a></p></li>
</ul></td>
<td><ul>
<li><p>Mensajería instantánea y presencia en Outlook</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">configuración de la integración local de Lync Server 2013 con Exchange Online</a></p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p></li>
<li><p>Mensajería instantánea y presencia en OWA</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">configuración de la integración local de Lync Server 2013 con Exchange Online</a></p></li>
<li><p>Programar y unirse a la reunión en línea desde Outlook Web App</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">configuración de la integración local de Lync Server 2013 con Exchange Online</a></p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>Unirse a reuniones en línea en clientes móviles</p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>Lista de contactos (por medio del almacén de contactos unificado). Para obtener más información, consulte <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">configurar Microsoft Lync Server 2013 para usar el almacén de contactos unificado</a></p>
<div>

> [!NOTE]  
> Solo Lync Server 2013. Es necesario un cliente de escritorio de Lync 2013.


</div></li>
<li><p>Foto de contacto de alta resolución en el cliente de Lync 2013 y Lync Web App.</p>
<p>Para obtener más información, consulte <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">configuración del uso de fotos de alta resolución en Microsoft Lync Server 2013</a>.</p></li>
<li><p>Delegación de reuniones</p>
<p>Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.</p></li>
<li><p>El historial de conversaciones perdidas y registros de llamadas se escribe en el buzón de Exchange del usuario</p></li>
<li><p>Contenido de archivado (mensajería instantánea y reuniones) en Exchange.</p>
<p>Para obtener más información, vea <a href="lync-server-2013-deployment-checklist-for-archiving.md">lista de comprobación de la implementación para archivar en Lync Server 2013</a></p></li>
<li><p>Buscar información archivada. Para obtener más información, consulte <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">configurar Exchange para el centro de exhibición de SharePoint</a></p></li>
<li><p>Correo de voz. Para obtener más información, consulte <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">proporcionar usuarios de Lync Server 2013 correo de voz en mensajería unificada de Exchange hospedado</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Mensajería instantánea y presencia en Outlook</p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>El historial de conversaciones perdidas y registros de llamadas se escribe en el buzón de Exchange del usuario</p></li>
<li><p>Foto de contacto de alta resolución en el cliente de Lync 2013.</p>
<div>

> [!NOTE]  
> Requiere Microsoft Exchange Server 2013. Este no es compatible con Lync Web App cuando los usuarios están alojados en Skype empresarial online.


</div></li>
<li><p>Unirse a reuniones en línea en clientes móviles</p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>Delegación de reuniones</p>
<p>Se admite solo cuando ambos usuarios están hospedados en línea en el mismo bosque o ambos están hospedados localmente.</p></li>
</ul></td>
<td><ul>
<li><p>Mensajería instantánea y presencia en Outlook</p></li>
<li><p>Programar y unirse a reuniones en línea a través de Outlook</p></li>
<li><p>Mensajería instantánea en Outlook Web App</p></li>
<li><p>Programar y unirse a la reunión en línea desde Outlook Web App</p></li>
<li><p>Mensajería instantánea y presencia en clientes móviles</p></li>
<li><p>Unirse a reuniones en línea en clientes móviles</p></li>
<li><p>Publicar el estado según la información de disponibilidad del calendario de Outlook</p></li>
<li><p>El historial de conversaciones perdidas y registros de llamadas se escribe en el buzón de Exchange del usuario</p></li>
<li><p>Lista de contactos (por medio del almacén de contactos unificado)</p>
<div>

> [!NOTE]  
> Cliente de Lync Server 2013 requerido


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


</div>

<div>

## <a name="integration-with-sharepoint"></a>Integración con SharePoint

En la tabla siguiente se enumeran las características compatibles con una implementación híbrida de Lync Server 2013 cuando se integra con SharePoint.


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


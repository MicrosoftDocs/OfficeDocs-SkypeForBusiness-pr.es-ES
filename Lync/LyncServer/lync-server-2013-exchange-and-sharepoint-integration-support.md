---
title: 'Lync Server 2013: compatibilidad con la integración de Exchange y SharePoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fdfaffa12d84b57f0ae0203ebc14491bb6d8d4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Compatibilidad con la integración de Exchange y SharePoint en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-01-18_

Lync Server 2013 y Lync 2013 pueden comunicarse de forma segura y sin problemas con otras aplicaciones y productos de servidor, incluidos Office 2013, Exchange Server 2013, Exchange Server 2016 y SharePoint, si estos productos se integran. La integración de Lync Server 2013 y Office proporciona a los usuarios acceso en contexto a la mensajería instantánea (mi), la presencia mejorada, la telefonía y las capacidades de conferencia de Lync. Los usuarios de Office pueden acceder a las características de Lync desde el cliente de mensajería y colaboración de Outlook 2013 y otros programas de Office o desde una página de SharePoint. Los usuarios también pueden ver un registro de las conversaciones de Lync en la carpeta Historial de conversaciones de Outlook. Cuando se integra con Exchange 2013, Exchange 2016 o Exchange Online, Lync Server 2013 también admite lo siguiente:

  - Almacén de contactos unificado, que permite a los usuarios almacenar toda la información de contacto en Exchange o Exchange Online para que la información esté disponible de forma global en Lync 2013, Exchange, Outlook y Outlook Web App.

  - Historial de conversaciones e historial de conferencias web, que se almacenan en las carpetas de usuario de Exchange.

  - El contenido archivado de Lync, como la mensajería instantánea y el contenido de reuniones, se puede almacenar en el almacenamiento de Exchange.

<div>


> [!NOTE]  
> Lync Server 2013 admite la integración con versiones anteriores de Microsoft Exchange Server y SharePoint Server, pero no todas las funciones son compatibles con estas versiones anteriores, como la integración del almacenamiento de archivado con Microsoft Exchange.<BR>Si va a migrar los usuarios a Exchange 2013 o Exchange 2016, puede usar el almacenamiento de Exchange y el almacenamiento de Lync Server de manera provisional, mientras completa la migración. No se admite el uso permanente de almacenamiento de Exchange y Lync Server.



</div>

La integración de Lync Server 2013 con Exchange Server y SharePoint Server requiere la autenticación de servidor a servidor entre los servidores que ejecutan Lync Server 2013, Exchange Server y SharePoint Server. Lync Server 2013 admite el protocolo OAuth (Open Authorization) para la autenticación y autorización de servidor a servidor. Para la autenticación de servidor a servidor local entre dos servidores de Microsoft, no es necesario utilizar un servidor de token de terceros. Lync Server 2013, Exchange Server y SharePoint Server tienen un servidor de tokens integrado que se puede usar para fines de autenticación entre sí. Por ejemplo, Lync Server 2013 puede emitir y firmar un token de seguridad por sí mismo, y usar ese token para comunicarse con Exchange. En este caso, no es necesario utilizar un servidor de token de terceros.

Lync Server 2013 admite los dos escenarios de autenticación de servidor a servidor. Esto incluye la configuración de la autenticación de servidor a servidor entre los elementos siguientes:

  - Una instalación local de Lync Server 2013 y una instalación local de Exchange Server 2013, Exchange Server 2016 y/o SharePoint Server.

  - Un par de componentes de Office (por ejemplo, entre Microsoft Exchange 365 y Microsoft Lync Server 365, o entre Microsoft Lync Server 365 y Microsoft SharePoint 365).

<div>


> [!NOTE]  
> La autenticación de servidor a servidor entre un servidor local y un componente de Office 365 no se admite en esta versión 2013 de Lync Server. Entre otras cosas, esto significa que no se puede configurar la autenticación de servidor a servidor entre una instalación local de Lync Server 2013 y Microsoft Exchange 365.



</div>

Para obtener información detallada acerca de la autenticación de servidor a servidor, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación de implementación u operaciones.

</div>

<span> </span>

</div>

</div>

</div>


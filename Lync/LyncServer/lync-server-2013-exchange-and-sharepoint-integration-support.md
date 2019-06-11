---
title: 'Lync Server 2013: compatibilidad con la integración de Exchange y SharePoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4d378337643adf79557bd4bbb649a01948de27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Compatibilidad de integración de Exchange y SharePoint en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-01-18_

Lync Server 2013 y Lync 2013 pueden comunicarse de manera segura y sin problemas con otras aplicaciones y productos de servidor, como Office 2013, Exchange Server 2013, Exchange Server 2016 y SharePoint, si integra estos productos. La integración de Lync Server 2013 y Office ofrece a los usuarios acceso en contexto a la mensajería instantánea (mi), la presencia mejorada, la telefonía y las capacidades de conferencia de Lync. Los usuarios de Office pueden tener acceso a las características de Lync desde el cliente de mensajería y colaboración de Outlook 2013 y otros programas de Office o desde una página de SharePoint. Los usuarios también pueden ver un registro de las conversaciones de Lync en la carpeta Historial de conversaciones de Outlook. Cuando se integra con Exchange 2013, Exchange 2016 o Exchange Online, Lync Server 2013 también admite lo siguiente:

  - Almacén de contactos unificado, que permite a los usuarios almacenar toda la información de contacto en Exchange o Exchange Online, de modo que la información esté disponible en todo el mundo en Lync 2013, Exchange, Outlook y Outlook Web App.

  - Historial de conversaciones y historial de conferencias web, que se almacenan en las carpetas de usuario de Exchange.

  - El contenido archivado de Lync, como el mensajería instantánea y el contenido de la reunión, puede almacenarse en el almacenamiento de Exchange.

<div>


> [!NOTE]  
> Lync Server 2013 admite la integración con versiones anteriores de Microsoft Exchange Server y SharePoint Server, pero no todas las funciones son compatibles con estas versiones anteriores, como la integración del almacenamiento de archivado con Microsoft Exchange.<BR>Si va a migrar los usuarios a Exchange 2013 o Exchange 2016, puede usar el almacenamiento de Exchange y el almacenamiento de Lync Server de forma provisional, mientras completa la migración. No se admite el uso permanente del almacenamiento de Exchange y de Lync Server.



</div>

La integración de Lync Server 2013 con Exchange Server y SharePoint Server requiere la autenticación de servidor a servidor entre los servidores que ejecutan Lync Server 2013, Exchange Server y SharePoint Server. Lync Server 2013 admite el protocolo OAuth (Open Authorization) para la autenticación y la autorización de servidor a servidor. Para la autenticación local de servidor a servidor entre dos servidores de Microsoft, no es necesario usar un servidor de tokens de terceros. Lync Server 2013, Exchange Server y SharePoint Server tienen un token de servidor integrado que se puede usar para fines de autenticación entre sí. Por ejemplo, Lync Server 2013 puede emitir y firmar un token de seguridad por sí mismo, y usar ese token al comunicarse con Exchange. En este caso, no es necesario usar un servidor de tokens de terceros.

Lync Server 2013 admite los dos escenarios de autenticación de servidor a servidor. Esto incluye la configuración de la autenticación de servidor a servidor entre los siguientes:

  - Una instalación local de Lync Server 2013 y una instalación local de Exchange Server 2013, Exchange Server 2016 y/o SharePoint Server.

  - Un par de componentes de Office (por ejemplo, entre Microsoft Exchange 365 y Microsoft Lync Server 365, o entre Microsoft Lync Server 365 y Microsoft SharePoint 365).

<div>


> [!NOTE]  
> La autenticación de servidor a servidor entre un servidor local y un componente de Office 365 no se admite en esta versión 2013 de Lync Server. Entre otras cosas, esto significa que no se puede configurar la autenticación de servidor a servidor entre una instalación local de Lync Server 2013 y Microsoft Exchange 365.



</div>

Para obtener más información sobre la autenticación de servidor a servidor, vea [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación de implementación o de operaciones.

</div>

<span> </span>

</div>

</div>

</div>


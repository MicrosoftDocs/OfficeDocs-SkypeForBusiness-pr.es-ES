---
title: "Lync Server 2013: Compatibilidad de la integración Exchange Server y SharePoint"
TOCTitle: Compatibilidad de la integración Exchange Server y SharePoint
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48275666
ms.date: 01/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad de la integración Exchange Server y SharePoint en Lync Server 2013

 

_**Última modificación del tema:** 2017-01-18_

Lync Server 2013 y Lync 2013 pueden comunicarse de forma segura y directa con otras aplicaciones y otros productos de servidor, como Office 2013, Exchange 2013 y SharePoint, si integra estos productos. La integración de Lync Server 2013 y Office permite a los usuarios acceder dentro del contexto a las funcionalidades de mensajería instantánea (MI), presencia mejorada, telefonía y conferencia de Lync. Los usuarios de Office pueden acceder a las características de Lync desde el cliente de mensajería y colaboración de Outlook 2013 y otros programas de Office, o desde una página de Microsoft SharePoint Server 2010. Los usuarios también pueden ver un registro de las conversaciones de Lync en la carpeta del historial de conversaciones de Outlook. Cuando se integra con Exchange 2013 o Exchange Online, Lync Server 2013 admite también lo siguiente:

  - Almacén de contactos unificado, que permite a los usuarios almacenar toda la información de contacto en Exchange 2013 o Exchange Online para que la información esté disponible de forma global en Lync 2013, Exchange, Outlook y Outlook Web App.

  - Historial de conversaciones y conferencias web, que se almacenan en las carpetas de usuarioExchange.

  - El contenido archivado de Lync, como el contenido de la mensajería instantánea y las reuniones, se puede almacenar en el almacenamiento de Exchange.


> [!NOTE]
> Lync Server 2013 admite la integración con las versiones anteriores de Microsoft Exchange Server ySharePoint, pero no se admiten todas las funcionalidades con estas versiones anteriores, como la integración del almacén de archivado con Microsoft Exchange.<BR>Si está migrando sus usuarios aExchange 2013, puede utilizar tanto el almacenamiento de Exchange como el almacenamiento de Lync Server de modo provisional, mientras completa la migración. El uso permanente de los almacenamientosExchangeyLync Server no se admite.



La integración de Lync Server 2013 con Exchange 2013 y SharePoint Server requiere una autenticación de servidor a servidor entre los servidores que ejecutan Lync Server 2013,Microsoft Exchange Server y SharePoint Server. Lync Server 2013 admite el protocolo OAuth (Open Authorization) para la autenticación y la autorización de servidor a servidor. Para la autenticación de servidor a servidor local entre dos servidores de Microsoft, no es necesario utilizar un servidor de token de terceros.Lync Server 2013, Exchange 2013 y SharePoint tienen un servidor de token integrado que se puede utilizar con fines de autenticación entre ellos. Por ejemplo, Lync Server 2013 puede emitir y crear un token de seguridad para utilizarlo al comunicarse con Exchange 2013. En este caso, no es necesario utilizar un servidor de token de terceros.

Lync Server 2013 admite los dos escenarios de autenticación de servidor a servidor. Esto incluye la configuración de la autenticación de servidor a servidor entre los elementos siguientes:

  - Una instalación local de Lync Server 2013 y una instalación local de Exchange 2013 y/o SharePoint Server.

  - Un par de componentes de Office (por ejemplo, entre Microsoft Exchange 365 y Microsoft Lync Server 365, o entre Microsoft Lync Server 365 y Microsoft SharePoint 365).


> [!NOTE]
> La autenticación de servidor a servidor entre un servidor local y un componente de Office 365 no se admite en esta versión de Lync Server 2013. Entre otras cosas, esto significa que no se puede configurar una autenticación de servidor a servidor entre una instalación local de Lync Server 2013 y Microsoft Exchange 365.



Para más información sobre la autenticación de servidor a servidor, vea [Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación sobre la implementación o sobre las operaciones.


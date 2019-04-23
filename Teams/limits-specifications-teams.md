---
title: Límites y especificaciones para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: karuanag
description: Obtenga información sobre los límites, especificaciones y otros requisitos que se aplican a Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: a151ca7e35f6b512064bc1554b754e9aefdef358
ms.sourcegitcommit: c011e4ab6f936a9e26d304835634293b1cedc57d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2019
ms.locfileid: "31043360"
---
<a name="limits-and-specifications-for-microsoft-teams"></a>Límites y especificaciones para Microsoft Teams
=============================================

Este artículo describe algunos de los límites, especificaciones y otros requisitos que se aplican a Teams. 

<a name="teams-and-channels"></a>Equipos y canales 
------------------

|Característica    | Límite máximo |
|-----------|---------------|
|Número de equipos que un usuario puede crear | Sujeto a un límite de 250 objetos&sup1;         |
|Número de miembros de un equipo | 5 000       |
|Número de miembros de un [equipo de toda la organización](create-an-org-wide-team.md) | 5 000       |
|Número de equipos que un administrador global puede crear        |  500 000   |
|Número de equipos que puede tener un espacio empresarial de Office 365    | 500 000     |
|Número de canales por equipo    | 200 (incluye canales eliminados)         |

&sup1;Cualquier objeto de directorio en Azure Active Directory cuenta para este límite. Los administradores globales están exentos de este límite, al igual que las aplicaciones que llaman a Microsoft Graph mediante [permisos de aplicación](https://docs.microsoft.com/graph/permissions-reference).

<a name="meetings-and-calls"></a>Reuniones y llamadas 
------------------

|Característica     | Límite máximo |
|------------|---------------|
|Número de personas en una reunión  | 250    |
|Número de usuarios en un chat privado  | 50    |

<a name="storage"></a>Almacenamiento
-------

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.

Si no tiene habilitado SharePoint Online en su espacio empresarial, los usuarios de Microsoft Teams no podrán compartir archivos en los equipos. Los usuarios de chats privados tampoco podrán compartir archivos, porque se necesita OneDrive para la Empresa (que está ligado a la licencia de SharePoint) para esa funcionalidad.

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino. (Para obtener más información, vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md)).

Ya que Teams se ejecuta en un back-end de SharePoint Online para compartir archivos, las limitaciones de SharePoint se aplican a la sección Archivos en un equipo. Estos son los límites de almacenamiento correspondientes para SharePoint Online.

|Característica                 |Office 365 Empresa Essentials  |Office 365 Empresa Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Almacenamiento                 |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización, además de 10 GB por cada licencia adquirida.   |1 TB por organización, además de 10 GB por cada licencia adquirida. |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización           |
|Almacenamiento de archivos de Teams  |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |
|Límite de carga de archivo       |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Cada pestaña Archivos en Teams se ejecuta en un back-end de SharePoint Online, por lo que los límites de almacenamiento anteriores se aplican para cada canal de un equipo.

Para obtener más información, vea [Límites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

<a name="messaging"></a>Mensajería 
---------

Los usuarios que participan en conversaciones que forman parte de la lista de Chat en Microsoft Teams deben tener un buzón de Exchange Online (en la nube) para que un administrador busque conversaciones de chat. Esto sucede porque las conversaciones que son parte de la lista de Chat se almacenan en los buzones basados en la nube de los participantes del chat. Si un participante del chat no tiene un buzón de Exchange Online, el administrador no podrá buscar o establecer una suspensión en las conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con buzones locales podrían participar en conversaciones que forman parte de la lista de Chat en Microsoft Teams. Pero en este caso, el contenido de estas conversaciones no se puede buscar y no se puede colocar en espera, ya que los usuarios no tienen buzones en la nube. (Para obtener más información, vea [Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md)).

La función de chat de Microsoft Teams funciona en un back-end de Microsoft Exchange, por lo que puede aplicar los límites de mensajería de Exchange en la función de chat en Microsoft Teams. Si los usuarios quieren enviar un correo electrónico a un canal en Teams, pueden hacerlo mediante la dirección de correo electrónico del canal. Cuando un correo electrónico forma parte de un canal, cualquier persona puede responder para iniciar una conversación. Estos son algunos de los límites correspondientes para enviar correo electrónico a un canal. 

|Característica  |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|---------|---------|---------|---------|---------|
|Límite de tamaño de mensaje &dagger;  |25 KB   |25 KB   |25 KB   |25 KB   |
|Límite de datos adjuntos &Dagger;  |10     |10     |10     |10    |
|Límite de imágenes en línea &Dagger; |50   |50   |50   |50   |

&dagger; Si el mensaje supera este límite, se genera un mensaje de vista previa y se pide al usuario ver o descargar el mensaje original desde el vínculo proporcionado.

&Dagger; Si el número de datos adjuntos o imágenes supera este límite, el mensaje no se procesará y se enviará un correo electrónico NDR al remitente para informarle del error.

Para más información, vea [Límites de Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).

<a name="browsers"></a>Exploradores 
--------

[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="operating-systems"></a>Sistemas operativos
-----------------

Para obtener información sobre los requisitos del sistema operativo, consulte [Obtener clientes para Microsoft Teams](get-clients.md).



---
title: Límites y especificaciones para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: Obtenga información sobre los límites, especificaciones y otros requisitos que se aplican a Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecd31a243da999704b7d466b3dc93dd66fb7ac25
ms.sourcegitcommit: 9053c0d5ddb6be3ce3da85dffcde3f45dbc0ab7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "36407884"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Límites y especificaciones para Microsoft Teams

Este artículo describe algunos de los límites, especificaciones y otros requisitos que se aplican a Teams.

## <a name="teams-and-channels"></a>Equipos y canales 

|Característica    | Límite máximo |
|-----------|---------------|
|Número de equipos que un usuario puede crear | Sujeto a un límite de 250 objetos&sup1;         |
|Número de miembros de un equipo | 5 000       |
|Número de equipos de toda la organización permitidos en un espacio empresarial | 5     |
|Número de miembros de un [equipo de toda la organización](create-an-org-wide-team.md) | 5 000       |
|Número de equipos que un administrador global puede crear        |  500 000   |
|Número de equipos que puede tener un espacio empresarial de Office 365    | 500.000&sup2     |
|Número de canales por equipo    | 200 (incluye canales eliminados) &sup3;         |

&sup1;Cualquier objeto de directorio en Azure Active Directory cuenta para este límite. Los administradores globales están exentos de este límite, al igual que las aplicaciones que llaman a Microsoft Graph mediante [permisos de aplicación](https://docs.microsoft.com/graph/permissions-reference).

&sup2; Este límite incluye equipos archivados.

&sup3; los canales eliminados se pueden restaurar en un plazo de 30 días. Durante estos 30 días, un canal eliminado continúa contando con el canal de 200 por límite de equipo. Después de los 30 días, un canal eliminado y su contenido se eliminan permanentemente y el canal ya no se cuenta en los canales 200 por límite de equipo.

## <a name="channel-names"></a>Nombres de canales

Los nombres de canal no pueden contener los siguientes caracteres o palabras.

|||
|---------|---------|
|Personajes     | ~ #% & * {} +/\:  < > ? &#124; ' "..        |
|Caracteres en estos intervalos    | 0 a 1F<br>80 a 9F        |
|Varias     | Forms, con, CONIN $, CONOUT $, PRN, AUX, NUL, COM1 a COM9, LPT1 a LPT9, Desktop. ini, &#95;VTI&#95;|

Los nombres de canales tampoco pueden empezar con un carácter de subrayado (_) o punto (.) ni finalizar con un punto (.).

## <a name="meetings-and-calls"></a>Reuniones y llamadas

|Característica     | Límite máximo |
|------------|---------------|
|Número de personas en una reunión  | 250    |

## <a name="teams-live-events"></a>Eventos de Teams Live

|Característica     | Límite máximo |
|------------|---------------|
|Tamaño de la audiencia | 10.000 asistentes |
|Duración del evento | 4 horas |
|Columna1  |Columna2  |
|---------|---------|
|Row1     |         |
|Row2     |         |

| Eventos en directo simultáneos en un inquilino de Office 365 | 15 |

Para obtener más información sobre eventos en directo y una comparación de los eventos de Teams Live para la difusión de reunión de Skype, vaya a [eventos de Teams Live y difusión de reunión de Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).

## <a name="storage"></a>Almacenamiento

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.

Si no tiene habilitado SharePoint Online en su espacio empresarial, los usuarios de Microsoft Teams no podrán compartir archivos en los equipos. Los usuarios de chats privados tampoco podrán compartir archivos, porque se necesita OneDrive para la Empresa (que está ligado a la licencia de SharePoint) para esa funcionalidad.

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino. (Para obtener más información, vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md)).

Ya que Teams se ejecuta en un back-end de SharePoint Online para compartir archivos, las limitaciones de SharePoint se aplican a la sección Archivos en un equipo. Estos son los límites de almacenamiento correspondientes para SharePoint Online.

|Característica                 |Office 365 Empresa Essentials  |Office 365 Empresa Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Almacenamiento                 |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización, además de 10 GB por cada licencia adquirida.   |1 TB por organización, además de 10 GB por cada licencia adquirida. |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización           |
|Almacenamiento de archivos de Teams  |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |
|Límite de carga de archivos (por archivo)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Los canales están respaldados por carpetas dentro de la colección de sitios de SharePoint Online creada para el equipo, por lo que las pestañas de archivos de los canales comparten los límites de almacenamiento del equipo al que pertenecen.

Para obtener más información, vea [Límites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="messaging"></a>Mensajería 

Los usuarios que participan en conversaciones que forman parte de la lista de Chat en Microsoft Teams deben tener un buzón de Exchange Online (en la nube) para que un administrador busque conversaciones de chat. Esto sucede porque las conversaciones que son parte de la lista de Chat se almacenan en los buzones basados en la nube de los participantes del chat. Si un participante del chat no tiene un buzón de Exchange Online, el administrador no podrá buscar o establecer una suspensión en las conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con buzones locales podrían participar en conversaciones que forman parte de la lista de Chat en Microsoft Teams. Pero en este caso, el contenido de estas conversaciones no se puede buscar y no se puede colocar en espera, ya que los usuarios no tienen buzones en la nube. (Para obtener más información, vea [Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md)).

La función de chat de Microsoft Teams funciona en un back-end de Microsoft Exchange, por lo que puede aplicar los límites de mensajería de Exchange en la función de chat en Microsoft Teams. Si los usuarios quieren enviar un correo electrónico a un canal en Teams, pueden hacerlo mediante la dirección de correo electrónico del canal. Cuando un correo electrónico forma parte de un canal, cualquier persona puede responder para iniciar una conversación. Estos son algunos de los límites correspondientes para enviar correo electrónico a un canal. 

|Característica  | Límite máximo  |
|---------|---------|
|Número de usuarios en un chat privado  | 100    |
|Tamaño del mensaje&dagger;  |25 KB   |
|Número de archivos adjuntos&Dagger;  |base10     |
|Número de imágenes en línea&Dagger; |50   |

&dagger; Si el mensaje supera este límite, se genera un mensaje de vista previa y se pide al usuario ver o descargar el mensaje original desde el vínculo proporcionado.

&Dagger;Si el número de archivos adjuntos o imágenes supera este límite, no se procesará el mensaje y se enviará un mensaje de correo electrónico de NDR al remitente para notificarle el error.

> [!NOTE]
> El tamaño de los mensajes, los datos adjuntos y los límites de las imágenes en línea son los mismos en todas las licencias de Office 365.

Para más información, vea [Límites de Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).

## <a name="browsers"></a>Exploradores

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Sistemas operativos

Para obtener información sobre los requisitos del sistema operativo, consulte [Obtener clientes para Microsoft Teams](get-clients.md).

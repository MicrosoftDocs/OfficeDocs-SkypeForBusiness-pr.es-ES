---
title: Límites y especificaciones para Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: Este artículo describe los límites, especificaciones y otros requisitos que se aplican a Microsoft Teams.
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5ae4adf9d803ea0b3482451a9ece5d3ceb0df598
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307535"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Límites y especificaciones para Microsoft Teams

Este artículo describe algunos de los límites, especificaciones y otros requisitos que se aplican a Teams.

## <a name="teams-and-channels"></a>Equipos y canales

|Característica    | Límite máximo |
|-----------|---------------|
|Número de equipos que un usuario puede crear | Sujeto a un límite de 250 objetos&sup1;         |
|Número de equipos en los que un usuario puede ser un miembro de|1 000&sup2;|
|Número de miembros de un equipo | 25 000<sup>6</sup>     |
|Número de propietarios por equipo | 100   |
|Número de equipos de la organización que se pueden usar en un espacio empresarial | 5&sup2;     |
|Número de miembros de un [equipo de toda la organización](create-an-org-wide-team.md) | 10 000       |
|Número de equipos que un administrador global puede crear        |  500 000   |
|Cantidad de equipos que puede tener una organización de Microsoft 365 y Office 365    | 500 000&sup3;     |
|Número de canales por equipo    | 200 (incluye canales eliminados)<sup>4</sup>        |
|Número de canales privados por equipo    |30 (incluye canales eliminados)<sup>4</sup>        |
|Número de miembros de un canal privado    |250|
|Tamaño máximo de la lista de distribución, grupo de seguridad o grupo de Microsoft 365 que se puede importar a un equipo    |3,500|
|Número máximo de miembros de un grupo de Microsoft 365 que se pueden convertir en un equipo    |10 000<sup>6</sup>     |
|Tamaño de publicación de conversación de canal | Aproximadamente 28 KB por publicación<sup>5</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).

<sup>2</sup> Este límite incluye equipos archivados. 

<sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant. Increase is only made for real-life production scenarios.

<sup>4</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.

<sup>5</sup> 28 KB es un límite aproximado, ya que incluye al mensaje en sí (texto, vínculos de la imagen, etc.), las @menciones, el número de conectores y las reacciones.

<sup>6</sup> Los miembros de canales compartidos de fuera del equipo cuentan para este límite. Además, tenga en cuenta que las menciones de canales y equipos están bloqueadas en equipos con más de 10 000 miembros.

> [!NOTE]
> Para ver los límites de los canales compartidos, consulte [Límites de los canales compartidos](/MicrosoftTeams/shared-channels#limits-for-shared-channels).

## <a name="messaging"></a>Mensajería 

### <a name="chat"></a>Chat

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)


|Característica  | Límite máximo  |
|---------|---------|
|Número de usuarios en un chat privado<sup>1</sup>  | 250<sup>2</sup> |
|Cantidad de personas en una llamada de audio o vídeo desde el chat | 20 |
|Número de datos adjuntos de archivos<sup>3</sup>  |10     |
|Tamaño de chat | Aproximadamente 28 KB por publicación<sup>4</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup> Only 200 members at a time can be added to a group chat. [See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> Si el número de archivos adjuntos supera este límite, aparecerá un mensaje de error.

<sup>4</sup> 28 KB es un límite aproximado, ya que incluye el mensaje en sí (texto, vínculos a imágenes, etc.), las @menciones y las reacciones.

### <a name="emailing-a-channel"></a>Enviar un correo electrónico a un canal

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

|Característica  | Límite máximo  |
|---------|---------|
|Tamaño del mensaje<sup>1<sup> | 24 KB |
|Número de datos adjuntos de archivo<sup>2</sup>  |20     |
|Tamaño de los datos adjuntos del archivo | Menos de 10 MB |
|Número de imágenes insertadas<sup>2</sup> |50   |

> [!NOTE]
> Hay un límite en cuanto al número de correos electrónicos que puede enviar a un canal. El límite es de seis correos electrónicos por diez segundos por canal por usuario y ocho correos electrónicos por diez segundos por inquilino por usuario.
<sup>1</sup> Si el mensaje excede este límite, se genera un mensaje de vista previa y se le pide al usuario que descargue y vea el correo electrónico original desde el enlace proporcionado.

<sup>2</sup> Si el número de archivos adjuntos o imágenes supera este límite, aparecerá un mensaje de error.

Para más información, consulte [Límites de Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.

## <a name="channel-names"></a>Nombres del canal

Los nombres de los canales no pueden contener ninguno de los siguientes caracteres o palabras:

|Tipo|Ejemplo|
|---------|---------|
|Caracteres     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|Caracteres en estos rangos    | 0 a 1F<br>80 a 9F        |
|Palabras     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;|

Los nombres de canal tampoco pueden empezar con un carácter de subrayado (_) o un punto (.), ni terminar con un punto (.).

## <a name="meetings-and-calls"></a>Reuniones y llamadas

|Característica     | Límite máximo |
|------------|---------------|
|Número de personas en una reunión (pueden chatear y llamar)  | 1000, incluye GCC, GCCH y DoD, pero no A1 (300). **Solo lectura** permite que hasta 20 000 participantes solo para escuchar se unan a una reunión en la que el organizador tenga una licencia para SKU de E3/E5/A3/A5, así como administración pública (GCC, GCC High, DoD). La experiencia de solo vista pronto también estará disponible para los seminarios web. Más información sobre la [Experiencia de solo vista](view-only-meeting-experience.md).<sup>1,2</sup>|
|Cantidad de personas en una llamada de audio o vídeo desde el chat | 20 |
|Tamaño máximo de archivo de PowerPoint | 2 GB|
|Teams guarda [grabaciones de la reunión](cloud-recording.md) que no se cargan en Microsoft Stream, que se pueden descargar de forma local | 20 días |
| Duración máxima de la grabación de la reunión | 4 horas o 1,5 GB. Cuando se alcance este límite, la grabación finalizará y se reiniciará automáticamente.
  
<sup>1</sup> Para obtener la mejor experiencia con seminarios web, eventos en directo y reuniones de gran tamaño, Microsoft recomienda usar la última versión del cliente de escritorio o los clientes móviles de Teams.

<sup>2</sup> Los moderadores de seminarios web, eventos en directo y reuniones de gran tamaño deben usar el cliente de escritorio de Teams. Para obtener más consejos sobre cómo organizar reuniones grandes, consulte [Prácticas recomendadas para una reunión grande de equipos](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16).

> [!NOTE]
> Las salas para sesión de subgrupo solo se pueden crear en reuniones con menos de 300 asistentes. Además, la creación de salas para sesión de subgrupo en una reunión limita automáticamente el número de asistentes de la reunión a 300. Aconseje a los usuarios finales que no inicien salas para sesión de subgrupo en reuniones en las que esperen más de 300 participantes. Para más información sobre las reuniones de gran tamaño de Teams, comparta las instrucciones [Procedimientos recomendados para reuniones de gran tamaño de Teams](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16) con los usuarios finales.

### <a name="meeting-expiration"></a>Expiración de la reunión

> [!NOTE]
> A meeting URL will never stop working. The expiry only relates to any PSTN dial-in numbers, CVI coordinates, and/or underlying meeting policies and settings.

|Tipo de reunión  |La reunión expira después de esta cantidad de tiempo  |Cada vez que se inicia o actualiza una reunión, la expiración se extiende por este tiempo  |
|---------|---------|---------|
|Reunirse ahora     |Hora de inicio + 8 horas         |N/D         |
|Regular sin hora de finalización     |Hora de inicio + 60 días         | 60 días        |
|Regular con hora de finalización     |Hora de finalización + 60 días         |60 días         |
|Periódica sin hora de finalización     |Hora de inicio + 60 días         |60 días         |
|Periódica con hora de finalización     |Hora de finalización de la última repetición + 60 días         |60 días         |

> [!NOTE]
> Las reuniones de Microsoft Teams tienen un límite de tiempo de 30 horas.

## <a name="teams-live-events"></a>Eventos en directo en Teams

|Característica     | Límite máximo |
|------------|---------------|
|Tamaño de público | 10 000 asistentes |
|Duración del evento | 4 horas |
|Eventos en directo simultáneos ejecutándose en una organización de Microsoft 365 y Office 365 <sup>1</sup> | 15 |

<sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.

Para obtener más información sobre eventos en directo, vaya a [Eventos en directo de Teams](teams-live-events/plan-for-teams-live-events.md#teams-live-events). Consulte [Programar un evento en directo de Teams](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)

> [!IMPORTANT]
> **Aumentamos el límite de eventos en directo de Microsoft 365**
>
> **Para seguir apoyando las necesidades de nuestros clientes, ampliaremos los aumentos temporales de los eventos en directo hasta el 30 de junio de 2023, incluyendo:**
>
>- Soporte de eventos de hasta 20 000 asistentes
>- 50 eventos se pueden hospedar de forma simultánea en un espacio empresarial
>- Difusión de un evento de 16 horas de duración
>
> Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

## <a name="presence-in-outlook"></a>Presencia en Outlook

Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).

## <a name="storage"></a>Almacenamiento

Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.

> [!NOTE]
> Cada [canal privado](./private-channels.md) tiene su propio sitio de SharePoint (antes llamado "colección de sitios")

If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.

By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)

Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.

|Característica                 |Microsoft 365 Empresa Básico  |Microsoft 365 Empresa Estándar   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Almacenamiento                 |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización, además de 10 GB por cada licencia adquirida.   |1 TB por organización, además de 10 GB por cada licencia adquirida. |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización           |
|Almacenamiento de archivos de Teams  |Hasta 25 TB por sitio o grupo |Hasta 25 TB por sitio o grupo |Hasta 25 TB por sitio o grupo |Hasta 25 TB por sitio o grupo |Hasta 25 TB por sitio o grupo |Hasta 25 TB por sitio o grupo |
|Límite de carga de archivos (por archivo)    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |

Los canales están respaldados por carpetas dentro del sitio de SharePoint Online (antes llamado "colección de sitios") creadas para el equipo, por lo que las pestañas de archivo de los canales comparten los límites de almacenamiento del equipo al que pertenezcan.

Para obtener más información, vea [Límites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="class-teams"></a>Equipos de clase

Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

Un equipo de clase es un tipo de plantilla con aplicaciones adicionales incluidas y con límites separados para el número de miembros del equipo.

> [!NOTE]
> Se requiere una [Licencia de Microsoft Office 365 para el ámbito educativo](https://www.microsoft.com/education/products/office) para usar los equipos de clase.

En la siguiente tabla se muestran los límites de los equipos de clase:

|Característica  |Límite máximo  |
|---------|---------|
|Número de miembros de un equipo    | Vea la sección [Equipos y canales](#teams-and-channels) de este artículo        |
|Número de miembros que pueden usar Tareas en un equipo de clase    | 300        |
|Número de miembros para usar un Bloc de notas de clase de OneNote en un equipo de clase     |300         |

A class team can support more than 300 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.

## <a name="tags"></a>Etiquetas

|Característica  |Límite máximo  |
|---------|---------|
|Número de etiquetas por equipo    | 100        |
|Número de etiquetas predeterminadas sugeridas por equipo    | 25        |
|Número de miembros del equipo asignados a una etiqueta    |200         |
|Número de etiquetas asignadas a un usuario por equipo    |25         |

## <a name="contacts"></a>Contactos

Teams usa los siguientes contactos:

- Contactos en Active Directory de su organización
- Contactos agregados a la carpeta predeterminada de Outlook del usuario

Los usuarios de Teams pueden comunicarse con cualquier usuario de Active Directory de su organización y pueden agregar como contacto a cualquier usuario de Active Directory de su organización y a sus listas de contactos en **Chat** > **Contactos** o **Llamadas** > **Contactos**.

Los usuarios de Teams también pueden agregar como contacto a un usuario que no se encuentra en Active Directory de su organización en **Llamadas** > **Contactos**.

## <a name="browsers"></a>Exploradores

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Sistemas operativos

Para obtener información sobre los requisitos del sistema operativo, consulte [Obtener clientes para Microsoft Teams](get-clients.md).

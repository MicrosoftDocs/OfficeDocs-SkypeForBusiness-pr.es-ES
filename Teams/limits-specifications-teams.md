---
title: Límites y especificaciones para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Este artículo describe los límites, especificaciones y otros requisitos que se aplican a Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28a77271c66dc473dfb774db2c02ca80bc842587
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "43950975"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Límites y especificaciones para Microsoft Teams

Este artículo describe algunos de los límites, especificaciones y otros requisitos que se aplican a Teams.

## <a name="teams-and-channels"></a>Equipos y canales

|Característica    | Límite máximo |
|-----------|---------------|
|Número de equipos que un usuario puede crear | Sujeto a un límite de 250 objetos&sup1;         |
|Número de equipos en los que un usuario puede ser un miembro de|1 000 |
|Número de miembros de un equipo | 5,000       |
|Número de propietarios por equipo | 100   |
|Número de equipos de la organización que se pueden usar en un espacio empresarial | 5     |
|Número de miembros de un [equipo de toda la organización](create-an-org-wide-team.md) | 5 000       |
|Número de equipos que un administrador global puede crear        |  500 000   |
|Cantidad de equipos que puede tener una organización de Office 365    | 500 000&sup2;     |
|Número de canales por equipo    | 200 (incluye canales eliminados)&sup3;         |
|Número de cadenas privadas por equipo    |30|
|Tamaño de publicación de conversación de canal | Aproximadamente 28 KB por publicación<sup>4</sup> |

&sup1; Cualquier objeto de directorio en Azure Active Directory cuenta para este límite. Los administradores globales están exentos de este límite, al igual que las aplicaciones que llaman a Microsoft Graph usando[permisos de aplicación](https://docs.microsoft.com/graph/permissions-reference).

&sup2; Este límite incluye los equipos archivados.

&sup3; Los canales borrados pueden ser restaurados en un plazo de 30 días. Durante estos 30 días, se sigue contando el canal eliminado en el límite de 200 canales por equipo. Después de 30 días, un canal eliminado y su contenido se eliminan de forma permanente y se deja de contar el canal en el límite de 200 canales por equipo.

<sup>4</sup> 28 KB es un límite aproximado, ya que incluye el mensaje en sí (texto, vínculos a imágenes, etc.), las @menciones, el número de conectores y las reacciones.

## <a name="messaging"></a>Mensajería 

### <a name="chat"></a>Chat

Los usuarios que participan en conversaciones que forman parte de la lista de chats de Microsoft Teams deben tener un buzón de Exchange Online (en la nube) para que un administrador busque conversaciones de chat. Esto sucede porque las conversaciones que son parte de la lista de chats se almacenan en los buzones en la nube de los participantes del chat. Si un participante del chat no tiene un buzón de Exchange Online, el administrador no podrá buscar o establecer una suspensión en las conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con buzones locales podrían participar en conversaciones que forman parte de la lista de chats de Teams. Pero en este caso, el contenido de estas conversaciones no se puede buscar y no se puede colocar en espera, ya que los usuarios no tienen buzones en la nube. (Para obtener más información, vea [Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md)).

El chat de Teams funciona en un servidor backend de Microsoft Exchange, por lo que los límites de mensajes de Exchange se aplican a la función de chat de Teams.

|Característica  | Límite máximo  |
|---------|---------|
|Número de usuarios en un chat privado<sup>1</sup>  | 100    |
|Cantidad de personas en una llamada de audio o vídeo desde el chat | 20 |
|Cantidad de datos adjuntos de archivo<sup>2</sup>  |10     |
|Tamaño de chat | Aproximadamente 28 KB por publicación<sup>3</sup> |

<sup>1</sup> Si tienes más de 20 personas en un chat, las siguientes funciones de chat están desactivadas: Respuestas automáticas de Outlook y mensajes de estado de los equipos; indicador de escritura; llamadas de vídeo y audio; compartir; leer recibos.

<sup>2</sup> Si el número de archivos adjuntos supera este límite, aparecerá un mensaje de error.

<sup>3</sup> 28 KB es un límite aproximado, ya que incluye el mensaje en sí (texto, vínculos a imágenes, etc.), las @menciones y las reacciones.

### <a name="emailing-a-channel"></a>Enviar un correo electrónico a un canal

 Si los usuarios quieren enviar un correo electrónico a un canal en Teams, pueden hacerlo mediante la dirección de correo electrónico del canal. Cuando un correo electrónico forma parte de un canal, cualquier persona puede responder para iniciar una conversación. Estos son algunos de los límites correspondientes para enviar correo electrónico a un canal.

|Característica  | Límite máximo  |
|---------|---------|
|Tamaño del mensaje<sup>1<sup> | 24 KB |
|Número de datos adjuntos de archivo<sup>2</sup>  |20     |
|Tamaño de los datos adjuntos del archivo | Menos de 10 MB |
|Número de imágenes insertadas<sup>2</sup> |50   |

<sup>1</sup> Si el mensaje excede este límite, se genera un mensaje de vista previa y se le pide al usuario que descargue y vea el correo electrónico original desde el enlace proporcionado.

<sup>2</sup> Si el número de archivos adjuntos o imágenes supera este límite, aparecerá un mensaje de error.

Para más información, vea [Límites de Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Los límites de tamaño de los mensajes, datos adjuntos e imágenes insertadas son iguales en todas las licencias de Office 365.

## <a name="channel-names"></a>Nombres de canal

Los nombres de canal no pueden contener los siguientes caracteres o palabras:

|||
|---------|---------|
|Caracteres     | ~ # % & * { } + / \ : < > ? &#124; ' " ..        |
|Caracteres en estos rangos    | 0 a 1F<br>80 a 9F        |
|Palabras     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;|

Los nombres de canal tampoco pueden empezar con un carácter de subrayado (_) o un punto (.), ni terminar con un punto (.).

## <a name="meetings-and-calls"></a>Reuniones y llamadas

|Característica     | Límite máximo |
|------------|---------------|
|Número de personas en una reunión  | 250    |
|Cantidad de personas en una llamada de audio o vídeo desde el chat | 20 |
|Tamaño máximo de archivo de PowerPoint | 2 GB|
|Teams guarda [grabaciones de la reunión](cloud-recording.md) que no se cargan en Microsoft Stream, que se pueden descargar de forma local | 20 días |

### <a name="meeting-expiration"></a>Expiración de la reunión

|Tipo de reunión  |La reunión expira después de esta cantidad de tiempo  |Cada vez que se inicia o actualiza una reunión, la expiración se extiende por este tiempo  |
|---------|---------|---------|
|Reunirse ahora     |Hora de inicio + 8 horas         |N/D         |
|Regular sin hora de finalización     |Hora de inicio + 60 días         | 60 días        |
|Regular con hora de finalización     |Hora de finalización + 60 días         |60 días         |
|Periódica sin hora de finalización     |Hora de inicio + 60 días         |60 días         |
|Periódica con hora de finalización     |Hora de finalización de la última repetición + 60 días         |60 días         |

## <a name="teams-live-events"></a>Eventos en directo en Teams

|Característica     | Límite máximo |
|------------|---------------|
|Tamaño de público | 10 000 asistentes |
|Duración del evento | 4 horas |
|Eventos en directo simultáneos en una organización de Office 365 | 15 |

Para obtener más información sobre los eventos en directo y una comparación de los eventos en directo de Teams y la Difusión de reunión de Skype, vaya a [Eventos en directo de Teams y Difusión de reunión de Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).

> [!IMPORTANT]
> **Aumentamos el límite de eventos en directo de Microsoft 365**
> 
> Para ayudar a los clientes a cumplir con unas necesidades de comunicación que cambian cada día, los eventos en directo de Microsoft 365 Live elevarán temporalmente sus límites predeterminados hasta el 1 de julio de 2020 para eventos en directo alojados en Teams. A finales de abril de 2020 se comenzaron a elevar los siguientes límites:
> - Límite de asistentes: los eventos pueden dar cabida a hasta 20 000 asistentes.
> - Eventos simultáneos: 50 eventos se pueden hospedar de forma simultánea en un espacio empresarial.
> - Duración del evento: se ha aumentado la duración del evento hasta a 16 horas por difusión.



## <a name="presence-in-outlook"></a>Presencia en Outlook

La presencia de Teams en Outlook es compatible con la aplicación de escritorio Outlook 2013 y posteriores. Para obtener más información acerca de la presencia en equipos, consulte [Presencia de usuarios en Teams](presence-admins.md).

## <a name="storage"></a>Almacenamiento

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.

Si no tiene habilitado SharePoint Online en su espacio empresarial, los usuarios de Microsoft Teams no podrán compartir archivos en los equipos. Los usuarios de chats privados tampoco podrán compartir archivos, porque se necesita OneDrive para la Empresa (que está ligado a la licencia de SharePoint) para esa funcionalidad.

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino. (Para obtener más información, vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md)).

Ya que Teams se ejecuta en un back-end de SharePoint Online para compartir archivos, las limitaciones de SharePoint se aplican a la sección Archivos en un equipo. Estos son los límites de almacenamiento correspondientes para SharePoint Online.

|Característica                 |Microsoft 365 Empresa Básico  |Microsoft 365 Empresa Estándar   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Almacenamiento                 |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización, además de 10 GB por cada licencia adquirida.   |1 TB por organización, además de 10 GB por cada licencia adquirida. |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización           |
|Almacenamiento de archivos de Teams  |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |Hasta 25 TB por grupo o colección de sitios. |
|Límite de carga de archivos (por archivo)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Las copias de seguridad de los canales se encuentran en carpetas dentro de la colección de sitios de SharePoint Online que se creó para el equipo, por lo que las pestañas de archivo de los canales comparten los límites de almacenamiento del equipo al que pertenecen.

Para obtener más información, vea [Límites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="tags"></a>Etiquetas

|Característica  |Límite máximo  |
|---------|---------|
|Número de etiquetas por equipo    | 100        |
|Número de etiquetas predeterminadas sugeridas por equipo    | 25        |
|Número de miembros del equipo que se asignan a una etiqueta    |100         |
|Número de etiquetas asignadas a un usuario    |25         |

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

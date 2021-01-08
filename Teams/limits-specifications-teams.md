---
title: Límites y especificaciones para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: Este artículo describe los límites, especificaciones y otros requisitos que se aplican a Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b64042a318e6967523e80e62d1cca429bc7f7e88
ms.sourcegitcommit: f1f3b5220c4b411f2001fbdcbe25ae7c14b94df6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49776851"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Límites y especificaciones para Microsoft Teams

Este artículo describe algunos de los límites, especificaciones y otros requisitos que se aplican a Teams.

## <a name="teams-and-channels"></a>Equipos y canales

|Característica    | Límite máximo |
|-----------|---------------|
|Número de equipos que un usuario puede crear | Sujeto a un límite de 250 objetos&sup1;         |
|Número de equipos en los que un usuario puede ser un miembro de|1 000&sup2;|
|Número de miembros de un equipo | 10 000<sup>5</sup>     |
|Número de propietarios por equipo | 100   |
|Número de equipos de la organización que se pueden usar en un espacio empresarial | 5     |
|Número de miembros de un [equipo de toda la organización](create-an-org-wide-team.md) | 5 000       |
|Número de equipos que un administrador global puede crear        |  500 000   |
|Cantidad de equipos que puede tener una organización de Microsoft 365 y Office 365    | 500 000&sup2;     |
|Número de canales por equipo    | 200 (incluye canales eliminados)&sup3;         |
|Número de cadenas privadas por equipo    |30| (incluye canales eliminados)&sup3;
|Número de miembros de un canal privado    |250|
|Tamaño máximo de lista de distribución, grupo de seguridad o grupo de Office 365 que puede importarse a un equipo    |3500|
|Número máximo de miembros de un grupo de Office 365 que se pueden convertir en un equipo    |10 000<sup>5</sup>     |
|Tamaño de publicación de conversación de canal | Aproximadamente 28 KB por publicación<sup>4</sup> |

<sup>1</sup> Cualquier objeto del directorio de Azure Active Directory cuenta para este límite. Los administradores globales están exentos de este límite, al igual que las aplicaciones que llamen a Microsoft Graph usando los [permisos de la aplicación](https://docs.microsoft.com/graph/permissions-reference).

<sup>2</sup> Este límite incluye equipos archivados. Para sobrepasar el número máximo de equipos que puede tener una organización de Microsoft 365 u Office 365, debe contactar con el soporte de Microsoft.

<sup>3</sup> Los canales eliminados se pueden restaurar en un plazo de 30 días. Durante estos 30 días, el canal eliminado seguirá contando dentro del límite de 200 canales o 30 canales privados por equipo. Después de los 30 días, el canal eliminado y su contenido serán eliminados permanentemente y el canal ya no contará para el límite por equipo.

<sup>4</sup> 28 KB es un límite aproximado, ya que incluye al mensaje en sí (texto, vínculos de la imagen, etc.), las @menciones, el número de conectores y las reacciones.

<sup>5</sup> Microsoft Teams en GCC solo puede aceptar 5 000 miembros y los equipos en GCCH/DoD solo pueden aceptar 2 500 miembros.

## <a name="messaging"></a>Mensajería 

### <a name="chat"></a>Chat

Los usuarios que participen en las conversaciones que forman parte de la lista de chats en Teams deben tener un buzón de Exchange Online (basado en la nube) para que el administrador pueda buscar en las conversaciones de chat. Esto se debe a que las conversaciones que forman parte de la lista de chat se almacenan en los buzones de los participantes del chat basados en la nube. Si algún participante del chat no tiene buzón de Exchange Online, el administrador no podrá buscar ni suspender la conversación. Por ejemplo, en una implementación híbrida de Exchange, es posible que los usuarios con buzones locales puedan participar en conversaciones que formen parte de la lista de chat en Teams. Sin embargo, en este caso, el contenido de estas conversaciones no es susceptible de búsqueda y no se puede suspender, ya que los usuarios carecen de buzones basados en la nube. Para obtener más información, consulte [Cómo interactúan Exchange y Microsoft Teams](exchange-teams-interact.md).

El chat de Teams funciona en un servidor back-end de Microsoft Exchange, por lo que los límites de mensajes de Exchange se aplican a la función de chat dentro de Teams.

|Característica  | Límite máximo  |
|---------|---------|
|Número de usuarios en un chat privado<sup>1</sup>  | 250<sup>2</sup> |
|Cantidad de personas en una llamada de audio o vídeo desde el chat | 20 |
|Número de datos adjuntos de archivos<sup>3</sup>  |10     |
|Tamaño de chat | Aproximadamente 28 KB por publicación<sup>4</sup> |

<sup>1</sup> Si tiene más de 20 contactos en un chat, se desactivarán las siguientes características del chat: mensajes de respuesta automáticos de Outlook y de estado de Teams; indicador de escritura; llamadas de audio y vídeo; uso compartido; confirmaciones de lectura. El botón de "Establecer opciones de entrega" (!) también desaparece cuando hay más de 20 miembros en los chats de grupo privado.

<sup>2</sup> Solo se pueden agregar a una conversación de grupo 200 miembros cada vez. [Consulte este artículo para obtener más información](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> Si el número de archivos adjuntos supera este límite, aparecerá un mensaje de error.

<sup>4</sup> 28 KB es un límite aproximado, ya que incluye el mensaje en sí (texto, vínculos a imágenes, etc.), las @menciones y las reacciones.

### <a name="emailing-a-channel"></a>Enviar un correo electrónico a un canal

 Si los usuarios desean enviar un correo electrónico a un canal en Teams, pueden usar la dirección de correo electrónico del canal. Cuando un correo electrónico forma parte de un canal, cualquiera puede responder a él para iniciar una conversación. Estos son algunos de los límites aplicables para enviar correos electrónicos a los canales.

|Característica  | Límite máximo  |
|---------|---------|
|Tamaño del mensaje<sup>1<sup> | 24 KB |
|Número de datos adjuntos de archivo<sup>2</sup>  |20     |
|Tamaño de los datos adjuntos del archivo | Menos de 10 MB |
|Número de imágenes insertadas<sup>2</sup> |50   |

<sup>1</sup> Si el mensaje excede este límite, se genera un mensaje de vista previa y se le pide al usuario que descargue y vea el correo electrónico original desde el enlace proporcionado.

<sup>2</sup> Si el número de archivos adjuntos o imágenes supera este límite, aparecerá un mensaje de error.

Para más información, consulte [Límites de Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Los límites de tamaño de los mensajes, datos adjuntos e imágenes incorporadas son iguales en todas las licencias de Microsoft 365 y Office 365. Para las organizaciones GCC/GCCH/DOD de Office no es posible enviar correos electrónicos a un canal en Teams.

## <a name="channel-names"></a>Nombres del canal

Los nombres de los canales no pueden contener ninguno de los siguientes caracteres o palabras:

|Tipo|Ejemplo|
|---------|---------|
|Caracteres     | ~ # % & * { } + / \ : < > ? &#124; ' " , .        |
|Caracteres en estos rangos    | 0 a 1F<br>80 a 9F        |
|Palabras     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;|

Los nombres de canal tampoco pueden empezar con un carácter de subrayado (_) o un punto (.), ni terminar con un punto (.).

## <a name="meetings-and-calls"></a>Reuniones y llamadas

> [!IMPORTANT]
> **Aumentamos el límite de eventos en directo de Microsoft 365**
>
> **Para continuar cubriendo las necesidades de nuestros clientes, hasta el 30 de junio de 2021, extenderemos los aumentos de los límites temporales para los eventos en vivo, incluyendo**:
>
>- Soporte de eventos de hasta 20 000 asistentes
>- 50 eventos se pueden hospedar de forma simultánea en un espacio empresarial
>- Difusión de un evento de 16 horas de duración
>
> Además, los eventos en directo con hasta 100 000 asistentes pueden planearse con el programa de asistencia de Microsoft 365. El equipo evaluará cada solicitud y trabajará con usted para determinar las opciones disponibles. [Obtenga más información](https://aka.ms/Stream/Blog/LiveEventOptions).

|Característica     | Límite máximo |
|------------|---------------|
|Número de personas en una reunión (pueden chatear y llamar)  | 300 |
|Cantidad de personas en una llamada de audio o vídeo que se ha originado desde la pestaña de chat | 20 |
|Tamaño máximo de los archivos de PowerPoint | 2 GB|
|Teams guarda las [grabaciones de la reunión](cloud-recording.md) que no se cargan en Microsoft Stream y las deja disponibles para descarga local | 20 días |

>[!Note]
> El cambio de uso desde Microsoft Stream a [OneDrive para la Empresa y SharePoint para grabar las reuniones](tmr-meeting-recording-change.md) estará basado en fases. Durante el lanzamiento podrá participar en esta experiencia, en noviembre tendrá que cancelar la suscripción si desea continuar usando Stream y por un tiempo, a principios de 2021, requeriremos que todos los clientes usen OneDrive para la Empresa y SharePoint para grabar nuevas reuniones.

### <a name="meeting-expiration"></a>Expiración de la reunión

|Tipo de reunión  |La reunión expira después de esta cantidad de tiempo  |Cada vez que se inicia o actualiza una reunión, la expiración se extiende por este tiempo  |
|---------|---------|---------|
|Reunirse ahora     |Hora de inicio + 8 horas         |N/D         |
|Regular sin hora de finalización     |Hora de inicio + 60 días         | 60 días        |
|Regular con hora de finalización     |Hora de finalización + 60 días         |60 días         |
|Periódica sin hora de finalización     |Hora de inicio + 60 días         |60 días         |
|Periódica con hora de finalización     |Hora de finalización de la última repetición + 60 días         |60 días         |

> [!NOTE]
> Las reuniones de Microsoft Teams tienen un límite de tiempo de 24 horas.

## <a name="teams-live-events"></a>Eventos en directo en Teams

|Característica     | Límite máximo |
|------------|---------------|
|Tamaño de público | 10 000 asistentes |
|Duración del evento | 4 horas |
|Eventos en directo simultáneos ejecutándose en una organización de Microsoft 365 y Office 365 <sup>1</sup> | 15 |

<sup>1</sup> Puede programar todos los eventos en directo que quiera, pero solo puede ejecutar 15 a la vez. Tan pronto como el productor se una a un evento en directo, se considerará que ya está en ejecución. Si un productor intenta unirse a un decimosexto evento en directo, recibirá un mensaje de error.

Para obtener más información acerca de los eventos en directo y una comparación de los eventos en directo de Teams con la Difusión de reunión de Skype, vaya a [Eventos en directo de Teams y Difusión de reunión de Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). Consulte también [Programar un evento en directo de Teams](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

> [!IMPORTANT]
> **Aumento del límite de eventos en directo de Microsoft 365**
>
> **Para continuar cubriendo las necesidades de nuestros clientes, hasta el 30 de junio de 2021, extenderemos los aumentos de los límites temporales para los eventos en vivo, incluyendo**:
>
>- Soporte de eventos de hasta 20 000 asistentes
>- 50 eventos se pueden hospedar de forma simultánea en un espacio empresarial
>- Difusión de un evento de 16 horas de duración
>
> Además, los eventos en directo con hasta 100 000 asistentes pueden planearse con el programa de asistencia de Microsoft 365. El equipo evaluará cada solicitud y trabajará con usted para determinar las opciones disponibles. [Obtenga más información](https://aka.ms/Stream/Blog/LiveEventOptions). 

## <a name="presence-in-outlook"></a>Presencia en Outlook

La presencia de Teams en Outlook es compatible con la aplicación de escritorio de Outlook 2013 y posteriores. Para obtener más información sobre la presencia en Teams, consulte [Presencia del usuario en Teams](presence-admins.md).

## <a name="storage"></a>Almacenamiento

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.

> [!NOTE]
> Cada [canal privado](https://docs.microsoft.com/microsoftteams/private-channels) tiene su propio sitio de SharePoint (antes llamado "colección de sitios")

Si no tiene SharePoint Online habilitado en su espacio empresarial, los usuarios de Microsoft Teams no siempre podrán compartir archivos en los equipos. Los usuarios en el chat privado tampoco podrán compartir archivos, ya que se necesita OneDrive para la Empresa (el cual está vinculado a la licencia de SharePoint) para dicha función.

Al almacenar los archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se seguirán todas las reglas de cumplimiento configuradas en el nivel del espacio empresarial. Para obtener más información, consulte [Cómo interactúan SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md).

Como Teams se ejecuta en un servidor de back-end de SharePoint Online para el uso compartido de archivos, se aplican las limitaciones de SharePoint a la sección de Archivos en Teams. Aquí se muestran los límites de almacenamiento aplicables para SharePoint Online.

|Característica                 |Microsoft 365 Empresa Básico  |Microsoft 365 Empresa Estándar   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Almacenamiento                 |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización, además de 10 GB por cada licencia adquirida.   |1 TB por organización, además de 10 GB por cada licencia adquirida. |1 TB por organización, además de 10 GB por cada licencia adquirida.  |1 TB por organización           |
|Almacenamiento de archivos de Teams  |Hasta 25 TB por sitio o grupo |Hasta 25 TB por sitio o grupo |Hasta 25 TB por sitio o grupo |Hasta 25 TB por sitio o grupo |Hasta 25 TB por sitio o grupo |Hasta 25 TB por sitio o grupo |
|Límite de carga de archivos (por archivo)    |100 GB    |100 GB    |100 GB    |100 GB    |100 GB    |100 GB    |

Los canales están respaldados por carpetas dentro del sitio de SharePoint Online (antes llamado "colección de sitios") creadas para el equipo, por lo que las pestañas de archivo de los canales comparten los límites de almacenamiento del equipo al que pertenezcan.

Para obtener más información, vea [Límites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="class-teams"></a>Equipos de clase

Microsoft Teams para el ámbito educativo ofrece plantillas diseñadas para escenarios educativos únicos, como la enseñanza en clase. Puede obtener más información sobre los tipos de equipo, incluidos los equipos de clase, en [Elija un tipo de equipo para colaborar en Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

Un equipo de clase es un tipo de plantilla con aplicaciones adicionales incluidas y con límites separados para el número de miembros del equipo.

> [!NOTE]
> Se requiere una [Licencia de Microsoft Office 365 para el ámbito educativo](https://www.microsoft.com/education/products/office) para usar los equipos de clase.

En la siguiente tabla se muestran los límites de los equipos de clase:

|Característica  |Límite máximo  |
|---------|---------|
|Número de miembros de un equipo    | Vea la sección [Equipos y canales](#teams-and-channels) de este artículo        |
|Número de miembros que pueden usar Tareas en un equipo de clase    | 200        |
|Número de miembros para usar un Bloc de notas de clase de OneNote en un equipo de clase     |200         |

Un equipo de clase puede admitir a más de 200 miembros. Sin embargo, si tiene previsto usar la aplicación Tareas o la aplicación Bloc de notas de clase en su equipo, tendrá que mantener el número de miembros por debajo de los límites máximos anteriores.

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

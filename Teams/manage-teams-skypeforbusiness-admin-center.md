---
title: Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Aprenda a administrar la configuración de todos los inquilinos y usuarios de Teams durante la transición de la experiencia de Teams en el centro de administración de Microsoft 365 al nuevo centro de administración de Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 0d473ffa67b21c4ec3a160a8687a1688ea1d1cf5
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "37564788"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>¿Qué es el nuevo centro de administración de Microsoft Teams?  

La nueva experiencia del centro de administración le proporcionará una experiencia unificada para administrar tanto los equipos como Skype empresarial. Ofrecemos funciones adicionales, información completa y la capacidad de administrar la configuración de Teams en un nivel de usuario.

![Captura de pantalla del centro de administración de Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Configuración migrada al nuevo centro de administración de Microsoft Teams

La siguiente tabla identifica las secciones de la experiencia de teams que se han migrado y muestra la relación entre la configuración actual y las directivas del nuevo portal de administración.

|Sección de Teams en el centro de administración de Microsoft 365  |Nombre de configuración (nivel de inquilino)  |Directiva del centro de administración de Microsoft Teams   |Nivel: inquilino o usuario   |
|---------|---------|---------|---------|
|General     |Mostrar organigrama en el perfil personal        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Espacios       |
|General     |Usar Skype empresarial para los destinatarios que no tienen equipos         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Espacios         |
|Integración de correo electrónico     |Permitir que los usuarios envíen correos electrónicos a los canales         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Espacios         |
|Integración de correo electrónico     |Lista de remitentes permitidos         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Espacios         |
|Almacenamiento en nube personalizado     |Rectángulo         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Espacios         |
|Almacenamiento en nube personalizado     |FTP        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Espacios         |
|Almacenamiento en nube personalizado     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Espacios         |
|Almacenamiento en nube personalizado     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Espacios         |
|Configuración por usuario o tipo de licencia     |Activar o desactivar Microsoft Teams para todos los usuarios          |Obsoleto<sup>1</sup>        |         |
|Equipos y canales     |         |Redirige a la administración de grupos de Azure Active Directory (igual que la experiencia actual).              |Usuario         |
|Equipos y canales     |         |Redirige a la administración de grupos de AAD (igual que la experiencia actual).             |Usuario          |
|Aplicaciones|Habilitar nuevas aplicaciones externas de manera predeterminada|Configuración de la aplicación en toda la organización|Espacios|
|Aplicaciones|Permitir aplicaciones externas|Configuración de la aplicación en toda la organización|Espacios|
|Aplicaciones|Permitir la transferencia local de aplicaciones externas<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Usuario|
|Aplicaciones|Aplicaciones predeterminadas<sup>3</sup>|TeamsAppPermissionPolicy|Usuario|
|Aplicaciones|Aplicaciones externas<sup>3</sup>|TeamsAppPermissionPolicy|Usuario|
|Llamadas y reuniones     |Permitir la programación de reuniones privadas         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir Meetup de canal ad hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir la programación de reuniones de canal         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir vídeos en reuniones         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir la pantalla compartida en reuniones         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir llamadas privadas         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Usuario          |
|Mensajería      |Habilitar Giphy para que los usuarios puedan agregar GIF a las conversaciones         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Clasificación de contenido         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Habilitar los memes que los usuarios pueden editar y agregar a las conversaciones         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Habilitar adhesivos que los usuarios pueden editar y agregar a conversaciones         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir que los propietarios eliminen todos los mensajes         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir que los usuarios editen sus propios mensajes         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir que los usuarios eliminen sus propios mensajes         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permite que los usuarios puedan chatear de forma privada         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |

<sup>1</sup> desusado para invitados. Habilitar o deshabilitar invitado ahora se puede administrar en el centro de administración de Microsoft Teams. La habilitación o deshabilitación de Teams para empresas, los estudiantes de edu y los profesores de edu estarán obsoletas próximamente. Esto debe administrarse mediante la asignación de licencias en el centro de administración de Microsoft 365. Consulte [administrar el acceso de usuarios a Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> la transferencia local se divide de la siguiente manera:

- Permitir a un usuario transferir aplicaciones que se pueden administrar a nivel de usuario en [TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
- Permita que los usuarios de un inquilino interactúen con aplicaciones personalizadas que se pueden administrar en el nivel de inquilino en la configuración de la aplicación de toda la organización.
 
<sup>3</sup> las aplicaciones predeterminadas y las aplicaciones externas se pueden habilitar y deshabilitar en el nivel de usuario en TeamsAppPermissionPolicy. Además, las aplicaciones se pueden bloquear en el nivel de espacio empresarial en la configuración de la aplicación de toda la organización, que reemplaza cualquier configuración de usuario y de nivel de inquilino. 

> [!NOTE]
> Continuará usando el panel grupos en el centro de administración de Microsoft 365 para la configuración relacionada con equipos y canales. La configuración de las aplicaciones permanecerá en el área de equipos del centro de administración de Microsoft 365 y se migrará más tarde. 

## <a name="manage-settings-during-the-migration"></a>Administrar la configuración durante la migración

Puede continuar modificando la configuración en el centro de administración de Microsoft 365 y en el centro de administración de Skype empresarial hasta que se complete la migración de una sección para su inquilino. 

En la tabla siguiente se muestra dónde puede administrar características durante la migración.

|Característica  |Centro de administración de Microsoft Teams                      |Centro de administración de Skype empresarial (heredado)  |Centro de administración de Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Directivas de mensajería, reuniones y eventos en directo de Teams     |     X    |         |         |
|Directiva de actualización de Teams     |    X     |         |         |
|Configuración de invitado para mensajería, reuniones y voz     |   X      |         |         |
|Administración del ciclo de vida de Teams   |    X    |      |       |
|Configuración de Teams   |    X    |      |       |
|Configuración de acceso externo     |    X    |      |       |
|Administración de usuarios    |         |         |    X     |    
|Audioconferencia     |    X     |    X     |         |
|Planes de llamada     |         |    X     |         |
|Sistema telefónico    |         |     X    |         |
|Administración de números de teléfono     |         |   X      |         |
|Licencias para características de voz en la nube     |         |         |    X     |
|Operadores automáticos     |         |    X     |         |
|Colas de llamadas     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Administrar la configuración después de la migración

Cuando haya finalizado la migración de esta configuración, la deshabilitaremos en el centro de administración de Office 365 y en el centro de administración de Skype empresarial, y se podrán administrar en el nuevo centro de administración de Microsoft Teams.


## <a name="edu-migration-june-july-2019"></a>Migración de EDU de junio a 2019 de julio

Durante el 2019 de junio y julio, los inquilinos restantes de EDU se migrarán de la antigua experiencia de administrador (en el centro de administración de Microsoft 365) al centro de administración de Teams. Consulte el centro de mensajes (en el centro de administración de Microsoft 365) para saber cuándo se migrará. Esto es lo que verá después de migrar:

|Sección de Teams en el centro de administración de Microsoft 365  |Nombre de configuración (nivel de inquilino)  |Directiva del centro de administración de Microsoft Teams   |Nivel: inquilino o usuario   |
|---------|---------|---------|---------|  
| Mensajería   |Los propietarios pueden eliminar los mensajes enviados |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |
| Mensajería  | Los usuarios pueden eliminar mensajes enviados |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |
| Mensajería   | Los usuarios pueden editar mensajes enviados |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)  |Usuario|
| Mensajería  | Permitir que los usuarios puedan chatear |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |
| Mensajería  | Usar imágenes giphy en conversaciones | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |
| Mensajería  | Clasificación de contenido de Giphy | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |
| Mensajería  | Usar memes en las conversaciones  |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |
| Mensajería  | Usar adhesivos en las conversaciones |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |

Además, estas son las opciones de configuración que solo están disponibles en el centro de administración de Microsoft Teams:

|Nombre de configuración | Directiva del centro de administración de Microsoft Teams | Nivel: inquilino o usuario
|-------------|-------------------------------------|---------|
|Permitir vistas previas de direcciones URL | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |
|Permitir a un usuario quitar usuarios de un chat grupal |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |
|Permitir el lector inmersivo para ver mensajes |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| Usuario |
|Permitir que los usuarios traduzcan mensajes |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)| Usuario |
|Confirmaciones de lectura | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |
|Los usuarios pueden enviar notificaciones prioritarias | [TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) | Usuario |
|Creación de mensajes de voz |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| Usuario |
|En dispositivos móviles, Mostrar canales favoritos por encima de los chats recientes |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)| Usuario |

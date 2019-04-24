---
title: Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Entender cómo administrar todo el inquilino y configuración del usuario para los equipos durante la transición de los equipos de la experiencia en el centro de administración de Office 365 para el nuevo centro de administración de Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 9f1adb47709d3e053bb2349d8a3e548bedc58d9d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199570"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>¿Qué es el nuevo centro de administración de Microsoft Teams?  

La nueva experiencia del centro de administración le proporcionará una experiencia unificada para administrar los equipos y Skype para la empresa. Ofrecemos una funcionalidad adicional, entendimiento de extremo a otro y la capacidad para administrar la configuración de los equipos en un nivel de usuario.

![Captura de pantalla del centro de administración de equipos de Microsoft.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>La configuración de migrar al nuevo centro de administración de Microsoft Teams

En la siguiente tabla identifica las secciones de la experiencia de los equipos que se han migrado y se muestran la relación entre la configuración actual y las directivas en el nuevo portal de administración.

|Sección de los equipos en el centro de administración de Office 365  |Nombre de la configuración (nivel de inquilino)  |Directiva de centro de administración de Microsoft Teams   |Nivel: Usuario o inquilino   |
|---------|---------|---------|---------|
|General     |Mostrar Chat organizativa en perfil Personal        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Inquilino       |
|General     |Usar Skype para la empresa para los destinatarios que no tienen los equipos         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Integración de correo electrónico     |Permitir a los usuarios enviar correos electrónicos a canales         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Integración de correo electrónico     |Permitir que los remitentes lista         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Inquilino         |
|Almacenamiento en nube personalizado     |Cuadro de         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |Lista desplegable        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |Unidad de Google        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Configuración por tipo de licencia de usuario o     |Activar Microsoft Teams activado o desactivado para todos los usuarios          |En desuso<sup>1</sup>        |         |
|Equipos y canales     |         |Redirecciones a Azure grupo Administración de Active Directory (igual que la experiencia actual).              |Usuario         |
|Equipos y canales     |         |Redirige a la administración de grupo de AAD (igual que la experiencia actual).             |Usuario          |
|Aplicaciones|Habilitar nuevas aplicaciones externas de manera predeterminada|Configuración de aplicaciones de toda la organización|Inquilino|
|Aplicaciones|Permitir aplicaciones externas|Configuración de aplicaciones de toda la organización|Inquilino|
|Aplicaciones|Permitir sideloading de aplicaciones externas<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Usuario|
|Aplicaciones|De forma predeterminada aplicaciones<sup>3</sup>|TeamsAppPermissionPolicy|Usuario|
|Aplicaciones|<sup>3</sup> de aplicaciones externas|TeamsAppPermissionPolicy|Usuario|
|Las llamadas y las reuniones     |Permitir la programación de reuniones privadas         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Las llamadas y las reuniones     |Permitir meetup de canal Ad hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Las llamadas y las reuniones     |Permitir la programación de reuniones de canal         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Las llamadas y las reuniones     |Permitir vídeos en las reuniones         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Las llamadas y las reuniones     |Permitir el uso compartido en reuniones de pantalla         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Las llamadas y las reuniones     |Permitir llamadas privada         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Usuario          |
|Mensajería      |Habilitar Giphy, por lo que los usuarios pueden agregar archivos GIF a las conversaciones         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Clasificación de contenido         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Habilitar memes que los usuarios pueden editar y agregar a las conversaciones         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Habilitar a pegatinas que los usuarios pueden editar y agregar a las conversaciones         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir que los propietarios de eliminar todos los mensajes         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir a los usuarios editar sus propios mensajes de         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir a los usuarios eliminar sus propios mensajes de         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permite a los usuarios a conversaciones en privado         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |

<sup>1</sup> en desuso de invitado. Habilitación o deshabilitación de invitado ahora pueden administrarse en el centro de administración de Microsoft Teams. Habilitar o deshabilitar los equipos para profesionales de empresa, Edu estudiantes, y quedará obsoleto Edu profesores pronto. Esto debe administrarse mediante la asignación de licencias en el centro de administración de Office 365. Vea [administrar el acceso de usuarios a los equipos de Microsoft](user-access.md).
<br><br>
<sup>2</sup> Sideloading se divide de la siguiente manera:

- Permitir que a un usuario a las aplicaciones sideload que se pueden administrar en un nivel de usuario en [TeamsAppSetupPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
- Permitir a los usuarios en un inquilino para interactuar con aplicaciones personalizadas que se pueden administrar en un nivel de inquilino de la configuración de aplicaciones de toda la organización.
 
<sup>3</sup> aplicaciones predeterminadas y aplicaciones externas pueden ser habilitadas y deshabilitadas en el nivel de usuario en TeamsAppPermissionPolicy. Además, las aplicaciones se pueden bloquear en el nivel de inquilino en la configuración de aplicaciones de toda la organización que invalida cualquier configuración de nivel de inquilino y usuario. 

> [!NOTE]
> Podrá continuar usar el panel de grupos en el centro de administración de Office 365 para la configuración relacionada con los equipos y los canales. Configuración de aplicaciones permanecerá en el área de los equipos del centro de administración de Office 365 y se van a migrar más adelante. 

## <a name="manage-settings-during-the-migration"></a>Administración de la configuración durante la migración

Puede continuar modificar la configuración en el centro de administración de Office 365 y el Skype para el centro de administración de negocio hasta que se complete para el inquilino de migración para una sección. 

La siguiente tabla se muestra donde puede administrar las características durante la migración.

|Característica  |Centro de administración de Microsoft Teams                      |Skype para el centro de administración empresarial (heredada)  |Centro de administración de Office 365  |
|---------|:---------:|:---------:|:---------:|
|Los equipos de las directivas de mensajería, reuniones y eventos de Live Meeting     |     X    |         |         |
|Directiva de actualización de los equipos     |    X     |         |         |
|Configuración de invitado de mensajería, las reuniones y voz     |   X      |         |         |
|Administración del ciclo de vida de los equipos   |    X    |      |       |
|Configuración de los equipos   |    X    |      |       |
|Configuración del acceso externo     |    X    |      |       |
|Administración de usuarios    |         |         |    X     |    
|Audioconferencia     |    X     |    X     |         |
|Planes de llamada     |         |    X     |         |
|Sistema telefónico    |         |     X    |         |
|Administración de números de teléfono     |         |   X      |         |
|Concesión de licencias para las características de voz en la nube     |         |         |    X     |
|Operadores automáticos     |         |    X     |         |
|Colas de llamadas     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Administrar la configuración después de la migración

Una vez finalizada la migración de estas configuraciones, debe deshabilitarlas en el centro de administración de Office 365 y el Skype para el centro de administración de negocio y, a continuación, se pueden administrar en el nuevo centro de administración de Microsoft Teams.



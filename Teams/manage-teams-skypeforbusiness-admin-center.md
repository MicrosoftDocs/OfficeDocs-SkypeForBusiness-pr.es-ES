---
title: Administrar la transición de Teams al nuevo Centro de administración de Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de Teams para todos los inquilinos y usuarios durante la transición de Teams en el centro de administración de Microsoft 365 al nuevo Centro de administración de Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: ee63c3d49a8c4b4bf047f0df3910bec39a4d5541
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790422"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>¿Qué es el nuevo Centro de administración de Microsoft Teams?  

La nueva experiencia del Centro de administración le proporcionará una experiencia unificada para administrar Teams y Skype Empresarial. Ofrecemos funcionalidades adicionales, información de un extremo a otro y la capacidad de administrar la configuración de Teams a nivel de usuario.

![Captura de pantalla del Centro de administración de Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Configuración migrada al nuevo Centro de administración de Microsoft Teams

En la tabla siguiente se identifican las secciones de la experiencia de Teams que se han migrado y se muestra la relación entre la configuración actual y las directivas en el nuevo portal de administración.

|Sección de Teams en el Centro de administración de Microsoft 365  |Nombre de configuración (nivel de inquilino)  |Directiva del centro de administración de Microsoft Teams   |Nivel: inquilino o usuario   |
|---------|---------|---------|---------|
|General     |Mostrar organigrama en perfil personal        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Inquilino       |
|General     |Usar Skype Empresarial para destinatarios que no tienen Teams         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Integración de correo electrónico     |Permitir que los usuarios envíen correos electrónicos a canales         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Integración de correo electrónico     |Permitir la lista de remitentes         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Inquilino         |
|Almacenamiento en nube personalizado     |Box         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |Egnyte        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Configuración por tipo de usuario/licencia     |Activar o desactivar Microsoft Teams para todos los usuarios          |En<sup>desuso 1</sup>        |         |
|Equipos y canales     |         |Redirige a la administración de grupos de Azure Active Directory (igual que la experiencia actual).              |Usuario         |
|Equipos y canales     |         |Redirige a la administración de grupos de AAD (igual que la experiencia actual).             |Usuario          |
|Aplicaciones|Habilitar nuevas aplicaciones externas de manera predeterminada|Configuración de la aplicación para toda la organización|Inquilino|
|Aplicaciones|Permitir aplicaciones externas|Configuración de la aplicación para toda la organización|Inquilino|
|Aplicaciones|Permitir la instalación de sideloading de aplicaciones<sup>externas 2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Usuario|
|Aplicaciones|Aplicaciones predeterminadas<sup>3</sup>|TeamsAppPermissionPolicy|Usuario|
|Aplicaciones|Aplicaciones externas<sup>3</sup>|TeamsAppPermissionPolicy|Usuario|
|Llamadas y reuniones     |Permitir la programación de reuniones privadas         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir la reunión de canal Ad-hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir la programación de reuniones de canal         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir vídeos en reuniones         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir el uso compartido de la pantalla en las reuniones         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir llamadas privadas         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Usuario          |
|Mensajería      |Habilitar Giphy para que los usuarios puedan agregar archivos GIF a las conversaciones         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Clasificación de contenido         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Habilitar memes que los usuarios pueden editar y agregar a las conversaciones         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Habilitar adhesivos que los usuarios pueden editar y agregar a las conversaciones         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir que los propietarios eliminen todos los mensajes         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir a los usuarios editar sus propios mensajes         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir que los usuarios eliminen sus propios mensajes         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permite a los usuarios chatear en privado         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |

<sup>1 en</sup> desuso para invitados. Habilitar o deshabilitar invitados ahora se puede administrar en el Centro de administración de Microsoft Teams. La habilitación o deshabilitación de Teams para empresas, estudiantes educativos y profesores educativos dejará de estar disponible próximamente. Esto debe administrarse asignando licencias en el Centro de administración de Microsoft 365. Consulte [Administrar el acceso de los usuarios a Microsoft Teams.](user-access.md)
<br><br>
<sup>2 La</sup> instalación de sideloading se divide de la siguiente manera:

- Permitir a un usuario realizar la instalación de la instalación de seguridad de aplicaciones que se pueden administrar a nivel de usuario [en TeamsAppSetupPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)
- Permita que los usuarios de un inquilino interactúen con aplicaciones personalizadas que se pueden administrar a nivel de inquilino en la configuración de aplicaciones para toda la organización.

<sup>3 Las</sup> aplicaciones y aplicaciones externas predeterminadas se pueden activar o desactivar en el nivel de usuario en TeamsAppPermissionPolicy. Además, las aplicaciones se pueden bloquear en el nivel de inquilino en la configuración de aplicaciones de toda la organización, lo que reemplaza cualquier configuración de nivel de usuario e inquilino.

> [!NOTE]
> Seguirá usando el panel Grupos en el Centro de administración de Microsoft 365 para la configuración relacionada con Teams y canales. La configuración de las aplicaciones permanecerá en el área de Teams del Centro de administración de Microsoft 365 y se migrará más adelante.

## <a name="manage-settings-during-the-migration"></a>Administrar la configuración durante la migración

Puede seguir modificando la configuración en el Centro de administración de Microsoft 365 y el Centro de administración de Skype Empresarial hasta que se complete la migración de una sección para su inquilino.

La tabla siguiente muestra dónde puede administrar características durante la migración.

|Característica  |Centro de administración de Microsoft Teams                      |Centro de administración de Skype Empresarial (heredado)  |Centro de administración de Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Directivas de mensajería, reuniones y eventos en directo de Teams     |     X    |         |         |
|Directiva de actualización de Teams     |    X     |         |         |
|Configuración de invitado para Mensajería, Reuniones y Voz     |   X      |         |         |
|Administración del ciclo de vida de Teams   |    X    |      |       |
|Configuración de Teams   |    X    |      |       |
|Configuración de acceso externo     |    X    |      |       |
|Administración de usuarios    |         |         |    X     |
|Audioconferencia     |    X     |    X     |         |
|Planes de llamada     |    X    |    X     |         |
|Sistema telefónico    |    X    |     X    |         |
|Administración de números de teléfono     |    X    |   X      |         |
|Licencias para características de voz en la nube     |         |         |    X     |
|Operadores automáticos     |    X    |          |         |
|Colas de llamadas     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Administrar la configuración después de la migración

Cuando se complete la migración de esta configuración, la deshabilitaremos en el Centro de administración de Microsoft 365 y el Centro de administración de Skype Empresarial para que puedan administrarse en el nuevo Centro de administración de Microsoft Teams.

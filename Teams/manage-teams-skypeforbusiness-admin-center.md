---
title: Administrar la transición de Teams al nuevo Centro de administración de Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo administrar la configuración de usuarios y de todos los inquilinos para Teams durante la transición de Teams en la Centro de administración de Microsoft 365 al nuevo Centro de administración de Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: 39566c490a5de37adc699c39c049717525bd5821
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563958"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>¿Cuál es el nuevo Centro de administración de Microsoft Teams?  

La nueva experiencia del centro de administración le proporcionará una experiencia unificada para administrar Tanto Teams como Skype Empresarial. Estamos ofreciendo funciones adicionales, información de un extremo a otro y la capacidad de administrar la configuración de Teams en un nivel de usuario.

![Captura de pantalla del Centro de administración de Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Configuración migrada al nuevo Centro de administración de Microsoft Teams

La tabla siguiente identifica las secciones de la experiencia de Teams que se han migrado y muestra la relación entre la configuración actual y las directivas del nuevo portal de administración.

|Sección de Teams en Centro de administración de Microsoft 365  |Nombre de configuración (nivel de espacio empresarial)  |Directiva del Centro de administración de Microsoft Teams   |Nivel: Inquilino o usuario   |
|---------|---------|---------|---------|
|General     |Mostrar organigrama en perfil personal        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  Inquilino       |
|General     |Usar Skype Empresarial para los destinatarios que no tienen Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Integración de correo electrónico     |Permitir a los usuarios enviar correos electrónicos a canales         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Integración de correo electrónico     |Lista Permitir remitentes         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |Inquilino         |
|Almacenamiento en nube personalizado     |Caja         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Almacenamiento en nube personalizado     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Almacenamiento en nube personalizado     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Almacenamiento en nube personalizado     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Almacenamiento en nube personalizado     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Configuración por tipo de usuario/licencia     |Activar o desactivar Microsoft Teams para todos los usuarios          |En desuso<sup>1</sup>        |         |
|Equipos y canales     |         |Redirige a la administración de grupos de Azure Active Directory (igual que la experiencia actual).              |Usuario         |
|Equipos y canales     |         |Redirige a administración de grupos de AAD (igual que la experiencia actual).             |Usuario          |
|Aplicaciones|Habilitar nuevas aplicaciones externas de manera predeterminada|Configuración de aplicaciones para toda la organización|Inquilino|
|Aplicaciones|Permitir aplicaciones externas|Configuración de aplicaciones para toda la organización|Inquilino|
|Aplicaciones|Permitir la instalación de prueba de aplicaciones externas<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|Usuario|
|Aplicaciones|Aplicaciones predeterminadas<sup>3</sup>|TeamsAppPermissionPolicy|Usuario|
|Aplicaciones|Aplicaciones externas<sup>3</sup>|TeamsAppPermissionPolicy|Usuario|
|Llamadas y reuniones     |Permitir la programación de reuniones privadas         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuario          |
|Llamadas y reuniones     |Permitir reunión de canal ad hoc         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuario          |
|Llamadas y reuniones     |Permitir la programación de reuniones de canal         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuario          |
|Llamadas y reuniones     |Permitir vídeos en reuniones         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuario          |
|Llamadas y reuniones     |Permitir el uso compartido de la pantalla en reuniones         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuario          |
|Llamadas y reuniones     |Permitir llamadas privadas         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)        |Usuario          |
|Mensajería      |Habilitar Giphy para que los usuarios puedan agregar ARCHIVOS GIF a las conversaciones         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuario         |
|Mensajería      |Clasificación de contenido         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuario         |
|Mensajería      |Habilitar memes que los usuarios puedan editar y agregar a conversaciones         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuario         |
|Mensajería      |Habilitar adhesivos que los usuarios puedan editar y agregar a conversaciones         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuario         |
|Mensajería      |Permitir que los propietarios eliminen todos los mensajes         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuario         |
|Mensajería      |Permitir a los usuarios editar sus propios mensajes         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuario         |
|Mensajería      |Permitir a los usuarios eliminar sus propios mensajes         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuario         |
|Mensajería      |Permite a los usuarios chatear en privado         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuario         |

<sup>1</sup> En desuso para invitado. Habilitar o deshabilitar Invitado ahora se puede administrar en el Centro de administración de Microsoft Teams. La habilitación o deshabilitación de Teams para empresas enterprise, estudiantes educativos y profesores de educación estarán en desuso próximamente. Esto se debe administrar asignando licencias en el Centro de administración de Microsoft 365. Consulte [Administrar el acceso de usuarios a Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> La instalación de prueba se divide de la siguiente manera:

- Permitir a un usuario realizar instalaciones de prueba de aplicaciones que se pueden administrar a nivel de usuario en [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy).
- Permita que los usuarios de un inquilino interactúen con aplicaciones personalizadas que se pueden administrar a nivel de inquilino en la configuración de aplicaciones de toda la organización.

<sup>3</sup> Las aplicaciones predeterminadas y las aplicaciones externas pueden habilitarse y deshabilitarse en el nivel de usuario en TeamsAppPermissionPolicy. Además, las aplicaciones se pueden bloquear en el nivel de inquilino en la configuración de aplicaciones de toda la organización, que reemplaza cualquier configuración de usuario y de nivel de inquilino.

> [!NOTE]
> Seguirá usando el panel Grupos de la Centro de administración de Microsoft 365 para la configuración relacionada con Teams y canales. La configuración de las aplicaciones permanecerá en el área de Equipos de la Centro de administración de Microsoft 365 y se migrará más adelante.

## <a name="manage-settings-during-the-migration"></a>Administrar la configuración durante la migración

Puede seguir modificando la configuración de la Centro de administración de Microsoft 365 y del centro de administración de Skype Empresarial hasta que se complete la migración de una sección para su inquilino.

En la tabla siguiente se muestra dónde puede administrar las características durante la migración.

|Característica  |Centro de administración de Microsoft Teams                      |centro de administración de Skype Empresarial (heredado)  |Centro de administración de Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Directivas de mensajería, reuniones y eventos en directo de Teams     |     X    |         |         |
|Directiva de actualización de Teams     |    X     |         |         |
|Configuración de invitado para mensajes, reuniones y voz     |   X      |         |         |
|Administración del ciclo de vida de Teams   |    X    |      |       |
|Configuración de Teams   |    X    |      |       |
|Configuración de acceso externo     |    X    |      |       |
|Administración de usuarios    |         |         |    X     |
|Audioconferencia     |    X     |    X     |         |
|Planes de llamada     |    X    |    X     |         |
|Sistema telefónico    |    X    |     X    |         |
|Administración de números de teléfono     |    X    |   X      |         |
|Licencias para las características de voz en la nube     |         |         |    X     |
|Operadores automáticos     |    X    |          |         |
|Colas de llamadas     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Administrar la configuración después de la migración

Una vez completada la migración de esta configuración, la deshabilitaremos en el Centro de administración de Microsoft 365 y en el centro de administración de Skype Empresarial y, a continuación, se podrán administrar en el nuevo Centro de administración de Microsoft Teams.

---
title: Administrar Teams transición al nuevo centro de Teams administración
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de usuario y de espacio empresarial para Teams durante la transición de Teams en el centro de administración de Microsoft 365 al nuevo centro de administración de Teams inquilino.
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
ms.openlocfilehash: 875db7be64e23b32f5f758f9f5a701199c068528
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100906"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>¿Cuál es la nueva Microsoft Teams de administración?  

La nueva experiencia del centro de administración le proporcionará una experiencia unificada para administrar tanto Teams como Skype Empresarial. Estamos ofreciendo funcionalidades adicionales, información de un extremo a otro y la capacidad de administrar Teams configuración en un nivel de usuario.

![Captura de pantalla del Microsoft Teams de administración.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Configuración migrado al nuevo centro de Microsoft Teams administración

En la tabla siguiente se identifican las secciones de la experiencia Teams que se han migrado y se muestra la relación entre la configuración actual y las directivas en el nuevo portal de administración.

|Sección de Teams en Microsoft 365 de administración  |Nombre de configuración (nivel de inquilino)  |Microsoft Teams del Centro de administración   |Nivel: Inquilino o Usuario   |
|---------|---------|---------|---------|
|General     |Mostrar organigrama en perfil personal        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Inquilino       |
|General     |Use Skype Empresarial para destinatarios que no tienen Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Integración de correo electrónico     |Permitir a los usuarios enviar correos electrónicos a canales         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Integración de correo electrónico     |Permitir la lista de remitentes         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Inquilino         |
|Almacenamiento en nube personalizado     |Cuadro         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Almacenamiento en nube personalizado     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Configuración por usuario o tipo de licencia     |Activar Microsoft Teams o desactivar para todos los usuarios          |En desuso<sup>1</sup>        |         |
|Equipos y canales     |         |Redirige a Azure Active Directory de grupo (igual que la experiencia actual).              |Usuario         |
|Equipos y canales     |         |Redirige a la administración de grupos de AAD (igual que la experiencia actual).             |Usuario          |
|Aplicaciones|Habilitar nuevas aplicaciones externas de manera predeterminada|Configuración de la aplicación para toda la organización|Inquilino|
|Aplicaciones|Permitir aplicaciones externas|Configuración de la aplicación para toda la organización|Inquilino|
|Aplicaciones|Permitir la carga lateral de aplicaciones externas<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Usuario|
|Aplicaciones|Aplicaciones<sup>predeterminadas 3</sup>|TeamsAppPermissionPolicy|Usuario|
|Aplicaciones|Aplicaciones externas<sup>3</sup>|TeamsAppPermissionPolicy|Usuario|
|Llamadas y reuniones     |Permitir la programación de reuniones privadas         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir reunión de canales ad hoc         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir la programación de reuniones de canal         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir vídeos en reuniones         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir el uso compartido de pantalla en las reuniones         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuario          |
|Llamadas y reuniones     |Permitir llamadas privadas         |[TeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Usuario          |
|Mensajería      |Habilitar Giphy para que los usuarios puedan agregar ARCHIVOS GIF a las conversaciones         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Clasificación de contenido         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Habilitar memes que los usuarios pueden editar y agregar a conversaciones         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Habilitar adhesivos que los usuarios pueden editar y agregar a conversaciones         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir que los propietarios eliminen todos los mensajes         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir a los usuarios editar sus propios mensajes         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permitir a los usuarios eliminar sus propios mensajes         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |
|Mensajería      |Permite a los usuarios chatear en privado         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuario         |

<sup>1 En</sup> desuso para invitado. Habilitar o deshabilitar invitado ahora se puede administrar en el Microsoft Teams de administración. Habilitar o deshabilitar Teams para empresas Enterprise, Edu Student y Edu Faculty dejarán de estar en desuso próximamente. Esto debe administrarse asignando licencias en el centro Microsoft 365 administración. Vea [Administrar el acceso de usuario a Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> La carga lateral se divide de la siguiente manera:

- Permitir que un usuario descargue las aplicaciones que se pueden administrar a nivel de usuario en [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
- Permitir que los usuarios de un espacio empresarial interactúen con aplicaciones personalizadas que se pueden administrar a nivel de inquilino en la configuración de aplicaciones de toda la organización.

<sup>3</sup> Las aplicaciones predeterminadas y las aplicaciones externas se pueden habilitar y deshabilitar en el nivel de usuario en TeamsAppPermissionPolicy. Además, las aplicaciones se pueden bloquear en el nivel de inquilino en la configuración de aplicaciones de toda la organización que reemplaza cualquier configuración de usuario e inquilino.

> [!NOTE]
> Seguirá usando el panel Grupos en el centro de administración de Microsoft 365 para la configuración relacionada con Teams y canales. Configuración para aplicaciones permanecerá en el área Teams del centro de administración de Microsoft 365 y se migrará más adelante.

## <a name="manage-settings-during-the-migration"></a>Administrar la configuración durante la migración

Puede seguir modificando la configuración en el centro de administración de Microsoft 365 y el Centro de administración de Skype Empresarial hasta que se complete la migración de una sección para el inquilino.

En la tabla siguiente se muestra dónde puede administrar las características durante la migración.

|Característica  |Microsoft Teams de administración                      |Skype Empresarial de administración (heredado)  |Microsoft 365 de administración  |
|---------|:---------:|:---------:|:---------:|
|Teams Directivas de mensajería, reuniones y eventos en directo     |     X    |         |         |
|Teams Directiva de actualización     |    X     |         |         |
|Configuración de invitado para mensajería, reuniones y voz     |   X      |         |         |
|Teams Administración del ciclo de vida   |    X    |      |       |
|Teams Configuración   |    X    |      |       |
|Configuración de acceso externo     |    X    |      |       |
|Administración de usuarios    |         |         |    X     |
|Audioconferencia     |    X     |    X     |         |
|Planes de llamada     |    X    |    X     |         |
|Sistema telefónico    |    X    |     X    |         |
|Teléfono de números     |    X    |   X      |         |
|Licencias para características de voz en la nube     |         |         |    X     |
|Operadores automáticos     |    X    |          |         |
|Colas de llamadas     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Administrar la configuración después de la migración

Cuando se complete la migración de estas configuraciones, las deshabilitaremos en el centro de administración de Microsoft 365 y en el centro de administración de Skype Empresarial y, a continuación, se pueden administrar en el nuevo centro de administración de Microsoft Teams.
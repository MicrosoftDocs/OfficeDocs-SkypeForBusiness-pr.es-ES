---
title: Usar chats supervisados para inquilinos no educativos
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.custom: chat-teams-channels-revamp
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre los chats supervisados para inquilinos no educativos en Microsoft reuniones de Teams.
ms.collection:
- M365-collaboration
ms.openlocfilehash: dc7ddf23b600ec2a7f4d4f02c2328587627572fc
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198292"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>Chats supervisados para inquilinos no educativos

El chat supervisado permite a los supervisores designados iniciar chats con cualquier persona de su organización e impide que los usuarios puedan iniciar nuevos chats a menos que esté presente un supervisor adecuado. Cuando se habilita la supervisión del chat, los supervisores no pueden abandonar chats y otros participantes no pueden eliminarlos, lo que garantiza que los chats con usuarios restringidos se supervisen correctamente.

Estas limitaciones solo se aplican a los nuevos chats privados que se crean después de habilitar completamente el chat supervisado. No se aplican a chats privados, chats de reuniones o canales existentes.

El chat supervisado está adaptado a las necesidades de las instituciones educativas, pero también está disponible para los inquilinos no educativos.

> [!NOTE]
> El chat supervisado protege los nuevos chats creados después de exigir la característica. No protege los chats existentes.

## <a name="enable-supervised-chat"></a>Habilitar el chat supervisado

> [!NOTE]
> Asegúrese de configurar los roles de permisos de chat y las directivas de permisos de chat basadas en roles antes de habilitar el chat de su institución para evitar el acceso restringido no deseado de los usuarios a los chats sin supervisión.

**Defina los roles de permisos de chat para cada usuario de su entorno**:

Para que el chat supervisado funcione según lo esperado, cada usuario de su entorno debe tener asignado el rol de permisos de chat correcto. Hay tres roles que un usuario puede tener asignados:

- Permisos completos: este rol debe asignarse a los supervisores de chat de su entorno. Pueden iniciar chats con cualquier usuario de su entorno. Se espera que los usuarios con permisos completos supervisen los chats en los que participan. No se pueden abandonar ni quitar de los chats que inician o de los chats que supervisan en los inquilinos federados.

- Permisos limitados: este rol es ideal para los miembros del personal que solo deberían tener acceso supervisado a usuarios restringidos. Pueden iniciar chats con usuarios completos o limitados, pero no pueden iniciar chats con usuarios restringidos. Si un usuario con permisos completos inicia un chat con un usuario restringido, se pueden incorporar usuarios limitados a la conversación. Este acceso se produce porque un usuario con permisos completos está presente para supervisar la colaboración entre usuarios limitados y restringidos.

- Permisos restringidos: este rol es ideal para los usuarios que necesitan ser supervisados. Solo pueden iniciar chats con usuarios con permisos completos. Pueden participar en cualquier conversación a la que un usuario con permisos completos le invite. En los casos de chat federado, los usuarios restringidos solo pueden agregarlos a chats los usuarios con permisos completos procedentes del inquilino del usuario restringido.

Para establecer el rol de permisos de chat de los usuarios, use la directiva de **rol Permisos** de chat que se encuentra en las opciones de la directiva de mensajería en el portal de administración de Teams. Puede usar PowerShell para definir roles mediante la directiva ChatPermissionRole con los valores Full, Limited o Restricted. Esta directiva se encuentra en [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).

Los roles no se pueden asignar a los invitados de su inquilino. A los invitados se les asigna el rol limitado.

## <a name="allow-supervised-chat"></a>Permitir chat supervisado

El chat supervisado está deshabilitado de forma predeterminada para su inquilino. Después de establecer roles de permisos de chat para los usuarios, puede habilitar el chat supervisado dentro de su inquilino yendo a **Configuración de** **Teams** \> teams y estableciendo la directiva de **permisos de chat basado en** roles **en Activado**. También puedes usar PowerShell para habilitar el chat supervisado estableciendo AllowRoleBasedChatPermissions en True. Este cmdlet se encuentra en [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration).

El chat supervisado debe estar habilitado para todos los usuarios del espacio empresarial y no se puede habilitar para solo una parte de los usuarios.

**Habilitar chat**:

Habilite el chat para todos los usuarios con la directiva de chat existente disponible en el Centro de administración de Teams.

**Mantener chats supervisados**:

Después de habilitar inicialmente el chat supervisado, tendrá que hacer algunas cosas para asegurarse de que los chats de su entorno permanezcan supervisados:

- Asigne roles adecuados a los nuevos usuarios que se unan al inquilino. De forma predeterminada, a los usuarios se les asignará un rol restringido.

- Si un usuario con permisos completos deja de estar o se quita de un inquilino, los chats que supervisaban se dejaron sin supervisión. Antes de quitar el usuario original, asegúrese de que se agregue otro usuario con permisos completos a estas conversaciones para que el chat pueda permanecer supervisado. Una vez quitado el supervisor original, los nuevos participantes no se pueden agregar a la conversación, pero los participantes actuales pueden seguir comunicándose.

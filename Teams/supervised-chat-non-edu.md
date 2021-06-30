---
title: Usar chats supervisados para inquilinos no educativos
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre los chats supervisados para inquilinos no educativos en Microsoft Teams reuniones.
ms.openlocfilehash: 9d3e7707632a384f82a89a965f6db51f786f9d66
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203736"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>Chats supervisados para inquilinos no educativos

El chat supervisado permite a los supervisores designados iniciar chats con cualquier persona de su organización y impide que los usuarios inicien nuevos chats a menos que haya un supervisor adecuado. Cuando la supervisión del chat está habilitada, los supervisores no pueden abandonar chats y otros participantes no pueden quitarlos, lo que garantiza que los chats que implican usuarios restringidos estén debidamente supervisados.

Estas limitaciones solo se aplican a los nuevos chats privados que se crean después de que el chat supervisado se haya habilitado por completo. No se aplican a chats privados, chats de reuniones o canales existentes.

El chat supervisado está adaptado a las necesidades de las instituciones educativas, pero también está disponible para inquilinos no educativos.

> [!NOTE]
> El chat supervisado protege los nuevos chats creados después de que se aplique la característica. No protege los chats existentes.

## <a name="enable-supervised-chat"></a>Habilitar el chat supervisado

> [!NOTE]
> Asegúrese de configurar los roles de permisos de chat y las directivas de permisos de chat basadas en roles antes de habilitar el chat para su institución para evitar el acceso restringido de usuarios no deseados a chats sin supervisión.

**Definir roles de permisos de chat para cada usuario de su entorno**

Para que el chat supervisado funcione según lo esperado, cada usuario de su entorno debe tener asignado el rol de permisos de chat correcto. Hay tres roles que un usuario puede tener asignados:

- Permisos completos: este rol debe asignarse a los supervisores de chat de su entorno. Pueden iniciar chats con cualquier usuario de su entorno. Se espera que los usuarios con permisos completos supervisen los chats en los que participan. No pueden salir ni quitarse de los chats que inician o chats que supervisan en inquilinos federados.

- Permisos limitados: este rol es ideal para los miembros del personal que solo deben tener acceso supervisado a usuarios restringidos. Pueden iniciar chats con usuarios completos o limitados, pero no pueden iniciar chats con usuarios restringidos. Si un usuario con permisos completos inicia un chat con un usuario restringido, se pueden agregar usuarios limitados a la conversación. Este acceso se produce porque un usuario con permisos completos está presente para supervisar la colaboración entre usuarios limitados y restringidos.

- Permisos restringidos: este rol es ideal para los usuarios que necesitan ser supervisados. Solo pueden iniciar chats con usuarios con permisos completos. Pueden participar en cualquier conversación a la que un usuario con permisos completos les invite. En los casos de chat federado, los usuarios restringidos solo pueden agregarse a los chats por un usuario con permisos completos que sea del inquilino del usuario restringido.

Para establecer el rol de permisos  de chat de los usuarios, use la directiva de roles Permisos de chat que se encuentra en las opciones de directiva de mensajería en el Teams de administración. Puede usar PowerShell para definir roles con la directiva ChatPermissionRole con los valores Full, Limited o Restricted. Esta directiva se encuentra en [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).

Los roles no se pueden asignar a los invitados de su inquilino. A los invitados se les asigna el rol limitado.

## <a name="allow-supervised-chat"></a>Permitir el chat supervisado

El chat supervisado está deshabilitado de forma predeterminada para el inquilino. Después de establecer roles de permisos de chat para los usuarios, puede habilitar el chat supervisado dentro de su inquilino yendo a Configuración de toda la organización Teams Configuración y estableciendo la directiva de permisos de chat basado en roles en  >   **Activar**.  También puede usar PowerShell para habilitar el chat supervisado estableciendo AllowRoleBasedChatPermissions en True. Este cmdlet se encuentra en [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps).

El chat supervisado debe estar habilitado para todos los usuarios del inquilino y no se puede habilitar solo para una parte de los usuarios.

**Habilitar el chat**

Habilite el chat para todos los usuarios con la directiva de chat existente disponible en Teams de administración.

**Mantener chats supervisados**

Una vez que el chat supervisado esté habilitado inicialmente, tendrá que hacer algunas cosas para asegurarse de que los chats de su entorno permanezcan supervisados:

- Asigne roles adecuados a los nuevos usuarios que se unan a su inquilino. De forma predeterminada, a los usuarios se les asignará un rol restringido.

- Si un usuario con permisos completos abandona o se quita de un inquilino, los chats que supervisaban se dejarán sin supervisión. Antes de quitar el usuario original, asegúrese de que otro usuario con permisos completos se agrega a estas conversaciones para que el chat pueda permanecer supervisado. Una vez que se quita el supervisor original, los nuevos participantes no se pueden agregar a la conversación, pero los participantes actuales pueden seguir comunicándose.

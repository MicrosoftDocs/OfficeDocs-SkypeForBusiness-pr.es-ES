---
title: Usar chats supervisados
author: DaniEASmith
ms.author: danismith
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
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre los chats supervisados en las reuniones de Microsoft Teams.
ms.openlocfilehash: c355730424ec164c2853d4f4dc55956fb7554ce2
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789985"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Chats supervisados en Microsoft Teams

Las instituciones de educación proporcionan un espacio digital seguro y saludable para los estudiantes. El espacio digital incluye correos electrónicos, llamadas y reuniones en línea, y mensajería en Teams. Para evitar un comportamiento de mensajería inadecuado, muchas escuelas deshabilitan el chat privado en Teams. Desafortunadamente, deshabilitar el chat también bloquea la oportunidad de que los profesores se comuniquen con los alumnos en privado para el aprendizaje personalizado. Con el chat deshabilitado, los alumnos no pueden ponerse en contacto con los profesores cuando prefieren no publicar los mensajes públicamente en los equipos de clase.

El chat supervisado permite a los formadores designados iniciar chats con los alumnos e impide que los alumnos inicien nuevos chats a menos que esté presente un formador adecuado. Cuando se habilita la supervisión del chat, los supervisores no pueden abandonar chats y otros participantes no pueden eliminarlos, lo que garantiza que los chats con alumnos se supervisen correctamente.

Estas limitaciones solo se aplican a los nuevos chats privados que se crean después de habilitar completamente el chat supervisado. No se aplican a chats privados, chats de reuniones o canales existentes. Para obtener más información sobre los procedimientos recomendados para el chat de reuniones, la seguridad del canal y la seguridad de los alumnos, vea [Mantener seguros a los alumnos mientras usan Teams](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators).

> [!Note]
> El chat supervisado protege los nuevos chats creados después de exigir la característica.  No protege los chats existentes.

## <a name="review-use-cases-for-supervised-chats"></a>Revisar casos de uso de chats supervisados

Los ejemplos siguientes son descripciones de cuándo es necesario un chat supervisado.

- Un seguimiento 1.1 con un educador cuando los alumnos no se sientan cómodos compartiendo o haciendo preguntas públicamente.

- Los formadores que llegan 1.1 a un alumno sobre una tarea, interacción reciente con la clase (o falta de) u otro tema.

- Discusiones de grupo de alumnos supervisadas por un formador.

- Permita que el personal que no es docente chatee con los alumnos en un entorno supervisado.

## <a name="enable-supervised-chat"></a>Habilitar el chat supervisado

> [!Note]
> Asegúrese de configurar los roles de permisos de chat y las directivas de permisos de chat basadas en roles antes de habilitar el chat de su institución para evitar el acceso no deseado de los alumnos a los chats sin supervisión.

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>Definir roles de permisos de chat para cada usuario del entorno

Para que el chat supervisado funcione según lo esperado, cada usuario de su entorno debe tener asignado el rol de permisos de chat correcto. Hay tres roles que un usuario puede tener asignados:

- *Permisos completos* : este rol es ideal para educadores que deberían tener acceso total a los alumnos y a otros miembros del personal. Pueden iniciar chats con cualquier usuario de su entorno. Se espera que los usuarios con permisos completos supervisen los chats en los que participan. No se pueden abandonar ni quitar de los chats que inician o de los chats que supervisan en los inquilinos federados.

- *Permisos limitados* : este rol es ideal para los miembros del personal que solo deberían tener acceso supervisado a los alumnos y tener acceso total a otros docentes y profesores. Pueden iniciar chats con usuarios completos o limitados, pero no pueden iniciar chats con usuarios restringidos. Si un usuario con permisos completos inicia un chat con un usuario restringido, se pueden incorporar usuarios limitados a la conversación. Este acceso se produce porque un usuario con permisos completos está presente para supervisar la colaboración entre usuarios limitados y restringidos.

- *Permisos restringidos* : este rol es ideal para los alumnos que necesitan ser supervisados. Solo pueden iniciar chats con usuarios con permisos completos. Pueden participar en cualquier conversación a la que inicie un usuario con permisos completos y, a continuación, les invite. En los casos de chat federado, los usuarios restringidos solo pueden agregarlos a chats los usuarios con permisos completos procedentes del inquilino del usuario restringido.

Para establecer el rol de permisos de chat de los usuarios, use la directiva de **rol** **Permisos** de chat que se encuentra en las opciones de la directiva de mensajería en el portal de administración de Teams. Puede usar PowerShell para definir roles mediante la directiva ChatPermissionRole con los valores Full, Limited o Restricted. Esta directiva se encuentra en CsTeamsMessagingPolicy.

Para obtener más información sobre la configuración. Directivas de Teams consulte Directivas de Teams y paquetes de directivas para Educación y Asignar directivas a grandes conjuntos de guías de usuarios.

Los roles no se pueden asignar a los invitados de su inquilino. A los invitados se les asigna el rol limitado.

### <a name="allow-supervised-chat"></a>Permitir chat supervisado

El chat supervisado está deshabilitado de forma predeterminada para su inquilino. Después de establecer roles de permisos de chat para los usuarios, puede habilitar el chat supervisado dentro de su inquilino yendo a la **configuración** de **Teams** &gt; Teams y estableciendo la directiva de **permisos de chat basado en** roles *en Activado.* También puedes usar PowerShell para habilitar el chat supervisado estableciendo AllowRoleBasedChatPermissions en True. Este cmdlet se encuentra en CsTeamsClientConfiguration.

El chat supervisado debe estar habilitado para todos los usuarios del espacio empresarial y no se puede habilitar para solo una parte de los usuarios.

### <a name="enable-chat"></a>Habilitar chat

Habilite el chat para todos los usuarios con la directiva de chat existente disponible en el Centro de administración de Teams.

## <a name="maintain-supervised-chats"></a>Mantener chats supervisados

Después de habilitar inicialmente el chat supervisado, tendrá que hacer algunas cosas para asegurarse de que los chats de su entorno permanezcan supervisados:

- Asigne roles adecuados a los nuevos usuarios que se unan al inquilino. De forma predeterminada, a los usuarios se les asignará un rol restringido.

- Si un usuario con permisos completos deja de estar o se quita de un inquilino, los chats que supervisaban se dejaron sin supervisión. Antes de quitar el usuario original, asegúrese de que se agregue otro usuario con permisos completos a estas conversaciones para que el chat pueda permanecer supervisado. Una vez quitado el supervisor original, los nuevos participantes no se pueden agregar a la conversación, pero los participantes actuales pueden seguir comunicándose.

## <a name="related-topics"></a>Temas relacionados

[Chats supervisados para Teams en el ámbito educativo](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)

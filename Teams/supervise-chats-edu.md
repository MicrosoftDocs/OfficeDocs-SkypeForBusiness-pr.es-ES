---
title: Usar chats supervisados
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
description: Obtenga información sobre los chats supervisados en Microsoft Teams reuniones.
ms.openlocfilehash: e705120eb2f8b92ea437c78be67c139018f786fc
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506692"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Chats supervisados en Microsoft Teams

Las instituciones educativas proporcionan un espacio digital seguro y saludable para los alumnos. El espacio digital incluye correos electrónicos, reuniones y llamadas en línea, y mensajería en Teams. Para evitar comportamientos de mensajería inadecuados, muchas escuelas deshabilitan el chat privado en Teams. Desafortunadamente, deshabilitar el chat también bloquea la oportunidad de que los profesores se unan a los alumnos en privado para obtener un aprendizaje personalizado. Con el chat deshabilitado, los alumnos no pueden comunicarse con los profesores cuando prefieren no publicar los mensajes públicamente en los equipos de clase.

El chat supervisado permite a los profesores designados iniciar chats con alumnos y bloquea que los alumnos inicien nuevos chats a menos que haya un educador adecuado. Cuando la supervisión del chat está habilitada, los supervisores no pueden abandonar los chats y otros participantes no pueden quitarlos, lo que garantiza que los chats que implican a los alumnos estén debidamente supervisados.

Estas limitaciones solo se aplican a los nuevos chats privados que se crean después de que el chat supervisado se haya habilitado por completo. No se aplican a chats privados, chats de reuniones o canales existentes. Para obtener más información sobre los procedimientos recomendados para el chat de reunión, la seguridad del canal y mantener a los alumnos seguros, vea Mantener a los alumnos seguros mientras [usan Teams](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators).

> [!Note]
> El chat supervisado protege los nuevos chats creados después de que se aplique la característica.  No protege los chats existentes.

## <a name="review-use-cases-for-supervised-chats"></a>Revisar casos de uso de chats supervisados

Los ejemplos siguientes son descripciones de cuándo es necesario un chat supervisado.

- Un seguimiento 1.1 con un educador cuando los alumnos no se sienten cómodos compartiendo o haciendo preguntas públicamente.

- Los formadores que se acercan a un alumno sobre una tarea, la interacción de clase reciente (o la falta de) u otro tema.

- Discusiones de grupo de alumnos supervisadas por un educador.

- Permitir que el personal no docente chatee con el alumno en un entorno supervisado.

## <a name="enable-supervised-chat"></a>Habilitar el chat supervisado

> [!Note]
> Asegúrese de configurar los roles de permisos de chat y las directivas de permisos de chat basadas en roles antes de habilitar el chat para su institución para evitar el acceso no deseado de los alumnos a chats sin supervisión.

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>Definir roles de permisos de chat para cada usuario de su entorno

Para que el chat supervisado funcione según lo esperado, cada usuario de su entorno debe tener asignado el rol de permisos de chat correcto. Hay tres roles que un usuario puede tener asignados:

- *Permisos completos:* este rol es ideal para los profesores que deben tener acceso completo a los alumnos y otros miembros del personal. Pueden iniciar chats con cualquier usuario de su entorno. Se espera que los usuarios con permisos completos supervisen los chats en los que participan. No pueden salir ni quitarse de los chats que inician o chats que supervisan en inquilinos federados.

- *Permisos limitados:* este rol es ideal para los miembros del personal que solo deben tener acceso supervisado a los alumnos y tener acceso completo a otros docentes y docentes. Pueden iniciar chats con usuarios completos o limitados, pero no pueden iniciar chats con usuarios restringidos. Si un usuario con permisos completos inicia un chat con un usuario restringido, se pueden agregar usuarios limitados a la conversación. Este acceso se produce porque un usuario con permisos completos está presente para supervisar la colaboración entre usuarios limitados y restringidos.

- *Permisos restringidos:* este rol es ideal para los alumnos que necesitan ser supervisados. Solo pueden iniciar chats con usuarios con permisos completos. Pueden participar en cualquier conversación a la que un usuario con permisos completos les invite. En los casos de chat federado, los usuarios restringidos solo pueden agregarse a los chats por un usuario con permisos completos que sea del inquilino del usuario restringido.

Para establecer el rol de permisos   de chat de los usuarios, use la directiva de roles Permisos de chat que se encuentra en las opciones de directiva de mensajería en el Teams de administración. Puede usar PowerShell para definir roles con la directiva ChatPermissionRole con los valores Full, Limited o Restricted. Esta directiva se encuentra en CsTeamsMessagingPolicy.

Para obtener más información sobre la configuración. Teams ver Teams directivas y paquetes de directivas para Educación y Asignar directivas a grandes conjuntos de guías de usuarios.

Los roles no se pueden asignar a los invitados de su inquilino. A los invitados se les asigna el rol limitado.

### <a name="allow-supervised-chat"></a>Permitir el chat supervisado

El chat supervisado está deshabilitado de forma predeterminada para el inquilino. Después de establecer roles de permisos de chat para los usuarios, puede  habilitar el chat supervisado dentro de su inquilino yendo a Configuración de toda la organización Teams Configuración y estableciendo la directiva de permisos de chat basado en roles en &gt;  *Activar.*  También puede usar PowerShell para habilitar el chat supervisado estableciendo AllowRoleBasedChatPermissions en True. Este cmdlet se encuentra en CsTeamsClientConfiguration.

El chat supervisado debe estar habilitado para todos los usuarios del inquilino y no se puede habilitar solo para una parte de los usuarios.

### <a name="enable-chat"></a>Habilitar el chat

Habilite el chat para todos los usuarios con la directiva de chat existente disponible en Teams de administración.

## <a name="maintain-supervised-chats"></a>Mantener chats supervisados

Una vez que el chat supervisado esté habilitado inicialmente, tendrá que hacer algunas cosas para asegurarse de que los chats de su entorno permanezcan supervisados:

- Asigne roles adecuados a los nuevos usuarios que se unan a su inquilino. De forma predeterminada, a los usuarios se les asignará un rol restringido.

- Si un usuario con permisos completos abandona o se quita de un inquilino, los chats que supervisaban se dejarán sin supervisión. Antes de quitar el usuario original, asegúrese de que otro usuario con permisos completos se agrega a estas conversaciones para que el chat pueda permanecer supervisado. Una vez que se quita el supervisor original, los nuevos participantes no se pueden agregar a la conversación, pero los participantes actuales pueden seguir comunicándose.

## <a name="related-topics"></a>Temas relacionados

[Chats supervisados para Teams en el sector educativo](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)

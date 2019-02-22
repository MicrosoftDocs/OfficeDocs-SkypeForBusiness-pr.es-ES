---
title: Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Experiencia de los equipos cliente y la compatibilidad con los modos de coexistencia
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d97bf7230e8d1f78f2cf5c169fbf48a93f415bb
ms.sourcegitcommit: d3c459dc1304db5f5ba78b5e093b5a4fd797c8ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "30178649"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia

> [!NOTE]
> Esta página describe los próximos cambios importantes en el comportamiento del cliente de los equipos cuando los usuarios están en cualquiera de los Skype para los modos de negocio (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).


El propósito de los modos de la coexistencia es proporcionar una experiencia sencilla y predecible para los usuarios finales como transición de las organizaciones de Skype para la empresa a los equipos.  Para una organización mover a los equipos, el modo de TeamsOnly es el destino final de cada usuario, aunque no todos los usuarios deben asignarse TeamsOnly (o cualquier otro modo) al mismo tiempo.  Antes de alcanzar el modo TeamsOnly de los usuarios, las organizaciones pueden usar cualquiera de los Skype para los modos de negocio (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantizar la comunicación entre los usuarios que están TeamsOnly y aquellos que no están todavía predecible. 

Cuando un usuario se encuentra en cualquiera de los Skype para los modos de negocio, todos los chats entrantes y las llamadas se enrutan a Skype del usuario para clientes empresariales. Para evitar confusiones al usuario final y garantizar el enrutamiento correcto, llamadas y conversaciones funcionalidad en el cliente de los equipos está pensada para deshabilitar cuando un usuario se encuentra en cualquiera de los Skype para los modos de negocio. De forma similar, programar reuniones en los equipos está pensada para ser explícitamente deshabilitado cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y explícitamente habilitado cuando un usuario se encuentra en el modo de SfBWithTeamsCollabAndMeetings.  La funcionalidad para deshabilitar automáticamente conversaciones y llamar a funciones, así como habilitar o deshabilitar la programación basada en el modo de la reunión es ahora comenzando a implantación a los clientes puntee dos veces en.  

Antes de esta funcionalidad, instrucciones de Microsoft era garantizar la experiencia de usuario adecuados estableciendo la correspondiente configuración en mensajería, llamar a y las directivas de reunión. Sin embargo, se ha producido ningún formal cumplimiento de esta y, como predeterminada, los usuarios tenían acceso total a toda la funcionalidad en el cliente de los equipos, algunos usuarios es posible que haya conserva el acceso a algunas o todas estas evaluaciones en el cliente de los equipos, independientemente del modo.  Como resultado, tal y como se implementa esta funcionalidad, algunos usuarios pueden ver un cambio en su experiencia en el cliente de los equipos a medida que la experiencia del usuario comienza a cumplir con su modo.  En la tabla siguiente se muestra el nuevo comportamiento:


|Modo eficaz del usuario|Experiencia de cliente de los equipos|
|---|---|
|Cualquier Skype para el modo de negocio|Llamadas y conversaciones<sup>1</sup> están deshabilitadas.|
|SfBWithTeamsCollabAndMeetings|Programación de la reunión está disponible|
|SfBWithTeamsCollab o SfBOnly<sup>2</sup>|Programación de la reunión no está disponible|
|||

**Notas:**
<sup>1</sup> chat de reunión sigue estando disponible.

<sup>2</sup> por ahora, SfBwithTeamsCollab y SfBOnly comportan de la misma, pero la intención es para que el modo de SfBOnly deshabilitar también la funcionalidad de canales y los archivos en los equipos; Sin embargo, actualmente no hay ninguna opción que permite que esta funcionalidad en los equipos que va a deshabilitar.


## <a name="how-organizations-can-prepare-for-automatic-ux-conformance-to-modes"></a>¿Cómo pueden preparar las organizaciones de conformidad de experiencia de usuario automática para los modos de

Antes de realizar este cambio implantar, las organizaciones pueden beneficiarse de la experiencia que desee en el cliente de los equipos mediante directivas adicionales como se describe en esta sección. Esto garantiza que la implantación es transparente para los usuarios finales. Tenga en cuenta que una vez que implementa el cambio, establecer estas directivas no será necesario.  Como alternativa, las organizaciones que no desean que los usuarios han reducido la funcionalidad en el cliente de los equipos pueden cambiar sus usuarios a modo de islas o TeamsOnly, sin embargo, tendrá un impacto así como el enrutamiento.

Para configurar manualmente la experiencia del usuario final, los administradores usar las directivas y la configuración siguiente:


|**Modalidad (aplicación)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Llamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Programación de reuniones|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||


Los administradores deben establecer cada una de estas opciones de configuración para los siguientes valores de un modo determinado:

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly o Islas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Deshabilitado|Deshabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab o SfBOnly|Deshabilitado|Deshabilitado|Deshabilitado|Deshabilitado|
||||||

Antes de la implantación de conformidad automática de la experiencia del usuario en función de los modos, el `Grant-CsTeamsUpgradePolicy` cmdlet comprueba la configuración de los valores correspondientes en TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy para determinar si estos configuración de es compatible con el modo especificado. Si alguna no están configurado correctamente, la concesión se realizará correctamente pero, proporcionará una advertencia en PowerShell que indica qué configuración específica no está configurados correctamente. A continuación es un ejemplo del aspecto que podría tener la advertencia de PowerShell:


' Grant-CsTeamsUpgradePolicy-SfBWithTeamsCollab - PolicyName de identidad user1@contoso.com

Advertencia: El usuario 'user1@contoso.com' tiene actualmente los valores de directiva efectiva habilitado para: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. En el término near, al conceder TeamsUpgradePolicy con el modo = SfBWithTeamsCollab a un usuario, debe asignar también por separado directiva para asegurarse de que el usuario tiene los valores de directiva efectiva deshabilitada para: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. En el futuro, la capacidad de automáticamente respeta TeamsUpgradePolicy.'

Al ver una advertencia de este tipo, el administrador debe actualizar posteriormente las directivas indicadas para proporcionar una experiencia de usuario final compatible en los equipos. Si el administrador decide no realizar ninguna acción como consecuencia de la advertencia, los usuarios aún tener acceso a conversaciones, llamar o funciones de programación en los equipos según los valores de TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy, de la reunión lo que puede conllevar una experiencia de usuario final confusa.

Una vez conformidad automática de la experiencia del cliente de los equipos basada en el modo de TeamsUpgradePolicy está disponible, ya no será necesario establecer estas directivas. El valor del modo de TeamsUpgradePolicy tendrá prioridad sobre los valores de estas configuraciones específicas. Conformidad automática se consigue durante la resolución de directiva en la infraestructura de directiva. En caso de conflicto de las diferentes configuraciones, el comportamiento basado en el modo se win a través de los valores de AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling y AllowChannelMeetingScheduling. Una vez que se ha entregado conformidad automática, se actualizarán las advertencias de PowerShell para informar al administrador que automáticamente se aplicará la experiencia del cliente, a pesar de cualquiera de los valores de TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy.








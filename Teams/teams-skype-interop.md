---
title: Interoperabilidad de Teams e Skype
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Obtenga información sobre las capacidades de interoperabilidad entre los usuarios de Teams de su organización y los usuarios de Skype (consumidor).
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093960"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilidad de Teams e Skype

En este artículo se ofrece información general sobre las capacidades de interoperabilidad entre Microsoft Teams y Skype (consumidor). Obtenga información sobre cómo los usuarios de Teams y los usuarios de Skype pueden comunicarse a través de chats y llamadas y los controles de administración que se aplican.

Los usuarios de Teams de su organización pueden chatear y llamar a usuarios de Skype mediante su dirección de correo electrónico y viceversa.

- Los usuarios de Teams pueden buscar e iniciar una conversación de solo texto uno a uno o una llamada de audio y vídeo con un usuario de Skype.
- Los usuarios de Skype pueden buscar e iniciar una conversación de solo texto uno a uno o una llamada de audio y vídeo con un usuario de Teams.

Estas capacidades están disponibles en los clientes de escritorio, web y móvil (Android e iOS) para Teams y Skype. Para una experiencia óptima, recomendamos la versión 8.58 de Skype y versiones posteriores.

> [!NOTE]
> Las capacidades de interoperabilidad de Teams y Skype que se deba en este artículo no están disponibles en implementaciones de GCC, GCC High o DOD, ni en entornos de nube privados.

## <a name="chat-and-calling-experience"></a>Experiencia de chat y llamadas

Esta es una descripción general de la experiencia de chat y llamadas.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>El usuario de Teams inicia un chat o una llamada con un usuario de Skype

Los usuarios de Teams pueden buscar un usuario de Skype escribiendo su dirección de correo electrónico en un nuevo chat o en la barra de búsqueda.  El usuario de Teams puede seleccionar el usuario de Skype en los resultados de búsqueda para iniciar un chat o una llamada con ellos.

Un usuario de Skype puede elegir no aparecer en los resultados de búsqueda. En este caso, no se mostrarán en los resultados de búsqueda en Teams y los usuarios de Teams no podrán encontrarlos.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>El usuario de Skype inicia un chat o una llamada con un usuario de Teams

Los usuarios de Skype pueden buscar e iniciar un chat con un usuario de Teams con su dirección de correo electrónico. Se notifica al usuario de Teams que tiene un mensaje nuevo de un usuario de Skype y primero tiene que aceptar el mensaje antes de poder responderlo.

- Si el usuario de Teams selecciona **Aceptar,** se acepta la conversación y ambos usuarios pueden chatear y llamarse entre sí.
- Si el usuario de Teams selecciona **Bloquear,** la conversación está bloqueada y los mensajes y llamadas posteriores de ese usuario de Skype se bloquean.
- Si el usuario de Teams selecciona Ver **mensajes,** el mensaje se muestra en Teams, lo que ayuda al usuario a decidir si acepta o bloquea la conversación.

> [!NOTE]
> Si has actualizado de Skype Empresarial a Teams y tus usuarios están en modo solo de Teams, los chats y las llamadas de los usuarios de Skype a los usuarios de Teams se entregan a Teams. Si los usuarios están en modo Islas, los chats y las llamadas de los usuarios de Skype a los usuarios de Teams se entregan a Skype Empresarial.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>El usuario de Teams bloquea o desbloquea un usuario de Skype

Después de que un usuario de Teams acepte o bloquee la solicitud de conversación inicial de un usuario de Skype, puede bloquear o desbloquear a esa persona en cualquier momento. Pueden hacerlo en la conversación o en su configuración de privacidad en Teams. Los usuarios de Skype no sabrán que se han bloqueado.

Los usuarios de Skype bloqueados, junto con otras personas y números de teléfono de red telefónica conmutada (RTC) bloqueados por un usuario de Teams, aparecen en la lista de contactos bloqueados del usuario en Teams.

## <a name="limitations"></a>Limitaciones

- Las conversaciones son de solo texto. Esto significa que no hay ningún formato enriquecido, @mentions, emojis u otras características de chat que estén disponibles en una experiencia de chat nativa de [Teams.](native-chat-for-external-users.md)
- Las conversaciones son solo uno a uno. Los chats grupales no son compatibles.
- Los usuarios de Teams y los usuarios de Skype no pueden ver la presencia de los demás.
- No se admite la búsqueda de usuarios de Skype mediante su id. de Skype o su número de teléfono.
- Los usuarios de Skype no pueden llamar a los usuarios de Teams que configuren el reenvío de llamadas al número de otro usuario, al número de un delegado o a un número de red telefónica conmutada (RTC).  Solo se admite el correo de voz.
- La escalación de interoperabilidad, las llamadas grupales y las reuniones no son compatibles.
- No se admite la posibilidad de que un delegado llame a un usuario de Skype en nombre de un usuario de Teams.
- No se admite el uso compartido de pantalla con el chat.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Establecer si los usuarios de Teams pueden comunicarse con usuarios de Skype

Como administrador, use el Centro de administración de Microsoft Teams o PowerShell para establecer la configuración de acceso externo para controlar si los usuarios de Teams de su organización pueden comunicarse con los usuarios de Skype. De forma predeterminada, esta funcionalidad está activada para los nuevos inquilinos. Sin embargo, existe un requisito previo para que el administrador de TI configure el siguiente registro SRV dns si aún no está disponible para su dominio, por ejemplo _sipfederationtls.contoso.com.  

**Servicio:** sipfederationtls<br/>
**Protocolo:** TCP<br/>
**Prioridad:** 100<br/>
**Peso:** 1<br/>
**Puerto:** 5061<br/>
**Destino:** sipfed.online.lync.com

Si ha actualizado de Skype Empresarial a Teams, la configuración de comunicaciones externas que configuró en el Centro de administración de Skype Empresarial se migrará a Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>En el centro de administración de Microsoft Teams

En el Centro de administración de Microsoft Teams, vaya a Configuración de toda la organización Acceso externo y, a continuación, active Los usuarios  >  pueden comunicarse con los usuarios **de Skype.** Para obtener instrucciones paso a paso sobre cómo configurar esta y otras opciones de acceso externo, vea Administrar el [acceso externo en Teams.](./manage-external-access.md#allow-or-block-domains)

### <a name="using-powershell"></a>Con PowerShell

Haga lo siguiente: 
1. Use el cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) junto con el parámetro para controlar si los usuarios de Teams pueden ```EnablePublicCloudAccess``` comunicarse con los usuarios de Skype. Establecer el parámetro para ```true``` que permita a los usuarios de Teams comunicarse con los usuarios de Skype. Puede usar el parámetro para habilitar o deshabilitar ```EnablePublicCloudAudioVideoAccess``` las llamadas de audio y vídeo.

2. Use el cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) junto con el parámetro establecido en para que los usuarios de ```Provider``` ```"WindowsLive"``` Teams puedan comunicarse con los usuarios de Skype.

## <a name="related-topics"></a>Temas relacionados

- [Administrar el acceso externo en Teams](manage-external-access.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
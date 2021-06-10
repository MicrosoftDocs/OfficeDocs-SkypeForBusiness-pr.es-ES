---
title: Teams y Skype interoperabilidad
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
description: Obtenga información sobre las capacidades de interoperabilidad entre Teams usuarios de su organización y Skype (consumidor).
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093960"
---
# <a name="teams-and-skype-interoperability"></a>Teams y Skype interoperabilidad

En este artículo se ofrece información general sobre las capacidades de interoperabilidad entre Microsoft Teams y Skype (consumidor). Obtenga información sobre Teams usuarios y Skype pueden comunicarse a través de chats y llamadas y los controles de administración que se aplican.

Teams usuarios de su organización pueden chatear y llamar a Skype mediante su dirección de correo electrónico y viceversa.

- Teams usuarios pueden buscar e iniciar una conversación de solo texto uno a uno o una llamada de audio o vídeo con un Skype usuario.
- Skype usuarios pueden buscar e iniciar una conversación de solo texto uno a uno o una llamada de audio o vídeo con un Teams usuario.

Estas funcionalidades están disponibles en los clientes de escritorio, web y móvil (Android e iOS) tanto para Teams como Skype. Para una experiencia óptima, le recomendamos que Skype versión 8.58 y posteriores.

> [!NOTE]
> Las Teams y Skype de interoperabilidad que se deba en este artículo no están disponibles en implementaciones de GCC, GCC High o DOD, ni en entornos de nube privados.

## <a name="chat-and-calling-experience"></a>Experiencia de chat y llamadas

Esta es una descripción general de la experiencia de chat y llamadas.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams usuario inicia un chat o llamada con un Skype usuario

Teams usuarios pueden buscar un usuario Skype escribiendo su dirección de correo electrónico en un nuevo chat o en la barra de búsqueda.  El Teams puede seleccionar el Skype en los resultados de búsqueda para iniciar un chat o una llamada con ellos.

Un Skype usuario puede elegir no aparecer en los resultados de búsqueda. En este caso, no se mostrarán en los resultados de búsqueda en Teams y Teams usuarios no podrán encontrarlos.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype usuario inicia un chat o una llamada con un Teams usuario

Skype usuarios pueden buscar e iniciar un chat con un usuario Teams usando su dirección de correo electrónico. Al Teams de correo electrónico se le notifica que tiene un mensaje nuevo de un usuario de Skype y primero tiene que aceptar el mensaje antes de poder responderlo.

- Si el Teams selecciona **Aceptar,** se acepta la conversación y ambos usuarios pueden chatear y llamarse entre sí.
- Si el Teams selecciona **Bloquear,** la conversación está bloqueada y se bloquean los mensajes y las llamadas posteriores de Skype usuario.
- Si el Teams selecciona Ver **mensajes,** el mensaje se muestra en Teams, lo que ayuda al usuario a decidir si desea aceptar o bloquear la conversación.

> [!NOTE]
> Si ha actualizado de Skype Empresarial Teams y los usuarios están en el modo solo Teams, los chats y las llamadas de los usuarios de Skype Teams a Teams. Si los usuarios están en el modo Islas, los chats y las llamadas de Skype a Teams usuarios se entregan a Skype Empresarial.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams usuario bloquea o desbloquea un Skype usuario

Después de que Teams usuario acepte o bloquee la solicitud de conversación inicial de un usuario de Skype, puede elegir bloquear o desbloquear a esa persona en cualquier momento. Pueden hacerlo en la conversación o en su configuración de privacidad en Teams. Skype usuarios no sabrán que se han bloqueado.

Los Skype, junto con otras personas y números de teléfono de red telefónica conmutada (RTC) bloqueados por un usuario de Teams, aparecen en la lista de contactos bloqueados del usuario en Teams.

## <a name="limitations"></a>Limitaciones

- Las conversaciones son de solo texto. Esto significa que no hay ningún formato enriquecido, @mentions, emojis u otras características de chat que estén disponibles en una experiencia de chat de Teams [nativa.](native-chat-for-external-users.md)
- Las conversaciones son solo uno a uno. Los chats grupales no son compatibles.
- Teams usuarios y Skype usuarios no pueden ver la presencia de los demás.
- No se admite Skype usuarios con su Skype o número de teléfono.
- Skype usuarios no pueden llamar Teams usuarios que configuren el reenvío de llamadas al número de otro usuario, al número de un delegado o a un número de red telefónica conmutada (RTC).  Solo se admite el correo de voz.
- La escalación de interoperabilidad, las llamadas grupales y las reuniones no son compatibles.
- No se admite la capacidad para que un delegado llame a Skype usuario en nombre de un usuario Teams usuario.
- No se admite el uso compartido de pantalla con el chat.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Establecer si Teams usuarios pueden comunicarse con Skype usuarios

Como administrador, use el centro de administración de Microsoft Teams o PowerShell para establecer la configuración de acceso externo para controlar si Teams usuarios de su organización pueden comunicarse con Skype usuarios. De forma predeterminada, esta funcionalidad está activada para los nuevos inquilinos. Sin embargo, existe un requisito previo para que el administrador de TI configure el siguiente registro SRV dns si aún no está disponible para su dominio, por ejemplo _sipfederationtls.contoso.com.  

**Servicio:** sipfederationtls<br/>
**Protocolo:** TCP<br/>
**Prioridad:** 100<br/>
**Peso:** 1<br/>
**Puerto:** 5061<br/>
**Destino:** sipfed.online.lync.com

Si actualizó de Skype Empresarial a Teams, la configuración de comunicaciones externas que configuró en el centro de administración de Skype Empresarial se migrará a Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>En el centro de administración de Microsoft Teams

En el Microsoft Teams de administración, vaya a Configuración de toda la organización Acceso externo y, a continuación, active Los usuarios pueden comunicarse con  >   **Skype usuarios.** Para obtener instrucciones paso a paso sobre cómo configurar esta y otras opciones de acceso externo, vea Administrar el acceso [externo en Teams](./manage-external-access.md#allow-or-block-domains).

### <a name="using-powershell"></a>Con PowerShell

Haga lo siguiente: 
1. Use el cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) junto con el parámetro para controlar si Teams usuarios pueden comunicarse ```EnablePublicCloudAccess``` con Skype usuarios. Al establecer el parámetro ```true``` para que Teams usuarios puedan comunicarse con Skype usuarios. Puede usar el parámetro para habilitar o deshabilitar ```EnablePublicCloudAudioVideoAccess``` las llamadas de audio y vídeo.

2. Use el cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) junto con el parámetro establecido en para que Teams usuarios puedan comunicarse con ```Provider``` ```"WindowsLive"``` Skype usuarios.

## <a name="related-topics"></a>Temas relacionados

- [Administrar el acceso externo en Teams](manage-external-access.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
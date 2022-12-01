---
title: Equipos y interoperabilidad de Skype
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Obtenga información sobre las capacidades de interoperabilidad entre los usuarios de Teams de su organización y los usuarios de Skype (consumidores).
ms.localizationpriority: medium
ms.openlocfilehash: e8f6d102a3b66d5140473d0f2ab11b5af97fc78f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198682"
---
# <a name="teams-and-skype-interoperability"></a>Equipos y interoperabilidad de Skype

En este artículo se ofrece información general sobre las capacidades de interoperabilidad entre Microsoft Teams y Skype (consumidor). Obtenga información sobre cómo los usuarios de Teams y los usuarios de Skype pueden comunicarse a través de chats y llamadas, así como de los controles de administración que se aplican.

Los usuarios de Teams de su organización pueden chatear con usuarios de Skype y llamarlos usando su dirección de correo electrónico y viceversa.

- Los usuarios de Teams pueden buscar e iniciar una conversación de solo texto individual o una llamada de audio o vídeo con un usuario de Skype.
- Los usuarios de Skype pueden buscar e iniciar una conversación de solo texto individual o una llamada de audio o vídeo con un usuario de Teams.

Estas funcionalidades están disponibles en los clientes de escritorio, web y móviles (Android e iOS) tanto para Teams como para Skype. Para obtener una experiencia óptima, recomendamos la versión 8.58 y posteriores de Skype.

> [!NOTE]
> Las funcionalidades de interoperabilidad de Teams y Skype que se describen en este artículo no están disponibles en GCC, GCC High, implementaciones de DOD ni en entornos de nube privada.

## <a name="chat-and-calling-experience"></a>Experiencia de chat y llamadas

Esta es una descripción general de la experiencia de chat y llamadas.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>El usuario de Teams inicia un chat o una llamada con un usuario de Skype

Los usuarios de Teams pueden buscar un usuario de Skype escribiendo su dirección de correo electrónico en un nuevo chat o en la barra de búsqueda.  A continuación, el usuario de Teams puede seleccionar el usuario de Skype en los resultados de búsqueda para iniciar un chat o una llamada con el usuario.

Un usuario de Skype puede elegir no aparecer en los resultados de búsqueda. En este caso, no aparecerán en los resultados de búsqueda en Teams y los usuarios de Teams no podrán encontrarlos.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Un usuario de Skype inicia un chat o una llamada con un usuario de Teams

Los usuarios de Skype pueden buscar e iniciar un chat con un usuario de Teams mediante su dirección de correo electrónico. Al usuario de Teams se le notifica que tiene un mensaje nuevo de un usuario de Skype y primero tiene que aceptar el mensaje antes de poder responder a él.

- Si el usuario de Teams selecciona **Aceptar**, se acepta la conversación y ambos usuarios pueden chatear y llamar entre sí.
- Si el usuario de Teams selecciona **Bloquear**, se bloquea la conversación y se bloquean los mensajes y las llamadas posteriores de ese usuario de Skype.
- Si el usuario de Teams selecciona **Ver mensajes**, el mensaje se muestra en Teams, lo que ayuda al usuario a decidir si desea aceptar o bloquear la conversación.

> [!NOTE]
> Si ha actualizado de Skype Empresarial a Teams y los usuarios se encuentran en el modo Solo teams, los chats y las llamadas de los usuarios de Skype a los usuarios de Teams se entregan a Teams. Si los usuarios se encuentran en el modo Islas, los chats y las llamadas de los usuarios de Skype a los usuarios de Teams se entregan a Skype Empresarial.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>El usuario de Teams bloquea o desbloquea a un usuario de Skype

Después de que un usuario de Teams acepte o bloquee la solicitud de conversación inicial de un usuario de Skype, puede elegir bloquear o desbloquear a esa persona en cualquier momento. Pueden hacerlo en la conversación o en su configuración de privacidad en Teams. Los usuarios de Skype no sabrán que se les ha bloqueado.

Los usuarios de Skype bloqueados, junto con otras personas y los números de teléfono de la red telefónica conmutada (RTC) que un usuario de Teams ha bloqueado, aparecen en la lista de contactos bloqueados del usuario en Teams.

## <a name="limitations"></a>Limitaciones

- Las conversaciones son solo de texto. Esto significa que no hay formato enriquecido, @mentions, emojis u otras características de chat que estén disponibles en una [experiencia de chat nativa de Teams](native-chat-for-external-users.md).
- Las conversaciones son individuales. Los chats grupales no son compatibles.
- Los usuarios de Teams y los usuarios de Skype no pueden ver la presencia de los demás.
- No se admite la búsqueda de usuarios de Skype con su id. de Skype o su número de teléfono.
- Los usuarios de Skype no pueden llamar a los usuarios de Teams que configuran el desvío de llamadas al número de otro usuario, al número de un delegado o a un número de red telefónica conmutada (RTC).  Solo se admite el correo de voz.
- No se admite la escalación de interoperabilidad, las llamadas de grupo y las reuniones.
- No se admite la posibilidad de que un delegado llame a un usuario de Skype en nombre de un usuario de Teams.
- No se admite el uso compartido de la pantalla con el chat.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Establecer si los usuarios de Teams pueden comunicarse con usuarios de Skype

Como administrador, use el Microsoft Centro de administración de Teams o PowerShell para establecer la configuración de acceso externo para controlar si los usuarios de Teams de su organización pueden comunicarse con usuarios de Skype. De forma predeterminada, esta funcionalidad está activada para los nuevos inquilinos. Sin embargo, hay un requisito previo para que el siguiente registro SRV de DNS deba configurarlo el Administración de TI si aún no está disponible para su dominio, por ejemplo, _sipfederationtls._tcp.contoso.com.  

**Servicio**: sipfederationtls<br/>
**Protocolo**: TCP<br/>
**Prioridad**: 100<br/>
**Peso**: 1<br/>
**Puerto**: 5061<br/>
**Objetivo**: sipfed.online.lync.com

Si ha actualizado de Skype Empresarial a Teams, la configuración de comunicaciones externas que configuró en el centro de administración de Skype Empresarial se migra a Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>En el centro de administración de Microsoft Teams

En el Microsoft Centro de administración de Teams, vaya a **Usuarios** >  con **acceso externo** y active **Los usuarios pueden comunicarse con usuarios de Skype**. Para obtener instrucciones paso a paso sobre cómo configurar esta y otras opciones de acceso externo, consulte [Administrar el acceso externo en Teams](./manage-external-access.md#allow-or-block-domains).

### <a name="using-powershell"></a>Con PowerShell

Haga lo siguiente: 
1. Use el cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) junto con el ```EnablePublicCloudAccess``` parámetro para controlar si los usuarios de Teams pueden comunicarse con usuarios de Skype. Establecer el parámetro para permitir que ```true``` los usuarios de Teams se comuniquen con usuarios de Skype. Puede usar el ```EnablePublicCloudAudioVideoAccess``` parámetro para habilitar/deshabilitar llamadas de audio o vídeo.

2. Use el cmdlet [Set-CsTenant PostProvider](/powershell/module/skype/Set-CsTenantPublicProvider) junto con el ```Provider``` parámetro establecido para ```"WindowsLive"``` que los usuarios de Teams puedan comunicarse con usuarios de Skype.

## <a name="related-topics"></a>Temas relacionados

- [Administrar el acceso externo en Teams](manage-external-access.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)

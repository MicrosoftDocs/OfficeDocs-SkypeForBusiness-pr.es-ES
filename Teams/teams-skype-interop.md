---
title: interoperabilidad Teams y Skype
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Obtenga información sobre las capacidades de interoperabilidad entre los usuarios de Teams de su organización y los usuarios de Skype (consumidores).
ms.localizationpriority: medium
ms.openlocfilehash: dd5bb05f1206baf94f2651899d0c49edbf6fe902
ms.sourcegitcommit: 5bb00d639828c744951a39705fefe81ed6698efe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2022
ms.locfileid: "66167274"
---
# <a name="teams-and-skype-interoperability"></a>interoperabilidad Teams y Skype

En este artículo se ofrece información general sobre las capacidades de interoperabilidad entre Microsoft Teams y Skype (consumidor). Obtenga información sobre cómo Teams usuarios y Skype los usuarios pueden comunicarse a través de chats y llamadas y los controles de administrador que se aplican.

Teams usuarios de su organización pueden chatear con los usuarios de Skype y llamar a ellos con su dirección de correo electrónico y viceversa.

- Teams usuarios pueden buscar e iniciar una conversación de solo texto individual o una llamada de audio o vídeo con un usuario Skype.
- Skype los usuarios pueden buscar e iniciar una conversación de solo texto individual o una llamada de audio o vídeo con un usuario Teams.

Estas funcionalidades están disponibles en los clientes de escritorio, web y móvil (Android y iOS) tanto para Teams como para Skype. Para obtener una experiencia óptima, se recomienda Skype versión 8.58 y posteriores.

> [!NOTE]
> Las funcionalidades de interoperabilidad de Teams y Skype que se describen en este artículo no están disponibles en GCC, GCC High, implementaciones de DOD ni en entornos de nube privada.

## <a name="chat-and-calling-experience"></a>Experiencia de chat y llamadas

Esta es una descripción general de la experiencia de chat y llamadas.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams usuario inicia un chat o una llamada con un usuario Skype

Teams los usuarios pueden buscar un usuario de Skype escribiendo su dirección de correo electrónico en un chat nuevo o en la barra de búsqueda.  A continuación, el usuario Teams puede seleccionar el usuario Skype en los resultados de la búsqueda para iniciar un chat o una llamada con el usuario.

Un usuario Skype puede elegir no aparecer en los resultados de búsqueda. En este caso, no aparecerán en los resultados de búsqueda en Teams y Teams los usuarios no podrán encontrarlos.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype usuario inicia un chat o una llamada con un usuario Teams

Skype los usuarios pueden buscar e iniciar un chat con un Teams usuario mediante su dirección de correo electrónico. Al usuario Teams se le notifica que tiene un mensaje nuevo de un usuario de Skype y primero tiene que aceptar el mensaje antes de poder responderlo.

- Si el usuario Teams selecciona **Aceptar**, se acepta la conversación y ambos usuarios pueden chatear y llamar entre sí.
- Si el usuario Teams selecciona **Bloquear**, se bloqueará la conversación y se bloquearán los mensajes y las llamadas posteriores de esa Skype usuario.
- Si el usuario Teams selecciona **Ver mensajes**, el mensaje se muestra en Teams, lo que ayuda al usuario a decidir si desea aceptar o bloquear la conversación.

> [!NOTE]
> Si ha actualizado de Skype Empresarial a Teams y los usuarios están en modo Solo Teams, los chats y las llamadas de Skype usuarios a Teams usuarios se entregan a Teams. Si los usuarios se encuentran en el modo Islas, los chats y las llamadas de Skype usuarios a Teams usuarios se entregan a Skype Empresarial.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams usuario bloquea o desbloquea un usuario Skype

Después de que un usuario de Teams acepte o bloquee la solicitud de conversación inicial de un usuario de Skype, puede elegir bloquear o desbloquear a esa persona en cualquier momento. Puede hacerlo en la conversación o en la configuración de privacidad de Teams. Skype los usuarios no sabrán que se les ha bloqueado.

Los usuarios bloqueados Skype, junto con otros usuarios y los números de teléfono de la red telefónica conmutada (RTC) que ha bloqueado un usuario de Teams, aparecen en la lista de contactos bloqueados del usuario en Teams.

## <a name="limitations"></a>Limitaciones

- Las conversaciones son solo de texto. Esto significa que no hay formato enriquecido, @mentions, emojis u otras características de chat que estén disponibles en una [experiencia de chat nativa Teams](native-chat-for-external-users.md).
- Las conversaciones son individuales. Los chats grupales no son compatibles.
- Teams los usuarios y los usuarios de Skype no pueden ver la presencia de los demás.
- No se admite la búsqueda de Skype usuarios con su id. de Skype o número de teléfono.
- Skype los usuarios no pueden llamar a Teams usuarios que configuran el desvío de llamadas al número de otro usuario, al número de un delegado o a un número de red telefónica conmutada (RTC).  Solo se admite el correo de voz.
- No se admite la escalación de interoperabilidad, las llamadas de grupo y las reuniones.
- No se admite la posibilidad de que un delegado llame a un usuario Skype en nombre de un usuario de Teams.
- No se admite el uso compartido de la pantalla con el chat.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Establecer si Teams los usuarios pueden comunicarse con Skype usuarios

Como administrador, use el centro de administración de Microsoft Teams o PowerShell para establecer la configuración de acceso externo y controlar si Teams usuarios de su organización pueden comunicarse con Skype usuarios. De forma predeterminada, esta funcionalidad está activada para los nuevos inquilinos. Sin embargo, hay un requisito previo para que el siguiente registro SRV de DNS deba configurarlo el Administración de TI si aún no está disponible para su dominio, por ejemplo, _sipfederationtls._tcp.contoso.com.  

**Servicio**: sipfederationtls<br/>
**Protocolo**: TCP<br/>
**Prioridad**: 100<br/>
**Peso**: 1<br/>
**Puerto**: 5061<br/>
**Objetivo**: sipfed.online.lync.com

Si ha actualizado de Skype Empresarial a Teams, la configuración de comunicaciones externas que configuró en el centro de administración de Skype Empresarial se migra a Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>En el centro de administración de Microsoft Teams

En el centro de administración de Microsoft Teams, vaya a **Usuarios** > **con acceso externo** y active **Los usuarios pueden comunicarse con Skype usuarios**. Para obtener instrucciones paso a paso sobre cómo configurar esta y otras opciones de acceso externo, vea [Administrar el acceso externo en Teams](./manage-external-access.md#allow-or-block-domains).

### <a name="using-powershell"></a>Con PowerShell

Haga lo siguiente: 
1. Use el cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) junto con el ```EnablePublicCloudAccess``` parámetro para controlar si los usuarios de Teams pueden comunicarse con Skype usuarios. Establecer el parámetro para que permita a ```true``` Teams usuarios comunicarse con Skype usuarios. Puede usar el ```EnablePublicCloudAudioVideoAccess``` parámetro para habilitar/deshabilitar llamadas de audio o vídeo.

2. Use el cmdlet [Set-CsTenant PostProvider](/powershell/module/skype/Set-CsTenantPublicProvider) junto con el ```Provider``` parámetro establecido para ```"WindowsLive"``` que los usuarios de Teams puedan comunicarse con usuarios de Skype.

## <a name="related-topics"></a>Temas relacionados

- [Administrar el acceso externo en Teams](manage-external-access.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)

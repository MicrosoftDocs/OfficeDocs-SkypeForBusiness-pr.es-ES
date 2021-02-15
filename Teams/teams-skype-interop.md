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
ms.openlocfilehash: 8bb6a83eddc60ff680d1a08c7266e082dd8b0188
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055652"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilidad de Teams e Skype

En este artículo se ofrece información general sobre las capacidades de interoperabilidad entre Microsoft Teams y Skype (consumidor). Obtenga información sobre cómo los usuarios de Teams y Skype se pueden comunicar a través de chats, llamadas y los controles de administración que se aplican.

Los usuarios de Teams de su organización pueden chatear con usuarios de Skype y llamar a ellos mediante su dirección de correo electrónico y viceversa.

- Los usuarios de Teams pueden buscar e iniciar una conversación privada solo para texto o una llamada de audio o vídeo con un usuario de Skype.
- Los usuarios de Skype pueden buscar e iniciar una conversación privada solo para texto o una llamada de audio o vídeo con un usuario de Teams.

Estas funcionalidades están disponibles en el escritorio, en la web y en los clientes móviles (Android e iOS) tanto para Teams como para Skype. Para obtener una experiencia óptima, recomendamos la versión 8.58 de Skype y versiones posteriores.

> [!NOTE]
> Las funciones de interoperabilidad de Teams y Skype analizadas en este artículo no están disponibles en implementaciones GCC, GCC High o DOD, ni en entornos de nube privados.

## <a name="chat-and-calling-experience"></a>Experiencia de chat y llamadas

Esta es una descripción general de la experiencia de chat y llamadas.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Un usuario de Teams inicia un chat o una llamada con un usuario de Skype

Los usuarios de Teams pueden buscar un usuario de Skype escribiendo su dirección de correo electrónico en un chat nuevo o en la barra de búsqueda.  A continuación, el usuario de Teams puede seleccionar el usuario de Skype en los resultados de búsqueda para iniciar un chat o una llamada con él.

Un usuario de Skype puede elegir no aparecer en los resultados de búsqueda. En este caso, no se mostrarán en los resultados de búsqueda en Teams y los usuarios de Teams no podrán encontrarlos.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Un usuario de Skype inicia un chat o una llamada con un usuario de Teams

Los usuarios de Skype pueden buscar e iniciar un chat con un usuario de Teams mediante su dirección de correo electrónico. Al usuario de Teams se le notifica que tiene un mensaje nuevo de un usuario de Skype y primero tiene que aceptar el mensaje antes de poder responder.

- Si el usuario de Teams selecciona **Aceptar,** la conversación se aceptará y ambos usuarios podrán chatear y llamarse entre sí.
- Si el usuario de Teams selecciona **Bloquear,** la conversación se bloquea y se bloquean los mensajes y llamadas siguientes de ese usuario de Skype.
- Si el usuario de Teams selecciona Ver **mensajes,** el mensaje se muestra en Teams, lo que ayuda al usuario a decidir si desea aceptar o bloquear la conversación.

> [!NOTE]
> Si ha actualizado de Skype Empresarial a Teams y los usuarios están en modo Solo equipos, los chats y llamadas de los usuarios de Skype a los usuarios de Teams se entregan a Teams. Si los usuarios se encuentran en el modo Islas, los chats y llamadas de los usuarios de Skype a los usuarios de Teams se entregan a Skype Empresarial.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Un usuario de Teams bloquea o desbloquea un usuario de Skype

Después de que un usuario de Teams acepte o bloquee la solicitud de conversación inicial de un usuario de Skype, puede elegir bloquear o desbloquear a esa persona en cualquier momento. Pueden hacerlo en la conversación o en su configuración de privacidad en Teams. Los usuarios de Skype no sabrán que se han bloqueado.

Los usuarios bloqueados de Skype, junto con otras personas y los números de teléfono de la red telefónica conmutada (RTC) que ha bloqueado un usuario de Teams, aparecen en la lista de contactos bloqueados del usuario en Teams.

## <a name="limitations"></a>Limitaciones

- Las conversaciones son de solo texto. Esto significa que no hay ningún formato enriquecido, @mentions, emojis u otras características de chat que estén disponibles en una experiencia de [chat nativa de Teams.](native-chat-for-external-users.md)
- Las conversaciones son solo uno a uno. Los chats grupales no son compatibles.
- Los usuarios de Teams y Skype no pueden ver la presencia de los demás.
- No se admite la búsqueda de usuarios de Skype mediante su id. de Skype o número de teléfono.
- Los usuarios de Skype no pueden llamar a los usuarios de Teams que configuren el reenvío de llamadas al número de otro usuario, al número de un delegado o a un número de red telefónica conmutada (RTC).  Solo se admite el correo de voz.
- La escalación de interoperabilidad, las llamadas de grupo y las reuniones no son compatibles.
- La posibilidad de que un delegado llame a un usuario de Skype en nombre de un usuario de Teams no es compatible.
- No se admite el uso compartido de la pantalla con el chat.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Establecer si los usuarios de Teams se pueden comunicar con usuarios de Skype

Como administrador, puede usar el Centro de administración de Microsoft Teams o PowerShell para establecer la configuración de acceso externo para controlar si los usuarios de Teams de su organización pueden comunicarse con los usuarios de Skype. De forma predeterminada, esta función está activada para nuevos inquilinos. Sin embargo, hay un requisito previo para que el administrador de TI tenga que configurar el siguiente registro SRV de DNS si aún no está disponible para su dominio, por ejemplo, _sipfederationtls.contoso.com.  

**Servicio:** sipfederationtls<br/>
**Protocolo**: TCP<br/>
**Prioridad**: 100<br/>
**Peso**: 1<br/>
**Puerto:** 5061<br/>
**Destino:** sipfed.online.lync.com

Si ha actualizado de Skype Empresarial a Teams, la configuración de comunicaciones externas que configuró en el Centro de administración de Skype Empresarial se migrará a Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>En el centro de administración de Microsoft Teams

En el Centro de administración de Microsoft Teams, vaya a configuración para toda la organización Acceso externo y active Los usuarios pueden comunicarse  >  con usuarios **de Skype.** Para obtener instrucciones paso a paso sobre cómo configurar esta y otras opciones de acceso externo, consulte Administrar el [acceso externo en Teams.](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)

### <a name="using-powershell"></a>Con PowerShell

Haga lo siguiente: 
1. Use el [cmdlet Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) junto con el parámetro para controlar si los usuarios de ```EnablePublicCloudAccess``` Teams se pueden comunicar con usuarios de Skype. La configuración del parámetro permite ```true``` a los usuarios de Teams comunicarse con usuarios de Skype. Puede usar el parámetro ```EnablePublicCloudAudioVideoAccess``` para habilitar o deshabilitar las llamadas de audio y vídeo.

2. Use el [cmdlet Set-CsTenantProviderprovider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) junto con el parámetro establecido en para que los usuarios de Teams puedan comunicarse ```Provider``` con los usuarios de ```"WindowsLive"``` Skype.

## <a name="related-topics"></a>Temas relacionados

- [Administrar el acceso externo en Teams](manage-external-access.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)

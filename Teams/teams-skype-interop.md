---
title: Interoperabilidad entre equipos y Skype
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Obtenga más información sobre las capacidades de interoperabilidad entre los usuarios de los equipos de su organización y los usuarios de Skype (consumidor).
localization_priority: Normal
ms.openlocfilehash: 00bd5c079a062875ebf5569600803e1c366429fe
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410435"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilidad entre equipos y Skype

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Este artículo le ofrece una descripción general de las capacidades de interoperabilidad entre Microsoft Teams y Skype (consumidor). Obtenga información sobre cómo los usuarios de Teams y los usuarios de Skype pueden comunicarse a través de chats y llamadas, y los controles de administrador que se aplican.

Los usuarios de Teams de su organización pueden chatear y llamar a usuarios de Skype usando su dirección de correo electrónico y viceversa.

- Los usuarios de Teams pueden buscar e iniciar una conversación de solo texto única o una llamada de audio o vídeo con un usuario de Skype.
- Los usuarios de Skype pueden buscar e iniciar una conversación de solo texto única o una llamada de audio o vídeo con un usuario de Teams.

Está disponible en los clientes de escritorio, Web y móviles (Android e iOS) tanto para equipos como para Skype. Para obtener una experiencia óptima, recomendamos la versión 8,58 de Skype y versiones posteriores.

## <a name="chat-and-calling-experience"></a>Experiencia de llamadas y chat

A continuación se ofrece una descripción general de la conversación y la experiencia de llamada.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>El usuario de Teams inicia una conversación o una llamada con un usuario de Skype

Los usuarios de Teams pueden buscar un usuario de Skype escribiendo su dirección de correo electrónico en una nueva conversación o en la barra de búsqueda.  A continuación, el usuario de Teams puede seleccionar el usuario de Skype en los resultados de la búsqueda para iniciar un chat o una llamada con ellos.

Un usuario de Skype puede elegir no aparecer en los resultados de búsqueda. En este caso, no aparecerán en los resultados de la búsqueda en Teams y Teams, ya que los usuarios no podrán encontrarlos.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>El usuario de Skype inicia un chat o una llamada con un usuario de Teams

Los usuarios de Skype pueden buscar e iniciar una conversación con un usuario de Teams usando su dirección de correo electrónico. Se notifica al usuario de los equipos que tiene un mensaje nuevo de un usuario de Skype y primero debe aceptar el mensaje antes de que pueda responder a él.

- Si el usuario de Teams selecciona **Aceptar**, se acepta la conversación y ambos usuarios pueden chatear y llamarse entre sí.
- Si el usuario de Teams selecciona **bloquear**, la conversación se bloquea y los mensajes y las llamadas posteriores de ese usuario de Skype se bloquean.
- Si el usuario de Teams selecciona **Ver mensajes**, el mensaje se muestra en Teams, lo que permite al usuario decidir si desea aceptar o bloquear la conversación.

> [!NOTE]
> Si ha actualizado de Skype empresarial a teams y los usuarios solo se encuentran en el modo de solo equipos, los chats y las llamadas de los usuarios de Skype a los usuarios de Teams se envían a teams. Si los usuarios están en modo islas, las conversaciones y las llamadas de usuarios de Skype a usuarios de Teams se envían a Skype empresarial.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>El usuario de Teams bloquea o desbloquea un usuario de Skype

Después de que el usuario de un equipo acepte o bloquee la solicitud de conversación inicial de un usuario de Skype, podrá elegir bloquear o desbloquear esa persona en cualquier momento, ya sea en la conversación o en la configuración de privacidad de Teams. Los usuarios de Skype no sabrán que han sido bloqueados.

Los usuarios de Skype bloqueados, junto con otras personas y números de teléfono de red telefónica conmutada (RTC) que un usuario de un equipo ha bloqueado, aparecen en la lista de contactos bloqueados del usuario en Teams.

## <a name="limitations"></a>Algunas

- Las conversaciones son solo de texto. Esto significa que no hay ningún formato enriquecido, @mentions, Emoji ni ninguna otra de las características de chat que están disponibles en una experiencia de [chat de equipos nativos](native-chat-for-external-users.md).
- Las conversaciones son solo una persona. Los chats grupales no son compatibles.
- Los usuarios de Teams y los usuarios de Skype no pueden ver la presencia de los demás.
- No se admite la búsqueda de usuarios de Skype mediante su identificador de Skype o número de teléfono.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Establecer si los usuarios de Teams pueden comunicarse con usuarios de Skype

Como administrador, use el centro de administración de Microsoft Teams o PowerShell para establecer la configuración de acceso externo para controlar si los usuarios de Teams de su organización pueden comunicarse con los usuarios de Skype. De forma predeterminada, esta capacidad está activada para los inquilinos nuevos.

Si ha actualizado de Skype empresarial a Teams, la configuración de comunicaciones externas que configuró en el centro de administración de Skype empresarial se migrará a teams.

### <a name="in-the-microsoft-teams-admin-center"></a>En el centro de administración de Microsoft Teams

En el centro de administración de Microsoft Teams, vaya a configuración de acceso externo a **toda la organización**  >  **External access**y Active **los usuarios pueden comunicarse con los usuarios de Skype**. Para obtener instrucciones paso a paso sobre cómo configurar esta y otras opciones de acceso externo, consulte [administrar el acceso externo en Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).

### <a name="using-powershell"></a>Con PowerShell

Use el cmdlet [set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) junto con el ```EnablePublicCloudAccess``` parámetro para controlar si los usuarios de Teams pueden comunicarse con los usuarios de Skype. Establecer el parámetro para ```true``` permitir que los usuarios de Teams se comuniquen con usuarios de Skype. Ten en cuenta que el ```EnablePublicCloudAudioVideoAccess``` parámetro puede usarse para habilitar o deshabilitar las llamadas de audio y vídeo.

## <a name="related-topics"></a>Temas relacionados

- [Administrar el acceso externo en Teams](manage-external-access.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)

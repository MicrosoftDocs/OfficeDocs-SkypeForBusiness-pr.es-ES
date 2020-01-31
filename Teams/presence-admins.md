---
title: La presencia del usuario en Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Información para administradores sobre la presencia en Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7660cc35986b8b0debc449bacde686bb9e2694b
ms.sourcegitcommit: 43a17ce6fea3951719b55bfbda03c500cef4816c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41580927"
---
# <a name="user-presence-in-teams"></a>La presencia del usuario en Teams

La presencia es parte de un perfil de usuario de Microsoft Teams (y de toda la 365 de Office) que indica la disponibilidad y el estado actuales del usuario a otros usuarios. De forma predeterminada, cualquier persona de la organización que use Teams puede ver (en casi tiempo real) si hay otros usuarios disponibles en línea.

> [!IMPORTANT]
> Si desinstala el cliente de Skype Empresarial después de mover un usuario al modo **Teams solo**, la presencia dejará de funcionar en Outlook y en otras aplicaciones de Office. La presencia funciona bien en Teams. Solución: para ver la presencia en Outlook (y en otras aplicaciones de Office), debe estar instalado Skype empresarial, incluso si está ejecutando Teams en modo de **solo Teams** . Microsoft es consciente de este problema y está buscando una solución. 

La presencia de Teams en Outlook es compatible con la aplicación de escritorio Outlook 2013 y posteriores.

## <a name="presence-states-in-teams"></a>Estados de presencia en Teams

Los Estados de presencia de usuario disponibles en Teams son:

|Usuario configurado|Aplicación configurada|
|:--- |:---|
| ![Marca de verificación verde sólido, indica la presencia disponible](media/Presence_Available.png) Disponible|![Marca de verificación verde sólido, indica la presencia disponible](media/Presence_Available.png) Disponible|
|| ![Abrir la marca de verificación verde, indica el OOF disponible](media/Presence_Available_OOF.png) Disponible, fuera de la oficina |
|  ![Círculo rojo sólido, indica ocupado](media/Presence_Busy.png) Ocupado |  ![Círculo rojo sólido, indica ocupado](media/Presence_Busy.png) Ocupado  |
|| ![Círculo rojo sólido, indica ocupado en una llamada](media/Presence_Busy.png) En una llamada|
|| ![Círculo rojo sólido, indica ocupado en una reunión](media/Presence_Busy.png) En una reunión |
|| ![Abrir un círculo rojo, indica ocupado](media/Presence_Busy_OOF.png) En una llamada, fuera de la oficina|
|  ![Círculo rojo con línea blanca, indica que no molestar](media/Presence_DND.png) No molestar ||
|| ![Un círculo rojo con línea blanca indica la presentación](media/Presence_DND.png) Moderado|
|| ![Un círculo rojo con línea blanca indica el foco](media/Presence_DND.png) Énfasis|
| ![Icono de reloj amarillo, indica ausente](media/Presence_Away.png) Desaparece| ![Icono de reloj amarillo, indica ausente](media/Presence_Away.png) Desaparece|
|| ![Icono de reloj amarillo, que](media/Presence_Away.png) indica que está fuera de la última *hora* de vista|
|![Icono amarillo de reloj, indica que está ausente, volver a la derecha](media/Presence_Away.png) Enseguida regreso| |
|| ![Icono de reloj amarillo, indica que no hay trabajo](media/Presence_Away.png)  Descuento en el trabajo|
|| ![Círculo gris con x, indica sin conexión](media/Presence_Offline.png) Línea |
|| ![Abrir un círculo gris, indica el estado desconocido](media/Presence_Unknown.png) Estado desconocido|
||![Círculo rojo abierto con línea diagonal, indica bloqueado](media/Presence_Blocked.png) Bloqueado |
|| ![Círculo púrpura con flecha, indica fuera de la oficina](media/Presence_OOF.png) Fuera de la oficina|
|||
 
Los usuarios pueden establecer manualmente el estado de presencia actual en algunas opciones, y su estado se reflejará a todos los demás usuarios. También se actualizan automáticamente más detalles de presencia de usuario. Los cambios se basan en la actividad del usuario (disponible, ausente), Estados del calendario de Outlook (en una reunión) o Estados de la aplicación de Teams (en una llamada, presentando), para Estados que tienen sangría en la lista. Hay un tiempo de espera de 15 minutos de inactividad, después de que el estado de presencia actual se restablezca a ausente.

Los usuarios reciben todos los mensajes de chat que se les envían en Teams, independientemente de su estado de presencia. Si un usuario está desconectado cuando alguien le envía un mensaje, el mensaje de la conversación aparecerá en teams la próxima vez que el usuario esté conectado. Si un usuario se encuentra en un estado de no molestar, el usuario recibirá mensajes instantáneos pero no se mostrará una notificación emergente.

Los usuarios reciben llamadas en todos los Estados de presencia, excepto los Estados no molestar, en los que las llamadas entrantes se envían a su buzón de voz. Si el destinatario bloqueó al autor de la llamada, la llamada no se entregará y el autor de la llamada verá la presencia del destinatario como desconectado.

Los usuarios pueden agregar personas a su lista de acceso prioritario yendo a **configuración** > **privacidad** en Teams. Las personas con acceso prioritario pueden ponerse en contacto con el usuario incluso cuando el usuario se encuentra en un estado de no molestar.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Configuración de administración de equipos comparada con Skype empresarial

La siguiente configuración de administración de Skype empresarial es diferente en Teams:

- En Teams, el uso compartido de presencia siempre está habilitado para los usuarios de la organización. La configuración de privacidad (donde se define quién puede ver la presencia) no está disponible en Teams.
- El uso compartido de presencia con todos los usuarios (incluidos los servicios federados) siempre está habilitado para los usuarios en Teams. Su lista de contactos (si tenía una en Skype empresarial) está visible en **conversación > contactos** o en **llamadas > contactos**.
- Las características de cliente no molestar y de avance siempre están habilitadas para los usuarios de Teams.
- La integración de calendario (incluye fuera de oficina y otra información de calendario) siempre está habilitada para los usuarios cuando se integran Teams con Outlook.
- El *último* indicador, visto o *ausente, ya* está habilitado para los usuarios de Teams si la organización también usa Skype empresarial.

> [!NOTE]
> La capacidad de un administrador de equipos para personalizar esta configuración no es compatible actualmente.

## <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

Vea [coexistencia con Skype empresarial](coexistence-chat-calls-presence.md) para obtener información sobre cómo funciona la presencia de Teams cuando su organización también usa Skype empresarial.

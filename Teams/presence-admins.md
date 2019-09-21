---
title: Presencia de usuario en Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Información para administradores sobre la presencia en Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd57165cbb88df135827ae72fa3952dd8ddd452
ms.sourcegitcommit: 299f854bbb73887ba315b09b9adf9ea9ff91e8ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37062966"
---
# <a name="user-presence-in-teams"></a>Presencia de usuario en Teams

La presencia es parte de un perfil de usuario de Microsoft Teams (y de toda la 365 de Office) que indica la disponibilidad y el estado actuales del usuario a otros usuarios. De forma predeterminada, cualquier persona de la organización que use Teams puede ver (en casi tiempo real) si hay otros usuarios disponibles en línea.

> [!IMPORTANT]
> Si desinstala el cliente de Skype empresarial después de mover un usuario al modo **solo de Teams** , la presencia dejará de funcionar en Outlook y en otras aplicaciones de Office. La presencia funciona bien en Teams. Solución: para ver la presencia en Outlook (y en otras aplicaciones de Office), debe estar instalado Skype empresarial, incluso si está ejecutando Teams en modo de **solo Teams** . Microsoft es consciente de este problema y está trabajando en una corrección.

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
 
Los usuarios pueden establecer manualmente el estado de presencia actual en algunas opciones, y su estado se reflejará a todos los demás usuarios. También se actualizan automáticamente más detalles de presencia de usuario. Los cambios se basan en la actividad del usuario (disponible, ausente), Estados del calendario de Outlook (en una reunión) o Estados de la aplicación de Teams (en una llamada, presentando), para Estados que tienen sangría en la lista.

Hay un tiempo de espera de 15 minutos de inactividad, después de que el estado de presencia actual se restablezca a ausente.

Los usuarios pueden especificar quién puede romperse (es decir, póngase en contacto con él a pesar de un estado no molestar). Esta configuración está disponible en el cliente de Teams.

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

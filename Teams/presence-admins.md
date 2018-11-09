---
title: Presencia de usuario en los equipos
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rakayala
description: Los administradores de información deben conocer acerca de la presencia en los equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1934a602d89240c89ffb4f7410192d19a7dd2e61
ms.sourcegitcommit: 139b3d3b7fcc1dd7fba7fd14ff34e4ffdfcc7eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2018
ms.locfileid: "26038882"
---
# <a name="user-presence-in-teams"></a>Presencia de usuario en los equipos

Presencia forma parte de un perfil de usuario en Microsoft Teams (y a lo largo de Office 365) – e indica la disponibilidad actual y el estado a otros usuarios de la organización del usuario. De forma predeterminada, cualquier persona de su organización con los equipos puede ver si otros usuarios están disponibles en línea.

## <a name="presence-states-in-teams"></a>Estados de presencia en los equipos

Los Estados de presencia de usuario disponibles en los equipos son:

|Configurada por el usuario|Aplicación configurado|
|:--- |:---|
| ![Presencia disponible](media/Presence_Available.png) Disponible|![Presencia disponible](media/Presence_Available.png) Disponible|
|| ![oof disponible](media/Presence_Available_OOF.png) Está disponible, fuera de la oficina |
|  ![No disponible](media/Presence_Busy.png) No disponible |  ![No disponible](media/Presence_Busy.png) No disponible  |
|| ![No disponible](media/Presence_Busy.png) En una llamada|
|| ![No disponible](media/Presence_Busy.png) En una reunión |
|| ![oof ocupado](media/Presence_Busy_OOF.png) En una llamada, fuera de la oficina|
|  ![No molestar](media/Presence_DND.png) No molestar ||
|| ![No molestar](media/Presence_DND.png) Presentación|
| ![estado ausente](media/Presence_Away.png) Estado ausente| ![estado ausente](media/Presence_Away.png) Estado ausente|
|| ![ausente](media/Presence_Away.png) como ausente último visto *tiempo*|
|![estado ausente](media/Presence_Away.png) Enseguida regreso| |
|| ![estado ausente](media/Presence_Away.png)  Día libre|
|| ![Sin conexión](media/Presence_Offline.png) Sin conexión |
|| ![desconocido](media/Presence_Unknown.png) Estado desconocido|
||![bloqueado](media/Presence_Blocked.png) Bloqueado |
|| ![Fuera de la oficina](media/Presence_OOF.png) Fuera de la oficina|
|||
 
Los usuarios pueden establecer manualmente su estado de presencia actual a algunas de las opciones y obtiene refleja su estado a todos los demás usuarios. Detalles de la presencia de usuario adicionales también se actualizan automáticamente en función de la actividad del usuario (por ejemplo, disponible o ausente), Estados del calendario de Outlook (como en una reunión) o Estados de la aplicación de los equipos (en una llamada, presentar), los Estados de las que se aplica sangría en la lista.

No hay un tiempo de espera de inactividad de 15 minutos, después del cual se restablecerá el estado de presencia actual de los usuarios a ausente.

Los usuarios pueden especificar quién puede interrumpir a través de (póngase en contacto con ellos reemplazar una opción de configuración no molestar). Estas opciones están disponibles en la aplicación.

## <a name="teams-is-not-skype-for-business"></a>Los equipos no es Skype para la empresa

La siguiente configuración de administración en Skype para la empresa es diferente en los equipos:
- Uso compartido de presencia siempre está habilitado en los equipos de los usuarios de la organización. Configuración de privacidad (decidir quién puede ver la presencia) no está disponible en los equipos.
- Uso compartido con todos los usuarios (incluidos los servicios federados) de presencia siempre está habilitado para los usuarios en los equipos. Está visible en su lista de contactos (si tuvieran uno en SfB) **conversaciones > contactos** o en **llamadas > contactos**.
- Características de cliente no molestar e innovadora siempre están habilitadas para los usuarios en los equipos.
- Calendario (incluye OOF & otra información de calendario) integración siempre está habilitada para los usuarios de los equipos si integrado con Outlook.
- El indicador de *Ausente desde* (si está en un entorno dual con Skype para la empresa) o *visto por última vez* siempre está habilitado para los usuarios en los equipos.
- Establecer un estado de presencia personalizados no está habilitado para los usuarios en los equipos.

> [!NOTE]
> La capacidad de una administración de equipos para personalizar estas opciones no se admite actualmente.


## <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype para la empresa

Para obtener información detallada sobre el funcionamiento de presencia de los equipos cuando coexisten con Skype para la empresa, vea [coexistencia con Skype para la empresa](coexistence-chat-calls-presence.md) . 
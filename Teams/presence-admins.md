---
title: Presencia de usuario en Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Los administradores de la información deben comprender la presencia en Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11902a5d6ef768afa6d7bb1bba2f33b64757fef1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222096"
---
# <a name="user-presence-in-teams"></a>Presencia de usuario en Teams

La presencia es parte del perfil de un usuario en Microsoft Teams (y en todo el Office 365), e indica la disponibilidad y el estado actuales del usuario a otros usuarios de la organización. De forma predeterminada, cualquier persona de la organización que use Teams puede ver, casi en tiempo real, si otros usuarios están disponibles en línea.

## <a name="presence-states-in-teams"></a>Estados de presencia en Teams

Los Estados de presencia de usuario disponibles en Teams son:

|Usuario configurado|Aplicación configurada|
|:--- |:---|
| ![Marca CHEK verde sólido, que indica presencia disponible](media/Presence_Available.png) Disponible|![Marca CHEK verde sólido, que indica presencia disponible](media/Presence_Available.png) Disponible|
|| ![Marca de CHEK verde abierto, que indica el OOF disponible](media/Presence_Available_OOF.png) Disponible, fuera de la oficina |
|  ![Círculo rojo sólido, que indica que está ocupado](media/Presence_Busy.png) Ocupado |  ![Círculo rojo sólido, que indica que está ocupado](media/Presence_Busy.png) Ocupado  |
|| ![Círculo rojo sólido, que indica que está ocupado en una llamada](media/Presence_Busy.png) En una llamada|
|| ![Círculo rojo sólido, que indica que está ocupado en una reunión](media/Presence_Busy.png) En una reunión |
|| ![Abrir un círculo rojo, que indica un OOF ocupado](media/Presence_Busy_OOF.png) En una llamada, fuera de la oficina|
|  ![Círculo rojo con línea blanca, que indica que no molestar](media/Presence_DND.png) No molestar ||
|| ![Círculo rojo con línea blanca, que indica la presentación](media/Presence_DND.png) Moderado|
| ![Icono de reloj amarillo, que indica que está ausente](media/Presence_Away.png) Desaparece| ![Icono de reloj amarillo, que indica que está ausente](media/Presence_Away.png) Desaparece|
|| ![Icono de reloj amarillo, que](media/Presence_Away.png) indica que se está alejando la *hora* de última vista|
|![Icono de reloj amarillo, que indica que está ausente, volver al final](media/Presence_Away.png) Enseguida regreso| |
|| ![Icono de reloj amarillo, que indica que está ausente, trabajo](media/Presence_Away.png)  Descuento en el trabajo|
|| ![Círculo gris con x, que indica que no tiene conexión](media/Presence_Offline.png) Línea |
|| ![Abrir un círculo gris, que indica el estado desconocido](media/Presence_Unknown.png) Estado desconocido|
||![Círculo rojo abierto con línea diagonal, que indica que está bloqueado](media/Presence_Blocked.png) Bloqueado |
|| ![Círculo púrpura con flecha, que indica fuera de la oficina](media/Presence_OOF.png) Fuera de la oficina|
|||
 
Los usuarios pueden establecer manualmente el estado de presencia actual en algunas opciones, y su estado se reflejará a todos los demás usuarios. Los detalles de presencia de usuario adicionales también se actualizan automáticamente en función de la actividad del usuario (como disponible o ausente), los Estados del calendario de Outlook (como en una reunión) o los Estados de la aplicación de Teams (en una llamada, presentar), para los Estados que tienen sangría en la lista.

Hay un tiempo de espera de 15 minutos de inactividad, después del cual el estado de presencia actual de los usuarios se restablecerá a ausente.

Los usuarios pueden especificar quién puede interrumpir (póngase en contacto con ellos invalidando la configuración de no molestar). Esta configuración está disponible en la aplicación.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Configuración de administración de equipos comparada con Skype empresarial

La siguiente configuración de administración de Skype empresarial es diferente en Teams:

- En Teams, el uso compartido de presencia siempre está habilitado para los usuarios de la organización. La configuración de privacidad (decidir quién puede ver la presencia) no está disponible en Teams.
- El uso compartido de presencia con todos los usuarios (incluidos los servicios federados) siempre está habilitado para los usuarios en Teams. Su lista de contactos (si tenía una en Skype empresarial) está visible en **conversación > contactos** o en **llamadas > contactos**.
- Las características de cliente no molestar y de avance siempre están habilitadas para los usuarios de Teams.
- La integración de calendario (incluye fuera de oficina y otra información de calendario) siempre está habilitada para los usuarios de Teams si están integrados con Outlook.
- La *última fecha* de presentación o de *ausencia* (si en un entorno dual con Skype empresarial) está siempre habilitada para los usuarios de Teams.

> [!NOTE]
> La capacidad de un administrador de equipos para personalizar esta configuración no es compatible actualmente.

## <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

Vea [coexistencia con Skype empresarial](coexistence-chat-calls-presence.md) para obtener más información sobre cómo funciona la presencia de equipos cuando coexisten con Skype empresarial. 

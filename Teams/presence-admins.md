---
title: Presencia del usuario en Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Obtenga información sobre los Estados de presencia en Teams, así como la configuración administrativa de la característica de presencia.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a944616fef0c3fd9821486a41025adf5f0fdbcc
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814579"
---
# <a name="user-presence-in-teams"></a>Presencia del usuario en Teams

La presencia es parte del perfil de un usuario en Microsoft Teams (y en Microsoft 365 u Office 365) que indica la disponibilidad y el estado actuales del usuario a otros usuarios. De forma predeterminada, cualquier persona de su organización que utilice Teams puede ver (casi en tiempo real) si otros usuarios están disponibles en línea.

La presencia de Teams en Outlook es compatible con la aplicación de escritorio Outlook 2013 y posteriores.

 > [!Note]
 > Para obtener más información [, vea características de equipo por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) .

## <a name="presence-states-in-teams"></a>Estados de presencia en Teams

|Configurado por el usuario|Aplicación configurada|
|:--- |:---|
| ![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) Disponible|![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) Disponible|
|| ![Marca de verificación verde sólida, indica Presencia Abierta marca de verificación verde, indica disponible oof](media/Presence_Available_OOF.png) Disponibles, fuera de la oficina |
|  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) Ocupado |  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) Ocupado  |
|| ![Círculo rojo sólido, indica Ocupado en una llamada](media/Presence_Busy.png) En una llamada...|
|| ![Círculo rojo sólido, indica Ocupado en una reunión](media/Presence_Busy.png) En una reunión |
|| ![Círculo rojo abierto, indica Ocupado](media/Presence_Busy_OOF.png) En una llamada, fuera de la oficina|
|  ![Círculo rojo con línea blanca, indica No molestar](media/Presence_DND.png) No molestar ||
|| ![Círculo rojo con línea blanca, indica Presentando](media/Presence_DND.png) Presentando|
|| ![Círculo rojo con línea blanca, indica Modo enfoque](media/Presence_DND.png) Modo enfoque|
| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Ausente| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Ausente|
|| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Última vez visto ausente*hora*|
|![Icono del reloj amarillo, indica que está ausente, ahora vuelvo.](media/Presence_Away.png) Ahora vuelvo| |
|| ![Icono de reloj amarillo, indica que está ausente, fuera del trabajo](media/Presence_Away.png)  Fuera del trabajo|
|| ![Círculo gris con una x, indica que está Desconectado](media/Presence_Offline.png) Offline |
|| ![Círculo gris abierto, indica estado desconocido](media/Presence_Unknown.png) Estado desconocido|
||![Círculo rojo abierto con línea diagonal, indica que está bloqueado](media/Presence_Blocked.png) Bloqueado |
|| ![Círculo púrpura con flecha, indica Fuera de la oficina](media/Presence_OOF.png) Fuera de la oficina|
|||

Los Estados de presencia configurados por la aplicación se basan en la actividad del usuario (disponible, ausente), Estados del calendario de Outlook (en una reunión) o Estados de la aplicación de Teams (en una llamada, presentando). Tenga en cuenta que cuando se encuentra en el modo de foco basado en el calendario, el foco será el estado que verán los usuarios en Teams, pero se mostrarán como no molestar en otros productos.

El estado actual de presencia cambiará a ausente cuando bloquee el equipo o cuando entre en modo de suspensión o de espera. En dispositivos móviles, el estado de presencia cambiará a ausente cuando la aplicación de Teams esté en segundo plano.

Los usuarios reciben todos los mensajes de chat que se les envían en los equipos, independientemente de su estado de presencia. Si un usuario está desconectado cuando alguien le envía un mensaje, el mensaje de chat aparece en Teams la próxima vez que el usuario se conecta. Si un usuario no molesta, el usuario aún recibirá mensajes instantáneos pero no se mostrarán las notificaciones de banner.

Los usuarios reciben llamadas en todos los Estados de presencia excepto en no molestar, en el que las llamadas entrantes se dirigen al buzón de voz. Si el destinatario bloqueó la llamada, la llamada no será entregada y la persona que llama ve la presencia del destinatario como desconectada.

Los usuarios pueden agregar a personas a su lista de acceso prioritario yendo a **Configuración** > **Privacidad** en Teams. Las personas con acceso prioritario pueden ponerse en contacto con el usuario incluso cuando el usuario está en no molestar.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Configuración de administración en equipos en comparación con Skype Empresarial

La siguiente configuración de administración Skype Empresarial es diferente en Teams:

- En Teams, el uso compartido de la presencia siempre está habilitado para los usuarios de la organización. La configuración de privacidad (donde se define quién puede ver la presencia) no está disponible en Teams.
- Compartir la presencia con todo el mundo (incluidos los servicios Federados) siempre está habilitado para los usuarios de Teams. Su lista de contactos (si tenía una en Skype Empresarial) está visible en**Chat > Contactos** o en **Llamadas > Contactos**.
- Las funciones de No molestar al cliente y Contacto siempre están habilitadas para los usuarios de Teams.
- La integración del calendario (incluye información de fuera de la oficina y otra información de calendario) siempre está habilitada para los usuarios cuando Teams se integra con Outlook.
- El indicador *Último visto* o *Ausente desde* siempre está habilitado para los usuarios en Teams si la organización también usa Skype Empresarial.

> [!NOTE]
> Actualmente no se admite la capacidad de un administrador de Teams para personalizar estos ajustes.

## <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

Consulte[ Coexistencia con Skype Empresarial ](coexistence-chat-calls-presence.md)para obtener más información sobre cómo funciona la presencia en Teams cuando tu organización también usa Skype Empresarial.

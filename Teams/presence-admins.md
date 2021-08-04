---
title: Presencia del usuario en Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Obtenga información acerca de los Estados de presencia en Teams y la configuración administrativa para la Característica de presencia.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82d9f152dbba345f876ac166bcf6833e53bab799
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718041"
---
# <a name="user-presence-in-teams"></a>Presencia del usuario en Teams

La Presencia forma parte del perfil del usuario en Microsoft Teams (así como también para Microsoft 365 u Office 365). La Presencia indica a los demás el estado y la disponibilidad actuales del usuario. De forma predeterminada, cualquier persona de su organización que utilice Teams podrá ver (casi en tiempo real) si otros usuarios están disponibles en línea. La Presencia se actualiza en tiempo real en las versiones de escritorio y web cuando se actualiza la página en dispositivos móviles.

 > [!NOTE]
 > Para obtener más información acerca de las características del perfil de usuario de Teams en las distintas plataformas, consulte [Características de Teams según la plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

 > [!NOTE]
 > Teams respeta su configuración de privacidad, de modo que, si tiene habilitado el modo de privacidad, su presencia no será visible para los usuarios externos.
## <a name="presence-states-in-teams"></a>Estados de presencia en Teams

|Configurado por el usuario|Aplicación configurada|
|:--- |:---|
| ![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) Disponible|![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) Disponible|
|| ![Marca de verificación verde sólida, indica Presencia Abierta marca de verificación verde, indica disponible oof](media/Presence_Available_OOF.png) Disponible, Fuera de la oficina. Nota: Fuera de la oficina se configura automáticamente durante los períodos en los que el usuario establece las "Respuestas automáticas". Si el usuario está usando la aplicación durante estos períodos, es posible que se muestre una presencia doble, como "Fuera de la oficina, disponible". |
|  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) Ocupado |  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) Ocupado  |
|| ![Círculo rojo sólido, indica Ocupado en una llamada](media/Presence_Busy.png) Al teléfono|
|| ![Círculo rojo sólido, indica Ocupado en una reunión](media/Presence_Busy.png) En una reunión |
|| ![Círculo rojo abierto, indica Ocupado](media/Presence_Busy_OOF.png) En una llamada, fuera de la oficina|
|  ![Círculo rojo con línea blanca, indica No molestar](media/Presence_DND.png) No molestar ||
|| ![Círculo rojo con línea blanca, indica Presentando](media/Presence_DND.png) Presentando|
|| ![Círculo rojo con línea blanca, indica Modo enfoque](media/Presence_DND.png) Concentración. El estado de concentración se produce cuando los usuarios programan el tiempo de concentración en MyAnalytics/Insights en sus calendarios.|
| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Ausente| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Ausente|
|| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Última vez visto ausente *hora*|
|![Icono del reloj amarillo, indica que está ausente, ahora vuelvo.](media/Presence_Away.png) Ahora vuelvo| |
|![El círculo gris con una x, indica Sin conexión](media/Presence_Offline.png) Desconectado|![El círculo gris con una x, indica Sin conexión](media/Presence_Offline.png) Desconectado. Cuando los usuarios no tienen la sesión iniciada en ninguno de sus dispositivos durante unos minutos, aparecen como desconectados. | |
|| ![Círculo gris abierto, indica estado desconocido](media/Presence_Unknown.png) Estado desconocido|
|| ![El círculo púrpura con una flecha, indica Fuera de la oficina](media/Presence_OOF.png) Fuera de la oficina. Fuera de la oficina se usa cuando se establece una respuesta automática. |
|||
 > [!NOTE]
 > Para los usuarios que tienen su buzón hospedado en un entorno local, se esperan retrasos de una hora (como máximo) en la presencia.

Los Estados de presencia configurados a través de la aplicación se basan en la actividad del usuario (Disponible, Ausente), en los estados del Calendario de Outlook (En una reunión) o en los estados de la aplicación Teams (En una llamada, En una presentación). Cuando se encuentre en Modo de concentración de acuerdo con su calendario, el estado que verán los demás usuarios en Teams será **Concentrado**. El Modo de concentración se mostrará como **No molestar** en los demás productos.

Su estado de presencia actual cambiará a Ausente cuando bloquee el equipo o cuando entre en el modo de inactividad o de suspensión. En los dispositivos móviles, el estado de presencia cambiará a Ausente cada vez que la aplicación Teams esté en segundo plano.

Los usuarios reciben todos los mensajes de chat que se les envían en los equipos, independientemente de su estado de presencia. Si un usuario está desconectado cuando alguien le envía un mensaje, el mensaje de chat aparece en Teams la próxima vez que el usuario se conecta. Si el estado de un usuario se establece en No molestar, el usuario recibirá igualmente los mensajes del chat, aunque no se mostrarán las notificaciones de banner.

Los usuarios podrán recibir llamadas en todos los estados de presencia excepto en No molestar, en cuyo caso, las llamadas entrantes serán dirigidas al correo de voz. Si el destinatario bloqueó la llamada, la llamada no será entregada y la persona que llama ve la presencia del destinatario como desconectada.

Los usuarios pueden agregar a personas a su lista de acceso prioritario yendo a **Configuración** > **Privacidad** en Teams. Las personas con acceso prioritario podrán contactar al usuario incluso cuando su estado sea No molestar.

### <a name="dual-presence"></a>Presencia doble

  La forma en que funcionan los estados de presencia para la mayoría de los usuarios se relaciona con los eventos del calendario o del dispositivo, como una llamada. El usuario puede anular este estado en la IU si configura manualmente los estados, los cuales tienen una fecha de expiración.

## <a name="user-configured-states-expiration"></a>Caducidad de estados configurados por el usuario

Cuando un usuario selecciona un estado de presencia específico, tendrá prioridad sobre cualquier actualización en la actividad de la aplicación. Por ejemplo, si un usuario establece su estado en No molestar, su presencia permanecerá en No molestar aunque asista a una reunión o responda una llamada.

Los estados configurados por el usuario tienen una configuración de caducidad predeterminada en Teams para evitar que los usuarios muestren un estado que podría no ser relevante después de cierto tiempo.

|Estado configurado por el usuario|Caducidad predeterminada|
|:--- |:---|
| No disponible|1 día|
| No molestar|1 día|
| Otros|7 días|
|||

> [!NOTE]
> El usuario también puede configurar de forma manual la duración de su presencia. Por ejemplo, un usuario puede establecer el estado Desconectado hasta la mañana siguiente.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Configuración de administración en equipos en comparación con Skype Empresarial

La siguiente configuración de administración Skype Empresarial es diferente en Teams:

- En Teams, el uso compartido de la presencia siempre está habilitado para los usuarios de la organización. La configuración de privacidad (en donde define quién puede ver la presencia) no está disponible en Teams.
- Compartir la presencia con todo el mundo (incluidos los servicios Federados) siempre está habilitado para los usuarios de Teams. Su lista de contactos (si tenía una en Skype Empresarial) está visible en **Chat > Contactos** o en **Llamadas > Contactos**.
- Las funciones de No molestar al cliente y Contacto siempre están habilitadas para los usuarios de Teams.
- La integración del calendario (incluye información de fuera de la oficina y otra información de calendario) siempre está habilitada para los usuarios cuando Teams se integra con Outlook.
- El indicador *Último visto* o *Ausente desde* siempre está habilitado para los usuarios en Teams si la organización también usa Skype Empresarial.

> [!NOTE]
> Actualmente no se admite la capacidad de un administrador de Teams para personalizar estos ajustes.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Opciones de administrador en Teams comparadas con Microsoft Outlook

La presencia de Teams en Outlook es compatible con la aplicación de escritorio de Outlook 2013 y posteriores para contactos de la misma organización.

Si la directiva del modo de actualización de la cuenta del usuario se establece en TeamsOnly, Outlook se comunicará con Teams para obtener la presencia. Si la cuenta del usuario no está establecida en TeamsOnly, entonces Outlook se comunicará con Skype Empresarial.

## <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

Consulte la [Coexistencia con Skype Empresarial](coexistence-chat-calls-presence.md) para obtener más información sobre cómo funciona la presencia de Teams cuando su organización también usa Skype Empresarial.

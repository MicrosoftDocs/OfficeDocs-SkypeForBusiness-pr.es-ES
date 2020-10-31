---
title: Presencia del usuario en Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Obtenga información sobre los Estados de presencia en Teams y la configuración administrativa para la característica de presencia.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 15b71f3c62d39f85275a9bb916b8ac4ed6f99abb
ms.sourcegitcommit: 273f231098799975dc4cf609a68c9944b8072ce1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2020
ms.locfileid: "48818840"
---
# <a name="user-presence-in-teams"></a>Presencia del usuario en Teams

La presencia es parte del perfil de un usuario en Microsoft Teams (y en Microsoft 365 u Office 365). Presencia indica la disponibilidad y el estado actuales del usuario a otros usuarios. De forma predeterminada, cualquier persona de su organización que utilice Teams puede ver (casi en tiempo real) si otros usuarios están disponibles en línea. La presencia se actualiza en tiempo real en la web y las versiones de escritorio al actualizar la página en dispositivos móviles.

 > [!Note]
 > Para obtener más información sobre los perfiles de usuario de Teams en diferentes plataformas, consulte [características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="presence-states-in-teams"></a>Estados de presencia en Teams

|Configurado por el usuario|Aplicación configurada|
|:--- |:---|
| ![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) Disponible|![Marca de verificación verde sólida, indica Presencia disponible](media/Presence_Available.png) Disponible|
|| ![Marca de verificación verde sólida, indica Presencia Abierta marca de verificación verde, indica disponible oof](media/Presence_Available_OOF.png) Disponible, fuera de la oficina. Nota: fuera de la oficina se establece automáticamente para los períodos de tiempo en los que el usuario establece "respuestas automáticas". Si el usuario usa la aplicación durante estos períodos de tiempo, es posible que se muestre una presencia doble, como "fuera de la oficina, disponible". |
|  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) Ocupado |  ![Círculo rojo sólido, indica Ocupado](media/Presence_Busy.png) Ocupado  |
|| ![Círculo rojo sólido, indica Ocupado en una llamada](media/Presence_Busy.png) En una llamada...|
|| ![Círculo rojo sólido, indica Ocupado en una reunión](media/Presence_Busy.png) En una reunión |
|| ![Círculo rojo abierto, indica Ocupado](media/Presence_Busy_OOF.png) En una llamada, fuera de la oficina|
|  ![Círculo rojo con línea blanca, indica No molestar](media/Presence_DND.png) No molestar ||
|| ![Círculo rojo con línea blanca, indica Presentando](media/Presence_DND.png) Presentando|
|| ![Círculo rojo con línea blanca, indica Modo enfoque](media/Presence_DND.png) Énfasis. El foco se produce cuando los usuarios programan el tiempo de enfoque en myanalytics o perspectivas en sus calendarios.|
| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Ausente| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Ausente|
|| ![Icono del reloj amarillo, indica que está ausente](media/Presence_Away.png) Última vez visto ausente *hora*|
|![Icono del reloj amarillo, indica que está ausente, ahora vuelvo.](media/Presence_Away.png) Ahora vuelvo| |
|![Círculo gris con una x, indica que está Desconectado](media/Presence_Offline.png) Aparecer como desconectado|![Círculo gris con una x, indica que está Desconectado](media/Presence_Offline.png) Línea.  Cuando los usuarios no tienen sesión en ninguno de sus dispositivos durante unos minutos, aparecen como desconectados. | |
|| ![Círculo gris abierto, indica estado desconocido](media/Presence_Unknown.png) Estado desconocido|
|| ![Círculo púrpura con flecha, indica Fuera de la oficina](media/Presence_OOF.png) Fuera de la oficina. Fuera de la oficina se usa cuando se establece una respuesta automática. (Disponible solo en Outlook). |
|||

Los Estados de presencia configurados por la aplicación se basan en la actividad del usuario (disponible, ausente), Estados del calendario de Outlook (en una reunión) o Estados de la aplicación de Teams (en una llamada, presentando). Cuando esté en el modo enfocado en el **calendario, el foco será** el estado que verán los usuarios en Teams. El modo de foco se mostrará como **no molestar** en otros productos.

El estado actual de presencia cambiará a ausente cuando bloquee el equipo o cuando el equipo entre en modo de inactividad o de suspensión. En un dispositivo móvil, el estado de presencia cambiará a ausente cuando la aplicación de Teams esté en segundo plano.

Los usuarios reciben todos los mensajes de chat que se les envían en los equipos, independientemente de su estado de presencia. Si un usuario está desconectado cuando alguien le envía un mensaje, el mensaje de chat aparece en Teams la próxima vez que el usuario se conecta. Si el estado de un usuario se establece en no molestar, el usuario seguirá recibiendo mensajes de chat, pero no se mostrarán las notificaciones de banner.

Los usuarios reciben llamadas en todos los Estados de presencia excepto en no molestar, en el que las llamadas entrantes se dirigen al buzón de voz. Si el destinatario bloqueó la llamada, la llamada no será entregada y la persona que llama ve la presencia del destinatario como desconectada.

Los usuarios pueden agregar a personas a su lista de acceso prioritario yendo a **Configuración** > **Privacidad** en Teams. Los usuarios con prioridad pueden ponerse en contacto con el usuario aunque el estado del usuario esté establecido en no molestar.

### <a name="dual-presence"></a>Presencia dual

  La forma de presencia funciona para la mayoría de los usuarios está motivada por los eventos del calendario o los eventos del dispositivo, como una llamada. El usuario puede anular este estado en la interfaz de usuario mediante la configuración manual de Estados, que tienen una fecha de expiración.

## <a name="user-configured-states-expiration"></a>Expiración de Estados configurados por el usuario

Cuando un usuario selecciona un estado de presencia específico, tiene prioridad sobre cualquier actualización de actividad de la aplicación. Por ejemplo, si un usuario se establece como no molestar, su presencia permanecerá como no molestar aunque asista a una reunión o responda a una llamada.

Los Estados configurados por el usuario tienen una configuración de expiración predeterminada en Teams, para evitar que los usuarios muestren un estado que puede no ser relevante después de un período de tiempo.

|Estado configurado por el usuario|Caducidad predeterminada|
|:--- |:---|
| Ocupado|1 día|
| No molestar|1 día|
| Ven|7 días|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Configuración de administración en equipos en comparación con Skype Empresarial

La siguiente configuración de administración Skype Empresarial es diferente en Teams:

- En Teams, el uso compartido de la presencia siempre está habilitado para los usuarios de la organización. La configuración privacidad (donde se define quién puede ver la presencia) no está disponible en Teams.
- Compartir la presencia con todo el mundo (incluidos los servicios Federados) siempre está habilitado para los usuarios de Teams. Su lista de contactos (si tenía una en Skype Empresarial) está visible en **Chat > Contactos** o en **Llamadas > Contactos** .
- Las funciones de No molestar al cliente y Contacto siempre están habilitadas para los usuarios de Teams.
- La integración del calendario (incluye información de fuera de la oficina y otra información de calendario) siempre está habilitada para los usuarios cuando Teams se integra con Outlook.
- El indicador *Último visto* o *Ausente desde* siempre está habilitado para los usuarios en Teams si la organización también usa Skype Empresarial.

> [!NOTE]
> Actualmente no se admite la capacidad de un administrador de Teams para personalizar estos ajustes.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Configuración de administración de equipos comparada con Microsoft Outlook

La presencia de Teams en Outlook es compatible con la aplicación de escritorio Outlook 2013 y posteriores.

Si la Directiva modo de actualización de la cuenta de usuario se establece en TeamsOnly, Outlook se comunica con Teams para obtener información de presencia. Si la cuenta de usuario no está configurada en TeamsOnly, Outlook se comunica con Skype empresarial.

## <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

Vea [coexistencia con Skype empresarial](coexistence-chat-calls-presence.md) para obtener información sobre cómo funciona la presencia de Teams cuando su organización también usa Skype empresarial.

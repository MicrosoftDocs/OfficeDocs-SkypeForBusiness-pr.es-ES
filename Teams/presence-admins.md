---
title: Presencia del usuario en Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Información para los Administradores sobre la Presencia en Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863201"
---
# <a name="user-presence-in-teams"></a>Presencia del usuario en Teams

La presencia es parte del perfil de un usuario en Microsoft Teams (y en todo Office 365) que indica a los demás usuarios la disponibilidad y el estado actual del usuario. De forma predeterminada, cualquier persona de su organización que utilice Teams puede ver (casi en tiempo real) si otros usuarios están disponibles en línea.

> [!IMPORTANT]
> Si desinstala el cliente de Skype Empresarial después de mover un usuario al modo **Teams solo**, la presencia dejará de funcionar en Outlook y en otras aplicaciones de Office. La presencia funciona bien en Teams. Solución: Para ver la presencia en Outlook (y otras aplicaciones de Office), Skype Empresarial debe estar instalado, aunque esté ejecutando Teams en el modo **solo Teams**. Microsoft es consciente de este problema y está trabajando en una solución.

La presencia de Teams en Outlook es compatible con la aplicación de escritorio Outlook 2013 y posteriores.

## <a name="presence-states-in-teams"></a>Estados de presencia en Teams

Los estados de presencia del usuario disponibles en Teams son:

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
 
Los usuarios pueden ajustar manualmente su estado de presencia actual a algunas opciones, y su estado se refleja a todos los demás usuarios. También se actualizan automáticamente más detalles de la presencia del usuario. Los cambios se basan en la actividad del usuario (Disponible, Ausente), los estados del calendario de Outlook (En una reunión), o los estados de las aplicaciones de Teams (En una llamada, Presentando), a los estados que están sangrados en la lista. Hay un tiempo límite de inactividad de 15 minutos, después del cual el estado de presencia actual se reajusta a Ausente.

Los usuarios reciben todos los mensajes de chat que se les envían en los equipos, independientemente de su estado de presencia. Si un usuario está desconectado cuando alguien le envía un mensaje, el mensaje de chat aparece en Teams la próxima vez que el usuario se conecta. Si un usuario se encuentra en un estado de "No molestar", el usuario seguirá recibiendo mensajes de chat pero no se mostrará una notificación emergente.

Los usuarios reciben llamadas en todos los estados de presencia excepto en los estados de "No molestar", en los que las llamadas entrantes son entregadas a su buzón de voz. Si el destinatario bloqueó la llamada, la llamada no será entregada y la persona que llama ve la presencia del destinatario como desconectada.

Los usuarios pueden agregar a personas a su lista de acceso prioritario yendo a **Configuración** > **Privacidad** en Teams. Las personas que tienen acceso prioritario pueden ponerse en contacto con el usuario incluso cuando éste se encuentra en un estado de "No molestar".

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

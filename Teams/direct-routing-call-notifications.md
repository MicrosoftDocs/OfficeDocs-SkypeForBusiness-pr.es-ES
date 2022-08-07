---
title: Administrar notificaciones de llamadas para enrutamiento directo
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notificación de llamada de enrutamiento directo
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4aa8e6a6f75141f7858e2342b65fb59d09326c33
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268435"
---
# <a name="manage-call-notifications"></a>Administrar notificaciones perdidas

En este artículo se describe cómo administrar las notificaciones de llamadas para los usuarios de Enrutamiento directo. Puede configurar los puntos de conexión de llamada a Teams y a una central de seguridad privada (PBX) o un controlador de borde de sesión (SBC) de terceros. Esta configuración es útil, por ejemplo, si desea enviar una llamada a los teléfonos móviles y de escritorio de un usuario al mismo tiempo.   

En el siguiente diagrama, el usuario Irena tiene dos puntos de conexión:

- Un punto de conexión de Teams
- Un teléfono SIP conectado a un SBC de terceros

Cuando llega una llamada, el SBC bifurca la llamada entre Direct Routing y el SBC de terceros.


![Diagrama que muestra puntos de conexión de Teams bifurcados.](media/direct-routing-call-notification-1.png)

Si la llamada se acepta en La bifurcación 2 (por el SBC de terceros), Teams generará una notificación de "Llamada perdida".  

Puede evitar la notificación de "Llamada perdida" configurando el SBC para enviar una Cancelación en bifurcación 1 de la siguiente manera:

RAZÓN: SIP; cause=200;text"Llamada completada en otro lugar" 

La llamada no se registrará en los registros de detalles de llamada de Teams Phone System como una llamada correcta. La llamada se registrará como un "intento" con el código SIP final "487", el subcódigo final de Microsoft "540200" y la frase de código SIP final "Llamada completada en otro lugar".  (Para ver los registros de detalles de la llamada, vaya al Centro de Administración de Teams >**Informes de** uso de **análisis e informes** ->  y seleccione **Uso de RTC**).


El diagrama siguiente ilustra la escalera del SIP para la bifurcación 1, explica el flujo de la llamada, y la RAZÓN esperada en el mensaje de cancelación. 

![El diagrama muestra puntos de conexión de Teams bifurcados.](media/direct-routing-call-notification-2.png)

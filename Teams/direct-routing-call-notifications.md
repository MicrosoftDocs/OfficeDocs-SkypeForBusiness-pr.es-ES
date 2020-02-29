---
title: Enrutamiento directo del Sistema telefónico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notificación de llamada de enrutamiento directo
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341805"
---
# <a name="manage-call-notifications"></a>Administrar notificaciones perdidas

En este artículo se describe cómo administrar las notificaciones de llamadas para los usuarios. Puede configurar puntos de conexión de llamadas tanto a los dos equipos como a un controlador de borde de sesión (PBX) de terceros o a un controlador de borde de sesión (SBC).  Esto es útil, por ejemplo, si deseas enviar una llamada a los teléfonos móviles y de escritorio de un usuario al mismo tiempo.   

En el siguiente diagrama, la Irena de usuario tiene dos puntos de conexión:

- Un punto de conexión de Teams
- Un teléfono SIP conectado a un SBC de terceros

Cuando llega una llamada, el SBC bifurca la llamada entre el enrutamiento directo del sistema telefónico y el SBC de terceros.


![Diagrama que muestra los puntos de conexión de los equipos bifurcados](media/direct-routing-call-notification-1.png)

Si la llamada es aceptada en la horquilla 2 (mediante el SBC de terceros), Teams generará una notificación de "llamada perdida".  

Puede evitar la notificación "llamada perdida" configurando SBC para que envíe una cancelación en la horquilla 1 de la siguiente manera:

MOTIVO: SIP; causa = 200; texto "llamada completada en otro lugar" 

Tenga en cuenta que la llamada no se registrará en los registros de detalles de llamadas de Microsoft Phone System como una llamada correcta. La llamada se registrará como un "intento" con el código SIP final "487", el subcódigo final de Microsoft "540200" y la frase de código SIP final "llamada completada en otro lugar".  (Para ver los registros de detalles de llamadas, vaya al portal de administración de Teams, análisis e informes, informes de uso y seleccione el uso de RTC).


El diagrama siguiente muestra la escalera de SIP para la horquilla 1, explica el flujo de llamadas y el motivo esperado en el mensaje de cancelación. 

![Diagrama que muestra los puntos de conexión de los equipos bifurcados](media/direct-routing-call-notification-2.png)

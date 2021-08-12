---
title: 'Teams: Administrar notificaciones de llamadas'
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
ms.openlocfilehash: b251040f9433d9ac51b388d12fa530b7c982e0773580d6ac69d41825fbba1ae6
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848325"
---
# <a name="manage-call-notifications"></a>Administrar notificaciones perdidas

En este artículo se describe cómo administrar las notificaciones de llamadas para los usuarios. Puede configurar puntos de conexión de llamadas tanto en Teams como en una sucursal privada de terceros Exchange (PBX) o controlador de borde de sesión (SBC).  Esta configuración es útil, por ejemplo, si desea enviar una llamada a los teléfonos móviles y de escritorio de un usuario al mismo tiempo.   

En el diagrama siguiente, el usuario Irena tiene dos puntos de conexión:

- Un punto Teams de conexión
- Un teléfono SIP conectado a un SBC de terceros

Cuando llega una llamada, el SBC bifurca la llamada entre Sistema telefónico enrutamiento directo y el SBC de terceros.


![Diagrama que muestra puntos de conexión Teams bifurcados](media/direct-routing-call-notification-1.png)

Si la llamada se acepta en Bifurcación 2 (por el SBC de terceros), Teams generará una notificación de "Llamada perdida".  

Puede evitar la notificación "Llamada perdida" configurando el SBC para enviar una Cancelación en bifurcación 1 de la siguiente manera:

MOTIVO: SIP; cause=200;text"Llamada completada en otro lugar" 

La llamada no se registrará en los registros de detalles de llamada de Teléfono Microsoft Sistema como una llamada correcta. La llamada se registrará como un "Intento" con el código SIP final "487", el subcódigo final de Microsoft "540200" y la frase de código SIP final "Llamada completada en otro lugar".  (Para ver los registros de detalles de llamadas, vaya al portal de administración de Teams, Análisis e informes, Informes de uso y seleccione Uso de RTC).


En el diagrama siguiente se muestra la escala SIP de Bifurcación 1, se explica el flujo de llamadas y la RAZÓN esperada en el mensaje Cancelar. 

![Diagrama muestra puntos de conexión Teams bifurcados](media/direct-routing-call-notification-2.png)

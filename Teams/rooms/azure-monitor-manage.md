---
title: Administrar Salas de Microsoft Teams dispositivos con Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: En este artículo se describe cómo administrar Salas de Microsoft Teams dispositivos de forma integrada con Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41375c313940099b6ed6e102e2452290e0817bec
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874770"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Administrar Salas de Microsoft Teams dispositivos con Azure Monitor

En este artículo se describe cómo administrar Salas de Microsoft Teams dispositivos de forma integrada con Azure Monitor.

Puede configurar Azure Monitor para proporcionar telemetría básica para ayudarle a administrar Microsoft Teams de salas de reuniones. Vea [Planear Salas de Microsoft Teams administración con Azure Monitor](azure-monitor-plan.md) e Implementar Salas de Microsoft Teams con Azure [Monitor](azure-monitor-deploy.md) para obtener más información. A medida que la solución de administración madura, puede usar capacidades de administración y datos adicionales para crear una vista más detallada del rendimiento del dispositivo.

## <a name="understand-the-log-entries"></a>Conocer las entradas del registro

Las siguientes descripciones de eventos se insertan en el campo de descripción del registro de eventos cada cinco minutos, cuando la aplicación Salas de Microsoft Teams registra la información correspondiente en el registro de eventos Windows eventos. El Microsoft Monitoring Agent pasa estos registros a Log Analytics en Azure Monitor, que los analiza en el panel que creó en Implementar Salas de Microsoft Teams administración con [Azure Monitor.](azure-monitor-deploy.md) Con el panel, puede ver entradas de registro individuales para determinar los cursos de acción si es necesario.

Los IDs de evento 2000 y 3000 indican que el dispositivo en cuestión funciona según lo esperado. Los IDs de evento 2001 y 3001 indican que se ha encontrado un problema. El id. de evento 4000 puede requerir una acción si se ve con más frecuencia de lo esperado, en comparación con una línea base que estableció o con otros dispositivos implementados en su organización.

Si conoce estas descripciones de eventos, le servirán como alertas para saber rápidamente si se están generando problemas y como punto de partida para proceder con otras soluciones de problemas.

| Nivel &nbsp; de id. de &nbsp; evento|Comportamiento del &nbsp; evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Descripción del &nbsp; evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Información | Se trata de un evento de latidos del corazón en buen estado. Cada 5 minutos, Salas de Microsoft Teams comprueba si ha iniciado sesión en Microsoft Teams o Skype Empresarial y tiene conectividad de red Exchange conexión. <br> Si todos los 3 factores son verdaderos, escribe El id. de evento 2000 en el registro de eventos cada 5 minutos hasta que el dispositivo está desconectado o una o más de las condiciones ya no se cumplen. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> En este ejemplo, se cumplieron todas las condiciones de los latidos del corazón y Salas de Microsoft Teams dispositivo se marcó como correcto. Si, por el contrario, se hubiese producido algún error, la aplicación registraría el Id. de evento 2001. |
| 2001  <br> Error | Se trata de un evento de error de aplicación. Cada 5 minutos, Salas de Microsoft Teams comprueba si ha iniciado sesión en Microsoft Teams o Skype Empresarial con la red y Exchange conectividad. Si uno o varios factores no son verdaderos, escribe EventID 2001 en el registro de eventos cada 5 minutos hasta que el dispositivo esté desconectado o se vuelvan a cumplir todas las condiciones.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. ", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  En este ejemplo, Salas de Microsoft Teams que la conexión de red estaba en buen estado y que la aplicación estaba conectada a Exchange, pero la parte en negrita indica que la aplicación no está conectada. Puede tratarse de un problema en la configuración del dispositivo o el host.  <br> <br> El estado red se muestra como en buen estado o en mal estado. Si el estado es incorrecto, es posible que tenga un problema de red o que el dispositivo se haya desconectado (pero es probable que también tenga errores Exchange y Microsoft Teams o Skype Empresarial).  <br><br> El estado Exchange muestra como Conectado o como uno de los siguientes: Desconectado, Conexión, Detección automáticaError (el error más visto), GeneralError o ServerVersionNotSupported. Si el estado es Connecting, espere hasta que se envíe el siguiente mensaje de estado, ya que otros errores envían el problema a un administrador con experiencia en solucionar los problemas de Exchange.  <br><br>  El _estado de inicio de_ sesión (que indica que la aplicación ha iniciado sesión) se muestra como _En_ buen estado o En _mal estado._ Si aparece en mal estado, envíe un técnico para que siga investigando el problema. |
| 3000  <br> Información | Este evento comprueba que se ha ejecutado una comprobación de hardware y se ha encontrado que está en buen estado. Cada 5 Salas de Microsoft Teams comprueba que los componentes de hardware configurados como la pantalla frontal de la sala, el micrófono, el altavoz y la cámara están conectados y funcionando. Si todos los componentes están en buen estado, escribe EventID 3000 en el registro de eventos. Este evento se escribe cada 5 minutos a menos que haya un problema con un dispositivo conectado.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> En este ejemplo, todas las comprobaciones del hardware se superaron correctamente. Si hubiera errores, la aplicación registraría el id. de evento 3001 en su lugar. |
| 3001  <br> Evento de error  | Se trata de un evento de error de hardware. La Salas de Microsoft Teams aplicación tiene un proceso que comprueba el estado de los componentes de hardware conectados (delante de la sala, micrófono, altavoz, cámara) cada 5 minutos. Si uno o varios de los componentes no están en buen estado, escribe EventID 3001 en el registro de eventos. Este evento se escribe cada 5 minutos hasta que se solucione el problema con el dispositivo.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>   Los periféricos de hardware se muestran como Healthy (en buen estado) o Unhealthy (en mal estado).  <br> En este ejemplo, hay dos pantallas _frontales_ de sala configuradas y actualmente ninguna de ellas está disponible. El _estado del micrófono de conferencia_ no está en _buen_ estado, lo que podría tener varias causas posibles. Dado que al menos uno de los recursos no ha superado la comprobación, ResourceState (estado de recursos) se muestra como Unhealthy (en mal estado). Envíe un técnico para que siga investigando el problema. |
| 4000  <br> Información  <br> | Es un evento de reinicio de aplicación. Cada vez que se reinicia la aplicación, este evento aparece en el registro de eventos de Windows.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> La aplicación puede reiniciarse por varios motivos. Compare la frecuencia de reinicio de los dispositivos en el mismo edificio y en diferentes edificios. Tenga en cuenta problemas conocidos como fluctuaciones de energía y errores, ya que esto puede proporcionar pistas de problemas de infraestructura.|

## <a name="related-topics"></a>Temas relacionados
 

[Planear Salas de Microsoft Teams administración con Azure Monitor](azure-monitor-plan.md)

[Implementar Salas de Microsoft Teams de administración con Azure Monitor](azure-monitor-deploy.md)

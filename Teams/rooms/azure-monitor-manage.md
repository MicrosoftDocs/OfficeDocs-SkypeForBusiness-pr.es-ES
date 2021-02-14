---
title: Administrar dispositivos de Salas de Microsoft Teams con Monitor de Azure
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
description: En este artículo se describe cómo administrar los dispositivos de Salas de Microsoft Teams de forma integrada con Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16105e77c8e66afa00f089d1337984b7e7d9a502
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662055"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Administrar dispositivos de Salas de Microsoft Teams con Monitor de Azure

En este artículo se describe cómo administrar los dispositivos de Salas de Microsoft Teams de forma integrada con Azure Monitor.

Puedes configurar Azure Monitor para proporcionar telemetría básica para ayudarte a administrar los dispositivos de salas de reuniones de Skype. Consulte [Planear la administración de salas de Microsoft Teams con Monitor](azure-monitor-plan.md) de Azure e implementar la administración de salas de [Microsoft Teams con Azure Monitor](azure-monitor-deploy.md) para obtener más información. A medida que madure su solución de administración, puede usar capacidades de administración y datos adicionales para crear una vista más detallada del rendimiento del dispositivo.

## <a name="understand-the-log-entries"></a>Conocer las entradas del registro

Las siguientes descripciones de eventos se insertan en el campo de descripción del registro de eventos cada cinco minutos, cuando la aplicación Microsoft Teams Rooms registra la información correspondiente en el registro de eventos de Windows. El Agente de supervisión de Microsoft pasa estos registros a Log Analytics en Azure Monitor, que los analiza en el panel que creó en Implementar la administración de salones de [Microsoft Teams con Azure Monitor.](azure-monitor-deploy.md) Con el panel, puede buscar entradas de registro individuales para determinar cursos de acción si es necesario.

Los event IDs 2000 y 3000 indican que el dispositivo en cuestión funciona según lo esperado. Los event IDs 2001 y 3001 indican que se ha encontrado un problema. El id. de evento 4000 puede requerir una acción si se ve con más frecuencia de lo esperado, en comparación con una línea base establecida o con otros dispositivos implementados en su organización.

Si conoce estas descripciones de eventos, le servirán como alertas para saber rápidamente si se están generando problemas y como punto de partida para proceder con otras soluciones de problemas.

| Nivel &nbsp; de id. de &nbsp; evento|Comportamiento de &nbsp; los eventos&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Descripción del &nbsp; evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Información | Se trata de un evento de los pulsaciones del corazón con estado correcto. Cada 5 minutos, Salas de Microsoft Teams comprueba que ha iniciado sesión en Microsoft Teams o Skype Empresarial y tiene conectividad de red y Exchange. <br> Si los tres factores son verdaderos, escribe el id. de evento 2000 en el registro de eventos cada 5 minutos hasta que el dispositivo esté sin conexión o ya no se cumple una o varias de las condiciones. | {"Description}Heartbeat está en buen estado", "ResourceState}Healthy", "OperationName}Heartbeat", "OperationResult "OS}Windows 10", "OSVersion}10.0.14393.693", "Alias alias <span></span> @contoso.com", "DisplayName}Nombre para mostrar", "AppVersion}1.0.38.0", "IPv4Address <br><br> En este ejemplo, se cumplen todas las condiciones del corazón y el dispositivo de Microsoft Teams Rooms se marcó como correcto. Si, por el contrario, se hubiese producido algún error, la aplicación registraría el Id. de evento 2001. |
| 2001  <br> Error | Este es un evento de error de aplicación. Cada 5 minutos, Salas de Microsoft Teams comprueba que ha iniciado sesión en Microsoft Teams o Skype Empresarial con conectividad de red y Exchange. Si uno o varios factores no son verdaderos, escribe EventID 2001 en el registro de eventos cada 5 minutos hasta que el dispositivo se desconecta o se cumplen todas las condiciones de nuevo.  | {"Description":"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** ", "ResourceState "OS}Windows 10", "OSVersion}10.0.14393.693", "Alias}", "DisplayName}Nombre para mostrar", "AppVersion{1.0.38.0", "IPv4Address <br><br>  En este ejemplo, los salas de Microsoft Teams determinaron que la conexión de red estaba en buen estado y que la aplicación estaba conectada a Exchange, pero la parte en negrita indica que la aplicación no está conectada. Puede tratarse de un problema en la configuración del dispositivo o el host.  <br> <br> El estado de red se muestra como Correcto o Incorrecto. Si el estado es incorrecto, es posible que tenga un problema de red o que el dispositivo se haya desconectado (pero probablemente también tenga errores de Exchange y Microsoft Teams o Skype Empresarial).  <br><br> El estado de Exchange se muestra como Conectado o como uno de los siguientes: Desconectado, Conectando, AutodiscoveryError (el error más visto), GeneralError o ServerVersionNotSupported. Si el estado es Connecting, espere hasta que se envíe el siguiente mensaje de estado, ya que otros errores envían el problema a un administrador con experiencia en solucionar los problemas de Exchange.  <br><br>  El estado de inicio de sesión (que indica que la aplicación ha iniciado sesión) se muestra con buen estado o incorrecto. Si aparece en mal estado, envíe un técnico para que siga investigando el problema. |
| 3000  <br> Información | Este evento comprueba que se ha ejecutado una comprobación de hardware y que se ha encontrado que está en buen estado. Cada 5 minutos, Salas de Microsoft Teams comprueba si los componentes de hardware configurados como la pantalla frontal de la sala, el micrófono, el altavoz y la cámara están conectados y funcionales. Si todos los componentes están en buen estado, escribe EventID 3000 en el registro de eventos. Este evento se escribe cada 5 minutos a menos que haya un problema con un dispositivo conectado.  <br> | {"Description}HardwareCheckResult está en buen estado", "ResourceState}Healthy", "OperationName}HardwareCheckCheck", "OperationResult "OS}Windows 10", "OSVersion}10.0.14393.693", "Alias alias <span></span> @contoso.com", "DisplayName}Nombre para mostrar", "AppVersion  <br><br> En este ejemplo, todas las comprobaciones del hardware se superaron correctamente. Si hubiera errores, la aplicación registraría el id. de evento 3001 en su lugar. |
| 3001  <br> Evento de error  | Este es un evento de error de hardware. La aplicación Salas de Microsoft Teams tiene un proceso que comprueba el estado de los componentes de hardware conectados (frente a la sala, micrófono, altavoz y cámara) cada 5 minutos. Si uno o varios de los componentes tienen un estado incorrecto, escribe EventID 3001 en el registro de eventos. Este evento se escribe cada 5 minutos hasta que se solucione el problema con el dispositivo.   | {"Description} **Estado de visualización del anverso: incorrecto.** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. Estado de la cámara: Correcto.", "ResourceState "Alias}alias <span></span> @contoso.com", "DisplayName}Yosemite conference room", "AppVersion <br><br>  Los periféricos de hardware se muestran como Healthy (en buen estado) o Unhealthy (en mal estado). <br> En este ejemplo hay configuradas dos pantallas frontales de sala y, en este momento, ninguna de ellas está disponible. El estado del micrófono de conferencia no está en buen estado, lo que podría tener varias causas posibles. Dado que al menos uno de los recursos no ha superado la comprobación, ResourceState (estado de recursos) se muestra como Unhealthy (en mal estado). Envíe un técnico para que siga investigando el problema. |
| 4000  <br> Información  <br> | Es un evento de reinicio de aplicación. Cada vez que se reinicia la aplicación, este evento aparece en el registro de eventos de Windows.  <br> | {"Descripción}Se reinicia la aplicación". "ResourceState}Healthy", "OperationName "OS}Windows 10", "OSVersion}10.0.14393.693", "Alias alias <span></span> @domain.com", "DisplayName <br><br> La aplicación puede reiniciarse por varias razones. Compare la frecuencia de reinicio de los dispositivos del mismo edificio y de diferentes edificios. Tenga en cuenta problemas conocidos como fluctuaciones de potencia y errores, ya que esto puede proporcionar pistas en los problemas de infraestructura.|

## <a name="related-topics"></a>Temas relacionados
 

[Planear la administración de salas de Microsoft Teams con Azure Monitor](azure-monitor-plan.md)

[Implementar la administración de salas de Microsoft Teams con Azure Monitor](azure-monitor-deploy.md)

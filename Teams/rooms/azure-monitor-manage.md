---
title: Supervisar dispositivos Salas de Microsoft Teams con Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: En este artículo se describe cómo supervisar Salas de Microsoft Teams dispositivos de forma integrada con Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d82193bfae50bc2aafeb9f00425ab6eb69fec394
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761272"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Supervisar dispositivos Salas de Microsoft Teams con Azure Monitor

En este artículo se describe cómo supervisar Salas de Microsoft Teams de forma integrada con Azure Monitor.

Puede configurar Azure Monitor para proporcionar telemetría básica para ayudarle a supervisar Microsoft Teams dispositivos de salas de reuniones. Para obtener más información, consulta [Planear la administración de Salas de Microsoft Teams con Azure Monitor](azure-monitor-plan.md) e [Implementar la administración de Salas de Microsoft Teams con Azure Monitor](azure-monitor-deploy.md). A medida que la solución de supervisión madura, puede usar otras capacidades de supervisión y datos para crear una vista más detallada del rendimiento del dispositivo.

## <a name="understand-the-log-entries"></a>Conocer las entradas del registro

Las siguientes descripciones de eventos se insertan en el campo de descripción del registro de eventos cada cinco minutos, cuando la aplicación de Salas de Microsoft Teams registra la información correspondiente en el registro de eventos de Windows. La Microsoft Monitoring Agent pasa estos registros a Log Analytics en Azure Monitor, que los analiza en el panel que creó en [Implementación Salas de Microsoft Teams supervisión con Azure Monitor](azure-monitor-deploy.md). Con el panel, puede ver las entradas de registro individuales para determinar los cursos de acción si es necesario.

Los identificadores de evento 2000 y 3000 indican que Salas de Teams funciona según lo esperado. Los identificadores de evento 2001 y 3001 indican que se ha encontrado un problema. El id. de evento 4000 puede requerir una acción si se ve más a menudo de lo esperado, en comparación con una línea base establecida o con otros dispositivos implementados en su organización.

Si conoce estas descripciones de eventos, le servirán como alertas para saber rápidamente si se están generando problemas y como punto de partida para proceder con otras soluciones de problemas.

| Nivel de id. de&nbsp;evento&nbsp;|Comportamiento del evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Descripción del evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Información | Este es un evento de latido del corazón sano. Cada 5 minutos, Salas de Microsoft Teams comprueba que ha iniciado sesión en Microsoft Teams o Skype Empresarial y tiene conectividad de red y Exchange. <br> Si los tres factores son verdaderos, escribe Event ID 2000 en el registro de eventos cada 5 minutos hasta que el dispositivo está desconectado o una o más de las condiciones ya no se cumplen. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> En este ejemplo, se cumplen todas las condiciones del latido del corazón y el dispositivo Salas de Microsoft Teams se marca como correcto. Si, por el contrario, se hubiese producido algún error, la aplicación registraría el Id. de evento 2001. |
| 2001  <br> Error | Este es un evento de error de aplicación. Cada 5 minutos, Salas de Microsoft Teams comprueba que ha iniciado sesión en Microsoft Teams o Skype Empresarial con conectividad de red y Exchange. Si uno o más factores no son verdaderos, escribe EventID 2001 en el registro de eventos cada 5 minutos hasta que el dispositivo está desconectado o se cumplen todas las condiciones una vez más.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. Teams Signin status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  En este ejemplo, Salas de Microsoft Teams determinado que la conexión de red estaba en buen estado y la aplicación se conectó a Exchange, pero la parte en negrita indica que la aplicación no está conectada. Puede tratarse de un problema en la configuración del dispositivo o el host.  <br> <br> El estado de red se muestra como Correcto o No saludable. Si el estado es incorrecto, es posible que tengas un problema de red o que el dispositivo se haya desconectado (pero es probable que también tengas errores de Exchange y Microsoft Teams o Skype Empresarial).  <br><br> El estado de Exchange se muestra como Conectado o uno de los siguientes: Desconectado, Conectando, Detección automáticaError (el error más visto), GeneralError o ServerVersionNotSupported. Si el estado es Connecting, espere hasta que se envíe el siguiente mensaje de estado, ya que otros errores envían el problema a un administrador con experiencia en solucionar los problemas de Exchange.  <br><br>  El _estado_/ de Inicio de sesión _Teams Estado de inicio de sesión_ (que indica que la aplicación ha iniciado sesión) se muestra como _Correcto_ o _En mal estado_. Si aparece en mal estado, envíe un técnico para que siga investigando el problema. |
| 3000  <br> Información | Este evento comprueba que se ha ejecutado una comprobación de hardware y se ha comprobado que está en buen estado. Cada 5 minutos Salas de Microsoft Teams comprueba que los componentes de hardware configurados, como la pantalla frontal de la sala, el micrófono, el altavoz y la cámara, estén conectados y funcionen. Si todos los componentes están en buen estado, escribe EventID 3000 en el registro de eventos. Este evento se escribe cada 5 minutos, a menos que haya un problema con un dispositivo conectado.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> En este ejemplo, todas las comprobaciones del hardware se superaron correctamente. Si hubiera errores, la aplicación grabaría en su lugar el id. de evento 3001. |
| 3001  <br> Evento de error  | Se trata de un evento de error de hardware. La aplicación Salas de Microsoft Teams tiene un proceso que comprueba el estado de los componentes de hardware conectados (delante de la sala, micrófono, altavoz y cámara) cada 5 minutos. Si uno o varios de los componentes no tienen el estado correcto, escribe EventID 3001 en el registro de eventos. Este evento se escribe cada 5 minutos hasta que se corrige el problema con el dispositivo.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>   Los periféricos de hardware se muestran como Healthy (en buen estado) o Unhealthy (en mal estado).  <br> En este ejemplo, hay dos pantallas _frontales de sala_ configuradas y actualmente ninguna de ellas está disponible. El _estado micrófono_ de conferencia _no es correcto_, lo que podría tener varias causas posibles. Dado que al menos uno de los recursos no ha superado la comprobación, ResourceState (estado de recursos) se muestra como Unhealthy (en mal estado). Envíe un técnico para que siga investigando el problema. |
| 4000  <br> Información  <br> | Es un evento de reinicio de aplicación. Cada vez que se reinicia la aplicación, este evento aparece en el registro de eventos de Windows.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> La aplicación puede reiniciarse por varias razones. Compara la frecuencia de reinicio de dispositivos del mismo edificio y de edificios diferentes. Tenga en cuenta problemas conocidos como fluctuaciones de energía y errores, ya que esto puede proporcionar pistas de problemas de infraestructura.|

## <a name="related-topics"></a>Temas relacionados
 

[Planear la supervisión de Salas de Microsoft Teams con Azure Monitor](azure-monitor-plan.md)

[Implementar Salas de Microsoft Teams supervisión con Azure Monitor](azure-monitor-deploy.md)

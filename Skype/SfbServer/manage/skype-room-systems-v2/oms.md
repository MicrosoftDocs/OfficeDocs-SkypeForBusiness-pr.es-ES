---
title: Administración de los dispositivos de Sistemas de salas de Skype v2 con OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/19/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
description: 'En este artículo se comenta cómo se administran los dispositivos de Sistemas de salas de Skype v2 de una forma integrada y descentralizada mediante Microsoft Operations Management Suite. '
ms.openlocfilehash: 7c36203dd6f6a90ccdab801bc66ff31c4319a6e1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-systems-v2-devices-with-oms"></a>Administración de los dispositivos de Sistemas de salas de Skype v2 con OMS
 
En este artículo se comenta cómo se administran los dispositivos de Sistemas de salas de Skype v2 de una forma integrada y descentralizada mediante Microsoft Operations Management Suite.  
  
Puede configurar Microsoft operaciones Management Suite (OMS) para proporcionar la telemetría básico que le ayudarán a administrar dispositivos (consulte [administración de Plan de sistemas de salas de Skype v2 con OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) y [administración de implementar sistemas de salas de Skype v2 con OMS para salas de reuniones de Skype ](../../deploy/deploy-clients/with-oms.md)para obtener más detalles). A medida que madure la solución de administración, puede comprar más funcionalidades de administración y datos con los que se cree una vista más detallada del rendimiento de los dispositivos.
  
## <a name="understand-the-log-entries"></a>Conocer las entradas del registro
<a name="Telemetry"> </a>

Las siguientes descripciones de eventos se insertan en el campo de descripción de los registros de eventos cada cinco minutos, cuando la aplicación de Sistemas de salas de Skype (SRS, por sus siglas en inglés) registra la información correspondiente en el registro de eventos de Windows. El agente OMS pasa estos informes a OMS, que se analiza en el escritorio que creó en la [administración de implementar sistemas de salas de Skype v2 con OMS](../../deploy/deploy-clients/with-oms.md). En caso necesario, con el panel se pueden ver las entradas individuales del registro para determinar los cursos de acciones. 
  
Los Id. de evento 2000 y 3000 indican que el dispositivo en cuestión está funcionando como se espera. Los Id. de evento 2001 y 3001 indican que se ha producido un problema. Con el Id. de evento 4000, es posible que haya que hacer algo si aparece en más ocasiones de las normales en comparación con una base de referencia que se establezca o con otros dispositivos de su organización.
  
Si conoce estas descripciones de eventos, le servirán como alertas para saber rápidamente si se están generando problemas y como punto de partida para proceder con otras soluciones de problemas.
  
|**Id. de suceso <br/> nivel**|**Comportamiento del evento**|**Descripción del evento**|
|:-----|:-----|:-----|
|2000  <br/> Información  <br/> | Se trata de un evento de latido sano. Cada 5 minutos, SRS v2 comprueba que ha iniciado sesión en Skype para el negocio y que tiene conectividad de red y Exchange. Si se cumplen todos los 3 factores, escribirá 2000 de ID de evento en el registro de eventos cada 5 minutos hasta que el dispositivo está desconectado o uno o más de las condiciones no se cumple. <br/> | {"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass","OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias@contoso.com","DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IP v6 address"} <br/> En este ejemplo, se cumplen todas las condiciones de latidos y se establece que el dispositivo de SRS v2 está en buen estado. Si, por el contrario, se hubiese producido algún error, la aplicación registraría el Id. de evento 2001.  <br/> |
|2001  <br/> Error  <br/> |Se trata de un evento de error de la aplicación. Cada 5 minutos, SRS v2 comprueba que se ha iniciado sesión en Skype para empresas con conectividad de red y Exchange. Si no se cumplen uno o más factores, escribirá EventID 2001 en el registro de eventos cada 5 minutos hasta que el dispositivo está desconectado o todas las condiciones que puedan cumplirse una vez más.  <br/> |  {"Description":"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** ","ResourceState":"Unhealthy","OperationName":"Heartbeat","OperationResult":"Fail","OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"","DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10","IPv6Address":"ip v6 address"}<br/> En este ejemplo, SRSv2 ha determinado que la conexión de red estaba en buen estado y la aplicación estaba conectada a Exchange, pero la parte en negrita indica que la aplicación no está conectada a Skype Empresarial. Puede tratarse de un problema en la configuración del dispositivo o el host.  <br/> El estado de red se mostrará como Healthy (en buen estado) o Unhealthy (en mal estado). Si aparece en mal estado, es posible que haya un problema de red o que el dispositivo esté desconectado (sin embargo, en ese caso, también habría problemas en Exchange y Skype Empresarial).<br/> El cambio de estado se mostrará como conectado o uno de los siguientes: desconectado, conectando, AutodiscoveryError (el error más habituales), GeneralError o ServerVersionNotSupported. Si el estado es Connecting, espere hasta que se envíe el siguiente mensaje de estado, ya que otros errores envían el problema a un administrador con experiencia en solucionar los problemas de Exchange.  <br/> El estado Signin (que indica que la aplicación ha iniciado sesión en Skype Empresarial) se mostrará como Healthy (en buen estado) o Unhealthy (en mal estado). Si aparece en mal estado, envíe un técnico para que siga investigando el problema.<br/> |
|3000  <br/> Información  <br/> |Este evento comprueba que una comprobación de hardware se ejecuta y considerada sanas. Comprobaciones SRS v2 cada 5 minutos que configura los componentes de hardware como parte frontal de la cámara, micrófono, altavoz y presentación de sala están conectados y funcionando. Si todos los componentes están en buenas condiciones, EventID 3000 escribirá en el registro de sucesos. Este evento seguirá escribirse cada 5 minutos, a menos que haya un problema con un dispositivo conectado.  <br/> |{"Description":"HardwareCheckEngine is healthy.","ResourceState":"Healthy", "OperationName":"HardwareCheckEngine","OperationResult":"Pass","OS":"Windows 10","OSVersion":"10.0.14393.693","Alias":"alias@contoso.com","DisplayName":"Display Name","AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10","IPv6Address":"ip v6 address"}  <br/> En este ejemplo, todas las comprobaciones del hardware se superaron correctamente. Si, por el contrario, se hubiese producido algún error, la aplicación registraría el Id. de evento 3001.  <br/> |
|3001  <br/> Evento de error  <br/> |Se trata de un evento de error de hardware. La aplicación SRS tiene un proceso que se comprobará el estado de los componentes de hardware conectado (frontal de la sala, micrófono, altavoz, cámara) cada 5 minutos. Si uno o más de los componentes no funcionan correctamente, EventID 3001 escribirá en el registro de sucesos. Este evento se seguirá escribiendo cada 5 minutos hasta que se solucione el problema con el dispositivo.  <br/> |{"Description": " **frontal de sala Display status: insalubres.** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy. ","ResourceState":"Unhealthy","OperationName":"HardwareCheckEngine","OperationResult":"Fail","OS":"Windows 10","OSVersion":"10.0.14393.1198","Alias":"alias@contoso.com","DisplayName":"Yosemite conference room","AppVersion":"2.0.58.0","IPv4Address":"10.10.10.10","IPv6Address":"IPv6Address","IPv4Address2":"10.10.10.10"} <br/>  Los periféricos de hardware se muestran como Healthy (en buen estado) o Unhealthy (en mal estado). <br/> En este ejemplo hay configuradas dos pantallas frontales de sala y, en este momento, ninguna de ellas está disponible. El estado del micrófono de conferencia es malo, lo que podría deberse a varios motivos. Dado que al menos uno de los recursos no ha superado la comprobación, ResourceState (estado de recursos) se muestra como Unhealthy (en mal estado). Envíe un técnico para que siga investigando el problema.  <br/> |
|4000  <br/> Información  <br/> |Es un evento de reinicio de aplicación. Cada vez que se reinicia la aplicación, este evento aparece en el registro de eventos de Windows.  <br/> | {"Description":"App restarts.","ResourceState":"Healthy","OperationName":"Restart","OperationResult":"Pass","OS":"Windows 10","OSVersion":"10.0.14393.693","Alias":"alias@domain.com","DisplayName":"Display Name","AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10","IPv6Address":"ip v6 address"} <br/> La aplicación de Skype Empresarial se puede reinicar por diversos motivos. Compare la frecuencia de reinicio de los dispositivos que se encuentran en el mismo edificio y en distintos edificios, teniendo en cuenta algunos problemas conocidos, como los fallos y las fluctuaciones en la energía, ya que esto podría indicar que existen problemas en la infraestructura.  <br/> |
   
## <a name="see-also"></a>Vea también
<a name="Telemetry"> </a>

#### 

[Planear la administración de sistemas de salas de Skype v2 con OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Implementar la administración de sistemas de salas de Skype v2 con OMS](../../deploy/deploy-clients/with-oms.md)


---
title: Enrutamiento basado en ubicación para conferencias en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 10/13/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planear ubicación enrutamiento para conferencias en Skype para Telefonía IP empresarial de Business Server, incluyendo consultoría llame a transferencias.
ms.openlocfilehash: 4cfa76e10ed0107c1dc1fe4c1759a89536529ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server-2015"></a>Enrutamiento basado en ubicación para conferencias en Skype Empresarial Server 2015
 
Planear ubicación enrutamiento para conferencias en Skype para Telefonía IP empresarial de Business Server, incluyendo consultoría llame a transferencias.
  
Enrutamiento basado en ubicación permite restringir el enrutamiento de llamadas entre extremos de VoIP y extremos PSTN según la ubicación de las partes en la llamada. Enrutamiento para conferencias basadas en la ubicación le permite aplicar reglas de enrutamiento basadas en ubicación en reuniones (es decir, conferencias) para evitar que PSTN omisión de pago. La aplicación supervisa una conferencia activa y aplica restricciones de enrutamiento basado en la ubicación según la ubicación de los usuarios que participan. Además, el enrutamiento basado en la ubicación para la aplicación de conferencias permite la aplicación de restricciones de enrutamiento basado en la ubicación de las transferencias de consultoría que implican extremos PSTN.
  
La aplicación de conferencias basada en la ubicación de enrutamiento proporciona a Skype para conferencias de empresa omitir un mecanismo para la prevención de las llamadas PSTN. La aplicación supervisa conferencias activas e impone restricciones de enrutamiento basado en la ubicación según la ubicación de la Skype para los usuarios de negocios que participan. 
  
La aplicación de conferencias basada en la ubicación de enrutamiento determina si enrutamiento según ubicación está aplicando en un Skype para la reunión de negocios si se cumplen los siguientes criterios:
  
- Organizador de la reunión está habilitado para enrutamiento basado en la ubicación. Restricciones de enrutamiento basadas en ubicación se aplicará sólo a las conferencias que se organizan por usuarios habilitados para enrutamiento basado en la ubicación.
    
- Al menos uno de los participantes de la reunión es un extremo de RTC. Restricciones de enrutamiento basadas en ubicación son aplicables sólo para conferencias que incluyen extremos PSTN.
    
- El sitio de red donde se utiliza la puerta de enlace RTC para conectar la conferencia con la RTC se encuentra (al igual que los sitios de red) en la ubicación desde donde se conectan los organizadores y los participantes. 
    
El enrutamiento basado en la ubicación para la aplicación de conferencias impide la participación de Skype para usuarios empresariales y extremos PSTN desde sitios de red diferentes para la misma conferencia. Si el organizador de una reunión está habilitado para enrutamiento basado en la ubicación, la aplicación de conferencias impone las siguientes restricciones:
  
- Los extremos que pueden unirse a un Skype para la reunión de negocios dependen de los extremos que ya se unió a la conferencia, y esta restricción se ajusta como dejar extremos combinados y nuevos extremos de unirse a la conferencia. Si los organizadores y los participantes que se va a unir un Skype para reuniones de negocios desde el mismo sitio de red, entonces un extremo PSTN, otro participante en la misma ubicación de red, otro participante desde un sitio de red diferente o un participante desde un sitio de red desconocido le permite unirse a.
    
- Si organizadores y participantes se unen a la reunión desde diferentes sitios de red o sitios de red desconocidos, no se permite la entrada a la reunión de un extremo de RTC, si la llamada de RTC entra de un tronco SIP habilitado para el enrutamiento basado en ubicación.
    
- Si los organizadores y los participantes son unirse a la reunión desde el mismo sitio de red y hay participantes que se unan a la misma sesión de PSTN, no se permite un Skype para extremo del negocio desde un sitio de red diferente para unirse a la reunión.
    
Estas restricciones de enrutamiento basado en la ubicación de la conferencia se resumen en la tabla siguiente. 
  
| |
|**Usuarios en una conferencia en un momento dado**|**Usuarios puedos unirse a la conferencia**|**Usuarios no puedos unirse a la conferencia**|
|:-----|:-----|:-----|
|Skype para usuarios de cliente de VoIP del negocio desde un sitio de red  <br/> |Skype para el usuario de cliente de VoIP de negocio desde el mismo sitio de red  <br/> Skype para el usuario de cliente de VoIP del negocio desde un sitio de red diferente  <br/> Skype para el usuario de cliente de VoIP del negocio desde un sitio de red desconocido  <br/> Skype federado para el usuario del cliente de negocios VoIP  <br/> Usuario que se une desde un extremo de RTC  <br/> |Ninguno  <br/> |
|Skype para usuarios de cliente de VoIP del negocio desde un sitio de red desconocido  <br/> |Skype para el usuario de cliente de VoIP empresariales desde cualquier sitio  <br/> Skype para el usuario de cliente de VoIP del negocio desde un sitio desconocido  <br/> Skype federado para el usuario del cliente de negocios VoIP  <br/> |Usuario que se une a través de un extremo de RTC  <br/> |
|Skype para usuarios de cliente de VoIP del negocio de sitios de red diferente  <br/> |Skype para el usuario de cliente de VoIP empresariales desde cualquier sitio de la red  <br/> Skype para el usuario de cliente de VoIP del negocio desde un sitio de red desconocido  <br/> Skype federado para el usuario del cliente de negocios VoIP  <br/> |Usuario que se une a través de un extremo de RTC  <br/> |
|Skype para usuarios de cliente de VoIP de negocios desde un sitio de red y usuarios se unen a desde un extremo PSTN  <br/> |Skype para el usuario de cliente de VoIP de negocio desde el mismo sitio de red  <br/> |Skype para el usuario de cliente de VoIP del negocio desde un sitio de red diferente  <br/> Skype para el usuario de cliente de VoIP del negocio desde un sitio de red desconocido  <br/> Skype federado para el usuario del cliente de negocios VoIP  <br/> |
   
Las siguientes son características adicionales de la ruta basada en la ubicación de la aplicación de conferencia:
  
- Cuando un usuario no puede unirse a una conferencia impartida restricciones de enrutamiento basado en ubicación, se rechazará la llamada a la conferencia y el Skype para Business client le informe de que la llamada no fue completada o finalizada.
    
- Un PSTN extremo unirse a que una conferencia con aplicaciones de enrutamiento basado en ubicación no estará limitada a unirse a la conferencia independientemente de su estado, si el extremo se une a través de un tronco que no está habilitado para el enrutamiento basado en la ubicación.
    
- Un sistema PBX conectado a un servidor de mediación sobre un tronco SIP que no egreso llamadas a la RTC tendrán el mismo aplicaciones como Skype para usuarios de negocios se encuentran en el mismo sitio de red donde se define la troncal SIP. Por ejemplo, un extremo PSTN será capaz de unirse a una conferencia con un usuario de PBX y un Skype para usuarios de empresa si se encuentran en el mismo sitio de la red; de lo contrario, no se permitirá el extremo PSTN para unirse a la conferencia si el usuario PBX está en un sitio de red diferente que el Skype para usuarios de empresa.
    
> [!NOTE]
> Con la actualización acumulativa 4 de Skype Empresarial, debe observarse el comportamiento en la siguiente tabla: 
  
|**Usuario**|**Otra parte**|**Acción**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype Empresarial para móviles está en una llamada RTC. Skype Empresarial para móviles luego escala la llamada a un operador automático de conferencia (CAA).  <br/> |La llamada se bloquea, con un mensaje de error apropiado.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado o cliente de Skype Empresarial  <br/> |El cliente o el usuario federado está en una llamada de VoIP a un Skype para enrutamiento de Business Mobile Location-Based usuario y cualquiera de las partes se escala a un CAA.  <br/> |La llamada de escalación se bloquea, con un mensaje de error apropiado.  <br/> |
   
## <a name="consultative-call-transfers"></a>Transferencias de llamada de consulta

Además de aplicar el enrutamiento basado en la ubicación a Skype para reuniones de negocios, el enrutamiento basado en la ubicación para la aplicación de conferencia impone restricciones de enrutamiento basado en ubicación en transferencias de llamadas consultivo que egreso a extremos PSTN. Una transferencia de consultoría llamada es una llamada establecida entre dos partes donde una de las partes transfiere la llamada a un nuevo usuario. Por ejemplo, un extremo de RTC llama usuario (Skype para destinatario de negocio). El usuario A determina que el usuario PSTN se reenviará a usuario B (Skype para usuarios de empresa). Lugares de usuario A que la llamada con la RTC usuario en espera y llamadas B. usuario B se compromete a hablar con el usuario PSTN. El usuario A transfiere la llamada en espera al usuario B.
  
**Flujo de llamadas de llamada consultivo transferencia**

![Enrutamiento basado en ubicación para diagrama de conferencias](../../media/LocationBasedRoutingForConferencing.jpg)
  
Cuando un usuario habilitado para enrutamiento según ubicación inicia una transferencia de llamada consultiva de un extremo PSTN (como se muestra en la figura anterior), esto crea dos llamadas activas, una llamada entre el usuario PSTN y Skype para usuarios de la empresa A y la otra entre Skype para El enrutamiento basado en la ubicación para la aplicación de conferencia exige empresa A y Skype para usuarios de empresa B. el siguiente comportamiento:
  
- Si llama la troncal SIP enrutamiento PSTN está autorizado para volver a enrutar la llamada PSTN para el sitio de la red donde Skype para usuarios de la empresa B (es decir, el destino de transferencia) se encuentra, entonces se permitirá la transferencia de llamada; de lo contrario, se bloqueará la transferencia de llamada consultiva. Esta autorización se realiza basándose en la ubicación de la parte transferida en el mismo sitio de red que el tronco SIP que se está distribuyendo la llamada activa al extremo PSTN. 
    
- Si el tronco SIP enrutar la llamada entrante de RTC no está autorizado para dirigir las llamadas para el sitio de la red donde se encuentra la parte transferida (Skype para usuarios de la empresa B) o la parte transferida se encuentra en un sitio de red desconocido, entonces la llamada consultiva transferir a se bloqueará el extremo PSTN (es decir, destino de transferencia de llamada).
    
La tabla siguiente describe cómo ubicación enrutamiento restricciones se aplican mediante el enrutamiento basado en la ubicación para la aplicación de conferencia para transferencias de llamadas consultiva. A pesar de que los extremos de PBX no están directamente asociados con un sitio de red, el tronco SIP al cual está conectado la PBX se puede asignar a un sitio de red. Por lo tanto, el extremo de PBX se puede asociar indirectamente con el sitio de red.
  

|**Sitio de red de llamada transfiere parte**|**Sitio de la red de destino de la transferencia de llamada**|**Comportamiento**|
|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Skype para usuarios de empresa en el mismo sitio de la red (es decir, sitio 1)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Skype para usuarios de empresa en red diferentes sitios (es decir, 2)  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Skype para usuarios de empresa en un sitio de red desconocido  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Federados Skype para usuarios de empresa  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Extremo de PBX en el mismo sitio (es decir, el sitio 1)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Extremo de PBX en un sitio diferente (es decir, el sitio 2)  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en el mismo sitio (es decir, el sitio 1)  <br/> |Extremo de RTC  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en un sitio diferente (es decir, el sitio 2)  <br/> |Extremo de RTC  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Skype para usuarios de empresa en el mismo sitio de la red (es decir, sitio 1)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Skype para usuarios de empresa en red diferentes sitios (es decir, 2)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Skype para usuarios de empresa en un sitio de red desconocido  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Federados Skype para usuarios de empresa  <br/> |Se permitirá la transferencia de consulta  <br/> |
   
## <a name="requirements"></a>Requisitos

El enrutamiento basado en la ubicación para la aplicación de conferencia requiere que se implementa en Skype para Business Server o Lync Server 2013 acum actualización 2 en todos los grupos de aplicaciones para usuario y servidores Standard Edition de la topología. Si estas versiones de servidor no están instaladas en algunos servidores en la topología, restricciones de enrutamiento basado en la ubicación no pueden ser totalmente forzadas en reuniones y consultoría llame transferencias.
  
La siguiente tabla identifica la combinación de funciones de servidor y versiones que admiten el enrutamiento basado en la ubicación.
  

|**Versión de grupo de servidores front-end**|**Versión de servidor de mediación**|**Compatible**|
|:-----|:-----|:-----|
|Skype para Business Server o Lync Server 2013 actualización acumulativa 2  <br/> |Skype para Business Server o Lync Server 2013 actualización acumulativa 2  <br/> |Sí  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Actualización acumulativa 1 de Lync Server 2013  <br/> |No  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Lync Server 2010  <br/> |No  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |No  <br/> |
|Actualización acumulativa 1 de Lync Server 2013  <br/> |Cualquiera  <br/> |No  <br/> |
|Lync Server 2010  <br/> |Cualquiera  <br/> |No  <br/> |
|Office Communications Server 2007 R2  <br/> |Cualquiera  <br/> |No  <br/> |
   
## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuración de enrutamiento basado en ubicación para las conferencias

El enrutamiento basado en la ubicación para la aplicación de conferencia se basa en la configuración de enrutamiento basado en la ubicación. Las siguientes son las opciones de configuración principales: 
  
- La ubicación de los participantes que se unen a una reunión se determina a partir de su sitio de red. Un sitio de red y subredes de su red asociada deben definirse en Skype para Business Server con el fin de exigir el enrutamiento basado en la ubicación.
    
- Para aplicar el enrutamiento basado en la ubicación de las reuniones, Skype para los participantes del negocio debe habilitarse para enrutamiento basado en la ubicación.
    
- Para aplicar el enrutamiento basado en la ubicación de los extremos PSTN unirse a reuniones, la troncal SIP utilizado para conectar los extremos PSTN debe configurarse para enrutamiento basado en la ubicación.
    
## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitar el enrutamiento basado en ubicación para las conferencias

El enrutamiento basado en la ubicación para la aplicación de conferencia está deshabilitada de forma predeterminada. Antes de habilitar esta aplicación, tienes que determinar la prioridad adecuada para asignar a la aplicación. Para determinar esta prioridad, ejecute el siguiente cmdlet en Skype para el Shell de administración de servidor de negocios:
  
Get-CsServerApplication-identidad de servicio: Registrar:<Pool FQDN>en este cmdlet, \<Pool FQDN\> es el grupo en que el enrutamiento basado en la ubicación para la aplicación de conferencia debe habilitarse.
  
Este cmdlet devolverá la lista de las aplicaciones alojadas por Skype para Business Server y el valor de prioridad para cada uno de ellos. El enrutamiento basado en la ubicación para la aplicación de conferencia debe tener asignado un valor de prioridad mayor que la aplicación de "UdcAgent" e inferior a las aplicaciones "DefaultRouting", "ExumRouting" y "OutboundRouting". Se recomienda asignar el enrutamiento basado en la ubicación para la aplicación de conferencias en un valor de prioridad que es un punto mayor que el valor de prioridad de la aplicación de "UdcAgent".
  
Por ejemplo, si la aplicación de "UdcAgent" tiene un valor de prioridad de "2", la aplicación de "DefaultRouting" tiene un valor de prioridad de "8", la aplicación de "ExumRouting" tiene un valor de prioridad de "9" y la aplicación de "OutboundRouting" tiene un valor de prioridad de "10", a continuación el enrutamiento basado en la ubicación para la aplicación de conferencia debe asignar un valor de prioridad de "3". Al hacerlo, debe colocar la prioridad de las aplicaciones en el orden siguiente: otras aplicaciones (prioridades: 0 a 1), "UdcAgent" (prioridad: 2), aplicación de conferencia de enrutamiento basada en ubicación (prioridad: 3), otras aplicaciones (prioridades: 4 a 8), " DefaultRouting"(prioridad: 9),"ExumRouting"(prioridad: 10) y"OutboundRouting"(prioridad: 11).
  
Después de encontrar el valor correcto de prioridad para el enrutamiento basado en la ubicación para la aplicación de conferencias, escriba el siguiente cmdlet para cada servidor Standard Edition o el grupo de aplicaciones para el usuario que los usuarios de hogares habilitados para enrutamiento basado en la ubicación:
  
Nueva CsServerApplication-identidad de servicio: Registrar:<Pool FQDN>/LBRouting-prioridad <Application Priority> -habilitado $true-crítica $true - Uri http://www.microsoft.com/LCS/LBRoutingFor ejemplo:
  
Nueva CsServerApplication-identidad Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting-prioridad 3 - $true habilitado-crítica $true - Uri http://www.microsoft.com/LCS/LBRoutingAfter mediante este cmdlet, reinicie todos los servidores Front-End en los servidores Standard Edition o el grupo de servidores donde el Se ha habilitado el enrutamiento basado en la ubicación para la aplicación de conferencia.
  
> [!IMPORTANT]
> No se exige según ubicación enrutamiento aplicaciones para conferencias o consultivo transferencia hasta que todos los servidores frontales en las piscinas aplicables o se reinician los servidores Standard Edition. Si se establece **-crítico** **$true** en los cmdlets anteriores, su Skype para los servicios de servidor de Business se iniciará inmediatamente. Si no desea que estos servicios se reinicien inmediatamente, establezca **-crítico** **$false** por ahora y, a continuación, utilice el **Conjunto CsServerApplication** para cambiar **-crítico** **$true** más adelante, después de haberse reiniciados los servicios.
  
Una vez que se ha habilitado correctamente el enrutamiento basado en la ubicación para la aplicación de conferencia y todos los servidores aplicables se haya reiniciado, se supervisarán todas las conferencias organizadas por Skype para los usuarios de negocios habilitados para enrutamiento basado en la ubicación para evitar que Omitir pago PSTN
  


---
title: Enrutamiento para las conferencias en Skype para Business Server basados en ubicación
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planeación de basados en ubicación enrutamiento para las conferencias en Skype para Business Server Enterprise Voice, incluidas consultoría llame a transferencias.
ms.openlocfilehash: d786f8def8cf88e29bbac2a908163a5a92d61d47
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373245"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Enrutamiento para las conferencias en Skype para Business Server basados en ubicación

Planeación de basados en ubicación enrutamiento para las conferencias en Skype para Business Server Enterprise Voice, incluidas consultoría llame a transferencias.

Enrutamiento basado en ubicación hace posible restringir el enrutamiento de llamadas entre los extremos de VoIP y los extremos de RTC en función de la ubicación de las partes en la llamada. Enrutamiento para conferencias de acceso basados en ubicación le permite aplicar las reglas de enrutamiento basado en la ubicación en el desvío de pago de las reuniones (es decir, conferencias) para evitar que la RTC. La aplicación supervisa una conferencia activada e impone restricciones de enrutamiento basado en la ubicación en función de la ubicación de los usuarios que participan. Además, el enrutamiento basado en la ubicación para la aplicación de conferencia permite la aplicación de restricciones de enrutamiento basados en ubicación para transferencias con consultas que implican los extremos de RTC.

La aplicación de conferencias de enrutamiento basados en ubicación proporciona a Skype para conferencias de empresa un mecanismo para la prevención de pago de RTC de desvío. La aplicación supervisa conferencias activas e impone restricciones de enrutamiento basado en la ubicación en función de la ubicación de la Skype para usuarios profesionales que participan.

La aplicación de conferencias de enrutamiento basados en ubicación determina si enrutamiento basado en la ubicación es para que se ejecute en un Skype para la reunión de negocios si se cumplen los siguientes criterios:

- El organizador de la reunión está habilitado para enrutamiento basado en la ubicación. Restricciones de enrutamiento basados en ubicación se aplicará sólo a las conferencias que se organizan por los usuarios habilitados para enrutamiento basado en la ubicación.

- Al menos uno de los participantes de la reunión es un extremo de RTC. Restricciones de enrutamiento basados en ubicación son aplicables sólo para las conferencias que incluyen los extremos de RTC.

- El sitio de red donde se utiliza la puerta de enlace RTC para conectar la conferencia con la RTC se encuentra (al igual que los sitios de red) en la ubicación desde donde se conectan los organizadores y los participantes.

El enrutamiento basado en la ubicación para la aplicación de conferencia impide que la participación de Skype para los usuarios profesionales y extremos de RTC de sitios de red distinta a la misma conferencia. Si el organizador de una reunión está habilitado para enrutamiento basado en la ubicación, la aplicación de conferencias impone las siguientes restricciones:

- Los extremos que pueden unirse a una Skype para la reunión de negocios dependen de los extremos que ya se unió a la conferencia, y esta restricción se ajusta como extremos unidas deje y nuevos extremos unirse a la conferencia. Si los organizadores y los participantes se une a una Skype para la reunión de negocios desde el mismo sitio de red, a continuación, un extremo de RTC, otro participante desde el mismo sitio de red, otro participante desde un sitio de red distinta o un participante desde un sitio de red desconocido le permite unirse a.

- Si organizadores y participantes se unen a la reunión desde diferentes sitios de red o sitios de red desconocidos, no se permite la entrada a la reunión de un extremo de RTC, si la llamada de RTC entra de un tronco SIP habilitado para el enrutamiento basado en ubicación.

- Si los organizadores y los participantes se une a la reunión desde el mismo sitio de red y hay participantes que se unan a la reunión misma desde la RTC, no se permite un Skype para extremo empresarial desde un sitio de red diferentes para unirse a la reunión.

En la siguiente tabla se resumen estas restricciones de enrutamiento basado en la ubicación de la conferencia.

| |

|**Usuario(s) en una conferencia en un momento determinado**|**Usuarios(s) con permiso para unirse a la conferencia**|**Usuarios(s) sin permiso para unirse a la conferencia**|
|:-----|:-----|:-----|
|Skype para usuarios de cliente de VoIP empresarial desde un sitio de red único  <br/> |Skype para el usuario de cliente de VoIP de negocio desde el mismo sitio de red  <br/> Skype para el usuario de cliente de VoIP empresarial desde un sitio de red diferentes  <br/> Skype para el usuario de cliente de VoIP empresarial desde un sitio de red desconocido  <br/> Skype federada para el usuario de cliente de VoIP de negocio  <br/> Usuario que se une desde un extremo de RTC  <br/> |Ninguno  <br/> |
|Skype para usuarios de cliente de VoIP de negocio de un sitio de red desconocido  <br/> |Skype para el usuario de cliente de VoIP de negocio desde cualquier sitio  <br/> Skype para el usuario de cliente de VoIP empresarial desde un sitio desconocido  <br/> Skype federada para el usuario de cliente de VoIP de negocio  <br/> |Usuario que se une a través de un extremo de RTC  <br/> |
|Skype para los usuarios de cliente de VoIP empresarial desde sitios de red diferentes  <br/> |Skype para el usuario de cliente de VoIP empresarial desde cualquier sitio de red  <br/> Skype para el usuario de cliente de VoIP empresarial desde un sitio de red desconocido  <br/> Skype federada para el usuario de cliente de VoIP de negocio  <br/> |Usuario que se une a través de un extremo de RTC  <br/> |
|Skype para usuarios de cliente de VoIP empresarial desde un sitio de red único y los usuarios que se unan a partir de un extremo de RTC  <br/> |Skype para el usuario de cliente de VoIP de negocio desde el mismo sitio de red  <br/> |Skype para el usuario de cliente de VoIP empresarial desde un sitio de red diferentes  <br/> Skype para el usuario de cliente de VoIP empresarial desde un sitio de red desconocido  <br/> Skype federada para el usuario de cliente de VoIP de negocio  <br/> |

Las siguientes son características adicionales del enrutamiento basado en la ubicación para la aplicación de conferencia:

- Cuando un usuario no se permite unirse a una conferencia dada restricciones de enrutamiento basados en ubicación, se rechazará la llamada a la conferencia y el Skype para cliente empresarial va a informe de que la llamada no fue completado o ha finalizado.

- Una RTC extremo unirse a que una conferencia con aplicaciones de enrutamiento basado en la ubicación no se restringen a unirse a la conferencia, independientemente de su estado si el extremo se une a través de un tronco que no está habilitado para enrutamiento basado en la ubicación.

- Un sistema PBX conectado a un servidor de mediación a través de un tronco SIP que no egreso llamadas a la RTC tendrá el mismo aplicaciones como Skype para usuarios profesionales que se encuentran en el mismo sitio de red donde se define el tronco SIP. Por ejemplo, un extremo de RTC podrán unirse a una conferencia con un usuario de PBX y un Skype para usuarios de empresa si se encuentran en el mismo sitio de red; de lo contrario, no se permitirá el extremo de RTC para unirse a la conferencia si el usuario de PBX se encuentra en un sitio de red distinta que la Skype para usuarios de empresa.

> [!NOTE]
> Con la actualización acumulativa 4 de Skype Empresarial, debe observarse el comportamiento en la siguiente tabla:

|**Usuario**|**Terceros**|**Acción**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype Empresarial para móviles está en una llamada RTC. Skype Empresarial para móviles luego escala la llamada a un operador automático de conferencia (CAA).  <br/> |La llamada se bloquea, con un mensaje de error apropiado.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado o cliente de Skype Empresarial  <br/> |El cliente o el usuario federado está en una llamada VoIP a un Skype para enrutamiento de Business Mobile Location-Based usuario y cualquiera de las partes que se pasa a un CAA.  <br/> |La llamada de escalación se bloquea, con un mensaje de error apropiado.  <br/> |

## <a name="consultative-call-transfers"></a>Transferencias de llamada de consulta

Además de aplicar el enrutamiento basado en la ubicación a Skype para reuniones de negocios, el enrutamiento basado en la ubicación para la aplicación de conferencia impone restricciones de enrutamiento basado en la ubicación en las transferencias de consultoría de llamada que egreso a extremos de RTC. Una transferencia con consulta llamada es una llamada establecida entre dos partes donde una de las partes transfiere la llamada a un nuevo usuario. Por ejemplo, un extremo de RTC llama a usuario (Skype para el destinatario de la llamada empresarial). El usuario A determina que el usuario RTC se reenviará a usuario B (Skype para usuarios de empresa). Lugares de usuario A que la llamada con el usuario de RTC en espera y el usuario de las llamadas B. usuario B acepta para hablar con el usuario de RTC. El usuario A transfiere la llamada en espera al usuario B.

**Flujo de llamadas de transferencia de llamada de consulta**

![Enrutamiento basado en ubicación para diagrama de conferencias](../../media/LocationBasedRoutingForConferencing.jpg)

Cuando un usuario habilitado para enrutamiento basados en ubicación inicia una transferencia de llamada a través de un extremo de RTC (tal como se muestra en la ilustración anterior), esto crea dos llamadas activas, una llamada entre el usuario de RTC y Skype para el usuario empresarial A y la otra entre Skype para El enrutamiento basado en la ubicación para la aplicación de conferencia exige el usuario empresarial A y Skype para usuarios de empresa B. el siguiente comportamiento:

- Si el tronco SIP la RTC el enrutamiento de llamadas está autorizadas para volver a enrutar la llamada de RTC al sitio de red Skype para usuarios de empresa B (es decir, el destino de transferencia) se encuentra donde,,, a continuación, se permitirá la transferencia de llamada; de lo contrario, se bloqueará la transferencia de llamada de consultoría. Esta autorización se realiza en función en la ubicación de la parte transferidos que se está en el mismo sitio de red que el tronco SIP que redirige la llamada activa al extremo de RTC.

- Si el tronco SIP enrutar la llamada de RTC entrante no está autorizado para enrutar las llamadas al sitio de red donde se encuentra la parte transferida (Skype para usuarios de empresa B) o la parte transferida se encuentra en un sitio de red desconocido, a continuación, la llamada consultoría transferir a se bloqueará el extremo de RTC (es decir, objetivo de transferencia de llamadas).

En la siguiente tabla se describe cómo basado en la ubicación de enrutamiento se aplican restricciones por el enrutamiento basado en la ubicación para aplicación de conferencia para las transferencias de consultoría de llamada. A pesar de que los extremos de PBX no están directamente asociados con un sitio de red, el tronco SIP al cual está conectado la PBX se puede asignar a un sitio de red. Por lo tanto, el extremo de PBX se puede asociar indirectamente con el sitio de red.


|**Sitio de red de la entidad de origen de la transferencia de la llamada**|**Sitio de red del destino de la transferencia de la llamada**|**Comportamiento**|
|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Skype para usuarios de empresa en el mismo sitio de red (es decir, sitio 1)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Skype para usuarios de empresa en sitios de red diferentes (es decir, el sitio 2)  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Skype para usuarios de empresa en un sitio de red desconocido  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Skype federada para usuarios de empresa  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Extremo de PBX en el mismo sitio (es decir, el sitio 1)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Extremo de PBX en un sitio diferente (es decir, el sitio 2)  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en el mismo sitio (es decir, el sitio 1)  <br/> |Extremo de RTC  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en un sitio diferente (es decir, el sitio 2)  <br/> |Extremo de RTC  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Skype para usuarios de empresa en el mismo sitio de red (es decir, sitio 1)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Skype para usuarios de empresa en sitios de red diferentes (es decir, el sitio 2)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Skype para usuarios de empresa en un sitio de red desconocido  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Skype federada para usuarios de empresa  <br/> |Se permitirá la transferencia de consulta  <br/> |

## <a name="requirements"></a>Requisitos

El enrutamiento basado en la ubicación para la aplicación de conferencia requiere que se implementa en Skype para Business Server o en Lync Server 2013 acumulativa actualización 2 en todos los grupos de servidores front-end y servidores Standard Edition en la topología. Si estas versiones de servidor no están instaladas en algunos servidores en la topología, las restricciones de enrutamiento basado en la ubicación no pueden ser totalmente forzado en las reuniones y consultoría transferencias de llamadas.

En la siguiente tabla identifica la combinación de funciones de servidor y las versiones que admiten enrutamiento basado en la ubicación.


|**Versión del grupo de servidores front-end**|**Versión del servidor de mediación**|**Compatible**|
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

- La ubicación de los participantes que se unen a una reunión se determina a partir de su sitio de red. Un sitio de red y subredes de su red asociada deben definirse en Skype para Business Server con el fin de exigir la aplicación de enrutamiento basado en la ubicación.

- Para exigir la aplicación de enrutamiento basado en la ubicación de las reuniones, Skype para los participantes del negocio debe estar habilitado para enrutamiento basado en la ubicación.

- Para exigir la aplicación de enrutamiento basado en la ubicación de los extremos de RTC para unirse a una conferencia, debe configurarse el tronco SIP que se usa para conectar los extremos de RTC para enrutamiento basado en la ubicación.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitar el enrutamiento basado en la ubicación para las conferencias

El enrutamiento basado en la ubicación para la aplicación de conferencia está deshabilitada de forma predeterminada. Antes de habilitar esta aplicación, tienes que determinar la prioridad adecuada para asignar a la aplicación. Para determinar esta prioridad, ejecute el siguiente cmdlet en Skype para Shell de administración de servidor empresarial:

Get-CsServerApplication-identidad Service: Registrar:<Pool FQDN>en este cmdlet, \<FQDN del grupo de servidores\> es el grupo de servidores en el que el enrutamiento basado en la ubicación para la aplicación de conferencia a habilitarse.

Este cmdlet devolverá la lista de las aplicaciones hospedadas por Skype para Business Server y el valor de prioridad para cada uno de ellos. El enrutamiento basado en la ubicación para la aplicación de conferencia debe tener asignado un valor de prioridad mayor que la aplicación de "UdcAgent" y menor que las aplicaciones de "DefaultRouting", "ExumRouting" y "OutboundRouting". Se recomienda asignar el enrutamiento basado en la ubicación para la aplicación de conferencia en un valor de prioridad que es un punto mayor que el valor de prioridad de la aplicación de "UdcAgent".

Por ejemplo, si la aplicación de "UdcAgent" tiene un valor de prioridad de "2", la aplicación de "DefaultRouting" tiene un valor de prioridad de "8", la aplicación de "ExumRouting" tiene un valor de prioridad de "9" y la aplicación de "OutboundRouting" tiene un valor de prioridad de "10", a continuación el enrutamiento basado en la ubicación para la aplicación de conferencia debe asignar un valor de prioridad de "3". Al hacerlo, debe colocar la prioridad de las aplicaciones en el orden siguiente: otras aplicaciones (las prioridades: 0 a 1), "UdcAgent" (prioridad: 2), aplicación de conferencia de enrutamiento basados en ubicación (prioridad: 3), otras aplicaciones (las prioridades: 4 a 8), " DefaultRouting"(prioridad: 9),"ExumRouting"(prioridad: 10) y"OutboundRouting"(prioridad: 11).

Después de encontrar el valor de prioridad correcta para el enrutamiento basado en la ubicación para la aplicación de conferencia, escriba el siguiente cmdlet para cada servidor Standard Edition o grupo de servidores front-end que los usuarios de casas habilitados para enrutamiento basados en ubicación:

New-CsServerApplication-identidad Service: Registrar:<Pool FQDN>/LBRouting-prioridad <Application Priority> -habilitado $true-crítico $true - Uri <https://www.microsoft.com/LCS/LBRoutingFor> ejemplo:

New-CsServerApplication-Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting Identity-prioridad 3 - $true habilitado-crítico $true - Uri https://www.microsoft.com/LCS/LBRoutingAfter con este cmdlet, reinicie todos los servidores Front-End en los servidores Standard Edition o el grupo de servidores donde el Se ha habilitado el enrutamiento basado en la ubicación para la aplicación de conferencia.

> [!IMPORTANT]
> No se exige basados en ubicación de aplicaciones de enrutamiento a las conferencias o transferencias con consultas hasta que todos los servidores Front-End en los grupos de servidores aplicables o se reinician los servidores Standard Edition. Si establece **-crítico** en **$true** en los cmdlets anteriores, su Skype para servicios de Business Server va a reiniciarse inmediatamente. Si no desea que estos servicios para reiniciar inmediatamente, establezca **-crítico** a **$false** en este momento y, a continuación, utilice el **Set-CsServerApplication** para cambiar **-crítico** en **$true** más adelante, después de haberse reiniciados los servicios.

Una vez que se ha habilitado correctamente el enrutamiento basado en la ubicación para la aplicación de conferencia y se haya reiniciado todos los servidores aplicables, se van a supervisar para evitar que todas las conferencias organizadas por Skype para usuarios profesionales habilitados para enrutamiento basados en ubicación El desvío de llamadas de RTC



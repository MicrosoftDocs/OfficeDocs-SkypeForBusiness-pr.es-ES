---
title: Enrutamiento basado en la ubicación para conferencias en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planear el enrutamiento basado en la ubicación de las conferencias en la telefonía IP empresarial de Skype empresarial, incluyendo las transferencias de llamadas Consultiva.
ms.openlocfilehash: d9ca03920fe361cf4d7692fd80031bef01b03b17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276785"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Enrutamiento basado en la ubicación para conferencias en Skype empresarial Server

Planear el enrutamiento basado en la ubicación de las conferencias en la telefonía IP empresarial de Skype empresarial, incluyendo las transferencias de llamadas Consultiva.

El enrutamiento basado en la ubicación permite restringir el enrutamiento de llamadas entre puntos de conexión VoIP y puntos de conexión RTC en función de la ubicación de las partes en la llamada. El enrutamiento basado en la ubicación de las conferencias le permite aplicar reglas de enrutamiento basadas en la ubicación en reuniones (es decir, conferencias) para evitar el bypass de llamadas RTC. La aplicación supervisa una conferencia activa y aplica restricciones de enrutamiento basadas en la ubicación en función de la ubicación de los usuarios que participan. El enrutamiento basado en la ubicación de la aplicación de conferencia también permite la aplicación de restricciones de enrutamiento basadas en la ubicación a las transferencias consultivas que implican puntos de conexión RTC.

La aplicación de conferencia de enrutamiento basada en la ubicación proporciona a las conferencias de Skype empresarial un mecanismo para la prevención de la omisión de llamadas RTC. La aplicación supervisa las conferencias activas e impone restricciones de enrutamiento basadas en la ubicación en función de la ubicación de los usuarios de Skype empresarial que participan.

La aplicación de conferencia de enrutamiento basada en la ubicación determina si se debe aplicar el enrutamiento basado en la ubicación en una reunión de Skype empresarial si se cumplen los criterios siguientes:

- El organizador de la reunión está habilitado para el enrutamiento basado en la ubicación. Las restricciones de enrutamiento basadas en la ubicación solo se aplicarán a conferencias organizadas por usuarios que están habilitados para el enrutamiento basado en la ubicación.

- Al menos uno de los participantes de la reunión es un extremo de RTC. Las restricciones de enrutamiento basadas en la ubicación solo se aplican a las conferencias que incluyen puntos de conexión RTC.

- El sitio de red donde se utiliza la puerta de enlace RTC para conectar la conferencia con la RTC se encuentra (al igual que los sitios de red) en la ubicación desde donde se conectan los organizadores y los participantes.

El enrutamiento basado en la ubicación de la aplicación de conferencias impide la participación de los usuarios de Skype empresarial y los puntos finales de la RTC de diferentes sitios de red en la misma conferencia. Si el organizador de una reunión está habilitado para el enrutamiento basado en la ubicación, la aplicación de conferencias aplicará las siguientes restricciones:

- Los puntos de conexión que pueden unirse a una reunión de Skype empresarial dependen de los puntos de conexión que ya se hayan unido a la Conferencia, y esta restricción se ajusta como puntos de conexión Unidos y se unen nuevos puntos de conexión a la Conferencia. Si los organizadores y los participantes se unen a una reunión de Skype empresarial desde el mismo sitio de red, entonces un punto final de la RTC, otro participante del mismo sitio de red, otro participante de un sitio de red diferente o un participante de un sitio de red desconocido pueden unirse.

- Si organizadores y participantes se unen a la reunión desde diferentes sitios de red o sitios de red desconocidos, no se permite la entrada a la reunión de un extremo de RTC, si la llamada de RTC entra de un tronco SIP habilitado para el enrutamiento basado en ubicación.

- Si todos los organizadores y participantes se unen a la reunión desde el mismo sitio de red y hay participantes que se unen a la misma reunión de la RTC, un extremo de Skype empresarial desde un sitio de red diferente no puede unirse a la reunión.

En la tabla siguiente se resumen las restricciones de enrutamiento basadas en la ubicación de las conferencias.

| |

|**Usuario(s) en una conferencia en un momento determinado**|**Usuarios(s) con permiso para unirse a la conferencia**|**Usuarios(s) sin permiso para unirse a la conferencia**|
|:-----|:-----|:-----|
|Usuarios de cliente de VoIP de Skype empresarial desde un único sitio de red  <br/> |Usuario de cliente de VoIP de Skype empresarial desde el mismo sitio de red  <br/> Usuario de cliente de VoIP de Skype empresarial desde un sitio de red diferente  <br/> Usuario de cliente de VoIP de Skype empresarial desde un sitio de red desconocido  <br/> Usuario del cliente de VoIP de Skype empresarial federado  <br/> Usuario que se une desde un extremo de RTC  <br/> |Ninguno  <br/> |
|Usuarios de cliente de VoIP de Skype empresarial desde un sitio de red desconocido  <br/> |Usuario de cliente VoIP de Skype empresarial desde cualquier sitio  <br/> Usuario de cliente VoIP de Skype empresarial desde un sitio desconocido  <br/> Usuario del cliente de VoIP de Skype empresarial federado  <br/> |Usuario que se une a través de un extremo de RTC  <br/> |
|Usuarios de Skype empresarial VoIP para clientes de diferentes sitios de red  <br/> |Usuario de cliente de VoIP de Skype empresarial desde cualquier sitio de red  <br/> Usuario de cliente de VoIP de Skype empresarial desde un sitio de red desconocido  <br/> Usuario del cliente de VoIP de Skype empresarial federado  <br/> |Usuario que se une a través de un extremo de RTC  <br/> |
|Usuarios del cliente de VoIP de Skype empresarial desde un único sitio de red y usuarios que se unen desde un punto final de RTC  <br/> |Usuario de cliente de VoIP de Skype empresarial desde el mismo sitio de red  <br/> |Usuario de cliente de VoIP de Skype empresarial desde un sitio de red diferente  <br/> Usuario de cliente de VoIP de Skype empresarial desde un sitio de red desconocido  <br/> Usuario del cliente de VoIP de Skype empresarial federado  <br/> |

A continuación se muestran características adicionales de la ruta basada en la ubicación de la aplicación de conferencias:

- Cuando un usuario no puede unirse a una conferencia con las restricciones de enrutamiento basadas en la ubicación, se rechazará la llamada a la Conferencia y el cliente de Skype empresarial informará de que la llamada no se completó o ha finalizado.

- Un punto final de RTC que se une a una conferencia con las fuerzas de enrutamiento basadas en la ubicación no se verá restringido a unirse a la Conferencia, independientemente de su estado, si el punto de conexión se une a través de un tronco que no está habilitado para el enrutamiento basado en la ubicación.

- Un sistema PBX conectado a un servidor de mediación a través de un tronco del SIP que no esté de salida las llamadas a la RTC tendrán las mismas fuerzas que los usuarios de Skype empresarial que se encuentren en el mismo sitio de red en el que se define el tronco del SIP. Por ejemplo, un punto final de RTC podrá unirse a una conferencia con un usuario de PBX y un usuario de Skype empresarial si se encuentran en el mismo sitio de red; de lo contrario, el punto final de RTC no podrá unirse a la Conferencia si el usuario de PBX se encuentra en otro sitio de red que el usuario de Skype empresarial.

> [!NOTE]
> Con la actualización acumulativa 4 de Skype Empresarial, debe observarse el comportamiento en la siguiente tabla:

|**Usuario**|**Terceros**|**Acción**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype Empresarial para móviles está en una llamada RTC. Skype Empresarial para móviles luego escala la llamada a un operador automático de conferencia (CAA).  <br/> |La llamada se bloquea, con un mensaje de error apropiado.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado o cliente de Skype Empresarial  <br/> |El cliente o usuario federado está en una llamada de VoIP a un usuario de enrutamiento basado en una ubicación móvil de Skype empresarial, y cada una de ellas se eleva a un CAA.  <br/> |La llamada de escalación se bloquea, con un mensaje de error apropiado.  <br/> |

## <a name="consultative-call-transfers"></a>Transferencias de llamada de consulta

Además de exigir el enrutamiento basado en la ubicación de las reuniones de Skype empresarial, el enrutamiento basado en la ubicación de la aplicación de conferencias aplica restricciones de enrutamiento basadas en la ubicación en las transferencias de llamadas Consultiva que se producen a puntos de conexión de RTC. Una transferencia de llamadas Consultiva es una llamada establecida entre dos partes cuando una de las partes la transfiere a un nuevo usuario. Por ejemplo, un punto final de RTC llama al usuario A (llamada de Skype empresarial). El usuario A determina que el usuario de RTC debe reenviarse al usuario B (usuario de Skype empresarial). El usuario A coloca la llamada con el usuario de la RTC en espera y llama al usuario B. el usuario B acepta hablar con el usuario de la RTC. El usuario A transfiere la llamada en espera al usuario B.

**Flujo de llamadas de transferencia de llamada de consulta**

![Enrutamiento basado en ubicación para diagrama de conferencias](../../media/LocationBasedRoutingForConferencing.jpg)

Cuando un usuario habilitado para el enrutamiento basado en la ubicación inicia una llamada Consultiva de un extremo RTC (tal como se muestra en la ilustración anterior), se crean dos llamadas activas, una llamada entre el usuario de la RTC y el usuario de Skype empresarial A, y otra entre Skype para Empresa A y usuario de Skype empresarial B. el comportamiento de la aplicación de enrutamiento basado en la ubicación de la aplicación de conferencia es el siguiente:

- Si el enrutamiento de tronco del SIP la llamada RTC está autorizada para redirigir la llamada RTC al sitio de red en el que se encuentra el usuario B (por ejemplo, el destino de transferencia) de Skype empresarial, se permitirá la transferencia de llamadas; de lo contrario, la transferencia de llamadas Consultiva se bloqueará. Esta autorización se realiza en función de la ubicación de la parte transferida en el mismo sitio de red que el tronco del SIP que enruta la llamada activa al punto final de la RTC.

- Si el enrutamiento de tronco del SIP, la llamada RTC entrante no está autorizada para enrutar llamadas al sitio de red en el que se encuentra la parte transferida (usuario de Skype empresarial B) o la parte transferida se encuentra en un sitio de red desconocido, entonces la transferencia de la llamada consultiva a se bloqueará el extremo de la RTC (es decir, el destino de la transferencia de llamadas).

En la tabla siguiente se describe cómo aplican las restricciones de enrutamiento basado en la ubicación en el enrutamiento basado en la ubicación de la aplicación de conferencias para las transferencias de llamadas Consultiva. A pesar de que los extremos de PBX no están directamente asociados con un sitio de red, el tronco SIP al cual está conectado la PBX se puede asignar a un sitio de red. Por lo tanto, el extremo de PBX se puede asociar indirectamente con el sitio de red.


|**Sitio de red de la entidad de origen de la transferencia de la llamada**|**Sitio de red del destino de la transferencia de la llamada**|**Comportamiento**|
|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Usuario de Skype empresarial en el mismo sitio de red (es decir, sitio 1)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Usuario de Skype empresarial en diferentes sitios de red (es decir, sitio 2)  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Usuario de Skype empresarial en un sitio de red desconocido  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Usuario federado de Skype empresarial  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Extremo de PBX en el mismo sitio (es decir, el sitio 1)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de RTC  <br/> |Extremo de PBX en un sitio diferente (es decir, el sitio 2)  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en el mismo sitio (es decir, el sitio 1)  <br/> |Extremo de RTC  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en un sitio diferente (es decir, el sitio 2)  <br/> |Extremo de RTC  <br/> |No se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario de Skype empresarial en el mismo sitio de red (es decir, sitio 1)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario de Skype empresarial en diferentes sitios de red (es decir, sitio 2)  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario de Skype empresarial en un sitio de red desconocido  <br/> |Se permitirá la transferencia de consulta  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario federado de Skype empresarial  <br/> |Se permitirá la transferencia de consulta  <br/> |

## <a name="requirements"></a>Requisitos

Para la aplicación de conferencia de enrutamiento basado en la ubicación es necesario que se implemente Skype empresarial Server o la actualización acumulativa 2013 de Lync Server en todos los servidores Standard Edition y en los grupos de aplicaciones para el usuario de su topología. Si estas versiones de servidor no se instalan en algunos servidores de su topología, las restricciones de enrutamiento basadas en la ubicación no se pueden aplicar por completo en reuniones y transferencias de llamadas Consultiva.

En la siguiente tabla se identifica la combinación de las versiones y los roles de servidor que admiten el enrutamiento basado en la ubicación.


|**Versión del grupo de servidores front-end**|**Versión del servidor de mediación**|**Compatible**|
|:-----|:-----|:-----|
|Actualización acumulativa 2 de Skype empresarial Server o Lync Server 2013  <br/> |Actualización acumulativa 2 de Skype empresarial Server o Lync Server 2013  <br/> |Sí  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Actualización acumulativa 1 de Lync Server 2013  <br/> |No  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Lync Server 2010  <br/> |No  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |No  <br/> |
|Actualización acumulativa 1 de Lync Server 2013  <br/> |Cualquiera  <br/> |No  <br/> |
|Lync Server 2010  <br/> |Cualquiera  <br/> |No  <br/> |
|Office Communications Server 2007 R2  <br/> |Cualquiera  <br/> |No  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuración de enrutamiento basado en la ubicación para conferencias

El enrutamiento basado en la ubicación de la aplicación de conferencias depende de la configuración del enrutamiento basado en la ubicación. Las siguientes son las opciones de configuración principales:

- La ubicación de los participantes que se unen a una reunión se determina a partir de su sitio de red. Para aplicar el enrutamiento basado en la ubicación, se debe definir un sitio de red y sus subredes de red asociadas.

- Para aplicar el enrutamiento basado en la ubicación de las reuniones, los participantes de Skype empresarial deben estar habilitados para el enrutamiento basado en la ubicación.

- Para aplicar el enrutamiento basado en la ubicación de los puntos de conexión RTC que se unen a las reuniones, el troncal SIP usado para conectar los puntos de conexión RTC debe estar configurado para el enrutamiento basado en la ubicación.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitar el enrutamiento basado en la ubicación para las conferencias

El enrutamiento basado en la ubicación de la aplicación de conferencias está deshabilitado de forma predeterminada. Antes de habilitar esta aplicación, tienes que determinar la prioridad adecuada para asignar a la aplicación. Para determinar esta prioridad, ejecute el siguiente cmdlet en el shell de administración de Skype empresarial Server:

Get-CsServerApplication-Identity Service: registrar:<Pool FQDN>en este CMDLET, \<FQDN\> del grupo es el grupo en el que se va a habilitar el enrutamiento basado en la ubicación para la aplicación de conferencias.

Este cmdlet devolverá la lista de las aplicaciones hospedadas por Skype empresarial Server y el valor de prioridad para cada una de ellas. El enrutamiento basado en la ubicación de la aplicación de conferencias necesita tener asignado un valor de prioridad mayor que el de la aplicación "UdcAgent" y menor que las aplicaciones "DefaultRouting", "ExumRouting" y "OutboundRouting". Le recomendamos que asigne el enrutamiento basado en la ubicación de la aplicación de conferencias un valor de prioridad que sea un punto superior al valor de prioridad de la aplicación "UdcAgent".

Por ejemplo, si la aplicación "UdcAgent" tiene un valor de prioridad de "2", la aplicación "DefaultRouting" tiene un valor de prioridad de "8", la aplicación "ExumRouting" tiene un valor de prioridad de "9" y la aplicación "OutboundRouting" tiene un valor de prioridad de "10" y, a continuación, debe asignar el enrutamiento basado en la ubicación de la aplicación de conferencias como valor de prioridad "3". De esta manera, la prioridad de las aplicaciones se pondría en el siguiente orden: otras aplicaciones (prioridades: 0 a 1), "UdcAgent" (prioridad: 2), aplicación de conferencia de enrutamiento basada en la ubicación (prioridad: 3), otras aplicaciones (prioridades: de 4 a 8), " DefaultRouting "(Priority: 9)," ExumRouting "(Priority: 10) y" OutboundRouting "(Priority: 11).

Después de encontrar el valor de prioridad correcto para el enrutamiento basado en la ubicación de la aplicación de conferencias, escriba el siguiente cmdlet para cada grupo de servidores front-end o un servidor Standard Edition que aloje usuarios habilitados para el enrutamiento basado en la ubicación:

New-CsServerApplication-Identity Service: registrar: >/LBRouting-Priority Application Priority $true Enabled $true-URI<http://www.microsoft.com/LCS/LBRouting> 

Por ejemplo:

New-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3-habilitado $true-$true-URIhttp://www.microsoft.com/LCS/LBRouting 

Después de usar este cmdlet, reinicie todos los servidores front-end del grupo o los servidores Standard Edition donde se haya habilitado el enrutamiento basado en la ubicación de la aplicación de conferencias.

> [!IMPORTANT]
> Los cumplimientos de enrutamiento basado en la ubicación de las conferencias o las transferencias de asesoría no se aplicarán hasta que se reinicien todos los servidores front-end de los servidores Standard Edition o Standard Edition. Si establece **-crítico** para **$true** en los cmdlets anteriores, los servicios de Skype empresarial Server se reiniciarán inmediatamente. Si no desea que estos servicios se reinicien inmediatamente, establezca **-crítico** para **$false** por ahora y, a continuación, use **set-CsServerApplication** para que el cambio sea **crítico** para **$true** posteriormente, después de que se hayan reiniciado los servicios.

Una vez que se haya habilitado correctamente el enrutamiento basado en ubicación para la aplicación de conferencias y se hayan reiniciado todos los servidores correspondientes, todas las conferencias organizadas por usuarios de Skype empresarial habilitadas para el enrutamiento basado en la ubicación se supervisarán para evitar Omisión de pago de RTC



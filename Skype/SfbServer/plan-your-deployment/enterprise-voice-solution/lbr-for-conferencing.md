---
title: Location-Based enrutamiento de conferencias en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planear el enrutamiento basado en ubicación para conferencias en Skype Empresarial Server Telefonía IP empresarial, incluidas las transferencias de llamadas de consulta.
ms.openlocfilehash: 744f4b313f7ea458013aa0e45cff37ebbf85068a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825580"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based enrutamiento de conferencias en Skype Empresarial Server

Planear el enrutamiento basado en ubicación para conferencias en Skype Empresarial Server Telefonía IP empresarial, incluidas las transferencias de llamadas de consulta.

Location-Based enrutamiento permite restringir el enrutamiento de llamadas entre extremos VoIP y extremos RTC en función de la ubicación de las partes en la llamada. Location-Based enrutamiento de conferencias permite aplicar reglas de enrutamiento de Location-Based en reuniones (es decir, conferencias) para evitar la omisión de pago de RTC. La aplicación supervisa una conferencia activa y aplica Location-Based de enrutamiento basado en la ubicación de los usuarios que participan. La Location-Based enrutamiento de conferencias habilita además la aplicación de restricciones de enrutamiento de Location-Based para las transferencias de consulta que implican extremos RTC.

La Location-Based de enrutamiento de llamadas proporciona a las conferencias de Skype Empresarial un mecanismo para la prevención de la omisión de pago rtc. La aplicación supervisa las conferencias activas y aplica Location-Based de enrutamiento basado en la ubicación de los usuarios de Skype Empresarial que participan.

La Location-Based de enrutamiento de aplicaciones determina si el enrutamiento de Location-Based debe aplicarse en una reunión de Skype Empresarial si se cumplen los siguientes criterios:

- El organizador de la reunión está habilitado para Location-Based enrutamiento. Location-Based restricciones de enrutamiento se aplicarán solo a conferencias organizadas por usuarios habilitados para el Location-Based enrutamiento.

- Al menos un participante de la reunión es un extremo de RTC. Location-Based restricciones de enrutamiento solo se aplican a conferencias que incluyan extremos de RTC.

- El sitio de red donde se ha usado la puerta de enlace RTC para unir la conferencia a la RTC se encuentra, así como los sitios de red desde los que se conectan los organizadores y los participantes.

La Location-Based enrutamiento de conferencias impide la participación de usuarios de Skype Empresarial y puntos de conexión RTC de diferentes sitios de red a la misma conferencia. Si el organizador de una reunión está habilitado para el enrutamiento de Location-Based, la aplicación de conferencia aplica las siguientes restricciones:

- Los puntos de conexión que pueden unirse a una reunión de Skype Empresarial dependen de los puntos de conexión que ya se han unido a la conferencia y esta restricción se ajusta a medida que los puntos de conexión unidos salen y los nuevos puntos de conexión se unen a la conferencia. Si los organizadores y participantes se unen a una reunión de Skype Empresarial desde el mismo sitio de red, se permite un extremo rtc, otro participante del mismo sitio de red, otro participante de un sitio de red diferente o un participante de un sitio de red desconocido.

- Si los organizadores y participantes se unen a la reunión desde sitios de red distintos o desconocidos, no se permite que un extremo rtc se una a la reunión si la llamada RTC entra desde un tronco SIP habilitado para el enrutamiento de Location-Based.

- Si los organizadores y participantes se unen a la reunión desde el mismo sitio de red y hay participantes que se unen a la misma reunión desde la RTC, no se permite que un extremo de Skype Empresarial de un sitio de red diferente se una a la reunión.

Estas restricciones de Location-Based de conferencia se resumen en la tabla siguiente.

|Usuarios de una conferencia en un momento dado|Usuarios permitidos para unirse a la conferencia|Usuarios no permitidos para unirse a la conferencia|
|:-----|:-----|:-----|
|Usuarios de cliente VoIP de Skype Empresarial desde un único sitio de red  <br/> |Usuario de cliente VoIP de Skype Empresarial desde el mismo sitio de red  <br/> Usuario de cliente VoIP de Skype Empresarial desde un sitio de red diferente  <br/> Usuario de cliente VoIP de Skype Empresarial desde un sitio de red desconocido  <br/> Usuario de cliente VoIP federado de Skype Empresarial  <br/> Usuario que se une desde un extremo de RTC  <br/> |Ninguno  <br/> |
|Usuarios de cliente voIP de Skype Empresarial desde un sitio de red desconocido  <br/> |Usuario de cliente VoIP de Skype Empresarial desde cualquier sitio  <br/> Usuario de cliente VoIP de Skype Empresarial desde un sitio desconocido  <br/> Usuario de cliente VoIP federado de Skype Empresarial  <br/> |Usuario que se une a través de un extremo de RTC  <br/> |
|Usuarios de cliente VoIP de Skype Empresarial de diferentes sitios de red  <br/> |Usuario de cliente VoIP de Skype Empresarial desde cualquier sitio de red  <br/> Usuario de cliente VoIP de Skype Empresarial desde un sitio de red desconocido  <br/> Usuario de cliente VoIP federado de Skype Empresarial  <br/> |Usuario que se une a través de un extremo de RTC  <br/> |
|Usuarios de cliente voIP de Skype Empresarial desde un único sitio de red y usuarios que se unen desde un extremo de RTC  <br/> |Usuario de cliente VoIP de Skype Empresarial desde el mismo sitio de red  <br/> |Usuario de cliente VoIP de Skype Empresarial desde un sitio de red diferente  <br/> Usuario de cliente VoIP de Skype Empresarial desde un sitio de red desconocido  <br/> Usuario de cliente VoIP federado de Skype Empresarial  <br/> |

Las siguientes son características adicionales de la aplicación Location-Based enrutamiento de conferencias:

- Cuando un usuario no puede unirse a una conferencia dadas las restricciones de enrutamiento de Location-Based, se rechazará la llamada a la conferencia y el cliente de Skype Empresarial informará de que la llamada no se completó o finalizó.

- Un extremo de RTC que se una a una conferencia con las normas de enrutamiento de Location-Based no estará restringido para unirse a la conferencia independientemente de su estado si el extremo se une a través de un tronco que no está habilitado para el enrutamiento Location-Based web.

- Un sistema PBX conectado a un servidor de mediación a través de un tronco SIP que no salida llamadas a la RTC tendrá las mismas aplicaciones que los usuarios de Skype Empresarial ubicados en el mismo sitio de red donde se define el tronco SIP. Por ejemplo, un extremo de RTC podrá unirse a una conferencia con un usuario de PBX y un usuario de Skype Empresarial si se encuentra en el mismo sitio de red; de lo contrario, el extremo de RTC no podrá unirse a la conferencia si el usuario de PBX se encuentra en un sitio de red diferente al usuario de Skype Empresarial.

> [!NOTE]
> Con la actualización acumulativa 4 de Skype Empresarial, debe observarse el comportamiento de la tabla siguiente:

|User|Otra parte|Action|Resultado|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Mobile  <br/> |RTC  <br/> |Skype Empresarial Mobile está en una llamada RTC. A continuación, Skype Empresarial Mobile escala la llamada a una conferencia Operador automático (CAA).  <br/> |La llamada está bloqueada, con un mensaje de error adecuado.  <br/> |
|Skype Empresarial Mobile  <br/> |Cliente de Skype Empresarial o usuario federado  <br/> |El cliente o el usuario federado está en una llamada VoIP a un usuario de enrutamiento de Location-Based móvil de Skype Empresarial y cualquiera de las partes escala a una CAA.  <br/> |La llamada de escalación está bloqueada, con un mensaje de error adecuado.  <br/> |

## <a name="consultative-call-transfers"></a>Transferencias de llamadas de consulta

Además de aplicar el enrutamiento de Location-Based a reuniones de Skype Empresarial, la aplicación de enrutamiento de Location-Based para conferencias aplica restricciones de enrutamiento de Location-Based en las transferencias de llamadas de consulta que se transfieren a los extremos rtc. Una transferencia de llamada de consulta es una llamada establecida entre dos partes en la que una de las partes transfiere la llamada a un nuevo usuario. Por ejemplo, un extremo de RTC llama al usuario A (destinatario de la llamada de Skype Empresarial). El usuario A determina que el usuario RTC debe reenviarse al usuario B (usuario de Skype Empresarial). El usuario A pone la llamada con el usuario RTC en espera y llama al usuario B. El usuario B acepta hablar con el usuario RTC. El usuario A transfiere la llamada en espera al usuario B.

**Flujo de llamadas de transferencia de llamadas de consulta**

![Enrutamiento basado en ubicación para diagrama de conferencia](../../media/LocationBasedRoutingForConferencing.jpg)

Cuando un usuario habilitado para enrutamiento de Location-Based inicia una transferencia de llamada de consulta de un extremo RTC (como se muestra en la figura anterior), se crean dos llamadas activas, una entre el usuario RTC y el usuario A de Skype Empresarial y la otra entre el usuario A de Skype Empresarial y el usuario B de Skype Empresarial. El siguiente comportamiento lo aplica la aplicación de enrutamiento de Location-Based para conferencias:

- Si el tronco SIP que enruta la llamada RTC está autorizado a volver a enrutar la llamada RTC al sitio de red donde se encuentra el usuario B de Skype Empresarial (es decir, el destino de transferencia), se permitirá la transferencia de la llamada; de lo contrario, se bloqueará la transferencia de llamadas de consulta. Esta autorización se realiza en función de que la ubicación de la parte transferida se encuentra en el mismo sitio de red que el tronco SIP que está enrutando la llamada activa al extremo de RTC.

- Si el tronco SIP que enruta la llamada RTC entrante no está autorizado a enrutar las llamadas al sitio de red donde se encuentra la parte transferida (usuario B de Skype Empresarial) o la parte transferida se encuentra en un sitio de red desconocido, se bloqueará la transferencia de llamada de consulta al extremo de RTC (es decir, el destino de transferencia de llamadas).

En la tabla siguiente se describe cómo Location-Based las restricciones de enrutamiento por parte de la aplicación Location-Based enrutamiento de conferencia para transferencias de llamadas de consulta. Aunque los extremos de PBX no están asociados directamente con un sitio de red, el tronco SIP al que está conectada la PBX se puede asignar a un sitio de red. Por lo tanto, el extremo de PBX puede asociarse indirectamente a un sitio de red.


|Sitio de red de parte transferida de llamada|Sitio de red de destino de transferencia de llamadas|Comportamiento|
|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Usuario de Skype Empresarial en el mismo sitio de red (es decir, sitio 1)  <br/> |Se permitirá la transferencia de consultas  <br/> |
|Extremo de RTC  <br/> |Usuario de Skype Empresarial en sitios de red diferentes (es decir, sitio 2)  <br/> |No se permitirá la transferencia de consultas  <br/> |
|Extremo de RTC  <br/> |Usuario de Skype Empresarial en un sitio de red desconocido  <br/> |No se permitirá la transferencia de consultas  <br/> |
|Extremo de RTC  <br/> |Usuario federado de Skype Empresarial  <br/> |No se permitirá la transferencia de consultas  <br/> |
|Extremo de RTC  <br/> |Extremo de PBX en el mismo sitio (es decir, sitio 1)  <br/> |Se permitirá la transferencia de consultas  <br/> |
|Extremo de RTC  <br/> |Extremo de PBX en sitios diferentes (es decir, sitio 2)  <br/> |No se permitirá la transferencia de consultas  <br/> |
|Extremo de PBX en el mismo sitio (es decir, sitio 1)  <br/> |Extremo de RTC  <br/> |Se permitirá la transferencia de consultas  <br/> |
|Extremo de PBX en un sitio diferente (es decir, sitio 2)  <br/> |Extremo de RTC  <br/> |No se permitirá la transferencia de consultas  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario de Skype Empresarial en el mismo sitio de red (es decir, sitio 1)  <br/> |Se permitirá la transferencia de consultas  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario de Skype Empresarial en sitios de red diferentes (es decir, sitio 2)  <br/> |Se permitirá la transferencia de consultas  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario de Skype Empresarial en un sitio de red desconocido  <br/> |Se permitirá la transferencia de consultas  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario federado de Skype Empresarial  <br/> |Se permitirá la transferencia de consultas  <br/> |

## <a name="requirements"></a>Requirements

La aplicación Location-Based Routing for Conferencing requiere que Skype Empresarial Server o la actualización acumulativa 2 de Lync Server 2013 se implementen en todos los grupos de servidores Front-End y servidores Standard Edition de la topología. Si estas versiones de servidor no están instaladas en algunos servidores de la topología, las restricciones de enrutamiento de Location-Based no se pueden aplicar completamente en las reuniones y las transferencias de llamadas de consulta.

En la tabla siguiente se identifica la combinación de roles de servidor y versiones que admiten Location-Based enrutamiento.


|Front-End versión del grupo de servidores|Versión del servidor de mediación|Compatible|
|:-----|:-----|:-----|
|Actualización acumulativa 2 de Skype Empresarial Server o Lync Server 2013  <br/> |Actualización acumulativa 2 de Skype Empresarial Server o Lync Server 2013  <br/> |Sí  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Actualización acumulativa 1 de Lync Server 2013  <br/> |No  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Lync Server 2010  <br/> |No  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |No  <br/> |
|Actualización acumulativa 1 de Lync Server 2013  <br/> |Cualquiera  <br/> |No  <br/> |
|Lync Server 2010  <br/> |Cualquiera  <br/> |No  <br/> |
|Office Communications Server 2007 R2  <br/> |Cualquiera  <br/> |No  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuración de Location-Based enrutamiento de conferencias

La Location-Based enrutamiento de aplicaciones para conferencias depende de la configuración de Location-Based enrutamiento. Las configuraciones principales son las siguientes:

- La ubicación de los participantes que se unen a una reunión se determina en función de su sitio de red. Un sitio de red y sus subredes de red asociadas deben definirse en Skype Empresarial Server para aplicar Location-Based enrutamiento.

- Para aplicar Location-Based enrutamiento de reuniones, los participantes de Skype Empresarial deben estar habilitados para Location-Based enrutamiento.

- Para aplicar Location-Based enrutamiento de los extremos RTC que se unen a reuniones, el tronco SIP usado para conectar los extremos de RTC debe configurarse para Location-Based enrutamiento.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitación del Location-Based enrutamiento de conferencias

La Location-Based enrutamiento de conferencias está deshabilitada de forma predeterminada. Antes de habilitar esta aplicación, debe determinar la prioridad correcta para asignarla. Para determinar esta prioridad, ejecute el siguiente cmdlet en el Shell de administración de Skype Empresarial Server:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

En este cmdlet, es el grupo en el que se va a habilitar Location-Based enrutamiento de aplicaciones \<Pool FQDN\> para conferencias.

Este cmdlet devolverá la lista de las aplicaciones hospedadas por Skype Empresarial Server y el valor de prioridad para cada una de ellas. A la aplicación Location-Based routing for Conferencing se le debe asignar un valor de prioridad mayor que la aplicación "UdcAgent" y menor que las aplicaciones "DefaultRouting", "ExumRouting" y "OutboundRouting". Se recomienda asignar a la aplicación Location-Based Routing for Conferencing un valor de prioridad que sea un punto superior al valor de prioridad de la aplicación "UdcAgent".

Por ejemplo, si la aplicación "UdcAgent" tiene un valor de prioridad de "2", la aplicación "DefaultRouting" tiene un valor de prioridad de "8", la aplicación "ExumRouting" tiene un valor de prioridad de "9" y la aplicación "OutboundRouting" tiene un valor de prioridad de "10", entonces debe asignar al enrutamiento de Location-Based para la aplicación de conferencia un valor de prioridad de "3". Al hacerlo, la prioridad de las aplicaciones se coloca en el siguiente orden: Otras aplicaciones (prioridades: 0 a 1), "UdcAgent" (prioridad: 2), aplicación de conferencia de enrutamiento de Location-Based (prioridad: 3), otras aplicaciones (prioridades: 4 a 8), "DefaultRouting" (prioridad: 9), "ExumRouting" (prioridad: 10) y "OutboundRouting" (prioridad: 11).

Una vez que encuentre el valor de prioridad correcto para la aplicación de enrutamiento de Location-Based para conferencias, escriba el siguiente cmdlet para cada grupo de servidores Front-End o servidor Standard Edition que aloja usuarios habilitados para el enrutamiento de Location-Based:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Por ejemplo:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Después de usar este cmdlet, reinicie todos los servidores front-end del grupo de servidores o los servidores Standard Edition en los que se haya habilitado el enrutamiento de Location-Based para conferencias.

> [!IMPORTANT]
> Location-Based aplicación de enrutamiento a conferencias o transferencias de consulta no se aplicarán hasta que se reinicien todos los servidores front-end de los grupos de servidores aplicables o los servidores Standard Edition. Si establece **-Critical para** **$true** en los cmdlets anteriores, los servicios de Skype Empresarial Server se reiniciarán inmediatamente. Si no desea que estos servicios se reinicien inmediatamente, establezca **-Critical** en **$false** por ahora y, a continuación, use **Set-CsServerApplication** para cambiar **-Critical** **$true** más adelante, después de haber reiniciado los servicios.

Una vez que la aplicación Location-Based Routing for Conferencing se ha habilitado correctamente y se han reiniciado todos los servidores aplicables, se supervisarán todas las conferencias organizadas por usuarios de Skype Empresarial habilitados para el enrutamiento de Location-Based para evitar la omisión de pago rtc.



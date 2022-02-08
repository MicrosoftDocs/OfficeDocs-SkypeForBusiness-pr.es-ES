---
title: Location-Based enrutamiento de conferencias en Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planeación del enrutamiento basado en ubicación para conferencias en Skype Empresarial Server Telefonía IP empresarial, incluidas las transferencias de llamadas consultiva.
ms.openlocfilehash: 3c5c7e4d374e9ece3ee0f0ce092d4030d2d84100
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387708"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based enrutamiento de conferencias en Skype Empresarial Server

Planeación del enrutamiento basado en ubicación para conferencias en Skype Empresarial Server Telefonía IP empresarial, incluidas las transferencias de llamadas consultiva.

Location-Based enrutamiento permite restringir el enrutamiento de llamadas entre extremos VoIP y puntos de conexión RTC en función de la ubicación de las partes en la llamada. Location-Based routing for Conferencing permite aplicar reglas de enrutamiento de Location-Based en reuniones (es decir, conferencias) para evitar la omisión de pago rtc. La aplicación supervisa una conferencia activa y aplica Location-Based de enrutamiento en función de la ubicación de los usuarios participantes. La Location-Based de enrutamiento para conferencias permite además la aplicación de restricciones de enrutamiento Location-Based las transferencias consulttivas que implican extremos RTC.

La Location-Based de conferencia de enrutamiento proporciona a Skype Empresarial conferencias un mecanismo para la prevención de la omisión de pago RTC. La aplicación supervisa las conferencias activas y aplica Location-Based de enrutamiento en función de la ubicación de los Skype Empresarial participantes.

La Location-Based de conferencia de enrutamiento de Location-Based determina si el enrutamiento de Location-Based debe aplicarse en una reunión de Skype Empresarial si se cumplen los siguientes criterios:

- El organizador de la reunión está habilitado para Location-Based enrutamiento. Location-Based restricciones de enrutamiento se aplicarán solo a conferencias organizadas por usuarios que están habilitados para Location-Based enrutamiento.

- Al menos un participante de la reunión es un extremo RTC. Location-Based restricciones de enrutamiento solo se aplican a conferencias que incluyen puntos de conexión RTC.

- El sitio de red desde el que se usa la puerta de enlace RTC para conectar la conferencia a la RTC, así como los sitios de red desde los que se conectan los organizadores y los participantes.

La Location-Based de enrutamiento para conferencias impide la participación de usuarios Skype Empresarial y puntos de conexión RTC de diferentes sitios de red a la misma conferencia. Si el organizador de una reunión está habilitado para el Location-Based, la aplicación de conferencia aplica las siguientes restricciones:

- Los puntos de conexión que pueden unirse a una reunión de Skype Empresarial dependen de los puntos de conexión que ya se han unido a la conferencia y esta restricción se ajusta a medida que los extremos unidos salen y los nuevos extremos se unen a la conferencia. Si los organizadores y participantes se unen a una reunión de Skype Empresarial desde el mismo sitio de red, se permite un extremo RTC, otro participante del mismo sitio de red, otro participante de un sitio de red diferente o un participante de un sitio de red desconocido.

- Si organizadores y participantes se unen a la reunión desde sitios de red diferentes o desconocidos, no se permite que un extremo RTC se una a la reunión si la llamada RTC entra desde un tronco SIP habilitado para el enrutamiento Location-Based.

- Si los organizadores y los participantes se unen a la reunión desde el mismo sitio de red y hay participantes que se unen a la misma reunión desde la RTC, no se permite que un extremo de Skype Empresarial de un sitio de red diferente se una a la reunión.

Estas restricciones de Location-Based de enrutamiento se resumen en la tabla siguiente.

|Usuarios en una conferencia en un momento dado|Usuarios permitidos para unirse a la conferencia|Los usuarios no pueden unirse a la conferencia|
|:-----|:-----|:-----|
|Skype Empresarial usuarios cliente VoIP desde un único sitio de red  <br/> |Skype Empresarial cliente VoIP desde el mismo sitio de red  <br/> Skype Empresarial cliente VoIP desde un sitio de red diferente  <br/> Skype Empresarial cliente VoIP desde un sitio de red desconocido  <br/> Usuario cliente Skype Empresarial VoIP federado  <br/> Unión de usuarios desde un punto de conexión RTC  <br/> |Ninguno  <br/> |
|Skype Empresarial usuarios cliente VoIP desde un sitio de red desconocido  <br/> |Skype Empresarial cliente VoIP desde cualquier sitio  <br/> Skype Empresarial cliente VoIP desde un sitio desconocido  <br/> Usuario cliente Skype Empresarial VoIP federado  <br/> |Unión de usuarios a través de un extremo RTC  <br/> |
|Skype Empresarial usuarios cliente VoIP de diferentes sitios de red  <br/> |Skype Empresarial cliente VoIP desde cualquier sitio de red  <br/> Skype Empresarial cliente VoIP desde un sitio de red desconocido  <br/> Usuario cliente Skype Empresarial VoIP federado  <br/> |Unión de usuarios a través de un extremo RTC  <br/> |
|Skype Empresarial usuarios cliente VoIP desde un único sitio de red y usuarios que se unen desde un extremo rtc  <br/> |Skype Empresarial cliente VoIP desde el mismo sitio de red  <br/> |Skype Empresarial cliente VoIP desde un sitio de red diferente  <br/> Skype Empresarial cliente VoIP desde un sitio de red desconocido  <br/> Usuario cliente Skype Empresarial VoIP federado  <br/> |

Las siguientes son características adicionales de la aplicación Location-Based enrutamiento para conferencias:

- Cuando un usuario no puede unirse a una conferencia dadas las restricciones de enrutamiento de Location-Based, la llamada a la conferencia se rechazará y el cliente de Skype Empresarial informará de que la llamada no se completó o que ha finalizado.

- Un extremo RTC que se une a una conferencia con las fuerzas de enrutamiento de Location-Based no se restringirá para unirse a la conferencia independientemente de su estado si el extremo se une a través de un tronco que no está habilitado para el enrutamiento Location-Based.

- Un sistema PBX conectado a un servidor de mediación a través de un tronco SIP que no realiza llamadas de salida a la RTC tendrá las mismas aplicaciones que los usuarios de Skype Empresarial ubicados en el mismo sitio de red donde se define el tronco SIP. Por ejemplo, un extremo RTC podrá unirse a una conferencia con un usuario de PBX y un usuario de Skype Empresarial si se encuentran en el mismo sitio de red; de lo contrario, el extremo RTC no podrá unirse a la conferencia si el usuario pbx está en un sitio de red diferente al del usuario de Skype Empresarial.

> [!NOTE]
> Con Skype Empresarial acumulativa 4, se debe observar el comportamiento de la tabla siguiente:

|Usuario|Otra parte|Acción|Resultado|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Móvil  <br/> |RTC  <br/> |Skype Empresarial Mobile está en una llamada RTC. Skype Empresarial Mobile escala la llamada a una conferencia Operador automático (CAA).  <br/> |La llamada está bloqueada, con un mensaje de error adecuado.  <br/> |
|Skype Empresarial Móvil  <br/> |Skype Empresarial cliente o usuario federado  <br/> |El cliente o el usuario federado se encuentra en una llamada VoIP a un usuario de Skype Empresarial Mobile Location-Based Routing y cualquiera de las partes escala a una CAA.  <br/> |La llamada de escalación está bloqueada, con un mensaje de error adecuado.  <br/> |

## <a name="consultative-call-transfers"></a>Transferencias de llamadas consultiva

Además de aplicar Location-Based enrutamiento a reuniones de Skype Empresarial, la aplicación de enrutamiento de Location-Based para conferencias aplica restricciones de enrutamiento de Location-Based en las transferencias de llamadas consulttivas que se transfieren a los puntos de conexión RTC. Una transferencia de llamada consultiva es una llamada establecida entre dos partes donde una de las partes transfiere la llamada a un nuevo usuario. Por ejemplo, un extremo RTC llama al usuario A (Skype Empresarial destinatario). El usuario A determina que el usuario RTC debe reenviarse al usuario B (Skype Empresarial usuario). El usuario A pone la llamada con el usuario RTC en espera y llama al usuario B. El usuario B acepta hablar con el usuario RTC. El usuario A transfiere la llamada en espera al usuario B.

**Flujo de llamadas de transferencia de llamadas consultiva**

![Enrutamiento basado en ubicación para diagrama de conferencia.](../../media/LocationBasedRoutingForConferencing.jpg)

Cuando un usuario habilitado para el enrutamiento de Location-Based inicia una transferencia de llamada consultiva de un extremo RTC (como se muestra en la figura anterior), se crean dos llamadas activas, una entre el usuario RTC y el usuario A de Skype Empresarial y la otra entre el usuario Skype Empresarial A y Skype Empresarial  usuario B. El siguiente comportamiento lo aplica la aplicación Location-Based routing for Conferencing:

- Si el enrutamiento troncal SIP de la llamada RTC está autorizado para Skype Empresarial volver a enrutar la llamada RTC al sitio de red donde se encuentra un usuario B (es decir, destino de transferencia), se permitirá la transferencia de llamadas; de lo contrario, se bloqueará la transferencia de llamadas consultiva. Esta autorización se realiza en función de la ubicación de la parte transferida que se encuentra en el mismo sitio de red que el tronco SIP que enruta la llamada activa al extremo RTC.

- Si el enrutamiento troncal SIP de la llamada RTC entrante no está autorizado para enrutar llamadas al sitio de red donde se encuentra la parte transferida Skype Empresarial (usuario B) o la parte transferida se encuentra en un sitio de red desconocido, se bloqueará la transferencia de llamada consultiva al punto de conexión rtc (es decir, destino de transferencia de llamadas).

En la tabla siguiente se describe cómo Location-Based restricciones de enrutamiento se aplican mediante la aplicación Location-Based enrutamiento para conferencias para transferencias de llamadas consultiva. Aunque los extremos de PBX no están asociados directamente con un sitio de red, el tronco SIP al que está conectada la PBX puede asignarse a un sitio de red. Por lo tanto, el extremo PBX puede asociarse indirectamente a un sitio de red.


|Sitio de red de la parte transferida de llamadas|Sitio de red de destino de transferencia de llamadas|Comportamiento|
|:-----|:-----|:-----|
|Extremo RTC  <br/> |Skype Empresarial usuario en el mismo sitio de red (es decir, sitio 1)  <br/> |Se permitirá la transferencia consultiva  <br/> |
|Extremo RTC  <br/> |Skype Empresarial usuario en diferentes sitios de red (es decir, sitio 2)  <br/> |No se permitirá la transferencia consultiva  <br/> |
|Extremo RTC  <br/> |Skype Empresarial usuario en un sitio de red desconocido  <br/> |No se permitirá la transferencia consultiva  <br/> |
|Extremo RTC  <br/> |Usuario Skype Empresarial federado  <br/> |No se permitirá la transferencia consultiva  <br/> |
|Extremo RTC  <br/> |Extremo PBX en el mismo sitio (es decir, sitio 1)  <br/> |Se permitirá la transferencia consultiva  <br/> |
|Extremo RTC  <br/> |Extremo PBX en un sitio diferente (es decir, sitio 2)  <br/> |No se permitirá la transferencia consultiva  <br/> |
|Extremo PBX en el mismo sitio (es decir, sitio 1)  <br/> |Extremo RTC  <br/> |Se permitirá la transferencia consultiva  <br/> |
|Extremo PBX en un sitio diferente (es decir, sitio 2)  <br/> |Extremo RTC  <br/> |No se permitirá la transferencia consultiva  <br/> |
|Extremo PBX en cualquier sitio  <br/> |Skype Empresarial usuario en el mismo sitio de red (es decir, sitio 1)  <br/> |Se permitirá la transferencia consultiva  <br/> |
|Extremo PBX en cualquier sitio  <br/> |Skype Empresarial usuario en diferentes sitios de red (es decir, sitio 2)  <br/> |Se permitirá la transferencia consultiva  <br/> |
|Extremo PBX en cualquier sitio  <br/> |Skype Empresarial usuario en un sitio de red desconocido  <br/> |Se permitirá la transferencia consultiva  <br/> |
|Extremo PBX en cualquier sitio  <br/> |Usuario Skype Empresarial federado  <br/> |Se permitirá la transferencia consultiva  <br/> |

## <a name="requirements"></a>Requirements

La aplicación Location-Based routing for Conferencing requiere que Skype Empresarial Server o Lync Server 2013 Cumulative Update 2 se implemente en todos los grupos de servidores de Front-End y servidores Standard Edition de la topología. Si estas versiones de servidor no están instaladas en algunos servidores de la topología, las restricciones de enrutamiento de Location-Based no se pueden aplicar por completo en reuniones y transferencias de llamadas consultiva.

En la tabla siguiente se identifica la combinación de roles de servidor y versiones que admiten Location-Based enrutamiento.


|Front-End versión del grupo de servidores|Versión del servidor de mediación|Compatible|
|:-----|:-----|:-----|
|Skype Empresarial Server o Lync Server 2013 Actualización acumulativa 2  <br/> |Skype Empresarial Server o Lync Server 2013 Actualización acumulativa 2  <br/> |Sí  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Actualización acumulativa 1 de Lync Server 2013  <br/> |No  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Lync Server 2010  <br/> |No  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |No  <br/> |
|Actualización acumulativa 1 de Lync Server 2013  <br/> |Cualquiera  <br/> |No  <br/> |
|Lync Server 2010  <br/> |Cualquiera  <br/> |No  <br/> |
|Office Communications Server 2007 R2  <br/> |Cualquiera  <br/> |No  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuración de Location-Based de enrutamiento para conferencias

La Location-Based de enrutamiento para conferencias se basa en la configuración de Location-Based enrutamiento. Las configuraciones principales son las siguientes:

- La ubicación de los participantes que se unen a una reunión se determina en función de su sitio de red. Un sitio de red y sus subredes de red asociadas deben definirse en Skype Empresarial Server para aplicar Location-Based enrutamiento.

- Para aplicar Location-Based enrutamiento de reuniones, Skype Empresarial los participantes deben estar habilitados para Location-Based enrutamiento.

- Para aplicar Location-Based enrutamiento de puntos de conexión RTC que se unen a reuniones, el tronco SIP usado para conectar los puntos de conexión RTC debe configurarse para Location-Based enrutamiento.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitar el Location-Based de enrutamiento para conferencias

La Location-Based de enrutamiento para conferencias está deshabilitada de forma predeterminada. Antes de habilitar esta aplicación, debe determinar la prioridad correcta para asignarla. Para determinar esta prioridad, ejecute el siguiente cmdlet en Skype Empresarial Server Shell de administración:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

En este cmdlet, \<Pool FQDN\> es el grupo en el que se va a habilitar la aplicación Location-Based enrutamiento de conferencia.

Este cmdlet devolverá la lista de las aplicaciones hospedadas por Skype Empresarial Server y el valor de prioridad para cada una de ellas. A la aplicación de enrutamiento de Location-Based para conferencias se le debe asignar un valor de prioridad mayor que la aplicación "UdcAgent" y menor que las aplicaciones "DefaultRouting", "ExumRouting" y "OutboundRouting". Se recomienda asignar a la aplicación Location-Based routing for Conferencing un valor de prioridad que sea un punto superior al valor de prioridad de la aplicación "UdcAgent".

Por ejemplo, si la aplicación "UdcAgent" tiene un valor de prioridad de "2", la aplicación "DefaultRouting" tiene un valor de prioridad de "8", la aplicación "ExumRouting" tiene un valor de prioridad de "9" y la aplicación "OutboundRouting" tiene un valor de prioridad de "10", entonces debe asignar a la aplicación de enrutamiento de Location-Based para conferencia un valor de prioridad de "3". Al hacerlo, se colocaría la prioridad de las aplicaciones en el orden siguiente: Otras aplicaciones (prioridades: 0 a 1), "UdcAgent" (prioridad: 2), aplicación de conferencia de enrutamiento de Location-Based (prioridad: 3), otras aplicaciones (prioridades: 4 a 8), "DefaultRouting" (prioridad: 9), "ExumRouting" (prioridad: 10) y "OutboundRouting" (prioridad: 11).

Después de encontrar el valor de prioridad correcto para la aplicación de enrutamiento de Location-Based para conferencias, escriba el siguiente cmdlet para cada grupo de Front-End o servidor Standard Edition que aloja usuarios habilitados para el enrutamiento Location-Based:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Por ejemplo:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Después de usar este cmdlet, reinicie todos los servidores front-end del grupo de servidores o los servidores Standard Edition donde se ha habilitado la aplicación Location-Based enrutamiento para conferencias.

> [!IMPORTANT]
> Location-Based no se aplicarán las directivas de enrutamiento a conferencias o transferencias consulttivas hasta que se reinicien todos los servidores front-end de los grupos de servidores aplicables o los servidores Standard Edition. Si establece **-Critical en** **$true** en los cmdlets anteriores, los servicios Skype Empresarial Server se reiniciarán inmediatamente. Si no desea que estos servicios se reinicien inmediatamente, establezca **-Critical** en **$false** por ahora y, a continuación, use **Set-CsServerApplication** para cambiar **-Critical** **a $true** más adelante, después de reiniciar los servicios.

Una vez que la aplicación Location-Based Routing for Conferencing se haya habilitado correctamente y se hayan reiniciado todos los servidores aplicables, se supervisarán todas las conferencias organizadas por usuarios de Skype Empresarial habilitados para el enrutamiento de Location-Based para evitar la omisión de peaje RTC



---
title: Enrutamiento basado en ubicación para conferencias en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Planeación del enrutamiento basado en ubicación para conferencias en Skype empresarial Server Enterprise Voice, incluidas las transferencias de llamadas Consultiva.
ms.openlocfilehash: cec7eb1f853752997ca3dcfbe8546b86227fde9b
ms.sourcegitcommit: d664ef6994e242bf18a29dac31286c78c163478a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2020
ms.locfileid: "44710744"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Enrutamiento basado en ubicación para conferencias en Skype empresarial Server

Planeación del enrutamiento basado en ubicación para conferencias en Skype empresarial Server Enterprise Voice, incluidas las transferencias de llamadas Consultiva.

El enrutamiento basado en ubicación permite restringir el enrutamiento de las llamadas entre los extremos de VoIP y los extremos de RTC en función de la ubicación de las partes en la llamada. El enrutamiento basado en ubicación para conferencias permite aplicar reglas de enrutamiento basadas en la ubicación en reuniones (es decir, conferencias) para evitar el desvío de llamadas RTC. La aplicación supervisa una conferencia activa y aplica las restricciones de enrutamiento basadas en la ubicación en función de la ubicación de los usuarios que participan. El enrutamiento basado en ubicación para la aplicación de conferencia también permite la aplicación de restricciones de enrutamiento basadas en ubicación a las transferencias de consulta que implican puntos de conexión RTC.

La aplicación de conferencia de enrutamiento basada en ubicación proporciona a las conferencias de Skype empresarial un mecanismo para prevenir la omisión de peajes RTC. La aplicación supervisa las conferencias activas y aplica las restricciones de enrutamiento basadas en la ubicación en función de la ubicación de los usuarios de Skype empresarial que participan.

La aplicación de conferencia de enrutamiento basada en ubicación determina si el enrutamiento basado en ubicación se debe aplicar en una reunión de Skype empresarial si se cumplen los siguientes criterios:

- El organizador de la reunión está habilitado para el enrutamiento basado en ubicación. Las restricciones de enrutamiento basadas en ubicación solo se aplicarán a las conferencias organizadas por usuarios que están habilitados para el enrutamiento basado en ubicación.

- Al menos un participante de la reunión es un punto de conexión RTC. Las restricciones de enrutamiento basadas en ubicación solo son aplicables a las conferencias que incluyen extremos de RTC.

- El sitio de red en el que se ubica la puerta de enlace RTC que se usa para salvar la Conferencia a la RTC se encuentra, así como los sitios de red desde donde se conectan los organizadores y participantes.

El enrutamiento basado en ubicación de la aplicación de conferencias evita la participación de los usuarios de Skype empresarial y los puntos de conexión de RTC de distintos sitios de red en la misma conferencia. Si el organizador de una reunión está habilitado para el enrutamiento basado en ubicación, la aplicación de conferencia exige las siguientes restricciones:

- Los puntos de conexión que se pueden unir a una reunión de Skype empresarial dependen de los puntos de conexión que ya se hayan unido a la Conferencia, y esta restricción se ajusta como extremos Unidos y los nuevos puntos de conexión se unen a la Conferencia. Si los organizadores y los participantes se unen a una reunión de Skype empresarial desde el mismo sitio de red, se permite unirse a otro participante de un sitio de red diferente o a un participante de un sitio de red desconocido desde el mismo sitio de red.

- Si los organizadores y participantes se unen a la reunión desde sitios de red diferentes o desconocidos, un extremo de RTC no puede unirse a la reunión si la llamada RTC se encuentra en un tronco SIP habilitado para el enrutamiento basado en ubicación.

- Si todos los organizadores y participantes se unen a la reunión desde el mismo sitio de red y hay participantes que se unen a la misma reunión desde la RTC, un extremo de Skype empresarial desde un sitio de red diferente no puede unirse a la reunión.

En la tabla siguiente se resumen las restricciones de enrutamiento basadas en la ubicación de las conferencias.

|Usuario (s) en una conferencia en un punto determinado|Usuarios que han permitido unirse a la Conferencia|Usuario (s) sin permiso para unirse a la Conferencia|
|:-----|:-----|:-----|
|Usuarios del cliente de VoIP de Skype empresarial desde un único sitio de red  <br/> |Usuario de cliente VoIP de Skype empresarial desde el mismo sitio de red  <br/> Usuario de cliente VoIP de Skype empresarial desde un sitio de red diferente  <br/> Usuario de cliente VoIP de Skype empresarial desde un sitio de red desconocido  <br/> Usuario del cliente VoIP de Skype empresarial federado  <br/> Unirse a un usuario desde un punto de conexión RTC  <br/> |None  <br/> |
|Usuarios del cliente de VoIP de Skype empresarial desde un sitio de red desconocido  <br/> |Usuario de cliente VoIP de Skype empresarial desde cualquier sitio  <br/> Usuario del cliente VoIP de Skype empresarial desde un sitio desconocido  <br/> Usuario del cliente VoIP de Skype empresarial federado  <br/> |Unión de usuarios a través de un punto de conexión RTC  <br/> |
|Usuarios de clientes de VoIP de Skype empresarial de diferentes sitios de red  <br/> |Usuario de cliente VoIP de Skype empresarial desde cualquier sitio de red  <br/> Usuario de cliente VoIP de Skype empresarial desde un sitio de red desconocido  <br/> Usuario del cliente VoIP de Skype empresarial federado  <br/> |Unión de usuarios a través de un punto de conexión RTC  <br/> |
|Usuarios del cliente de VoIP de Skype empresarial de un único sitio de red y usuarios que se unen desde un punto de conexión de RTC  <br/> |Usuario de cliente VoIP de Skype empresarial desde el mismo sitio de red  <br/> |Usuario de cliente VoIP de Skype empresarial desde un sitio de red diferente  <br/> Usuario de cliente VoIP de Skype empresarial desde un sitio de red desconocido  <br/> Usuario del cliente VoIP de Skype empresarial federado  <br/> |

Las siguientes son características adicionales de la ruta basada en ubicación para la aplicación de Conferencia:

- Cuando no se permite que un usuario se una a una conferencia con las restricciones de enrutamiento basadas en la ubicación, se rechazará la llamada a la Conferencia y el cliente de Skype empresarial informará de que la llamada no se completó o ha finalizado.

- Un punto de conexión RTC que se une a una conferencia con las fuerzas de enrutamiento basadas en ubicación no se verá restringido a unirse a la Conferencia independientemente de su estado si el punto de conexión se une a través de un tronco que no está habilitado para el enrutamiento basado en la ubicación.

- Un sistema PBX conectado a un servidor de mediación a través de un tronco SIP que no tenga salidas de salida a la RTC tendrá las mismas fuerzas que los usuarios de Skype empresarial que se encuentran en el mismo sitio de red en el que se define el tronco SIP. Por ejemplo, un extremo de RTC podrá unirse a una conferencia con un usuario de PBX y un usuario de Skype empresarial si están ubicados en el mismo sitio de red; de lo contrario, el punto de conexión de RTC no podrá unirse a la Conferencia si el usuario de PBX se encuentra en un sitio de red diferente que el usuario de Skype empresarial.

> [!NOTE]
> Con la actualización acumulativa 4 de Skype empresarial, debe cumplirse el comportamiento de la siguiente tabla:

|User|Otra parte|Action|Resultado|
|:-----|:-----|:-----|:-----|
|Skype empresarial Mobile  <br/> |RTC  <br/> |Skype empresarial Mobile está en una llamada RTC. Skype empresarial Mobile escala la llamada a un operador automático de conferencia (CAA).  <br/> |La llamada se bloquea, con un mensaje de error apropiado.  <br/> |
|Skype empresarial Mobile  <br/> |Cliente de Skype empresarial o usuario federado  <br/> |El cliente o el usuario federado está en una llamada de VoIP a un usuario de enrutamiento basado en ubicación móvil de Skype empresarial, y cualquiera de las partes escala a un CAA.  <br/> |La llamada de escalado se bloquea, con un mensaje de error apropiado.  <br/> |

## <a name="consultative-call-transfers"></a>Transferencias de llamadas de consultoría

Además de aplicar el enrutamiento basado en ubicación a las reuniones de Skype empresarial, el enrutamiento basado en ubicación de la aplicación de conferencias aplica restricciones de enrutamiento basadas en ubicación en las transferencias de llamadas de consulta que se transfieren a los extremos de RTC. Una transferencia de llamada Consultiva es una llamada establecida entre dos partes en la que una de las partes transfiere la llamada a un nuevo usuario. Por ejemplo, un punto de conexión RTC llama al usuario A (llamada de Skype empresarial). El usuario A determina el usuario de RTC que se debe reenviar al usuario B (Skype empresarial). El usuario A realiza la llamada con el usuario RTC en espera y llama al usuario B. el usuario B acuerda hablar con el usuario RTC. El usuario A transfiere la llamada en espera al usuario B.

**Flujo de llamada de transferencia de llamada Consultiva**

![Enrutamiento basado en ubicación para diagrama de conferencia](../../media/LocationBasedRoutingForConferencing.jpg)

Cuando un usuario habilitado para el enrutamiento basado en ubicación inicia una transferencia de llamada Consultiva de un extremo de RTC (tal como se muestra en la figura anterior), esto crea dos llamadas activas, una llamada entre el usuario de RTC y el usuario de Skype empresarial A, y la otra entre el usuario A de Skype empresarial A y el usuario B de Skype empresarial. el comportamiento basado en ubicación de la aplicación de conferencia se aplica a los siguientes comportamientos: :

- Si el enrutamiento de tronco SIP la llamada RTC tiene autorización para redirigir la llamada RTC al sitio de red en el que se encuentra el usuario B de Skype empresarial (por ejemplo, el destino de transferencia), se permitirá la transferencia de llamadas; de lo contrario, se bloqueará la transferencia de la llamada Consultiva. Esta autorización se realiza en función de la ubicación de la entidad transferida que se encuentra en el mismo sitio de red que el tronco SIP que enruta la llamada activa al punto de conexión de RTC.

- Si el enrutamiento de tronco SIP la llamada RTC entrante no está autorizada para enrutar llamadas al sitio de red donde se encuentra la entidad transferida (usuario de Skype empresarial B) o la entidad transferida se encuentra en un sitio de red desconocido, se bloqueará la transferencia de llamadas de consulta al punto de conexión de RTC (es decir, el destino de transferencia de llamadas).

En la tabla siguiente se describe cómo se aplican las restricciones de enrutamiento basada en ubicación para la aplicación de conferencia para las transferencias de llamadas de consultoría. Aunque los extremos de PBX no están directamente asociados a un sitio de red, el tronco SIP al que se conecta la PBX se puede asignar a un sitio de red. Por lo tanto, el extremo de PBX se puede asociar indirectamente con un sitio de red.


|Sitio de red de la persona que ha transferido la llamada|Sitio de red del destino de transferencia de llamadas|Comportamiento|
|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Usuario de Skype empresarial en el mismo sitio de red (por ejemplo, sitio 1)  <br/> |Se permitirá la transferencia Consultiva  <br/> |
|Extremo de RTC  <br/> |Usuario de Skype empresarial en diferentes sitios de red (por ejemplo, sitio 2)  <br/> |La transferencia Consultiva no se permitirá  <br/> |
|Extremo de RTC  <br/> |Usuario de Skype empresarial en un sitio de red desconocido  <br/> |La transferencia Consultiva no se permitirá  <br/> |
|Extremo de RTC  <br/> |Usuario federado de Skype empresarial  <br/> |La transferencia Consultiva no se permitirá  <br/> |
|Extremo de RTC  <br/> |Extremo de PBX en el mismo sitio (es decir, sitio 1)  <br/> |Se permitirá la transferencia Consultiva  <br/> |
|Extremo de RTC  <br/> |Extremo de PBX en sitios diferentes (por ejemplo, sitio 2)  <br/> |La transferencia Consultiva no se permitirá  <br/> |
|Extremo de PBX en el mismo sitio (es decir, sitio 1)  <br/> |Extremo de RTC  <br/> |Se permitirá la transferencia Consultiva  <br/> |
|Extremo de PBX en un sitio diferente (por ejemplo, sitio 2)  <br/> |Extremo de RTC  <br/> |La transferencia Consultiva no se permitirá  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario de Skype empresarial en el mismo sitio de red (por ejemplo, sitio 1)  <br/> |Se permitirá la transferencia Consultiva  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario de Skype empresarial en diferentes sitios de red (por ejemplo, sitio 2)  <br/> |Se permitirá la transferencia Consultiva  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario de Skype empresarial en un sitio de red desconocido  <br/> |Se permitirá la transferencia Consultiva  <br/> |
|Extremo de PBX en cualquier sitio  <br/> |Usuario federado de Skype empresarial  <br/> |Se permitirá la transferencia Consultiva  <br/> |

## <a name="requirements"></a>Requirements

El enrutamiento basado en ubicación para la aplicación de conferencia requiere que se implemente la actualización acumulativa 2 de Skype empresarial Server o Lync Server 2013 en todos los grupos de servidores front-end y servidores Standard Edition de la topología. Si estas versiones de servidor no están instaladas en algunos servidores de la topología, las restricciones de enrutamiento basadas en ubicación no se pueden aplicar completamente en las reuniones y las transferencias de llamadas de asesoría.

En la siguiente tabla se identifica la combinación de roles de servidor y versiones que admiten el enrutamiento basado en ubicación.


|Versión del grupo de servidores front-end|Versión del servidor de mediación|Compatible|
|:-----|:-----|:-----|
|Actualización acumulativa 2 de Skype empresarial Server o Lync Server 2013  <br/> |Actualización acumulativa 2 de Skype empresarial Server o Lync Server 2013  <br/> |Sí  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Actualización acumulativa 1 de Lync Server 2013  <br/> |No  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Lync Server 2010  <br/> |No  <br/> |
|Actualización acumulativa 2 de Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |No  <br/> |
|Actualización acumulativa 1 de Lync Server 2013  <br/> |Cualquiera  <br/> |No  <br/> |
|Lync Server 2010  <br/> |Cualquiera  <br/> |No  <br/> |
|Office Communications Server 2007 R2  <br/> |Cualquiera  <br/> |No  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuración del enrutamiento basado en ubicación para conferencias

El enrutamiento basado en ubicación de la aplicación de conferencia se basa en la configuración del enrutamiento basado en ubicación. Las configuraciones principales son las siguientes:

- La ubicación de los participantes que se unen a una reunión se determina en función de su sitio de red. Un sitio de red y sus subredes de red asociadas deben definirse en Skype empresarial Server para aplicar el enrutamiento basado en la ubicación.

- Para aplicar el enrutamiento basado en la ubicación de las reuniones, los participantes de Skype empresarial deben estar habilitados para el enrutamiento basado en ubicación.

- Para aplicar el enrutamiento basado en la ubicación de los extremos de RTC que se unen a las reuniones, el tronco SIP que se usa para conectar los extremos de RTC debe configurarse para el enrutamiento basado en ubicación.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitar el enrutamiento basado en ubicación para conferencias

El enrutamiento basado en ubicación para la aplicación de conferencia está deshabilitado de forma predeterminada. Antes de habilitar esta aplicación, debe determinar la prioridad correcta que se asignará a la aplicación. Para determinar esta prioridad, ejecute el siguiente cmdlet en el shell de administración de Skype empresarial Server:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

En este cmdlet, \<Pool FQDN\> es el grupo de servidores en el que se habilitará el enrutamiento basado en ubicación para la aplicación de conferencias.

Este cmdlet devolverá la lista de las aplicaciones hospedadas en Skype empresarial Server y el valor de prioridad de cada una de ellas. El enrutamiento basado en ubicación para la aplicación de conferencia debe tener asignado un valor de prioridad mayor que el de la aplicación "UdcAgent" y menor que el de las aplicaciones "DefaultRouting", "ExumRouting" y "OutboundRouting". Le recomendamos que asigne el enrutamiento basado en ubicación de la aplicación de conferencias, un valor de prioridad que sea un punto superior al valor de prioridad de la aplicación "UdcAgent".

Por ejemplo, si la aplicación "UdcAgent" tiene un valor de prioridad de "2", la aplicación "DefaultRouting" tiene un valor de prioridad de "8", la aplicación "ExumRouting" tiene un valor de prioridad de "9" y la aplicación "OutboundRouting" tiene un valor de prioridad de "10", debe asignar el enrutamiento basado en ubicación para la aplicación de conferencia con un valor de prioridad de Si lo hace, se colocará la prioridad de las aplicaciones en el siguiente orden: otras aplicaciones (prioridades: 0 a 1), "UdcAgent" (prioridad: 2), aplicación de conferencia de enrutamiento basada en ubicación (prioridad: 3), otras aplicaciones (prioridades: 4 a 8), "DefaultRouting" (prioridad: 9), "ExumRouting" (prioridad: 10) y "OutboundRouting" (prioridad: 11).

Una vez que haya encontrado el valor de prioridad correcto para la aplicación enrutamiento basado en ubicación para la aplicación de conferencia, escriba el siguiente cmdlet para cada grupo de servidores front-end o servidor Standard Edition que aloje a los usuarios habilitados para el enrutamiento basado en ubicación:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Por ejemplo:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Después de usar este cmdlet, reinicie todos los servidores front-end en el grupo o los servidores Standard Edition donde se haya habilitado el enrutamiento basado en ubicación para la aplicación de conferencias.

> [!IMPORTANT]
> Las fuerzas de enrutamiento basadas en ubicación para las conferencias o las transferencias de consulta no se aplicarán hasta que se reinicien todos los servidores front-end de los grupos de servidores correspondientes o los servidores Standard Edition. Si configura **-crítico** para **$true** en los cmdlets anteriores, los servicios de Skype empresarial Server se reiniciarán inmediatamente. Si no desea que estos servicios se reinicien inmediatamente, establezca **-crítico** para **$false** por ahora y, a continuación, use **set-CsServerApplication** para cambios **críticos** a **$true** posterior, una vez reiniciados los servicios.

Una vez que el enrutamiento basado en ubicación para la aplicación de conferencia se haya habilitado correctamente y se hayan reiniciado todos los servidores correspondientes, todas las conferencias organizadas por los usuarios de Skype empresarial habilitados para el enrutamiento basado en ubicación se supervisarán para evitar el desvío de llamadas RTC.



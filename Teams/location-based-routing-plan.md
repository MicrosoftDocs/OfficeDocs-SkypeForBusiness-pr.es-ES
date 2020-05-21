---
title: Planear enrutamiento basado en la ubicación para el enrutamiento directo
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Aprenda a planificar el enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f72360f4462a64e357d58489aa70203bf10c532
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326647"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planear enrutamiento basado en la ubicación para el enrutamiento directo

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview-of-location-based-routing"></a>Información general sobre el enrutamiento basado en la ubicación

En algunos países y regiones, no es ilegal eludir el proveedor de la red telefónica conmutada (RTC) para reducir los gastos de llamadas de larga distancia. Este artículo describe cómo usar el enrutamiento basado en la ubicación para restringir el omisión de pago para los usuarios de Microsoft Teams en función de su ubicación geográfica. Este artículo se aplica únicamente al enrutamiento de un sistema telefónico directo.

Aquí se ofrece información general sobre el enrutamiento basado en la ubicación y la orientación para ayudarle a planificarlo. Cuando esté listo para aplicar y habilitar el enrutamiento basado en la ubicación, consulte:
- [Implementar la configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)

El enrutamiento basado en la ubicación es una característica que le permite restringir la omisión de pago en función de la Directiva y la ubicación geográfica del usuario en el momento de una llamada RTC entrante o saliente. 

Cuando un usuario de Teams está habilitado para el enrutamiento basado en la ubicación, se aplican las siguientes acciones:
- Para hacer una llamada RTC saliente, una de las siguientes condiciones debe cumplirse:
    - El extremo del usuario se encuentra en un sitio de red que está habilitado para el enrutamiento basado en la ubicación y las llamadas salida a través de la puerta de enlace correspondiente que está habilitada para el enrutamiento basado en la ubicación. 
    - El punto final del usuario se encuentra en un sitio de red que no está habilitado para el enrutamiento basado en la ubicación y las llamadas salida a través de una puerta de enlace que no está habilitada para el enrutamiento basado en la ubicación.

    No se permiten llamadas salientes en ningún otro escenario.

- Para recibir una llamada RTC entrante, el punto final de respuesta del usuario debe encontrarse en el mismo sitio de red donde se encuentra la llamada a través de la puerta de enlace que está habilitada para el enrutamiento basado en la ubicación. En cualquier otro escenario, como si el usuario está en itinerancia, la llamada no está permitida y se enruta a la configuración del desvío de llamadas del usuario (normalmente, el buzón de voz).
- Para transferir una llamada RTC a otro usuario de Teams, el extremo del usuario de destino debe estar ubicado en el mismo sitio de red que el usuario que inicia la transferencia. No se permiten las transferencias en ningún otro escenario. 
- Para transferir otro usuario de Teams a la RTC, la llamada debe transferirse a través de una puerta de enlace habilitada para enrutamiento basado en la ubicación que se encuentra en el mismo sitio de red que la persona que llama. No se permiten las transferencias en ningún otro escenario.

El enrutamiento basado en la ubicación usa la misma definición de región de red, sitio y subred que usa Skype empresarial Server. Cuando se restringe la omisión de peaje en una ubicación, un administrador asocia cada subred IP y cada puerta de enlace RTC de esa ubicación a un sitio de red. La ubicación de un usuario está determinada por la subred IP a la que están conectados los puntos de conexión de los equipos del usuario en el momento de una llamada RTC. Un usuario puede tener varios clientes de Teams ubicados en diferentes sitios, en cuyo caso el enrutamiento basado en la ubicación aplica el enrutamiento de cada cliente por separado, en función de la ubicación de su punto de conexión. 

Para familiarizarse con algunos de los términos de la red que se usan en este artículo, consulte [configuración de red para características de voz en la nube en Teams](cloud-voice-network-settings.md).

## <a name="apply-location-based-routing"></a>Aplicar enrutamiento basado en la ubicación

Debe aplicar enrutamiento basado en la ubicación a los usuarios, los sitios de red y las puertas de enlace RTC.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar enrutamiento basado en la ubicación en la ubicación del usuario

Como se mencionó anteriormente, el enrutamiento basado en la ubicación solo se aplica a los usuarios que están configurados para el enrutamiento directo. El enrutamiento basado en la ubicación no se aplica a los usuarios que están configurados para el plan de llamadas. Los usuarios deben estar habilitados para el enrutamiento basado en la ubicación si se encuentran en restricción de omisión de pago, que controla las condiciones en las que puede hacer y recibir llamadas RTC y la puerta de enlace PSTN que se puede usar. Cuando un usuario que está habilitado para el enrutamiento basado en la ubicación se encuentra en un sitio habilitado para el enrutamiento basado en la ubicación, el usuario debe hacer llamadas a través de una puerta de enlace habilitada para enrutamiento basado en la ubicación conectada al sitio. 

El enrutamiento basado en la ubicación funciona determinando la ubicación actual del usuario en función de la dirección IP del punto de conexión de equipo del usuario y aplica las reglas según corresponda. La ubicación de un usuario que está habilitado para el enrutamiento basado en la ubicación se puede clasificar de la siguiente manera: 
- **El usuario se encuentra en el mismo sitio habilitado para enrutamiento basado en la ubicación que se asocia a la puerta de enlace RTC donde se les asignó su acción.**<br>En este escenario, el usuario se encuentra en un sitio de red conocido que está habilitado para el enrutamiento basado en la ubicación y el número de marcado directo directo del usuario (hecho) termina en una puerta de enlace RTC que está en el mismo sitio de red. Por ejemplo, el usuario está en su oficina. 
- **El usuario se encuentra en un sitio habilitado para enrutamiento basado en la ubicación que no está asociado a la puerta de enlace RTC donde se le asignó su acción.**<br>En este escenario, el usuario se encuentra en un sitio de red conocido que está habilitado para el enrutamiento basado en la ubicación, y ese sitio no está asociado a la puerta de enlace PSTN donde se ha asignado el número de la persona que tenía el usuario. Por ejemplo, el usuario viaja a otra oficina.  
- **El usuario se encuentra en un sitio interno que no está habilitado para el enrutamiento basado en la ubicación.** <br>En este escenario, el usuario se encuentra en un sitio de red interna conocido que no está habilitado para el enrutamiento basado en la ubicación. 
- **El usuario se encuentra en un sitio desconocido.** 
    - El usuario se encuentra dentro de la red interna que no está definida como un sitio de red. 
    - El usuario se encuentra fuera de la red interna. Por ejemplo, el usuario está en Internet en casa o en una cafetería. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar enrutamiento basado en la ubicación en el sitio de red 
Los sitios de red deben estar habilitados para el enrutamiento basado en la ubicación con el fin de determinar qué puertas de enlace pueden enrutar a los usuarios con enrutamiento basado en la ubicación al roaming. Si un usuario que está habilitado para el enrutamiento basado en la ubicación se mueve a un sitio que está habilitado para el enrutamiento basado en la ubicación, solo se puede usar la puerta de enlace PSTN habilitada para el enrutamiento basado en la ubicación en ese sitio para las llamadas salientes. Si un usuario que está habilitado para el enrutamiento basado en la ubicación se mueve a un sitio que no está habilitado para el enrutamiento basado en la ubicación, cualquier puerta de enlace que no esté habilitada para el enrutamiento basado en la ubicación se puede usar para las llamadas salientes.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar enrutamiento basado en la ubicación en la puerta de enlace RTC 

Las puertas de enlace se asocian a sitios para determinar dónde se puede ubicar un usuario que está habilitado para el enrutamiento basado en la ubicación cuando realiza o recibe una llamada RTC. Las puertas de enlace deben estar habilitadas para el enrutamiento basado en la ubicación para garantizar que está bajo restricciones de omisión de pago y que los usuarios que no están habilitados para el enrutamiento basado en la ubicación no pueden usarlas. La misma puerta de enlace puede estar asociada a varios sitios y se puede configurar para que se habilite para el enrutamiento basado en la ubicación o no se habilite para el enrutamiento basado en la ubicación, en función del sitio.

## <a name="scenarios-for-location-based-routing"></a>Escenarios para el enrutamiento basado en ubicación

En esta sección se describen diferentes escenarios para restringir el omisión de pago mediante el enrutamiento basado en la ubicación y se compara cómo se enrutan las llamadas de los usuarios que no tienen habilitado el enrutamiento basado en la ubicación con los usuarios que están habilitados para el enrutamiento basado en la ubicación.

- [El usuario de Teams realiza una llamada saliente a la RTC](#teams-user-places-an-outbound-call-to-the-pstn)
- [El usuario de Teams recibe una llamada entrante de la RTC](#teams-user-receives-an-inbound-call-from-the-pstn)
- [El usuario de Teams transfiere o reenvía una llamada a otro usuario de Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [El usuario de Teams transfiere o reenvía una llamada a un extremo RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Tono de llamada simultáneo](#simultaneous-ringing)
- [Delegación](#delegation)

En el diagrama siguiente se muestran las restricciones habilitadas por el enrutamiento basado en la ubicación en cada escenario. Los usuarios, los sitios de red y las puertas de enlace habilitadas para el enrutamiento basado en la ubicación tienen un borde a su lado. Use el diagrama como guía para comprender cómo funciona el enrutamiento basado en la ubicación en cada escenario.  

![Diagrama que muestra escenarios de enrutamiento basado en la ubicación](media/lbr-direct-routing.png "Diagrama que muestra escenarios de enrutamiento basado en la ubicación")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>El usuario de Teams realiza una llamada saliente a la RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>El usuario no está habilitado para el enrutamiento basado en la ubicación

Un usuario que no está habilitado para el enrutamiento basado en la ubicación puede hacer llamadas salientes usando cualquier puerta de enlace en cualquier sitio que no esté habilitado para el enrutamiento basado en la ubicación a través de la Directiva de enrutamiento de voz asignada. Sin embargo, si una puerta de enlace está habilitada para el enrutamiento basado en la ubicación, el usuario no puede hacer llamadas salientes a través de la puerta de enlace aunque esté asignada a su Directiva de enrutamiento de voz. Si el usuario se desplaza a un sitio que está habilitado para el enrutamiento basado en la ubicación, solo puede hacer llamadas a través de las puertas de enlace de enrutamiento normal que no están habilitadas para el enrutamiento basado en la ubicación.
 
#### <a name="user-enabled-for-location-based-routing"></a>Habilitado por el usuario para el enrutamiento basado en la ubicación
En comparación, el enrutamiento de llamadas salientes para los usuarios que están habilitados para el enrutamiento basado en la ubicación se ve afectado por la ubicación de red del extremo del usuario. En la tabla siguiente se muestra cómo afecta el enrutamiento basado en la ubicación al enrutamiento de las llamadas salientes de user1, según la ubicación de Usuario1. 

|Ubicación del extremo del Usuario1  |Enrutamiento de llamadas salientes para Usuario1  |
|---------|---------|
|El mismo sitio donde se asignó el usuario, sitio habilitado para enrutamiento basado en la ubicación (Sitio1)      |Llamada enrutada a través de la puerta de enlace habilitada para enrutamiento basado en la ubicación (GW1) en Sitio1, en función de la Directiva de enrutamiento de voz del usuario.         |
|Sitio distinto del lugar donde se asignó el usuario, sitio habilitado para enrutamiento basado en la ubicación (Site2)    |Llamada enrutada a través de la puerta de enlace habilitada para enrutamiento basado en la ubicación (GW2) en el Site2 de itinerancia, basado en la Directiva de enrutamiento de voz del usuario.        |
|Sitio distinto del lugar donde se asignó el usuario, sitio no habilitado para enrutamiento basado en la ubicación (Site3)  |Llamada enrutada a través de la puerta de enlace que no está habilitada para el enrutamiento basado en la ubicación en el sitio que no está habilitado para enrutamiento basado en la ubicación (GW3), en función de la Directiva de enrutamiento de voz del usuario       |
|Red interna desconocida (Location4)    |  No se permiten las llamadas RTC       |
|Red externa desconocida (Location5)    | No se permiten las llamadas RTC        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>El usuario de Teams recibe una llamada entrante de la RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>El usuario no está habilitado para el enrutamiento basado en la ubicación

Un usuario que no está habilitado para el enrutamiento basado en la ubicación puede recibir una llamada entrante de la puerta de enlace que no está habilitada para el enrutamiento basado en la ubicación desde el que se han asignado sus números. Si el usuario se desplaza a un sitio que no está habilitado para el enrutamiento basado en la ubicación, aún podrá recibir llamadas a través de las puertas de enlace RTC normales.
  
#### <a name="user-enabled-for-location-based-routing"></a>Habilitado por el usuario para el enrutamiento basado en la ubicación

En comparación, los usuarios habilitados para el enrutamiento basado en la ubicación solo pueden recibir llamadas entrantes de la puerta de enlace RTC a la que se les haya asignado cuando se encuentren en el mismo sitio. En la tabla siguiente se muestra cómo el usuario1 recibe llamadas entrantes cuando el usuario1 se mueve a ubicaciones de red diferentes. Si la llamada no se dirige al punto final del usuario, se dirige a la configuración de desvío de llamadas del usuario, si la configuración está configurada. Normalmente, este es el buzón de voz.  

|Ubicación del extremo del Usuario1  |Enrutamiento de llamadas entrantes a usuario1  |
|---------|---------|
|El mismo sitio que la persona con la que se asignó el usuario, sitio habilitado para enrutamiento basado en la ubicación (Sitio1)   | Llamadas dirigidas al extremo de Usuario1 en Sitio1        |
|Sitio distinto del lugar donde se asignó el usuario, sitio habilitado para enrutamiento basado en la ubicación (Site2)    | Llamadas no dirigidas a puntos de conexión en Site2        |
|Sitio distinto del lugar donde se asignó el usuario, sitio no habilitado para enrutamiento basado en la ubicación (Site3)    | Llamadas no dirigidas a puntos de conexión en Site3        |
|Red interna desconocida (Location4)   | Llamadas no dirigidas a puntos de conexión en Location4        |
|Red externa desconocida (Location5)     | Llamadas no dirigidas a puntos de conexión en Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>El usuario de Teams transfiere o reenvía una llamada a otro usuario de Teams

Cuando se trata de un punto final de RTC, el enrutamiento basado en la ubicación analiza si uno o ambos usuarios están habilitados para el enrutamiento basado en la ubicación y determina si la llamada se debe transferir o desviar en función de la ubicación de ambos puntos de conexión. 
 
La transferencia de llamadas requiere que el usuario que inicia la llamada atienda la llamada mientras el desvío de llamadas no requiere que se responda la llamada inicial. Esto significa que las llamadas se pueden desviar incluso si User1 no está en una ubicación para recibir llamadas entrantes (consulte la tabla en el equipo que el [usuario recibe una llamada entrante de la sección RTC](#teams-user-receives-an-inbound-call-from-the-pstn) ) y no se pueden transferir las llamadas si User1 no puede recibir la llamada entrante. 

#### <a name="user-not-enabled-for-location-based-routing"></a>El usuario no está habilitado para el enrutamiento basado en la ubicación

Un usuario que no está habilitado para el enrutamiento basado en la ubicación puede transferir o desviar llamadas RTC a otros usuarios que no tengan habilitado el enrutamiento basado en la ubicación. Por lo general, el usuario no podrá transferir ni reenviar una llamada RTC a un usuario que tenga habilitado el enrutamiento basado en la ubicación porque los usuarios con enrutamiento basado en ubicación generalmente solo se pueden ubicar en las puertas de enlace de enrutamiento basadas en la ubicación para las llamadas RTC. La excepción es cuando un usuario habilitado para enrutamiento basado en la ubicación se desplaza a un sitio que no está habilitado para el enrutamiento basado en la ubicación. En este escenario, la llamada transferida está permitida.  

Del mismo modo, un usuario que no está habilitado para el enrutamiento basado en la ubicación solo puede recibir una llamada RTC de transferencia o de reenvío de otro usuario que no está habilitado para el enrutamiento basado en la ubicación. 

#### <a name="user-enabled-for-location-based-routing"></a>Habilitado por el usuario para el enrutamiento basado en la ubicación

Generalmente, la transferencia y el reenvío de llamadas RTC entrantes desde una puerta de enlace que está habilitada para el enrutamiento basado en la ubicación solo se permite si el usuario de destino está habilitado para el enrutamiento basado en la ubicación y se encuentra en el mismo sitio. De lo contrario, no se permite la transferencia y el reenvío de llamadas. 

En la tabla siguiente se muestra si se permiten el desvío de llamadas y las transferencias de llamadas, en función de la ubicación del usuario de destino. En esta tabla, usuario1, que se encuentra en Sitio1, inicia la transferencia o el reenvío a otros usuarios de teams que también están habilitados para el enrutamiento basado en la ubicación y que se encuentran en ubicaciones diferentes.  

|Ubicación de extremo de usuario de destino|Usuario1 inicia la transferencia de llamadas |Usuario1 inicia la llamada en adelante|
|---------|---------|---------|
|Mismo sitio de red que el iniciador (usuario2)|Tienen|Tienen|
|Sitio de red diferente, sitio habilitado para enrutamiento basado en la ubicación (Usuario3)|No se permiten|No se permiten|
|Sitio de red diferente, sitio no habilitado para enrutamiento basado en la ubicación (User4)|No se permiten|No se permiten|
|Red interna desconocida (User5)| No se permiten|No se permiten|
|Red externa desconocida (User6)| No se permiten|No se permiten|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>El usuario de Teams transfiere o reenvía una llamada a un extremo RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>El usuario no está habilitado para el enrutamiento basado en la ubicación

- Se permite transferir y reenviar una llamada RTC a otro número de RTC. 
- Transferir y reenviar una llamada de VOIP entrante a la RTC debe cumplir con las restricciones de omisión de peaje de la persona que llama. 
    - Si el autor de la llamada no está habilitado para el enrutamiento basado en la ubicación, se puede transferir a cualquier puerta de enlace RTC que no esté habilitada para el enrutamiento basado en la ubicación.
    - Si la persona que llama está habilitada para el enrutamiento basado en la ubicación, solo se puede transferir a una puerta de enlace habilitada para enrutamiento basado en la ubicación en el mismo sitio de red. 

#### <a name="user-enabled-for-location-based-routing"></a>Habilitado por el usuario para el enrutamiento basado en la ubicación

- Transferencia y reenvío de entrada una llamada RTC se debe enrutar fuera de la misma puerta de enlace habilitada para enrutamiento basado en la ubicación en la que llegó la llamada entrante. 
- Al transferir y reenviar una llamada de VOIP entrante a la RTC, debe respetar las restricciones de omisión de peaje del usuario. 
    - Si el autor de la llamada no está habilitado para el enrutamiento basado en la ubicación, se puede transferir a cualquier puerta de enlace RTC que no esté habilitada para el enrutamiento basado en la ubicación.
    - Si la persona que llama está habilitada para el enrutamiento basado en la ubicación, solo se puede transferir a una puerta de enlace habilitada para enrutamiento basado en la ubicación en el mismo sitio de red.
 
En la tabla siguiente se muestra cómo el enrutamiento basado en la ubicación afecta al enrutamiento de una llamada de VOIP de user1 al Sitio1 a los usuarios de ubicaciones distintas que transfieren o desvían la llamada a un punto final de RTC.  

|El usuario está iniciando la transferencia de llamadas o el reenvío  |Transferir a RTC  |Reenviar a RTC  |
|---------|---------|---------|
|Mismo sitio de red, sitio habilitado para enrutamiento basado en la ubicación (usuario2)   |La transferencia de llamadas solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz User2's         |El desvío de llamadas solo se puede enrutar a través de Gateway1 habilitado para enrutamiento basado en la ubicación en Sitio1, en función de la Directiva de enrutamiento de voz User2's         |
|Sitio de red diferente, sitio habilitado para enrutamiento basado en la ubicación (Usuario3)    |La transferencia de llamadas solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz User3's         |El desvío de llamadas solo se puede enrutar a través de Gateway1 habilitado para enrutamiento basado en la ubicación en Sitio1, en función de la Directiva de enrutamiento de voz User3's         |
|Sitio de red diferente, sitio no habilitado para enrutamiento basado en la ubicación (User4)    |La transferencia de llamadas solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz User4's         |El desvío de llamadas solo se puede enrutar a través de Gateway1 habilitado para enrutamiento basado en la ubicación en Sitio1, en función de la Directiva de enrutamiento de voz User4's         |
|Red interna desconocida (User5)     |La transferencia de llamadas solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz User5's         |El desvío de llamadas solo se puede enrutar a través de Gateway1 habilitado para enrutamiento basado en la ubicación en Sitio1, en función de la Directiva de enrutamiento de voz User5's         |
|Red externa desconocida (User6)   |La transferencia de llamadas solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz User6's        |El desvío de llamadas solo se puede enrutar a través de Gateway1 habilitado para enrutamiento basado en la ubicación en Sitio1, en función de la Directiva de enrutamiento de voz User6's         |

### <a name="simultaneous-ringing"></a>Tono de llamada simultáneo

Cuando un usuario que está habilitado para el enrutamiento basado en la ubicación recibe una llamada y tiene habilitado el timbre simultáneo, el enrutamiento basado en la ubicación analiza la ubicación de la persona que llama y los puntos finales de las partes a las que se llama para determinar si se debe enrutar la llamada. Los timbres simultáneos siguen las mismas reglas basadas en la ubicación que las transferencias de llamadas y los reenvíos. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Llamadas simultáneas a otro usuario de Teams

En la tabla siguiente se muestra si el enrutamiento basado en la ubicación permite llamadas simultáneas a diferentes usuarios para una llamada RTC entrante para Usuario1.

|Ubicación de extremo de usuario de destino|Llamadas simultáneas  |
|---------|---------|
|Mismo sitio de red que el iniciador (usuario2)   |Tienen         |
|Sitio de red móvil diferente habilitado para el enrutamiento basado en la ubicación (Usuario3)   |No se permiten         |
|Sitio de red móvil no habilitado para enrutamiento basado en la ubicación (User4)   |No se permiten        |
|Red interna desconocida (User5)    | No se permiten        |
|Red externa desconocida (User6)    |No se permiten        |
|El usuario de destino es un número RTC    |La llamada solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz de Usuario1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Llamadas simultáneas a un punto final de RTC

En la tabla siguiente se muestra el comportamiento de enrutamiento basado en la ubicación de una llamada de VOIP entrante de Usuario1 que se encuentra en el Sitio1 para los usuarios en diferentes ubicaciones con el establecimiento simultáneo de llamadas a un número de RTC. 

|Llamada ubicación de punto final de usuario  |El objetivo de llamada simultánea es un punto final de RTC |
|---------|---------|
|Mismo sitio de red, sitio habilitado para enrutamiento basado en la ubicación (usuario2)    |La llamada solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz User2's       |
|Sitio de red diferente habilitado para enrutamiento basado en la ubicación (Usuario3)    |La llamada solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz User3's        |
|Sitio de red diferente no habilitado para enrutamiento basado en la ubicación (User4)    |La llamada solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz User4's         |
|Red interna desconocida (User5)    |La llamada solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz User5's         |
|Red externa desconocida (User6)   |La llamada solo se puede enrutar mediante el enrutamiento basado en la ubicación Gateway1 en Sitio1, en función de la Directiva de enrutamiento de voz User6's         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Llamadas entrantes a través de la aplicación de voz (operador automático o cola de llamadas)

Las llamadas RTC entrantes de una puerta de enlace con enrutamiento basado en la ubicación pueden conectarse a un operador automático o a una cola de llamadas. Los usuarios habilitados para el enrutamiento basado en la ubicación solo pueden recibir transferencias de llamadas entrantes de estas aplicaciones cuando se encuentran en el mismo sitio desde el que se origina la llamada RTC de entrada. 
 
Se permite el desvío de llamadas y las llamadas simultáneas a usuarios y a PSTN para las transferencias de la aplicación de voz. Completar la llamada al destino está sujeto a las mismas reglas de enrutamiento basadas en la ubicación que se indican anteriormente.  
 
También se permite el reenvío al buzón de voz.  

### <a name="delegation"></a>Delegación

Un usuario de Teams puede elegir delegados que pueden hacer y recibir llamadas en su nombre. La capacidad de delegación de Teams se ve afectada por el enrutamiento basado en la ubicación de la siguiente manera: 
- Para las llamadas salientes desde un delegado habilitado para enrutamiento basado en la ubicación en nombre de un delegador, se aplican las mismas reglas. El enrutamiento de llamadas se basa en la Directiva de autorización de llamadas del delegado, la Directiva de enrutamiento de voz y la ubicación. Para obtener más información, vea [el usuario de Teams coloca una llamada saliente a la RTC](#teams-user-places-an-outbound-call-to-the-pstn). 
- Para las llamadas RTC entrantes a un delegador, las mismas reglas de enrutamiento basadas en la ubicación que se aplican al desvío de llamadas o a llamadas simultáneas a otros usuarios también se aplican a delegados. Para obtener más información, vea las [transferencias de usuarios de Teams o reenvían una llamada a otro usuario](#teams-user-transfers-or-forwards-call-to-another-teams-user) [de Teams](#teams-user-transfers-or-forwards-call-to-pstn-endpoint); [Simultaneous ringing](#simultaneous-ringing) Cuando un delegado establece un punto final de la RTC como un destino de llamada simultánea, se usa la Directiva de enrutamiento de voz del delegado para enrutar la llamada a la RTC. 
- Para la delegación, se recomienda que el delegador y los delegados asociados se encuentren en el mismo sitio de red. 

## <a name="other-planning-considerations"></a>Otras consideraciones de planificación

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Cambios de una implementación de enrutamiento basada en una ubicación local

Ya no se usa la Directiva de enrutamiento de voz del sitio de red. En su lugar, usamos la Directiva de enrutamiento de voz del usuario. Esto significa que, para permitir que los usuarios puedan desplazarse a otros sitios, la Directiva de enrutamiento de voz debe incluir las puertas de enlace de los sitios móviles. 

### <a name="technical-considerations-for-location-based-routing"></a>Consideraciones técnicas para el enrutamiento basado en ubicación

Las subredes IPv4 e IPv6 son compatibles, pero IPv6 tiene prioridad al buscar una coincidencia.

### <a name="client-support-for-location-based-routing"></a>Compatibilidad del cliente con el enrutamiento basado en la ubicación

Se admiten los siguientes clientes de Teams:
- Clientes de escritorio de Teams (Windows y Mac)
- Equipos clientes móviles (iOS y Android)
- Teléfonos IP de Teams

No se admiten los clientes Web de Teams y de Skype empresarial.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Capacidades no compatibles con el enrutamiento basado en ubicación

El enrutamiento basado en la ubicación no se aplica a los siguientes tipos de interacciones. El enrutamiento basado en la ubicación no se aplica cuando los puntos de conexión de Teams interactúan con los puntos de conexión RTC en los siguientes escenarios: 
- Estacionamiento o recuperación de llamadas RTC a través del estacionamiento de llamadas 
- Un usuario local de Skype empresarial o un usuario de Skype empresarial online llama a un usuario de Teams  

### <a name="location-based-routing-for-conferencing"></a>Enrutamiento basado en la ubicación para conferencias

Un usuario con capacidad de enrutamiento basado en la ubicación en una llamada RTC no puede iniciar una conferencia con otro usuario o número RTC. Se permite la conexión a los operadores automáticos o a las colas de llamadas. Si el usuario tiene una licencia de conferencia, el usuario debe iniciar una conferencia con los usuarios correspondientes y llamar a la RTC a través del puente de conferencia para iniciar una llamada de conferencia.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito de omisión de medios para enrutamiento basado en la ubicación

Si implementas el enrutamiento basado en la ubicación en India, también es necesario configurar la omisión de medios. Para obtener más información, vea [planear la omisión de multimedia con el enrutamiento directo](direct-routing-plan-media-bypass.md) y la [optimización de medios locales para el enrutamiento directo](direct-routing-media-optimization.md).

## <a name="next-steps"></a>Pasos siguientes

Vaya a [configurar la configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md).

## <a name="related-topics"></a>Temas relacionados

- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
- [Configuración de red de las características de voz en la nube en Teams](cloud-voice-network-settings.md)

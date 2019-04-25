---
title: Planear enrutamiento basado en la ubicación para el enrutamiento directo
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: roykuntz
search.appverid: MET150
description: Obtenga información sobre cómo planear el enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: b91eb877da7d18b41fdb21acbb7ade018a2c97b5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32246147"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planear enrutamiento basado en la ubicación para el enrutamiento directo

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview-of-location-based-routing"></a>Información general de enrutamiento basado en la ubicación

En algunos países y regiones, no es válido para omitir el proveedor público red de telefónica conmutada (RTC) para reducir los costos de llamada de larga distancia. Este artículo describe cómo usar el enrutamiento basado en la ubicación para restringir el desvío de teléfono de pago para los usuarios de Microsoft Teams en función de su ubicación geográfica. En este artículo se aplica únicamente a enrutamiento directo de teléfono del sistema.

Aquí podrá obtener una visión general de enrutamiento basados en ubicación e instrucciones que le ayudarán a planear para él. Cuando esté listo para aplicar y habilitar el enrutamiento basado en la ubicación, consulte:
- [Implementar la configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)

Enrutamiento basado en la ubicación es una característica que le permite restringir el desvío de pago en función de directiva y la ubicación geográfica del usuario en el momento de una llamada entrante o saliente de RTC. 

Cuando un usuario de los equipos está habilitado para enrutamiento basados en ubicación, se aplica lo siguiente:
- Para realizar una llamada saliente de RTC, debe cumplirse una de las siguientes opciones:
    - Extremo del usuario se encuentra en un sitio de red que está habilitado para la salida de llamadas y enrutamiento basados en ubicación a través de la puerta de enlace correspondiente que está habilitado para enrutamiento basado en la ubicación. 
    - Extremo del usuario se encuentra en un sitio de red que no está habilitado para enrutamiento basado en la ubicación y las llamadas de salida a través de una puerta de enlace que no está habilitado para enrutamiento basado en la ubicación.

    Las llamadas salientes no están permitidas en cualquier otro escenario.

- Para recibir una llamada entrante de RTC, extremo contestador automático del usuario debe estar ubicada en el mismo sitio de red donde la ingresses de llamada a través de la puerta de enlace que está habilitado para enrutamiento basado en la ubicación. En cualquier otro escenario, por ejemplo, si el usuario es móvil, la llamada no está permitida y se enruta a la llamada del usuario (normalmente, correo de voz) de la configuración de transferencia.
- Para transferir una llamada de RTC a otro usuario de los equipos, el destino de extremo del usuario debe estar ubicada en el mismo sitio de red como el usuario que inicia a la transferencia. Las transferencias no están permitidas en cualquier otro escenario. 
- Para transferir el otro usuario de los equipos a la RTC, la llamada debe transferirse a través de una puerta de enlace de enrutamiento basados en ubicación habilitado para que se encuentra en el mismo sitio de red que el autor de la llamada inicial. Las transferencias no están permitidas en cualquier otro escenario.

Enrutamiento basado en ubicación usa la misma subred, sitio y región definiciones de red que usa Skype para Business Server. Cuando el desvío de pago está restringido para una ubicación, un administrador asocia cada subred IP y cada puerta de enlace de RTC para esa ubicación a un sitio de red. Ubicación de un usuario está determinada por la subred IP a la que están conectados los extremos de los equipos del usuario a en el momento de una llamada de RTC. Un usuario puede tener varios clientes de los equipos ubicados en diferentes sitios, en cuyo caso enrutamiento basados en ubicación exige cada cliente enrutamiento por separado según la ubicación de su extremo. 

Para familiarizarse con la parte de la terminología de red que se usa en este artículo, consulte [terminología de enrutamiento basado en la ubicación](location-based-routing-terminology.md).

## <a name="apply-location-based-routing"></a>Aplicar el enrutamiento basado en la ubicación

Enrutamiento basado en la ubicación se debe aplicar a los usuarios, sitios de red y puertas de enlace RTC.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar el enrutamiento basado en la ubicación en la ubicación del usuario

Como se mencionó anteriormente, enrutamiento basado en la ubicación sólo se aplica a los usuarios que estén configurados para el enrutamiento directo. Enrutamiento basado en la ubicación no se aplica a los usuarios que estén configurados para la planeación de la llamada. Los usuarios deben habilitarse para enrutamiento basado en la ubicación si se encuentran en la restricción de desvío de pago, que controla las condiciones en las que pueden realizar y recibir llamadas de RTC y la puerta de enlace de RTC que se puede usar. Cuando un usuario habilitado para enrutamiento basados en ubicación está ubicado en un sitio que se ha habilitado para enrutamiento basado en la ubicación, el usuario debe realizar llamadas a través de una puerta de enlace de enrutamiento basados en ubicación habilitado conectado al sitio. 

Enrutamiento basado en ubicación funciona mediante la determinación de la ubicación del usuario actual en función de la dirección IP del extremo de los equipos del usuario y aplica las reglas según corresponda. La ubicación de un usuario habilitado para enrutamiento basados en ubicación se puede clasificar en las siguientes maneras: 
- **El usuario se encuentra en el mismo sitio basados en ubicación enrutamiento habilitado asociado a la puerta de enlace de RTC que se ha asignado su DID.**<br>En este escenario, el usuario se encuentra en un sitio de red conocidos que está habilitado para enrutamiento basado en la ubicación y directa DID del usuario (llamada) número termina en una puerta de enlace de RTC que se encuentra en el mismo sitio de red. Por ejemplo, el usuario está en su oficina. 
- **El usuario se encuentra en un sitio de enrutamiento basados en ubicación habilitado diferente no está asociado a la puerta de enlace RTC que se ha asignado su DID.**<br>En este escenario, el usuario se encuentra en un sitio de red conocidos que está habilitado para enrutamiento basado en la ubicación y ese sitio no está asociado con la puerta de enlace de RTC que se asigna un número DID del usuario. Por ejemplo, el usuario se desplaza a otra oficina.  
- **El usuario se encuentra en un sitio interno que no está habilitado para enrutamiento basado en la ubicación.** <br>En este escenario, el usuario se encuentra en un sitio de red interna conocidos que no está habilitado para enrutamiento basado en la ubicación. 
- **El usuario se encuentra en un sitio desconocido.** 
    - El usuario se encuentra dentro de la red interna que no se ha definido como un sitio de red. 
    - El usuario se encuentra fuera de la red interna. Por ejemplo, el usuario está en Internet en casa o en un cibercafé. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar el enrutamiento basado en la ubicación en el sitio de red 
Sitios de red deben estar habilitados para que enrutamiento basados en ubicación ayudar a determinar qué puertas de enlace para enrutar enrutamiento basados en ubicación habilitado a los usuarios al desplazarse. Si un usuario habilitado para enrutamiento basado en la ubicación se desplaza a un sitio que está habilitado para enrutamiento basados en ubicación, se puede usar sólo la puerta de enlace de RTC que está habilitado para enrutamiento basado en la ubicación en el sitio para las llamadas salientes. Si un usuario habilitado para enrutamiento basado en la ubicación se desplaza a un sitio que no está habilitado para enrutamiento basados en ubicación, se puede usar cualquier puerta de enlace que no está habilitado para enrutamiento basado en la ubicación para las llamadas salientes.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar el enrutamiento basado en la ubicación en la puerta de enlace de RTC 

Las puertas de enlace están asociadas a sitios para determinar donde un usuario habilitado para enrutamiento basado en la ubicación puede ser encuentra al realizar o recibir una llamada de RTC. Las puertas de enlace deben estar habilitados para que enrutamiento basados en ubicación para asegurarse de que está bajo restricciones de desvío de pago y no se puede usar por los usuarios que no están habilitados para enrutamiento basado en la ubicación. La misma puerta de enlace se pueden asociar a varios sitios y puede ser configurada para estar habilitado para enrutamiento basado en la ubicación o no habilitado para enrutamiento basados en ubicación, según el sitio. 

## <a name="scenarios-for-location-based-routing"></a>Escenarios para el enrutamiento basado en ubicación

En esta sección se describe distintos escenarios para restringir el desvío de llamadas mediante el uso de enrutamiento basado en la ubicación y compara cómo las llamadas se enrutan a los usuarios que no están habilitados para enrutamiento basados en ubicación con los usuarios habilitados para enrutamiento basado en la ubicación.

- [Usuario de los equipos realiza una llamada saliente a la RTC](#teams-user-places-an-outbound-call-to-the-pstn)
- [Usuario de los equipos recibe una llamada entrante de la RTC](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Usuario de los equipos se transfiere o reenvía la llamada a otro usuario de los equipos](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Usuario de los equipos se transfiere o reenvía la llamada al extremo de RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Tono de llamada simultáneo](#simultaneous-ringing)
- [Delegación](#delegation)

El siguiente diagrama muestra las restricciones habilitadas por enrutamiento basado en la ubicación en cada escenario. Los usuarios, sitios de red y las puertas de enlace que están habilitados para enrutamiento basado en la ubicación con un borde alrededor de ellos. Use el diagrama como una guía que le ayudarán a comprender cómo basados en ubicación enrutamiento funciona en cada escenario.  

![Diagrama que muestra los escenarios de enrutamiento basados en ubicación] (media/lbr-direct-routing.png "Diagrama que muestra los escenarios de enrutamiento basados en ubicación")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Usuario de los equipos realiza una llamada saliente a la RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para el enrutamiento basado en la ubicación

Un usuario que no está habilitado para enrutamiento basados en ubicación puede realizar llamadas salientes con cualquier puerta de enlace en cualquier sitio que no está habilitado para enrutamiento basado en la ubicación a través de su directiva de enrutamiento de voz asignada. Sin embargo, si una puerta de enlace está habilitado para enrutamiento basado en la ubicación, el usuario no puede realizar llamadas salientes a través de la puerta de enlace incluso si se asigna a su directiva de enrutamiento de voz. Si el usuario se desplaza a un sitio que está habilitado para enrutamiento basados en ubicación, sólo puede realizar llamadas a través de sus puertas de enlace de enrutamiento normales que no están habilitados para enrutamiento basado en la ubicación.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para el enrutamiento basado en la ubicación
En comparación, el enrutamiento de llamadas salientes para que los usuarios habilitados para enrutamiento basados en ubicación se ve afectado por la ubicación de red del extremo del usuario. La siguiente tabla muestra cómo basados en ubicación enrutamiento afecta el enrutamiento de llamadas salientes de User1, según la ubicación del Usuario1. 

|Ubicación del extremo de User1  |Enrutamiento de llamadas salientes para usuario1  |
|---------|---------|
|Mismo sitio donde se asigna DID del usuario, sitio habilitado para enrutamiento basados en ubicación (sitio1)      |Llamadas enrutadas a través de la puerta de enlace que está habilitado para enrutamiento basados en ubicación (GW1) en sitio1, basándose en la directiva de enrutamiento de voz del usuario         |
|Sitio distinto de donde se asigna DID del usuario, sitio habilitado para enrutamiento basados en ubicación (Site2)    |Llamada enrutada a través de la puerta de enlace que está habilitado para enrutamiento basados en ubicación (GW2) en itinerancia Site2, en función de la directiva de enrutamiento de voz del usuario        |
|Sitio distinto de donde se asigna DID del usuario, sitio no habilitado para enrutamiento basados en ubicación (3)  |Llamadas enrutadas a través de la puerta de enlace que no está habilitado para enrutamiento basado en la ubicación en el sitio que no se ha habilitado para enrutamiento basados en ubicación (GW3), en función de la directiva de enrutamiento de voz del usuario       |
|Red interna desconocido (Location4)    |  RTC de llamada no permitidos       |
|Red externa desconocido (Location5)    | RTC de llamada no permitidos        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Usuario de los equipos recibe una llamada entrante de la RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para el enrutamiento basado en la ubicación

Un usuario que no está habilitado para enrutamiento basados en ubicación puede recibir una llamada entrante desde la puerta de enlace que no está habilitado para enrutamiento según la ubicación desde la que sus asignado número DID ingresses. Si el usuario se desplaza a un sitio que no está habilitado para enrutamiento basados en ubicación, aún pueden recibir llamadas a través de sus puertas de enlace de RTC normales.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para el enrutamiento basado en la ubicación

En comparación, los usuarios habilitados para enrutamiento basados en ubicación sólo pueden recibir llamadas entrantes de la puerta de enlace de RTC que su DID asignada a cuando se encuentran en el mismo sitio. En la tabla siguiente se muestra cómo User1 recibe las llamadas entrantes cuando usuario1 se desplaza a las ubicaciones de red diferentes. Si la llamada no se enruta al extremo del usuario, va a configuración de transferencia de llamadas del usuario si se establece la configuración. Normalmente, se trata de correo de voz.  

|Ubicación del extremo de User1  |Enrutamiento de llamadas entrantes al Usuario1  |
|---------|---------|
|Mismo sitio como donde se asigna DID del usuario, sitio habilitado para enrutamiento basados en ubicación (sitio1)   | Llamadas enrutadas al extremo de Usuario1 en el sitio 1        |
|Sitio distinto de donde se asigna DID del usuario, sitio habilitado para enrutamiento basados en ubicación (Site2)    | Llamadas que no se enrutan a los extremos en Site2        |
|Sitio distinto de donde se asigna DID del usuario, sitio no habilitado para enrutamiento basados en ubicación (3)    | Llamadas que no se enrutan a los extremos en 3        |
|Red interna desconocido (Location4)   | Llamadas que no se enrutan a los extremos en Location4        |
|Red externa desconocido (Location5)     | Llamadas que no se enrutan a los extremos en Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Usuario de los equipos se transfiere o reenvía la llamada a otro usuario de los equipos

Cuando se trate de un extremo de RTC, enrutamiento basados en ubicación analiza si uno o ambos de los usuarios están habilitados para enrutamiento basado en la ubicación y determina si se debe transferirse o reenviarse según la ubicación de ambos extremos de la llamada. 
 
Transferencia de llamada requiere que el usuario Inicio atender la llamada mientras el desvío de llamadas no requiere la llamada inicial al responder. Esto significa que se pueden reenviar las llamadas incluso si Usuario1 no está en una ubicación para recibir entrante llama (vea la tabla en la sección [usuario equipos recibe una llamada entrante desde la RTC](#teams-user-receives-an-inbound-call-from-the-pstn) ) y no se pueden transferir las llamadas si no puede recibir la llamada entrante Usuario1. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para el enrutamiento basado en la ubicación

Puede transferir un usuario que no está habilitado para enrutamiento basado en la ubicación o llamadas RTC hacia delante a otros usuarios que no están habilitados para enrutamiento basado en la ubicación. El usuario normalmente no se permitirá para transferir o desviar una llamada de RTC a un usuario habilitado para enrutamiento basados en ubicación debido a que el enrutamiento basado en ubicación habilitado a los usuarios generalmente sólo se permiten para la co-autoría encontrarse en enrutamiento basados en ubicación habilitado puertas de enlace de RTC llamadas. La excepción se produce cuando un enrutamiento basados en ubicación habilitado se mueve de usuario a un sitio que no está habilitado para enrutamiento basado en la ubicación. En este escenario, se autoriza la llamada transferida.  

Del mismo modo, un usuario que no está habilitado para enrutamiento basados en ubicación sólo puede recibir a una transferencia o reenviar la llamada de RTC que no está habilitado para enrutamiento basado en la ubicación de otro usuario. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para el enrutamiento basado en la ubicación

Por lo general, transferir y desviar llamadas RTC entrantes desde una puerta de enlace que está habilitado para enrutamiento basado en la ubicación sólo se permiten si el usuario de destino está habilitado para enrutamiento basado en la ubicación y se encuentra en el mismo sitio. De lo contrario, no se permiten transferir y desviar llamadas. 

En la siguiente tabla se muestra si se permiten las transferencias de reenvío y llamada de llamada, según la ubicación del usuario de destino. En esta tabla, Usuario1, que se encuentra en el sitio 1, se inicia la transferencia o desviar a otros usuarios de los equipos que también están habilitado para enrutamiento basado en la ubicación y que se encuentran en distintas ubicaciones.  

|Ubicación de extremo de usuario de destino|Usuario1 inicia la transferencia de llamadas |Usuario1 inicia desviar llamadas|
|---------|---------|---------|
|Mismo sitio de red como iniciador (User2)|Permitido|Permitido|
|Sitio de red distinta, sitio habilitado para enrutamiento basados en ubicación (User3)|No se permiten|No se permiten|
|Sitio de red distinta, sitio no habilitado para enrutamiento basados en ubicación (User4)|No se permiten|No se permiten|
|Red interna desconocido (User5)| No se permiten|No se permiten|
|Red externa desconocido (User6)| No se permiten|No se permiten|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Usuario de los equipos se transfiere o reenvía la llamada al extremo de RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para el enrutamiento basado en la ubicación

- Se permite transferir y desviar una llamada de RTC a otro número de RTC. 
- Transferir y desviar una llamada entrante de VOIP a la RTC deben cumplir con las restricciones de desvío de pago el autor de la llamada. 
    - Si el autor de la llamada no está habilitado para enrutamiento basados en ubicación, se pueden transferir a cualquier puerta de enlace de RTC que no está habilitado para enrutamiento basado en la ubicación.
    - Si el autor de la llamada está habilitado para enrutamiento basados en ubicación, solo pueden transferirse a una puerta de enlace de enrutamiento basados en ubicación habilitado para que se encuentra en el mismo sitio de red. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para el enrutamiento basado en la ubicación

- Transferir y transferencia de entrada una RTC debe enrutarse a la puerta de enlace de enrutamiento basados en ubicación habilitado mismo que ha llegado la llamada entrante de llamada a otro número de RTC. 
- Transferir y desvío de una entrada VOIP llamada a la RTC debe cumplir ambas el autor de la llamada y el pago del usuario llamado Omitir restricciones. 
    - Si el autor de la llamada no está habilitado para enrutamiento basados en ubicación, se pueden transferir a cualquier puerta de enlace de RTC que no está habilitado para enrutamiento basado en la ubicación.
    - Si el autor de la llamada está habilitado para enrutamiento basados en ubicación, se pueden sólo se puede transferir a una puerta de enlace de enrutamiento basados en ubicación habilitado para que se encuentra en el mismo sitio de red.
 
En la siguiente tabla muestra cómo basado en la ubicación de enrutamiento afecta al enrutamiento de una llamada VOIP de User1 en sitio1 a los usuarios de distintas ubicaciones que transfieran o desviar la llamada a un extremo de RTC.  

|Usuario que inicia la transferencia de llamada o reenviar  |Transferir a RTC  |Desviar a RTC  |
|---------|---------|---------|
|Mismo sitio de red, sitio habilitado para enrutamiento basado en la ubicación de (usuario 2)   |Llamada de transferencia sólo se puedan enrutar a través de enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz de usuario2         |Puede hacia delante de llamada sólo se enrutan a través de enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz de usuario2         |
|Sitio de red distinta, sitio habilitado para enrutamiento basados en ubicación (User3)    |Llamada de transferencia sólo se puedan enrutar a través de enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz del User3         |Desviar llamadas solo pueden enrutarse a través del enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz del User3         |
|Sitio de red distinta, sitio no habilitado para enrutamiento basados en ubicación (User4)    |Llamada de transferencia sólo se puedan enrutar a través de enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz del User4         |Desviar llamadas solo pueden enrutarse a través del enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz del User4         |
|Red interna desconocido (User5)     |Llamada de transferencia sólo se puedan enrutar a través de enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz del User5         |Desviar llamadas solo pueden enrutarse a través del enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz del User5         |
|Red externa desconocido (User6)   |Llamada de transferencia sólo se puedan enrutar a través de enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz del User6        |Desviar llamadas solo pueden enrutarse a través del enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz del User6         |

### <a name="simultaneous-ringing"></a>Tono de llamada simultáneo

Cuando un usuario habilitado para enrutamiento basados en ubicación recibe una llamada y las llamadas simultáneas ha habilitado, analiza el enrutamiento basado en la ubicación de la ubicación de la parte que llama y los extremos de las partes llamados para determinar si se debe enrutar la llamada. Las llamadas simultáneas sigue las mismas reglas basados en ubicación como transfiere y reenvía la llamada. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Llamadas de otro usuario de los equipos simultáneas

En la siguiente tabla muestra si el enrutamiento basado en la ubicación permite llamadas a distintos usuarios para una llamada entrante de RTC para User1 simultánea.

|Ubicación de extremo de usuario de destino|Llamada simultánea  |
|---------|---------|
|Mismo sitio de red como iniciador (User2)   |Permitido         |
|Sitio de red de uso en otros equipos diferentes habilitado para enrutamiento basados en ubicación (User3)   |No se permiten         |
|Sitio de red de uso en otros equipos no habilitado para enrutamiento basados en ubicación (User4)   |No se permiten        |
|Red interna desconocido (User5)    | No se permiten        |
|Red externa desconocido (User6)    |No se permiten        |
|Usuario de destino es un número de RTC    |Llamada sólo se puedan enrutar a través de enrutamiento basados en ubicación habilitado Gateway1 en sitio1, basándose en la directiva de enrutamiento de voz de Usuario1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Llamadas a un extremo de RTC simultáneas

En la siguiente tabla muestra el comportamiento de enrutamiento basado en la ubicación de una llamada entrante de VOIP de User1 ubicado en sitio1 a los usuarios en distintas ubicaciones con la llamada simultánea establecida en un número de RTC. 

|Ubicación del extremo de usuario llamado  |Destino de la llamada simultánea es el extremo de RTC |
|---------|---------|
|Mismo sitio de red, sitio habilitado para enrutamiento basado en la ubicación de (usuario 2)    |Llamada puede ser sólo se redirige a través basados en ubicación Gateway1 de enrutamiento en sitio1, basándose en la directiva de enrutamiento de voz de usuario2       |
|Sitio de red diferentes habilitado para enrutamiento basados en ubicación (User3)    |Llamada sólo puede enrutarse a través de Gateway1 de enrutamiento basados en ubicación en sitio1, basándose en la directiva de enrutamiento de voz del User3        |
|Sitio de red diferentes no habilitado para enrutamiento basados en ubicación (User4)    |Llamada sólo puede enrutarse a través de Gateway1 de enrutamiento basados en ubicación en sitio1, basándose en la directiva de enrutamiento de voz del User4         |
|Red interna desconocido (User5)    |Llamada sólo puede enrutarse a través de Gateway1 de enrutamiento basados en ubicación en sitio1, basándose en la directiva de enrutamiento de voz del User5         |
|Red externa desconocido (User6)   |Llamada sólo puede enrutarse a través de Gateway1 de enrutamiento basados en ubicación en sitio1, basándose en la directiva de enrutamiento de voz del User6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Llamadas entrantes a través de la aplicación de voz (operador automático o cola de llamadas)

Se permiten las llamadas RTC entrantes desde una puerta de enlace de enrutamiento basados en ubicación habilitado para conectarse a una cola de llamada o de operador automático. Los usuarios habilitados para enrutamiento basados en ubicación sólo pueden recibir transferencias de llamadas entrantes desde estas aplicaciones cuando se encuentran en el mismo sitio que origina la llamada entrante de RTC. 
 
Desvío de llamadas y las llamadas simultáneas a los usuarios y RTC está permitida para las transferencias de aplicación de voz. Completar la llamada en el destino está sujeto a las mismas reglas de enrutamiento basado en la ubicación indicadas anteriormente.  
 
También se permite la transferencia de correo de voz.  

### <a name="delegation"></a>Delegación

Un usuario de los equipos puede elegir a delegados que pueden realizar y recibir llamadas en su nombre. Capacidades de delegación en los equipos se ven afectadas por enrutamiento basado en la ubicación de la siguiente manera: 
- Para las llamadas salientes desde un delegado de enrutamiento basados en ubicación habilitado en nombre de un usuario delegado, se aplican las mismas reglas. Enrutamiento de llamadas se basa en la directiva de autorización de llamada del delegado, directiva de enrutamiento de voz y la ubicación. Para obtener más información, vea el [usuario de los equipos realiza una llamada saliente a la RTC](#teams-user-places-an-outbound-call-to-the-pstn). 
- Para las llamadas RTC entrantes a un usuario que ha delegado, las mismas reglas de enrutamiento basado en la ubicación que se aplican para el desvío de llamadas o llamar simultáneamente a otros usuarios también son aplicables a los delegados. Para obtener más información, vea [las transferencias de usuario de los equipos o reenvía la llamada a otro usuario de los equipos](#teams-user-transfers-or-forwards-call-to-another-teams-user), [las transferencias de usuario de los equipos o reenvía la llamada al extremo de RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)y [llamadas simultáneas](#simultaneous-ringing). Cuando un delegado establece un extremo de RTC como un destino de la llamada simultánea, la directiva de enrutamiento de voz del delegado se usa para enrutar la llamada a la RTC. 
- Para la delegación, se recomienda que el usuario delegado y los delegados asociados se encuentran en el mismo sitio de red. 

## <a name="other-planning-considerations"></a>Otras consideraciones de planificación

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Cambios de una implementación de enrutamiento basado en la ubicación local

Ya no se usa la directiva de enrutamiento de voz de sitios de red. En su lugar, usamos la directiva de enrutamiento de voz del usuario. Esto significa que, para permitir que los usuarios se desplazan a otros sitios, la directiva de enrutamiento de voz debe incluir las puertas de enlace de los sitios de uso en otros equipos. 

### <a name="technical-considerations-for-location-based-routing"></a>Consideraciones técnicas para el enrutamiento basado en ubicación

Se admiten las subredes IPv4 e IPv6, sin embargo, IPv6 tiene prioridad durante la comprobación de una coincidencia. Compatibilidad con IPv6 está actualmente en curso y estará disponible por disponibilidad General (GA) para el enrutamiento basado en la ubicación. 

### <a name="client-support-for-location-based-routing"></a>Compatibilidad con clientes de enrutamiento basados en ubicación

Se admiten los siguientes clientes de los equipos:
- Clientes de escritorio de los equipos (Windows y Mac)
- Clientes móviles de equipos (iOS y Android)
- Teléfonos IP de los equipos

No se admiten el cliente de web de los equipos y Skype para clientes empresariales.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Capacidades no compatibles con el enrutamiento basado en ubicación

Enrutamiento basado en la ubicación no se aplica a los siguientes tipos de interacciones. Enrutamiento basado en la ubicación no se aplica cuando los extremos de los equipos interactúan con extremos de RTC en los siguientes escenarios: 
- Estacionamiento o recuperación de llamadas RTC a través del estacionamiento de llamadas 
- Un Skype local para usuarios de empresa o un Skype para usuario empresarial en línea llama a un usuario de los equipos  

### <a name="location-based-routing-for-conferencing"></a>Enrutamiento basado en la ubicación para las conferencias

No se permite un usuario habilitado de enrutamiento basados en ubicación en una llamada de RTC para iniciar una conferencia con otro usuario o número de RTC. Se permite que se conectan a los operadores automáticos o colas de llamadas. Si el usuario tiene una licencia de conferencia, el usuario debe iniciar una conferencia con los usuarios relevantes y llamar a la RTC a través del puente de conferencia para iniciar una llamada de conferencia.  

## <a name="next-steps"></a>Pasos siguientes
Vaya a [configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md).

### <a name="related-topics"></a>Temas relacionados
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
- [Terminología de enrutamiento basado en la ubicación](location-based-routing-terminology.md)
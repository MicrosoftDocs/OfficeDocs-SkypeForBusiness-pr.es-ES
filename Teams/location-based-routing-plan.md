---
title: Planear enrutamiento basado en la ubicación para el enrutamiento directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Obtenga información sobre cómo planear Location-Based de enrutamiento directo.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: f05049cdc181aef72f9ed018f20cd8d2e3264909
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822930"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planear enrutamiento basado en la ubicación para el enrutamiento directo

## <a name="overview-of-location-based-routing"></a>Información general sobre Location-Based de correo

En algunos países y regiones, es ilegal omitir el proveedor de red telefónica conmutada (RTC) para disminuir los costes de las llamadas de larga distancia. En este artículo se describe cómo usar el enrutamiento de Location-Based para restringir la omisión de pago para los usuarios de Microsoft Teams en función de su ubicación geográfica. Este artículo se aplica solo al enrutamiento directo de sistema telefónico.

Aquí encontrará información general sobre el enrutamiento de Location-Based instrucciones que le ayudarán a planearlo. Cuando esté listo para aplicar y habilitar el enrutamiento de Location-Based, vea:

- [Implementar la configuración de red para Location-Based distribución](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)

> [!NOTE]
> Location-Based implementación de Microsoft 365 Government Community Cloud (GCC) High o DoD.

Location-Based enrutamiento es una característica que le permite restringir la omisión de pago en función de la directiva y la ubicación geográfica del usuario en el momento de una llamada RTC de entrada o salida. Location-Based enrutamiento está diseñado para proporcionar un mecanismo para evitar la omisión de pago. No debería usarse como mecanismo para enrutar de forma dinámica las llamadas RTC en función de la ubicación del usuario o de consecuencias no deseadas que se puedan producir.

Cuando a un usuario de Teams se le habilita Location-Based de enrutamiento de correo electrónico, se aplica lo siguiente:

- Para realizar una llamada RTC saliente, debe cumplirse una de las siguientes condiciones:
    - El punto de conexión del usuario se encuentra en un sitio de red habilitado para Location-Based Enrutamiento y salida de llamadas a través de la puerta de enlace correspondiente que está habilitada para Location-Based web. 
    - El punto de conexión del usuario se encuentra en un sitio de red que no está habilitado para el enrutamiento de Location-Based y la salida de llamadas a través de una puerta de enlace que no está habilitada para el enrutamiento de Location-Based.

    Las llamadas salientes no se permiten en ningún otro escenario.

- Para recibir una llamada RTC entrante, el punto de conexión de respuesta del usuario debe encontrarse en el mismo sitio de red en el que la llamada entra a través de la puerta de enlace habilitada para el enrutamiento de Location-Based. En cualquier otro escenario, por ejemplo, si el usuario está en itinerancia, la llamada no está permitida y se enruta a la configuración del reenvío de llamadas del usuario (normalmente, el correo de voz).
- Para transferir una llamada RTC a otro usuario de Teams, el punto de conexión del usuario de destino debe encontrarse en el mismo sitio de red que el usuario que inicia la transferencia. Las transferencias no se permiten en ningún otro escenario. 
- Para transferir otro usuario de Teams a RTC, la llamada debe transferirse a través de una puerta de enlace habilitada para enrutamiento de Location-Based ubicada en el mismo sitio de red que el autor de la llamada inicial. Las transferencias no se permiten en ningún otro escenario.

Location-Based enrutamiento de red usa la misma región de red, sitio y definiciones de subred que utiliza Skype Empresarial Server. Cuando se restringe la omisión de pago para una ubicación, un administrador asocia cada subred IP y cada puerta de enlace RTC para esa ubicación a un sitio de red. La ubicación de un usuario se determina mediante la subred IP a la que están conectados los puntos de conexión de Teams del usuario en el momento de una llamada RTC. Un usuario puede tener varios clientes de Teams ubicados en sitios diferentes, en cuyo caso Location-Based Enrutamiento aplica el enrutamiento de cada cliente por separado según la ubicación de su punto de conexión. 

Para familiarizarse con algunos de los términos de red usados en este artículo, consulte Configuración de red para las características de [voz en la nube en Teams.](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>Aplicar Location-Based de correo

Debe aplicar el enrutamiento Location-Based a usuarios, sitios de red y puertas de enlace RTC.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar Location-Based de acceso directo en la ubicación del usuario

Como se mencionó anteriormente, Location-Based solo se aplica a los usuarios que están configurados para enrutamiento directo. Location-Based de enrutamiento no se aplica a los usuarios que están configurados para plan de llamadas. Los usuarios deben estar habilitados para el enrutamiento de Location-Based si están bajo una restricción de omisión de pago, que controla las condiciones en las que pueden realizar y recibir llamadas RTC y la puerta de enlace RTC que se puede usar. Cuando un usuario habilitado para el enrutamiento de Location-Based se encuentra en un sitio habilitado para enrutamiento de Location-Based, el usuario debe realizar llamadas a través de una puerta de enlace habilitada para enrutamiento de Location-Based conectada al sitio. 

Location-Based enrutamiento funciona determinando la ubicación actual del usuario en función de la dirección IP del punto de conexión de Teams del usuario y aplica las reglas en consecuencia. La ubicación de un usuario habilitado para el enrutamiento de Location-Based se puede clasificar de las siguientes maneras: 
- **El usuario se encuentra en el mismo lugar Location-Based sitio habilitado para enrutamiento asociado a la puerta de enlace RTC a la que se asignó su DID.**<br>En este escenario, el usuario se encuentra en un sitio de red conocido habilitado para Location-Based El enrutamiento y el número de Marcado entrante directo (DID) del usuario terminan en una puerta de enlace RTC que está en el mismo sitio de red. Por ejemplo, el usuario se encuentra en su oficina. 
- **El usuario se encuentra en otro Location-Based sitio habilitado para enrutamiento no asociado a la puerta de enlace RTC a la que se asignó su DID.**<br>En este escenario, el usuario se encuentra en un sitio de red conocido habilitado para enrutamiento de Location-Based y ese sitio no está asociado a la puerta de enlace RTC a la que se asigna el número DID del usuario. Por ejemplo, el usuario viaja a otra oficina.  
- **El usuario se encuentra en un sitio interno que no está habilitado para el enrutamiento Location-Based usuario.** <br>En este escenario, el usuario se encuentra en un sitio de red interna conocido que no está habilitado para el Location-Based usuario. 
- **El usuario se encuentra en un sitio desconocido.** 
    - El usuario se encuentra dentro de la red interna que no está definida como sitio de red. 
    - El usuario se encuentra fuera de la red interna. Por ejemplo, el usuario está en Internet en casa o en una cafetería. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar Location-Based de acceso directo en el sitio de red 
Los sitios de red deben estar habilitados para Location-Based para ayudar a determinar qué puertas de enlace enrutar a los Location-Based habilitado para enrutamiento cuando se está en itinerancia. Si un usuario habilitado para Location-Based enrutamiento se desruta a un sitio habilitado para enrutamiento de Location-Based, solo se puede usar la puerta de enlace RTC habilitada para Location-Based Enrutamiento en ese sitio para llamadas salientes. Si un usuario habilitado para Location-Based enrutamiento se desruta a un sitio que no está habilitado para enrutamiento de Location-Based, cualquier puerta de enlace que no esté habilitada para el enrutamiento de Location-Based puede usarse para llamadas salientes.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar Location-Based de acceso directo en la puerta de enlace de RTC 

Las puertas de enlace se asocian a los sitios para determinar dónde puede encontrarse un usuario habilitado para el Location-Based en el momento de realizar o recibir una llamada RTC. Las puertas de enlace deben estar habilitadas para el enrutamiento de Location-Based para asegurarse de que está bajo restricciones de omisión de pago y que los usuarios que no están habilitados para el enrutamiento de Location-Based no pueden usarse. La misma puerta de enlace se puede asociar a varios sitios y se puede configurar para habilitarse para el enrutamiento de Location-Based o no para el enrutamiento de Location-Based, dependiendo del sitio.

## <a name="scenarios-for-location-based-routing"></a>Escenarios para el enrutamiento basado en ubicación

En esta sección se describen diferentes escenarios para restringir la omisión de pago mediante el enrutamiento de Location-Based y compara cómo se enrutan las llamadas para los usuarios que no están habilitados para Location-Based Enrutamiento con usuarios habilitados para enrutamiento de Location-Based.

- [El usuario de Teams coloca una llamada saliente a LA](#teams-user-places-an-outbound-call-to-the-pstn)
- [El usuario de Teams recibe una llamada entrante de LA](#teams-user-receives-an-inbound-call-from-the-pstn)
- [La transferencia o el reenvío de una llamada de usuario de Teams a otro usuario de Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Transferencia o reenvíos de usuario de Teams a punto de conexión de RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Tono de llamada simultáneo](#simultaneous-ringing)
- [Delegación](#delegation)

El siguiente diagrama muestra las restricciones habilitadas por el Location-Based en cada escenario. Los usuarios, los sitios de red y las puertas de enlace que están habilitadas Location-Based enrutamiento de red tienen un borde alrededor de ellos. Use el diagrama como guía para comprender cómo funciona Location-Based de enrutamiento en cada escenario.  

![Diagrama que muestra escenarios para Location-Based enrutamiento](media/lbr-direct-routing.png "Diagrama en el que se muestran escenarios para Location-Based de correo")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>El usuario de Teams coloca una llamada saliente a LA

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para el Location-Based web

Un usuario que no está habilitado para el enrutamiento de Location-Based puede realizar llamadas salientes con cualquier puerta de enlace en cualquier sitio que no esté habilitado para Location-Based Mediante su directiva de enrutamiento de voz asignada. Sin embargo, si una puerta de enlace está habilitada para el enrutamiento de Location-Based, el usuario no podrá realizar llamadas salientes a través de la puerta de enlace aunque esté asignada a su directiva de enrutamiento de voz. Si el usuario realiza la ruta a un sitio habilitado para enrutamiento de Location-Based, solo podrá realizar llamadas a través de sus puertas de enlace de enrutamiento normales que no están habilitadas para Location-Based enrutamiento.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para Location-Based web
En comparación, el enrutamiento de llamadas salientes para los usuarios habilitados para el enrutamiento de Location-Based se ve afectado por la ubicación de red del punto de conexión del usuario. En la tabla siguiente se muestra Location-Based afecta al enrutamiento de llamadas salientes de Usuario1, según la ubicación de Usuario1. 

|Ubicación del punto de conexión de Usuario1  |Enrutamiento de llamadas salientes para Usuario1  |
|---------|---------|
|El mismo sitio en el que se asignó la DID del usuario, sitio habilitado para el Location-Based de acceso directo (Sitio1)      |Llamada enrutada a través de una puerta de enlace habilitada para Location-Based routing (GW1) en Site1, en función de la directiva de enrutamiento de voz del usuario         |
|Sitio diferente al donde se asignó el DID del usuario, sitio habilitado para el Location-Based de sitios (Sitio2)    |Llamada enrutada a través de una puerta de enlace habilitada para Location-Based web (GW2) en el sitio de direccionamiento 2, en función de la directiva de enrutamiento de voz del usuario        |
|Sitio diferente al donde se asignó el DID del usuario, sitio no habilitado para el Location-Based de sitios (Sitio3)  |Llamada enrutada a través de una puerta de enlace que no está habilitada para el enrutamiento de Location-Based en un sitio que no está habilitado para el enrutamiento de Location-Based (GW3), en función de la directiva de enrutamiento de voz del usuario       |
|Red interna desconocida (Ubicación4)    |  Llamadas RTC no permitidas       |
|Red externa desconocida (Ubicación5)    | Llamadas RTC no permitidas        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>El usuario de Teams recibe una llamada entrante de LA

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para el Location-Based web

Un usuario que no está habilitado para Location-Based El enrutamiento puede recibir una llamada entrante desde la puerta de enlace que no está habilitada para Location-Based Enrutamiento desde el que se recibe el número DID asignado. Si el usuario se desenlaza a un sitio que no está habilitado para el enrutamiento Location-Based, aún podrá recibir llamadas a través de sus puertas de enlace RTC normales.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para Location-Based web

En comparación, los usuarios habilitados para Location-Based El enrutamiento solo puede recibir llamadas entrantes de la puerta de enlace RTC a la que se ha asignado su DID cuando se encuentran en el mismo sitio. En la tabla siguiente se muestra cómo recibe User1 las llamadas entrantes cuando Usuario1 se mueve a diferentes ubicaciones de red. Si la llamada no se enruta al punto de conexión del usuario, esta irá a la configuración del reenvío de llamadas del usuario, si la configuración está configurada. Normalmente, es correo de voz.  

|Ubicación del punto de conexión de Usuario1  |Enrutamiento de llamadas entrantes a Usuario1  |
|---------|---------|
|El mismo sitio donde se asignó el DID del usuario, sitio habilitado para el Location-Based de sitios (Sitio1)   | Llamadas enrutadas al punto de conexión de Usuario1 en Sitio1        |
|Sitio diferente al donde se asignó el DID del usuario, sitio habilitado para el Location-Based de sitios (Sitio2)    | Llamadas no enrutadas a puntos de conexión en Sitio2        |
|Sitio diferente al donde se asignó el DID del usuario, sitio no habilitado para el Location-Based de sitios (Sitio3)    | Llamadas no enrutadas a puntos de conexión en Site3        |
|Red interna desconocida (Ubicación4)   | Llamadas no enrutadas a puntos de conexión en Ubicación4        |
|Red externa desconocida (Ubicación5)     | Llamadas no enrutadas a puntos de conexión en Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>La transferencia o el reenvío de una llamada de usuario de Teams a otro usuario de Teams

Cuando un punto de conexión de RTC está implicado, Location-Based Routing analiza si uno o ambos usuarios están habilitados para el enrutamiento de Location-Based y determina si la llamada se debe transferir o reenviar según la ubicación de ambos puntos de conexión. 
 
La transferencia de llamadas requiere que el usuario que inicia recoja la llamada, mientras que el reenvío de llamadas no requiere que se conteste a la llamada inicial. Esto significa que las llamadas se pueden reenviar incluso si Usuario1 no se encuentra en una ubicación para recibir llamadas entrantes (vea la tabla del usuario de [Teams](#teams-user-receives-an-inbound-call-from-the-pstn) recibe una llamada entrante de la sección RTC) y las llamadas no se pueden transferir si el Usuario1 no puede recibir la llamada entrante. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para Location-Based de correo

Un usuario que no está habilitado para Location-Based Enrutamiento puede transferir o reenviar llamadas RTC a otros usuarios que no están habilitados para Location-Based correo electrónico. Normalmente, al usuario no se le permite transferir o reenviar una llamada RTC a un usuario habilitado para enrutamiento de Location-Based ya que, en general, en Location-Based los usuarios habilitados para enrutamiento solo pueden encontrarse en co-ubicación en puertas de enlace habilitadas para enrutamiento para llamadas RTC de Location-Based. La excepción es cuando un Location-Based habilitado para enrutamiento de sitios se des recorrido a un sitio que no está habilitado para Location-Based web. En este escenario, se permite la llamada transferida.  

Del mismo modo, un usuario que no está habilitado para el enrutamiento de Location-Based solo puede recibir una transferencia o una llamada RTC reenviada de otro usuario que no está habilitado para el enrutamiento de Location-Based. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para Location-Based web

Por lo general, la transferencia y el reenvío de llamadas RTC entrantes desde una puerta de enlace habilitada para Location-Based Solo se permite el enrutamiento si el usuario de destino está habilitado para Location-Based Routing y se encuentra en el mismo sitio. En caso contrario, no se permite transferir ni reenviar llamadas. 

En la tabla siguiente se muestra si se permiten el reenvío de llamadas y las transferencias de llamadas, según la ubicación del usuario de destino. En esta tabla, Usuario1, que se encuentra en Sitio1, inicia la transferencia o se reenvía a otros usuarios de Teams que también están habilitados para el enrutamiento de Location-Based y que están en ubicaciones diferentes.  

|Ubicación del extremo de usuario de destino|El usuario1 inicia la transferencia de llamadas |El usuario1 inicia el reenvío de llamada|
|---------|---------|---------|
|El mismo sitio de red que lo hace (Usuario2)|Permitido|Permitido|
|Sitio de red diferente habilitado para el Location-Based de distribución (usuario3)|No se permiten|No se permiten|
|Sitio de red diferente, sitio no habilitado para Location-Based de red (Usuario4)|No se permiten|No se permiten|
|Red interna desconocida (Usuario5)| No se permiten|No se permiten|
|Red externa desconocida (Usuario6)| No se permiten|No se permiten|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Transferencia o reenvíos de usuario de Teams a punto de conexión de RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para Location-Based de correo

- Se permite transferir y reenviar una llamada RTC a otro número RTC. 
- La transferencia y el reenvío de una llamada VOIP entrante a la RTC debe respetar las restricciones de omisión de pago del autor de la llamada. 
    - Si el autor de la llamada no está habilitado para el Location-Based de llamada, se puede transferir a cualquier puerta de enlace RTC que no esté habilitada para Location-Based de llamada.
    - Si al autor de la llamada se le habilita Location-Based de enrutamiento, solo se puede transferir a una puerta de enlace Location-Based habilitada para enrutamiento ubicada en el mismo sitio de red. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para Location-Based web

- La transferencia y el reenvío de una llamada RTC a otro número RTC se deben enrutar de la misma manera Location-Based puerta de enlace habilitada para enrutamiento a la que llegó la llamada entrante. 
- Para transferir y reenviar una llamada VOIP entrante a la RTC, tanto el autor de la llamada como las restricciones de omisión de pago del usuario. 
    - Si el autor de la llamada no está habilitado para el Location-Based de llamada, se puede transferir a cualquier puerta de enlace RTC que no esté habilitada para Location-Based de llamada.
    - Si al autor de la llamada se le habilita Location-Based de enrutamiento de red, solo se pueden transferir a una puerta de enlace habilitada Location-Based enrutamiento ubicada en el mismo sitio de red.
 
En la tabla siguiente se muestra cómo el enrutamiento de Location-Based afecta al enrutamiento de una llamada VOIP desde Usuario1 en Sitio1 a los usuarios de diferentes ubicaciones que transfieren o desvía la llamada a un punto de conexión de RTC.  

|Usuario que inicia una transferencia o reenvío de llamada  |Transferir a RTC  |Reenviar a RTC  |
|---------|---------|---------|
|Mismo sitio de red, sitio habilitado para Location-Based (usuario2)   |La transferencia de llamadas solo se puede enrutar a través Location-Based De enlace habilitado para enrutamiento en el sitio1, en función de la directiva de enrutamiento de voz de User2         |El reenvío de llamadas solo se puede enrutar a través Location-Based de enrutamiento habilitado para enrutamiento1 en el sitio1, según la directiva de enrutamiento de voz de User2         |
|Sitio de red diferente habilitado para Location-Based web (usuario3)    |La transferencia de llamadas solo se puede enrutar a través de Location-Based De enlace habilitado para enrutamiento en el sitio1, en función de la directiva de enrutamiento de voz de User3         |El reenvío de llamadas solo se puede enrutar a través Location-Based de enrutamiento habilitado para enrutamiento1 en el sitio1, en función de la directiva de enrutamiento de voz de User3         |
|Sitio de red diferente, sitio no habilitado para Location-Based de red (Usuario4)    |La transferencia de llamadas solo se puede enrutar a través de la Location-Based de enlace habilitada para enrutamiento en el sitio1, en función de la directiva de enrutamiento de voz del usuario4         |El reenvío de llamadas solo se puede enrutar a través de la puerta Location-Based de enlace habilitada para enrutamiento en el sitio1, en función de la directiva de enrutamiento de voz del usuario4         |
|Red interna desconocida (Usuario5)     |La transferencia de llamadas solo se puede enrutar a Location-Based de enlace habilitado para enrutamiento en el sitio1, en función de la directiva de enrutamiento de voz de User5         |El reenvío de llamadas solo se puede enrutar a través de una puerta Location-Based de enlace habilitada para enrutamiento en el sitio1, en función de la directiva de enrutamiento de voz de User5         |
|Red externa desconocida (Usuario6)   |La transferencia de llamadas solo se puede enrutar a través de la puerta Location-Based de enlace habilitada para enrutamiento en el sitio1, en función de la directiva de enrutamiento de voz de User6        |El reenvío de llamadas solo se puede enrutar a través Location-Based de enlace habilitado para enrutamiento1 en el sitio1, en función de la directiva de enrutamiento de voz de User6         |

### <a name="simultaneous-ringing"></a>Tono de llamada simultáneo

Cuando un usuario habilitado para el enrutamiento de Location-Based recibe una llamada y tiene habilitada la llamada simultánea, el enrutamiento de Location-Based analiza la ubicación del usuario que realiza la llamada y los puntos de conexión de las partes llamadas para determinar si se debe enrutar la llamada. Las llamadas simultáneas siguen las mismas reglas Location-Based que las transferencias y los reenvíos de llamadas. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Llamada simultánea para otro usuario de Teams

En la tabla siguiente se muestra si Location-Based de llamada simultánea a diferentes usuarios para una llamada RTC entrante para Usuario1.

|Ubicación del extremo de usuario de destino|Llamada simultánea  |
|---------|---------|
|El mismo sitio de red que lo hace (Usuario2)   |Permitido         |
|Sitio de red móvil diferente habilitado para Location-Based dinámico (usuario3)   |No se permiten         |
|Sitio de red con recorrido no habilitado para Location-Based dinámico (usuario4)   |No se permiten        |
|Red interna desconocida (Usuario5)    | No se permiten        |
|Red externa desconocida (Usuario6)    |No se permiten        |
|El usuario de destino es un número RTC    |La llamada solo se puede enrutar a través Location-Based De enlace habilitado para enrutamiento en el sitio1, en función de la directiva de enrutamiento de voz de User1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Llamada simultánea a un punto de conexión de RTC

En la tabla siguiente se Location-Based comportamiento de enrutamiento para una llamada VOIP entrante de Usuario1 ubicado en Sitio1 a usuarios en diferentes ubicaciones con llamadas simultáneas establecidas en un número RTC. 

|Ubicación de extremo de usuario llamada  |El destino de llamada simultánea es el punto de conexión de RTC |
|---------|---------|
|Mismo sitio de red, sitio habilitado para Location-Based (usuario2)    |La llamada solo se puede enrutar a través de Location-Based Routing Gateway1 en Site1, en función de la directiva de enrutamiento de voz de User2       |
|Sitio de red distinto habilitado para Location-Based de distribución (usuario3)    |La llamada solo se puede enrutar a través Location-Based Routing Gateway1 en Site1, en función de la directiva de enrutamiento de voz de User3        |
|Sitio de red diferente no habilitado para Location-Based de distribución (usuario4)    |La llamada solo se puede enrutar a través Location-Based Routing Gateway1 en Site1, en función de la directiva de enrutamiento de voz de User4         |
|Red interna desconocida (Usuario5)    |La llamada solo se puede enrutar a través Location-Based Routing Gateway1 en Site1, en función de la directiva de enrutamiento de voz de User5         |
|Red externa desconocida (Usuario6)   |La llamada solo se puede enrutar a través Location-Based Routing Gateway1 en Site1, en función de la directiva de enrutamiento de voz de User6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Llamadas entrantes a través de la aplicación de voz (Operador automático o cola de llamadas)

Las llamadas RTC de entrada de una Location-Based puerta de enlace habilitada para enrutamiento permiten conectarse a un operador automático o a una cola de llamadas. Los usuarios habilitados para Location-Based solo pueden recibir transferencias de llamadas entrantes desde estas aplicaciones cuando se encuentran en el mismo sitio del que procede la llamada RTC de entrada. 
 
El reenvío de llamadas y las llamadas simultáneas a usuarios y RTC se permiten para las transferencias de aplicaciones de voz. Completar la llamada al destino está sujeto a las Location-Based de enrutamiento indicadas anteriormente.  
 
También se permite el reenvío al correo de voz.  

### <a name="delegation"></a>Delegación

Un usuario de Teams puede elegir delegados que pueden realizar y recibir llamadas en su nombre. Las capacidades de delegación en Teams se ven afectadas por la Location-Based de enrutamiento de la siguiente manera: 
- Para las llamadas salientes de un Location-Based delegado habilitado para enrutamiento en nombre de un delegador, se aplican las mismas reglas. El enrutamiento de llamadas se basa en la directiva de autorización de llamadas, la directiva de enrutamiento de voz y la ubicación del delegado. Para obtener más información, vea [que el usuario de Teams coloca una llamada saliente a RTC.](#teams-user-places-an-outbound-call-to-the-pstn) 
- Para las llamadas RTC de entrada a un delegador, las mismas reglas de enrutamiento de Location-Based que se aplican para el reenvío de llamadas o la llamada simultánea a otros usuarios también se aplican a los delegados. Para obtener más información, vea las transferencias o las llamadas de los usuarios de Teams a otro usuario de [Teams,](#teams-user-transfers-or-forwards-call-to-another-teams-user)las transferencias de usuario de [Teams](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)o las llamadas a puntos de conexión RTC y las llamadas [simultáneas.](#simultaneous-ringing) Cuando un delegado establece un punto de conexión de RTC como destino de llamada simultánea, la directiva de enrutamiento de voz del delegado se usa para enrutar la llamada a RTC. 
- Para la delegación, se recomienda que el delegador y los delegados asociados se encuentran en el mismo sitio de red. 

## <a name="other-planning-considerations"></a>Otras consideraciones de planificación

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Cambios de una implementación de enrutamiento Location-Based local

Ya no se usa la directiva de enrutamiento de voz del sitio de red. En su lugar, usamos la directiva de enrutamiento de voz del usuario. Esto significa que para permitir a los usuarios realizar la ruta a otros sitios, la directiva de enrutamiento de voz debe incluir las puertas de enlace de los sitios recorridos. 

### <a name="technical-considerations-for-location-based-routing"></a>Consideraciones técnicas para el enrutamiento basado en ubicación

Las subredes IPv4 e IPv6 son compatibles, pero IPv6 tiene prioridad al comprobar una coincidencia.

### <a name="client-support-for-location-based-routing"></a>Compatibilidad con clientes para Location-Based de correo electrónico

Se admiten los siguientes clientes de Teams:
- Clientes de escritorio de Teams (Windows y Mac)
- Clientes móviles de Teams (iOS y Android)
- Teléfonos IP de Teams

El cliente web de Teams y los clientes de Skype Empresarial no son compatibles.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Capacidades no compatibles con el enrutamiento basado en ubicación

Location-Based enrutamiento no se aplica a los siguientes tipos de interacciones. Location-Based no se aplica el enrutamiento cuando los puntos de conexión de Teams interactúan con puntos de conexión de RTC en los siguientes escenarios: 
- Estacionamiento o recuperación de llamadas RTC a través del estacionamiento de llamadas 
- Un usuario local de Skype Empresarial o un usuario de Skype Empresarial Online llama a un usuario de Teams  

### <a name="location-based-routing-for-conferencing"></a>Location-Based para conferencias

Un Location-Based en una llamada RTC no tiene permiso para iniciar una conferencia con otro usuario o número de RTC. Se permite la conexión con operadores automáticos o colas de llamadas. Si el usuario tiene una licencia de conferencia, debe iniciar una conferencia con los usuarios pertinentes y llamar a RTC a través del puente de conferencia para iniciar una llamada de conferencia.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito de omisión de medios para Location-Based de correo

Si va a implementar el enrutamiento Location-Based en la India, también es necesario configurar la omisión de medios. Para obtener más información, consulte Planear la omisión [de medios con enrutamiento](direct-routing-plan-media-bypass.md) directo y optimización de medios locales para el enrutamiento [directo.](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>Voz directa sobre IP (VoIP)

La voz directa sobre IP (VoIP) no se debe implementar con ningún equipo de telefonía en India.

## <a name="next-steps"></a>Pasos siguientes

Vaya a [Configurar las opciones de red para Location-Based de red.](location-based-routing-configure-network-settings.md)

## <a name="related-topics"></a>Temas relacionados

- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
- [Configuración de red para las características de voz en la nube en Teams](cloud-voice-network-settings.md)

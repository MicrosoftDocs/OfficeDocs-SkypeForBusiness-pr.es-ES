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
description: Obtenga información sobre cómo planear Location-Based enrutamiento directo.
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

## <a name="overview-of-location-based-routing"></a>Información general sobre Location-Based enrutamiento

En algunos países y regiones, es ilegal omitir el proveedor de red telefónica conmutada (RTC) para reducir los costos de llamadas de larga distancia. En este artículo se describe cómo usar Location-Based enrutamiento para restringir la omisión de peaje para Microsoft Teams usuarios en función de su ubicación geográfica. Este artículo solo se aplica a Sistema telefónico enrutamiento directo.

Aquí encontrará información general sobre el Location-Based y las instrucciones para ayudarle a planearlo. Cuando esté listo para aplicar y habilitar el Location-Based, vea:

- [Implementar la configuración de red para Location-Based enrutamiento](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)

> [!NOTE]
> Location-Based enrutamiento no está disponible en implementaciones Microsoft 365 Government Community Cloud (GCC) High o DoD.

Location-Based enrutamiento es una característica que le permite restringir la omisión de peaje en función de la directiva y la ubicación geográfica del usuario en el momento de una llamada RTC entrante o saliente. Location-Based enrutamiento está destinado a proporcionar un mecanismo para evitar la omisión de peaje. No debe usarse como mecanismo para enrutar dinámicamente las llamadas RTC en función de la ubicación del usuario o las consecuencias no deseadas pueden resultar.

Cuando un Teams está habilitado para Location-Based enrutamiento, se aplica lo siguiente:

- Para realizar una llamada RTC saliente, debe cumplirse una de las siguientes acciones:
    - El punto de conexión del usuario se encuentra en un sitio de red habilitado para la salida de llamadas y enrutamiento de Location-Based a través de la puerta de enlace correspondiente habilitada para Location-Based enrutamiento. 
    - El punto de conexión del usuario se encuentra en un sitio de red que no está habilitado para la salida de llamadas y enrutamiento de Location-Based a través de una puerta de enlace que no está habilitada para Location-Based enrutamiento.

    Las llamadas salientes no están permitidas en ningún otro escenario.

- Para recibir una llamada RTC entrante, el punto de conexión de respuesta del usuario debe estar ubicado en el mismo sitio de red donde la llamada entra a través de la puerta de enlace habilitada para Location-Based enrutamiento. En cualquier otro escenario, como si el usuario está en itinerancia, la llamada no está permitida y se enruta a la configuración de reenvío de llamadas del usuario (normalmente correo de voz).
- Para transferir una llamada RTC a otro usuario de Teams, el punto de conexión del usuario de destino debe estar en el mismo sitio de red que el usuario que inicia la transferencia. Las transferencias no están permitidas en ningún otro escenario. 
- Para transferir otro Teams a la RTC, la llamada debe transferirse a través de una puerta de enlace habilitada para enrutamiento de Location-Based ubicada en el mismo sitio de red que el autor de la llamada inicial. Las transferencias no están permitidas en ningún otro escenario.

Location-Based enrutamiento usa las mismas definiciones de región de red, sitio y subred que Skype Empresarial Server red. Cuando la omisión de peaje está restringida para una ubicación, un administrador asocia cada subred IP y cada puerta de enlace RTC de esa ubicación a un sitio de red. La ubicación de un usuario está determinada por la subred IP a la que están conectados los puntos de conexión Teams del usuario en el momento de una llamada RTC. Un usuario puede tener varios clientes de Teams ubicados en sitios diferentes, en cuyo caso Location-Based Enrutamiento exige el enrutamiento de cada cliente por separado según la ubicación de su punto de conexión. 

Para familiarizarse con algunos de los términos de red usados en este [artículo,](cloud-voice-network-settings.md)vea Configuración de red para las características de voz en la nube en Teams .

## <a name="apply-location-based-routing"></a>Aplicar Location-Based enrutamiento

Debe aplicar el Location-Based a usuarios, sitios de red y puertas de enlace RTC.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar Location-Based enrutamiento en la ubicación del usuario

Como se mencionó anteriormente, Location-Based enrutamiento solo se aplica a los usuarios que están configurados para enrutamiento directo. Location-Based enrutamiento no se aplica a los usuarios que están configurados para plan de llamadas. Los usuarios deben estar habilitados para el enrutamiento de Location-Based si están bajo restricción de omisión de peaje, que controla las condiciones en las que pueden realizar y recibir llamadas RTC y la puerta de enlace RTC que se puede usar. Cuando un usuario habilitado para Location-Based Enrutamiento se encuentra en un sitio habilitado para enrutamiento de Location-Based, el usuario debe realizar llamadas a través de una puerta de enlace habilitada para enrutamiento de Location-Based conectada al sitio. 

Location-Based enrutamiento funciona determinando la ubicación actual del usuario en función de la dirección IP del punto de conexión Teams del usuario y aplica las reglas en consecuencia. La ubicación de un usuario habilitado para Location-Based enrutamiento se puede clasificar de las siguientes maneras: 
- **El usuario se encuentra en el mismo Location-Based sitio habilitado para enrutamiento asociado a la puerta de enlace RTC donde se asigna su DID.**<br>En este escenario, el usuario se encuentra en un sitio de red conocido habilitado para enrutamiento de Location-Based y el número de marcado directo entrante (DID) del usuario finaliza en una puerta de enlace RTC que se encuentra en el mismo sitio de red. Por ejemplo, el usuario se encuentra en su oficina. 
- **El usuario se encuentra en un sitio Location-Based enrutamiento no asociado a la puerta de enlace RTC donde se asigna su DID.**<br>En este escenario, el usuario se encuentra en un sitio de red conocido habilitado para enrutamiento de Location-Based y ese sitio no está asociado con la puerta de enlace RTC donde se asigna el número DID del usuario. Por ejemplo, el usuario viaja a otra oficina.  
- **El usuario se encuentra en un sitio interno que no está habilitado para Location-Based enrutamiento.** <br>En este escenario, el usuario se encuentra en un sitio de red interno conocido que no está habilitado para Location-Based enrutamiento. 
- **El usuario se encuentra en un sitio desconocido.** 
    - El usuario se encuentra dentro de la red interna que no se define como un sitio de red. 
    - El usuario se encuentra fuera de la red interna. Por ejemplo, el usuario está en Internet en casa o en una cafetería. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar Location-Based enrutamiento en el sitio de red 
Los sitios de red deben estar habilitados para Location-Based enrutamiento para ayudar a determinar qué puertas de enlace enrutar Location-Based usuarios habilitados para enrutamiento al itinerancia. Si un usuario habilitado para el enrutamiento de Location-Based va a un sitio habilitado para enrutamiento de Location-Based, solo se puede usar la puerta de enlace RTC habilitada para Location-Based Enrutamiento en ese sitio para llamadas salientes. Si un usuario habilitado para Location-Based Enrutamiento se desancha a un sitio que no está habilitado para enrutamiento de Location-Based, cualquier puerta de enlace que no esté habilitada para Location-Based Enrutamiento se puede usar para las llamadas salientes.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar Location-Based enrutamiento en la puerta de enlace RTC 

Las puertas de enlace están asociadas a sitios para determinar dónde se puede encontrar un usuario habilitado para Location-Based enrutamiento cuando realiza o recibe una llamada RTC. Las puertas de enlace deben estar habilitadas para el enrutamiento de Location-Based para asegurarse de que se encuentra bajo restricciones de omisión de peaje y que los usuarios que no están habilitados para el enrutamiento de Location-Based pago. La misma puerta de enlace puede estar asociada a varios sitios y se puede configurar para que esté habilitada para enrutamiento de Location-Based o no habilitada para Location-Based enrutamiento, según el sitio.

## <a name="scenarios-for-location-based-routing"></a>Escenarios para el enrutamiento basado en ubicación

En esta sección se describen diferentes escenarios para restringir la omisión de peaje mediante el enrutamiento de Location-Based y se compara cómo se enrutan las llamadas para los usuarios que no están habilitados para el enrutamiento de Location-Based con los usuarios habilitados para Location-Based Enrutamiento.

- [Teams usuario coloca una llamada saliente a la RTC](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams usuario recibe una llamada entrante desde la RTC](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams de transferencia o reenvío de usuarios a otro Teams usuario](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams de transferencia de usuarios o reenvía llamadas al punto de conexión RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Tono de llamada simultáneo](#simultaneous-ringing)
- [Delegación](#delegation)

En el siguiente diagrama se muestran las restricciones habilitadas por Location-Based enrutamiento en cada escenario. Los usuarios, sitios de red y puertas de enlace habilitados para Location-Based enrutamiento tienen un borde alrededor de ellos. Use el diagrama como guía para ayudarle a comprender cómo funciona Location-Based enrutamiento en cada escenario.  

![Diagrama que muestra escenarios para Location-Based enrutamiento](media/lbr-direct-routing.png "Diagrama que muestra escenarios para Location-Based enrutamiento")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams usuario coloca una llamada saliente a la RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para Location-Based enrutamiento

Un usuario que no está habilitado para el enrutamiento de Location-Based puede realizar llamadas salientes con cualquier puerta de enlace en cualquier sitio que no esté habilitado para Location-Based Enrutamiento a través de su directiva de enrutamiento de voz asignada. Sin embargo, si una puerta de enlace está habilitada para el enrutamiento de Location-Based, el usuario no puede realizar llamadas salientes a través de la puerta de enlace incluso si está asignada a su directiva de enrutamiento de voz. Si el usuario va a un sitio habilitado para enrutamiento de Location-Based, solo puede realizar llamadas a través de sus puertas de enlace de enrutamiento normales que no están habilitadas para Location-Based enrutamiento.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para Location-Based enrutamiento
En comparación, el enrutamiento de las llamadas salientes para los usuarios que están habilitados para Location-Based Enrutamiento se ve afectado por la ubicación de red del punto de conexión del usuario. En la tabla siguiente se muestra cómo Location-Based enrutamiento afecta al enrutamiento de llamadas salientes de User1, según la ubicación de User1. 

|Ubicación del punto de conexión user1  |Enrutamiento de llamadas salientes para Usuario1  |
|---------|---------|
|El mismo sitio en el que se asignó el DID del usuario, sitio habilitado para Location-Based enrutamiento (sitio1)      |Llamada enrutada a través de la puerta de enlace habilitada para Location-Based Routing (GW1) en Site1, según la directiva de enrutamiento de voz del usuario         |
|Sitio diferente del lugar donde se ha asignado el DID del usuario, sitio habilitado para Location-Based enrutamiento (Sitio2)    |Llamada enrutada a través de puerta de enlace habilitada para Location-Based Routing (GW2) en roam Site2, según la directiva de enrutamiento de voz del usuario        |
|Sitio diferente del lugar donde se asigna did del usuario, sitio no habilitado para Location-Based enrutamiento (Sitio3)  |Llamada enrutada a través de la puerta de enlace que no está habilitada para Location-Based Enrutamiento en el sitio que no está habilitado para el enrutamiento de Location-Based (GW3), según la directiva de enrutamiento de voz del usuario       |
|Red interna desconocida (Ubicación4)    |  Llamadas RTC no permitidas       |
|Red externa desconocida (Location5)    | Llamadas RTC no permitidas        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams usuario recibe una llamada entrante desde la RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para Location-Based enrutamiento

Un usuario que no está habilitado para Location-Based Enrutamiento puede recibir una llamada entrante desde la puerta de enlace que no está habilitada para Location-Based Enrutamiento desde el que se ha asignado la entrada de número DID. Si el usuario se desenlaza a un sitio que no está habilitado para Location-Based enrutamiento, todavía pueden recibir llamadas a través de sus puertas de enlace RTC normales.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para Location-Based enrutamiento

En comparación, los usuarios habilitados para Location-Based enrutamiento solo pueden recibir llamadas entrantes desde la puerta de enlace RTC a la que se asigna su DID cuando se encuentran en el mismo sitio. En la tabla siguiente se muestra cómo User1 recibe llamadas entrantes cuando User1 se mueve a distintas ubicaciones de red. Si la llamada no se enruta al punto de conexión del usuario, se dirigirá a la configuración de reenvío de llamadas del usuario, si la configuración está configurada. Normalmente, este es el correo de voz.  

|Ubicación del punto de conexión user1  |Enrutamiento de llamadas entrantes a Usuario1  |
|---------|---------|
|El mismo sitio donde se ha asignado el DID del usuario, sitio habilitado para Location-Based enrutamiento (sitio1)   | Llamadas enrutadas al punto de conexión de User1 en sitio1        |
|Sitio diferente del lugar donde se ha asignado el DID del usuario, sitio habilitado para Location-Based enrutamiento (Sitio2)    | Llamadas no enrutadas a puntos de conexión en el sitio2        |
|Sitio diferente del lugar donde se asigna did del usuario, sitio no habilitado para Location-Based enrutamiento (Sitio3)    | Llamadas no enrutadas a puntos de conexión en Site3        |
|Red interna desconocida (Ubicación4)   | Llamadas no enrutadas a puntos de conexión en Ubicación4        |
|Red externa desconocida (Location5)     | Llamadas no enrutadas a puntos de conexión en Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams de transferencia o reenvío de usuarios a otro Teams usuario

Cuando se trata de un punto de conexión RTC, Location-Based Routing analiza si uno o ambos usuarios están habilitados para enrutamiento de Location-Based y determina si la llamada debe transferirse o reenviarse en función de la ubicación de ambos puntos de conexión. 
 
La transferencia de llamadas requiere que el usuario que inicia la llamada resalte la llamada mientras que el reenvío de llamadas no requiere que se conteste la llamada inicial. Esto significa que las llamadas se pueden reenviar incluso si User1 no está en una ubicación para recibir llamadas entrantes (vea la tabla del usuario de Teams recibe una llamada entrante desde la sección [RTC)](#teams-user-receives-an-inbound-call-from-the-pstn) y las llamadas no se pueden transferir si User1 no puede recibir la llamada entrante. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para Location-Based enrutamiento

Un usuario que no está habilitado para Location-Based enrutamiento puede transferir o reenviar llamadas RTC a otros usuarios que no están habilitados para Location-Based enrutamiento. Normalmente, el usuario no podrá transferir o reenviar una llamada RTC a un usuario habilitado para enrutamiento de Location-Based porque Location-Based Los usuarios habilitados para enrutamiento generalmente solo pueden estar en co-ubicación en las puertas de enlace habilitadas para enrutamiento de Location-Based para llamadas RTC. La excepción es cuando un Location-Based de enrutamiento habilitado para enrutamiento se desancha a un sitio que no está habilitado para Location-Based enrutamiento. En este escenario, se permite la llamada transferida.  

Del mismo modo, un usuario que no está habilitado para Location-Based Enrutamiento solo puede recibir una transferencia o una llamada RTC reenviada de otro usuario que no está habilitado para Location-Based enrutamiento. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para Location-Based enrutamiento

Por lo general, transferir y reenviar llamadas RTC entrantes desde una puerta de enlace habilitada para Location-Based Enrutamiento solo se permite si el usuario de destino está habilitado para el enrutamiento de Location-Based y se encuentra en el mismo sitio. De lo contrario, la transferencia y el reenvío de llamadas no está permitido. 

En la tabla siguiente se muestra si el reenvío de llamadas y las transferencias de llamadas están permitidos, dependiendo de la ubicación del usuario de destino. En esta tabla, User1, ubicado en sitio1, inicia la transferencia o reenvía a otros usuarios de Teams que también están habilitados para Location-Based Routing y que se encuentran en ubicaciones diferentes.  

|Ubicación del punto de conexión de usuario de destino|Usuario1 inicia transferencia de llamadas |Usuario1 inicia el reenvío de llamadas|
|---------|---------|---------|
|Mismo sitio de red que iniciador (Usuario2)|Permitido|Permitido|
|Sitio de red diferente, sitio habilitado para Location-Based (Usuario3)|No se permiten|No se permiten|
|Sitio de red diferente, sitio no habilitado para Location-Based enrutamiento (Usuario4)|No se permiten|No se permiten|
|Red interna desconocida (User5)| No se permiten|No se permiten|
|Red externa desconocida (Usuario6)| No se permiten|No se permiten|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams de transferencia de usuarios o reenvía llamadas al punto de conexión RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para Location-Based enrutamiento

- Se permite transferir y reenviar una llamada RTC a otro número RTC. 
- Transferir y reenviar una llamada VOIP entrante a la RTC debe respetar las restricciones de omisión de pago del autor de la llamada. 
    - Si el autor de la llamada no está habilitado para Location-Based enrutamiento, se pueden transferir a cualquier puerta de enlace RTC que no esté habilitada para Location-Based enrutamiento.
    - Si el autor de la llamada está habilitado para Location-Based enrutamiento, solo se pueden transferir a una puerta de enlace habilitada Location-Based enrutamiento ubicada en el mismo sitio de red. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para Location-Based enrutamiento

- La transferencia y el reenvío entrante de una llamada RTC a otro número RTC se deben enrutar a la misma puerta de enlace habilitada Location-Based enrutamiento a la que llegó la llamada entrante. 
- Transferir y reenviar una llamada VOIP entrante a la RTC debe respetar las restricciones de omisión de pago del usuario y el autor de la llamada. 
    - Si el autor de la llamada no está habilitado para Location-Based enrutamiento, se pueden transferir a cualquier puerta de enlace RTC que no esté habilitada para Location-Based enrutamiento.
    - Si el autor de la llamada está habilitado para Location-Based enrutamiento, solo se pueden transferir a una puerta de enlace habilitada Location-Based enrutamiento ubicada en el mismo sitio de red.
 
En la tabla siguiente se muestra cómo Location-Based Enrutamiento afecta al enrutamiento de una llamada VOIP desde User1 en el sitio1 a los usuarios de distintas ubicaciones que transfieren o reenvía la llamada a un punto de conexión RTC.  

|Usuario iniciando la transferencia de llamadas o reenviar  |Transferir a RTC  |Reenviar a RTC  |
|---------|---------|---------|
|Mismo sitio de red, sitio habilitado para Location-Based enrutamiento (Usuario2)   |La transferencia de llamadas solo se puede enrutar a través de Location-Based enrutamiento habilitado Gateway1 en El sitio1, según la directiva de enrutamiento de voz de User2         |El reenvío de llamadas solo se puede enrutar Location-Based enrutamiento habilitado puerta de enlace1 en el sitio1, según la directiva de enrutamiento de voz de User2         |
|Sitio de red diferente, sitio habilitado para Location-Based (Usuario3)    |La transferencia de llamadas solo se puede enrutar a través de Location-Based enrutamiento habilitado gateway1 en el sitio1, según la directiva de enrutamiento de voz de User3         |El reenvío de llamadas solo se puede enrutar Location-Based enrutamiento habilitado puerta de enlace1 en el sitio1, según la directiva de enrutamiento de voz de User3         |
|Sitio de red diferente, sitio no habilitado para Location-Based enrutamiento (Usuario4)    |La transferencia de llamadas solo se puede enrutar a través de Location-Based enrutamiento habilitado Gateway1 en El sitio1, según la directiva de enrutamiento de voz de User4         |El reenvío de llamadas solo se puede enrutar a través de Location-Based enrutamiento habilitado gateway1 en el sitio1, según la directiva de enrutamiento de voz de User4         |
|Red interna desconocida (User5)     |La transferencia de llamadas solo se puede enrutar a través de Location-Based enrutamiento habilitado gateway1 en el sitio1, según la directiva de enrutamiento de voz de User5         |El reenvío de llamadas solo se puede enrutar Location-Based enrutamiento habilitado gateway1 en el sitio1, según la directiva de enrutamiento de voz de User5         |
|Red externa desconocida (Usuario6)   |La transferencia de llamadas solo se puede enrutar a través Location-Based enrutamiento habilitado gateway1 en el sitio1, según la directiva de enrutamiento de voz de User6        |El reenvío de llamadas solo se puede enrutar a través de Location-Based enrutamiento habilitado gateway1 en el sitio1, según la directiva de enrutamiento de voz de User6         |

### <a name="simultaneous-ringing"></a>Tono de llamada simultáneo

Cuando un usuario habilitado para enrutamiento de Location-Based recibe una llamada y tiene habilitada la llamada simultánea, enrutamiento de Location-Based analiza la ubicación de la parte que llama y los puntos de conexión de las partes llamadas para determinar si la llamada se debe enrutar. La llamada simultánea sigue las mismas Location-Based que las transferencias de llamadas y los reenvíos. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Llamada simultánea para otro Teams usuario

En la tabla siguiente se muestra si Location-Based enrutamiento permite llamar simultáneamente a diferentes usuarios para una llamada RTC entrante para Usuario1.

|Ubicación del punto de conexión de usuario de destino|Anillo simultáneo  |
|---------|---------|
|Mismo sitio de red que iniciador (Usuario2)   |Permitido         |
|Sitio de red roamed diferente habilitado para Location-Based enrutamiento (Usuario3)   |No se permiten         |
|Sitio de red roamed no habilitado para Location-Based enrutamiento (User4)   |No se permiten        |
|Red interna desconocida (User5)    | No se permiten        |
|Red externa desconocida (Usuario6)    |No se permiten        |
|El usuario de destino es un número RTC    |La llamada solo se puede enrutar a través Location-Based enrutamiento habilitado gateway1 en el sitio1, según la directiva de enrutamiento de voz de User1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Llamada simultánea a un punto de conexión RTC

En la tabla siguiente se muestra el Location-Based de enrutamiento de una llamada VOIP entrante desde User1 ubicada en el sitio1 a los usuarios de distintas ubicaciones con llamada simultánea establecida en un número RTC. 

|Ubicación de punto de conexión de usuario llamada  |El destino de llamada simultánea es el punto de conexión RTC |
|---------|---------|
|Mismo sitio de red, sitio habilitado para Location-Based enrutamiento (Usuario2)    |La llamada solo se puede enrutar a través de Location-Based Routing Gateway1 en El sitio1, según la directiva de enrutamiento de voz de User2       |
|Sitio de red diferente habilitado para Location-Based enrutamiento (Usuario3)    |La llamada solo se puede enrutar Location-Based Routing Gateway1 en El sitio1, según la directiva de enrutamiento de voz de User3        |
|Sitio de red diferente no habilitado para Location-Based enrutamiento (Usuario4)    |La llamada solo se puede enrutar Location-Based Routing Gateway1 en el Sitio1, según la directiva de enrutamiento de voz de User4         |
|Red interna desconocida (User5)    |La llamada solo se puede enrutar Location-Based Routing Gateway1 en El sitio1, según la directiva de enrutamiento de voz de User5         |
|Red externa desconocida (Usuario6)   |La llamada solo se puede enrutar Location-Based Routing Gateway1 en El sitio1, según la directiva de enrutamiento de voz de User6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Llamadas entrantes a través de la aplicación de voz (Operador automático o Cola de llamadas)

Las llamadas RTC entrantes desde una Location-Based puerta de enlace habilitada para enrutamiento pueden conectarse a un operador automático o a una cola de llamadas. Los usuarios habilitados para Location-Based enrutamiento solo pueden recibir transferencias de llamadas entrantes desde estas aplicaciones cuando se encuentran en el mismo sitio del que procede la llamada RTC entrante. 
 
El reenvío de llamadas y la llamada simultánea a los usuarios y la RTC se permiten para las transferencias de aplicaciones de voz. Completar la llamada al destino está sujeto a las mismas Location-Based reglas de enrutamiento enumeradas anteriormente.  
 
También se permite el reenvío al correo de voz.  

### <a name="delegation"></a>Delegación

Un Teams usuario puede elegir delegados que pueden realizar y recibir llamadas en su nombre. Las capacidades de delegación Teams se ven afectadas por Location-Based enrutamiento de la siguiente manera: 
- Para las llamadas salientes de Location-Based delegado habilitado para enrutamiento en nombre de un delegado, se aplican las mismas reglas. El enrutamiento de llamadas se basa en la directiva de autorización de llamadas, la directiva de enrutamiento de voz y la ubicación del delegado. Para obtener más información, [vea Teams usuario coloca una llamada saliente a la RTC.](#teams-user-places-an-outbound-call-to-the-pstn) 
- Para las llamadas RTC entrantes a un delegado, las mismas reglas de enrutamiento de Location-Based que se aplican para el reenvío de llamadas o la llamada simultánea a otros usuarios también se aplican a los delegados. Para obtener más información, vea Teams llamadas de transferencia de usuario o [reenvíos Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)otro usuario de Teams , Teams llamadas de transferencia de usuario o [reenvíos al](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)punto de conexión RTC y llamada [simultánea.](#simultaneous-ringing) Cuando un delegado establece un punto de conexión RTC como un destino de llamada simultánea, la directiva de enrutamiento de voz del delegado se usa para enrutar la llamada a la RTC. 
- Para la delegación, se recomienda que el delegado y los delegados asociados se encuentran en el mismo sitio de red. 

## <a name="other-planning-considerations"></a>Otras consideraciones de planificación

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Cambios desde una implementación de enrutamiento Location-Based local

La directiva de enrutamiento de voz del sitio de red ya no se usa. En su lugar, usamos la directiva de enrutamiento de voz del usuario. Esto significa que, para permitir que los usuarios desistan a otros sitios, la directiva de enrutamiento de voz debe incluir las puertas de enlace de los sitios desogarados. 

### <a name="technical-considerations-for-location-based-routing"></a>Consideraciones técnicas para el enrutamiento basado en ubicación

Las subredes IPv4 e IPv6 son compatibles, pero IPv6 tiene prioridad al comprobar si hay una coincidencia.

### <a name="client-support-for-location-based-routing"></a>Soporte técnico de cliente para Location-Based enrutamiento

Los siguientes Teams son compatibles:
- Teams de escritorio (Windows y Mac)
- Teams móviles (iOS y Android)
- Teams Teléfonos IP

El Teams web y Skype Empresarial no son compatibles.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Capacidades no compatibles con el enrutamiento basado en ubicación

Location-Based enrutamiento no se aplica a los siguientes tipos de interacciones. Location-Based enrutamiento no se exige cuando los Teams interactúan con los puntos de conexión RTC en los siguientes escenarios: 
- Estacionamiento o recuperación de llamadas RTC a través del estacionamiento de llamadas 
- Un usuario Skype Empresarial local o un usuario Skype Empresarial online llama a un Teams usuario  

### <a name="location-based-routing-for-conferencing"></a>Location-Based enrutamiento de conferencias

Un Location-Based habilitado para enrutamiento en una llamada RTC no puede iniciar una conferencia con otro usuario o número RTC. Se permite la conexión a operadores automáticos o colas de llamadas. Si el usuario tiene una licencia de conferencia, debe iniciar una conferencia con los usuarios relevantes y llamar a la RTC a través del puente de conferencia para iniciar una llamada de conferencia.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito de omisión de medios para Location-Based enrutamiento

Si va a implementar Location-Based enrutamiento en india, también es necesario configurar la omisión de medios. Para obtener más información, vea Planear la [omisión de medios con enrutamiento directo](direct-routing-plan-media-bypass.md) y [optimización de medios locales para enrutamiento directo.](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>Voz directa sobre IP (VoIP)

Voz directa sobre IP (VoIP) no debe implementarse con ningún equipo de telefonía en india.

## <a name="next-steps"></a>Pasos siguientes

Vaya a [Configurar la configuración de red para Location-Based enrutamiento.](location-based-routing-configure-network-settings.md)

## <a name="related-topics"></a>Temas relacionados

- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
- [Configuración de red para las características de voz en la nube en Teams](cloud-voice-network-settings.md)

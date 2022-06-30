---
title: Planear enrutamiento basado en la ubicación para el enrutamiento directo
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Obtenga información sobre cómo planear el enrutamiento Location-Based para el enrutamiento directo del teléfono de Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: d282a2cd9588c2e7104b3093d03da082e9cf388b
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562629"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planear enrutamiento basado en la ubicación para el enrutamiento directo

En algunos países y regiones, es ilegal omitir el proveedor de la red telefónica conmutada (RTC) para reducir los costos de llamadas de larga distancia. 

En este artículo se describe lo que debe saber para usar Location-Based enrutamiento para restringir la omisión de pago para los usuarios de Microsoft Teams en función de su ubicación geográfica. Este artículo se aplica solo al enrutamiento directo. Location-Based enrutamiento no se aplica al plan de llamadas ni a la conexión del operador.

Cuando esté listo para habilitar el enrutamiento Location-Based, consulte:

- [Configuración de red de enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Implementar la configuración de red para el enrutamiento de Location-Based](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)

> [!NOTE]
> No debe usar Location-Based Enrutamiento para enrutar de forma dinámica las llamadas RTC en función de la ubicación del usuario. Si lo hace, es posible que se produzcan resultados no deseados.

## <a name="overview"></a>Información general

Location-Based enrutamiento le permite restringir la omisión de pago para un usuario en función de la directiva y la ubicación geográfica del usuario en el momento de una llamada RTC de entrada o salida. 

Location-Based Routing utiliza la topología de red que defina para la región, el sitio y la subred de red. Cuando la omisión de pago está restringida para una ubicación, se asocia cada subred IP y cada puerta de enlace RTC de esa ubicación a un sitio de red. 

En el momento de una llamada RTC, la ubicación de un usuario está determinada por la subred IP a la que están conectados los puntos de conexión de Teams del usuario. Si un usuario tiene varios clientes de Teams ubicados en sitios diferentes, el enrutamiento de Location-Based exige el enrutamiento de cada cliente por separado en función de la ubicación de los puntos de conexión de Teams.

Para obtener más información sobre la configuración de red, consulte [Configuración de red para las características de voz en la nube en Teams](cloud-voice-network-settings.md).

En este artículo se supone que un sitio de red puede estar en uno de los siguientes estados:

- **Habilitado** : sitio configurado con subredes y sitios de red de inquilinos y habilitado para el enrutamiento de Location-Based.

- **No habilitado** : sitio configurado mediante sitios y subredes de red de espacio empresarial, pero no habilitado para el enrutamiento de Location-Based.

- **Desconocido** : sitio no configurado con subredes y sitios de red de inquilinos. Normalmente, estos sitios son internos a la red corporativa, pero por diseño no configurado, o externos a la red corporativa. En cualquier caso, estos sitios no están habilitados para Location-Based Enrutamiento. 

### <a name="toll-bypass-evaluation-and-outcome"></a>Evaluación y resultado de omisión de pago

Cuando se usa Location-Based enrutamiento, se evalúa una llamada entre un usuario de Teams y la RTC para determinar si la omisión de pago está restringida. En función de los resultados, la llamada se completará o no. 

Si un usuario está habilitado para Location-Based Enrutamiento y el usuario se encuentra en un sitio donde están en vigor Location-Based Restricciones de enrutamiento, la omisión de pago está restringida para ese usuario. Teams usa la siguiente información para determinar si está restringida la omisión de peaje: 

- Si el usuario de Teams está habilitado para Location-Based Enrutamiento, tal y como se define en la directiva de llamadas de Teams del usuario.

- La ubicación del sitio de red del punto de conexión del usuario de Teams y si el sitio está habilitado o no para Location-Based enrutamiento.

- La ubicación del sitio de red de la puerta de enlace RTC que usa la llamada.

- Si la puerta de enlace RTC que usa la llamada se ha habilitado para el enrutamiento de Location-Based.

- En los escenarios de transferencia, la ruta de la llamada RTC se basa en la configuración de enrutamiento de la persona que transfiere la llamada y en la configuración de enrutamiento Location-Based del usuario de Teams al que se transfiere la llamada.  

- Para los escenarios de conferencia y llamada de grupo, si un usuario de Teams para el que está restringido el desvío de pagos es o ha sido parte de la llamada.

Si una llamada no se puede completar, el usuario de Teams recibirá una notificación como se indica a continuación:

- Para las llamadas RTC salientes, aparece el siguiente mensaje en la ventana de llamada: Llamada no permitida debido a la configuración de su organización.

- Para las llamadas RTC entrantes, la llamada se enruta en función de la configuración de desvío de llamadas no respondida del usuario de Teams, normalmente al correo de voz. Si el usuario de Teams no tiene configurada la configuración de llamadas sin responder, la llamada se desconectará.

## <a name="apply-location-based-routing"></a>Aplicar enrutamiento Location-Based

Debe aplicar Location-Based Enrutamiento a lo siguiente:

- [Usuarios](#apply-location-based-routing-at-the-user-location)
- [Sitios de red](#apply-location-based-routing-at-the-network-site)
- [Puertas de enlace RTC](#apply-location-based-routing-at-the-pstn-gateway)

Tenga en cuenta los siguientes procedimientos recomendados:

- La puerta de enlace RTC y el sitio de red asociado a la puerta de enlace deben estar habilitados para Location-Based enrutamiento.

- Para realizar llamadas a través de una puerta de enlace RTC habilitada para Location-Based Enrutamiento, los usuarios también deben estar habilitados para Location-Based Enrutamiento.

- Para permitir que los usuarios habilitados para el enrutamiento de Location-Based puedan realizar llamadas RTC salientes desde un sitio de red desconocido, debe cumplirse lo siguiente:

  - La llamada debe salir desde una puerta de enlace RTC habilitada para el enrutamiento de Location-Based.
  - La puerta de enlace RTC debe configurarse con la marca GatewayLbrEnabledUserOverride establecida en True.


### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar Location-Based enrutamiento en la ubicación del usuario

La restricción de omisión de pago controla las condiciones en las que un usuario puede realizar y recibir llamadas RTC y la puerta de enlace RTC que se puede usar. 

Si un usuario está sujeto a una restricción de omisión de pago, ese usuario debe estar habilitado para Location-Based Enrutamiento. Cuando el usuario habilitado se encuentra en un sitio habilitado para Location-Based Enrutamiento, el usuario debe realizar llamadas a través de una puerta de enlace que esté conectada al sitio y habilitada para Location-Based Enrutamiento. 

Location-Based Enrutamiento funciona determinando la ubicación actual del usuario en función de la dirección IP del punto de conexión de Teams del usuario y aplica las reglas en consecuencia. La ubicación de un usuario habilitado para Location-Based Enrutamiento se puede clasificar como sigue: 

- **El usuario se encuentra en la misma Location-Based sitio habilitado para enrutamiento asociado a la puerta de enlace RTC donde se asigna su DID.**<br>En este escenario, el usuario se encuentra en un sitio de red configurado que está habilitado para Location-Based enrutamiento y el número de marcado directo (DID) del usuario termina en una puerta de enlace RTC que está en el mismo sitio de red. Por ejemplo, el usuario está en su oficina. 

- **El usuario se encuentra en otro Location-Based sitio habilitado para enrutamiento no asociado a la puerta de enlace RTC donde se asigna su DID.**<br>En este escenario, el usuario se encuentra en un sitio de red configurado que está habilitado para el enrutamiento de Location-Based y ese sitio no está asociado a la puerta de enlace RTC donde se asigna el número DID del usuario. Por ejemplo, el usuario viaja a otra oficina.  

- **El usuario se encuentra en un sitio interno que no está habilitado para Location-Based Enrutamiento.** <br>En este escenario, el usuario se encuentra en un sitio de red configurado que no está habilitado para Location-Based Enrutamiento. 

- **El usuario se encuentra en un sitio desconocido.** 
    - El usuario se encuentra dentro de la red interna que no está definida como un sitio de red. 
    - El usuario se encuentra fuera de la red interna. Por ejemplo, el usuario está en Internet en casa o en una cafetería. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar Location-Based enrutamiento en el sitio de red 

Cuando los usuarios habilitados para el enrutamiento Location-Based estén en itinerancia, los sitios de red habilitados para el enrutamiento de Location-Based ayudarán a determinar qué puertas de enlace usar. Por ejemplo:

- Si un usuario habilitado para Location-Based enrutamiento se desplaza a un sitio habilitado para Location-Based Enrutamiento, solo se puede usar la puerta de enlace RTC habilitada para Location-Based enrutamiento en ese sitio para llamadas salientes. 

- Si un usuario habilitado para Location-Based enrutamiento se desplaza a un sitio que no está habilitado para Location-Based Enrutamiento, cualquier puerta de enlace que no esté habilitada para Location-Based Enrutamiento se puede usar para las llamadas salientes.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar Location-Based enrutamiento en la puerta de enlace RTC  

Para aplicar Location-Based enrutamiento en la puerta de enlace RTC, debe hacer lo siguiente:

- Habilite la puerta de enlace para Location-Based Enrutamiento. (Las puertas de enlace deben estar habilitadas para el enrutamiento de Location-Based para asegurarse de que no pueden usarlas los usuarios que no están habilitados para Location-Based Enrutamiento).

- Asigne un sitio de red a la puerta de enlace.

A continuación, el sistema determina si un usuario determinado de un sitio determinado puede usar la puerta de enlace. 

Además, si establece GatewayLbrEnabledUserOverride en True, los usuarios habilitados de enrutamiento basado en ubicación en sitios desconocidos (por ejemplo, los usuarios que trabajan en casa) pueden realizar llamadas RTC salientes.


## <a name="restriction-rules"></a>Reglas de restricción

Las reglas de restricción dependen de si un usuario de Teams está habilitado o no para Location-Based Enrutamiento.

### <a name="user-is-enabled-for-location-based-routing"></a>El usuario está habilitado para el enrutamiento Location-Based

Cuando un usuario está habilitado para Location-Based Enrutamiento, se aplica lo siguiente:

- **Para realizar una llamada RTC de salida**, debe cumplirse una de las siguientes condiciones:

  - El punto de conexión del usuario se encuentra en un sitio habilitado para Location-Based Enrutamiento y llamadas de salida a través de una puerta de enlace RTC habilitada para el enrutamiento de Location-Based en el mismo sitio.  

  - El punto de conexión del usuario se encuentra en un sitio desconocido y llama a la salida a través de una puerta de enlace RTC que está habilitada para Location-Based enrutamiento. La puerta de enlace RTC está configurada con el parámetro GatewayLbrEnabledUserOverride establecido en True.

  - El punto de conexión del usuario se encuentra en un sitio que no está habilitado para Location-Based Enrutamiento y llama a la salida a través de una puerta de enlace RTC que no está habilitada para el enrutamiento de Location-Based.

- **Para recibir una llamada RTC de entrada**, debe cumplirse una de las siguientes condiciones: 

   - El punto de conexión de respuesta del usuario y la puerta de enlace RTC por la que entra la llamada deben encontrarse en el mismo sitio que está habilitado para el enrutamiento de Location-Based. La puerta de enlace RTC debe estar habilitada para el enrutamiento de Location-Based.

   - El punto de conexión de respuesta del usuario y la puerta de enlace RTC por la que entra la llamada deben encontrarse en el mismo sitio que no está habilitado para el enrutamiento de Location-Based. La puerta de enlace RTC no debe estar habilitada para el enrutamiento de Location-Based.  (Este escenario implica volver a redirigir la llamada RTC entrante a la entrada aunque otra puerta de enlace RTC que la que se usa normalmente para las llamadas entrantes al número de teléfono del usuario).

   - En cualquier otro escenario, como si el usuario está en itinerancia, la llamada no está permitida y se enruta a la configuración de desvío de llamadas no respondida del usuario (normalmente, correo de voz).  
   
- **Para una llamada VoIP de Teams 1:1 y una transferencia a RTC**, tenga en cuenta lo siguiente:

  - El enrutamiento de la llamada (es decir, qué puerta de enlace RTC a la salida de la llamada en) se basa en la configuración de enrutamiento del usuario que transfiere la llamada.

  - Si la transferencia se permitirá se basa en lo siguiente:
  
    - La configuración de enrutamiento Location-Based del usuario que se transfiere a RTC.
    - La ubicación del sitio de red del punto de conexión.
    - Si la ubicación está habilitada para Location-Based Enrutamiento.

    La transferencia se permitirá si el usuario que se transfiere puede realizar esa llamada RTC en su ubicación actual con la misma puerta de enlace RTC.

- **Para una llamada RTC entrante o saliente y la transferencia a otro usuario de Teams**, si se permite la transferencia depende de lo siguiente:

   - La configuración de enrutamiento del usuario que recibe la llamada transferida. 
   - La ubicación del sitio de red del punto de conexión.
   - Si la ubicación está habilitada para Location-Based Enrutamiento.

   La transferencia se permitirá si la persona que recibe la llamada transferida puede realizar o recibir esa llamada RTC en su ubicación actual con la puerta de enlace RTC que usa la llamada RTC en curso.


### <a name="user-is-not-enabled-for-location-based-routing"></a>El usuario no está habilitado para el enrutamiento Location-Based

Cuando un usuario de Teams no está habilitado para Location-Based Enrutamiento, todas las llamadas a ese usuario y desde ese usuario deben redirigirse a través de una puerta de enlace RTC que no esté habilitada para Location-Based enrutamiento. Una llamada entrante a este usuario enrutada a través de una puerta de enlace RTC habilitada para Location-Based enrutamiento se redirigirá a la configuración de desvío de llamadas no respondida del usuario (normalmente, correo de voz).

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>Flujos de decisión para llamadas entrantes y salientes

En los diagramas siguientes se muestran los flujos de decisión para llamadas entrantes y salientes.

**Llamadas entrantes**

![Diagrama que muestra LBR para llamadas entrantes](media/lbr-routing-inbound1.png "Diagrama que muestra escenarios de enrutamiento Location-Based")

**Llamadas salientes**

![Diagrama que muestra LBR para llamadas salientes](media/lbr-routing-outbound1.png "Diagrama que muestra escenarios de enrutamiento Location-Based")


## <a name="scenarios-for-location-based-routing"></a>Escenarios para el enrutamiento basado en ubicación

En esta sección se describen diferentes escenarios para restringir la omisión de pago mediante Location-Based enrutamiento. Los escenarios comparan cómo se enrutan las llamadas para los usuarios que no están habilitados para el enrutamiento de Location-Based con los usuarios habilitados para Location-Based Enrutamiento.

- [El usuario de Teams realiza una llamada saliente a la rtc.](#teams-user-places-an-outbound-call-to-the-pstn)
- [El usuario de Teams recibe una llamada entrante desde la RTC](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Los usuarios de Teams transfieren o reenvía llamadas a otro usuario de Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Las transferencias o los reenvíos de llamadas de los usuarios de Teams al extremo RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Tono de llamada simultáneo](#simultaneous-ringing)
- [Delegación](#delegation)

El siguiente diagrama muestra las restricciones habilitadas por el enrutamiento de Location-Based en cada escenario. Los usuarios, los sitios de red y las puertas de enlace que están habilitadas para Location-Based Enrutamiento tienen un borde alrededor de ellos. Use el diagrama como guía para ayudarle a comprender cómo funciona Location-Based enrutamiento en cada escenario.  

![Diagrama que muestra escenarios de enrutamiento Location-Based.](media/lbr-direct-routing.png "Diagrama que muestra escenarios de enrutamiento Location-Based")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>El usuario de Teams realiza una llamada saliente a la rtc.

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para el enrutamiento de Location-Based

Un usuario que no está habilitado para el enrutamiento de Location-Based puede realizar llamadas salientes con cualquier puerta de enlace en cualquier sitio que no esté habilitado para Location-Based Enrutamiento a través de su directiva de enrutamiento de voz asignada. Sin embargo, si una puerta de enlace está habilitada para el enrutamiento de Location-Based, el usuario no puede realizar llamadas salientes a través de la puerta de enlace incluso si está asignada a su directiva de enrutamiento de voz. Si el usuario se desplaza a un sitio habilitado para Location-Based Enrutamiento, solo podrá realizar llamadas a través de sus puertas de enlace de enrutamiento normales que no estén habilitadas para Location-Based Enrutamiento.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para enrutamiento Location-Based

En comparación, el enrutamiento de llamadas salientes para los usuarios habilitados para Location-Based Enrutamiento se ve afectado por la ubicación de red del punto de conexión del usuario. En la tabla siguiente se muestra cómo afecta Location-Based enrutamiento al enrutamiento de llamadas salientes de User1, según la ubicación de User1. 

|Ubicación del punto de conexión user1  |Enrutamiento de llamadas salientes para Usuario1  |
|---------|---------|
|Mismo sitio al que se asignó EL DID del usuario, sitio habilitado para el enrutamiento de Location-Based (Sitio1)      |Llamada enrutada a través de una puerta de enlace habilitada para enrutamiento de Location-Based (GW1) en Site1, según la directiva de enrutamiento de voz del usuario         |
|Sitio distinto al que se asigna DID del usuario, sitio habilitado para enrutamiento de Location-Based (sitio2)    |Llamada enrutada a través de una puerta de enlace habilitada para enrutamiento de Location-Based (GW2) en sitio de itinerancia2, según la directiva de enrutamiento de voz del usuario        |
|Sitio distinto al que se asigna DID del usuario, sitio no habilitado para enrutamiento de Location-Based (sitio3)  |Llamada enrutada a través de una puerta de enlace que no está habilitada para el enrutamiento de Location-Based en el sitio que no está habilitado para el enrutamiento de Location-Based (GW3), según la directiva de enrutamiento de voz del usuario       |
|Red interna desconocida (Ubicación4)    |  Las llamadas RTC no se permiten a menos que la puerta de enlace tenga GatewayLbrEnabledUserOverride establecido en True       |
|Red externa desconocida (Ubicación5)    | Las llamadas RTC no se permiten a menos que la puerta de enlace tenga GatewayLbrEnabledUserOverride establecido en True       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>El usuario de Teams recibe una llamada entrante desde la RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para el enrutamiento de Location-Based

Un usuario que no está habilitado para el enrutamiento de Location-Based puede recibir una llamada entrante desde la puerta de enlace que no está habilitada para Location-Based enrutamiento desde la que entra el número DID asignado. Si el usuario se desplaza a un sitio que no está habilitado para el enrutamiento de Location-Based, puede seguir recibiendo llamadas a través de sus puertas de enlace RTC normales.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para enrutamiento Location-Based

En comparación, los usuarios habilitados para Location-Based Enrutamiento solo pueden recibir llamadas entrantes desde la puerta de enlace RTC a la que se asignaron sus DID cuando se encuentran en el mismo sitio. En la tabla siguiente se muestra cómo User1 recibe llamadas entrantes cuando el usuario1 se mueve a diferentes ubicaciones de red. Si la llamada no se enruta al punto de conexión del usuario, irá a la configuración de desvío de llamadas no respondida del usuario, si la configuración está configurada. Normalmente, las llamadas se desvía al correo de voz.  

|Ubicación del punto de conexión user1  |Enrutamiento de llamadas entrantes a Usuario1  |
|---------|---------|
|El sitio está habilitado para Location-Based Routing (Sitio1)   | Llamadas enrutadas al punto de conexión del usuario1 en Site1        |
|Sitio distinto al que se asigna DID del usuario, sitio habilitado para enrutamiento de Location-Based (sitio2)    | Llamadas no enrutadas a puntos de conexión en Site2        |
|Sitio distinto al que se asigna DID del usuario, sitio no habilitado para enrutamiento de Location-Based (sitio3)    | Llamadas no enrutadas a puntos de conexión en Site3        |
|Red interna desconocida (Ubicación4)   | Llamadas no enrutadas a puntos de conexión en Ubicación4        |
|Red externa desconocida (Ubicación5)     | Las llamadas no se enrutan a los puntos de conexión en Ubicación5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Los usuarios de Teams transfieren o reenvía llamadas a otro usuario de Teams

Cuando hay un punto de conexión RTC implicado, el enrutamiento de Location-Based analiza si uno o ambos usuarios están habilitados para Location-Based Enrutamiento y determina si la llamada se debe transferir o desviar en función de la ubicación de ambos puntos de conexión. 
 
La transferencia de llamada requiere que el usuario iniciador recoja la llamada, mientras que el desvío de llamadas no requiere que se responda la llamada inicial. Las llamadas se pueden desviar incluso si el usuario1 no se encuentra en una ubicación para recibir llamadas entrantes (vea la tabla en teams, el [usuario recibe una llamada entrante de la sección RTC](#teams-user-receives-an-inbound-call-from-the-pstn) ) y las llamadas no se pueden transferir si el usuario1 no puede recibir la llamada entrante. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para el enrutamiento de Location-Based

Un usuario que no esté habilitado para Location-Based Enrutamiento puede transferir o desviar llamadas RTC a otros usuarios que no estén habilitados para Location-Based Enrutamiento. Los usuarios habilitados para Location-Based Enrutamiento suelen encontrarse en Location-Based puertas de enlace habilitadas para enrutamiento para llamadas RTC. Por lo tanto, los usuarios que no están habilitados no pueden transferir ni reenviar una llamada RTC a un usuario habilitado para el enrutamiento de Location-Based. La excepción es cuando un usuario habilitado Location-Based Enrutamiento se desplaza a un sitio que no está habilitado para Location-Based enrutamiento. En este escenario, se permite la llamada transferida.  

Del mismo modo, un usuario que no está habilitado para Location-Based enrutamiento solo puede recibir una transferencia o una llamada RTC reenviada de otro usuario que no está habilitado para el enrutamiento de Location-Based. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para enrutamiento Location-Based

La transferencia y el reenvío de llamadas RTC entrantes desde una puerta de enlace habilitada para Location-Based Enrutamiento solo se permite si el usuario de destino está habilitado para Location-Based Enrutamiento y se encuentra en el mismo sitio. En caso contrario, no se permite transferir ni desviar llamadas. 

La tabla siguiente muestra si se permiten el desvío de llamadas y las transferencias de llamadas, según la ubicación del usuario de destino. En esta tabla, Usuario1, ubicado en Sitio1, inicia la transferencia o reenvío a otros usuarios de Teams que también están habilitados para Location-Based Enrutamiento y que se encuentran en ubicaciones diferentes.  

|Ubicación del punto de conexión del usuario de destino|Usuario1 inicia la transferencia de llamadas |User1 inicia el desvío de llamadas|
|---------|---------|---------|
|El mismo sitio de red que el iniciador (Usuario2)|Permitido|Permitido|
|Sitio de red diferente, sitio habilitado para enrutamiento de Location-Based (usuario3)|No se permiten|No se permiten|
|Sitio de red diferente, sitio no habilitado para enrutamiento de Location-Based (usuario4)|No se permiten|No se permiten|
|Red interna desconocida (Usuario5)| No se permiten|No se permiten|
|Red externa desconocida (Usuario6)| No se permiten|No se permiten|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Las transferencias o los reenvíos de llamadas de los usuarios de Teams al extremo RTC

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuario no habilitado para el enrutamiento de Location-Based

- Se permite transferir y reenviar una llamada RTC a otro número de RTC. 

- Transferir y reenviar una llamada VOIP entrante a la RTC debe respetar las restricciones de omisión de pago del autor de la llamada. 

    - Si el autor de la llamada no está habilitado para Location-Based Enrutamiento, se puede transferir a cualquier puerta de enlace RTC que no esté habilitada para Location-Based Enrutamiento.
    - Si el autor de la llamada está habilitado para Location-Based Enrutamiento, solo se puede transferir a una puerta de enlace habilitada para enrutamiento Location-Based ubicada en el mismo sitio de red. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuario habilitado para enrutamiento Location-Based

- La transferencia y el desvío de llamadas entrantes de una llamada RTC a otro número de RTC deben redirigirse a la misma Location-Based puerta de enlace habilitada para enrutamiento a la que llegó la llamada entrante.

- La transferencia y el reenvío de una llamada VOIP entrante a la RTC deben respetar tanto al autor de la llamada como a las restricciones de omisión de pago del usuario que ha llamado. 

    - Si el autor de la llamada no está habilitado para Location-Based Enrutamiento, se puede transferir a cualquier puerta de enlace RTC que no esté habilitada para Location-Based Enrutamiento.

    - Si el autor de la llamada está habilitado para Location-Based Enrutamiento, solo se puede transferir a una puerta de enlace habilitada para enrutamiento Location-Based ubicada en el mismo sitio de red.
 
En la tabla siguiente se muestra cómo afecta el enrutamiento de Location-Based al enrutamiento de una llamada VOIP desde Location-Based Usuario habilitado para enrutamiento1 en site1 a usuarios de diferentes ubicaciones que transfieren o desvía la llamada a un punto de conexión RTC.  

|Usuario que inicia la transferencia de llamadas o el desvío de llamadas  |Transferir o reenviar a RTC  |
|---------|---------|
|Mismo sitio de red, sitio habilitado para enrutamiento de Location-Based (usuario2)   |La llamada RTC resultante solo se permitirá si la ruta calculada basada en la directiva de enrutamiento de voz del usuario2 da como resultado una ruta a través de Location-Based Puerta de enlace habilitada para enrutamiento1 en Site1         |
|Sitio de red diferente, sitio habilitado para enrutamiento de Location-Based (usuario3)    |La llamada RTC resultante solo se permitirá si la ruta calculada basada en la directiva de enrutamiento de voz de User3 da como resultado una ruta a través de Location-Based puerta de enlace habilitada para enrutamiento1 en Site1 |
|Sitio de red diferente, sitio no habilitado para enrutamiento de Location-Based (usuario4)    |La llamada RTC resultante solo se permitirá si la ruta calculada basada en la directiva de enrutamiento de voz de User4 da como resultado una ruta a través de Location-Based puerta de enlace habilitada para enrutamiento1 en site1          |
|Red interna desconocida (Usuario5)     |La llamada RTC resultante solo se permitirá si la ruta calculada basada en la directiva de enrutamiento de voz de User5 da como resultado una ruta a través de Location-Based puerta de enlace habilitada para enrutamiento1 en Site1          |
|Red externa desconocida (Usuario6)   |La llamada RTC resultante solo se permitirá si la ruta calculada basada en la directiva de enrutamiento de voz de User6 da como resultado una ruta a través de Location-Based Puerta de enlace habilitada para enrutamiento1 en Site1          |

### <a name="simultaneous-ringing"></a>Tono de llamada simultáneo

Cuando un usuario habilitado para el enrutamiento de Location-Based recibe una llamada y tiene habilitada la llamada simultánea, el enrutamiento de Location-Based analiza la ubicación del receptor de la llamada y los puntos de conexión de las partes a las que se llama para determinar si se debe enrutar la llamada. La llamada simultánea sigue las mismas reglas de Location-Based que los desvíos y transferencias de llamadas. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Llamada simultánea para otro usuario de Teams

En la tabla siguiente se muestra si el enrutamiento de Location-Based permite la llamada simultánea a diferentes usuarios para una llamada RTC de entrada para Usuario1.

|Ubicación del punto de conexión del usuario de destino|Llamada simultánea  |
|---------|---------|
|El mismo sitio de red que el iniciador (Usuario2)   |Permitido         |
|Sitio de red itinerancia diferente habilitado para el enrutamiento de Location-Based (Usuario3)   |No se permiten         |
|Sitio de red itinerancia no habilitado para el enrutamiento de Location-Based (usuario4)   |No se permiten        |
|Red interna desconocida (Usuario5)    | No se permiten        |
|Red externa desconocida (Usuario6)    |No se permiten        |
|El usuario de destino es un número DE RTC    |La llamada solo se puede enrutar a través de Location-Based Puerta de enlace habilitada para enrutamiento1 en Site1, según la directiva de enrutamiento de voz del usuario1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Llamar simultáneamente a un punto de conexión RTC

En la tabla siguiente se muestra Location-Based Comportamiento de enrutamiento para una llamada VoIP entrante desde Location-Based Usuario habilitado para enrutamiento1 ubicado en Site1 a usuarios en diferentes ubicaciones con llamadas simultáneas establecidas en un número RTC. 

|Ubicación del punto de conexión del usuario denominada  |El destino de llamada simultánea es el punto de conexión RTC |
|---------|---------|
|Mismo sitio de red, sitio habilitado para enrutamiento de Location-Based (usuario2)    |La llamada RTC resultante solo se permitirá si la ruta calculada basada en la directiva de enrutamiento de voz del usuario2 da como resultado una ruta a través de Location-Based Puerta de enlace habilitada para enrutamiento1 en Site1        |
|Sitio de red diferente habilitado para el enrutamiento Location-Based (Usuario3)    |La llamada RTC resultante solo se permitirá si la ruta calculada basada en la directiva de enrutamiento de voz de User3 da como resultado una ruta a través de Location-Based puerta de enlace habilitada para enrutamiento1 en Site1         |
|Otro sitio de red no habilitado para el enrutamiento de Location-Based (usuario4)    |La llamada RTC resultante solo se permitirá si la ruta calculada basada en la directiva de enrutamiento de voz de User4 da como resultado una ruta a través de Location-Based puerta de enlace habilitada para enrutamiento1 en site1          |
|Red interna desconocida (Usuario5)    |La llamada RTC resultante solo se permitirá si la ruta calculada basada en la directiva de enrutamiento de voz de User5 da como resultado una ruta a través de Location-Based puerta de enlace habilitada para enrutamiento1 en Site1          |
|Red externa desconocida (Usuario6)   |La llamada RTC resultante solo se permitirá si la ruta calculada basada en la directiva de enrutamiento de voz de User6 da como resultado una ruta a través de Location-Based Puerta de enlace habilitada para enrutamiento1 en Site1          |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>Llamadas entrantes a través de aplicaciones de voz (operador automático o cola de llamadas)

Las llamadas RTC entrantes desde una puerta de enlace habilitada para enrutamiento Location-Based pueden conectarse a un operador automático o a una cola de llamadas. 

Los usuarios habilitados para Location-Based Enrutamiento son compatibles con la recepción de transferencias de llamadas entrantes para estas aplicaciones cuando se encuentran en el mismo sitio desde el que se origina la llamada RTC entrante.
 
El desvío de llamadas y las llamadas simultáneas a los usuarios y RTC se permiten para las transferencias de aplicaciones de voz. Completar la llamada al destino está sujeta a las mismas reglas de enrutamiento Location-Based enumeradas anteriormente.  
 
También se permite reenviar al correo de voz.  

### <a name="delegation"></a>Delegación

Un usuario de Teams puede elegir delegados que puedan realizar y recibir llamadas en su nombre. Las capacidades de delegación en Teams se ven afectadas por el enrutamiento de Location-Based como se indica a continuación: 

- Para las llamadas salientes de un delegado habilitado para enrutamiento de Location-Based en nombre de un delegador, se aplican las mismas reglas. El enrutamiento de llamadas se basa en la directiva de autorización de llamadas del delegado, la directiva de enrutamiento de voz y la ubicación. Para obtener más información, vea [El usuario de Teams realiza una llamada saliente a la RTC](#teams-user-places-an-outbound-call-to-the-pstn). 

- Para las llamadas RTC entrantes a un delegador, también se aplican a los delegados las mismas reglas de enrutamiento Location-Based que se aplican al desvío de llamadas o a la llamada simultánea a otros usuarios. Para obtener más información, vea [Transferir o desviar llamadas de usuarios de Teams a otro usuario de Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user), [Transferir o desviar llamadas de usuarios de Teams al extremo RTC](#teams-user-transfers-or-forwards-call-to-pstn-endpoint) y [Llamada simultánea](#simultaneous-ringing). Cuando un delegado establece un punto de conexión RTC como destino de llamada simultánea, la directiva de enrutamiento de voz del delegado se usa para redirigir la llamada a la RTC. 

- Para la delegación, Microsoft recomienda que el delegador y los delegados asociados se encuentren en el mismo sitio de red. 

## <a name="other-planning-considerations"></a>Otras consideraciones de planificación

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Cambios de una implementación de enrutamiento Location-Based local

Ya no se usa la directiva de enrutamiento de voz del sitio de red. En su lugar, usamos la directiva de enrutamiento de voz del usuario. Para permitir a los usuarios desplazarse a otros sitios, la directiva de enrutamiento de voz debe incluir las puertas de enlace de los sitios itinerancia. 

### <a name="technical-considerations-for-location-based-routing"></a>Consideraciones técnicas para el enrutamiento basado en ubicación

Las subredes IPv4 e IPv6 son compatibles, pero IPv6 tiene prioridad al buscar una coincidencia.

### <a name="client-support-for-location-based-routing"></a>Soporte técnico al cliente para el enrutamiento de Location-Based

Se admiten los siguientes clientes de Teams:
- Clientes de escritorio de Teams (Windows y Mac)
- Clientes móviles de Teams (iOS y Android)
- Teléfonos IP de Teams

El cliente web de Teams y los clientes de Skype Empresarial no son compatibles.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Capacidades no compatibles con el enrutamiento basado en ubicación

Location-Based Enrutamiento no se aplica a los siguientes tipos de interacciones. Location-Based El enrutamiento no se aplica cuando los puntos de conexión de Teams interactúan con puntos de conexión RTC en los siguientes escenarios: 

- Estacionamiento o recuperación de llamadas RTC a través del estacionamiento de llamadas 

- Un usuario de Skype Empresarial local o un usuario de Skype Empresarial Online llama a un usuario de Teams  

### <a name="location-based-routing-for-conferencing"></a>Location-Based enrutamiento para conferencias

Un usuario habilitado para enrutamiento de Location-Based en una llamada RTC no puede iniciar una conferencia con otro usuario o número de RTC. Se permite la conexión a operadores automáticos o colas de llamadas.

Si el usuario tiene una licencia de audioconferencia, debe iniciar una conferencia con los usuarios relevantes y llamar a la RTC a través del puente de conferencia para iniciar una llamada de conferencia.

En una llamada de conferencia iniciada por un usuario sin una licencia de audioconferencia, no se permite agregar participantes RTC si hay o ha sido al menos un usuario habilitado para enrutamiento Location-Based en la llamada de conferencia. Si al menos un participante de RTC forma parte de una llamada de conferencia o forma parte de ella antes de invitar a algún participante habilitado para enrutamiento Location-Based a unirse a la llamada, Location-Based los participantes habilitados para enrutamiento no se pueden agregar a la llamada.

Si el usuario habilitado Location-Based enrutamiento se une a la llamada de conferencia desde un sitio interno que no está habilitado para Location-Based enrutamiento, no se aplican las restricciones del párrafo anterior. 

Las conferencias en red para Audioconferencia NO se deben implementar con ningún equipo de telefonía en India.


### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito de omisión de medios para enrutamiento de Location-Based

Si va a implementar Location-Based Enrutamiento en India, es un requisito configurar también la omisión de medios. Para obtener más información, consulta [Planear la omisión de medios con Enrutamiento directo](direct-routing-plan-media-bypass.md) y [Optimización de medios locales para enrutamiento directo](direct-routing-media-optimization.md).

### <a name="direct-voice-over-ip-voip"></a>Voz directa sobre IP (VoIP)

Direct Voice over IP (VoIP) no se debe implementar con ningún equipo de telefonía en la India.


## <a name="related-articles"></a>Artículos relacionados

- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
- [Configuración de red para las características de voz en la nube en Teams](cloud-voice-network-settings.md)

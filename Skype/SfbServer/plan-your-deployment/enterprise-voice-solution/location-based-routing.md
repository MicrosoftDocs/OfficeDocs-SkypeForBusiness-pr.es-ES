---
title: Planear el enrutamiento basado en ubicación en Skype Empresarial
ms.reviewer: null
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
ms.custom: null
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: 'Planeación del enrutamiento basado en ubicación en Skype Empresarial Server Telefonía IP empresarial, incluida la interacción con llamadas y delegación simultáneas, y escenarios admitidos para el enrutamiento basado en ubicación.'
---

# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planear el enrutamiento basado en ubicación en Skype Empresarial

Planeación del enrutamiento basado en ubicación en Skype Empresarial Server Telefonía IP empresarial, incluida la interacción con llamadas y delegación simultáneas, y escenarios admitidos para el enrutamiento basado en ubicación.

Location-Based enrutamiento permite restringir el enrutamiento de llamadas entre extremos VoIP y puntos de conexión RTC en función de la ubicación de las partes en la llamada. Location-Based routing es una característica de administración de llamadas que controla cómo se enruta Skype Empresarial Server. Aplica reglas de autorización de llamadas sobre si las llamadas se pueden enrutar a puntos de conexión PBX o RTC en función de la Skype Empresarial geográfica del autor de la llamada.

Location-Based Routing presenta un nuevo conjunto de reglas que modifica el enrutamiento de llamadas RTC nacionales e internacionales para evitar la omisión de peaje. Location-Based routing proporciona la flexibilidad para establecer el ámbito de estas reglas en regiones específicas, puertas de enlace específicas o solo para un conjunto específico de usuarios.

Los siguientes escenarios ilustran los principales tipos de restricciones que Location-Based el enrutamiento puede aplicar:

- Egress: el enrutamiento de Location-Based puede aplicar llamadas salientes a la salida a una puerta de enlace RTC que se encuentra en la misma región en la que se encuentra el autor de la llamada para evitar la omisión de peaje RTC, lo que impide que las llamadas a la salida a una puerta de enlace RTC ubicada en una región diferente como el autor de la llamada.

- Llamadas de entrada: el enrutamiento de Location-Based puede impedir que las llamadas RTC entrantes llamen Skype Empresarial extremos si la puerta de enlace RTC enruta la llamada entrante no se encuentra en la misma región que el usuario Skype Empresarial llamada.

- Regiones desconocidas: el enrutamiento de Location-Based restringe las llamadas RTC entrantes y salientes a y desde usuarios que se encuentran en ubicaciones indeterminadas (es decir, usuarios remotos que se conectan desde Internet o se encuentran en regiones desconocidas).

- Regiones internacionales: Location-Based routing exige el enrutamiento de llamadas salientes a través de puertas de enlace RTC internacionales si no se encuentra una puerta de enlace local a la ubicación del usuario.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Instrucciones sobre dónde aplicar el Location-Based enrutamiento

Location-Based el enrutamiento según la situación se puede aplicar en la ubicación del sitio de red de extremo del usuario o en la ubicación del sitio de red de la puerta de enlace RTC. En este tema se proporcionan instrucciones sobre cómo Location-Based se aplica el enrutamiento.

### <a name="applying-location-based-routing-at-the-users-location"></a>Aplicar Location-Based enrutamiento en la ubicación del usuario

Location-Based Routing aprovecha las mismas regiones de red, sitios y subredes definidas en Skype Empresarial Server usadas por E9-1-1, CAC y Omisión de medios para aplicar restricciones de enrutamiento de llamadas para evitar la omisión de números RTC. La ubicación de un usuario viene determinada por la subred IP de los puntos Skype Empresarial de conexión del usuario están conectados desde. Cada subred IP está asociada a un sitio de red, que se agregan a las regiones de red definidas por el administrador. Location-Based se aplica el enrutamiento basado en el sitio de red del usuario.

Location-Based reglas de enrutamiento se aplican por sitio de red, lo que significa que se aplicará un conjunto determinado de reglas a todos los puntos de conexión habilitados para el enrutamiento de Location-Based que se encuentran dentro del mismo sitio de red. Los administradores pueden aplicar Location-Based enrutamiento a los sitios de red que lo requieran.

Las directivas de enrutamiento de voz se pueden definir por sitio de red para definir una puerta de enlace RTC determinada que deben usar todos los usuarios ubicados en el sitio de red para llamar a números de teléfono RTC. Estas directivas de enrutamiento de voz tendrán prioridad sobre el enrutamiento definido por la directiva de voz del usuario cuando el usuario se encuentra en un sitio de red habilitado para el enrutamiento de Location-Based y evitará el enrutamiento de llamadas a través de otras puertas de enlace RTC habilitadas para el enrutamiento de Location-Based. Cuando un Skype Empresarial realiza una llamada RTC, la directiva de voz del usuario determina si se puede autorizar al usuario a realizar la llamada. Si la directiva de voz del usuario permite al usuario realizar la llamada, Location-Based Routing determina de qué puerta de enlace RTC debe realizar la salida de la llamada. Location-Based routing realiza esta determinación en función de la ubicación del usuario.

Una ubicación de usuario se puede clasificar de las siguientes maneras:

- El usuario se encuentra en un sitio de red conocido habilitado para Location-Based Routing y su número DID (Direct Inward Dial) finaliza en una puerta de enlace RTC colocada en el mismo sitio de red (es decir, office). El enrutamiento de las llamadas salientes se realizará a través de la directiva de enrutamiento de voz del sitio de red en el que se encuentra el usuario. Las llamadas RTC entrantes al usuario se enrutan a puntos de conexión que se encuentran en el mismo sitio de red que la puerta de enlace RTC.

- El usuario se encuentra en un sitio de red conocido que es diferente del sitio de red donde se encuentra la puerta de enlace RTC. (es decir, el usuario ha viajado a otra oficina corporativa). El enrutamiento de llamadas salientes estará usando la directiva de enrutamiento de voz del sitio de red en el que se encuentra el usuario. Las llamadas RTC entrantes al usuario no se enrutarán a puntos de conexión que se encuentran en sitios diferentes a la puerta de enlace RTC para evitar el desvío de los peajes RTC.

- Cuando un usuario se encuentra en un sitio de red desconocido para la implementación de Skype Empresarial Server, el enrutamiento de llamadas salientes se basará en la directiva de voz asignada al usuario a puertas de enlace RTC no enlazadas a restricciones de enrutamiento Location-Based. Las llamadas RTC entrantes no se enrutarán a puntos de conexión que se encuentran en sitios de red desconocidos para evitar la omisión de peaje RTC.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Aplicar Location-Based enrutamiento en la ubicación de la puerta de enlace RTC

Las llamadas enrutadas a través de puertas de enlace RTC y PBX pueden requerir restricciones Location-Based de enrutamiento en función de la ubicación de dichos sistemas. Location-Based enrutamiento se puede habilitar en la granularidad por tronco.

Location-Based Routing presenta el siguiente conjunto de reglas cuando se habilita en un tronco:

- Cuando Location-Based enrutamiento se habilita por tronco, las reglas que se definen en ese tronco se aplicarán solo a las llamadas enrutadas a través de ese tronco.

- Para evitar la omisión de los peajes RTC donde las llamadas se originan desde un sitio de red diferente al sitio de red donde se encuentra la puerta de enlace RTC, Location-Based Routing presenta la asociación de un sitio de red a un tronco determinado. Esto define el sitio de red que permite que las llamadas se enrutan a un tronco determinado.

Los troncos se pueden habilitar para Location-Based enrutamiento de dos maneras:

- El tronco se define para una puerta de enlace RTC que salida de llamadas a la RTC. Las llamadas entrantes enrutadas por un tronco de este tipo se enrutarán solo a los puntos de conexión ubicados dentro del mismo sitio de red que el tronco.

- El tronco se define para un servidor de mediación del mismo nivel que no hace llamadas de salida a los usuarios rtc y de servicios con teléfonos heredados en ubicaciones estáticas (por ejemplo, teléfonos PBX). Para esta configuración en particular, todas las llamadas entrantes enrutadas por un tronco de este tipo se considerarán originadas desde el mismo sitio de red que el tronco. Las llamadas de los usuarios de PBX tendrán el mismo Location-Based de enrutamiento que Skype Empresarial usuarios que se encuentran en el mismo sitio de red que el tronco. Si dos sistemas PBX ubicados en sitios de red independientes están conectados a través de Skype Empresarial Server, el enrutamiento de Location-Based permitirá el enrutamiento de un punto de conexión PBX en un sitio de red a otro punto de conexión PBX en el otro sitio de red. Este escenario no se bloqueará mediante Location-Based enrutamiento. Además de este escenario y de forma similar que un usuario de Skype Empresarial en la misma ubicación, los puntos de conexión conectados a un servidor de mediación del mismo nivel con esta configuración podrán realizar o recibir llamadas desde y hacia otro servidor del mismo nivel del servidor de mediación que no enrute llamadas a la RTC (es decir, un extremo conectado a una PBX diferente) independientemente del sitio de red al que esté asociado el servidor de mediación. Todas las llamadas entrantes, llamadas salientes, transferencias de llamadas y reenvíos de llamadas que impliquen extremos RTC estarán sujetas al enrutamiento basado en ubicación para usar solo puertas de enlace RTC definidas como locales para dicho servidor de mediación del mismo nivel.

## <a name="scenarios-for-location-based-routing"></a>Escenarios para Location-Based enrutamiento

Location-Based routing aplica las siguientes reglas generales al enrutar llamadas en los siguientes escenarios.

### <a name="outgoing-calls"></a>Llamadas salientes

El enrutamiento de llamadas salientes de usuarios habilitados para Location-Based enrutamiento se ve afectado por la ubicación de red del extremo del usuario. En la tabla siguiente se muestra cómo Location-Based routing afecta al enrutamiento de llamadas salientes en función de la ubicación del extremo del autor de la llamada.

**Llamador que realiza una llamada saliente a la RTC**

|&nbsp;|Extremo de usuario ubicado en un sitio de red habilitado para Location-Based enrutamiento|Extremo de usuario ubicado en un sitio de red desconocido o no habilitado para el Location-Based enrutamiento|
|:-----|:-----|:-----|
|Autorización de llamadas salientes   |La llamada se autoriza en función de la directiva de voz del usuario   |La llamada se autoriza en función de la directiva de voz del usuario   |
|Enrutamiento de llamadas salientes   |La llamada se enruta según la directiva de enrutamiento de voz del sitio de red   |La llamada se enruta según la directiva de voz del usuario y solo a través de troncos no habilitados para Location-Based enrutamiento (si está disponible)   |

### <a name="incoming-calls"></a>Llamadas entrantes

El enrutamiento de llamadas entrantes a usuarios habilitados para Location-Based enrutamiento depende de la ubicación del extremo del usuario. El enrutamiento de las llamadas entrantes se ve afectado de la siguiente manera. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento de Location-Based y el extremo se encuentra en el mismo sitio de red que la puerta de enlace RTC, se enruta la llamada. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento de Location-Based y el extremo se encuentra en un sitio de red diferente a la puerta de enlace RTC, la llamada no se enruta. Cuando un usuario no tiene puntos de conexión ubicados en el mismo sitio de red que la puerta de enlace RTC desde la que se origina la llamada entrante, la llamada entrante se enruta directamente al correo de voz del usuario y se enviará una notificación de llamada perdida a la parte llamada.

La configuración de reenvío de llamadas de un usuario que está habilitado para el enrutamiento de Location-Based se seguirá aplicando, sin embargo, las llamadas reenviadas estarán sujetas a Location-Based restricciones de enrutamiento del usuario.

En la tabla siguiente se muestra cómo Location-Based routing afecta al enrutamiento de llamadas entrantes en función de la ubicación del extremo del destinatario. El sitio de red de la puerta de enlace RTC está habilitado para el enrutamiento de Location-Based y el enrutamiento de Location-Based solo permite el enrutamiento de llamadas RTC a puntos de conexión dentro del mismo sitio de red.

**Destinatario de llamada que recibe una llamada entrante de la RTC**

|&nbsp;|Punto de conexión del destinatario de la llamada ubicado en el mismo sitio de red que la puerta de enlace RTC|El extremo del destinatario no se encuentra en el mismo sitio de red que la puerta de enlace RTC|Punto de conexión del destinatario de la llamada ubicado en un sitio de red desconocido o no habilitado para el Location-Based enrutamiento|
|:-----|:-----|:-----|:-----|
|Enrutamiento de llamadas RTC entrantes   |La llamada entrante se enruta a los puntos de conexión del destinatario   |La llamada entrante no se enruta a los puntos de conexión del destinatario   |La llamada entrante no se enruta a los puntos de conexión del destinatario   |

### <a name="call-transfers-and-call-forwarding"></a>Transferencias de llamadas y reenvío de llamadas

Cuando se trata de un extremo RTC, Location-Based Routing analiza la ubicación del extremo de la calle y el punto de conexión al que se transferirá o reenviará la llamada (es decir, destino de transferencia/reenvío). Location-Based routing determina si la llamada debe transferirse o reenviarse en función de la ubicación de ambos extremos.

En la tabla siguiente se muestra el escenario de un usuario Skype Empresarial en una llamada con un extremo RTC y el usuario Skype Empresarial transfiere la llamada a otro Skype Empresarial usuario. Según la ubicación del sitio de red del punto de conexión del destinatario de la transferencia, Location-Based Routing afecta al enrutamiento de la transferencia de llamadas o el reenvío.

**Iniciar la transferencia de llamadas o reenviar**

|Usuario que inicia la transferencia/reenvío de llamadas|El extremo de destino se encuentra en el mismo sitio de red que el usuario que inicia la transferencia o reenvío de llamadas|El extremo de destino se encuentra en un sitio de red diferente como usuario que inicia la transferencia o reenvío de llamadas|El extremo de destino está en sitio de red desconocido o sitio de red no habilitado para el Location-Based enrutamiento
|:-----|:-----|:-----|:-----|
|Usuario de Skype® Empresarial   |Se permite la transferencia o reenvío de llamadas   |No se permite la transferencia o el reenvío de llamadas   |No se permite la transferencia o el reenvío de llamadas   |

Por ejemplo: un Skype Empresarial en una llamada con un extremo RTC transfiere la llamada a otro usuario Skype Empresarial que se encuentra en el mismo sitio de red. En este caso, se permite la transferencia de llamadas.

En la tabla siguiente se muestra el escenario de un usuario Skype Empresarial en una llamada con otro usuario de Skype Empresarial y uno de los usuarios transfiere la llamada a un extremo RTC. Según la ubicación del usuario al que se transfiera la llamada, la tabla detalla cómo afecta Location-Based enrutamiento a la llamada.

**Transferencia de llamadas o reenvío al punto de conexión RTC**

|Destino de extremo de transferencia/reenvío de llamadas|Skype Empresarial usuarios en el mismo sitio de red|Skype Empresarial usuarios en diferentes sitios de red|Uno o ambos usuarios Skype Empresarial sitio de red desconocido o sitio de red no habilitado para el Location-Based enrutamiento|
|:-----|:-----|:-----|:-----|
|Extremo RTC   |Reenvío de llamadas o transferencia permitidos por la directiva de enrutamiento de voz del sitio del usuario transferido   |Reenvío de llamadas o transferencia permitidos por la directiva de enrutamiento de voz del sitio del usuario transferido   |Reenvío de llamadas o transferencia permitidos por la directiva de voz del usuario transferido solo a través de troncos no habilitados para el Location-Based enrutamiento   |

Por ejemplo: un Skype Empresarial en una llamada con otro usuario de Skype Empresarial que se encuentra en el mismo sitio de red transfiere la llamada a un extremo RTC y se permite la transferencia de llamadas.

### <a name="simultaneous-ringing"></a>Llamadas simultáneas

Cuando la parte llamada tiene habilitada la llamada simultánea, Location-Based Routing analiza la ubicación de la parte que llama y los extremos de las partes llamadas para determinar si se debe enrutar la llamada.

En la tabla siguiente se muestra un usuario configurado con llamadas simultáneas y el destino de llamada simultánea es un usuario en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido.

****

|Llamada RTC entrante para|Ubicado en el mismo sitio de red que el destinatario de la llamada|Ubicado en un sitio de red diferente del destinatario de la llamada|Ubicado en un sitio de red desconocido o no habilitado para el Location-Based enrutamiento|
|:-----|:-----|:-----|:-----|
|Usuario de Skype® Empresarial   |Anillo simultáneo permitido   |Anillo simultáneo no permitido   |Anillo simultáneo no permitido   |

En la tabla siguiente se muestra una llamada de un usuario de Skype Empresarial (es decir, Skype Empresarial llamador) en el mismo sitio de red, en un sitio de red diferente o desde un sitio de red desconocido. El destinatario de la llamada tiene un punto de conexión RTC (es decir, teléfono móvil) configurado como un destino de anillo simultáneo. En este escenario, Location-Based Routing determinará si la llamada se debe enrutar al destino de llamada simultánea (es decir, el teléfono móvil) del destinatario de la llamada o no.

****

|Destino de anillo simultáneo|Ubicado en el mismo sitio de red que el destinatario de la llamada|Ubicado en un sitio de red diferente del destinatario de la llamada|Ubicado en un sitio de red desconocido o no habilitado para el Location-Based enrutamiento|
|:-----|:-----|:-----|:-----|
|Extremo RTC   |Anillo simultáneo permitido a través de la directiva de enrutamiento de voz del sitio del autor de la llamada   |Anillo simultáneo permitido a través de la directiva de enrutamiento de voz del sitio del autor de la llamada   |Anillo simultáneo permitido a través de la directiva de voz del autor de la llamada a troncos no habilitados para Location-Based enrutamiento   |

### <a name="skype-for-business-cumulative-update-4"></a>Skype Empresarial acumulativa 4

Con la actualización acumulativa 4, verá lo siguiente:

- Location-Based el enrutamiento seguirá habilitado a través de la directiva de voz, incluidos los Skype Empresarial móviles.

- El comportamiento de las llamadas Skype Empresarial los clientes móviles se basarán en si están habilitados para el enrutamiento Location-Based y el cliente de comunicación. Esto está diseñado para ser estático, pero puede haber, en determinadas situaciones, un esfuerzo para asociar un cliente móvil de Skype Empresarial a una puerta de enlace RTC local y permitir ciertos comportamientos, como una escalación

- Independientemente del sistema operativo, Skype Empresarial cliente móvil debe tener la misma funcionalidad.

En la tabla siguiente se le mostrarán algunos de los escenarios posteriores a la actualización acumulativa 4:

|Location-Based de enrutamiento|Otra parte|Acción|Resultado|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Móvil   |RTC   |Skype Empresarial Mobile recibe una llamada RTC entrante.   |La llamada se enruta mediante llamada a través del trabajo (CvW) y no voIP.   |
|Skype Empresarial Móvil   |RTC   |Skype Empresarial Mobile realiza una llamada RTC saliente.   |La llamada se enruta a través de CvW y no voIP.   |
|Skype Empresarial Móvil   |RTC   |Skype Empresarial Mobile está en una llamada RTC. Skype Empresarial Mobile escala la llamada a otro usuario o contacto.   |La llamada se enruta a través de VoIP si el usuario o el contacto es local en el tramo de puerta de enlace RTC.  <br/> Si el usuario o el contacto es remoto desde el tramo de puerta de enlace RTC, la llamada se enruta a través de CvW.  <br/> Si no se puede acceder al usuario de destino a través de la RTC, se produce un error en la llamada.  <br/> Si el contacto de destino es una conferencia Operador automático (CAA), la llamada se bloquea.   |
|Skype Empresarial Móvil   |Skype Empresarial cliente o usuario federado   |Un Skype Empresarial Mobile inicia una llamada de voz a otro Skype Empresarial cliente o usuario federado.   |La llamada se completa a través de VoIP.   |
|Skype Empresarial Móvil   |Skype Empresarial cliente o usuario federado   | Un Skype Empresarial o un usuario federado inicia una llamada de voz a un usuario Skype Empresarial mobile Location-Based enrutamiento.  |La llamada se completa a través de VoIP.   |
|Skype Empresarial Móvil   |Skype Empresarial cliente o usuario federado   |Un Skype Empresarial cliente o un usuario federado está en una llamada VoIP a un Skype Empresarial móvil. Cualquiera de las partes se escala a un usuario Skype Empresarial o federado adicional.   |La llamada se completa a través de VoIP.   |
|Skype Empresarial Móvil   |Usuario federado   |Un usuario federado está en llamada de voz a un usuario de Skype Empresarial Mobile Location-Based Routing; un usuario de Skype Empresarial Mobile escala a un usuario RTC.   |La llamada está bloqueada.   |
|Skype Empresarial Móvil   |Usuario federado   |Un usuario federado está en una llamada VoIP a un usuario de Skype Empresarial Mobile Location-Based Routing; cualquiera de las partes escala a un contacto caa.   |La llamada escalada está bloqueada, con un mensaje de error adecuado.   |
|Skype Empresarial Móvil   |Usuario federado   |Un usuario federado está en una llamada VoIP a un usuario de Skype Empresarial Mobile Location-Based Routing y el usuario federado escala a un usuario RTC.   |La escalación se permitirá o no se permitirá en función del Location-Based enrutamiento del usuario federado. La Skype Empresarial aplicación del Location-Based de enrutamiento móvil no lleva a ninguna acción.   |

### <a name="delegation"></a>Delegación

Las capacidades de delegación en Skype Empresarial se ven afectadas por Location-Based enrutamiento de la siguiente manera:

- Cuando un delegado habilitado para Location-Based Routing hace una llamada en nombre de un administrador, la directiva de voz del delegado se usa para autorizar la llamada y la directiva de enrutamiento de voz del sitio del delegado se usará para enrutar la llamada.

- Para las llamadas RTC entrantes a un administrador, se aplicarán las mismas reglas aplicables para el reenvío de llamadas o la llamada simultánea, como se describe en los temas Transferencias de llamadas y reenvío y llamadas simultáneas.

- Cuando un delegado establece un extremo RTC como destino de llamada simultánea, para una llamada entrante al administrador, se usará la directiva de enrutamiento de voz del sitio asociado al tronco entrante para enrutar la llamada al extremo RTC del delegado.

- Para la delegación, se recomienda que el administrador y sus delegados asociados se ubican normalmente en el mismo sitio de red.

## <a name="other-planning-considerations"></a>Otras consideraciones de planeación

Al planear Location-Based enrutamiento, debe tener en cuenta el impacto en los siguientes escenarios.

### <a name="disaster-recovery"></a>Recuperación ante desastres

Durante una conmutación por error del grupo principal a un grupo de servidores de copia de seguridad, así como al restaurar las operaciones normales en el grupo de servidores principal, el enrutamiento de Location-Based se aplica en todo momento durante un procedimiento de recuperación y desastres.

### <a name="survivable-branch-appliance"></a>Aplicación de sucursal con funciones de supervivencia

La configuración Location-Based enrutamiento afecta a la planeación de dónde se implementan las puertas de enlace asociadas a los dispositivos de sucursal con funciones de supervivencia. La puerta de enlace asociada a su SBA debe encontrarse en el mismo sitio de red que la aplicación de sucursal con funciones de supervivencia; de lo contrario, los usuarios que se alomen en la aplicación de sucursal con funciones de supervivencia no podrán realizar llamadas salientes si Location-Based enrutamiento está configurado. Cuando la conexión WAN entre la aplicación de sucursal con funciones de supervivencia y el sitio central está abajo, Location-Based restricciones de enrutamiento se aplican.

## <a name="client-and-server-support-for-location-based-routing"></a>Compatibilidad de cliente y servidor para Location-Based enrutamiento

Location-Based el enrutamiento se aplica mediante Skype Empresarial Server. Skype Empresarial Server identificar los sitios de red desde los que los usuarios se conectan desde dentro de la red corporativa. Dado que los usuarios remotos están fuera de la red corporativa, su ubicación se considera desconocida.

### <a name="server-support"></a>Compatibilidad con el servidor

Location-Based routing requiere que Skype Empresarial Server o Lync Server 2013 CU1 se implemente en todos los grupos de servidores front-end y servidores Standard Edition en una topología determinada. Si estas versiones del servidor no están instaladas, las restricciones de enrutamiento basado en ubicación no se pueden aplicar por completo.

En la tabla siguiente se identifica la combinación de roles de servidor y versiones compatibles con Location-Based enrutamiento.

****

|Versión del grupo|Versión del servidor de mediación|Compatible|
|:-----|:-----|:-----|
|Skype Empresarial Server o Lync Server 2013 Actualización acumulativa de febrero de 2013   |Skype Empresarial Server o Lync Server 2013 Actualización acumulativa de febrero de 2013   |sí   |
|Skype Empresarial Server o Lync Server 2013 Actualización acumulativa de febrero de 2013   |Lync Server 2013   |no   |
|Skype Empresarial Server o Lync Server 2013 Actualización acumulativa de febrero de 2013   |Lync Server 2010   |no   |
|Skype Empresarial Server o Lync Server 2013 Actualización acumulativa de febrero de 2013   |Office Communications Server 2007 R2   |no   |
|Lync Server 2013   |cualquiera   |no   |
|Lync Server 2010   |cualquiera   |no   |
|Office Communications Server 2007 R2   |cualquiera   |no   |

### <a name="client-support"></a>Soporte técnico de cliente

En la tabla siguiente se identifican los clientes que admite Location-Based enrutamiento.

****

|Tipo de cliente|Compatible|Detalles|
|:-----|:-----|:-----|
|Skype Empresarial   |sí   ||
|Lync 2013   |sí   ||
|Lync 2010   |sí   ||
|Office Communicator 2007 R2   |no   ||
|Lync Phone Edition   |sí   ||
|Operador de Lync   |sí   ||
|Lync para Windows 8   |no   ||
|Lync Mobile 2013   |no   |VoIP debe deshabilitarse para clientes de Lync Mobile 2013 si los usuarios usan el Location-Based enrutamiento habilitado.   |
|Lync Mobile 2010   |sí   ||

> [!NOTE]
> Para deshabilitar VoIP para Skype Empresarial clientes, asigne una directiva de movilidad con la configuración, IP Audio/Vídeo, deshabilitada para todos los usuarios habilitados para Location-Based enrutamiento. Para obtener más información acerca de la directiva de movilidad, [vea New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Funcionalidades no admitidas por Location-Based enrutamiento

Location-Based routing no se aplica a los siguientes tipos de interacciones. Location-Based el enrutamiento no se aplica cuando los Skype Empresarial interactúan con puntos de conexión RTC con estas funcionalidades.

- Acceso telefónico RTC a conferencias

- Llamadas RTC entrantes y salientes a través del grupo de respuesta

- Estacionamiento de llamadas o recuperación de llamadas RTC a través del estacionamiento de llamadas

- Llamadas RTC entrantes al servicio de anuncios

- Llamadas RTC entrantes recuperadas a través de la recogida de llamadas de grupo

Para aplicar Location-Based de enrutamiento a los tipos de interacciones de la siguiente lista, debe habilitar Location-Based enrutamiento para conferencias:

- Acceso telefónico RTC desde conferencias

- Escalaciones de conversaciones de audio punto a punto a conferencias que implican extremos RTC

- Transferencias consulttivas que implican puntos de conexión RTC

Para habilitar Location-Based enrutamiento para conferencias, vea [Location-Based Routing for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-location-based-routing-for-conferencing).
---
title: Plan for Location-Based Routing in Skype for Business
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
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planeación del enrutamiento basado en ubicación en Skype Empresarial Server Telefonía IP empresarial, incluida la interacción con llamadas y delegación simultáneas, y escenarios compatibles para el enrutamiento basado en ubicación.
ms.openlocfilehash: 99a76d3cda40bb1fdc71bdffc7f6c896c96c5cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101486"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Plan for Location-Based Routing in Skype for Business

Planeación del enrutamiento basado en ubicación en Skype Empresarial Server Telefonía IP empresarial, incluida la interacción con llamadas y delegación simultáneas, y escenarios compatibles para el enrutamiento basado en ubicación.

Location-Based enrutamiento permite restringir el enrutamiento de llamadas entre extremos VoIP y puntos de conexión RTC en función de la ubicación de las partes en la llamada. Location-Based routing es una característica de administración de llamadas que controla cómo se enruta las llamadas por Skype Empresarial Server. Aplica reglas de autorización de llamadas sobre si las llamadas se pueden enrutar a puntos de conexión PBX o RTC en función de la ubicación geográfica del autor de la llamada de Skype Empresarial.

Location-Based Routing presenta un nuevo conjunto de reglas que modifica el enrutamiento de llamadas RTC nacionales e internacionales para evitar la omisión de peaje. Location-Based routing proporciona la flexibilidad para establecer el ámbito de estas reglas en regiones específicas, puertas de enlace específicas o solo para un conjunto específico de usuarios.

Los siguientes escenarios ilustran los principales tipos de restricciones que Location-Based el enrutamiento puede aplicar:

- Llamadas de salida: el enrutamiento de Location-Based puede aplicar llamadas salientes a la salida a una puerta de enlace RTC que se encuentra en la misma región en la que el autor de la llamada es para evitar la omisión de peaje RTC, lo que impide que las llamadas a la salida a una puerta de enlace RTC ubicada en una región diferente como el autor de la llamada.

- Llamadas de entrada: el enrutamiento de Location-Based puede impedir que las llamadas RTC entrantes llamen a puntos de conexión de Skype Empresarial si la puerta de enlace RTC enruta la llamada entrante no se encuentra en la misma región que el usuario de Skype Empresarial.

- Regiones desconocidas: el enrutamiento de Location-Based restringe las llamadas RTC entrantes y salientes a y desde usuarios que se encuentran en ubicaciones indeterminadas (es decir, usuarios remotos que se conectan desde Internet o se encuentran en regiones desconocidas).

- Regiones internacionales: Location-Based routing exige el enrutamiento de llamadas salientes a través de puertas de enlace RTC internacionales si no se encuentra una puerta de enlace local a la ubicación del usuario.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Instrucciones sobre dónde aplicar el Location-Based enrutamiento

Location-Based el enrutamiento según la situación se puede aplicar en la ubicación del sitio de red de extremo del usuario o en la ubicación del sitio de red de la puerta de enlace RTC. En este tema se proporcionan instrucciones sobre cómo Location-Based se aplica el enrutamiento.

### <a name="applying-location-based-routing-at-the-users-location"></a>Aplicar Location-Based enrutamiento en la ubicación del usuario

Location-Based Routing aprovecha las mismas regiones de red, sitios y subredes que se definen en Skype Empresarial Server usado por E9-1-1, CAC y Omisión de medios para aplicar restricciones de enrutamiento de llamadas para evitar la omisión de números RTC. La ubicación de un usuario viene determinada por la subred IP desde la que se conectan los puntos de conexión de Skype Empresarial del usuario. Cada subred IP está asociada a un sitio de red, que se agregan a las regiones de red definidas por el administrador. Location-Based se aplica el enrutamiento basado en el sitio de red del usuario.

Location-Based reglas de enrutamiento se aplican por sitio de red, lo que significa que se aplicará un conjunto determinado de reglas a todos los puntos de conexión habilitados para el enrutamiento de Location-Based que se encuentran dentro del mismo sitio de red. Los administradores pueden aplicar Location-Based enrutamiento a los sitios de red que lo requieran.

Las directivas de enrutamiento de voz se pueden definir por sitio de red para definir una puerta de enlace RTC determinada que deben usar todos los usuarios ubicados en el sitio de red para llamar a números de teléfono RTC. Estas directivas de enrutamiento de voz tendrán prioridad sobre el enrutamiento definido por la directiva de voz del usuario cuando el usuario se encuentra en un sitio de red habilitado para el enrutamiento de Location-Based y evitará el enrutamiento de llamadas a través de otras puertas de enlace RTC habilitadas para el enrutamiento de Location-Based. Cuando un usuario de Skype Empresarial realiza una llamada RTC, la directiva de voz del usuario determina si se puede autorizar al usuario a realizar la llamada. Si la directiva de voz del usuario permite al usuario realizar la llamada, Location-Based Routing determina de qué puerta de enlace RTC debe realizar la salida de la llamada. Location-Based routing realiza esta determinación en función de la ubicación del usuario.

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

- El tronco se define para un servidor de mediación del mismo nivel que no hace llamadas de salida a los usuarios rtc y de servicios con teléfonos heredados en ubicaciones estáticas (por ejemplo, teléfonos PBX). Para esta configuración en particular, todas las llamadas entrantes enrutadas por un tronco de este tipo se considerarán originadas desde el mismo sitio de red que el tronco. Las llamadas de los usuarios de PBX tendrán el mismo Location-Based de enrutamiento que los usuarios de Skype Empresarial que se encuentran en el mismo sitio de red que el tronco. Si dos sistemas PBX ubicados en sitios de red independientes están conectados a través de Skype Empresarial Server, el enrutamiento de Location-Based permitirá el enrutamiento de un punto de conexión PBX en un sitio de red a otro extremo pbx en el otro sitio de red. Este escenario no se bloqueará mediante Location-Based enrutamiento. Además de este escenario y de forma similar que un usuario de Skype Empresarial en la misma ubicación, los puntos de conexión conectados a un servidor de mediación del mismo nivel con esta configuración podrán realizar o recibir llamadas desde y hacia otro servidor de mediación del mismo nivel que no enrute llamadas a la RTC (es decir, un extremo conectado a una PBX diferente) independientemente del sitio de red al que esté asociado el mismo servidor de mediación. Todas las llamadas entrantes, llamadas salientes, transferencias de llamadas y reenvíos de llamadas que impliquen extremos RTC estarán sujetas al enrutamiento basado en ubicación para usar solo puertas de enlace RTC definidas como locales para dicho servidor de mediación del mismo nivel.

## <a name="scenarios-for-location-based-routing"></a>Escenarios para Location-Based enrutamiento

Location-Based routing aplica las siguientes reglas generales al enrutar llamadas en los siguientes escenarios.

### <a name="outgoing-calls"></a>Llamadas salientes

El enrutamiento de llamadas salientes de usuarios habilitados para Location-Based enrutamiento se ve afectado por la ubicación de red del extremo del usuario. En la tabla siguiente se muestra cómo Location-Based routing afecta al enrutamiento de llamadas salientes en función de la ubicación del extremo del autor de la llamada.

**Llamador que realiza una llamada saliente a la RTC**

||**Extremo de usuario ubicado en un sitio de red habilitado para Location-Based enrutamiento**|**Extremo de usuario ubicado en un sitio de red desconocido o no habilitado para el Location-Based enrutamiento**|
|:-----|:-----|:-----|
|Autorización de llamadas salientes  <br/> |La llamada se autoriza en función de la directiva de voz del usuario  <br/> |La llamada se autoriza en función de la directiva de voz del usuario  <br/> |
|Enrutamiento de llamadas salientes  <br/> |La llamada se enruta según la directiva de enrutamiento de voz del sitio de red  <br/> |La llamada se enruta según la directiva de voz del usuario y solo a través de troncos no habilitados para Location-Based enrutamiento (si está disponible)  <br/> |

### <a name="incoming-calls"></a>Llamadas entrantes

El enrutamiento de llamadas entrantes a usuarios habilitados para Location-Based enrutamiento depende de la ubicación del extremo del usuario. El enrutamiento de las llamadas entrantes se ve afectado de la siguiente manera. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento de Location-Based y el extremo se encuentra en el mismo sitio de red que la puerta de enlace RTC, se enruta la llamada. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento de Location-Based y el extremo se encuentra en un sitio de red diferente a la puerta de enlace RTC, la llamada no se enruta. Cuando un usuario no tiene puntos de conexión ubicados en el mismo sitio de red que la puerta de enlace RTC desde la que se origina la llamada entrante, la llamada entrante se enruta directamente al correo de voz del usuario y se enviará una notificación de llamada perdida a la parte llamada.

La configuración de reenvío de llamadas de un usuario que está habilitado para el enrutamiento de Location-Based se seguirá aplicando, sin embargo, las llamadas reenviadas estarán sujetas a Location-Based restricciones de enrutamiento del usuario.

En la tabla siguiente se muestra cómo Location-Based routing afecta al enrutamiento de llamadas entrantes en función de la ubicación del extremo del destinatario. El sitio de red de la puerta de enlace RTC está habilitado para el enrutamiento de Location-Based y el enrutamiento de Location-Based solo permite el enrutamiento de llamadas RTC a puntos de conexión dentro del mismo sitio de red.

**Destinatario de llamada que recibe una llamada entrante de la RTC**

||**Punto de conexión del destinatario de la llamada ubicado en el mismo sitio de red que la puerta de enlace RTC**|**El extremo del destinatario no se encuentra en el mismo sitio de red que la puerta de enlace RTC**|**Punto de conexión del destinatario de la llamada ubicado en un sitio de red desconocido o no habilitado para el Location-Based enrutamiento**|
|:-----|:-----|:-----|:-----|
|Enrutamiento de llamadas RTC entrantes  <br/> |La llamada entrante se enruta a los puntos de conexión del destinatario  <br/> |La llamada entrante no se enruta a los puntos de conexión del destinatario  <br/> |La llamada entrante no se enruta a los puntos de conexión del destinatario  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Transferencias de llamadas y reenvío de llamadas

Cuando se trata de un extremo RTC, Location-Based Routing analiza la ubicación del extremo de la calle y el punto de conexión al que se transferirá o reenviará la llamada (es decir, destino de transferencia/reenvío). Location-Based routing determina si la llamada debe transferirse o reenviarse en función de la ubicación de ambos extremos.

En la tabla siguiente se muestra el escenario de un usuario de Skype Empresarial en una llamada con un extremo RTC y el usuario de Skype Empresarial transfiere la llamada a otro usuario de Skype Empresarial. Según la ubicación del sitio de red del punto de conexión del destinatario de la transferencia, Location-Based Routing afecta al enrutamiento de la transferencia de llamadas o el reenvío.

**Iniciar la transferencia de llamadas o reenviar**

|**Usuario que inicia la transferencia/reenvío de llamadas**|**El extremo de destino se encuentra en el mismo sitio de red que el usuario que inicia la transferencia o reenvío de llamadas**|**El extremo de destino se encuentra en un sitio de red diferente como usuario que inicia la transferencia o reenvío de llamadas**|**El extremo de destino está en sitio de red desconocido o sitio de red no habilitado para el Location-Based enrutamiento**|
|:-----|:-----|:-----|:-----|
|Usuario de Skype Empresarial  <br/> |Se permite la transferencia o reenvío de llamadas  <br/> |No se permite la transferencia o el reenvío de llamadas  <br/> |No se permite la transferencia o el reenvío de llamadas  <br/> |

Por ejemplo: un usuario de Skype Empresarial en una llamada con un extremo RTC transfiere la llamada a otro usuario de Skype Empresarial que se encuentra en el mismo sitio de red. En este caso, se permite la transferencia de llamadas.

En la tabla siguiente se muestra el escenario de un usuario de Skype Empresarial en una llamada con otro usuario de Skype Empresarial y uno de los usuarios transfiere la llamada a un extremo RTC. Según la ubicación del usuario al que se transfiera la llamada, la tabla detalla cómo afecta Location-Based enrutamiento a la llamada.

**Transferencia de llamadas o reenvío al punto de conexión RTC**

|**Destino de extremo de transferencia/reenvío de llamadas**|**Usuarios de Skype Empresarial en el mismo sitio de red**|**Usuarios de Skype Empresarial en diferentes sitios de red**|**Uno o ambos usuarios de Skype Empresarial en sitios de red o sitios de red desconocidos no están habilitados para Location-Based enrutamiento**|
|:-----|:-----|:-----|:-----|
|Extremo RTC  <br/> |Reenvío de llamadas o transferencia permitidos por la directiva de enrutamiento de voz del sitio del usuario transferido  <br/> |Reenvío de llamadas o transferencia permitidos por la directiva de enrutamiento de voz del sitio del usuario transferido  <br/> |Reenvío de llamadas o transferencia permitidos por la directiva de voz del usuario transferido solo a través de troncos no habilitados para el Location-Based enrutamiento  <br/> |

Por ejemplo: un usuario de Skype Empresarial en una llamada con otro usuario de Skype Empresarial que se encuentra en el mismo sitio de red transfiere la llamada a un extremo RTC y se permite la transferencia de llamadas.

### <a name="simultaneous-ringing"></a>Llamadas simultáneas

Cuando la parte llamada tiene habilitada la llamada simultánea, Location-Based Routing analiza la ubicación de la parte que llama y los extremos de las partes llamadas para determinar si se debe enrutar la llamada.

En la tabla siguiente se muestra un usuario configurado con llamadas simultáneas y el destino de llamada simultánea es un usuario en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido.

****

|**Llamada RTC entrante para**|**Ubicado en el mismo sitio de red que el destinatario de la llamada**|**Ubicado en un sitio de red diferente del destinatario de la llamada**|**Ubicado en un sitio de red desconocido o no habilitado para el Location-Based enrutamiento**|
|:-----|:-----|:-----|:-----|
|Usuario de Skype Empresarial  <br/> |Anillo simultáneo permitido  <br/> |Anillo simultáneo no permitido  <br/> |Anillo simultáneo no permitido  <br/> |

En la tabla siguiente se muestra una llamada de un usuario de Skype Empresarial (es decir, llamador de Skype Empresarial) en el mismo sitio de red, en un sitio de red diferente o desde un sitio de red desconocido. El destinatario de la llamada tiene un punto de conexión RTC (es decir, teléfono móvil) configurado como un destino de anillo simultáneo. En este escenario, Location-Based Routing determinará si la llamada se debe enrutar al destino de llamada simultánea (es decir, el teléfono móvil) del destinatario de la llamada o no.

****

|**Destino de anillo simultáneo**|**Ubicado en el mismo sitio de red que el destinatario de la llamada**|**Ubicado en un sitio de red diferente del destinatario de la llamada**|**Ubicado en un sitio de red desconocido o no habilitado para el Location-Based enrutamiento**|
|:-----|:-----|:-----|:-----|
|Extremo RTC  <br/> |Anillo simultáneo permitido a través de la directiva de enrutamiento de voz del sitio del autor de la llamada  <br/> |Anillo simultáneo permitido a través de la directiva de enrutamiento de voz del sitio del autor de la llamada  <br/> |Anillo simultáneo permitido a través de la directiva de voz del autor de la llamada a troncos no habilitados para Location-Based enrutamiento  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Actualización acumulativa de Skype Empresarial 4

Con la actualización acumulativa 4, verá lo siguiente:

- Location-Based el enrutamiento seguirá habilitado a través de la directiva de voz, incluidos los clientes de Skype Empresarial Mobile.

- El comportamiento de las llamadas de los clientes de Skype Empresarial Mobile se basará en si están habilitados para el enrutamiento Location-Based y el cliente de comunicación. Esto está diseñado para ser estático, pero puede haber, en determinadas situaciones, un esfuerzo para asociar un cliente de Skype Empresarial Mobile a una puerta de enlace RTC local y permitir ciertos comportamientos, como una escalación

- Independientemente del sistema operativo, el cliente de Skype Empresarial Mobile debe tener la misma funcionalidad.

En la tabla siguiente se le mostrarán algunos de los escenarios posteriores a la actualización acumulativa 4:

|**Usuario de enrutamiento basado en ubicación**|**Otra parte**|**Acción**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Mobile  <br/> |RTC  <br/> |Skype Empresarial Mobile recibe una llamada RTC entrante.  <br/> |La llamada se enruta mediante llamada a través del trabajo (CvW) y no voIP.  <br/> |
|Skype Empresarial Mobile  <br/> |RTC  <br/> |Skype Empresarial Mobile realiza una llamada RTC saliente.  <br/> |La llamada se enruta a través de CvW y no voIP.  <br/> |
|Skype Empresarial Mobile  <br/> |RTC  <br/> |Skype Empresarial Mobile está en una llamada RTC. A continuación, Skype Empresarial Mobile escala la llamada a otro usuario o contacto.  <br/> |La llamada se enruta a través de VoIP si el usuario o el contacto es local en el tramo de puerta de enlace RTC.  <br/> Si el usuario o el contacto es remoto desde el tramo de puerta de enlace RTC, la llamada se enruta a través de CvW.  <br/> Si no se puede acceder al usuario de destino a través de la RTC, se produce un error en la llamada.  <br/> Si el contacto de destino es una conferencia Operador automático (CAA), la llamada se bloquea.  <br/> |
|Skype Empresarial Mobile  <br/> |Cliente de Skype Empresarial o usuario federado  <br/> |Un Skype Empresarial Mobile inicia una llamada de voz a otro cliente o usuario federado de Skype Empresarial.  <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial Mobile  <br/> |Cliente de Skype Empresarial o usuario federado  <br/> | Un cliente de Skype Empresarial o un usuario federado inicia una llamada de voz a un usuario de enrutamiento de Skype Empresarial Mobile Location-Based enrutamiento. <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial Mobile  <br/> |Cliente de Skype Empresarial o usuario federado  <br/> |Un cliente de Skype Empresarial o un usuario federado está en una llamada VoIP a un usuario de Skype Empresarial Mobile. Cualquiera de las partes se escala a un skype empresarial adicional o a un usuario federado.  <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial Mobile  <br/> |Usuario federado  <br/> |Un usuario federado está en llamada de voz a un usuario de enrutamiento de skype empresarial Location-Based móvil; una parte de Skype Empresarial Mobile se escala a un usuario RTC.  <br/> |La llamada está bloqueada.  <br/> |
|Skype Empresarial Mobile  <br/> |Usuario federado  <br/> |Un usuario federado está en una llamada VoIP a un usuario de enrutamiento de skype empresarial Location-Based móvil; cualquiera de las partes se escala a un contacto caa.  <br/> |La llamada escalada está bloqueada, con un mensaje de error adecuado.  <br/> |
|Skype Empresarial Mobile  <br/> |Usuario federado  <br/> |Un usuario federado está en una llamada VoIP a un usuario de enrutamiento de Skype Empresarial Mobile Location-Based y el usuario federado escala a un usuario RTC.  <br/> |La escalación se permitirá o no se permitirá en función del Location-Based enrutamiento del usuario federado. La aplicación de Skype Empresarial Mobile Location-Based aplicación del usuario de enrutamiento no hace ninguna acción.  <br/> |

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

Location-Based el enrutamiento es obligatorio por Skype Empresarial Server. Skype Empresarial Server puede identificar los sitios de red en los que los usuarios se conectan desde dentro de la red corporativa. Dado que los usuarios remotos están fuera de la red corporativa, su ubicación se considera desconocida.

### <a name="server-support"></a>Compatibilidad con el servidor

Location-Based routing requiere que Skype Empresarial Server o Lync Server 2013 CU1 se implementen en todos los grupos de servidores front-end y servidores Standard Edition en una topología determinada. Si estas versiones del servidor no están instaladas, las restricciones de enrutamiento basado en ubicación no se pueden aplicar por completo.

En la tabla siguiente se identifica la combinación de roles de servidor y versiones compatibles con Location-Based enrutamiento.

****

|**Versión del grupo**|**Versión del servidor de mediación**|**Compatible**|
|:-----|:-----|:-----|
|Actualización acumulativa de Skype Empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Actualización acumulativa de Skype Empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |sí  <br/> |
|Actualización acumulativa de Skype Empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Lync Server 2013  <br/> |no  <br/> |
|Actualización acumulativa de Skype Empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Lync Server 2010  <br/> |no  <br/> |
|Actualización acumulativa de Skype Empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Office Communications Server 2007 R2  <br/> |no  <br/> |
|Lync Server 2013  <br/> |cualquiera  <br/> |no  <br/> |
|Lync Server 2010  <br/> |cualquiera  <br/> |no  <br/> |
|Office Communications Server 2007 R2  <br/> |cualquiera  <br/> |no  <br/> |

### <a name="client-support"></a>Soporte técnico de cliente

En la tabla siguiente se identifican los clientes que admite Location-Based enrutamiento.

****

|**Tipo de cliente**|**Compatible**|**Detalles**|
|:-----|:-----|:-----|
|Skype Empresarial  <br/> |sí  <br/> ||
|Lync 2013  <br/> |sí  <br/> ||
|Lync 2010  <br/> |sí  <br/> ||
|Office Communicator 2007 R2  <br/> |no  <br/> ||
|Lync Phone Edition  <br/> |sí  <br/> ||
|Operador de Lync  <br/> |sí  <br/> ||
|Lync para Windows 8  <br/> |no  <br/> ||
|Lync Mobile 2013  <br/> |no  <br/> |VoIP debe deshabilitarse para clientes de Lync Mobile 2013 si los usuarios usan el Location-Based enrutamiento habilitado.  <br/> |
|Lync Mobile 2010  <br/> |sí  <br/> ||

> [!NOTE]
> Para deshabilitar VoIP para clientes de Skype Empresarial, asigne una directiva de movilidad con la configuración, IP Audio/Vídeo, deshabilitada para todos los usuarios habilitados para Location-Based enrutamiento. Para obtener más información acerca de la directiva de movilidad, [vea New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Funcionalidades no admitidas por Location-Based enrutamiento

Location-Based routing no se aplica a los siguientes tipos de interacciones. Location-Based el enrutamiento no se aplica cuando los puntos de conexión de Skype Empresarial interactúan con puntos de conexión RTC con estas funcionalidades.

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
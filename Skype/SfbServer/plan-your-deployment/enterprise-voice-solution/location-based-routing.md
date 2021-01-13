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
description: Planear el enrutamiento basado en ubicación en Skype Empresarial Server Telefonía IP empresarial, incluida la interacción con llamadas y delegación simultáneas, y escenarios admitidos para el enrutamiento basado en ubicación.
ms.openlocfilehash: 473ed77dce8edaee3b43822adcb8920027795d9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825560"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Plan for Location-Based Routing in Skype for Business

Planear el enrutamiento basado en ubicación en Skype Empresarial Server Telefonía IP empresarial, incluida la interacción con llamadas y delegación simultáneas, y escenarios admitidos para el enrutamiento basado en ubicación.

Location-Based enrutamiento permite restringir el enrutamiento de llamadas entre extremos VoIP y extremos RTC en función de la ubicación de las partes en la llamada. Location-Based enrutamiento es una característica de administración de llamadas que controla cómo se enruta la llamada por Skype Empresarial Server. Aplica reglas de autorización de llamadas en función de si las llamadas se pueden enrutar a puntos de conexión RTC o PBX en función de la ubicación geográfica del autor de la llamada de Skype Empresarial.

Location-Based enrutamiento presenta un nuevo conjunto de reglas que modifica el enrutamiento de llamadas RTC nacionales e internacionales para evitar la omisión de pago. Location-Based enrutamiento proporciona la flexibilidad de definir el ámbito de estas reglas solo a regiones específicas, puertas de enlace específicas o a un conjunto específico de usuarios.

Los siguientes escenarios ilustran los tipos principales de restricciones Location-Based que puede aplicar el enrutamiento:

- Llamadas de salida: el enrutamiento de Location-Based puede aplicar llamadas salientes para la salida a una puerta de enlace RTC ubicada en la misma región en la que se encuentra el autor de la llamada para evitar la omisión de pago de RTC, lo que impide que las llamadas entren a una puerta de enlace RTC ubicada en una región diferente a la del autor de la llamada.

- Llamadas de entrada: el enrutamiento de Location-Based puede impedir que las llamadas RTC entrantes suene a los puntos de conexión de Skype Empresarial si la puerta de enlace RTC que enruta la llamada entrante no se encuentra en la misma región que el usuario de Skype Empresarial llamado.

- Regiones desconocidas: Location-Based enrutamiento restringe las llamadas RTC entrantes y salientes a los usuarios que se encuentran en ubicaciones indeterminadas (es decir, usuarios remotos que se conectan desde Internet o que se encuentran en regiones desconocidas).

- Regiones internacionales: Location-Based enrutamiento aplica el enrutamiento de llamadas salientes a través de puertas de enlace RTC internacionales si no se encuentra una puerta de enlace local en la ubicación del usuario.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Instrucciones sobre dónde aplicar el Location-Based enrutamiento

Location-Based enrutamiento en función de la situación se puede aplicar en la ubicación del sitio de red del extremo del usuario o en la ubicación del sitio de red de la puerta de enlace RTC. En este tema se proporcionan instrucciones sobre cómo Location-Based se aplica el enrutamiento.

### <a name="applying-location-based-routing-at-the-users-location"></a>Aplicación de Location-Based enrutamiento en la ubicación del usuario

Location-Based Enrutamiento aprovecha las mismas regiones de red, sitios y subredes definidos en Skype Empresarial Server usado por E9-1-1, CAC y Desvío de medios para aplicar restricciones de enrutamiento de llamadas para evitar la omisión de pago rtc. La ubicación de un usuario viene determinada por la subred IP desde la que están conectados los puntos de conexión de Skype Empresarial del usuario. Cada subred IP está asociada a un sitio de red, que se agrega a las regiones de red definidas por el administrador. Location-Based enrutamiento se aplica en función del sitio de red del usuario.

Location-Based reglas de enrutamiento se aplican por sitio de red, lo que significa que se aplicará un conjunto determinado de reglas a todos los puntos de conexión habilitados para el enrutamiento de Location-Based que se encuentran dentro del mismo sitio de red. Los administradores pueden aplicar Location-Based enrutamiento a sitios de red que lo requieran.

Las directivas de enrutamiento de voz se pueden definir por sitio de red para definir una puerta de enlace RTC determinada que todos los usuarios ubicados en el sitio de red deben usar para llamar a números de teléfono RTC. Estas directivas de enrutamiento de voz tendrán prioridad sobre el enrutamiento definido por la directiva de voz del usuario cuando el usuario se encuentra en un sitio de red habilitado para enrutamiento de Location-Based y evitará el enrutamiento de llamadas a través de otras puertas de enlace RTC habilitadas para el enrutamiento de Location-Based. Cuando un usuario de Skype Empresarial realiza una llamada RTC, la directiva de voz del usuario determina si el usuario puede estar autorizado a realizar la llamada. Si la directiva de voz del usuario permite al usuario realizar la llamada, Location-Based enrutamiento determina desde qué puerta de enlace RTC debe partir la llamada. Location-Based enrutamiento realiza esta determinación en función de la ubicación del usuario.

Una ubicación de usuario se puede clasificar de las siguientes maneras:

- El usuario se encuentra en un sitio de red conocido habilitado para enrutamiento de Location-Based y su número DID (marcado directo a la extensión) finaliza en una puerta de enlace RTC situada en el mismo sitio de red (es decir, office). El enrutamiento de las llamadas salientes se realizará a través de la directiva de enrutamiento de voz del sitio de red en el que se encuentra el usuario. Las llamadas RTC entrantes al usuario se enrutar a los puntos de conexión ubicados en el mismo sitio de red que la puerta de enlace RTC.

- El usuario se encuentra en un sitio de red conocido que es diferente del sitio de red donde se encuentra la puerta de enlace RTC. (es decir, el usuario ha viajado a otra oficina corporativa). El enrutamiento de llamadas salientes se realizará mediante la directiva de enrutamiento de voz del sitio de red en el que se encuentra el usuario. Las llamadas RTC entrantes al usuario no se enrutarán a los puntos de conexión ubicados en sitios distintos de la puerta de enlace RTC para evitar la omisión de pago de RTC.

- Cuando un usuario se encuentra en un sitio de red desconocido para la implementación de Skype Empresarial Server, el enrutamiento de llamadas salientes se basará en la directiva de voz asignada al usuario a puertas de enlace RTC no enlazadas a restricciones de enrutamiento de Location-Based. Las llamadas RTC entrantes no se enrutarán a los puntos de conexión ubicados en sitios de red desconocidos para evitar la omisión de pago de RTC.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Aplicación de Location-Based enrutamiento en la ubicación de la puerta de enlace RTC

Las llamadas enrutadas a través de puertas de enlace RTC y PBX pueden requerir restricciones Location-Based enrutamiento en función de la ubicación de dichos sistemas. Location-Based enrutamiento se puede habilitar en la granularidad por tronco.

Location-Based enrutamiento presenta el siguiente conjunto de reglas cuando se habilita en un tronco:

- Cuando Location-Based enrutamiento por tronco, las reglas que se definen en ese tronco se aplicarán solo a las llamadas enrutadas a través de ese tronco.

- Para evitar la omisión de los números de pago rtc en los que las llamadas se originan desde un sitio de red diferente al sitio de red donde se encuentra la puerta de enlace RTC, Location-Based Routing introduce la asociación de un sitio de red a un tronco determinado. Esto define el sitio de red que permite enrutar las llamadas a un tronco determinado.

Los troncos se pueden habilitar para Location-Based enrutamiento de dos maneras:

- El tronco se define para una puerta de enlace RTC que salida las llamadas a la RTC. Las llamadas entrantes enrutadas por un tronco de este tipo se enrutarán solo a los puntos de conexión ubicados en el mismo sitio de red que el tronco.

- El tronco se define para un servidor de mediación del mismo nivel que no salida llamadas a los usuarios rtc y de servicios con teléfonos heredados en una ubicación estática (por ejemplo, teléfonos PBX). Para esta configuración en particular, se considerará que todas las llamadas entrantes enrutadas por un tronco de este tipo proceden del mismo sitio de red que el tronco. Las llamadas de los usuarios de PBX tendrán la misma aplicación Location-Based enrutamiento que los usuarios de Skype Empresarial que se encuentran en el mismo sitio de red que el tronco. Si dos sistemas PBX ubicados en sitios de red independientes están conectados a través de Skype Empresarial Server, el enrutamiento de Location-Based permitirá el enrutamiento de un extremo de PBX en un sitio de red a otro extremo de PBX en el otro sitio de red. Este escenario no se bloqueará mediante Location-Based enrutamiento. Además de este escenario y de forma similar a un usuario de Skype Empresarial en la misma ubicación, los extremos conectados a un servidor de mediación del mismo nivel con esta configuración podrán realizar o recibir llamadas desde y hacia otro servidor de mediación del mismo nivel que no enrutar llamadas a la RTC (es decir, un extremo conectado a una PBX diferente) independientemente del sitio de red al que esté asociado el servidor de mediación. Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y los reenvíos de llamadas que impliquen extremos de RTC estarán sujetos al enrutamiento basado en ubicación para usar solo puertas de enlace RTC definidas como locales para dicho servidor de mediación del mismo nivel.

## <a name="scenarios-for-location-based-routing"></a>Escenarios para el Location-Based enrutamiento

Location-Based enrutamiento aplica las siguientes reglas generales al enrutar llamadas en los siguientes escenarios.

### <a name="outgoing-calls"></a>Llamadas salientes

El enrutamiento de llamadas salientes de usuarios habilitados para Location-Based enrutamiento se ve afectado por la ubicación de red del extremo del usuario. En la tabla siguiente se muestra cómo Location-Based enrutamiento afecta al enrutamiento de llamadas salientes en función de la ubicación del extremo del autor de la llamada.

**Autor de la llamada que realiza una llamada saliente a la RTC**

||**Extremo de usuario ubicado en un sitio de red habilitado para enrutamiento Location-Based usuario**|**Extremo de usuario ubicado en un sitio de red desconocido o no habilitado para enrutamiento Location-Based usuario**|
|:-----|:-----|:-----|
|Autorización de llamadas salientes  <br/> |La llamada se autoriza en función de la directiva de voz del usuario  <br/> |La llamada se autoriza en función de la directiva de voz del usuario  <br/> |
|Enrutamiento de llamadas salientes  <br/> |La llamada se enruta según la directiva de enrutamiento de voz del sitio de red  <br/> |La llamada se enruta según la directiva de voz del usuario y solo a través de troncos no habilitados para Location-Based enrutamiento (si está disponible)  <br/> |

### <a name="incoming-calls"></a>Llamadas entrantes

El enrutamiento de las llamadas entrantes a los usuarios habilitados para Location-Based enrutamiento depende de la ubicación del extremo del usuario. El enrutamiento de las llamadas entrantes se ve afectado de la siguiente manera. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento de Location-Based y el extremo se encuentra en el mismo sitio de red que la puerta de enlace RTC, la llamada se enruta. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento de Location-Based y el extremo se encuentra en un sitio de red diferente al de la puerta de enlace RTC, la llamada no se enruta. Cuando un usuario no tiene extremos ubicados en el mismo sitio de red que la puerta de enlace RTC desde la que se origina la llamada entrante, la llamada entrante se enruta directamente al correo de voz del usuario y se enviará una notificación de llamada perdida a la parte que recibe la llamada.

La configuración de reenvío de llamadas de un usuario que está habilitado para el enrutamiento de Location-Based se seguirá aplicando; sin embargo, las llamadas reenviadas estarán sujetas Location-Based restricciones de enrutamiento del usuario.

En la tabla siguiente se muestra cómo Location-Based enrutamiento afecta al enrutamiento de llamadas entrantes en función de la ubicación del extremo del destinatario de la llamada. El sitio de red de la puerta de enlace RTC está habilitado para el enrutamiento de Location-Based y el enrutamiento de Location-Based solo permite el enrutamiento de llamadas RTC a los puntos de conexión dentro del mismo sitio de red.

**Destinatario de la llamada que recibe una llamada entrante de la RTC**

||**Extremo del destinatario de la llamada ubicado en el mismo sitio de red que la puerta de enlace RTC**|**El extremo del destinatario de la llamada no se encuentra en el mismo sitio de red que la puerta de enlace RTC**|**El extremo del destinatario de la llamada se encuentra en un sitio de red desconocido o no está habilitado para el Location-Based enrutamiento**|
|:-----|:-----|:-----|:-----|
|Enrutamiento de llamadas RTC entrantes  <br/> |La llamada entrante se enruta a los extremos del destinatario de la llamada  <br/> |La llamada entrante no se enruta a los extremos del destinatario de la llamada  <br/> |La llamada entrante no se enruta a los extremos del destinatario de la llamada  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Transferencia de llamadas y reenvío de llamadas

Cuando se trata de un extremo de RTC, Location-Based Routing analiza la ubicación del extremo de la calle y el extremo al que se transferirá o reenviará la llamada (es decir, el destino de transferencia o reenvío). Location-Based enrutamiento determina si la llamada debe transferirse o reenviarse en función de la ubicación de ambos extremos.

En la tabla siguiente se muestra el escenario de un usuario de Skype Empresarial en una llamada con un punto de conexión rtc y el usuario de Skype Empresarial transfiere la llamada a otro usuario de Skype Empresarial. Según la ubicación del sitio de red del extremo del usuario de transferencia, Location-Based enrutamiento afecta al enrutamiento de la transferencia o reenvío de llamadas.

**Iniciar la transferencia o el reenvío de llamadas**

|**Usuario que inicia la transferencia o reenvío de llamadas**|**El extremo de destino se encuentra en el mismo sitio de red que el usuario que inicia la transferencia o el reenvío de llamadas**|**El extremo de destino se encuentra en un sitio de red diferente cuando el usuario inicia la transferencia o el reenvío de llamadas**|**El extremo de destino está en un sitio de red desconocido o en un sitio de red no habilitado para el enrutamiento Location-Based enrutamiento**|
|:-----|:-----|:-----|:-----|
|Usuario de Skype Empresarial  <br/> |Se permite el reenvío o la transferencia de llamadas  <br/> |No se permite el reenvío o transferencia de llamadas  <br/> |No se permite el reenvío o transferencia de llamadas  <br/> |

Por ejemplo: un usuario de Skype Empresarial en una llamada con un extremo rtc transfiere la llamada a otro usuario de Skype Empresarial que se encuentra en el mismo sitio de red. En este caso, se permite la transferencia de llamadas.

En la tabla siguiente se muestra el escenario de un usuario de Skype Empresarial en una llamada con otro usuario de Skype Empresarial y uno de los usuarios transfiere la llamada a un extremo de RTC. En función de la ubicación del usuario al que se transfiere la llamada, en la tabla se detalla cómo afecta Location-Based enrutamiento a la llamada.

**Transferencia o reenvío de llamadas al extremo de RTC**

|**Destino de extremo de transferencia/reenvío de llamadas**|**Usuarios de Skype Empresarial en el mismo sitio de red**|**Usuarios de Skype Empresarial en sitios de red diferentes**|**Uno o ambos usuarios de Skype Empresarial en un sitio de red o sitio de red desconocidos no están habilitados para el Location-Based enrutamiento**|
|:-----|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Transferencia o reenvío de llamadas permitido por la directiva de enrutamiento de voz del sitio del usuario transferido  <br/> |Transferencia o reenvío de llamadas permitido por la directiva de enrutamiento de voz del sitio del usuario transferido  <br/> |Transferencia o reenvío de llamadas permitido por la directiva de voz del usuario transferido solo a través de troncos no habilitados para enrutamiento Location-Based enrutamiento  <br/> |

Por ejemplo: un usuario de Skype Empresarial en una llamada con otro usuario de Skype Empresarial que se encuentra en el mismo sitio de red transfiere la llamada a un extremo de RTC y se permite la transferencia de llamada.

### <a name="simultaneous-ringing"></a>Llamadas simultáneas

Cuando la persona a la que se llama tiene habilitadas las llamadas simultáneas, el enrutamiento de Location-Based analiza la ubicación de la persona que llama y los extremos de las partes a las que se llama para determinar si se debe enrutar la llamada.

En la tabla siguiente se muestra un usuario configurado con llamadas simultáneas y el destino de las llamadas simultáneas es un usuario en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido.

****

|**Llamada RTC entrante para**|**Ubicado en el mismo sitio de red que el destinatario de la llamada**|**Ubicado en un sitio de red diferente del destinatario de la llamada**|**Ubicado en un sitio de red desconocido o no habilitado para el Location-Based enrutamiento**|
|:-----|:-----|:-----|:-----|
|Usuario de Skype Empresarial  <br/> |Llamadas simultáneas permitidas  <br/> |Llamadas simultáneas no permitidas  <br/> |Llamadas simultáneas no permitidas  <br/> |

En la tabla siguiente se muestra una llamada de un usuario de Skype Empresarial (es decir, el llamador de Skype Empresarial) en el mismo sitio de red, en un sitio de red diferente o desde un sitio de red desconocido. El destinatario de la llamada tiene un extremo de RTC (es decir, un teléfono móvil) configurado como destino de llamadas simultáneas. En este escenario, Location-Based enrutamiento determina si la llamada se debe enrutar al destino de la llamada simultánea (es decir, al teléfono móvil) del destinatario de la llamada o no.

****

|**Destino de llamadas simultáneas**|**Ubicado en el mismo sitio de red que el destinatario de la llamada**|**Ubicado en un sitio de red diferente del destinatario de la llamada**|**Ubicado en un sitio de red desconocido o no habilitado para el Location-Based enrutamiento**|
|:-----|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Llamada simultánea permitida a través de la directiva de enrutamiento de voz del sitio del autor de la llamada  <br/> |Llamada simultánea permitida a través de la directiva de enrutamiento de voz del sitio del autor de la llamada  <br/> |Llamadas simultáneas permitidas a través de la directiva de voz del autor de la llamada a troncos no habilitados para enrutamiento Location-Based llamadas  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Actualización acumulativa 4 de Skype Empresarial

Con la actualización acumulativa 4, verá lo siguiente:

- Location-Based enrutamiento de voz seguirá habilitado a través de la directiva de voz, incluidos los clientes de Skype Empresarial Mobile.

- El comportamiento de las llamadas para los clientes móviles de Skype Empresarial se basará en si están habilitados para el enrutamiento de Location-Based y el cliente de comunicación. Está diseñado para ser estático, pero puede haber, en determinadas situaciones, un esfuerzo para asociar un cliente de Skype Empresarial Mobile a una puerta de enlace RTC local y permitir ciertos comportamientos, como una escalación

- Independientemente del sistema operativo, el cliente de Skype Empresarial Mobile debe tener la misma funcionalidad.

En la tabla siguiente se le mostrarán algunos de los escenarios posteriores a la actualización acumulativa 4:

|**Usuario de enrutamiento basado en ubicación**|**Otra parte**|**Acción**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Mobile  <br/> |RTC  <br/> |Skype Empresarial Mobile recibe una llamada RTC entrante.  <br/> |La llamada se enruta a través de Vía trabajo (CvW) y no voIP.  <br/> |
|Skype Empresarial Mobile  <br/> |RTC  <br/> |Skype Empresarial Mobile realiza una llamada RTC saliente.  <br/> |La llamada se enruta a través de CvW y no voIP.  <br/> |
|Skype Empresarial Mobile  <br/> |RTC  <br/> |Skype Empresarial Mobile está en una llamada RTC. A continuación, Skype Empresarial Mobile escala la llamada a otro usuario o contacto.  <br/> |La llamada se enruta a través de VoIP si el usuario o contacto es local en la parte de la puerta de enlace RTC.  <br/> Si el usuario o contacto es remoto desde la parte de la puerta de enlace RTC, la llamada se enruta a través de CvW.  <br/> Si no se puede acceder al usuario de destino a través de la RTC, se produce un error en la llamada.  <br/> Si el contacto de destino es una conferencia Operador automático (CAA), la llamada se bloquea.  <br/> |
|Skype Empresarial Mobile  <br/> |Cliente de Skype Empresarial o usuario federado  <br/> |Skype Empresarial Mobile inicia una llamada de voz a otro cliente o usuario federado de Skype Empresarial.  <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial Mobile  <br/> |Cliente de Skype Empresarial o usuario federado  <br/> | Un cliente de Skype Empresarial o un usuario federado inicia una llamada de voz a un usuario de enrutamiento de Location-Based Skype Empresarial Mobile. <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial Mobile  <br/> |Cliente de Skype Empresarial o usuario federado  <br/> |Un cliente de Skype Empresarial o un usuario federado está en una llamada VoIP a un usuario de Skype Empresarial Mobile. Cualquiera de las partes escala a un usuario adicional de Skype Empresarial o federado.  <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial Mobile  <br/> |Usuario federado  <br/> |Un usuario federado está en llamada de voz a un usuario de enrutamiento de Location-Based Skype Empresarial Mobile; Una parte de Skype Empresarial Mobile escala a un usuario RTC.  <br/> |La llamada está bloqueada.  <br/> |
|Skype Empresarial Mobile  <br/> |Usuario federado  <br/> |Un usuario federado está en una llamada VoIP a un usuario de enrutamiento móvil de Skype Empresarial Location-Based móvil; cualquiera de las partes escala a un contacto de CAA.  <br/> |La llamada escalada está bloqueada, con un mensaje de error adecuado.  <br/> |
|Skype Empresarial Mobile  <br/> |Usuario federado  <br/> |Un usuario federado está en una llamada VoIP a un usuario de enrutamiento de Location-Based de Skype Empresarial Mobile, y el usuario federado escala a un usuario RTC.  <br/> |La escalación se permitirá o no en función del Location-Based enrutamiento del usuario federado. La aplicación del usuario de enrutamiento Location-Based Skype Empresarial Mobile no hace ninguna acción.  <br/> |

### <a name="delegation"></a>Delegación

Las capacidades de delegación de Skype Empresarial se ven afectadas por Location-Based enrutamiento de la siguiente manera:

- Cuando un delegado habilitado para Location-Based Routing hace una llamada en nombre de un administrador, la directiva de voz del delegado se usa para autorizar la llamada y la directiva de enrutamiento de voz del sitio del delegado se usará para enrutar la llamada.

- Para las llamadas RTC entrantes a un administrador, se aplicarán las mismas reglas aplicables para el reenvío de llamadas o las llamadas simultáneas, como se describe en los temas Transferencia y reenvío de llamadas y llamadas simultáneas.

- Cuando un delegado establece un extremo de RTC como destino de llamadas simultáneas, para una llamada entrante al administrador, la directiva de enrutamiento de voz del sitio asociado al tronco entrante se usará para enrutar la llamada al extremo de RTC del delegado.

- Para la delegación, se recomienda que el administrador y sus delegados asociados se ubican normalmente en el mismo sitio de red.

## <a name="other-planning-considerations"></a>Otras consideraciones de planeación

Al planear Location-Based enrutamiento, debe tener en cuenta el impacto en los siguientes escenarios.

### <a name="disaster-recovery"></a>Recuperación ante desastres

Durante una conmutación por error del grupo de servidores principal a un grupo de servidores de copia de seguridad, así como al restaurar las operaciones normales en el grupo de servidores principal, el enrutamiento de Location-Based se aplica en todo momento durante un procedimiento de recuperación y desastres.

### <a name="survivable-branch-appliance"></a>Aplicación de sucursal con funciones de supervivencia

La configuración Location-Based enrutamiento afecta a la planeación de dónde se implementan las puertas de enlace asociadas a las aplicaciones de sucursal con funciones de supervivencia. La puerta de enlace asociada al SBA debe estar ubicada en el mismo sitio de red que la aplicación de sucursal con funciones de supervivencia; de lo contrario, los usuarios que se alomen en la aplicación de sucursal con funciones de supervivencia no podrán realizar llamadas salientes si se Location-Based enrutamiento. Cuando la conexión WAN entre la aplicación de sucursal con funciones de supervivencia y el sitio central está fuera de servicio, Location-Based restricciones de enrutamiento se aplican.

## <a name="client-and-server-support-for-location-based-routing"></a>Compatibilidad de cliente y servidor para enrutamiento Location-Based cliente

Location-Based enrutamiento se aplica mediante Skype Empresarial Server. Skype Empresarial Server puede identificar los sitios de red desde los que los usuarios se conectan desde la red corporativa. Dado que los usuarios remotos están fuera de la red corporativa, su ubicación se considera desconocida.

### <a name="server-support"></a>Compatibilidad con servidores

Location-Based enrutamiento de clientes requiere que Skype Empresarial Server o Lync Server 2013 CU1 se implementen en todos los grupos de servidores front-end y servidores Standard Edition en una topología determinada. Si estas versiones del servidor no están instaladas, las restricciones de enrutamiento basado en ubicación no se pueden aplicar por completo.

En la tabla siguiente se identifica la combinación de roles de servidor y versiones compatibles con Location-Based enrutamiento.

****

|**Versión del grupo de servidores**|**Versión del servidor de mediación**|**Compatible**|
|:-----|:-----|:-----|
|Actualización acumulativa de Skype Empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Actualización acumulativa de Skype Empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |sí  <br/> |
|Actualización acumulativa de Skype Empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Lync Server 2013  <br/> |no  <br/> |
|Actualización acumulativa de Skype Empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Lync Server 2010  <br/> |no  <br/> |
|Actualización acumulativa de Skype Empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Office Communications Server 2007 R2  <br/> |no  <br/> |
|Lync Server 2013  <br/> |cualquiera  <br/> |no  <br/> |
|Lync Server 2010  <br/> |cualquiera  <br/> |no  <br/> |
|Office Communications Server 2007 R2  <br/> |cualquiera  <br/> |no  <br/> |

### <a name="client-support"></a>Compatibilidad con clientes

En la tabla siguiente se identifican los clientes que admite Location-Based enrutamiento.

****

|**Tipo de cliente**|**Compatible**|**Detalles**|
|:-----|:-----|:-----|
|Skype Empresarial  <br/> |sí  <br/> ||
|Lync 2013  <br/> |sí  <br/> ||
|Lync 2010  <br/> |sí  <br/> ||
|Office Communicator 2007 R2  <br/> |no  <br/> ||
|Lync Phone Edition  <br/> |sí  <br/> ||
|Lync Attendant  <br/> |sí  <br/> ||
|Lync para Windows 8  <br/> |no  <br/> ||
|Lync Mobile 2013  <br/> |no  <br/> |VoIP debe deshabilitarse para los clientes de Lync Mobile 2013 si los usuarios con el enrutamiento de Location-Based habilitado.  <br/> |
|Lync Mobile 2010  <br/> |sí  <br/> ||

> [!NOTE]
> Para deshabilitar VoIP para clientes de Skype Empresarial, asigne una directiva de movilidad con la configuración, Audio/Vídeo IP, deshabilitada para todos los usuarios habilitados para el enrutamiento Location-Based ip. Para obtener más información acerca de la directiva de movilidad, [vea New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Funcionalidades no admitidas por Location-Based enrutamiento

Location-Based enrutamiento no se aplica a los siguientes tipos de interacciones. Location-Based enrutamiento no se aplica cuando los puntos de conexión de Skype Empresarial interactúan con los puntos de conexión rtc que usan estas funcionalidades.

- Acceso telefónico RTC a conferencias

- Llamadas RTC entrantes y salientes a través del grupo de respuesta

- Estacionamiento de llamadas o recuperación de llamadas RTC a través del estacionamiento de llamadas

- Llamadas RTC entrantes al servicio de anuncio

- Llamadas RTC entrantes recuperadas a través de la atención de llamadas grupales

Para aplicar Location-Based reglas de enrutamiento a los tipos de interacciones de la lista siguiente, debe habilitar el enrutamiento Location-Based para conferencias:

- Llamada RTC desde conferencias

- Escalaciones de conversaciones de audio punto a punto a conferencias en las que intervienen extremos RTC

- Transferencias de consulta en las que intervienen extremos RTC

Para habilitar Location-Based enrutamiento de conferencias, consulte Enrutamiento basado [en ubicación para conferencias.](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx)



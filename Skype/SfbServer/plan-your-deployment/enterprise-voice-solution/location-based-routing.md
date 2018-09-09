---
title: Plan para basados en ubicación enrutamiento en Skype para la empresa
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planeación de basados en ubicación enrutamiento en Skype para Business Server Enterprise Voice, incluida la interacción con las llamadas simultáneas y la delegación y escenarios admitidos para enrutamiento basado en la ubicación.
ms.openlocfilehash: 1e4f19d96306db31be0606dbfda799e93c2d34e0
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886101"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Plan para basados en ubicación enrutamiento en Skype para la empresa

Planeación de basados en ubicación enrutamiento en Skype para Business Server Enterprise Voice, incluida la interacción con las llamadas simultáneas y la delegación y escenarios admitidos para enrutamiento basado en la ubicación.

Enrutamiento basado en ubicación hace posible restringir el enrutamiento de llamadas entre los extremos de VoIP y los extremos de RTC en función de la ubicación de las partes en la llamada. Enrutamiento basado en la ubicación es una característica de administración de llamadas que controla cómo las llamadas se enrutan por Skype para Business Server. Aplica las reglas de autorización de llamada en si se pueden enrutar llamadas a extremos PBX o RTC según la Skype para la ubicación geográfica de negocio autor de la llamada.

El enrutamiento basado en ubicación introduce un nuevo conjunto de reglas que modifica el enrutamiento de llamadas RTC nacionales e internacionales para evitar que se omitan los números de pago. El enrutamiento basado en ubicación proporciona la flexibilidad para delimitar estas reglas solo a regiones específicas, a puertas de enlace específicas o a un conjunto específico de usuarios.

Los siguientes escenarios ilustran los principales tipos de restricciones que puede exigir la aplicación de enrutamiento basados en ubicación:

- Las llamadas de salida - enrutamiento basados en ubicación puede exigir que las llamadas salientes egreso a una puerta de enlace de RTC que se encuentra en la misma región como donde el autor de la llamada es para evitar el desvío de pago RTC, lo que evita que las llamadas a egreso a una puerta de enlace de RTC que se encuentra en una región diferente como el autor de la llamada.

- Las llamadas de entrada - enrutamiento basados en ubicación puede evitar que las llamadas RTC entrantes para llamar a Skype para los extremos de negocio si la puerta de enlace de RTC enrutar la llamada entrante no se encuentra en la misma región como el llamado Skype para usuarios de empresa.

- Regiones desconocidas - restringe el enrutamiento basado en la ubicación de llamadas RTC entrantes y salientes a y desde los usuarios que se encuentran en ubicaciones indeterminadas (es decir, los usuarios remotos que se conectan desde Internet o que se encuentra en regiones desconocidas).

- Regiones internacionales - enrutamiento basados en ubicación exige el enrutamiento de llamadas a través de puertas de enlace de RTC internacionales de salida si no se encuentra una puerta de enlace local a la ubicación del usuario.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Instrucciones para dónde aplicar enrutamiento basados en ubicación

Enrutamiento basado en la ubicación según la situación se puede aplicar en ubicación de sitio de red de extremo del usuario o en la ubicación de sitio de red de la puerta de enlace del RTC. En este tema se proporciona orientación sobre cómo basado en la ubicación de enrutamiento se aplica.

### <a name="applying-location-based-routing-at-the-users-location"></a>Aplicación de enrutamiento basado en la ubicación en la ubicación del usuario

Ubicación basada en enrutamiento aprovecha el mismo regiones de red, sitios y subredes, como se define en Skype para Business Server usado por E9-1-1, CAC y el desvío de medios para aplicar restricciones de enrutamiento de llamadas para evitar que el pago de RTC pasan por alto. Ubicación de un usuario viene determinada por la subred IP de Skype del usuario correspondiente están conectados los extremos de negocio desde. Cada subred IP está asociada a un sitio de red, y los sitios de red se agrupan en regiones de red definidas por el administrador. Enrutamiento basado en la ubicación se exige basándose en el sitio de red del usuario.

Se aplican las reglas de enrutamiento de basados en ubicación en una por cada sitio de red, lo que significa que un determinado conjunto de reglas se aplicará a todos los extremos habilitados para enrutamiento basado en la ubicación que se encuentran dentro del mismo sitio de red. Los administradores pueden aplicar el enrutamiento basado en ubicación a los sitios de red que lo necesiten.

Se pueden definir directivas de enrutamiento de voz en cada sitio de red, para que todos los usuarios ubicados en el sitio de red utilicen una puerta de enlace RTC concreta para llamar a números de teléfono de RTC. Estas directivas de enrutamiento de voz tendrá prioridad sobre el enrutamiento definido por la directiva de voz del usuario cuando el usuario se encuentra en un sitio de red habilitado para enrutamiento basado en la ubicación y se evitará que el enrutamiento de llamadas a través de otras puertas de enlace de RTC que están habilitados para Enrutamiento basado en la ubicación. Cuando un Skype para usuarios de empresa realiza una llamada de RTC, la directiva de voz del usuario determina si el usuario puede estar autorizado a realizar la llamada. Si la directiva de voz del usuario lo permite al usuario que realiza la llamada, enrutamiento basados en ubicación determina qué puerta de enlace de RTC que la llamada debe egreso desde. Enrutamiento basado en ubicación realiza esta decisión basándose en la ubicación del usuario.

La ubicación de un usuario se puede clasificar de las siguientes maneras:

- El usuario se encuentra en un sitio de red conocidos habilitado para enrutamiento basado en la ubicación y su número DID (llamada directa marcado) termina en una puerta de enlace de RTC que coloca en el mismo sitio de red (es decir, office). El enrutamiento de las llamadas salientes se realizará a través de la directiva de enrutamiento de voz del sitio de red en el que está ubicado el usuario. Las llamadas de RTC entrantes que reciba el usuario se redirigirán a los extremos ubicados en el mismo sitio de red que la puerta de enlace RTC.

- El usuario está ubicado en un sitio de red conocido y diferente del sitio de red donde se encuentra la puerta de enlace RTC (es decir, el usuario viajó a otra oficina de la compañía). El enrutamiento de las llamadas salientes utilizará la directiva de enrutamiento de voz del sitio de red en el que está ubicado el usuario. Las llamadas de RTC entrantes que reciba el usuario no se redirigirán a los extremos ubicados en sitios diferentes del de la puerta de enlace RTC, para evitar que se omitan los números de pago de RTC.

- Cuando un usuario se encuentra en un sitio de red que es desconocido para el Skype para la implementación de Business Server, el enrutamiento de llamadas salientes se basará en la directiva de voz asignada al usuario a puertas de enlace RTC no enlazado a las restricciones de enrutamiento basado en la ubicación. Las llamadas de RTC entrantes no se redirigirán a los extremos ubicados en sitios de red desconocidos, para evitar que se omitan los números de pago de RTC.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Aplicación de enrutamiento basado en la ubicación en la ubicación de la puerta de enlace del RTC

Las llamadas se enrutan a través de puertas de enlace RTC y PBX puede que necesite restricciones de enrutamiento basados en ubicación según la ubicación de los sistemas. Enrutamiento basado en la ubicación se puede habilitar en el nivel de detalle en una base por tronco.

Enrutamiento basado en ubicación presenta el siguiente conjunto de reglas cuando se habilita en un tronco:

- Cuando está habilitado el enrutamiento basado en la ubicación según la por tronco, las reglas definen en la que se aplicará tronco únicamente a las llamadas enrutadas a través de ese tronco.

- Para evitar que el sitio de red donde se encuentra la puerta de enlace de RTC de desvío de las cuotas de RTC donde las llamadas proceden de un sitio de red diferente, según la ubicación enrutamiento presenta la asociación de un sitio de red a un tronco determinado. Esto define el sitio de red que permite que las llamadas se redirijan hacia determinado tronco.

Troncos pueden habilitarse para enrutamiento basados en ubicación de dos maneras:

- El tronco se define para una puerta de enlace RTC que realiza llamadas a la RTC. Las llamadas entrantes redirigidas por un tronco de este tipo se redirigen solo a los extremos ubicados dentro del mismo sitio de red que el tronco.

- El tronco se define para un servidor de mediación del mismo nivel que no egreso las llamadas a los usuarios de RTC y servicios con teléfonos antiguos en ubicaciones estática (es decir, los teléfonos PBX). Para esta configuración en particular, todas las llamadas entrantes enrutadas por un tronco de este tipo se considerarán a ser salientes desde el mismo sitio de red que el tronco. Las llamadas de los usuarios de PBX tendrán el mismo cumplimiento de enrutamiento basado en la ubicación como Skype para los usuarios empresariales que se encuentran en el mismo sitio de red que el tronco. Si los dos sistemas PBX ubicados en sitios de red independiente están conectados a través de Skype para Business Server, enrutamiento basados en ubicación le permitirá el enrutamiento desde un extremo de PBX en un sitio de red al otro extremo de PBX en el otro sitio de red. En este escenario no se bloqueará por enrutamiento basado en la ubicación. Además de este escenario y de forma similar, como un Skype para usuarios de empresa en la misma ubicación, extremos conectados a un par de servidor de mediación con esta configuración podrá realizar o recibir llamadas a y desde otro del mismo nivel del servidor de mediación que no enrutan las llamadas t o la RTC (es decir, un extremo conectado a un sistema PBX diferente) independientemente del sitio de red al que está asociado el par de servidor de mediación. Todas las llamadas entrantes, las llamadas salientes, las transferencias y extremos de RTC que implican estarán sujetas a enrutamiento de ubicación para usar sólo puertas de enlace RTC que se definen como locales para este tipo del mismo nivel del servidor de mediación de reenvío de llamadas.

## <a name="scenarios-for-location-based-routing"></a>Escenarios para el enrutamiento basado en ubicación

El enrutamiento basado en ubicación aplica las siguientes reglas generales al redirigir llamadas en los siguientes escenarios.

### <a name="outgoing-calls"></a>Llamadas salientes

El enrutamiento de llamadas salientes de los usuarios habilitados para enrutamiento basados en ubicación se ve afectado por la ubicación de red del extremo del usuario. En la siguiente tabla ilustra cómo basados en ubicación afecta a de enrutamiento el enrutamiento de llamadas salientes según la ubicación del extremo del autor de la llamada.

**El autor de la llamada hace una llamada saliente a la RTC**

||**El extremo del usuario se encuentra en un sitio de red habilitado para el enrutamiento basado en ubicación**|**El extremo del usuario se encuentra en un sitio de red desconocido o no habilitado para el enrutamiento basado en ubicación**|
|:-----|:-----|:-----|
|Autorización de llamadas salientes  <br/> |Llamada está autorizada en función de la directiva de voz del usuario  <br/> |Llamada está autorizada en función de la directiva de voz del usuario  <br/> |
|Enrutamiento de llamadas salientes  <br/> |Llamada se enruta según la directiva de enrutamiento de voz del sitio de red  <br/> |Llamada se enruta de acuerdo con la directiva de voz del usuario y sólo a través de troncos no habilitados para enrutamiento basados en ubicación (si está disponible)  <br/> |

### <a name="incoming-calls"></a>Llamadas entrantes

El enrutamiento de las llamadas entrantes a los usuarios habilitados para enrutamiento basados en ubicación depende de la ubicación del extremo del usuario. El enrutamiento de llamadas entrantes se ve afectado de la siguiente manera. Si un usuario tiene una llamada entrante a un extremo que se encuentra en un enrutamiento basados en ubicación habilitado para el sitio de red y el extremo se encuentra en el mismo sitio de red como la puerta de enlace de RTC, se van a enrutar la llamada. Si un usuario tiene una llamada entrante a un extremo que se encuentra en un enrutamiento basados en ubicación habilitado para el sitio de red y el extremo se encuentra en un sitio de red distinta que la puerta de enlace de RTC, no se van a enrutar la llamada. Cuando un usuario no tiene ningún extremo que se encuentra en el mismo sitio de red como la puerta de enlace RTC donde se origina la llamada entrante, la llamada entrante se van a enrutar directamente al correo de voz del usuario y se van a enviar una notificación de llamada perdida a la parte de la llamada.

La configuración de un usuario que está habilitado para enrutamiento basado en la ubicación de transferencia de llamada se siguen aplicando, sin embargo, las llamadas que se desvíen estarán sujetas a las restricciones de enrutamiento basado en la ubicación del usuario.

En la siguiente tabla ilustra cómo basados en ubicación enrutamiento afecta el enrutamiento de las llamadas entrantes según la ubicación del extremo del destinatario de la llamada. El sitio de red de la puerta de enlace RTC está habilitado para enrutamiento basado en la ubicación y enrutamiento basados en ubicación solo permite el enrutamiento de llamadas de RTC a los extremos dentro del mismo sitio de red.

**El destinatario recibe una llamada entrante desde la RTC**

||**Extremo del destinatario de la llamada que se encuentra en el mismo sitio de red como puerta de enlace RTC**|**Extremo del destinatario de la llamada que no se encuentra en el mismo sitio de red como puerta de enlace RTC**|**Extremo del destinatario de la llamada que se encuentra en el sitio de red desconocido o no habilitado para enrutamiento basados en ubicación**|
|:-----|:-----|:-----|:-----|
|Enrutamiento de una llamada RTC entrante  <br/> |Llamada entrante se enruta a los extremos del destinatario de la llamada  <br/> |Llamada entrante no se enruta a los extremos del destinatario de la llamada  <br/> |Llamada entrante no se enruta a los extremos del destinatario de la llamada  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Transferencia y desvío de llamadas

Cuando se trate de un extremo de RTC, la ubicación del extremo de la calle y el extremo donde la llamada se transfiere o reenviar a (es decir, el destino de transferencia o reenvío) analiza el enrutamiento basado en la ubicación. Enrutamiento basado en la ubicación determina si se debe transferirse o reenviarse según la ubicación de ambos extremos de la llamada.

En la siguiente tabla ilustra el escenario de un Skype para usuarios de empresa en una llamada con un extremo de RTC y la Skype para usuarios de empresa transfiere la llamada a otro Skype para usuarios de empresa. Según la ubicación de sitio de red del extremo del cesionario, afecta al enrutamiento basados en ubicación hacia delante o el enrutamiento de la transferencia de llamadas.

**Inicio de la transferencia o el desvío de la llamada**

|**Usuario que inicia la transferencia o el desvío de la llamada**|**El extremo de destino está en el mismo sitio de red que el usuario que inicia la transferencia o el desvío de la llamada**|**El extremo de destino está en un sitio de red diferente del sitio del usuario que inicia la transferencia o el desvío de la llamada**|**Extremo de destino en el sitio de red desconocido o sitio de red no está habilitado para enrutamiento basados en ubicación**|
|:-----|:-----|:-----|:-----|
|Skype para usuarios de empresa  <br/> |Se permite el desvío o la transferencia de la llamada  <br/> |No se permite el desvío ni la transferencia de la llamada  <br/> |No se permite el desvío ni la transferencia de la llamada  <br/> |

Por ejemplo: un Skype para usuarios de empresa en una llamada con un extremo de RTC transfiere la llamada a otro Skype para usuarios de empresa que se están en el mismo sitio de red. En este caso, se permite la transferencia de la llamada.

En la siguiente tabla ilustra el escenario de un Skype para usuarios de empresa en una llamada con otra Skype para usuarios de empresa y uno de los usuarios transfiere la llamada a un extremo de RTC. La tabla recoge los detalles de cómo el enrutamiento basado en ubicación afecta a la llamada en función de la ubicación del usuario al que se transfiere la llamada.

**Transferencia o desvío de la llamada al extremo de RTC**

|**Destino del extremo de la transferencia o el desvío de la llamada**|**Skype para los usuarios de negocio en el mismo sitio de red**|**Skype para los usuarios de negocio en sitios de red diferentes**|**Uno o ambos Skype para los usuarios de negocio en el sitio de red desconocido o no habilitado para enrutamiento basado en la ubicación de sitio de red**|
|:-----|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Desviar llamadas o transferencia permitida por la directiva de enrutamiento de voz de sitio del usuario transferidos  <br/> |Desviar llamadas o transferencia permitida por la directiva de enrutamiento de voz de sitio del usuario transferidos  <br/> |Desviar llamadas o transferencia permitida por la directiva de voz del usuario transferidos sólo a través de troncos no habilitado para enrutamiento basados en ubicación  <br/> |

Por ejemplo: un Skype para usuarios de empresa en una llamada con otra Skype para usuarios de empresa que se están en el mismo sitio de red transfiere la llamada a un extremo de RTC y se permite la transferencia de llamadas.

### <a name="simultaneous-ringing"></a>Llamadas simultáneas

Cuando el receptor tiene habilitadas las llamadas simultáneas, analiza el enrutamiento basado en la ubicación de la ubicación de la parte que llama y los extremos de las partes llamados para determinar si se debe enrutar la llamada.

En la siguiente tabla se muestra un usuario con la configuración de llamadas simultáneas habilitada y el destino de llamadas simultáneas es un usuario en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido.

****

|**Llamada RTC entrante para**|**Ubicado en el mismo sitio de red que el destinatario**|**Ubicado en un sitio de red distinto del sitio del destinatario**|**Que se encuentra en el sitio de red desconocido o no habilitado para enrutamiento basados en ubicación**|
|:-----|:-----|:-----|:-----|
|Skype para usuarios de empresa  <br/> |Llamadas simultáneas permitidas  <br/> |Llamadas simultáneas no permitidas  <br/> |Llamadas simultáneas no permitidas  <br/> |

En la siguiente tabla ilustra una llamada desde un Skype para usuarios de empresa (es decir, Skype para el autor de la llamada empresarial) en el mismo sitio de red, en un sitio de red distinta, o desde un sitio de red desconocido. El destinatario de la llamada tiene un extremo de RTC (es decir, cellphone) configurado como un destino de la llamada simultánea. En este escenario, el enrutamiento basado en la ubicación determinará si se debe enrutar la llamada al destino de la llamada simultánea (es decir, cellphone) del destinatario de la llamada o no.

****

|**Destino de llamadas simultáneas**|**Ubicado en el mismo sitio de red que el destinatario**|**Ubicado en un sitio de red distinto del sitio del destinatario**|**Que se encuentra en el sitio de red desconocido o no habilitado para enrutamiento basados en ubicación**|
|:-----|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Llamada simultánea permitida a través de la directiva de enrutamiento de voz de sitio del autor de la llamada  <br/> |Llamada simultánea permitida a través de la directiva de enrutamiento de voz de sitio del autor de la llamada  <br/> |Llamada simultánea permitida a través de la directiva de voz el autor de la llamada a troncos no habilitado para enrutamiento basados en ubicación  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Actualización acumulativa 4 de Skype Empresarial

Con la actualización acumulativa 4, verá lo siguiente:

- Enrutamiento basado en ubicación seguirán a habilitarse mediante una directiva de voz, incluidos Skype para clientes empresariales móviles.

- El comportamiento de llamada de Skype para clientes móviles de negocio se basará en si están habilitados para el enrutamiento basado en la ubicación y el cliente de comunicación. Está pensado para ser estático, pero, en determinados casos, se puede realizar un esfuerzo por asociar un cliente de Skype Empresarial para móviles con una puerta de enlace RTC local y permitir determinados comportamientos, como una escalación.

- Independientemente del sistema operativo, su cliente de Skype Empresarial para móviles debe tener la misma funcionalidad.

En la siguiente tabla se recorren algunos de los escenarios posteriores a la actualización acumulativa 4: 

|**Usuario de enrutamiento basada en ubicación**|**Terceros**|**Acción**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype para profesionales Mobile recibe una llamada entrante de RTC.  <br/> |La llamada se redirige a través de Vía trabajo (CvW) en lugar de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype para profesionales Mobile realiza una llamada de RTC saliente.  <br/> |La llamada se redirige a través de (CvW) en lugar de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype Empresarial para móviles está en una llamada RTC. Skype para Mobile empresariales, a continuación, pasa la llamada a otro usuario o contacto.  <br/> |La llamada se redirige a través de VoIP si el usuario o el contacto es local en la sección de puerta de enlace RTC.  <br/> Si el usuario o el contacto es remoto para la sección de puerta de enlace RTC, la llamada se redirige a través de CvW.  <br/> Si no es posible contactar con el usuario de destino a través de RTC, se produce un error en la llamada.  <br/> Si el contacto de destino es un operador automático de conferencia (CAA), la llamada se bloquea.  <br/> |
|Skype Empresarial para móviles  <br/> |Skype para cliente empresarial o un usuario federado  <br/> |Un Skype para Mobile empresarial inicia una llamada de voz a otro Skype para cliente empresarial o un usuario federado.  <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |Skype para cliente empresarial o un usuario federado  <br/> | Un Skype para cliente empresarial o un usuario federado inicia una llamada de voz a un Skype para enrutamiento de Business Mobile Location-Based de usuario. <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |Skype para cliente empresarial o un usuario federado  <br/> |Un Skype para cliente empresarial o un usuario federado está en una llamada VoIP a un Skype para el usuario móvil empresarial. Cualquiera de las partes que se pasa a un Skype adicional para el usuario empresarial o federados.  <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado  <br/> |Es un usuario federado en llamada de voz a un Skype para enrutamiento de Business Mobile Location-Based usuario; un Skype para parte del negocio Mobile pasa a un usuario de RTC.  <br/> |La llamada se bloquea.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado  <br/> |Un usuario federado está en una llamada VoIP a un Skype para enrutamiento de Business Mobile Location-Based usuario; cualquiera de las partes que se pasa a un contacto CAA.  <br/> |La llamada escalada se bloquea, con un mensaje de error apropiado.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado  <br/> |Un usuario federado está en una llamada VoIP a un Skype para enrutamiento de Business Mobile Location-Based usuario y el usuario federado que se pasa a un usuario de RTC.  <br/> |Se les permitirá o no permite la escalación según el enrutamiento basado en la ubicación del usuario federado. El Skype para la aplicación del usuario de enrutamiento Business Mobile Location-Based no realice ninguna acción.  <br/> |

### <a name="delegation"></a>Delegación

Las capacidades de delegación en Skype para la empresa se ven afectadas por el enrutamiento basado en la ubicación de la siguiente manera:

- Cuando un delegado habilitado para sitios de enrutamiento basado en la ubicación de una llamada en nombre de un administrador, directiva de voz del delegado se usa para autorizar la llamada y voz de sitio del delegado se usará la directiva de enrutamiento para enrutar la llamada

- Para las llamadas RTC entrantes a un administrador, se aplican las mismas reglas correspondientes para el reenvío de llamadas o para las llamadas simultáneas, tal como se describe en los temas Transferencias y reenvíos de llamadas y Llamadas simultáneas.

- Cuando un delegado establece un extremo de RTC como destino de la llamada simultánea, para una llamada entrante al director, la directiva de enrutamiento de voz del sitio que está asociado al tronco entrante se usará para enrutar la llamada al extremo de RTC del delegado.

- Para la delegación, se recomienda el administrador y sus delegados asociados a la que se encuentra normalmente en el mismo sitio de red.

## <a name="other-planning-considerations"></a>Otras consideraciones de planificación

Al planear el enrutamiento basado en la ubicación, debe tener en cuenta el impacto en los siguientes escenarios.

### <a name="disaster-recovery"></a>Recuperación ante desastres

Durante una conmutación por error del grupo principal a un grupo de reserva que al restaurar las operaciones normales en el grupo principal, enrutamiento basados en ubicación permanezca forzado en todas las veces durante un procedimiento ante desastres y recuperación.

### <a name="survivable-branch-appliance"></a>Aplicación de sucursal con funciones de supervivencia

Configuración de enrutamiento basados en ubicación afecta a la planeación de dónde implementar las puertas de enlace que se asocia a sus aplicaciones de sucursal con funciones de supervivencia. La puerta de enlace que se asocia a la SBA debe estar ubicada en el mismo sitio de red que su aplicación de sucursal con funciones de supervivencia; de lo contrario, los usuarios alojados en su aplicación de sucursal con funciones de supervivencia no tendrán permiso para realizar llamadas salientes si está configurado el enrutamiento basado en la ubicación. Cuando la conexión WAN entre la aplicación de sucursal con funciones de supervivencia y el sitio central está apagado, restricciones de enrutamiento basados en ubicación permanece forzado.

## <a name="client-and-server-support-for-location-based-routing"></a>Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación

Enrutamiento basado en la ubicación se exige por Skype para Business Server. Skype para Business Server puede identificar los sitios de red donde los usuarios se conectan desde dentro de la red corporativa. Dado que los usuarios remotos están fuera de la red corporativa, su ubicación se considera como desconocida.

### <a name="server-support"></a>Compatibilidad con servidores

Enrutamiento basado en ubicación requiere que Skype para Business Server o Lync Server 2013 CU1 se implementa en todos los grupos de servidores Front-End y servidores Standard Edition en una topología determinada. Si estas versiones del servidor no están instaladas, no se pueden aplicar restricciones de enrutamiento basados en ubicación totalmente.

En la siguiente tabla identifica la combinación de funciones de servidor y las versiones que se admite para el enrutamiento basado en la ubicación.

****

|**Versión del grupo**|**Versión del servidor de mediación**|**Compatible**|
|:-----|:-----|:-----|
|Skype para la actualización acumulativa de Business Server o Lync Server 2013 de febrero de 2013  <br/> |Skype para la actualización acumulativa de Business Server o Lync Server 2013 de febrero de 2013  <br/> |sí  <br/> |
|Skype para la actualización acumulativa de Business Server o Lync Server 2013 de febrero de 2013  <br/> |Lync Server 2013  <br/> |no  <br/> |
|Skype para la actualización acumulativa de Business Server o Lync Server 2013 de febrero de 2013  <br/> |Lync Server 2010  <br/> |no  <br/> |
|Skype para la actualización acumulativa de Business Server o Lync Server 2013 de febrero de 2013  <br/> |Office Communications Server 2007 R2  <br/> |no  <br/> |
|Lync Server 2013  <br/> |cualquiera  <br/> |no  <br/> |
|Lync Server 2010  <br/> |cualquiera  <br/> |no  <br/> |
|Office Communications Server 2007 R2  <br/> |cualquiera  <br/> |no  <br/> |

### <a name="client-support"></a>Compatibilidad con clientes

En la siguiente tabla identifica a los clientes que admite el enrutamiento basado en la ubicación.

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
|Lync Mobile 2013  <br/> |no  <br/> |VoIP debe estar deshabilitado para los clientes de Lync Mobile 2013 si usa los usuarios con enrutamiento basados en ubicación habilitado.  <br/> |
|Lync Mobile 2010  <br/> |sí  <br/> ||

> [!NOTE]
> Para deshabilitar VoIP de Skype para clientes empresariales, asignar una directiva de movilidad con la configuración IP Audio y vídeo, deshabilitada para todos los usuarios habilitados para enrutamiento basado en la ubicación. Para obtener más información acerca de la directiva de movilidad, vea [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Capacidades no compatibles con el enrutamiento basado en ubicación

Enrutamiento basado en la ubicación no se aplica a los siguientes tipos de interacciones. Enrutamiento basado en la ubicación no se exige cuando Skype para los extremos de negocio de interactuar con los extremos de RTC con estas capacidades.

- Marcación RTC para conferencias

- Llamadas RTC entrantes y salientes a través del grupo de respuesta

- Estacionamiento o recuperación de llamadas RTC a través del estacionamiento de llamadas

- Llamadas RTC entrantes al servicio de anuncio

- Llamadas RTC entrantes recuperadas a través de la atención de llamadas de grupo

Para aplicar las reglas de enrutamiento basado en la ubicación a los tipos de interacciones en la siguiente lista, debe habilitar el enrutamiento basado en la ubicación para las conferencias:

- Iniciar llamadas RTC desde una conferencia

- Escalaciones desde conversaciones de audio de punto a punto a conferencias en las que participen extremos de RTC

- Transferencias de consulta con extremos de RTC

Para habilitar el enrutamiento basado en la ubicación para las conferencias, vea [enrutamiento basados en ubicación para las conferencias](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).



---
title: Planear el enrutamiento basado en la ubicación en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planear el enrutamiento basado en la ubicación en Skype empresarial Server Enterprise Voice, incluida la interacción con llamadas simultáneas y la delegación y escenarios admitidos para el enrutamiento basado en la ubicación.
ms.openlocfilehash: 8c6ce8467c48231ebcab706874e70341ba431fd8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276750"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planear el enrutamiento basado en la ubicación en Skype empresarial

Planear el enrutamiento basado en la ubicación en Skype empresarial Server Enterprise Voice, incluida la interacción con llamadas simultáneas y la delegación y escenarios admitidos para el enrutamiento basado en la ubicación.

El enrutamiento basado en la ubicación permite restringir el enrutamiento de llamadas entre puntos de conexión VoIP y puntos de conexión RTC en función de la ubicación de las partes en la llamada. El enrutamiento basado en la ubicación es una característica de administración de llamadas que controla cómo se enrutan las llamadas por parte de Skype empresarial Server. Cumple con las reglas de autorización de llamadas si las llamadas se pueden enrutar a puntos de conexión PBX o RTC en función de la ubicación geográfica de la llamada de Skype empresarial.

El enrutamiento basado en ubicación introduce un nuevo conjunto de reglas que modifica el enrutamiento de llamadas RTC nacionales e internacionales para evitar que se omitan los números de pago. El enrutamiento basado en ubicación proporciona la flexibilidad para delimitar estas reglas solo a regiones específicas, a puertas de enlace específicas o a un conjunto específico de usuarios.

Los siguientes escenarios ilustran los tipos principales de restricciones que el enrutamiento basado en ubicación puede exigir:

- Llamadas de salida: el enrutamiento basado en la ubicación puede exigir llamadas salientes a una puerta de enlace RTC que se encuentra en la misma región, donde el autor de la llamada impide la omisión de llamadas RTC, lo que evita que se produzcan salidas a una puerta de enlace RTC situada en otra región como la persona que llama.

- Llamadas de entrada: el enrutamiento basado en la ubicación puede evitar llamadas RTC entrantes para llamar a puntos de conexión de Skype empresarial si el enrutamiento de la puerta de enlace RTC la llamada entrante no se encuentra en la misma región que el usuario llamado Skype empresarial.

- Regiones desconocidas: el enrutamiento basado en la ubicación restringe las llamadas a través de la RTC entrantes y salientes a los usuarios que se encuentran en ubicaciones indeterminadas (es decir, los usuarios remotos se conectan desde Internet o se encuentran en regiones desconocidas).

- Regiones internacionales: el enrutamiento basado en la ubicación exige el enrutamiento de llamadas salientes a través de puertas de enlace RTC internacionales Si no se puede encontrar una puerta de enlace local a la ubicación del usuario.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Instrucciones sobre dónde aplicar el enrutamiento basado en la ubicación

El enrutamiento basado en la ubicación, según la situación, se puede aplicar en la ubicación del sitio de red del extremo del usuario o en la ubicación del sitio de red de la puerta de enlace RTC. En este tema se proporcionan instrucciones sobre cómo se aplica el enrutamiento basado en la ubicación.

### <a name="applying-location-based-routing-at-the-users-location"></a>Aplicar enrutamiento basado en la ubicación en la ubicación del usuario

El enrutamiento basado en la ubicación se aprovecha de las mismas regiones, sitios y subredes de la red que se definen en Skype empresarial Server utilizado por E9-1-1, CAC y media bypass para aplicar las restricciones de enrutamiento de llamadas para evitar el bypass de llamadas RTC. La ubicación de un usuario viene determinada por la subred IP de los puntos de conexión de Skype empresarial del usuario. Cada subred IP está asociada a un sitio de red, y los sitios de red se agrupan en regiones de red definidas por el administrador. El enrutamiento basado en la ubicación se aplica en función del sitio de red del usuario.

Las reglas de enrutamiento basadas en ubicación se aplican por sitio de red, lo que significa que se aplicará a todos los puntos de conexión que estén habilitados para el enrutamiento basado en la ubicación que se encuentra dentro del mismo sitio de red. Los administradores pueden aplicar el enrutamiento basado en ubicación a los sitios de red que lo necesiten.

Se pueden definir directivas de enrutamiento de voz en cada sitio de red, para que todos los usuarios ubicados en el sitio de red utilicen una puerta de enlace RTC concreta para llamar a números de teléfono de RTC. Dichas directivas de enrutamiento de voz tendrán prioridad sobre el enrutamiento definido por la Directiva de voz del usuario cuando el usuario se encuentre en un sitio de red habilitado para el enrutamiento basado en la ubicación y evitará el enrutamiento de llamadas a través de otras puertas de enlace RTC habilitadas para Enrutamiento basado en la ubicación. Cuando un usuario de Skype empresarial realiza una llamada RTC, la Directiva de voz del usuario determina si el usuario puede tener autorización para realizar la llamada. Si la Directiva de voz del usuario permite al usuario realizar la llamada, el enrutamiento basado en la ubicación determina qué puerta de enlace RTC debe salir de la llamada. El enrutamiento basado en la ubicación realiza esta determinación en función de la ubicación del usuario.

La ubicación de un usuario se puede clasificar de las siguientes maneras:

- El usuario se encuentra en un sitio de red conocido habilitado para enrutamiento basado en la ubicación y su número de ha finalizado (marcado directo) finaliza en una puerta de enlace RTC situada en el mismo sitio de red (es decir, Office). El enrutamiento de las llamadas salientes se realizará a través de la directiva de enrutamiento de voz del sitio de red en el que está ubicado el usuario. Las llamadas de RTC entrantes que reciba el usuario se redirigirán a los extremos ubicados en el mismo sitio de red que la puerta de enlace RTC.

- El usuario está ubicado en un sitio de red conocido y diferente del sitio de red donde se encuentra la puerta de enlace RTC (es decir, el usuario viajó a otra oficina de la compañía). El enrutamiento de las llamadas salientes utilizará la directiva de enrutamiento de voz del sitio de red en el que está ubicado el usuario. Las llamadas de RTC entrantes que reciba el usuario no se redirigirán a los extremos ubicados en sitios diferentes del de la puerta de enlace RTC, para evitar que se omitan los números de pago de RTC.

- Cuando un usuario se encuentra en un sitio de red desconocido para la implementación de Skype empresarial Server, el enrutamiento de las llamadas salientes se basará en la política de voz asignada al usuario a las puertas de enlace RTC no enlazadas a las restricciones de enrutamiento basadas en la ubicación. Las llamadas de RTC entrantes no se redirigirán a los extremos ubicados en sitios de red desconocidos, para evitar que se omitan los números de pago de RTC.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Aplicar enrutamiento basado en la ubicación en la ubicación de la puerta de enlace RTC

Las llamadas enrutadas a través de puertas de enlace y PBX RTC pueden requerir restricciones de enrutamiento basadas en la ubicación, en función de la ubicación de dichos sistemas. El enrutamiento basado en la ubicación se puede habilitar en la granularidad según el enlace.

El enrutamiento basado en la ubicación presenta el siguiente conjunto de reglas cuando se habilita en un tronco:

- Cuando el enrutamiento basado en la ubicación está habilitado para cada troncal, las reglas definidas en ese tronco se aplicarán únicamente a las llamadas dirigidas a través de ese tronco.

- Para evitar que los peajes de RTC omitan donde las llamadas se originan desde un sitio de red diferente que el sitio de red en el que se encuentra la puerta de enlace RTC, el enrutamiento basado en la ubicación introduce la Asociación de un sitio de red a un tronco determinado. Esto define el sitio de red que permite que las llamadas se redirijan hacia determinado tronco.

Los troncos se pueden habilitar para el enrutamiento basado en la ubicación de dos maneras:

- El tronco se define para una puerta de enlace RTC que realiza llamadas a la RTC. Las llamadas entrantes redirigidas por un tronco de este tipo se redirigen solo a los extremos ubicados dentro del mismo sitio de red que el tronco.

- El tronco se define para un servidor de mediación del mismo nivel que no de salida las llamadas a los usuarios de RTC y servicios con teléfonos heredados en ubicaciones estáticas (es decir, teléfonos PBX). Para esta configuración en particular, todas las llamadas entrantes dirigidas por un tronco de este tipo se considerarán originadas desde el mismo sitio de red que el tronco. Las llamadas de usuarios de PBX tendrán la misma aplicación de enrutamiento basada en la ubicación que los usuarios de Skype empresarial que se encuentren en el mismo sitio de red que el tronco. Si dos sistemas PBX ubicados en sitios de red independientes se conectan a través de Skype empresarial Server, el enrutamiento basado en la ubicación permitirá el enrutamiento desde un extremo de PBX de un sitio de red a otro extremo de PBX en el otro sitio de red. Este escenario no quedará bloqueado por el enrutamiento basado en la ubicación. Además de este escenario y de forma similar a como usuario de Skype empresarial en la misma ubicación, los puntos de conexión conectados a un servidor de mediación del mismo nivel con esta configuración podrán realizar o recibir llamadas a otros servidores de mediación del mismo nivel que no hagan llamadas t o la RTC (es decir, un extremo conectado a un sistema PBX diferente), independientemente del sitio de red al que está asociado el servidor de mediación del mismo nivel. Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y los reenvíos que impliquen puntos de conexión RTC estarán sujetos a enrutamiento basado en la ubicación para usar solo puertas de enlace RTC definidas como locales para este servidor del mismo nivel de media.

## <a name="scenarios-for-location-based-routing"></a>Escenarios para el enrutamiento basado en ubicación

El enrutamiento basado en ubicación aplica las siguientes reglas generales al redirigir llamadas en los siguientes escenarios.

### <a name="outgoing-calls"></a>Llamadas salientes

El enrutamiento de llamadas salientes de usuarios habilitados para el enrutamiento basado en la ubicación se ve afectado por la ubicación de red del extremo del usuario. En la tabla siguiente se muestra cómo afecta el enrutamiento basado en la ubicación al enrutamiento de las llamadas salientes en función de la ubicación del punto de conexión de la llamada.

**El autor de la llamada hace una llamada saliente a la RTC**

||**El extremo del usuario se encuentra en un sitio de red habilitado para el enrutamiento basado en ubicación**|**El extremo del usuario se encuentra en un sitio de red desconocido o no habilitado para el enrutamiento basado en ubicación**|
|:-----|:-----|:-----|
|Autorización de llamadas salientes  <br/> |La llamada está autorizada en función de la Directiva de voz del usuario.  <br/> |La llamada está autorizada en función de la Directiva de voz del usuario.  <br/> |
|Enrutamiento de llamadas salientes  <br/> |La llamada se enruta según la Directiva de enrutamiento de voz del sitio de red.  <br/> |La llamada se dirige según la política de voz del usuario y solo a través de troncos no habilitados para enrutamiento basado en la ubicación (si está disponible)  <br/> |

### <a name="incoming-calls"></a>Llamadas entrantes

El enrutamiento de llamadas entrantes a los usuarios habilitados para el enrutamiento basado en la ubicación depende de la ubicación del extremo del usuario. El enrutamiento de llamadas entrantes se ve afectado de la siguiente manera. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento basado en ubicación y el punto final se encuentra en el mismo sitio de red que la puerta de enlace PSTN, la llamada se redirigirá. Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento basado en ubicación y el punto final se encuentra en un sitio de red diferente de la puerta de enlace PSTN, la llamada no se redirigirá. Cuando un usuario no tiene puntos de conexión ubicados en el mismo sitio de red que la puerta de enlace PSTN de la que se origina la llamada entrante, la llamada entrante se redirigirá directamente al buzón de voz del usuario y se enviará una notificación de llamada perdida a la persona a la que se ha llamado.

La configuración del desvío de llamadas de un usuario habilitado para el enrutamiento basado en la ubicación se seguirá aplicando; sin embargo, las llamadas desviadas estarán sujetas a las restricciones de enrutamiento basadas en la ubicación del usuario.

En la tabla siguiente se muestra cómo afecta el enrutamiento basado en la ubicación al enrutamiento de las llamadas entrantes en función de la ubicación del punto final de la llamada. El sitio de red de la puerta de enlace RTC está habilitado para el enrutamiento basado en la ubicación y el enrutamiento basado en la ubicación solo permite el enrutamiento de llamadas RTC a puntos de conexión dentro del mismo sitio de red.

**El destinatario recibe una llamada entrante desde la RTC**

||**Punto final de la llamada que se encuentra en el mismo sitio de red que la puerta de enlace RTC**|**El extremo de la persona que llama no se encuentra en el mismo sitio de red que la puerta de enlace RTC**|**El extremo del destinatario de la llamada se encuentra en un sitio de red desconocido o no está habilitado para el enrutamiento basado en la ubicación**|
|:-----|:-----|:-----|:-----|
|Enrutamiento de una llamada RTC entrante  <br/> |La llamada entrante se enruta a los puntos de conexión de la persona que llama  <br/> |La llamada entrante no se enruta a los extremos de la llamada  <br/> |La llamada entrante no se enruta a los extremos de la llamada  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Transferencia y desvío de llamadas

Cuando se trata de un punto final de RTC, el enrutamiento basado en la ubicación analiza la ubicación del extremo de la calle y el punto final al que se transferirá o desviará la llamada (es decir, el destino de transferencia/reenvío). El enrutamiento basado en la ubicación determina si la llamada se debe transferir o desviar dependiendo de la ubicación de ambos puntos de conexión.

En la tabla siguiente se muestra el escenario de un usuario de Skype empresarial en una llamada con un punto final de RTC, y el usuario de Skype empresarial transfiere la llamada a otro usuario de Skype empresarial. En función de la ubicación del sitio de red del extremo del cesionario, el enrutamiento basado en la ubicación afecta al enrutamiento de la transferencia de la llamada o hacia adelante.

**Inicio de la transferencia o el desvío de la llamada**

|**Usuario que inicia la transferencia o el desvío de la llamada**|**El extremo de destino está en el mismo sitio de red que el usuario que inicia la transferencia o el desvío de la llamada**|**El extremo de destino está en un sitio de red diferente del sitio del usuario que inicia la transferencia o el desvío de la llamada**|**El extremo de destino está en un sitio de red desconocido o el sitio de red no está habilitado para el enrutamiento basado en la ubicación**|
|:-----|:-----|:-----|:-----|
|Usuario de Skype empresarial  <br/> |Se permite el desvío o la transferencia de la llamada  <br/> |No se permite el desvío ni la transferencia de la llamada  <br/> |No se permite el desvío ni la transferencia de la llamada  <br/> |

Por ejemplo: un usuario de Skype empresarial en una llamada con un punto final de la RTC transfiere la llamada a otro usuario de Skype empresarial que se encuentra en el mismo sitio de red. En este caso, se permite la transferencia de la llamada.

En la tabla siguiente se muestra el escenario de un usuario de Skype empresarial en una llamada con otro usuario de Skype empresarial, y uno de los usuarios transfiere la llamada a un punto final de la RTC. La tabla recoge los detalles de cómo el enrutamiento basado en ubicación afecta a la llamada en función de la ubicación del usuario al que se transfiere la llamada.

**Transferencia o desvío de la llamada al extremo de RTC**

|**Destino del extremo de la transferencia o el desvío de la llamada**|**Usuarios de Skype empresarial en el mismo sitio de red**|**Usuarios de Skype empresarial en diferentes sitios de red**|**Uno o ambos usuarios de Skype empresarial en sitios de red o sitios de red desconocidos no están habilitados para el enrutamiento basado en la ubicación**|
|:-----|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Desvío de llamadas o transferencia permitida por la Directiva de enrutamiento de voz del sitio del usuario transferido  <br/> |Desvío de llamadas o transferencia permitida por la Directiva de enrutamiento de voz del sitio del usuario transferido  <br/> |Desvío de llamadas o transferencia permitida por la Directiva de voz del usuario transferido solamente a través de troncos no habilitados para enrutamiento basado en la ubicación  <br/> |

Por ejemplo: un usuario de Skype empresarial en una llamada con otro usuario de Skype empresarial que se encuentra en el mismo sitio de red transfiere la llamada a un punto final de RTC y se permite la transferencia de llamadas.

### <a name="simultaneous-ringing"></a>Tono de llamada simultáneo

Cuando la persona a la que se llama tiene habilitado el timbre simultáneo, el enrutamiento basado en la ubicación analiza la ubicación de la persona que llama y los puntos finales de las partes a las que se llama para determinar si se debe distribuir la llamada.

En la siguiente tabla se muestra un usuario con la configuración de llamadas simultáneas habilitada y el destino de llamadas simultáneas es un usuario en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido.

****

|**Llamada RTC entrante para**|**Ubicado en el mismo sitio de red que el destinatario**|**Ubicado en un sitio de red distinto del sitio del destinatario**|**Se encuentra en un sitio de red desconocido o no está habilitado para el enrutamiento basado en la ubicación**|
|:-----|:-----|:-----|:-----|
|Usuario de Skype empresarial  <br/> |Llamadas simultáneas permitidas  <br/> |Llamadas simultáneas no permitidas  <br/> |Llamadas simultáneas no permitidas  <br/> |

En la tabla siguiente se muestra una llamada de un usuario de Skype empresarial (es decir, el autor de una llamada de Skype empresarial) en el mismo sitio de red, en un sitio de red diferente o desde un sitio de red desconocido. El destinatario de la llamada tiene un punto final de la RTC (por ejemplo, teléfono móvil) configurado como un objetivo de llamada simultánea. En este escenario, el enrutamiento basado en la ubicación determinará si la llamada debe dirigirse al destino simultáneo (por ejemplo, teléfono móvil) del destinatario de la llamada.

****

|**Destino de llamadas simultáneas**|**Ubicado en el mismo sitio de red que el destinatario**|**Ubicado en un sitio de red distinto del sitio del destinatario**|**Se encuentra en un sitio de red desconocido o no está habilitado para el enrutamiento basado en la ubicación**|
|:-----|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Se permiten llamadas simultáneas a través de la Directiva de enrutamiento de voz del sitio de la persona que llama  <br/> |Se permiten llamadas simultáneas a través de la Directiva de enrutamiento de voz del sitio de la persona que llama  <br/> |Se permiten llamadas simultáneas a través de la política de voz de la persona que llama a troncos que no están habilitados para el enrutamiento basado en la ubicación  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Actualización acumulativa 4 de Skype Empresarial

Con la actualización acumulativa 4, verá lo siguiente:

- El enrutamiento basado en la ubicación seguirá habilitado a través de la Directiva de voz, incluidos los clientes móviles de Skype empresarial.

- El comportamiento de la llamada para los clientes móviles de Skype empresarial se basará en si están habilitados para el enrutamiento basado en la ubicación y en el cliente de comunicación. Está pensado para ser estático, pero, en determinados casos, se puede realizar un esfuerzo por asociar un cliente de Skype Empresarial para móviles con una puerta de enlace RTC local y permitir determinados comportamientos, como una escalación.

- Independientemente del sistema operativo, su cliente de Skype Empresarial para móviles debe tener la misma funcionalidad.

En la siguiente tabla se recorren algunos de los escenarios posteriores a la actualización acumulativa 4: 

|**Usuario de enrutamiento basado en la ubicación**|**Terceros**|**Acción**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype empresarial Mobile recibe una llamada RTC entrante.  <br/> |La llamada se redirige a través de Vía trabajo (CvW) en lugar de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype empresarial Mobile hace una llamada RTC saliente.  <br/> |La llamada se redirige a través de (CvW) en lugar de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype Empresarial para móviles está en una llamada RTC. A continuación, Skype empresarial Mobile escala la llamada a otro usuario o contacto.  <br/> |La llamada se redirige a través de VoIP si el usuario o el contacto es local en la sección de puerta de enlace RTC.  <br/> Si el usuario o el contacto es remoto para la sección de puerta de enlace RTC, la llamada se redirige a través de CvW.  <br/> Si no es posible contactar con el usuario de destino a través de RTC, se produce un error en la llamada.  <br/> Si el contacto de destino es un operador automático de conferencia (CAA), la llamada se bloquea.  <br/> |
|Skype Empresarial para móviles  <br/> |Cliente de Skype empresarial o usuario federado  <br/> |Un teléfono móvil de Skype empresarial inicia una llamada de voz a otro cliente de Skype empresarial o a un usuario federado.  <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |Cliente de Skype empresarial o usuario federado  <br/> | Un cliente de Skype empresarial o un usuario federado inicia una llamada de voz a un usuario de enrutamiento basado en una ubicación móvil de Skype empresarial. <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |Cliente de Skype empresarial o usuario federado  <br/> |Un cliente de Skype empresarial o un usuario federado está en una llamada VoIP a un usuario móvil de Skype empresarial. Cualquiera de las partes se escala a un usuario adicional de Skype empresarial o federado.  <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado  <br/> |Un usuario federado está en una llamada de voz a un usuario de enrutamiento basado en una ubicación móvil de Skype empresarial; una fiesta de Skype empresarial Mobile escala a un usuario de la RTC.  <br/> |La llamada se bloquea.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado  <br/> |Un usuario federado se encuentra en una llamada VoIP a un usuario de enrutamiento basado en una ubicación móvil de Skype empresarial; cualquier parte se eleva a un contacto de CAA.  <br/> |La llamada escalada se bloquea, con un mensaje de error apropiado.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado  <br/> |Un usuario federado se encuentra en una llamada VoIP a un usuario de enrutamiento basado en una ubicación móvil de Skype empresarial, y el usuario federado escala a un usuario de la RTC.  <br/> |La escala se permitirá o no se basará en el enrutamiento basado en la ubicación del usuario federado. La aplicación de usuario de enrutamiento basado en la ubicación móvil de Skype empresarial no realiza ninguna acción.  <br/> |

### <a name="delegation"></a>Delegación

Las capacidades de delegación de Skype empresarial se ven afectadas por el enrutamiento basado en la ubicación de la siguiente manera:

- Cuando un delegado habilitado para el enrutamiento basado en la ubicación realiza una llamada en nombre de un administrador, se usa la Directiva de voz del delegado para autorizar la llamada y se usará la Directiva de enrutamiento de voz del sitio del delegado para enrutar la llamada

- Para las llamadas RTC entrantes a un administrador, se aplican las mismas reglas correspondientes para el reenvío de llamadas o para las llamadas simultáneas, tal como se describe en los temas Transferencias y reenvíos de llamadas y Llamadas simultáneas.

- Cuando un delegado establece un punto final de la RTC como un destino de llamada simultánea, para una llamada entrante al administrador, se usará la Directiva de enrutamiento de voz del sitio asociado al tronco entrante para enrutar la llamada al punto final de la RTC del delegado.

- Para la delegación, se recomienda que el administrador y sus delegados asociados se encuentren generalmente en el mismo sitio de red.

## <a name="other-planning-considerations"></a>Otras consideraciones de planificación

Al planear el enrutamiento basado en la ubicación, debe considerar el impacto en los siguientes escenarios.

### <a name="disaster-recovery"></a>Recuperación ante desastres

Durante una conmutación por error del repositorio principal a un grupo de copia de seguridad, así como al restaurar operaciones normales en el repositorio principal, el enrutamiento basado en la ubicación se mantiene en todo momento durante un procedimiento de recuperación ante desastres.

### <a name="survivable-branch-appliance"></a>Aplicación de sucursal con funciones de supervivencia

La configuración del enrutamiento basado en la ubicación afecta al planeamiento de la ubicación en la que se implementan las puertas de enlace asociadas a los dispositivos de las sucursales que son revivientes. La puerta de enlace asociada a su SBA debe estar ubicada en el mismo sitio de red que su equipo de sucursal con la supervivencia; de lo contrario, los usuarios alojados en su equipo de sucursal con su supervivencia no podrán realizar llamadas salientes si el enrutamiento basado en la ubicación está configurado. Cuando la conexión WAN entre el equipo de la sucursal y el sitio central está inactivo, se exige la aplicación de las restricciones de enrutamiento basadas en la ubicación.

## <a name="client-and-server-support-for-location-based-routing"></a>Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación

Skype empresarial Server exige el enrutamiento basado en la ubicación. Skype empresarial Server puede identificar los sitios de red desde los que se conectan los usuarios dentro de la red corporativa. Dado que los usuarios remotos están fuera de la red corporativa, su ubicación se considera como desconocida.

### <a name="server-support"></a>Compatibilidad con servidores

El enrutamiento basado en la ubicación requiere que Skype empresarial Server o Lync Server 2013 CU1 se implemente en todas las agrupaciones front end y servidores Standard Edition en una topología dada. Si estas versiones del servidor no están instaladas, las restricciones de enrutamiento basadas en la ubicación no se pueden aplicar por completo.

En la siguiente tabla se identifica la combinación de las versiones y los roles de servidor que se admiten para el enrutamiento basado en la ubicación.

****

|**Versión del grupo**|**Versión del servidor de mediación**|**Compatible**|
|:-----|:-----|:-----|
|Skype empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Skype empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |sí  <br/> |
|Skype empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Lync Server 2013  <br/> |no  <br/> |
|Skype empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Lync Server 2010  <br/> |no  <br/> |
|Skype empresarial Server o Lync Server 2013 de febrero de 2013  <br/> |Office Communications Server 2007 R2  <br/> |no  <br/> |
|Lync Server 2013  <br/> |cualquiera  <br/> |no  <br/> |
|Lync Server 2010  <br/> |cualquiera  <br/> |no  <br/> |
|Office Communications Server 2007 R2  <br/> |cualquiera  <br/> |no  <br/> |

### <a name="client-support"></a>Compatibilidad con clientes

La siguiente tabla identifica los clientes que admite el enrutamiento basado en la ubicación.

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
|Lync Mobile 2013  <br/> |no  <br/> |El VoIP debe estar deshabilitado para los clientes de Lync Mobile 2013 si lo usan los usuarios con el enrutamiento basado en la ubicación habilitado.  <br/> |
|Lync Mobile 2010  <br/> |sí  <br/> ||

> [!NOTE]
> Para deshabilitar VoIP para los clientes de Skype empresarial, asigne una directiva de movilidad con la configuración, audio/vídeo IP, deshabilitado para todos los usuarios habilitados para el enrutamiento basado en la ubicación. Para obtener más detalles sobre la directiva de movilidad, mira [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Capacidades no compatibles con el enrutamiento basado en ubicación

El enrutamiento basado en la ubicación no se aplica a los siguientes tipos de interacciones. El enrutamiento basado en la ubicación no se aplica cuando los puntos de conexión de Skype empresarial interactúan con puntos de conexión RTC usando estas funciones.

- Marcación RTC para conferencias

- Llamadas RTC entrantes y salientes a través del grupo de respuesta

- Estacionamiento o recuperación de llamadas RTC a través del estacionamiento de llamadas

- Llamadas RTC entrantes al servicio de anuncio

- Llamadas RTC entrantes recuperadas a través de la atención de llamadas de grupo

Para aplicar reglas de enrutamiento basadas en la ubicación a los tipos de interacciones de la siguiente lista, debe habilitar el enrutamiento basado en la ubicación para las conferencias:

- Iniciar llamadas RTC desde una conferencia

- Escalaciones desde conversaciones de audio de punto a punto a conferencias en las que participen extremos de RTC

- Transferencias de consulta con extremos de RTC

Para habilitar el enrutamiento basado en la ubicación de las conferencias, consulte [enrutamiento basado en la ubicación para conferencias](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).



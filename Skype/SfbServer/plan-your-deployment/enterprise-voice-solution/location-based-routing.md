---
title: Planificar el enrutamiento basado en ubicación en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/7/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planear la ubicación enrutamiento en Skype para Telefonía IP empresarial de servidor empresarial, incluida la interacción con Timbre simultáneo y delegación y escenarios admitidos para el enrutamiento basado en la ubicación.
ms.openlocfilehash: 90bf8605f7708d2e444d64005144c30638e03d4a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-location-based-routing-in-skype-for-business-2015"></a>Planificar el enrutamiento basado en ubicación en Skype Empresarial Server 2015
 
Planear la ubicación enrutamiento en Skype para Telefonía IP empresarial de servidor empresarial, incluida la interacción con Timbre simultáneo y delegación y escenarios admitidos para el enrutamiento basado en la ubicación.
  
Enrutamiento basado en ubicación permite restringir el enrutamiento de llamadas entre extremos de VoIP y extremos PSTN según la ubicación de las partes en la llamada. Enrutamiento basado en la ubicación es una característica de administración de llamada que controla cómo se enrutan las llamadas por Skype para Business Server. Aplica las reglas de autorización de llamada sobre si se pueden enrutar llamadas a extremos de PBX o RTC tomando como base el Skype para la ubicación geográfica del llamador de la empresa.
  
El enrutamiento basado en ubicación introduce un nuevo conjunto de reglas que modifica el enrutamiento de llamadas RTC nacionales e internacionales para evitar que se omitan los números de pago. El enrutamiento basado en ubicación proporciona la flexibilidad para delimitar estas reglas solo a regiones específicas, a puertas de enlace específicas o a un conjunto específico de usuarios.
  
Los siguientes escenarios ilustran los principales tipos de restricciones que puede imponer el enrutamiento basado en la ubicación:
  
- Llamadas de salida - enrutamiento según ubicación puede exigir llamadas salientes a egreso a una puerta de enlace PSTN que se encuentra en la misma región como dónde está el llamador evitar que la omisión de peaje PSTN, que evita que las llamadas a egreso a una puerta de enlace PSTN situado en una región distinta que el llamador.
    
- Llamadas de entrada - enrutamiento según ubicación puede impedir que las llamadas entrantes de PSTN a sonar Skype para extremos de negocio si la puerta de enlace PSTN enrutar la llamada entrante no se encuentra en la misma región como el llamado Skype para usuarios de empresa.
    
- Regiones desconocidas - enrutamiento según ubicación restringe llamadas PSTN entrantes y salientes desde y hacia los usuarios que se encuentran en ubicaciones indeterminados (es decir, los usuarios remotos conectarse desde Internet o situadas en regiones desconocidas).
    
- Regiones internacionales - enrutamiento según ubicación exige el enrutamiento de llamadas a través de puertas de enlace PSTN internacionales de salida si no se encuentra una puerta de enlace local a la ubicación del usuario.
    
## <a name="guidance-for-where-to-apply-location-based-routing"></a>Guía de dónde aplicar enrutamiento según ubicación

Enrutamiento basado en la ubicación según la situación puede aplicarse en ubicación de sitio de red de extremo del usuario o en la ubicación del sitio de red del gateway PSTN. Este tema proporciona orientación sobre cómo ubicación de enrutamiento se aplica.
  
### <a name="applying-location-based-routing-at-the-users-location"></a>Aplicación de enrutamiento basado en la ubicación a la ubicación del usuario

Ubicación basada en enrutamiento aprovecha la misma red regiones, sitios y subredes, tal como se define en Skype para Business Server utiliza E9-1-1, CAC y omitir los medios para aplicar restricciones de enrutamiento de llamadas para evitar llamadas PSTN pasan por alto. Ubicación de un usuario se determina por la subred IP de Skype del usuario para extremos de negocio están conectados desde. Cada subred IP está asociada a un sitio de red, y los sitios de red se agrupan en regiones de red definidas por el administrador. Enrutamiento basado en ubicación se aplica según el sitio de red del usuario.
  
Se aplican las reglas de enrutamiento basado en la ubicación de una por cada sitio de red, lo que significa que un determinado conjunto de reglas se aplicarán a todos los extremos habilitados para enrutamiento basado en la ubicación que se encuentran dentro del mismo sitio de red. Los administradores pueden aplicar el enrutamiento basado en ubicación a los sitios de red que lo necesiten.
  
Se pueden definir directivas de enrutamiento de voz en cada sitio de red, para que todos los usuarios ubicados en el sitio de red utilicen una puerta de enlace RTC concreta para llamar a números de teléfono de RTC. Estas directivas de enrutamiento de voz tiene prioridad sobre la ruta definida por la directiva de la voz del usuario cuando el usuario se encuentra en un sitio de red habilitado para enrutamiento basado en ubicación y evitará que el enrutamiento de llamadas a través de otras puertas de enlace de RTC que están habilitados para Ubicación de enrutamiento. Cuando un Skype para usuarios de empresa coloca una llamada PSTN, directiva de voz del usuario determina si el usuario puede estar autorizado para realizar la llamada. Si la directiva de la voz del usuario permite al usuario realizar la llamada, enrutamiento según ubicación determina qué puerta de enlace PSTN la llamada debe egreso desde. Enrutamiento basado en ubicación hace esta decisión basándose en la ubicación del usuario.
  
La ubicación de un usuario se puede clasificar de las siguientes maneras:
  
- El usuario se encuentra en un sitio de red conocida habilitado para enrutamiento basado en ubicación y su número DID (discado directo entrante) termina en una puerta de enlace PSTN colocado en el mismo sitio de la red (por ejemplo, office). El enrutamiento de las llamadas salientes se realizará a través de la directiva de enrutamiento de voz del sitio de red en el que está ubicado el usuario. Las llamadas de RTC entrantes que reciba el usuario se redirigirán a los extremos ubicados en el mismo sitio de red que la puerta de enlace RTC.
    
- El usuario está ubicado en un sitio de red conocido y diferente del sitio de red donde se encuentra la puerta de enlace RTC (es decir, el usuario viajó a otra oficina de la compañía). El enrutamiento de las llamadas salientes utilizará la directiva de enrutamiento de voz del sitio de red en el que está ubicado el usuario. Las llamadas de RTC entrantes que reciba el usuario no se redirigirán a los extremos ubicados en sitios diferentes del de la puerta de enlace RTC, para evitar que se omitan los números de pago de RTC.
    
- Cuando un usuario se encuentra en un sitio de red que es desconocido para el Skype para la implementación de Business Server, el enrutamiento de llamadas salientes se basará en la directiva de voz asignada al usuario para puertas de enlace PSTN no enlazado a restricciones de enrutamiento basado en la ubicación. Las llamadas de RTC entrantes no se redirigirán a los extremos ubicados en sitios de red desconocidos, para evitar que se omitan los números de pago de RTC. 
    
### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Aplicación de enrutamiento basadas en ubicación en ubicación del gateway PSTN

Las llamadas se enrutan a través de puertas de enlace PSTN y PBX podrían requerir restricciones de enrutamiento basado en ubicación dependiendo de la ubicación de dichos sistemas. Enrutamiento basado en la ubicación se puede habilitar en la granularidad en una base de cada tronco.
  
Enrutamiento basado en ubicación presenta el siguiente conjunto de reglas cuando se habilita en un tronco:
  
- Cuando está habilitado el enrutamiento basado en la ubicación en una base de cada tronco, las reglas definen en que tronco se aplicará únicamente a las llamadas enrutadas a través de ese tronco.
    
- Para evitar que el sitio de la red donde se encuentra la puerta de enlace PSTN de PSTN peajes bypass donde las llamadas proceden de un sitio de red diferentes, según ubicación enrutamiento presenta la asociación de un sitio de red a un tronco determinado. Esto define el sitio de red que permite que las llamadas se redirijan hacia determinado tronco.
    
Los troncos pueden habilitarse para el enrutamiento basado en la ubicación de dos maneras:
  
- El tronco se define para una puerta de enlace RTC que realiza llamadas a la RTC. Las llamadas entrantes redirigidas por un tronco de este tipo se redirigen solo a los extremos ubicados dentro del mismo sitio de red que el tronco.
    
- El tronco se define para un servidor de mediación del mismo nivel que no egreso llamadas a los usuarios servicios y PSTN con teléfonos antiguos en una ubicación estática (es decir, teléfonos PBX). Para esta configuración particular, todas las llamadas entrantes que se enrutan por un tronco de este tipo se considerará proceden del mismo sitio de red que el tronco. Llamadas de los usuarios de la PBX tendrá el mismo cumplimiento de enrutamiento basado en la ubicación como Skype para usuarios profesionales que se encuentran en el mismo sitio de red que el tronco. Si dos sistemas PBX en sitios de red independientes se conectan a través de Skype para Business Server, basada en la ubicación de enrutamiento permitirá enrutamiento desde un extremo de PBX en un sitio de red a otro extremo PBX en el otro sitio de red. Este escenario no se bloqueará por enrutamiento basado en la ubicación. Además de este escenario y de forma similar a como un Skype para usuarios de empresa en la misma ubicación, extremos conectados a un mismo nivel de servidor de mediación con esta configuración podrá realizar o recibir llamadas desde otro interlocutor de servidor de mediación y que no se enrutan llamadas t o PSTN (es decir, un extremo conectado a un sistema PBX diferentes) independientemente del sitio de red al que está asociado el interlocutor de servidor de mediación. Todas las llamadas entrantes, llamadas salientes, llame a transferencias y llamar remite relacionada con extremos PSTN se someterán a la ubicación de enrutamiento basado en utilizar sólo puertas de enlace PSTN que se definen como local a tal punto de servidor de mediación.
    
## <a name="scenarios-for-location-based-routing"></a>Escenarios para el enrutamiento basado en ubicación

El enrutamiento basado en ubicación aplica las siguientes reglas generales al redirigir llamadas en los siguientes escenarios.
  
### <a name="outgoing-calls"></a>Llamadas salientes

El enrutamiento de llamadas salientes de los usuarios habilitados para enrutamiento según ubicación se ve afectado por la ubicación de red de extremo del usuario. En la siguiente tabla ilustra afecta a cómo basados en ubicación de enrutamiento el enrutamiento de llamadas salientes según la ubicación del punto final del llamador. 
  
**Llamador colocando una llamada saliente a la RTC**

||**Extremo de usuario ubicado en un sitio de red habilitado para enrutamiento según ubicación**|**Extremo de usuario ubicado en el sitio de red desconocido o no habilitado para enrutamiento según ubicación**|
|:-----|:-----|:-----|
|Autorización de llamadas salientes  <br/> |Llamada está autorizada según directiva de voz del usuario  <br/> |Llamada está autorizada según directiva de voz del usuario  <br/> |
|Enrutamiento de llamadas salientes  <br/> |Llamadas se desvían según la directiva de enrutamiento de voz del sitio de red  <br/> |Llamada se enruta según la directiva de voz del usuario y sólo a través de los troncos no habilitados para enrutamiento basado en la ubicación (si está disponible)  <br/> |
   
### <a name="incoming-calls"></a>Llamadas entrantes

El enrutamiento de llamadas entrantes a los usuarios habilitados para enrutamiento según ubicación depende de la ubicación del extremo del usuario. El enrutamiento de llamadas entrantes se ve afectado de la siguiente manera. Si un usuario tiene una llamada entrante a un extremo que se encuentra en una ruta basada en la ubicación habilitada en el sitio de red y el extremo se encuentra en el mismo sitio de red que la puerta de enlace PSTN, se enrutarán la llamada. Si un usuario tiene una llamada entrante a un extremo que se encuentra en una ruta basada en la ubicación habilitada en el sitio de red y el extremo se encuentra en un sitio de red diferente que la puerta de enlace PSTN, la llamada no se enrutarán. Cuando un usuario no tiene ningún extremo ubicado en el mismo sitio de red como la puerta de enlace PSTN donde se origina la llamada entrante, la llamada entrante se dirigirán directamente al correo de voz del usuario y se enviará una notificación de llamada perdida para el receptor.
  
La configuración de un usuario habilitado para enrutamiento basado en ubicación de reenvío de llamadas se siguen aplicando, sin embargo, las llamadas se desvían estará sujeto a las restricciones de enrutamiento basado en la ubicación del usuario.
  
En la siguiente tabla ilustra afecta a cómo basados en ubicación de enrutamiento el enrutamiento de llamadas entrantes según la ubicación del extremo del destinatario de la llamada. El sitio de red de la puerta de enlace PSTN está habilitado para enrutamiento basado en ubicación y enrutamiento basado en ubicación sólo permite el enrutamiento de llamadas PSTN a extremos dentro del mismo sitio de red.
  
**Destinatario recibe una llamada entrante desde la PSTN**

||**Extremo del destinatario que se encuentra en el mismo sitio de la red como puerta de enlace PSTN**|**Extremo del destinatario que no se encuentra en el mismo sitio de la red como puerta de enlace PSTN**|**Extremo del destinatario ubicado en el sitio de red desconocido o no habilitado para enrutamiento según ubicación**|
|:-----|:-----|:-----|:-----|
|Enrutamiento de una llamada RTC entrante  <br/> |Llamada entrante se enruta a los extremos del destinatario  <br/> |Llamada entrante no se enruta a los extremos del destinatario  <br/> |Llamada entrante no se enruta a los extremos del destinatario  <br/> |
   
### <a name="call-transfers-and-call-forwarding"></a>Transferencia y desvío de llamadas

Cuando hay implicado un extremo PSTN, enrutamiento según ubicación analiza la ubicación del extremo de la calle y el extremo donde la llamada se transfiere o reenviada a (es decir, el destino de transferencia o reenvío). Enrutamiento basado en ubicación determina si la llamada se debe transferir o reenviarse dependiendo de la ubicación de ambos extremos.
  
La tabla siguiente ilustra el escenario de un Skype para usuarios de empresa en una llamada con un extremo PSTN y el Skype para usuarios de empresa transfiere la llamada a otro Skype para usuarios de empresa. Dependiendo de la ubicación del sitio de red de extremo del cesionario, enrutamiento basado en la ubicación afecta al enrutamiento de la transferencia de llamada o directa.
  
**Iniciar llamada, transferir o reenviar**

|**Usuario que inicia la llamada transferencia o reenvío**|**Extremo de destino está en el mismo sitio de red como el usuario que inicia la transferencia de llamadas o reenviar**|**Extremo de destino está en el sitio de red diferentes como el usuario que inicia la transferencia de llamadas o reenviar**|**Extremo de destino en el sitio de red desconocido o de red no está habilitada para enrutamiento según ubicación**|
|:-----|:-----|:-----|:-----|
|Skype para usuarios de empresa  <br/> |Se permite el desvío o la transferencia de la llamada  <br/> |No se permite el desvío ni la transferencia de la llamada  <br/> |No se permite el desvío ni la transferencia de la llamada  <br/> |
   
Por ejemplo: un Skype para usuarios de empresa en una llamada con un extremo PSTN transfiere la llamada a otro Skype para usuarios de empresa que se están en el mismo sitio de red. En este caso, se permite la transferencia de la llamada. 
  
La tabla siguiente ilustra el escenario de un Skype para usuarios de empresa en una llamada con otro Skype para usuarios de empresa y uno de los usuarios transfiere la llamada a un extremo de RTC. La tabla recoge los detalles de cómo el enrutamiento basado en ubicación afecta a la llamada en función de la ubicación del usuario al que se transfiere la llamada.
  
**Transferencia de llamadas o reenviar al extremo PSTN**

|**Llame al destino de transferencia o reenvío extremo**|**Skype para usuarios de negocios en el mismo sitio de red**|**Skype para usuarios profesionales de sitios de red diferente**|**Uno o ambos Skype para usuarios profesionales en el sitio de red desconocido o no habilitado para enrutamiento basado en la ubicación de sitio de red**|
|:-----|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Llame al reenviar o transferencia permitido por la directiva de enrutamiento de voz del usuario transferidos sitio  <br/> |Llame al reenviar o transferencia permitido por la directiva de enrutamiento de voz del usuario transferidos sitio  <br/> |Llame al reenviar o transferencia permitida por la directiva de voz del usuario transferidos sólo a través de los troncos no habilitado para enrutamiento basado en la ubicación  <br/> |
   
Por ejemplo: un Skype para usuarios de empresa en una llamada con otro Skype para usuarios de empresa que se están en el mismo sitio de red transfiere la llamada a un extremo PSTN y se permite la transferencia de llamada. 
  
### <a name="simultaneous-ringing"></a>Llamadas simultáneas

Cuando el receptor tiene habilitado de llamadas simultáneas, enrutamiento según ubicación analiza la ubicación de la persona que llama y los extremos de las partes llamados para determinar si se debe enrutar la llamada.
  
En la siguiente tabla se muestra un usuario con la configuración de llamadas simultáneas habilitada y el destino de llamadas simultáneas es un usuario en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido. 
  
****

|**Llamada entrante de RTC para**|**Ubicado en el mismo sitio de red que el destinatario de la llamada**|**Ubicado en el sitio de red diferente que el destinatario de la llamada**|**Ubicado en el sitio de red desconocido o no habilitado para enrutamiento según ubicación**|
|:-----|:-----|:-----|:-----|
|Skype para usuarios de empresa  <br/> |Llamadas simultáneas permitidas  <br/> |Llamadas simultáneas no permitidas  <br/> |Llamadas simultáneas no permitidas  <br/> |
   
En la tabla siguiente muestra una llamada desde un Skype para usuarios de la empresa (es decir, Skype para llamadas de negocios) en el mismo sitio de la red, en un sitio de red diferente, o desde un sitio de red desconocido. El destinatario tiene un extremo PSTN (es decir, teléfono móvil) configurado como un destino de llamada simultánea. En este escenario, el enrutamiento basado en la ubicación determinará si la llamada se debe colocar en el destino de llamadas simultáneas (es decir, teléfono móvil) del destinatario o no.
  
****

|**Destino de llamadas simultáneas**|**Ubicado en el mismo sitio de red que el destinatario de la llamada**|**Ubicado en el sitio de red diferente que el destinatario de la llamada**|**Ubicado en el sitio de red desconocido o no habilitado para enrutamiento según ubicación**|
|:-----|:-----|:-----|:-----|
|Extremo de RTC  <br/> |Llamadas simultáneas permitido a través de la directiva de enrutamiento de voz de sitio del llamador  <br/> |Llamadas simultáneas permitido a través de la directiva de enrutamiento de voz de sitio del llamador  <br/> |Llamadas simultáneas permitido a través de la directiva de voz del llamador a los troncos no habilitado para enrutamiento según ubicación  <br/> |
   
### <a name="skype-for-business-cumulative-update-4"></a>Actualización acumulativa 4 de Skype Empresarial

Con la actualización acumulativa 4, verá lo siguiente:
  
- Enrutamiento basado en ubicación seguirán activarse mediante una directiva de voz, incluyendo Skype para clientes empresariales móviles.
    
- El comportamiento llamado de Skype para clientes móviles de negocio se basará en si están habilitados para el enrutamiento basado en la ubicación y el cliente que se comunican. Está pensado para ser estático, pero, en determinados casos, se puede realizar un esfuerzo por asociar un cliente de Skype Empresarial para móviles con una puerta de enlace RTC local y permitir determinados comportamientos, como una escalación.
    
- Independientemente del sistema operativo, su cliente de Skype Empresarial para móviles debe tener la misma funcionalidad.
    
En la siguiente tabla se recorren algunos de los escenarios posteriores a la actualización acumulativa 4: 
  
|**Usuario de enrutamiento basada en ubicación**|**Otra parte**|**Acción**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype para Mobile Business recibe una llamada entrante de RTC.  <br/> |La llamada se redirige a través de Vía trabajo (CvW) en lugar de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype para móviles de negocios hace una llamada PSTN.  <br/> |La llamada se redirige a través de (CvW) en lugar de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |RTC  <br/> |Skype Empresarial para móviles está en una llamada RTC. Skype para Mobile Business escala entonces la llamada a otro usuario o contacto.  <br/> |La llamada se redirige a través de VoIP si el usuario o el contacto es local en la sección de puerta de enlace RTC.  <br/> Si el usuario o el contacto es remoto para la sección de puerta de enlace RTC, la llamada se redirige a través de CvW.  <br/> Si no es posible contactar con el usuario de destino a través de RTC, se produce un error en la llamada.  <br/> Si el contacto de destino es un operador automático de conferencia (CAA), la llamada se bloquea.  <br/> |
|Skype Empresarial para móviles  <br/> |Skype para cliente de negocios o un usuario federado  <br/> |Un Skype para Mobile Business inicia una llamada de voz a otro Skype para cliente de negocios o un usuario federado.  <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |Skype para cliente de negocios o un usuario federado  <br/> | Un Skype para cliente de negocios o un usuario federado inicia una llamada de voz a un Skype para enrutamiento de Business Mobile Location-Based de usuario. <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |Skype para cliente de negocios o un usuario federado  <br/> |Un Skype para cliente de negocios o un usuario federado está en una llamada de VoIP a un Skype para negocios Mobile user. Cualquiera de las partes se escala a un Skype adicional para el usuario de negocios o federados.  <br/> |La llamada se completa a través de VoIP.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado  <br/> |Un usuario federado está en las llamadas de voz a un Skype para enrutamiento de Business Mobile Location-Based de usuario; escala un Skype para parte de negocio Mobile a un usuario PSTN.  <br/> |La llamada se bloquea.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado  <br/> |Un usuario federado está en una llamada de VoIP a un Skype para enrutamiento de Business Mobile Location-Based de usuario; cualquiera de las partes se escala a un contacto de CAA.  <br/> |La llamada escalada se bloquea, con un mensaje de error apropiado.  <br/> |
|Skype Empresarial para móviles  <br/> |Usuario federado  <br/> |Un usuario federado está en una llamada de VoIP a un Skype para enrutamiento de Business Mobile Location-Based el usuario y el usuario federado se escala a un usuario PSTN.  <br/> |Se les permitirá o no permite el escalamiento basado en el enrutamiento basado en la ubicación del usuario federado. El Skype para la aplicación de enrutamiento Business Mobile Location-Based usuario no realiza ninguna acción.  <br/> |
   
### <a name="delegation"></a>Delegación

Enrutamiento basado en ubicación afecta a las capacidades de delegación en Skype para el negocio de la manera siguiente:
  
- Cuando un delegado habilitado para enrutamiento según ubicación lugares una llamada en nombre de un administrador, directiva de voz del delegado se utiliza para autorizar la llamada y la voz de sitio del delegado se utilizará Directiva de enrutamiento para enrutar la llamada
    
- Para las llamadas RTC entrantes a un administrador, se aplican las mismas reglas correspondientes para el reenvío de llamadas o para las llamadas simultáneas, tal como se describe en los temas Transferencias y reenvíos de llamadas y Llamadas simultáneas.
    
- Cuando un delegado establece un extremo PSTN como un destino de llamada simultánea para una llamada entrante al administrador, se utilizará la directiva de enrutamiento de voz del sitio al que está asociado al tronco entrante para enrutar la llamada al extremo PSTN del delegado.
    
- Para la delegación, se recomienda el administrador y sus delegados asociados que normalmente se encuentra en el mismo sitio de red.
    
## <a name="other-planning-considerations"></a>Otras consideraciones de planificación

Al planear el enrutamiento basado en la ubicación, debe considerar el impacto en los escenarios siguientes.
  
### <a name="disaster-recovery"></a>Recuperación ante desastres

Durante una conmutación por error del grupo principal a un conjunto de copia de seguridad, así como al restaurar las operaciones normales en el grupo principal, enrutamiento según ubicación sigue siendo obligatoria en todos veces durante un procedimiento ante desastres y recuperación.
  
### <a name="survivable-branch-appliance"></a>Aplicación de sucursal con funciones de supervivencia

Enrutamiento basado en la ubicación de configuración afecta a la planificación de donde implementar las puertas de enlace asociados a los dispositivos de la rama que sobreviven. La puerta de enlace asociada a la SBA debe estar ubicado en el mismo sitio de red que el dispositivo de la rama que sobreviven; de lo contrario, los usuarios alojados en el dispositivo de la rama que sobreviven no podrá realizar llamadas salientes si se configura Enrutamiento basado en la ubicación. Cuando la conexión entre el dispositivo de la rama que sobreviven y el sitio central WAN está inactivo, restricciones de enrutamiento basado en la ubicación sigue siendo obligatoria.
  
## <a name="client-and-server-support-for-location-based-routing"></a>Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación

Enrutamiento basado en ubicación se aplica por Skype para Business Server. Skype para Business Server puede identificar los sitios de la red donde los usuarios se conectan desde dentro de la red corporativa. Dado que los usuarios remotos están fuera de la red corporativa, su ubicación se considera como desconocida.
  
### <a name="server-support"></a>Compatibilidad con servidores

Enrutamiento basado en ubicación requiere que Skype para Business Server o Lync Server 2013 CU1 se implementa en todos los grupos de Front-End y los servidores Standard Edition en una topología dada. Si estas versiones del servidor no están instaladas, no pueden aplicar restricciones de enrutamiento basado en ubicación completamente.
  
La siguiente tabla identifica la combinación de funciones de servidor y las versiones que se admite para el enrutamiento basado en la ubicación.
  
****

|**Versión de grupo**|**Versión de servidor de mediación**|**Compatible**|
|:-----|:-----|:-----|
|Skype para actualización acumulativa Business Server o Lync Server 2013 febrero de 2013  <br/> |Skype para actualización acumulativa Business Server o Lync Server 2013 febrero de 2013  <br/> |sí  <br/> |
|Skype para actualización acumulativa Business Server o Lync Server 2013 febrero de 2013  <br/> |Lync Server 2013  <br/> |no  <br/> |
|Skype para actualización acumulativa Business Server o Lync Server 2013 febrero de 2013  <br/> |Lync Server 2010  <br/> |no  <br/> |
|Skype para actualización acumulativa Business Server o Lync Server 2013 febrero de 2013  <br/> |Office Communications Server 2007 R2  <br/> |no  <br/> |
|Lync Server 2013  <br/> |cualquiera  <br/> |no  <br/> |
|Lync Server 2010  <br/> |cualquiera  <br/> |no  <br/> |
|Office Communications Server 2007 R2  <br/> |cualquiera  <br/> |no  <br/> |
   
### <a name="client-support"></a>Compatibilidad con clientes

La tabla siguiente identifica a los clientes que admite enrutamiento basado en la ubicación.
  
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
|Lync Mobile 2013  <br/> |no  <br/> |VoIP debe deshabilitarse para los clientes de Lync Mobile 2013 si utilizados por usuarios con enrutamiento según ubicación habilitada.  <br/> |
|Lync Mobile 2010  <br/> |sí  <br/> ||
   
> [!NOTE]
> Para deshabilitar VoIP para Skype para clientes empresariales, asigne una directiva de movilidad con la configuración IP de Audio o vídeo, deshabilitada para todos los usuarios habilitados para enrutamiento basado en la ubicación. Para obtener más detalles acerca de la directiva de movilidad, consulte [CsMobilityPolicy de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps). 
  
## <a name="capabilities-not-supported-by-location-based-routing"></a>Capacidades no compatibles con el enrutamiento basado en ubicación

Enrutamiento basado en la ubicación no se aplica a los siguientes tipos de interacciones. Enrutamiento basado en la ubicación no se aplica cuando Skype para extremos de negocio interactúan con extremos PSTN con estas capacidades.
  
- Marcación RTC para conferencias
    
- Llamadas RTC entrantes y salientes a través del grupo de respuesta
    
- Estacionamiento o recuperación de llamadas RTC a través del estacionamiento de llamadas
    
- Llamadas RTC entrantes al servicio de anuncio
    
- Llamadas RTC entrantes recuperadas a través de la atención de llamadas de grupo
    
Para exigir las reglas de enrutamiento basado en la ubicación a los tipos de interacciones en la siguiente lista, debe habilitar el enrutamiento basado en la ubicación para las conferencias:
  
- Iniciar llamadas RTC desde una conferencia
    
- Escalaciones desde conversaciones de audio de punto a punto a conferencias en las que participen extremos de RTC 
    
- Transferencias de consulta con extremos de RTC
    
Para habilitar el enrutamiento basado en ubicación para conferencias, consulte [enrutamiento basado en ubicación para las conferencias](http://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).
  


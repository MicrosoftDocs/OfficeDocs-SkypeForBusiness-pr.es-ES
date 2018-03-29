---
title: Conexiones SIP directas en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Se admiten conexiones SIP directas entre Skype para Business Server y las puertas de enlace PSTN y IP-PBX en Telefonía IP empresarial.
ms.openlocfilehash: 36b549b20708f0f9b09b8aeadf6f4197b9de1371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="direct-sip-connections-in-skype-for-business-server-2015"></a>Conexiones SIP directas en Skype Empresarial Server 2015
 
Se admiten conexiones SIP directas entre Skype para Business Server y las puertas de enlace PSTN y IP-PBX en Telefonía IP empresarial.
  
Puede utilizar conexiones SIP directas para conectar Skype para Business Server a alguno de los siguientes:
  
- Un IP-PBX 
    
- Una puerta de enlace PSTN
    
Para implementar una conexión directa de SIP, siga esencialmente los mismos pasos de implementación que para implementar un troncal SIP. En ambos casos, se implementa la conexión mediante la interfaz externa de un servidor de mediación. La única diferencia es que se conectan los troncos SIP a una entidad externa, como una puerta de enlace ITSP y conectar conexiones SIP directas a una entidad interna dentro de su red local, como una PBX IP o una puerta de enlace de telefonía pública conmutada (PSTN) de la red.
  
## <a name="direct-sip-deployment-options"></a>Opciones de implementación SIP directa

### <a name="skype-for-business-server-stand-alone"></a>Skype para Business Server independiente
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Si su organización utiliza una de las implementaciones descritas en esta sección, puede utilizar Skype para Business Server como la solución de telefonía único para todo o parte de una organización. Esta sección describe las siguientes implementaciones en detalle:
  
- **Implementación incremental:** Esta opción supone que dispone de una infraestructura private branch exchange (PBX) y desea introducir la Telefonía IP empresarial gradualmente a grupos más pequeños o equipos dentro de su organización.
    
- **Implementación sólo VoIP:** esta opción se supone que están considerando la implementación de Telefonía IP empresarial en un sitio que no tiene una infraestructura de telefonía tradicional.
    
#### <a name="incremental-deployment"></a>Implementación incremental

En una implementación incremental, Skype para Business Server es la solución de telefonía exclusiva para equipos individuales o seguirán utilizando un PBX departamentos, mientras que el resto de los usuarios de una organización. Esta estrategia de implementación incremental proporciona una forma de introducir la telefonía IP en su empresa a través de programas piloto controlados. Grupos de trabajo cuya comunicación necesidades se sirve mejor en comunicaciones unificadas de Microsoft se mueven a la Telefonía IP empresarial, mientras otros usuarios permanecen en el PBX existente. Grupos de trabajo adicionales se pueden migrar a la Telefonía IP empresarial, según sea necesario.
  
Se recomienda la opción incremental si se han definido claramente que haya requisitos de comunicación en común y que se prestan a la administración centralizada de grupos de usuarios. Esta opción también es eficaz si tiene equipos o departamentos que se extienden sobre áreas área geográficas extensa, donde los ahorros en gastos de larga distancia pueden ser significativa. De hecho, esta opción es útil para crear equipos virtuales cuyos miembros pueden estar dispersos por todo el mundo. Puede crear, modificar o disolver estos equipos en una respuesta rápida a las cambiantes exigencias del negocio.
  
La siguiente figura muestra la topología genérica para la implementación de Telefonía IP empresarial detrás de una PBX. Se trata de la topología recomendada para la implementación incremental.
  
**Opción de implementación incremental**

![Diagrama de opción de migración departamental](../../media/Fig28_Departmental_migration_option.jpg)
  
> [!NOTE]
> Si está conectando su Skype para la implementación de Business Server a un asociado certificado de SIP directo, no se requiere una puerta de enlace de telefónica pública conmutada (PSTN) de la red entre el servidor de mediación y la PBX. Para obtener una lista de asociados de negocios certificados SIP directo, consulte el [Microsoft Unified Communications interoperabilidad programa abierto](https://go.microsoft.com/fwlink/p/?linkId=203309). 
  
> [!NOTE]
> La ruta de acceso de medios que se muestra en esta figura tiene habilitada la omisión de la media (configuración recomendada). Si decide para desactivar la omisión de medios, la ruta de acceso de medios se enruta a través del servidor de mediación. 
  
En esta topología, seleccionados departamentos o grupos de trabajo están habilitados para Telefonía IP empresarial. Una puerta de enlace PSTN vincula la voz sobre Protocolo Internet (VoIP)-habilitado el grupo de trabajo a la PBX. Los usuarios que están habilitados para Telefonía IP empresarial, incluidos los trabajadores remotos, comunican a través de la red IP. Llamadas a los usuarios de Telefonía IP empresarial a la RTC y compañeros de trabajo que no están habilitados para Telefonía IP empresarial se enrutan a la puerta de enlace PSTN apropiado. Llamadas de los compañeros que todavía están en el sistema PBX o de los llamadores de la RTC, se enrutan a la puerta de enlace PSTN, que reenvía las llamadas a Skype para Business Server para el enrutamiento.
  
Existen dos configuraciones recomendadas para la conexión de Telefonía IP empresarial a una infraestructura PBX existente para la interoperabilidad: Telefonía IP empresarial detrás de la PBX y Telefonía IP empresarial frente a la PBX.
  
#### <a name="enterprise-voice-behind-the-pbx"></a>Telefonía IP empresarial detrás de la PBX

Cuando se implementa la Telefonía IP empresarial detrás de la PBX, todas las llamadas desde la PSTN llegan a la PBX, que enruta las llamadas a los usuarios de Telefonía IP empresarial a una puerta de enlace PSTN y llama a los usuarios de PBX a la PBX. 
  
#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Telefonía IP empresarial frente a la PBX

Cuando se implementa la Telefonía IP empresarial frente a la PBX, todas las llamadas de llegan a la puerta de enlace PSTN, qué rutas se llama para que los usuarios de Telefonía IP empresarial Skype para Business Server y las llamadas a los usuarios de PBX a la PBX. Llamadas a la RTC de usuarios de Telefonía IP empresarial y PBX se enrutan a través de la red IP a la puerta de enlace PSTN más rentable. En la tabla siguiente muestra las ventajas y desventajas de esta configuración.
  
**Ventajas y desventajas de la implementación de Telefonía IP empresarial frente a PBX**

|**Ventajas**|**Desventajas**|
|:-----|:-----|
|PBX sirve aún no está habilitados para la Telefonía IP empresarial de los usuarios.  <br/> |Puertas de enlace existentes pueden que no admita las características o la capacidad que desee.  <br/> |
|PBX controla todos los dispositivos anteriores.  <br/> |Requiere un tronco de puerta de enlace a la PBX y de la puerta de enlace para el servidor de mediación. Puede que necesite más troncos del proveedor de servicios.  <br/> |
|Los usuarios de Telefonía IP empresarial mantener los mismos números de teléfono.  <br/> | <br/> |
   
#### <a name="voip-only-deployment"></a>Implementación sólo VoIP

Telefonía IP empresarial proporciona nuevas empresas y también nuevos sitios de office para las empresas existentes, con la oportunidad de implementar una solución de VoIP completa sin tener que preocuparse acerca de la integración de PBX o incurrir en la implementación sustancial y mantenimiento costos de una infraestructura de IP-PBX. Esta solución soporta los trabajadores remotos y a domicilio.
  
En esta implementación, todas las llamadas se enrutan a través de la red IP. Llamadas a la RTC se enrutan a la puerta de enlace PSTN apropiado. Skype para negocios o Lync Phone Edition actúa como un softphone. Control remoto de llamada es innecesario y no disponible porque no hay ningún teléfono PBX para que los usuarios de control. Correo de voz y servicios de operador automático están disponibles a través de la implementación opcional de Exchange Unified Messaging (UM).
  
> [!NOTE]
> Además de la infraestructura de red necesaria para soportar Skype para Business Server, una implementación de VoIP puede utilizar una puerta de enlace pequeño y completo para admitir dispositivos analógicos y máquinas de fax. 
  
La figura siguiente muestra una topología típica para una implementación de VoIP.
  
**Opción de implementación sólo VoIP**

![Opción de implementación en entorno virgen](../../media/Fig29_Greenfield_deployment_option.jpg)
  
> [!NOTE]
> La ruta de acceso de medios que se muestra en esta figura tiene habilitada la omisión de la media (configuración recomendada). Si decide para desactivar la omisión de medios, la ruta de acceso de medios se enruta a través del servidor de mediación. 
  
## <a name="pstn-gateway-deployment-options"></a>Opciones de implementación de la puerta de enlace PSTN

### <a name="pstn-gateways"></a>Puertas de enlace PSTN

Puertas de enlace de telefónica pública conmutada (PSTN) de la red son componentes de hardware de terceros que traducen la señalización y los medios de comunicación entre la infraestructura de Telefonía IP empresarial y PSTN, directamente o a través de la conexión a los troncos SIP. En cualquier topología, la puerta de enlace termina la RTC. La puerta de enlace está aislado en su propia subred y está conectado a la red de la empresa a través del servidor de mediación.
  
Una empresa con múltiples sitios normalmente sería implementar una o más puertas de enlace en cada sitio. Sitios de sucursales pueden conectarse a la red PSTN a través de una puerta de enlace, o un dispositivo de sucursal que sobreviven, que combina la puerta de enlace y servidores en una sola caja. Si los sitios de sucursal utilizan una puerta de enlace, un registrador y el servidor de mediación son necesarios en el sitio, a menos que el vínculo WAN es resistente. Uno o más servidores de mediación, que están ubicados en servidores frontales, puede enrutar llamadas para las puertas de enlace de uno o más en cada sitio. Se recomienda que el registrador, servidor de mediación y puerta de enlace requerida en el sitio se implementan como un dispositivo de la rama que sobreviven.
  
Determinar el número, tamaño y ubicación de puertas de enlace PSTN es quizás la decisión más importante y costosa que debe tomar al planear la infraestructura de Telefonía IP empresarial. 
  
Aquí están las principales cuestiones a tener en cuenta. Tenga en cuenta que las respuestas a estas preguntas son interdependientes en todo
  
- ¿Puertas de enlace PSTN cuántos son necesarios? La respuesta depende del número de usuarios, el número previsto de llamadas simultáneas (carga de tráfico) y el número de sitios (cada sitio necesita uno).
    
- ¿Qué tamaño deben ser las puertas de enlace? La respuesta depende del número de usuarios en el sitio y de la carga de tráfico.
    
- ¿Donde las puertas de enlace se deben ubicados? La respuesta depende en parte de la topología y en parte en la distribución geográfica de su organización.
    
 Debe considerar también la puerta de enlace opciones de topología (para obtener más información, consulte topologías de puerta de enlace más adelante en este tema).
  
#### <a name="mn-trunk-support"></a>Compatibilidad con troncos M:N

Los servidores de mediación puede enrutar llamadas a través de varias puertas de enlace, controladores de borde de sesión (SBCs) proporcionadas por proveedores de servicios de telefonía de Internet o una combinación de los dos. Además, varios servidores de mediación en el grupo puede interactuar con varias puertas de enlace. La ruta lógica definida entre un servidor de mediación y la puerta de enlace se denomina un tronco. Cuando un usuario interno realiza una llamada PSTN, lógica de enrutamiento de salida en el grupo de servidores Front-End elige que el tronco para enrutar a través de todas las combinaciones posibles que pueden estar disponibles para el enrutamiento a esa llamada concreta. Con equilibrio de carga DNS, si se produce un error en una llamada llegar a una puerta de enlace debido a un problema con un determinado servidor de mediación en el fondo, la llamada se volverá a un servidor de mediación alternativo en la agrupación. 
  
Para obtener más información acerca de cómo planear varias puertas de enlace, vea [m: n tronco en Skype para Business Server 2015](m-n-trunk.md).
  
Para obtener más información acerca de otras mejoras de enrutamiento de salida, vea [Llamar a rutas](http://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).
  
#### <a name="gateway-topologies"></a>Topologías de puerta de enlace

Al considerar las cuestiones fundamentales de la implementación de la puerta de enlace, siga estos pasos:
  
1. Contar los sitios en los que desea proporcionar conectividad PSTN mediante el uso de la Telefonía IP empresarial.
    
2. Estimar el tráfico en cada sitio (número de usuarios) y el promedio de llamadas por hora y por usuario.
    
3. Implementar una o más puertas de enlace en cada sitio para controlar el tráfico previsto.
    
Con esta topología, las llamadas entre los trabajadores en cada sitio y entre sitios se enrutan a través de la intranet. Llamadas a la RTC se enrutan a través de la red IP de empresa a las puertas de enlace que están cerca de la ubicación de los números de destino. Pero, ¿qué sucede si la organización admite decenas o cientos o incluso miles de sitios reparten en uno o varios continentes, como hacen muchas instituciones financieras y otras grandes empresas? En tales casos, no es práctico implementar una puerta de enlace independiente en cada sitio.
  
Para solucionar este problema, muchas grandes empresas prefieren implementar uno o varios sitios centrales de telefonía de gran tamaño.
  
En esta topología, varias puertas grandes suficientes para acomodar la carga anticipada de usuario se implementan en cada sitio central. Proveedor de servicios de teléfono de la empresa en un sitio central reenvía todas las llamadas a los usuarios de la empresa. Lógica de enrutamiento en el sitio central determina si se debe enrutar la llamada a través de la intranet o a la RTC.
  
#### <a name="gateway-location"></a>Ubicación de puerta de enlace

Ubicación de puerta de enlace también puede determinar los tipos de puertas de enlace que elija y cómo están configurados. Hay docenas de protocolos PSTN, ninguno de los cuales es un estándar en todo el mundo. Si las puertas de enlace se encuentran en un único país o región, no es un problema, pero si encuentra las puertas de enlace en varios países o regiones, cada una debe configurarse según los estándares de RTC de ese país o región. Por otra parte, las puertas de enlace que están certificados para su operación, por ejemplo, Canadá, no puede certificarse en India, Brasil o la Unión Europea.
  
#### <a name="gateway-size-and-number"></a>Número y tamaño de puerta de enlace

Las puertas de enlace PSTN que tendrá en cuenta la mayoría de las organizaciones implementar intervalo de tamaño de 2 a los puertos como máximo 960. (Hay puertas de enlace aún mayores, pero se utilizan principalmente por proveedores de servicio telefónico). Al estimar el número de puertos que necesita su organización, utilice las siguientes directrices:
  
- Las organizaciones con el uso de telefonía claro (una llamada PSTN por usuario y hora) deben asignar un puerto para cada 15 usuarios. Por ejemplo, si tiene 20 usuarios, necesitará una puerta de enlace con dos puertos.
    
- Las organizaciones con el uso de telefonía moderada (dos llamadas PSTN por usuario y hora) deben asignar un puerto para cada 10 usuarios. Por ejemplo, si tiene 100 usuarios, se requerirá un total de 10 puertos asignados entre una o varias puertas de enlace.
    
- Las organizaciones con el uso de telefonía pesado (tres o más llamadas PSTN por usuario y hora) deben asignar un puerto para cada cinco usuarios. Por ejemplo, si tiene 47.000 usuarios, requerirá un total de 9.400 puertos asignados entre puertas de enlace de gran tamaño al menos 10.
    
- Puertos adicionales pueden ser adquiridos como el número de usuarios o la cantidad de tráfico en los aumentos de la organización.
    
Para cualquier número dado de usuarios que debe admitir, tiene la opción de implementar puertas de enlace de menos, más grandes o más pequeñas. Como regla general, se recomienda un mínimo de dos puertas de enlace de una organización para mantener la disponibilidad si se produce un error en una puerta de enlace. 
  
Cada puerta de enlace PSTN que implemente debe tener al menos un servidor de mediación correspondiente.
  


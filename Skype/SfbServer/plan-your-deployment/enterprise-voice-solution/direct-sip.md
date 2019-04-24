---
title: Conexiones SIP directas en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Se admiten conexiones SIP directas entre Skype para Business Server y las puertas de enlace RTC y IP-PBX en Enterprise Voice.
ms.openlocfilehash: 1ddcf66fb19f39661ffdd4cffdff754999db90d3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207457"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Conexiones SIP directas en Skype para Business Server

Se admiten conexiones SIP directas entre Skype para Business Server y las puertas de enlace RTC y IP-PBX en Enterprise Voice.

Puede usar conexiones SIP directas para conectar Skype para Business Server a cualquiera de las siguientes opciones:

- Un sistema IP-PBX

- Una puerta de enlace de RTC

Para implementar una conexión directa de SIP, siga esencialmente los mismos pasos de implementación tal y como lo haría para implementar un tronco SIP. En ambos casos, se implementa la conexión mediante el uso de la interfaz externa de un servidor de mediación. La única diferencia es que se conectan troncos SIP a una entidad externa, como una puerta de enlace de protocolo, y conectar conexiones SIP directas a una entidad interna dentro de su red local, como un sistema IP-PBX o una puerta de enlace de telefónica conmutada (RTC).

## <a name="direct-sip-deployment-options"></a>Opciones de implementación SIP directa

### <a name="skype-for-business-server-stand-alone"></a>Skype para Business Server independiente
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Si su organización utiliza una de las implementaciones descritas en esta sección, puede usar Skype para Business Server como la única solución de telefonía para parte o la totalidad de una organización. En esta sección se describe las siguientes implementaciones en detalle:

- **Implementación incremental:** Esta opción se da por supuesto que dispone de una infraestructura central de conmutación (PBX) de exchange y que piensa introducir Enterprise Voice de forma incremental a grupos más pequeños o equipos dentro de su organización.

- **Implementación de solo VoIP:** esta opción, se da por supuesto que se está planteando la implementación de Enterprise Voice en un sitio que no tiene una infraestructura de telefonía tradicional.

#### <a name="incremental-deployment"></a>Implementación incremental

En una implementación incremental, Skype para Business Server es la única solución de telefonía para equipos individuales o departamentos, mientras que el resto de los usuarios de una organización seguirán usando un sistema PBX. Esta estrategia de implementación incremental proporciona una manera de introducir la telefonía IP en la empresa a través de programas piloto controlados. Grupos de trabajo cuya comunicación necesidades se satisfacen mejor con comunicaciones unificadas de Microsoft se mueven a Enterprise Voice, mientras que los demás usuarios permanecen en el sistema PBX existente. Grupos de trabajo adicional se pueden migrar a Enterprise Voice, según sea necesario.

Si se han definido claramente a grupos de usuarios que han requisitos de comunicación en común y que se prestan a la administración centralizada, se recomienda la opción incremental. Esta opción también es eficaz si tiene equipos o departamentos que están dispersos por amplias áreas geográficas, donde el ahorro en los gastos de llamadas de larga distancia puede ser significativo. De hecho, esta opción es útil para crear equipos virtuales cuyos miembros pueden estar dispersos por todo el mundo. Puede crear, modificar o disolver estos equipos en una respuesta rápida a los requisitos empresariales.

En la siguiente figura se muestra la topología genérica para la implementación de Enterprise Voice detrás de un sistema PBX. Esto es la topología recomendada para la implementación incremental.

**Opción de implementación incremental**

![Diagrama de opción de migración departamental](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Si va a conectar su Skype para la implementación de Business Server a un asociado certificado de SIP directo, no es necesario una puerta de enlace de telefónica conmutada (RTC) de red entre el servidor de mediación y el sistema PBX. Para obtener una lista de socios certificados SIP directo, consulte el [Microsoft Unified Communications Open Interoperability Program](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> La ruta de acceso de medios que se muestra en esta ilustración tiene habilitado el desvío de medios (la configuración recomendada). Si decide para deshabilitar el desvío de medios, la ruta de acceso de medios se enruta a través del servidor de mediación.

En esta topología, determinados departamentos o grupos de trabajo están habilitados para Enterprise Voice. Una puerta de enlace RTC vincula el de voz a través del protocolo de Internet (VoIP)-habilitado para el grupo de trabajo al sistema PBX. Los usuarios habilitados para Enterprise Voice, incluidos los usuarios remotos, comunican a través de la red IP. Las llamadas por usuarios de Enterprise Voice a la RTC y a los compañeros de trabajo que no están habilitados para Enterprise Voice se enrutan a la puerta de enlace de RTC adecuada. Las llamadas de compañeros que están todavía en el sistema PBX o de autores de llamadas en la RTC se enrutan a la puerta de enlace RTC, que reenvía las llamadas a Skype para Business Server para el enrutamiento.

Existen dos configuraciones recomendadas para conectar Enterprise Voice con una infraestructura PBX existente para la interoperabilidad: Enterprise Voice detrás del sistema PBX y Enterprise Voice delante del sistema PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice detrás del PBX

Cuando se implementa Enterprise Voice detrás del PBX, todas las llamadas desde la RTC llegan a la PBX, que enruta las llamadas a los usuarios de Enterprise Voice a una puerta de enlace RTC y llama a los usuarios de PBX al sistema PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice delante del sistema PBX

Cuando se implementa Enterprise Voice delante del sistema PBX, todas las llamadas llegan a la puerta de enlace RTC, que enruta las llamadas para que los usuarios de Enterprise Voice Skype para Business Server y las llamadas para usuarios de PBX al sistema PBX. Las llamadas a la RTC procedentes de usuarios de Enterprise Voice y PBX se enrutan a través de la red IP a la puerta de enlace de RTC más rentable. La siguiente tabla muestran las ventajas y desventajas de esta configuración.

**Ventajas y desventajas de la implementación de Enterprise Voice delante de PBX**

|**Ventajas**|**Desventajas**|
|:-----|:-----|
|PBX sigue dando servicio a los usuarios no habilitados para Enterprise Voice.  <br/> |Puertas de enlace existentes no es posible que admitan las características o la capacidad que desee.  <br/> |
|PBX administra todos los dispositivos anteriores.  <br/> |Requiere un tronco de puerta de enlace al sistema PBX y de la puerta de enlace para el servidor de mediación. Es posible que deba más troncos del proveedor de servicios.  <br/> |
|Los usuarios de Enterprise Voice mantienen los mismos números de teléfono.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>Implementación de solo VoIP

Enterprise Voice proporciona nuevas empresas y también nuevos sitios de office para las empresas existentes, con la oportunidad de implementar una solución de VoIP completas sin tener que preocuparse acerca de la integración de PBX o incurrir en la implementación sustancial y el mantenimiento costos de una infraestructura de IP-PBX. Esta solución admite los trabajadores locales y remotos.

En esta implementación, todas las llamadas se enrutan a través de la red IP. Las llamadas a la RTC se enrutan a la puerta de enlace de RTC adecuada. Skype para empresariales o de Lync Phone Edition actúa como un softphone. Control remoto de llamadas es innecesarios y no está disponible porque no hay ningún teléfonos PBX para que los usuarios de control. Correo de voz y servicios de operador automático están disponibles a través de la implementación opcional de Exchange mensajería unificada (UM).

> [!NOTE]
> Además de la infraestructura de red que se requiere para admitir Skype para Business Server, una implementación de solo VoIP puede usar una puerta de enlace pequeña y cualificada para admitir dispositivos analógicos y equipos de fax.

La siguiente ilustración muestra una topología típica para una implementación de VoIP.

**Opción de implementación de solo VoIP**

![Opción de implementación en entorno virgen](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> La ruta de acceso de medios que se muestra en esta ilustración tiene habilitado el desvío de medios (la configuración recomendada). Si decide para deshabilitar el desvío de medios, la ruta de acceso de medios se enruta a través del servidor de mediación.

## <a name="pstn-gateway-deployment-options"></a>Opciones de implementación de puerta de enlace RTC

### <a name="pstn-gateways"></a>Puertas de enlace RTC

Puertas de enlace de telefónica conmutada (RTC) son componentes de hardware de otro fabricante que convierten la señalización y los medios entre la infraestructura de Enterprise Voice y la RTC, ya sea directamente o a través de la conexión de troncos SIP. En cualquier topología, la puerta de enlace finaliza la RTC. La puerta de enlace se aísla en su propia subred y está conectado a la red de la empresa a través del servidor de mediación.

Una empresa con varios sitios normalmente sería implementar uno o más puertas de enlace en cada sitio. Sitios de sucursal pueden conectarse a la RTC a través de una puerta de enlace, o a través de una aplicación de sucursal con funciones de supervivencia, que combina la puerta de enlace y los servidores en un solo cuadro. Si los sitios de sucursal utilizan una puerta de enlace, un registrador y el servidor de mediación se requieren en el sitio, a menos que el vínculo WAN es resistente. Uno o varios servidores de mediación, que se instalan en servidores Front-End, puede enrutar las llamadas para las puertas de enlace de uno o más en cada sitio. Se recomienda que el registrador, el servidor de mediación y la puerta de enlace requerido en el sitio se implementan como una aplicación de sucursal con funciones de supervivencia.

Determinar el número, el tamaño y la ubicación de las puertas de enlace RTC es, posiblemente, la decisión más importante y costosa que debe tomar al planear la infraestructura de Enterprise Voice.

Aquí están las principales cuestiones a tener en cuenta. Tenga en cuenta que las respuestas a estas preguntas dependen todo

- ¿Cuántas puertas de enlace RTC se necesitan? La respuesta depende del número de usuarios, el número previsto de llamadas simultáneas (carga de tráfico) y el número de sitios (cada sitio necesita uno).

- ¿Qué tamaño deben tener las puertas de enlace? La respuesta depende del número de usuarios en el sitio y de la carga de tráfico.

- ¿Dónde deben colocarse las puertas de enlace? La respuesta depende en parte de la topología y en parte de la distribución geográfica de su organización.

  También debería considerar la puerta de enlace opciones de topología (para obtener información detallada, vea topologías de puerta de enlace más adelante en este tema).

#### <a name="mn-trunk-support"></a>Compatibilidad con troncos M:N

Los servidores de mediación puede enrutar las llamadas a través de varias puertas de enlace, controladores de borde de sesión (SBCs) proporcionadas por proveedores de servicios de telefonía de Internet, o una combinación de ambas. Además, varios servidores de mediación en el grupo de servidores puede interactuar con varias puertas de enlace. La ruta lógica definida entre un servidor de mediación y la puerta de enlace se denomina un tronco. Cuando un usuario interno realiza una llamada de RTC, la lógica de enrutamiento saliente en el grupo de servidores Front-End elige qué tronco a enrutar a través de fuera de todas las combinaciones posibles que pueden estar disponibles para el enrutamiento de esa llamada concreta. Con equilibrio de carga DNS, si se produce un error en una llamada llegar a una puerta de enlace debido a un problema con un determinado servidor de mediación del grupo de servidores, la llamada se volverá a un servidor de mediación alternativo en el grupo de servidores.

Para obtener información detallada sobre la planeación de varias puertas de enlace, vea [tronco m: n en Skype para Business Server](m-n-trunk.md).

Para obtener más información sobre otras mejoras de enrutamiento saliente, consulte [Rutas de llamadas](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Topologías de puerta de enlace

Cuando tenga en cuenta las preguntas fundamentales de implementación de la puerta de enlace, siga estos pasos:

1. Recuento de los sitios a la que desea proporcionar conectividad RTC mediante el uso de Enterprise Voice.

2. Estimar el tráfico en cada sitio (número de usuarios) y el número promedio de llamadas por hora y por usuario.

3. Implementar una o más puertas de enlace en cada sitio para administrar el tráfico previsto.

Con esta topología, las llamadas entre los trabajadores en cada sitio y entre sitios se enrutan a través de la intranet. Las llamadas a la RTC se enrutan a través de la red IP de empresa a las puertas de enlace que son más cercano a la ubicación de los números de destino. Pero ¿qué ocurre si la organización admite docenas o cientos o incluso miles de sitios distribuidos en uno o varios continentes, como hacen muchas entidades financieras y otras empresas grandes? En estos casos, no es práctico implementar una puerta de enlace independiente en cada sitio.

Para solucionar este problema, muchas compañías grandes prefieren implementar uno o varios sitios centrales de telefonía de gran tamaño.

En esta topología, se implementan varias puertas de enlace grandes suficientes para dar cabida a la carga de usuarios prevista en cada sitio central. Todas las llamadas a los usuarios de la empresa se transfieren por el proveedor de servicios de teléfono de la compañía a un sitio central. Lógica de enrutamiento en el sitio central determina si se debe enrutar la llamada a través de la intranet o a la RTC.

#### <a name="gateway-location"></a>Ubicación de la puerta de enlace

Ubicación de la puerta de enlace también puede determinar los tipos de puertas de enlace que elija y cómo están configurados. Hay docenas de protocolos RTC, ninguno de los cuales es un estándar mundial. Si todas las puertas de enlace se encuentran en un único país o región, este no es un problema, pero si encuentra las puertas de enlace en varios países o regiones, cada uno de ellos debe configurarse según los estándares de RTC de ese país o región. Además, las puertas de enlace certificadas para la operación en, por ejemplo, Canadá, pueden no estar certificadas en India, Brasil o la Unión Europea.

#### <a name="gateway-size-and-number"></a>Número y tamaño de la puerta de enlace

Las puertas de enlace RTC que la mayoría de las organizaciones consideren la implementación de intervalo de tamaño de 2 a los puertos de 960 como máximo. (Hay puertas de enlace incluso más grandes, pero las usan principalmente por proveedores de servicio de teléfono). La hora de valorar el número de puertos que necesita su organización, use las siguientes instrucciones:

- Las organizaciones con un uso de telefonía claro (una llamada de RTC por usuario por hora) deben asignar un puerto por cada 15 usuarios. Por ejemplo, si tiene 20 usuarios, se necesitará una puerta de enlace con dos puertos.

- Las organizaciones con un uso de telefonía moderadas (dos llamadas de RTC por usuario por hora) deben asignar un puerto por cada 10 usuarios. Por ejemplo, si tiene 100 usuarios, se necesitará un total de 10 puertos repartidos entre una o más puertas de enlace.

- Las organizaciones con un uso de telefonía intensa (tres o más llamadas de RTC por usuario por hora) deben asignar un puerto por cada cinco usuarios. Por ejemplo, si hay 47.000 usuarios, necesitará un total de 9.400 puertos repartidos entre al menos 10 puertas de enlace grandes.

- Como el número de usuarios o la cantidad de tráfico en su organización aumenta, se pueden adquirir puertos adicionales.

Para cualquier número determinado de usuarios que debe admitir, tiene la opción de implementar puertas de enlace menos, más grandes o pequeños. Como regla general, se recomienda un mínimo de dos puertas de enlace para una organización para mantener la disponibilidad si se produce un error en una puerta de enlace.

Cada puerta de enlace de RTC que implemente debe tener al menos un servidor de mediación correspondiente.



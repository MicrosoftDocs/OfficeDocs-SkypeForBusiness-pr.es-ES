---
title: Conexiones SIP directas en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Las conexiones SIP directas se admiten Skype Empresarial Server puertas de enlace RTC y IP-PBX en Telefonía IP empresarial.
ms.openlocfilehash: 1a3a2354074819f40780896897a8e9a2790a9421
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726269"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Conexiones SIP directas en Skype Empresarial Server

Las conexiones SIP directas se admiten Skype Empresarial Server puertas de enlace RTC y IP-PBX en Telefonía IP empresarial.

Puede usar conexiones SIP directas para conectar Skype Empresarial Server a cualquiera de las siguientes opciones:

- Un sistema IP-PBX

- Una puerta de enlace RTC

Para implementar una conexión SIP directa, deberá seguir básicamente los mismos pasos de implementación que seguiría para implementar un tronco SIP. En ambos casos, se implementa la conexión mediante la interfaz externa de un servidor de mediación. La única diferencia es que los troncos SIP se conectan a una entidad externa, como, por ejemplo, una puerta de enlace del proveedor de servicios de telefonía por Internet (ITSP), mientras que las conexiones SIP se conectan a una entidad interna de la red local, como, por ejemplo, una puerta de enlace de red telefónica conmutada (RTC) o un sistema IP-PBX.

## <a name="direct-sip-deployment-options"></a>Opciones de implementación SIP directa

### <a name="skype-for-business-server-stand-alone"></a>Skype Empresarial Server Stand-Alone
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Si su organización usa una de las implementaciones descritas en esta sección, puede usar Skype Empresarial Server como única solución de telefonía para una parte o para toda una organización. En esta sección se describen detalladamente las siguientes implementaciones:

- **Implementación incremental:** Esta opción supone que tiene una infraestructura de central de conmutación (PBX) privada existente y que tiene la intención de introducir Telefonía IP empresarial grupos o equipos más pequeños dentro de su organización.

- **Implementación de solo VoIP:** esta opción supone que está considerando implementar Telefonía IP empresarial en un sitio que no tiene una infraestructura de telefonía tradicional.

#### <a name="incremental-deployment"></a>Implementación incremental

En la implementación incremental, Skype Empresarial Server es la única solución de telefonía para equipos o departamentos individuales, mientras que el resto de los usuarios de una organización siguen usando una PBX. Esta estrategia de implementación incremental proporciona una forma de introducir la telefonía IP en su empresa a través de programas piloto controlados. Los grupos de trabajo cuyas necesidades de comunicación mejor se atendidas por las comunicaciones unificadas de Microsoft se mueven a Telefonía IP empresarial, mientras que otros usuarios permanecen en la PBX existente. Los grupos de trabajo adicionales se pueden migrar a Telefonía IP empresarial, según sea necesario.

La opción incremental se recomienda si tiene grupos de usuarios claramente definidos que tienen requisitos de comunicación en común y que se prestan a la administración centralizada. Esta opción también es eficaz si tiene equipos o departamentos que se extienden por amplias áreas geográficas, donde el ahorro en cargos de larga distancia puede ser significativo. De hecho, esta opción es útil para crear equipos virtuales cuyos miembros pueden estar dispersos por todo el mundo. Puede crear, modificar o disolver dichos equipos en respuesta rápida a los requisitos empresariales de cambio.

En la siguiente figura se muestra la topología genérica para la implementación de Telefonía IP empresarial detrás de una PBX. Esta es la topología recomendada para la implementación incremental.

**Opción de implementación incremental**

![Diagrama de opciones de migración departamental.](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Si va a conectar la implementación de Skype Empresarial Server a un partner SIP directo certificado, no es necesaria una puerta de enlace de red telefónica conmutada (RTC) entre el servidor de mediación y la PBX. Para obtener una lista de asociados SIP directos certificados, vea el Programa de interoperabilidad abierta de comunicaciones unificadas  [de Microsoft](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).

> [!NOTE]
> La ruta de acceso multimedia que se muestra en esta figura tiene habilitada la omisión de medios (la configuración recomendada). Si opta por deshabilitar la omisión de medios, la ruta de acceso multimedia se enruta a través del servidor de mediación.

En esta topología, los departamentos o grupos de trabajo seleccionados están habilitados para Telefonía IP empresarial. Una puerta de enlace RTC vincula el grupo de trabajo habilitado para Voz sobre Internet (VoIP) a la PBX. Los usuarios que están habilitados para Telefonía IP empresarial, incluidos los trabajadores remotos, se comunican a través de la red IP. Las llamadas Telefonía IP empresarial usuarios a la RTC y a compañeros de trabajo que no están habilitados para Telefonía IP empresarial se enruta a la puerta de enlace RTC adecuada. Las llamadas de compañeros que todavía están en el sistema PBX, o de autores de llamadas en la RTC, se enruta a la puerta de enlace RTC, que reenvía las llamadas a Skype Empresarial Server para el enrutamiento.

Hay dos configuraciones recomendadas para conectar Telefonía IP empresarial a una infraestructura PBX existente para la interoperabilidad: Telefonía IP empresarial detrás de la PBX y Telefonía IP empresarial delante de la PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>Telefonía IP empresarial Detrás de la PBX

Cuando Telefonía IP empresarial se implementa detrás de la PBX, todas las llamadas de la RTC llegan a la PBX, que enruta las llamadas Telefonía IP empresarial los usuarios a una puerta de enlace RTC y las llamadas a los usuarios de PBX a la PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Telefonía IP empresarial delante de la PBX

Cuando Telefonía IP empresarial se implementa delante de la PBX, todas las llamadas llegan a la puerta de enlace RTC, que enruta las llamadas de los usuarios de Telefonía IP empresarial Skype Empresarial Server y las llamadas de los usuarios pbx a la PBX. Las llamadas a la RTC de los usuarios de Telefonía IP empresarial y PBX se enruta a través de la red IP a la puerta de enlace RTC más rentable. En la tabla siguiente se muestran las ventajas y desventajas de esta configuración.

**Ventajas y desventajas de implementar Telefonía IP empresarial en frente de PBX**

|**Ventajas**|**Desventajas**|
|:-----|:-----|
|PBX sigue prestando servicios a usuarios no habilitados para Telefonía IP empresarial.  <br/> |Es posible que las puertas de enlace existentes no admitan las características o la capacidad que desee.  <br/> |
|PBX controla todos los dispositivos anteriores.  <br/> |Requiere un tronco de la puerta de enlace a la PBX y de la puerta de enlace al servidor de mediación. Es posible que necesite más troncos del proveedor de servicios.  <br/> |
|Telefonía IP empresarial usuarios mantienen los mismos números de teléfono.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>VoIP-Only implementación

Telefonía IP empresarial proporciona nuevas empresas, y también nuevos sitios de oficina para empresas existentes, con la oportunidad de implementar una solución VoIP con todas las características sin tener que preocuparse por la integración de PBX o incurrir en los costos importantes de implementación y mantenimiento de una infraestructura IP-PBX. Esta solución admite trabajadores tanto in situ como remotos.

En esta implementación, todas las llamadas se enruta a través de la red IP. Las llamadas a la RTC se enrutan a la puerta de enlace RTC adecuada. Skype Empresarial o Lync Teléfono Edition sirve como softphone. El control remoto de llamadas no está disponible e innecesario porque no hay teléfonos PBX que los usuarios puedan controlar. Los servicios de correo de voz y operadores automáticos están disponibles mediante la implementación opcional de Exchange mensajería unificada (MU).

> [!NOTE]
> Además de la infraestructura de red necesaria para admitir Skype Empresarial Server, una implementación de solo VoIP puede usar una puerta de enlace pequeña y cualificada para admitir máquinas de fax y dispositivos analógicos.

En la siguiente figura se muestra una topología típica para una implementación de solo VoIP.

**Opción de implementación de solo VoIP**

![Opción de implementación de Greenfidle.](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> La ruta de acceso multimedia que se muestra en esta figura tiene habilitada la omisión de medios (la configuración recomendada). Si opta por deshabilitar la omisión de medios, la ruta de acceso multimedia se enruta a través del servidor de mediación.

## <a name="pstn-gateway-deployment-options"></a>Opciones de implementación de puerta de enlace RTC

### <a name="pstn-gateways"></a>Puertas de enlace RTC

Las puertas de enlace de red telefónica conmutada (RTC) son componentes de hardware de terceros que convierten la señalización y los medios entre la infraestructura de Enterprise Voice y la RTC ya sea de forma directa o mediante una conexión a troncos SIP. En cualquier topología, la puerta de enlace finaliza la RTC. La puerta de enlace está aislada en su propia subred y está conectada a la red empresarial a través del servidor de mediación.

Una empresa con varios sitios, normalmente deberá implementar una o más puertas de enlace en cada sitio. Los sitios de sucursal pueden conectarse a la RTC a través de una puerta de enlace o a través de una aplicación de sucursal con funciones de supervivencia, que combina la puerta de enlace y los servidores en un solo cuadro. Si los sitios de sucursal usan una puerta de enlace, tanto un registrador como un servidor de mediación son necesarios en el sitio, a menos que el vínculo WAN sea resistente. Uno o varios servidores de mediación, que se encuentran en servidores front-end, pueden enrutar llamadas para una o más puertas de enlace en cada sitio. Se recomienda que el registrador, el servidor de mediación y la puerta de enlace necesarios en el sitio se implementen como una aplicación de sucursal con funciones de supervivencia.

Determinar el número, el tamaño y la ubicación de las puertas de enlace RTC es quizás la decisión más importante y costosa que debe tomar al planear la infraestructura Telefonía IP empresarial rtc.

A continuación presentamos las principales preguntas que hay que plantearse. Recuerde que las respuestas a estas preguntas están todas interrelacionadas

- ¿Cuántas puertas de enlace RTC se necesitan? La respuesta depende del número de usuarios, el número previsto de llamadas simultáneas (carga de tráfico) y el número de sitios (cada sitio necesita una).

- ¿Qué tamaño deben tener las puertas de enlace? La respuesta depende del número de usuarios en el sitio y en la carga de trabajo.

- ¿Dónde deben colocarse las puertas de enlace? La respuesta depende en parte de la topología y en parte de la distribución geográfica de la organización.

  Tenga en cuenta también las opciones de topología de la puerta de enlace (para más información, vea Topologías de puerta de enlace más adelante, en este tema).

#### <a name="mn-trunk-support"></a>Compatibilidad con troncos M:N

Los servidores de mediación pueden enrutar llamadas a través de varias puertas de enlace, controladores de borde de sesión (SBC) proporcionados por proveedores de servicios de telefonía por Internet o una combinación de las dos. Además, varios servidores de mediación del grupo pueden interactuar con varias puertas de enlace. La ruta lógica definida entre un servidor de mediación y una puerta de enlace se denomina tronco. Cuando un usuario interno hace una llamada RTC, la lógica de enrutamiento saliente en el grupo de servidores front-end elige qué tronco enrutar de todas las combinaciones posibles que puedan estar disponibles para enrutar esa llamada en particular. Con el equilibrio de carga dns, si una llamada no llega a una puerta de enlace debido a un problema con un servidor de mediación determinado en el grupo de servidores, la llamada se volverá a llamar a un servidor de mediación alternativo en el grupo de servidores.

Para obtener más información acerca de la planeación de varias puertas de enlace, vea [M:N trunk in Skype Empresarial Server](m-n-trunk.md).

Para obtener más información detallada sobre otras mejoras de enrutamiento saliente, vea [Call Routes](/previous-versions/office/lync-server-2013/lync-server-2013-voice-routes).

#### <a name="gateway-topologies"></a>Topologías de puerta de enlace

Cuando vaya a responder las preguntas fundamentales de la implementación de puertas de enlace, haga lo siguiente:

1. Contar los sitios en los que desea proporcionar conectividad RTC mediante Telefonía IP empresarial.

2. Calcule el tráfico en cada sitio (número de usuarios y promedio de llamadas por hora y por usuario).

3. Implemente una o varias puertas de enlace en cada sitio para administrar el tráfico previsto.

Con esta topología, las llamadas entre los empleados de cada sitio y entre los sitios se redirigen a través de la intranet de la compañía. Las llamadas a la RTC se redirigen a través de la red IP de la empresa a las puertas de enlace que se encuentran más cerca de la ubicación de los números de destino. No obstante, ¿qué sucede si la organización admite docenas, cientos o incluso miles de sitios distribuidos por uno o varios continentes, como es el caso de muchas entidades financieras y otras empresas de gran tamaño? En esos casos, no es práctico implementar una puerta de enlace independiente en cada sitio.

Para solucionar este problema, muchas empresas grandes prefieren implementar uno o algunos sitios centrales de telefonía grandes.

En esta topología, se implementan varias puertas de enlace grandes suficientes para dar cabida a la carga de usuario prevista en cada sitio central. El proveedor de servicios de telefonía de la compañía transfiere a un sitio central todas las llamadas para los usuarios de la empresa. La lógica de enrutamiento en el sitio central determina si la llamada se debe enrutar a través de la intranet o a la RTC.

#### <a name="gateway-location"></a>Ubicación de las puertas de enlace

La ubicación de las puertas de enlace también puede determinar los tipos de puertas de enlace elegidos y su configuración. Hay docenas de protocolos RTC, pero ninguno es un estándar mundial. Si todas las puertas de enlace se encuentran en un solo país o región, esto no supone un problema. Ahora bien, si se colocan puertas de enlace en varios países o regiones, cada una de ellas debe configurarse según las normas RTC de cada país o región. Es más, las puertas de enlace certificadas para, por ejemplo, Canadá pueden no estar certificadas en la India, Brasil o la Unión Europea.

#### <a name="gateway-size-and-number"></a>Tamaño y número de las puertas de enlace

Las puertas de enlace RTC que la mayoría de las organizaciones considerarán implementar varía entre 2 y 960 puertos. (Hay puertas de enlace incluso más grandes, pero las usan principalmente los proveedores de servicios de telefonía.) A la hora de valorar el número de puertos que la organización necesita, siga estas directrices:

- Las organizaciones con necesidades de telefonía reducidas (una llamada de RTC por usuario y por hora) deben asignar un puerto por cada quince usuarios. Por ejemplo, si hay veinte usuarios, se necesitará una puerta de enlace con dos puertos.

- Las organizaciones con necesidades de telefonía moderadas (dos llamadas de RTC por usuario y por hora) deben asignar un puerto por cada diez usuarios. Por ejemplo, si hay cien usuarios, se necesitará un total de diez puertos asignados a una o varias puertas de enlace.

- Las organizaciones con grandes necesidades de telefonía (tres o más llamadas de RTC por usuario y por hora) deben asignar un puerto por cada cinco usuarios. Por ejemplo, si hay 47 000 usuarios, se necesitarán 9400 puertos repartidos entre al menos diez puertas de enlace grandes.

- Se pueden adquirir puertos adicionales a medida que aumenta el número de usuarios o el tráfico de la organización.

Sea cual sea el número de usuarios, existe la opción de implementar menos puertas de enlace grandes o más puertas de enlace pequeñas. Como regla general, se recomienda un mínimo de dos puertas de enlace para mantener la disponibilidad si una de ellas deja de funcionar.

Cada puerta de enlace RTC que implemente debe tener al menos un servidor de mediación correspondiente.
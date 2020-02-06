---
title: Conexiones SIP directas en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Se admiten conexiones SIP directas entre Skype empresarial Server y las puertas de enlace RTC y IP-PBX en telefonía IP empresarial.
ms.openlocfilehash: 1948e08d63aed9d49c70443a386adce6dc65f78e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803060"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Conexiones SIP directas en Skype empresarial Server

Se admiten conexiones SIP directas entre Skype empresarial Server y las puertas de enlace RTC y IP-PBX en telefonía IP empresarial.

Puede usar las conexiones SIP directas para conectar Skype empresarial Server a una de las siguientes opciones:

- Un IP-PBX

- Una puerta de enlace RTC

Para implementar una conexión SIP directa, debe seguir esencialmente los mismos pasos de implementación que para implementar un tronco de SIP. En ambos casos, la conexión se implementa con la interfaz externa de un servidor de mediación. La única diferencia es que los troncos SIP se conectan a una entidad externa, como una puerta de enlace ITSP, y se conectan conexiones SIP directas a una entidad interna de su red local, como un IP-PBX o una puerta de enlace de red telefónica conmutada (RTC).

## <a name="direct-sip-deployment-options"></a>Opciones de implementación SIP directa

### <a name="skype-for-business-server-stand-alone"></a>Skype empresarial Server independiente
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Si su organización usa una de las implementaciones descritas en esta sección, puede usar Skype empresarial Server como la única solución de telefonía para una parte o la totalidad de una organización. En esta sección se describen las siguientes implementaciones en detalle:

- **Implementación incremental:** Esta opción supone que tiene una infraestructura de intercambio privado existente (PBX) y tiene previsto presentar la telefonía IP en forma incremental para grupos más pequeños o equipos de su organización.

- **Implementación de solo VoIP:** esta opción supone que está considerando implementar una telefonía IP empresarial en un sitio que no tiene una infraestructura de telefonía tradicional.

#### <a name="incremental-deployment"></a>Implementación incremental

En la implementación incremental, Skype empresarial Server es la única solución de telefonía para equipos individuales o departamentos, mientras que el resto de los usuarios de una organización continúa usando un sistema PBX. Esta estrategia de implementación incremental proporciona una forma de introducir la telefonía IP en su empresa a través de programas piloto controlados. Los grupos de trabajo cuyas comunicaciones unificadas de Microsoft se sirven mejor a las comunicaciones unificadas de Microsoft se mueven a telefonía IP empresarial, mientras que otros usuarios permanecen en el PBX existente. Se pueden migrar grupos de trabajo adicionales a la telefonía IP empresarial, según sea necesario.

Se recomienda usar la opción incremental si tiene definidos claramente grupos de usuarios que tienen requisitos de comunicación en común y que se prestan a una administración centralizada. Esta opción también es eficaz si tiene equipos o departamentos que están dispersos en áreas geográficas amplias, donde el ahorro en los cargos de larga distancia puede ser significativo. De hecho, esta opción es útil para crear equipos virtuales cuyos miembros pueden estar dispersos por todo el mundo. Puede crear, modificar o desintegrar esos equipos con rapidez para desplazarse por los requisitos empresariales.

La siguiente ilustración muestra la topología genérica para la implementación de telefonía IP empresarial detrás de un sistema PBX. Esta es la topología recomendada para una implementación incremental.

**Opción de implementación incremental**

![Diagrama de opción de migración departamental](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Si va a conectar su implementación de Skype empresarial Server a un socio certificado SIP certificado, una puerta de enlace de red telefónica conmutada (RTC) entre el servidor de mediación y la PBX no es necesaria. Para obtener una lista de socios de SIP directos certificados, consulte el [programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> La ruta multimedia que se muestra en esta figura tiene habilitada la omisión de medios (configuración recomendada). Si opta por deshabilitar la omisión de medios, la ruta de medios se redirige a través del servidor de mediación.

En esta topología, los departamentos o grupos de trabajo seleccionados están habilitados para telefonía IP empresarial. Una puerta de enlace RTC vincula el grupo de trabajo habilitado para el protocolo de voz a través de Internet (VoIP) a la PBX. Los usuarios que están habilitados para telefonía IP empresarial, incluidos los trabajadores remotos, se comunican a través de la red IP. Las llamadas de los usuarios de Voice empresarial a la RTC y a los compañeros de trabajo que no están habilitados para telefonía IP empresarial se enrutan a la puerta de enlace PSTN correspondiente. Las llamadas de colegas que aún están en el sistema PBX, o de las personas que llaman en la RTC, se enrutan a la puerta de enlace PSTN, que reenvía las llamadas a Skype empresarial Server para su enrutamiento.

Hay dos configuraciones recomendadas para conectar telefonía IP empresarial a una infraestructura PBX existente para la interoperabilidad: telefonía IP empresarial detrás de la PBX y la voz de empresa delante de la PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>Telefonía IP empresarial detrás de la PBX

Cuando se implementa la telefonía IP empresarial tras la PBX, todas las llamadas de la RTC llegan a la PBX, que dirige las llamadas a los usuarios de telefonía de la empresa a una puerta de enlace RTC y llama a los usuarios de PBX a la PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Voz empresarial delante de la PBX

Cuando se implementa la telefonía IP empresarial delante del sistema PBX, todas las llamadas llegan a la puerta de enlace PSTN, que dirige las llamadas de los usuarios de telefonía a Skype empresarial a Skype empresarial y les llama a los usuarios de PBX. Las llamadas a la RTC desde los usuarios de Enterprise Voice y PBX se dirigen a través de la red IP a la puerta de enlace RTC más económica. En la tabla siguiente se muestran las ventajas y desventajas de esta configuración.

**Ventajas y desventajas de implementar voz empresarial en la parte delantera de PBX**

|**Ofrece**|**Desventajas**|
|:-----|:-----|
|PBX aún da servicio a los usuarios que no tienen habilitada la telefonía IP empresarial.  <br/> |Es posible que las puertas de enlace existentes no admitan las características o la capacidad que usted desee.  <br/> |
|PBX controla todos los dispositivos anteriores.  <br/> |Requiere un tronco desde la puerta de enlace a la PBX y desde la puerta de enlace hasta el servidor de mediación. Es posible que necesites más troncos del proveedor de servicios.  <br/> |
|Los usuarios de voz empresarial conservan los mismos números de teléfono.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>Implementación solo con VoIP

Enterprise Voice ofrece nuevas empresas y también nuevos sitios de Office para empresas existentes, con la oportunidad de implementar una solución VoIP completa sin tener que preocuparse por la integración de PBX o incurrir en la implementación y el mantenimiento importantes. costos de una infraestructura IP-PBX. Esta solución es compatible tanto con trabajadores remotos como en el sitio.

En esta implementación, todas las llamadas se enrutan a través de la red IP. Las llamadas a la RTC se enrutan a la puerta de enlace PSTN adecuada. Skype empresarial o Lync Phone Edition funciona como softphone. El control remoto de llamadas no está disponible e innecesario porque no hay teléfonos PBX para que los usuarios puedan controlarlo. Los servicios de correo de voz y de operador automático están disponibles a través de la implementación opcional de mensajería unificada de Exchange (UM).

> [!NOTE]
> Además de la infraestructura de red necesaria para admitir Skype empresarial Server, una implementación de solo VoIP puede usar una pequeña y certificada puerta de enlace para admitir equipos de fax y dispositivos analógicos.

En la siguiente ilustración se muestra una topología típica para una implementación de solo VoIP.

**Opción de implementación solo de VoIP**

![Opción de implementación en entorno virgen](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> La ruta multimedia que se muestra en esta figura tiene habilitada la omisión de medios (configuración recomendada). Si opta por deshabilitar la omisión de medios, la ruta de medios se redirige a través del servidor de mediación.

## <a name="pstn-gateway-deployment-options"></a>Opciones de implementación de la puerta de enlace RTC

### <a name="pstn-gateways"></a>Puertas de enlace RTC

Las puertas de enlace de red de telefonía pública conmutada (RTC) son componentes de hardware de terceros que traducen las señales y los medios entre la infraestructura de telefonía IP empresarial y la RTC, ya sea directamente o a través de una conexión a los troncos SIP. En cualquiera de las dos topologías, la puerta de enlace finaliza la RTC. La puerta de enlace está aislada en su propia subred y está conectada a la red de la empresa a través del servidor de mediación.

Una empresa con varios sitios normalmente implementaría una o más puertas de enlace en cada sitio. Los sitios de sucursales se pueden conectar a la RTC a través de una puerta de enlace o a través de un equipo de sucursales con la supervivencia, que combina puerta de enlace y servidores en un único cuadro. Si los sitios de sucursal usan una puerta de enlace, se necesita un registrador y un servidor de mediación en el sitio, a menos que el vínculo WAN sea resistente. Uno o varios servidores de mediación, que se colocan en servidores front-end, pueden enrutar las llamadas de una o más puertas de enlace en cada sitio. Recomendamos que el registrador, el servidor de mediación y la puerta de enlace necesaria en el sitio se implementen como un equipo de sucursal con la supervivencia.

Determinar el número, el tamaño y la ubicación de las puertas de enlace RTC es quizás la decisión más importante y costosa que debe tomarse al planear la infraestructura de voz empresarial.

Estas son las principales preguntas que debe tener en cuenta. Tenga en cuenta que las respuestas a estas preguntas son totalmente interdependientes

- ¿Cuántas puertas de enlace RTC se necesitan? La respuesta depende del número de usuarios, el número anticipado de llamadas simultáneas (carga de tráfico) y el número de sitios (cada sitio necesita uno).

- ¿Qué tamaño deberían tener las puertas de enlace? La respuesta depende del número de usuarios del sitio y de la carga de tráfico.

- ¿Dónde se deben ubicar los gateways? La respuesta depende en parte de la topología y en parte de la distribución geográfica de su organización.

  También debe tener en cuenta las opciones de topología de la puerta de enlace (para obtener información detallada, vea topologías de puertas de enlace más adelante en este tema).

#### <a name="mn-trunk-support"></a>Compatibilidad con troncos M:N

Los servidores de mediación pueden enrutar las llamadas a través de varias puertas de enlace, controladores de borde de sesión (SBCs) proporcionados por proveedores de servicios de telefonía por Internet o una combinación de ambos. Además, varios servidores de mediación en el grupo pueden interactuar con varias puertas de enlace. La ruta lógica definida entre un servidor de mediación y la puerta de enlace se denomina troncal. Cuando un usuario interno realiza una llamada RTC, la lógica de enrutamiento de salida en el grupo de servidores front-end elige el tronco que se va a enrutar sobre todas las combinaciones posibles que pueden estar disponibles para enrutar esa llamada en particular. Con el equilibrio de carga de DNS, si una llamada no logra alcanzar una puerta de enlace debido a un problema con un servidor de mediación en particular en el grupo, la llamada se volverá a intentar con un servidor de mediación alternativo en el grupo.

Para obtener más información sobre cómo planear varias puertas de enlace, consulte [M:N troncal en Skype empresarial Server](m-n-trunk.md).

Para obtener más información sobre otras mejoras de enrutamiento saliente, vea [llamar a rutas](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Topologías de puerta de enlace

Cuando considere las preguntas fundamentales de la implementación de puertas de enlace, siga estos pasos:

1. Contar los sitios en los que desea proporcionar conectividad RTC mediante telefonía IP empresarial.

2. Estimar el tráfico de cada sitio (número de usuarios y número promedio de llamadas por hora por usuario).

3. Implemente una o más puertas de enlace en cada sitio para controlar el tráfico anticipado.

Con esta topología, las llamadas entre los trabajadores de cada sitio y entre sitios se enrutan a través de la intranet. Las llamadas a la RTC se enrutan a través de la red IP de la empresa a las puertas de enlace que están más cerca de la ubicación de los números de destino. Pero, ¿qué sucede si su organización admite decenas, cientos o incluso miles de sitios distribuidos en uno o más continentes, ya que muchas instituciones financieras y otras grandes empresas sí lo hacen? En estos casos, no es práctico implementar una puerta de enlace independiente en cada sitio.

Para solucionar este problema, muchas de las grandes empresas prefieren implementar uno o varios sitios centrales de telefonía grandes.

En esta topología, se implementan varias puertas de enlace grandes suficientes para dar cabida a la carga de usuarios prevista en cada sitio central. El proveedor de servicios telefónicos de la empresa reenvía todas las llamadas a los usuarios de la empresa a un sitio central. La lógica de enrutamiento en el sitio central determina si la llamada se debe enrutar a través de la intranet o de la RTC.

#### <a name="gateway-location"></a>Ubicación de la puerta de enlace

La ubicación de la puerta de enlace también puede determinar los tipos de puertas de enlace que elija y cómo se configuran. Hay docenas de protocolos de RTC, ninguno de los cuales es un estándar de todo el mundo. Si todas las puertas de enlace están ubicadas en un solo país o región, esto no es un problema, pero si encuentra puertas de enlace en varios países o regiones, cada una de ellas debe estar configurada de acuerdo con los estándares de la RTC de ese país o región. Además, las puertas de enlace que están certificadas para funcionar, por ejemplo, Canadá, pueden no estar certificadas en India, Brasil ni la Unión Europea.

#### <a name="gateway-size-and-number"></a>Número y tamaño de la puerta de enlace

Las puertas de enlace RTC que la mayoría de las organizaciones considerará para implementar intervalos de 2 a tan sólo puertos de 960. (Hay incluso puertas de enlace más grandes, pero las usan principalmente los proveedores de servicios de telefonía). Al estimar el número de puertos que necesita su organización, siga estas pautas:

- Las organizaciones con uso de telefonía leve (una llamada de RTC por usuario por hora) deben asignar un puerto por cada 15 usuarios. Por ejemplo, si tiene 20 usuarios, necesitará una puerta de enlace con dos puertos.

- Las organizaciones con uso moderado de telefonía (dos llamadas RTC por usuario por hora) deben asignar un puerto por cada 10 usuarios. Por ejemplo, si tiene 100 usuarios, necesitará un total de 10 puertos asignados entre una o más puertas de enlace.

- Las organizaciones con uso intensivo de telefonía (tres o más llamadas RTC por usuario por hora) deben asignar un puerto por cada cinco usuarios. Por ejemplo, si tiene 47.000 usuarios, necesitará un total de 9.400 puertos asignados entre al menos 10 puertas de enlace grandes.

- Se pueden adquirir puertos adicionales a medida que aumenta el número de usuarios o la cantidad de tráfico de la organización.

Para cualquier número de usuarios que deba admitir, tiene la opción de implementar menos puertas de enlace, más grandes o más pequeñas. Como regla, se recomienda usar un mínimo de dos puertas de enlace para una organización para mantener la disponibilidad si una de ellas falla.

Cada puerta de enlace RTC que implemente debe tener al menos un servidor de mediación correspondiente.



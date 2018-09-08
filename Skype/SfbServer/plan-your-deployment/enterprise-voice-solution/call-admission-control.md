---
title: Planeación de control de admisión de llamadas en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Obtenga información sobre el control de admisión de llamadas, lo que puede impedir que las llamadas procedentes de produciendo si poseen una calidad deficiente multimedia, en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: db4b2f7a77885ff96a4b43b01aa2337996418217
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883854"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Planeación de control de admisión de llamadas en Skype para Business Server

Obtenga información sobre el control de admisión de llamadas, lo que puede impedir que las llamadas procedentes de produciendo si poseen una calidad deficiente multimedia, en Skype para Business Server Enterprise Voice.

Para las aplicaciones basadas en IP, como la telefonía, el vídeo y el uso compartido de aplicaciones, el ancho de banda disponible de las redes empresariales no se considera normalmente un factor limitante dentro de los entornos de LAN. Sin embargo, en los vínculos WAN que conectan sitios entre sí, el ancho de banda de red puede restringirse.

Cuando el tráfico de red produce una saturación en un vínculo WAN, los mecanismos actuales, como la puesta en cola, el almacenamiento en búfer y la pérdida de paquetes, se usan para solucionar la congestión. El tráfico adicional normalmente se retrasa hasta que la congestión de la red mejora o, si es necesario, se elimina el tráfico. Para el tráfico de datos convencional en estas situaciones, el cliente receptor puede recuperarse; pero para el tráfico en tiempo real, como las comunicaciones unificadas, la congestión de la red no se puede solucionar de este modo, porque el tráfico de las comunicaciones unificadas es sensible a la latencia y a la pérdida de paquetes. La congestión en la WAN puede ocasionar una baja calidad de la experiencia (QoE) para los usuarios finales. Para el tráfico en tiempo real en condiciones de congestión, es mejor denegar las llamadas que permitir las conexiones de baja calidad.

El servicio de control de admisión de llamadas (CAC) determina si hay suficiente ancho de banda de red para establecer una sesión en tiempo real con una calidad aceptable. En Skype para Business Server, CAC controla el tráfico en tiempo real sólo de audio y vídeo, pero no afecta al tráfico de datos. Si la ruta de acceso de WAN predeterminada no tiene el ancho de banda necesario, CAC puede intentar redirigir la llamada a través de una ruta de acceso de Internet o a través de la red telefónica conmutada (RTC).

En esta sección se describen las funciones del servicio de control de admisión de llamadas y explica cómo planificar para CAC.

> [!NOTE]
> Skype para Business Server tiene tres características avanzadas de Enterprise Voice: admisión control de llamadas (CAC), servicios de emergencia (E9-1-1) y el desvío de medios. Para obtener información general de la planeación de información que es común a todos los tres de estas características, vea [configuración de red para las características avanzadas de Enterprise Voice en Skype para Business Server](network-settings-for-advanced-features.md).

El diseño CAC en Skype para Business Server ofrece cuatro atributos principales:

- Es fácil de implementar y administrar, y no requiere equipamiento adicional, como ocurre con los enrutadores especialmente configurados.

- Está dirigido a casos de uso de comunicaciones unificadas críticas, como los escenarios con usuarios remotos o múltiples puntos de presencia. Las directivas del CAC se aplican de acuerdo con el lugar donde se ubica el extremo, no con el lugar donde se hospeda el usuario.

- Además de las llamadas de voz, puede aplicarse a otro tráfico, como las videollamadas y las sesiones de conferencia de audio/vídeo.

- Proporciona la flexibilidad necesaria para habilitar la representación de varios tipos de topologías de red.

Si una sesión de vídeo o voz nueva supera los límites de ancho de banda que se han establecido en un vínculo WAN, la sesión se bloquea o (solo para llamadas telefónicas) se desvía a la RTC.

El CAC controla el tráfico en tiempo real solo para voz y vídeo. No controla el tráfico de datos.

Los administradores definir directivas CAC, que se aplican por el servicio de directivas de ancho de banda que se instala con cada grupo de servidores Front-End. Configuración de CAC se propaga automáticamente a Skype todos los para servidores Front-End de Business Server en la red.

Para las llamadas en las que se produce un error debido a las directivas del CAC, el orden de prioridad para desviar la llamada es el siguiente:

1. Internet

2. RTC

3. Correo de voz

Información de las capturas del registro de detalles de llamadas (CDR) sobre las llamadas que se desvían a la RTC o al correo de voz. El CDR no captura información sobre las llamadas que se desvían a Internet, ya que Internet se considera una ruta de acceso alternativa en lugar de una opción secundaria.

> [!NOTE]
> Los depósitos de correo de voz no se denegarán por restricciones del ancho de banda.

El servicio de directivas de ancho de banda genera dos tipos de archivo de registro en formato de valores separados por comas (CSV). El archivo de registro de **errores de comprobación** captura información cuando se deniegan las solicitudes de ancho de banda. El archivo de registro de **uso de vínculos** captura una instantánea de la topología de red y del uso del ancho de banda del vínculo WAN. Estos dos archivos de registro pueden ayudarte a ajustar las directivas del CAC en función del uso.

## <a name="call-admission-control-considerations"></a>Consideraciones relacionadas con el servicio de control de admisión de llamadas

El administrador elige instalar el servicio de directiva de ancho de banda en el primer grupo configurado en la ubicación central. Dado que hay una única ubicación central por región de red, solo hay un servicio de directivas de ancho de banda en cada región de red, que administra la directiva de ancho de banda para dicha región, sus sitios asociados y los vínculos a esos sitios. Se ejecuta el servicio de directiva de ancho de banda como parte de los servidores Front-End y, por lo tanto, la alta disponibilidad es integrada dentro de ese grupo. El servicio de directivas de ancho de banda que se ejecutan en cada servidor Front-End se sincroniza cada 15 segundos. Si se produce un error en el grupo de servidores Front-End, las directivas del CAC ya no se aplican para ese sitio hasta que el grupo de servidores Front-End y, en consecuencia, el servicio de directivas de ancho de banda vuelve a estar operativo. Esto implica que todas las llamadas pasarán mientras el servicio de directivas de ancho de banda esté fuera de servicio. En consecuencia, existe la posibilidad de saturación del ancho de banda de los vínculos durante este período.

El servicio de directivas de ancho de banda proporciona una alta disponibilidad dentro de un grupo de servidores Front-End; Sin embargo, no proporciona redundancia a través de grupos de servidores Front-End. El servicio de directivas de ancho de banda no conmutación por error de un grupo de servidores Front-End a otra. Una vez que se restaura el servicio al grupo de servidores Front-End, el servicio de directivas de ancho de banda se reanuda y puede exigir comprobaciones de directiva de ancho de banda de nuevo.

### <a name="network-considerations"></a>Consideraciones relacionadas con la red

Aunque se aplica la restricción de ancho de banda para audio y vídeo mediante el servicio de directivas de ancho de banda en Skype para Business Server, esta restricción no se exige en el enrutador de red (capa 2 y 3). El CAC no puede evitar que una aplicación de datos, por ejemplo, consuma todo el ancho de banda de la red con un vínculo WAN, incluido el ancho de banda que la directiva del CAC reserva para el audio y el vídeo. Para proteger el ancho de banda necesario en la red, puedes implementar un protocolo de calidad de servicio (QoS) como, por ejemplo, los servicios diferenciados (DiffServ). Así pues, el procedimiento recomendado es coordinar las directivas de ancho de banda del CAC que definas con cualquier configuración de QoS que puedas implementar.

### <a name="media-and-signaling-paths-over-vpn"></a>Rutas de acceso de señalización y medios sobre VPN

Si tu empresa admite medios a través de VPN, asegúrate de que tanto la secuencia de medios como la secuencia de señalización pasen por la VPN o se redirijan a través de Internet. De forma predeterminada, las secuencias de medios y de señalización pasan por el túnel VPN.

### <a name="call-admission-control-of-outside-users"></a>Servicio de control de admisión de llamadas de usuarios externos

Más allá de los límites de la Skype para organización Business Server no se aplica de control de admisión de llamadas. No se puede aplicar el CAC para el tráfico de medios recorrido de Internet, que no está administrado por Skype para Business Server. Comprobaciones CAC se realizará en la parte de la llamada que fluye a través de la red de empresa si el extremo llamado pertenece a la organización y el servidor perimetral se ha agregado a la configuración de red, tal como se describe en el control de admisión de llamadas [ implementación: lista de comprobación de final de Skype para Business Server](../../deploy/deploy-enterprise-voice/final-checklist.md). Si el extremo destinatario de la llamada no pertenece a la organización, como un usuario federado o un usuario PIC, no se realizan comprobaciones de la directiva de ancho de banda y la llamada saliente ignorará cualquier restricción de CAC.

### <a name="call-admission-control-of-pstn-connections"></a>Servicio de control de admisión de llamadas de conexiones RTC

El control de admisión de llamadas es aplicable en el servidor de mediación, independientemente de si se conecta a un sistema IP/PBX, una puerta de enlace RTC o un tronco SIP. Dado que el servidor de mediación es un agente de usuario opuesta (B2BUA), termina multimedia. Tiene dos lados de la conexión: un lado que está conectado a Skype para Business Server y un lado de la puerta de enlace, que está conectado a puertas de enlace RTC, IP/PBX o troncos SIP. Para obtener información detallada acerca de las conexiones de RTC, consulte [Plan para la conectividad de RTC en Skype para Business Server](pstn-connectivity-0.md).

CAC se puede aplicar en ambos lados del servidor de mediación a menos que el desvío de medios está habilitado. Si está habilitado el desvío de medios, el tráfico de medios no atravesar el servidor de mediación, pero en su lugar fluye directamente entre el Skype para clientes empresariales y la puerta de enlace. En este caso, el CAC no es necesario. Para obtener información detallada, vea [Plan para los medios de desvío en Skype para la empresa](media-bypass.md).

En la siguiente figura se muestra cómo se aplica el CAC a las conexiones RTC con la omisión de medios habilitada e inhabilitada.

**Cumplimiento del control de admisión de llamadas en conexiones al RTC**

![Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Definir los requisitos para el servicio de control de admisión de llamadas

La planificación del servicio de control de admisión de llamadas (CAC) requiere información detallada sobre la topología de red de la empresa. Para obtener ayuda para planificar las directivas del servicio de control de admisión de llamadas, siga estos pasos.

1. Identifica los concentradores o las redes troncales (denominados regiones de red) dentro de la red empresarial.

2. Identifica las oficinas o las ubicaciones (denominadas sitios de red) dentro de cada región de red.

3. Determina la ruta de red entre cada par de regiones de red.

4. Determina los límites de ancho de banda para cada vínculo WAN.

    > [!NOTE]
    > Límites de ancho de banda, consulte ¿cuánto del ancho de banda en un vínculo WAN se asigna para Enterprise Voice y el tráfico de audio y vídeo. Cuando un vínculo WAN se describe como "ancho de banda restringido", el vínculo WAN tiene un límite de ancho de banda que es menor que el tráfico de máxima esperada sobre el vínculo.

5. Identifica las subredes IP asignadas a cada sitio de red.

Para explicar estos conceptos, usaremos la topología de red de ejemplo que se muestra en la ilustración siguiente.

**Topología de ejemplo para el servicio de control de admisión de llamadas**

![Ejemplo de topología de red de Litware Inc.](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Todos los sitios de red están asociados a una región de red. Por ejemplo, Portland, Reno y Albuquerque están incluidos en la región Norteamérica. En esta figura, solo se muestran los vínculos WAN que tienen aplicadas directivas de CAC con límites de ancho de banda. Los sitios de red de Chicago, Nueva York y Detroit aparecen dentro del óvalo regional Norteamérica porque no tienen ancho de banda restringido y, por lo tanto, no precisan directivas de CAC.

Los componentes de esta topología de ejemplo se explican en las siguientes secciones. Para obtener más información acerca de cómo se ha planificado esta topología, incluidos los límites de ancho de banda, consulte [ejemplo: recopilación de requisitos de control de admisión de llamadas en Skype para Business Server](example-gathering-requirements.md).

### <a name="identify-network-regions"></a>Identificar regiones de red

Una región de red representa una red troncal de red o un concentrador de red.

Un concentrador de red o una red troncal es parte de la infraestructura de una red informática que interconecta las diferentes partes de la red, lo que proporciona una ruta de acceso para el intercambio de información entre las diferentes LAN o subredes. Una red troncal puede enlazar diversas redes, ya sea de una pequeña ubicación a una extensa área geográfica. Con frecuencia, la capacidad de la red troncal es mayor que la de las redes que se conectan a ella.

Nuestra topología de ejemplo tiene tres regiones de red: Norteamérica, EMEA y APAC. Una región de red contiene un grupo de sitios de red (vea la definición de sitios de red que aparece más adelante en este tema). Trabaja con el equipo de operaciones de red para identificar tus regiones de red.

### <a name="associating-a-central-site-with-each-network-region"></a>Asociar un sitio central a cada región de red

CAC requiere que se ha definido un Skype para sitio central Business Server para cada región de red. El sitio central está seleccionado con la mejor conectividad de red y el mayor ancho de banda respecto al resto de sitios dentro de esa región de la red. El ejemplo anterior de topología de red muestra tres regiones de red, cada una con un sitio central que administra las decisiones de CAC. En el ejemplo anterior, la asociación correspondiente se muestra en la siguiente tabla.

> [!NOTE]
> Los sitios centrales no corresponden necesariamente a sitios de red. En los ejemplos de esta documentación, algunos sitios centrales (Chicago, Londres y Pekín) comparten el mismo nombre que los sitios de red. Sin embargo, incluso si un sitio central y el sitio de red comparten el mismo nombre, el sitio central es un elemento de la Skype para la topología de servidor empresarial, mientras que el sitio de red es una parte de la red general en el que reside el Skype de topología de servidores de negocio.

**Regiones de red, sitios centrales y sitios de red**

|**Región de red**|**Sitio central**|**Sitios de red**|
|:-----|:-----|:-----|
|Norteamérica  <br/> |Chicago  <br/> |Chicago  <br/> Nueva York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |Londres  <br/> |Londres  <br/> Colonia  <br/> |
|APAC  <br/> |Pekín  <br/> |Pekín  <br/> Manila  <br/> |

### <a name="identify-network-sites"></a>Identificar sitios de red

Un sitio de red representa una ubicación en la que la organización tiene un local físico, por ejemplo, oficinas, un conjunto de edificios o un campus. Un local físico con una LAN y que tiene conectividad WAN con otros sitios se considera un sitio de red. Para iniciar, realizar un inventario de todas las oficinas de la organización. En nuestra topología de ejemplo, la región de red Norteamérica está formada por los siguientes sitios de red: Nueva York, Chicago, Detroit, Portland, Reno y Albuquerque.

Necesitas asociar todos los sitios de red con una región de red. En función de si el sitio de red tiene un vínculo WAN restringido, se asocia una directiva de ancho de banda con el sitio de red. Para obtener más detalles sobre las directivas de CAC y el ancho de banda que se asigna con ellas, mira "Definir directivas de ancho de banda" más adelante en este tema. Para configurar el CAC, asocia sitios de red con regiones de red y, luego, crea directivas de asignación de ancho de banda para aplicarlas a las conexiones con ancho de banda restringido entre un sitio o una región determinado y las conexiones WAN entre los sitios y las regiones.

### <a name="identify-network-links"></a>Identificar vínculos de red

Los vínculos de red representan conexiones a la WAN física que vincula diferentes regiones y sitios. En nuestra topología de ejemplo, hay dos vínculos de red regional, cinco vínculos de red entre regiones y sitios, y un vínculo de red entre dos sitios.

Los dos vínculos de red regional están entre Norteamérica y EMEA, representado como NA-EMEA-LINK y entre APAC y EMEA, representado como EMEA-APAC-LINK.

Los vínculos de sitios se indican con las líneas que conectan Portland, Reno y Albuquerque con la región Norteamérica, Manila con la región APAC y Colonia con la región EMEA. La línea entre Reno y Albuquerque muestra un vínculo de red directo entre estos dos sitios.

### <a name="define-bandwidth-policies"></a>Definir directivas de ancho de banda

Colabora con el equipo de operaciones de red para determinar la cantidad de ancho de banda WAN disponible para el tráfico de audio y vídeo en tiempo real a través de los vínculos WAN de la organización. Normalmente, las directivas de ancho de banda se aplican a vínculos WAN si el uso del ancho de banda está restringido; es decir, si se espera que sea mayor que el ancho de banda que se puede asignar para modalidades de audio y vídeo.

Las directivas de ancho de banda de CAC definen el ancho de banda máximo que se puede reservar para las modalidades de audio y vídeo en tiempo real. Ya que CAC no limita el ancho de banda de otro tráfico, no puede evitar que el tráfico de otros datos, como una transferencia de archivos grande o un streaming de música, use todo el ancho de banda de la red.

Las directivas de ancho de banda del CAC pueden definir cualquiera de las siguientes opciones o todas ellas:

- Ancho de banda total máximo asignado para audio.

- Ancho de banda total máximo asignado para vídeo.

- Ancho de banda máximo asignado para una única llamada de audio (sesión).

- Ancho de banda máximo asignado para una única videollamada (sesión).

> [!NOTE]
> Todos los valores de ancho de banda CAC representan los límites de ancho de banda máximo *unidireccional* .

> [!NOTE]
> El Skype para las características de directiva de voz de servidor empresarial de proporcionar comprueba la capacidad de invalidar la directiva de ancho de banda para las llamadas entrantes para el usuario (no para las llamadas salientes realizadas por el usuario). Una vez establecida la sesión, se justificará detalladamente el consumo de ancho de banda. Esta configuración se tiene que usar con moderación. Para obtener información detallada, vea [crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para la empresa](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) o [modificar una directiva de voz y configurar registros de uso de RTC](https://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx) en la documentación de implementación.

Para optimizar la utilización del ancho de banda por sesión, ten en cuenta el tipo de códecs de audio y vídeo que se van a usar. En concreto, evita una asignación insuficiente de ancho de banda a un códec que crees que se va a usar con frecuencia. Por el contrario, si deseas evitar que los medios usen un códec que precisa mayor ancho de banda, deberás establecer un ancho de banda máximo por sesión lo suficientemente bajo para disuadir su uso. En lo que respecta al audio, no todos los códecs están disponibles para todos los escenarios. Por ejemplo:

- Llamadas de audio de punto a punto entre Skype para los extremos de negocio usarán RTAudio (8kHz) o RTAudio (16kHz) cuando se tiene en cuenta el ancho de banda y la prioridad de los códecs.

- Las llamadas de conferencia entre Skype para los extremos de negocio y el servicio de conferencia A/v usarán G.722 o Siren.

- Las llamadas a la red telefónica conmutada (RTC) a o desde Skype para los extremos de negocio usarán G.711 o RTAudio (8kHz).

Usa la tabla que aparece a continuación para optimizar la configuración del ancho de banda máximo por sesión.

**Utilización de ancho de banda por códecs**

|**Códec**|**Requisito de ancho de banda sin corrección de errores de reenvío (FEC)**|**Requisito de ancho de banda con corrección de errores de reenvío (FEC)**|
|:-----|:-----|:-----|
|RTAudio (8 kHz)  <br/> |49,8 kbps  <br/> |61,6 kbps  <br/> |
|RTAudio (16 kHz)  <br/> |67 kbps  <br/> |96 kbps  <br/> |
|Siren  <br/> |57,6 kbps  <br/> |73,6 kbps  <br/> |
|G.711  <br/> |102 kbps  <br/> |166 kbps  <br/> |
|G.722  <br/> |105,6 kbps  <br/> |169,6 kbps  <br/> |
|RTVideo (CIF 15 fps)  <br/> |260 kbps  <br/> |No disponible  <br/> |
|RTVideo (VGA 30 fps)  <br/> |610 kbps  <br/> |No disponible  <br/> |

> [!NOTE]
> Los requisitos de ancho de banda tienen en cuenta la sobrecarga para: Ethernet II, IP, Protocolo de datagramas de usuario (UDP), Protocolo de transporte en tiempo real (RTP) y Protocolo de transporte en tiempo real seguro (SRTP). También incluyen 10 kbps para sobrecarga de RTCP.

Los códecs G.722.1 y Siren son similares, pero ofrecen diferentes velocidades de bits.

G.722, el códec predeterminado para Skype para conferencias de Business Server, es completamente diferente de los códecs G.722.1 y Siren.

El códec Siren se usa en Skype para Business Server en las situaciones siguientes:

- Si la directiva de ancho de banda tiene un valor demasiado bajo para el uso de G.722.

- Si un cliente de Communications Server 2007 o Communications Server 2007 R2 se conecta a un Skype para el servicio de conferencia de Business Server (debido a que estos clientes no admiten el códec G.722).

**Utilización de ancho de banda por escenario**

|**Escenario**|**Requisito de ancho de banda optimizado para cantidad (kbps)**|**Requisito de ancho de banda para modo de equilibrado (kbps)**|**Requisito de ancho de banda optimizado para calidad (kbps)**|
|:-----|:-----|:-----|:-----|
|Llamadas de audio de punto a punto  <br/> |45 kbps  <br/> |62 kbps  <br/> |91 kbps  <br/> |
|Llamadas de conferencia  <br/> |53 kbps  <br/> |101 kbps  <br/> |165 kbps  <br/> |
|Llamadas RTC (entre Skype para puerta de enlace de RTC y profesionales, con desvío de medios)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Llamadas RTC entre (Skype para la empresa) y el servidor de mediación, sin desvío de medios  <br/> |45 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Llamadas RTC (entre el servidor de mediación y puerta de enlace de RTC, sin desvío de medios)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Skype para la empresa - Polycom llama  <br/> |101 kbps  <br/> |101 kbps  <br/> |101 kbps  <br/> |

### <a name="identify-ip-subnets"></a>Identificar subredes IP

Para cada sitio de red, tendrás que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, tu trabajo se habrá simplificado en gran medida.

En nuestro ejemplo, el sitio Nueva York de la región Norteamérica tiene asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Demos por supuesto que Alberto, que normalmente trabaja en Detroit, viaja a la oficina de Nueva York para recibir formación. Cuando encienda su PC y se conecte a la red, su PC obtendrá una dirección IP de uno de los cuatro rangos reservados a Nueva York, por ejemplo, 172.29.80.103.

> [!CAUTION]
> Las subredes IP especificadas durante la configuración de red del servidor necesitan coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para la omisión de medios. Un Skype para clientes empresariales toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada. Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente. Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales. (Si implementar el control de admisión de llamadas, pero el desvío de medios no, el control de admisión de llamadas funcionará correctamente incluso si configurar virtuales subredes.) Por ejemplo, si un cliente inicia sesión en un equipo con una dirección IP de 172.29.81.57 con una máscara de subred de 255.255.255.0, Skype para la empresa solicitará el identificador de desvío asociado con la subred 172.29.81.0. Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia porque el registrador está buscando específicamente la subred 172.29.81.0. Por lo tanto, es importante que el administrador introduce subredes exactamente como proporcionado por Skype para clientes empresariales (que se aprovisionan con subredes durante la configuración de red estática o DHCP.)

## <a name="best-practices-for-call-admission-control"></a>Procedimientos recomendados para el servicio de control de admisión de llamadas

Para mejorar el rendimiento y facilitar la implementación, sigue los procedimientos recomendados descritos a continuación a la hora de implementar el servicio de control de admisión de llamadas:

- Comprueba que las redes WAN estén correctamente aprovisionadas para el tráfico de medios actual y previsto.

    > [!NOTE]
    > Recomendamos tener en cuenta un búfer además de los límites de ancho de banda. Existen escenarios, como condiciones de carrera, que afectan al ancho de banda total usado y pueden dar lugar a situaciones en que se supera el límite de ancho de banda. Por ejemplo, si se intentan iniciar dos llamadas cuando el tráfico de medios está alcanzando un límite de ancho de banda, es posible que una de ellas sea denegada porque la otra intentó iniciarse primero.

- Supervisa el uso de red y los registros de detalles de llamadas para que puedas elegir una configuración óptima de CAC y actualizarla conforme el uso de la red va cambiando.

- Usa directivas de ancho de banda de CAC para complementar la configuración de QoS.

- Si deseas volver a redirigir llamadas bloqueadas a la RTC, comprueba la capacidad y las funciones de la RTC. Para obtener información detallada, vea [Planeación de enrutamiento de llamadas salientes](https://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx).

    > [!NOTE]
    > La capacidad hace referencia a la cantidad de puertos que necesitas abrir para admitir un nuevo posible enrutamiento de la RTC.



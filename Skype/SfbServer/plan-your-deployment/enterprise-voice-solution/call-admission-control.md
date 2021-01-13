---
title: Planear el control de admisión de llamadas en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
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
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Obtenga información sobre el control de admisión de llamadas, que puede impedir que las llamadas tengan una calidad de medios deficiente, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 07b1e057e9edc296d0eee694e323e3c3c27ef05f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825960"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Planear el control de admisión de llamadas en Skype Empresarial Server

Obtenga información sobre el control de admisión de llamadas, que puede impedir que las llamadas tengan una calidad de medios deficiente, en Skype Empresarial Server Telefonía IP empresarial.

En el caso de las aplicaciones basadas en IP, como telefonía, vídeo y uso compartido de aplicaciones, el ancho de banda disponible de las redes empresariales no suele considerarse un factor limitante en entornos LAN. Sin embargo, en los vínculos WAN que interconectan sitios, el ancho de banda de red puede ser limitado.

Cuando el tráfico de red sobrescribe un vínculo WAN, se usan mecanismos actuales como colas, almacenamiento en búfer y colocación de paquetes para resolver la congestión. El tráfico adicional suele retrasarse hasta que la congestión de la red se acote o, si es necesario, se descarta el tráfico. Para el tráfico de datos convencional en estas situaciones, el cliente receptor puede recuperarse. Sin embargo, para el tráfico en tiempo real, como las comunicaciones unificadas, la congestión de la red no se puede resolver de esta manera, porque el tráfico de comunicaciones unificadas es sensible tanto a la latencia como a la pérdida de paquetes. La congestión en la WAN puede provocar una mala calidad de la experiencia (QoE) para los usuarios. Para el tráfico en tiempo real en condiciones congestionadas, es mejor denegar llamadas que proporcionar conexiones de mala calidad.

El servicio de control de admisión de llamadas (CAC) determina si hay suficiente ancho de banda de red para establecer una sesión en tiempo real con una calidad aceptable. En Skype Empresarial Server, cac controla el tráfico en tiempo real solo para audio y vídeo, pero no afecta al tráfico de datos. Si la ruta de acceso WAN predeterminada no tiene el ancho de banda necesario, CAC puede intentar enrutar la llamada a través de una ruta de acceso de Internet o de la RTC.

En esta sección se describen las funciones de control de admisión de llamadas y explica cómo planear para CAC.

> [!NOTE]
> Skype Empresarial Server tiene tres características avanzadas de Telefonía IP empresarial: control de admisión de llamadas (CAC), servicios de emergencia (E9-1-1) y desvío de medios. Para obtener información general sobre la planeación que es común a las tres características, consulte Configuración de red para las características avanzadas de Telefonía IP empresarial en [Skype Empresarial Server.](network-settings-for-advanced-features.md)

El diseño del CAC en Skype Empresarial Server ofrece cuatro atributos principales:

- Es fácil de implementar y administrar, y no requiere equipamiento adicional, como ocurre con los enrutadores especialmente configurados.

- Está dirigido a casos de uso de comunicaciones unificadas críticas, como los escenarios con usuarios remotos o múltiples puntos de presencia. Las directivas del CAC se aplican de acuerdo con el lugar donde se ubica el extremo, no con el lugar donde se hospeda el usuario.

- Además de las llamadas de voz, puede aplicarse a otro tráfico, como las videollamadas y las sesiones de conferencia de audio/vídeo.

- Proporciona la flexibilidad necesaria para habilitar la representación de varios tipos de topologías de red.

Si una sesión de vídeo o voz nueva supera los límites de ancho de banda que se han establecido en un vínculo WAN, la sesión se bloquea o (solo para llamadas telefónicas) se desvía al RTC.

El CAC controla el tráfico en tiempo real solo para voz y vídeo. No controla el tráfico de datos.

Los administradores definen directivas de CAC, que son aplicadas por el servicio de directivas de ancho de banda que se instala con cada grupo de servidores front-end. La configuración del CAC se propaga automáticamente a todos los servidores front-end de Skype Empresarial Server de la red.

Para las llamadas en las que se produce un error debido a las directivas del CAC, el orden de prioridad para desviar la llamada es el siguiente:

1. Internet

2. RTC

3. Correo de voz

Información de las capturas del registro de detalles de llamadas (CDR) acerca de las llamadas que se desvían al RTC o al correo de voz. El CDR no captura información acerca de las llamadas que se desvían a Internet, ya que Internet se considera una ruta alternativa en lugar de una opción secundaria.

> [!NOTE]
> Los depósitos de correo de voz no se denegarán por restricciones del ancho de banda.

El servicio de directivas de ancho de banda genera dos tipos de archivo de registro en formato de valores separados por comas (CSV). El archivo de registro de **errores de comprobación** captura información cuando se deniegan las solicitudes de ancho de banda. El archivo de registro de **uso de vínculos** captura una instantánea de la topología de red y del uso del ancho de banda del vínculo WAN. Estos dos archivos de registro pueden ayudarle a ajustar las directivas del CAC en base al uso.

## <a name="call-admission-control-considerations"></a>Consideraciones relacionadas con el control de admisión de llamadas

El administrador elige instalar el Servicio de directiva de ancho de banda en el primer grupo de servidores configurado en la ubicación central. Dado que hay una única ubicación central por región de red, solo hay un servicio de directivas de ancho de banda en cada región de red, que gestiona la directiva de ancho de banda para dicha región, sus sitios asociados y los vínculos a esos sitios. El servicio de directivas de ancho de banda se ejecuta como parte de los servidores front-end y, por lo tanto, la alta disponibilidad está integrada dentro de ese grupo de servidores. El servicio de directivas de ancho de banda que se ejecuta en cada servidor front-end se sincroniza cada 15 segundos. Si se produce un error en el grupo de servidores front-end, las directivas de CAC ya no se aplican para ese sitio hasta que el grupo de servidores front-end y, en consecuencia, el servicio de directivas de ancho de banda vuelve a estar operativo. Esto implica que todas las llamadas pasarán mientras el servicio de directivas de ancho de banda esté fuera de servicio. Por tanto, existe la posibilidad de saturación del ancho de banda de los enlaces durante este período.

El servicio de directivas de ancho de banda proporciona alta disponibilidad dentro de un grupo de servidores front-end; sin embargo, no proporciona redundancia entre grupos de servidores front-end. El servicio de directivas de ancho de banda no puede conmutar por error de un grupo de servidores front-end a otro. Una vez restaurado el servicio al grupo de servidores front-end, el servicio de directivas de ancho de banda se reanuda y puede volver a aplicar comprobaciones de directiva de ancho de banda.

### <a name="network-considerations"></a>Consideraciones relacionadas con la red

Aunque el servicio de directivas de ancho de banda de Skype Empresarial Server aplica la restricción de ancho de banda para audio y vídeo, esta restricción no se aplica en el enrutador de red (capa 2 y 3). El CAC no puede impedir que una aplicación de datos, por ejemplo, consuma todo el ancho de banda de red en un vínculo WAN, incluido el ancho de banda reservado para audio y vídeo por la directiva de CAC. Para proteger el ancho de banda necesario en la red, puede implementar un protocolo de calidad de servicio (QoS) como servicios diferenciados (DiffServ). Por lo tanto, un procedimiento recomendado es coordinar las directivas de ancho de banda de CAC que defina con cualquier configuración de QoS que pueda implementar.

### <a name="media-and-signaling-paths-over-vpn"></a>Rutas de señalización y medios sobre VPN

Si su empresa admite medios a través de VPN, asegúrese de que tanto la secuencia de medios como la secuencia de señalización pasan por la VPN o están enrutadas a través de Internet. De forma predeterminada, las secuencias de medios y de señalización pasan por el túnel VPN.

### <a name="call-admission-control-of-outside-users"></a>Control de admisión de llamadas de usuarios externos

El control de admisión de llamadas no se aplica más allá de los límites de la organización de Skype Empresarial Server. El CAC no se puede aplicar al tráfico de medios que atraviesa Internet, que no está administrado por Skype Empresarial Server. Las comprobaciones de CAC se realizarán en la parte de la llamada que fluye a través de la red empresarial si el extremo llamado pertenece a la organización y el servidor perimetral se ha agregado a la configuración de red, tal como se describe en la implementación del control de admisión de llamadas: lista de comprobación final para [Skype Empresarial Server.](../../deploy/deploy-enterprise-voice/final-checklist.md) Si el extremo al que se llama no pertenece a la organización, como un usuario federado o PIC, no se realiza ninguna comprobación de directiva de ancho de banda y la llamada saliente omitirá las restricciones de CAC.

### <a name="call-admission-control-of-pstn-connections"></a>Control de admisión de llamadas de conexiones RTC

El control de admisión de llamadas es aplicable en el servidor de mediación independientemente de si está conectado a una IP/PBX, una puerta de enlace RTC o un tronco SIP. Dado que el servidor de mediación es un agente de usuario back-to-back (B2BUA), finaliza los medios. Tiene dos lados de conexión: un lado que está conectado a Skype Empresarial Server y un lado de puerta de enlace, que está conectado a puertas de enlace RTC, IP/PBX o troncos SIP. Para obtener más información acerca de las conexiones RTC, consulte [Plan for PSTN connectivity in Skype for Business Server](pstn-connectivity-0.md).

El CAC se puede aplicar en ambos lados del servidor de mediación a menos que esté habilitada la omisión de medios. Si la omisión de medios está habilitada, el tráfico de medios no atraviesa el servidor de mediación, sino que fluye directamente entre el cliente de Skype Empresarial y la puerta de enlace. En este caso, el CAC no es necesario. Para obtener más información, consulte [Plan for media bypass in Skype for Business](media-bypass.md).

En la siguiente figura se muestra cómo se aplica el CAC a las conexiones RTC con el desvío de medios habilitado e inhabilitado.

**Aplicación del control de admisión de llamadas en conexiones al RTC**

![Aplicación de la conexión de omisión de medios de CAC de voz](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Definir los requisitos para el control de admisión de llamadas

La planeación del servicio de control de admisión de llamadas (CAC) requiere información detallada sobre la topología de red de la empresa. Para obtener ayuda para planear las directivas del servicio de control de admisión de llamadas, siga estos pasos.

1. Identifique los concentradores o redes troncales (denominadas regiones de red) dentro de la red de la empresa.

2. Identifique las oficinas o ubicaciones (denominadas sitios de red) dentro de cada región de red.

3. Determine la ruta de red entre cada par de regiones de red.

4. Determine los límites de ancho de banda para cada vínculo WAN.

    > [!NOTE]
    > Los límites de ancho de banda hacen referencia a la cantidad de ancho de banda en un vínculo WAN que se asigna al tráfico Telefonía IP empresarial de audio y vídeo. Cuando un vínculo WAN se describe como "con ancho de banda restringido", el vínculo WAN tiene un límite de ancho de banda inferior al tráfico máximo esperado a través del vínculo.

5. Identifique las subredes IP asignadas a cada sitio de red.

Para explicar estos conceptos, usaremos la topología de red de ejemplo que se muestra en la figura siguiente.

**Topología de ejemplo para el servicio de control de admisión de llamadas**

![Ejemplo de topología de red de Litware Inc.](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Todos los sitios de red están asociados a una región de red. Por ejemplo, Portland, Reno y Albuquerque están incluidos en la región Norteamérica. En esta figura, solo se muestran los vínculos WAN que tienen aplicadas directivas de CAC con límites de ancho de banda. Los sitios de red Chicago, Nueva York y Detroit aparecen dentro del óvalo regional Norteamérica debido a que no tienen ancho de banda restringido y, por lo tanto, no precisan directivas de CAC.

Los componentes de esta topología de ejemplo se explican en las siguientes secciones. Para obtener más información sobre cómo se planeó esta topología, incluidos los límites de ancho de banda, consulte Ejemplo: Recopilación de requisitos para el control de admisión de llamadas [en Skype Empresarial Server.](example-gathering-requirements.md)

### <a name="identify-network-regions"></a>Identificar regiones de red

Una región de red representa una red troncal de red o un concentrador de red.

Un concentrador de red o una red troncal es parte de la infraestructura de una red informática que interconecta las diferentes partes de la red, lo que proporciona una ruta de acceso para el intercambio de información entre las diferentes LAN o subredes. Una red troncal puede enlazar diversas redes, ya sea de una pequeña ubicación a una extensa área geográfica. Con frecuencia, la capacidad de la red troncal es mayor que la de las redes que se conectan a ella.

Nuestra topología de ejemplo tiene tres regiones de red: Norteamérica, EMEA y APAC. Una región de red contiene un grupo de sitios de red (vea la definición de sitios de red que aparece más adelante en este tema). Trabaje con el equipo de operaciones de red para identificar sus regiones de red.

### <a name="associating-a-central-site-with-each-network-region"></a>Asociación de un sitio central con cada región de red

El CAC requiere que se defina un sitio central de Skype Empresarial Server para cada región de red. El sitio central está seleccionado con la mejor conectividad de red y el mayor ancho de banda respecto al resto de sitios dentro de esa región de la red. El anterior ejemplo de topología de red muestra tres regiones de la red, cada uno con un sitio central que administra las decisiones de CAC. En el ejemplo anterior, la asociación correspondiente se muestra en la siguiente tabla.

> [!NOTE]
> Los sitios centrales no corresponden necesariamente a sitios de red. En los ejemplos de esta documentación, algunos sitios centrales (Chicago, Londres y Beijing) comparten el mismo nombre que algunos sitios de red. Sin embargo, incluso si un sitio central y un sitio de red comparten el mismo nombre, el sitio central es un elemento de la topología de Skype Empresarial Server, mientras que el sitio de red forma parte de la red general en la que reside la topología de Skype Empresarial Server.

**Regiones de red, sitios centrales y sitios de red**

|**Región de red**|**Sitio central**|**Sitios de red**|
|:-----|:-----|:-----|
|Norteamérica  <br/> |Guadalajara  <br/> |Guadalajara  <br/> Nueva York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |Londres  <br/> |Londres  <br/> Colonia  <br/> |
|APAC  <br/> |Beijing  <br/> |Beijing  <br/> Manila  <br/> |

### <a name="identify-network-sites"></a>Identificar sitios de red

Un sitio de red representa una ubicación en la que la organización tiene un local físico, por ejemplo, oficinas, un conjunto de edificios o un campus. Un local físico con una LAN y que tiene conectividad WAN con otros sitios se considera un sitio de red. Empiece por realizar un inventario de todas las oficinas de su organización. En nuestra topología de ejemplo, la región de red Norteamérica está formada por los siguientes sitios de red: Nueva York, Chicago, Detroit, Portland, Reno y Albuquerque.

Debe asociar todos los sitios de red con una región de red. En función de si el sitio de red tiene un vínculo WAN restringido, se asocia una directiva de ancho de banda con el sitio de red. Para más información sobre las directivas de CAC y el ancho de banda que asigna mediante ellas, vea "Definir directivas de ancho de banda" posteriormente en este tema. Para configurar el CAC, asocie sitios de red con regiones de red y, a continuación, cree directivas de asignación de ancho de banda para aplicarlas a las conexiones con ancho de banda restringido entre un sitio o región determinada y las conexiones WAN entre los sitios y regiones.

### <a name="identify-network-links"></a>Identificar vínculos de red

Los vínculos de red representan conexiones a la WAN física que vincula diferentes regiones y sitios. En nuestra topología de ejemplo, hay dos vínculos de red regional, cinco vínculos de red entre regiones y sitios y un vínculo de red entre dos sitios.

Los dos vínculos de red regional están entre Norteamérica y EMEA, representado como NA-EMEA-LINK y entre APAC y EMEA, representado como EMEA-APAC-LINK.

Los vínculos de sitios se indican mediante las líneas que conectan Portland, Reno y Albuquerque con la región Norteamérica, Manila con la región APAC y Colonia con la región EMEA. La línea entre Reno y Albuquerque muestra un vínculo de red directo entre estos dos sitios.

### <a name="define-bandwidth-policies"></a>Definir directivas de ancho de banda

Colabore con el equipo de operaciones de red para determinar la cantidad de ancho de banda WAN disponible para tráfico de audio y vídeo en tiempo real a través de los vínculos WAN de la organización. Normalmente, las directivas de ancho de banda se aplican a vínculos WAN si el uso del ancho de banda está restringido; es decir, si se espera que sea mayor que el ancho de banda que se puede asignar para modalidades de audio y vídeo.

Las directivas de ancho de banda de CAC definen el ancho de banda máximo que se puede reservar para las modalidades de audio y vídeo en tiempo real. Ya que CAC no limita el ancho de banda de otro tráfico, no puede evitar que el tráfico de otros datos como una transferencia de archivos grande o transmisión de música, use todo el ancho de banda.

Las directivas de ancho de banda del CAC pueden definir cualquiera de las siguientes opciones o todas ellas:

- Ancho de banda total máximo asignado para audio.

- Ancho de banda total máximo asignado para vídeo.

- Ancho de banda máximo asignado para una única llamada de audio (sesión).

- Ancho de banda máximo asignado para una única videollamada (sesión).

> [!NOTE]
> Todos los valores de ancho de banda de CAC representan los límites máximos de ancho de banda *unidireccional.*

> [!NOTE]
> Las características de la directiva de voz de Skype Empresarial Server proporcionan la capacidad de invalidar las comprobaciones de directivas de ancho de banda para las llamadas entrantes al usuario (no para las llamadas salientes realizadas por el usuario). Una vez establecida la sesión, se justificará detalladamente el consumo de ancho de banda. Esta configuración se debe usar con moderación. Para obtener más información, consulte Crear o modificar una directiva de voz y configurar registros de uso de RTC en [Skype](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) Empresarial o Modificar una directiva de voz y Configurar registros de uso [de](https://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx) RTC en la documentación de implementación.

Para optimizar la utilización del ancho de banda por sesión, tenga en cuenta el tipo de códecs de audio y vídeo que se van a usar. En concreto, evite una asignación insuficiente de ancho de banda a un códec que prevea que se va a usar con frecuencia. Por el contrario, si desea evitar que los medios usen un códec que precisa mayor ancho de banda, deberá establecer un ancho de banda máximo por sesión lo suficientemente bajo para disuadir de su uso. En lo que respecta al audio, no todos los códecs están disponibles para todos los escenarios. Por ejemplo:

- Las llamadas de audio punto a punto entre puntos de conexión de Skype Empresarial usarán RTAudio (8 kHz) o RTAudio (16 kHz) cuando se tiene en cuenta el ancho de banda y la priorización de códecs.

- Las llamadas de conferencia entre los puntos de conexión de Skype Empresarial y el servicio de conferencia A/V usarán G.722 o Siren.

- Las llamadas a la red telefónica conmutada (RTC) desde o hacia los puntos de conexión de Skype Empresarial usarán G.711 o RTAudio (8 kHz).

Use la tabla que aparece a continuación para optimizar la configuración de ancho de banda máximo por sesión.

**Utilización de ancho de banda por códecs**

|**Códec**|**Requisito de ancho de banda sin corrección de errores de reenvío (FEC)**|**Requisito de ancho de banda con corrección de errores de reenvío (FEC)**|
|:-----|:-----|:-----|
|RTAudio (8 kHz)  <br/> |49,8 kbps  <br/> |61,6 kbps  <br/> |
|RTAudio (16 kHz)  <br/> |67 kbps  <br/> |96 kbps  <br/> |
|Siren  <br/> |57,6 kbps  <br/> |73,6 kbps  <br/> |
|G.711  <br/> |102 kbps  <br/> |166 kbps  <br/> |
|G.722  <br/> |105,6 kbps  <br/> |169,6 kbps  <br/> |
|RTVideo (CIF 15 fps)  <br/> |260 kbps  <br/> |No aplicable  <br/> |
|RTVideo (VGA 30 fps)  <br/> |610 kbps  <br/> |No aplicable  <br/> |

> [!NOTE]
> Los requisitos de ancho de banda tienen en cuenta la sobrecarga para: Ethernet II, IP, Protocolo de datagramas de usuario (UDP), Protocolo de transporte en tiempo real (RTP) y Protocolo de transporte en tiempo real seguro (SRTP). También incluyen 10 kbps para sobrecarga de RTCP.

Los códecs G.722.1 y Siren son similares, pero ofrecen diferentes velocidades de bits.

G.722, el códec predeterminado para las conferencias de Skype Empresarial Server, es completamente diferente de los códecs G.722.1 y Siren.

El códec Siren se usa en Skype Empresarial Server en las siguientes situaciones:

- Si la directiva de ancho de banda tiene un valor demasiado bajo para el uso de G.722

- Si un cliente de Communications Server 2007 o Communications Server 2007 R2 se conecta a un servicio de conferencia de Skype Empresarial Server (porque dichos clientes no admiten el códec G.722).

**Utilización de ancho de banda por escenario**

|**Escenario**|**Requisito de ancho de banda optimizado para cantidad (kbps)**|**Requisito de ancho de banda para modo de equilibrado (kbps)**|**Requisito de ancho de banda optimizado para calidad (kbps)**|
|:-----|:-----|:-----|:-----|
|Llamadas de audio de punto a punto  <br/> |45 kbps  <br/> |62 kbps  <br/> |91 kbps  <br/> |
|Llamadas de conferencia  <br/> |53 kbps  <br/> |101 kbps  <br/> |165 kbps  <br/> |
|Llamadas RTC (entre Skype Empresarial y puerta de enlace RTC, con omisión de medios)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Llamadas RTC (entre Skype Empresarial y servidor de mediación, sin desvío de medios)  <br/> |45 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Llamadas RTC (entre el servidor de mediación y la puerta de enlace RTC, sin desvío de medios)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Skype Empresarial: llamadas polycom  <br/> |101 Kbps  <br/> |101 Kbps  <br/> |101 Kbps  <br/> |

### <a name="identify-ip-subnets"></a>Identificar subredes IP

Para cada sitio de red, tendrá que trabajar con el administrador de la red para determinar qué subredes IP están asignadas a cada sitio de red. Si el administrador de la red ya ha organizado las subredes IP en regiones de red y sitios de red, su trabajo se habrá simplificado en gran medida.

En nuestro ejemplo, el sitio Nueva York de la región Norteamérica tiene asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Demos por supuesto que Bob, que normalmente trabaja en Detroit, viaja a la oficina de Nueva York para recibir formación. Cuando encienda su equipo y se conecte a la red, su equipo obtendrá una dirección IP de uno de los cuatro rangos reservados a Nueva York, por ejemplo, 172.29.80.103.

> [!CAUTION]
> Las subredes IP especificadas durante la configuración de red del servidor deben coincidir con el formato que proporcionan los equipos cliente para que se puedan usar adecuadamente para el desvío de medios. Un cliente de Skype Empresarial toma su dirección IP local y enmascara la dirección IP con la máscara de subred asociada. Al determinar el identificador de omisión asociado a cada cliente, el registrador comparará la lista de subredes IP asociadas con cada sitio de red con la subred indicada por el cliente para comprobar que coincidan exactamente. Por este motivo, es importante que las subredes introducidas durante la configuración de la red del servidor sean subredes reales y no virtuales. (Si implementa el control de admisión de llamadas, pero no la omisión de medios, el control de admisión de llamadas funcionará correctamente incluso si configura subredes virtuales). Por ejemplo, si un cliente inicia sesión en un equipo con una dirección IP 172.29.81.57 con una máscara de subred IP de 255.255.255.0, Skype Empresarial solicitará el identificador de omisión asociado con la subred 172.29.81.0. Si la red se define como 172.29.0.0/16, aunque el cliente pertenezca a una subred virtual, el registrador no lo considerará una coincidencia debido a que el registrador está buscando específicamente la subred 172.29.81.0. Por lo tanto, es importante que el administrador introduzca subredes exactamente según lo proporcionado por los clientes de Skype Empresarial (que se aprovisionan con subredes durante la configuración de red de forma estática o mediante DHCP).

## <a name="best-practices-for-call-admission-control"></a>Procedimientos recomendados para el control de admisión de llamadas

Para mejorar el rendimiento y facilitar la implementación, siga los procedimientos recomendados descritos a continuación a la hora de implementar el control de admisión de llamadas:

- Compruebe que las redes WAN estén correctamente aprovisionadas para el tráfico de medios actual y previsto.

    > [!NOTE]
    > Se recomienda tener en cuenta un búfer además de los límites de ancho de banda. Existen escenarios, como condiciones de carrera, que afectan al ancho de banda total usado y pueden dar lugar a situaciones en que se supera el límite de ancho de banda. Por ejemplo, si se intentan iniciar dos llamadas cuando el tráfico de medios está alcanzando un límite de ancho de banda, es posible que una de ellas sea denegada porque la otra intentó iniciarse primero.

- Supervise el uso de red y los registros de detalles de llamadas para que pueda elegir una configuración óptima de control de admisión de llamadas y actualizarla conforme el uso de la red va cambiando.

- Use directivas de ancho de banda de control de admisión de llamadas para complementar la configuración de QoS.

- Si desea volver a enrutar llamadas bloqueados a la RTC, compruebe la capacidad y las funciones de la RTC. Para obtener información detallada, consulte [Planning Outbound Call Routing](https://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx).

    > [!NOTE]
    > La capacidad hace referencia al número de puertos que necesita abrir para poder volver a enrutar la RTC.



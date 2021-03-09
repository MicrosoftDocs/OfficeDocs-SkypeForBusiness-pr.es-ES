---
title: Implementar Calidad de servicio en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Obtenga información sobre cómo preparar la red de su organización para calidad de servicio (QoS) en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c07e3e71d391123d34ae64ebf5806c090c29a29d
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558209"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar calidad de servicio (QoS) en Microsoft Teams

La calidad del servicio (QoS) en Microsoft Teams permite que el tráfico de red en tiempo real que sea sensible a los retrasos de red (por ejemplo, transmisiones de voz o vídeo) se "corte en línea" frente al tráfico que sea menos confidencial (como descargar una nueva aplicación, donde un segundo adicional para descargar no es un gran negocio). QoS usa objetos de directiva de grupo de Windows y listas de control de acceso basadas en puertos para identificar y marcar todos los paquetes en transmisiones en tiempo real. Esto ayuda a su red a dar a las transmisiones de voz, vídeo y uso compartido de pantalla una parte dedicada del ancho de banda de red.

Si es compatible con un gran grupo de usuarios que están experimentando cualquiera de los problemas descritos en este artículo, es probable que tenga que implementar QoS. Es posible que una pequeña empresa con pocos usuarios no necesite QoS, pero incluso allí debería ser útil.

Sin algún tipo de QoS, es posible que vea los siguientes problemas de calidad en voz y vídeo:

- Vibración: paquetes multimedia que llegan a diferentes tarifas, lo que puede provocar que falte palabras o sílabas en las llamadas.
- Pérdida de paquetes: los paquetes se han eliminado, lo que también puede provocar una calidad de voz más baja y una voz difícil de entender
- Tiempo de ida y vuelta retrasado (RTT): los paquetes multimedia tardan mucho tiempo en llegar a sus destinos, lo que provoca retrasos notables entre dos partes de una conversación y hace que las personas hablen entre sí

La forma menos compleja de abordar estos problemas es aumentar el tamaño de las conexiones de datos, tanto interna como externamente a Internet. Dado que esto suele ser prohibitivo para los costos, QoS proporciona una forma de administrar de forma más eficaz los recursos que tiene en lugar de agregar ancho de banda. Para solucionar problemas de calidad, le recomendamos que primero use QoS y, después, agregue ancho de banda solo cuando sea necesario.

Para que QoS sea eficaz, debe aplicar una configuración de QoS coherente en toda la organización. Cualquier parte de la ruta que no sea compatible con sus prioridades de QoS puede degradar la calidad de las llamadas, el vídeo y el uso compartido de pantalla. Esto incluye aplicar la configuración a todos los equipos o dispositivos de usuario, modificadores de red, enrutadores a Internet y el servicio de Teams.

_Figura 1. La relación entre las redes de una organización y los servicios de Microsoft 365 u Office 365_

![Ilustración de la relación entre redes y servicios](media/Qos-in-Teams-Image1.png "La relación entre las redes de una organización y los servicios de Microsoft 365 u Office 365: la red local y los dispositivos se conectan con una red interconectada, que a su vez se conecta con los servicios de voz en la nube y audioconferencia de Microsoft 365 u Office 365.")

## <a name="qos-implementation-checklist"></a>Lista de comprobación de implementación de QoS

En un nivel alto, haga lo siguiente para implementar QoS:

1. [Asegúrese de que la red está lista.](#make-sure-your-network-is-ready)

1. [Seleccione un método de implementación de QoS](#select-a-qos-implementation-method).

1. [Elija rangos de puertos iniciales para cada tipo de elemento multimedia.](#choose-initial-port-ranges-for-each-media-type)

1. Implementar la configuración de QoS:
   1. En clientes que usan un objeto de directiva de grupo (GPO) para establecer intervalos y marcas de puerto de dispositivo [cliente.](QoS-in-Teams-clients.md)
   2. En enrutadores (consulte la documentación del fabricante) u otros dispositivos de red. Esto puede incluir listas de control de acceso (ACL) basadas en puertos o simplemente definir las colas de QoS y las marcas DSCP, o todas ellas.

      > [!IMPORTANT]
      > Se recomienda implementar estas directivas de QoS con los puertos de origen del cliente y una dirección IP de origen y destino de "cualquiera". Esto detectará el tráfico multimedia entrante y saliente en la red interna.  

   3. [Establezca cómo desea administrar el tráfico multimedia de las reuniones de Teams.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Valide la implementación de QoS](#validate-your-qos-implementation) analizando el tráfico de Teams en la red.

Cuando se prepare para implementar QoS, tenga en cuenta las siguientes directrices:

- La ruta más corta a Microsoft 365 es la mejor.
- El cierre de puertos solo provocará una degradación de la calidad.
- No se recomiendan los obstáculos entre ellos, como servidores proxy.
- Limitar el número de saltos:
  - Cliente a perímetro de red: de 3 a 5 saltos
  - ISP a Microsoft network edge: 3 saltos
  - Perímetro de red de Microsoft al destino final: irrelevante

Para obtener información sobre cómo configurar puertos de firewall, vaya a Direcciones [URL e intervalos IP de Office 365.](office-365-urls-ip-address-ranges.md)

## <a name="make-sure-your-network-is-ready"></a>Asegúrese de que la red está lista

Si está pensando en una implementación de QoS, ya debería haber determinado los requisitos de ancho de banda y otros [requisitos de red.](prepare-network.md)
  
La congestión del tráfico en una red afectará enormemente a la calidad de los medios. La falta de ancho de banda provoca una degradación del rendimiento y una mala experiencia de usuario. A medida que aumenta la adopción y el uso de Teams, use [informes,](use-call-analytics-to-troubleshoot-poor-call-quality.md)análisis de llamadas por usuario y Panel de calidad de llamadas [(CQD)](turning-on-and-using-call-quality-dashboard.md) para identificar problemas y, después, realizar ajustes con QoS y adiciones selectivas de ancho de banda.

### <a name="vpn-considerations"></a>Consideraciones de VPN

QoS solo funciona según lo esperado cuando se implementa en todos los vínculos entre las personas que llaman. Si usa QoS en una red interna y un usuario inicia sesión desde una ubicación remota, solo puede priorizar dentro de su red interna administrada. Aunque las ubicaciones remotas pueden recibir una conexión administrada implementando una red privada virtual (VPN), una VPN agrega intrínsecamente sobrecarga de paquetes y crea retrasos en el tráfico en tiempo real. Le recomendamos que evite ejecutar tráfico de comunicaciones en tiempo real a través de una VPN.

En una organización global con vínculos administrados que abarcan continentes, recomendamos encarecidamente QoS porque el ancho de banda de esos vínculos está limitado en comparación con la LAN.

## <a name="introduction-to-qos-queues"></a>Introducción a las colas de QoS

Para proporcionar QoS, los dispositivos de red deben tener una forma de clasificar el tráfico y deben poder distinguir voz o vídeo de otro tráfico de red.

Cuando el tráfico de red entra en un enrutador, el tráfico se coloca en una cola. Si una directiva de QoS no está configurada, solo hay una cola y todos los datos se tratan como primero en entrada y en primer lugar con la misma prioridad. Esto significa que el tráfico de voz (que es muy sensible a los retrasos) podría quedar atascado detrás del tráfico, donde un retraso de unos milisegundos adicionales no sería un problema.

Al implementar QoS, define varias colas con una de las varias características de administración de congestión, como las colas prioritarias de Cisco y la Cola justa ponderada basada en [clase (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) y las características de prevención de congestión, como la detección temprana aleatoria ponderada [(WRED).](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_Figura 2. Ejemplos de colas de QoS_

![Ilustración de las colas de QoS y la división de ancho de banda](media/Qos-in-Teams-Image2.png "El ancho de banda total disponible se divide entre varias colas (audio, vídeo y otro tráfico) a las que se han asignado diferentes prioridades.")

Una analogía simple es que QoS crea "carriles de uso compartido de coches" virtuales en su red de datos para que algunos tipos de datos nunca o rara vez se encuentren con un retraso. Una vez creados esos carriles, puede ajustar su tamaño relativo y administrar de forma mucho más eficaz el ancho de banda de conexión que tiene, a la vez que ofrece experiencias de nivel empresarial para los usuarios de su organización.

## <a name="select-a-qos-implementation-method"></a>Seleccionar un método de implementación de QoS

Puede implementar QoS mediante etiquetado basado en puertos, con listas de control de acceso (ACL) en los enrutadores de su red. El etiquetado basado en puertos es el método más confiable, ya que funciona en entornos mixtos de Windows, Mac y Linux y es el más fácil de implementar. Los clientes móviles no proporcionan un mecanismo para marcar el tráfico mediante valores DSCP, por lo que necesitarán este método.  

Con el etiquetado basado en puertos, el enrutador de la red examina un paquete entrante y, si el paquete llegó con un determinado puerto o rango de puertos, lo identifica como un tipo de medio determinado y lo coloca en la cola para ese tipo, agregando una marca [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada al encabezado de paquete IP para que otros dispositivos puedan reconocer su tipo de tráfico y darle prioridad en su cola.

Aunque el etiquetado basado en puertos funciona en todas las plataformas, solo marca el tráfico en el borde WAN (no todo el camino al equipo cliente) y crea sobrecargas de administración. Consulte la documentación proporcionada por el fabricante del enrutador para obtener instrucciones sobre cómo implementar este método.

### <a name="insert-dscp-markers"></a>Insertar marcadores DSCP

También puede implementar QoS mediante un objeto de directiva de grupo (GPO) para dirigir los dispositivos cliente a insertar un marcador DSCP en encabezados de paquetes IP que lo identifiquen como tipo particular de tráfico (por ejemplo, voz). Los enrutadores y otros dispositivos de red se pueden configurar para reconocerlo y colocar el tráfico en una cola independiente de mayor prioridad.

Aunque este escenario es totalmente válido, solo funcionará para clientes de Windows unidos a un dominio. Cualquier dispositivo que no sea un cliente de Windows unido a un dominio no se habilitará para el etiquetado de DSCP. Otros clientes, como los que ejecutan macOS, tienen etiquetas codificadas y siempre etiquetarán el tráfico.

En el lado más, controlar el marcado DSCP a través de GPO garantiza que todos los equipos unidos al dominio reciban la misma configuración y que solo un administrador pueda administrarlos. Los clientes que pueden usar GPO se etiquetarán en el dispositivo de origen y, después, los dispositivos de red configurados pueden reconocer la transmisión en tiempo real mediante el código DSCP y darle una prioridad adecuada.

### <a name="best-practice"></a>Procedimientos recomendados

Se recomienda una combinación de marcas DSCP en el punto de conexión y ACL basadas en puertos en enrutadores, si es posible. Usar un GPO para capturar la mayoría de los clientes y usar también el etiquetado DSCP basado en puertos garantizará que los dispositivos móviles, Mac y otros clientes seguirán teniendo tratamiento de QoS (al menos parcialmente).

Las marcas DSCP se pueden igualar a las estampillas postales que indican a los trabajadores postales lo urgente que es la entrega y la mejor manera de ordenarla para una entrega rápida. Una vez que haya configurado la red para dar prioridad a las transmisiones multimedia en tiempo real, los paquetes perdidos y los paquetes retrasados deberían disminuir considerablemente.

Una vez que todos los dispositivos de la red usan las mismas clasificaciones, marcas y prioridades, es posible reducir o eliminar retrasos, paquetes eliminados y vibración cambiando el tamaño de los rangos de puerto asignados a las colas usadas para cada tipo de tráfico. Desde la perspectiva de Teams, el paso de configuración más importante es la clasificación y el marcado de paquetes. Sin embargo, para que el QoS de un extremo a otro tenga éxito, también debe alinear cuidadosamente la configuración de la aplicación con la configuración de red subyacente. Una vez que QoS está completamente implementado, la administración en curso es una cuestión de ajustar los intervalos de puertos asignados a cada tipo de tráfico en función de las necesidades y el uso real de su organización.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Elegir rangos de puertos iniciales para cada tipo de medio

El valor DSCP indica a una red configurada correspondientemente qué prioridad debe dar a un paquete o transmisión, si la marca DSCP la asignan los clientes o la red en función de la configuración acl. Cada carga de trabajo multimedia obtiene su propio valor DSCP único (es posible que otros servicios permitan que las cargas de trabajo compartan un marcado DSCP, Teams no) y un rango de puertos definido y separado que se usa para cada tipo de medio. Es posible que otros entornos tengan una estrategia de QoS existente, lo que le ayudará a determinar la prioridad de las cargas de trabajo de red.

El tamaño relativo de los intervalos de puertos para diferentes cargas de trabajo de streaming en tiempo real establece la proporción del ancho de banda disponible total dedicado a esa carga de trabajo. Para volver a nuestra analogía postal anterior: una carta con un sello "Correo aéreo" podría ser llevada en una hora al aeropuerto más cercano, mientras que un pequeño paquete marcado como "Correo masivo" puede esperar un día antes de viajar por tierra en una serie de camiones.

_Rangos de puerto iniciales recomendados_

|Tipo de tráfico de medios | Rango de puertos de origen del cliente  |Protocolo|Valor de DSCP|Clase DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50 000 – 50 019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50 020 – 50 039|TCP/UDP|34|Desvío garantizado (AF41)|
|Aplicación/Compartir pantalla| 50 040 – 50 059|TCP/UDP|18|Desvío garantizado (AF21)|
||||||

Tenga en cuenta lo siguiente cuando use esta configuración:

- Si tiene previsto implementar ExpressRoute en el futuro y aún no ha implementado QoS, le recomendamos que siga las instrucciones para que los valores de DSCP sean los mismos de remitente a receptor.

- Todos los clientes, incluidos los clientes móviles y los dispositivos de Teams, usarán estos rangos de puertos y se verán afectados por cualquier directiva DSCP que implemente que use estos rangos de puertos de origen. Los únicos clientes que seguirán usando puertos dinámicos son los clientes basados en exploradores (clientes que permiten a los participantes unirse a reuniones con sus exploradores).

- Aunque el cliente mac usa los mismos rangos de puertos, también usa valores codificados de forma codificada para audio (EF) y vídeo (AF41). Estos valores no son configurables.

- Si más adelante necesita ajustar los intervalos de puertos para mejorar la experiencia del usuario, los rangos de puertos no se pueden superponer y deben ser adyacentes entre sí.

## <a name="migrate-qos-to-teams"></a>Migrar QoS a Teams

Si anteriormente implementó Skype Empresarial Online, incluido el etiquetado de QoS y los intervalos de puertos, y ahora está implementando. Teams, Teams respetará la configuración existente y usará los mismos intervalos de puertos y etiquetado que el cliente de Skype Empresarial. En la mayoría de los casos, no se necesita ninguna configuración adicional.

> [!NOTE]
> Si usa el etiquetado qoS de nombre de aplicación a través de la directiva de grupo, debe agregar Teams.exe como el nombre de la aplicación.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementar QoS en Teams en Windows con PowerShell

**Configurar QoS para audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Configurar QoS para vídeo**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Configurar QoS para compartir**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Administrar puertos de origen en el Centro de administración de Teams

En Teams, los puertos de origen de QoS usados por las diferentes cargas de trabajo deben administrarse activamente y ajustarse según sea necesario. Haciendo referencia a la tabla en [Elegir rangos](#choose-initial-port-ranges-for-each-media-type)de puerto iniciales para cada tipo de medios, los rangos de puertos son ajustables, pero las marcas DSCP no son configurables. Una vez que haya implementado esta configuración, es posible que encuentre que se necesitan más o menos puertos para un tipo de medio determinado. [](use-call-analytics-to-troubleshoot-poor-call-quality.md) El análisis de llamadas por usuario y el Panel de calidad de llamadas [(CQD)](turning-on-and-using-call-quality-dashboard.md) deben usarse para tomar una decisión para ajustar los intervalos de puertos después de implementar Teams y, periódicamente, según las necesidades cambien.

> [!NOTE]
> Si ya configuró QoS en función de los intervalos de puertos de origen y las marcas DSCP para Skype Empresarial Online, se aplicará la misma configuración a Teams y no será necesario realizar más cambios de cliente o red en la asignación, aunque es posible que tenga que establecer los [intervalos usados](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) en Teams para que coincidan con lo que se configuró para Skype Empresarial Online.

Si ya implementó Skype Empresarial Server localmente, es posible que tenga que volver a examinar las directivas de QoS. Ajustar las directivas para que coincidan con la configuración del intervalo de puertos que haya comprobado proporciona una experiencia de usuario de calidad para Teams.

## <a name="validate-your-qos-implementation"></a>Validar la implementación de QoS

Para que QoS sea eficaz, el valor DSCP establecido por el GPO debe estar presente en ambos extremos de una llamada. Al analizar el tráfico generado por el cliente de Teams, puede comprobar que el valor DSCP no se cambia o se quita cuando el tráfico de carga de trabajo de Teams se desplaza por la red.

Preferiblemente, capture el tráfico en el punto de salida de la red. Puede usar la duplicación de puertos en un conmutador o enrutador para ayudarle con esto.

## <a name="implement-qos-for-other-devices"></a>Implementar QoS para otros dispositivos

Lea estos temas para obtener información sobre cómo implementar QoS para Intune, Surface, iOS, Android y Mac

- [QoS para Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [QoS para Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [QoS para iOS, Android y Mac](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Temas relacionados

- [Vídeo: Planificación de red](https://aka.ms/teams-networking)

- [Preparar la red de la organización para Microsoft Teams](prepare-network.md)

- [Implementar QoS en el cliente de Teams](QoS-in-Teams-clients.md)

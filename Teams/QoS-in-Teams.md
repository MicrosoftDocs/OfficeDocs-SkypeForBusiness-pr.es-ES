---
title: Implementar Calidad de servicio en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Obtenga más información sobre cómo preparar la red de su organización de calidad de servicio (QoS) en Microsoft Teams.
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
ms.openlocfilehash: 52b1d03be3e5d54260084bbf44ad6695404607c9
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766583"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar calidad de servicio (QoS) en Microsoft Teams

Calidad de servicio (QoS) en Microsoft Teams permite que el tráfico de red en tiempo real sea sensible a los retrasos de la red (por ejemplo, secuencias de voz o vídeo) a "cortar en línea" frente al tráfico menos sensible (como descargar una nueva aplicación, donde un extra adicional que descargar no es una gran oferta). QoS usa objetos de directiva de grupo de Windows y listas de control de acceso basadas en puertos para identificar y marcar todos los paquetes en las transmisiones en tiempo real. Esto ayuda a que su red proporcione audio, vídeo y la pantalla compartida transmite una parte específica del ancho de banda de la red.

Si admite un grupo grande de usuarios que experimentan alguno de los problemas descritos en este artículo, probablemente necesite implementar QoS. Es posible que una pequeña empresa con pocos usuarios no necesite QoS, pero incluso allí debería ser útil.

Sin alguna forma de QoS, es posible que vea los siguientes problemas de calidad en la voz y el vídeo:

- Vibración: paquetes multimedia que llegan a tarifas diferentes, lo que puede provocar que falten palabras o sílabas en las llamadas.
- Pérdida de paquetes: paquetes descartados, lo que también puede dar como resultado una menor calidad de voz y dificultad para comprender la voz
- Tiempo de ida y vuelta retardado (RTT): los paquetes multimedia tardan mucho en llegar a sus destinos, lo que provoca retrasos evidentes entre dos partes en una conversación y hace que las personas se comuniquen entre sí

La manera menos compleja de solucionar estos problemas es aumentar el tamaño de las conexiones de datos, tanto internamente como fuera de Internet. Como esto suele ser prohibitiva, QoS proporciona una forma más eficaz de administrar los recursos que tiene en lugar de agregar ancho de banda. Para solucionar problemas de calidad, recomendamos que use primero QoS y, a continuación, agregue el ancho de banda solo cuando sea necesario.

Para que QoS sea efectivo, debe aplicar una configuración de QoS coherente en toda la organización. Cualquier parte de la ruta que no admita las prioridades de QoS puede degradar la calidad de las llamadas, el vídeo y la pantalla compartida. Esto incluye aplicar la configuración a todos los equipos o equipos de los usuarios, conmutadores de red, routers a Internet y el servicio de Teams.

_Ilustración 1. La relación entre las redes de una organización y los servicios de Microsoft 365 u Office 365_

![Ilustración de la relación entre redes y servicios](media/Qos-in-Teams-Image1.png "La relación entre las redes de una organización y los servicios de Microsoft 365 u Office 365: la red y los dispositivos locales se conectan con una red de interconexión, que a su vez se conecta con los servicios de conferencia de nube y voz de nube de Microsoft 365 u Office 365.")

## <a name="qos-implementation-checklist"></a>Lista de comprobación de implementación de QoS

En un nivel alto, haga lo siguiente para implementar QoS:

1. [Asegúrese de que su red está lista](#make-sure-your-network-is-ready)

1. [Seleccione un método de implementación de QoS](#select-a-qos-implementation-method)

1. [Elegir intervalos de puertos iniciales para cada tipo de medio](#choose-initial-port-ranges-for-each-media-type)

1. Implementar la configuración de QoS:
   1. En los clientes que usan un objeto de directiva de grupo (GPO) para [establecer intervalos de puertos de dispositivo de cliente y marcas](QoS-in-Teams-clients.md)
   2. En los enrutadores (consulte la documentación del fabricante) u otros dispositivos de red. Esto puede incluir listas de control de acceso (ACL) basadas en puertos o simplemente definir las colas de QoS y las marcas de DSCP, o todas ellas.

      > [!IMPORTANT]
      > Recomendamos implementar estas directivas de QoS con los puertos de origen del cliente y una dirección IP de origen y destino de "cualquiera". Esto capturará el tráfico multimedia entrante y saliente en la red interna.  

   3. [Establezca cómo desea controlar el tráfico multimedia de las reuniones de Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Valide la implementación de QoS mediante el](#validate-your-qos-implementation) análisis del tráfico de Teams en la red.

Mientras prepara la implementación de QoS, tenga en cuenta las siguientes pautas:

- La ruta más corta a Microsoft 365 es la mejor
- Cerrar puertos solo provocará una degradación de la calidad
- No se recomienda ningún obstáculo en los intermedios, como los proxies
- Limitar el número de saltos:
  - Cliente a perímetro de red: entre 3 y 5 saltos
  - Proveedor de servicios de Internet a Microsoft Network Edge: 3 saltos
  - Perímetro de la red de Microsoft en el destino final: irrelevante

Para obtener información sobre cómo configurar puertos de firewall, vaya a [Office 365 URL e intervalos IP](office-365-urls-ip-address-ranges.md).

## <a name="make-sure-your-network-is-ready"></a>Asegúrese de que su red está lista

Si está pensando en una implementación de QoS, ya debe haber determinado cuáles son los requisitos de ancho de banda y otros [requisitos de red](prepare-network.md).
  
La gestión del tráfico en toda la red afectará enormemente la calidad de los medios. La falta de ancho de banda conlleva la degradación del rendimiento y una mala experiencia del usuario. A medida que aumentan la adopción y el uso de equipos, use informes, [análisis de llamadas por usuario](use-call-analytics-to-troubleshoot-poor-call-quality.md)y [Panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md) para identificar los problemas y, a continuación, realice ajustes con QoS y adiciones de ancho de banda selectivo.

### <a name="vpn-considerations"></a>Consideraciones sobre VPN

QoS solo funciona como se espera cuando se implementa en todos los vínculos entre las personas que llaman. Si usa QoS en una red interna y un usuario inicia sesión desde una ubicación remota, solo puede priorizar en su red administrada interna. Aunque las ubicaciones remotas pueden recibir una conexión administrada al implementar una red privada virtual (VPN), una VPN agrega de forma inherente sobrecarga de paquetes y crea retrasos en el tráfico en tiempo real. Le recomendamos que evite ejecutar tráfico de comunicaciones en tiempo real a través de una VPN.

En una organización internacional con vínculos administrados que abarcan continentes, recomendamos encarecidamente QoS porque el ancho de banda de esos vínculos está limitado en comparación con la LAN.

## <a name="introduction-to-qos-queues"></a>Introducción a las colas de QoS

Para proporcionar QoS, los dispositivos de red deben tener una forma de clasificar el tráfico y deben poder diferenciar la voz o el video de otro tráfico de red.

Cuando el tráfico de red entra en un enrutador, el tráfico se coloca en una cola. Si una directiva QoS no está configurada, solo hay una cola y todos los datos se tratan como "primero en estar", primero en salir con la misma prioridad. Eso significa que el tráfico de voz (que es muy sensible a los retrasos) puede demorarse tras el tráfico, en el que un retraso de algunos milisegundos adicionales no sería un problema.

Al implementar QoS, se definen varias colas con una de varias características de administración de congestión, como la cola prioritaria de Cisco y las características de prevención de congestión [ponderadas basadas en clases (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) y de prevención de congestión, como la [Detección anticipada precoz (WRED) ponderada](https://en.wikipedia.org/wiki/Weighted_random_early_detection).

_Ilustración 2. Ejemplos de colas de QoS_

![Ilustración de las colas de QoS y la división de ancho de banda](media/Qos-in-Teams-Image2.png "El ancho de banda total disponible se divide entre varias colas (audio, vídeo y otros tipos de tráfico) a las que se les ha asignado prioridades diferentes.")

Una analogía simple es que QoS crea "carriles de autousos" virtuales en su red de datos para que algunos tipos de datos nunca se encuentren con un retraso. Una vez que cree esos carriles, puede ajustar su tamaño relativo y, de forma más eficaz, el ancho de banda de la conexión que tiene, sin dejar de ofrecer experiencias empresariales para los usuarios de su organización.

## <a name="select-a-qos-implementation-method"></a>Seleccione un método de implementación de QoS

Puede implementar QoS mediante el etiquetado basado en el puerto, mediante listas de control de acceso (ACL) en los enrutadores de su red. El etiquetado basado en puertos es el método más confiable porque funciona en entornos mixtos de Windows, Mac y Linux y es la más fácil de implementar. Los clientes móviles no proporcionan un mecanismo para marcar el tráfico mediante valores de DSCP, por lo que requerirán este método.  

Con el etiquetado basado en puertos, el enrutador de la red examina un paquete entrante y, si el paquete llegó usando un determinado puerto o intervalo de puertos, lo identifica como un tipo de medio determinado y lo coloca en la cola para ese tipo, agregando una marca de [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada al encabezado del paquete IP para que otros dispositivos puedan reconocer su tipo de tráfico y darle prioridad en su cola

Si bien el etiquetado basado en el puerto funciona a través de plataformas, solo marca el tráfico en la periferia de la WAN (no en el equipo cliente) y crea un overhead de administración. Para obtener instrucciones sobre cómo implementar este método, consulte la documentación proporcionada por el fabricante del router.

### <a name="insert-dscp-markers"></a>Insertar marcadores de DSCP

También puede implementar QoS mediante un objeto de directiva de grupo (GPO) para indicar a los dispositivos de cliente que inserten un marcador de DSCP en los encabezados de paquetes IP que lo identifiquen como un tipo de tráfico determinado (por ejemplo, voz). Los enrutadores y otros dispositivos de red se pueden configurar para que reconozcan esto y pongan el tráfico en una cola independiente de mayor prioridad.

Aunque este escenario es completamente válido, solo funcionará para clientes de Windows Unidos a un dominio. Cualquier dispositivo que no sea un cliente de Windows unido a un dominio no se habilitará para el etiquetado de DSCP. Los clientes como Mac OS tienen etiquetas codificadas y siempre marcan el tráfico.

En la parte más, el control del marcado de DSCP mediante GPO garantiza que todos los equipos Unidos a un dominio reciban la misma configuración y que solo un administrador pueda administrarlos. Los clientes que pueden usar un objeto de directiva de grupo se etiquetarán en el dispositivo de origen y, a continuación, los dispositivos de red podrán reconocer el flujo en tiempo real por el código DSCP y darle una prioridad adecuada.

### <a name="best-practice"></a>Procedimiento recomendado

Recomendamos una combinación de marcas de DSCP en el extremo y las ACL basadas en Puerto en los enrutadores, si es posible. Usar un GPO para llamar a la mayoría de los clientes, además de usar el etiquetado de DSCP basado en el puerto, garantizará que los clientes móviles, Mac y otros clientes seguirán teniendo el tratamiento de QoS (al menos parcialmente).

Los marcadores de DSCP se pueden likened a sellos postales que indican a los trabajadores postales lo urgente que es la entrega y cuál es el mejor de clasificarla para su entrega rápida. Una vez que haya configurado su red para dar prioridad a las transmisiones de medios en tiempo real, los paquetes perdidos y los paquetes retrasados deberían disminuir enormemente.

Una vez que todos los dispositivos de la red usen las mismas clasificaciones, marcas y prioridades, es posible reducir o eliminar retrasos, paquetes perdidos y vibración cambiando el tamaño de los intervalos de puertos asignados a las colas usadas para cada tipo de tráfico. Desde la perspectiva de Teams, el paso de configuración más importante es la clasificación y el marcado de paquetes. Sin embargo, para que el QoS se complete correctamente, también tiene que alinear cuidadosamente la configuración de la aplicación con la configuración de red subyacente. Una vez que QoS se ha implementado completamente, la administración continua es una pregunta de ajustar los intervalos de puertos asignados a cada tipo de tráfico según las necesidades de la organización y el uso real.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Elegir intervalos de puertos iniciales para cada tipo de medio

El valor DSCP indica a la red configurada de forma correspondiente la prioridad de dar un paquete o una transmisión por secuencias, ya sea que los clientes o la propia red asignen la marca de DSCP, en función de la configuración de ACL. Cada carga de trabajo multimedia obtiene su propio valor exclusivo de DSCP (otros servicios podrían permitir que las cargas de trabajo compartan un marcado de DSCP, los equipos no) y un intervalo de puertos definido e independiente usado para cada tipo de medio. Otros entornos pueden tener una estrategia de QoS existente, lo que le ayudará a determinar la prioridad de las cargas de trabajo de la red.

El tamaño relativo de los intervalos de puertos para las distintas cargas de trabajo de streaming en tiempo real establece la proporción del ancho de banda total disponible dedicado a esa carga de trabajo. Para volver a la analogía de los mensajes anteriores: una carta con un sello de "correo aéreo" puede tomarse dentro de una hora en el aeropuerto más cercano, mientras que un paquete pequeño marcado como "correo masivo" puede esperar un día antes de viajar por tierra en una serie de camiones.

_Intervalos de puerto iniciales recomendados_

|Tipo de tráfico de medios | Rango de puertos de origen del cliente  |Protocolo|Valor de DSCP|Clase DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50 000 – 50 019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50 020 – 50 039|TCP/UDP|34|Desvío garantizado (AF41)|
|Aplicación/Compartir pantalla| 50 040 – 50 059|TCP/UDP|18|Desvío garantizado (AF21)|
||||||

Tenga en cuenta lo siguiente cuando use esta configuración:

- Si planea implementar ExpressRoute en el futuro y aún no ha implementado QoS, le recomendamos que siga las instrucciones para que los valores DSCP sean los mismos del remitente al destinatario.
- Todos los clientes, incluidos los dispositivos de equipos y clientes móviles, usarán estos intervalos de puertos y se verán afectados por cualquier directiva de DSCP que implemente que use estos intervalos de puertos de origen. Los únicos clientes que seguirán usando puertos dinámicos son los clientes basados en el explorador (clientes que permiten a los participantes unirse a reuniones con sus exploradores).
- Aunque el cliente de Mac usa los mismos intervalos de puertos, también usa los valores de código de audio (EF) y vídeo (AF41). Estos valores no se pueden configurar.
- Si más adelante necesita ajustar los intervalos de puertos para mejorar la experiencia del usuario, los intervalos de puertos no se pueden solapar y deben ser adyacentes entre sí.

## <a name="migrate-qos-to-teams"></a>Migrar QoS a teams

Si ha implementado previamente Skype empresarial online, incluyendo el etiquetado de QoS y los intervalos de puerto, y ya está implementando. Teams, Teams respetará la configuración existente y usará los mismos intervalos de puertos y etiquetado que el cliente de Skype empresarial. En la mayoría de los casos, no será necesario realizar ninguna configuración adicional.

> [!NOTE]
> Si está usando el etiquetado QoS de nombre de aplicación a través de la Directiva de grupo, debe agregar Teams.exe como nombre de la aplicación.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementar QoS en Teams en Windows con PowerShell

**Establecer QoS para el audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Establecer QoS para vídeo**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Establecer QoS para compartir**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Administración de puertos de origen en el centro de administración de Teams

En Teams, los puertos de origen QoS usados por las diferentes cargas de trabajo deben administrarse activamente y ajustarse según sea necesario. Al hacer referencia a la tabla en [elegir los intervalos de puerto iniciales para cada tipo de medio](#choose-initial-port-ranges-for-each-media-type), los intervalos de puertos son ajustables, pero los marcadores de DSCP no se pueden configurar. Una vez que haya implementado esta configuración, es posible que encuentre que se necesitan más o menos puertos para un tipo de medio determinado. El [análisis de llamadas por usuario y el](use-call-analytics-to-troubleshoot-poor-call-quality.md) panel de calidad de [llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md) se deben usar para tomar la decisión de ajustar los intervalos de puertos después de la implementación de equipos y periódicamente a medida que cambien las necesidades.

> [!NOTE]
> Si ya ha configurado QoS en función de los intervalos de puertos de origen y las marcas de DSCP para Skype empresarial online, se aplicará la misma configuración a teams y no se requerirán cambios adicionales en el cliente o la red para la asignación, aunque es posible que tenga que [configurar los intervalos usados en Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) para que coincidan con lo que se ha configurado para Skype empresarial online.

Si ha implementado previamente Skype empresarial Server local, es posible que tenga que volver a examinar las directivas de QoS. Ajustar las directivas para que coincidan con la configuración de intervalo de puertos que ha verificado proporcione una experiencia de calidad al usuario para Teams.

## <a name="validate-your-qos-implementation"></a>Validar la implementación de QoS

Para que QoS sea efectivo, el valor de DSCP establecido por el objeto de directiva de grupo debe estar presente en ambos extremos de una llamada. Al analizar el tráfico generado por el cliente de Teams, puede comprobar que el valor de DSCP no se cambia o quita cuando el tráfico de la carga de trabajo de Teams pasa por la red.

Preferiblemente, capturas el tráfico en el punto de salida de la red. Para ayudarlo, puede usar el reflejo de puertos en un switch o un router.

## <a name="implement-qos-for-other-devices"></a>Implementar QoS para otros dispositivos

Lea estos temas para obtener información sobre cómo implementar QoS para Intune, Surface, iOS, Android y Mac

- [QoS para Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [QoS para Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [QoS para iOS, Android y Mac](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Temas relacionados

- [Vídeo: planificación de red](https://aka.ms/teams-networking)

- [Preparar la red de la organización para Microsoft Teams](prepare-network.md)

- [Implementar QoS en el cliente de Teams](QoS-in-Teams-clients.md)

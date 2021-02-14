---
title: Implementar Calidad de servicio en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Obtenga información sobre cómo preparar la red de su organización para la Calidad de servicio (QoS) en Microsoft Teams.
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
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar la calidad de servicio (QoS) en Microsoft Teams

La calidad de servicio (QoS) en Microsoft Teams permite que el tráfico de red en tiempo real que sea sensible a los retrasos de red (por ejemplo, las transmisiones de voz o vídeo) se "corte en línea" frente al tráfico que sea menos confidencial (como la descarga de una nueva aplicación, donde un segundo adicional para descargar no es demasiado grande). QoS usa objetos de directiva de grupo de Windows y listas de controles de acceso basado en puertos para identificar y marcar todos los paquetes en transmisiones en tiempo real. Esto ayuda a que la red dé a las transmisiones de voz, vídeo y uso compartido de pantalla una parte dedicada del ancho de banda de red.

Si es compatible con un gran grupo de usuarios que experimenta cualquiera de los problemas descritos en este artículo, es probable que necesite implementar QoS. Es posible que una pequeña empresa con pocos usuarios no necesite QoS, pero incluso ahí debería ser útil.

Sin algún tipo de QoS, es posible que vea los siguientes problemas de calidad en voz y vídeo:

- Vibración: paquetes multimedia que llegan a tarifas diferentes, lo que puede provocar la falta de palabras o sílabas en las llamadas
- Pérdida de paquetes: se descartan paquetes, lo que también puede dar lugar a una menor calidad de voz y a que la voz sea difícil de entender.
- Tiempo de ida y vuelta demorado (RTT): los paquetes multimedia tardan mucho tiempo en llegar a sus destinos, lo que provoca retrasos evidentes entre dos partes de una conversación y hace que las personas hablen entre sí

La manera menos compleja de solucionar estos problemas es aumentar el tamaño de las conexiones de datos, tanto interna como de salida a Internet. Como esto suele ser prohibitivo para los costes, QoS ofrece una forma de administrar los recursos de los que dispone de forma más eficaz, en lugar de agregar ancho de banda. Para solucionar problemas de calidad, le recomendamos que primero use QoS y, después, agregue el ancho de banda solo cuando sea necesario.

Para que QoS sea eficaz, debe aplicar una configuración coherente de QoS en toda la organización. Cualquier parte de la ruta que no sea compatible con sus prioridades de QoS puede degradar la calidad de las llamadas, el vídeo y el uso compartido de la pantalla. Esto incluye aplicar la configuración a todos los equipos o dispositivos de usuario, conmutadores de red, enrutadores a Internet y el servicio Teams.

_Figura 1. Relación entre las redes de una organización y los servicios de Microsoft 365 u Office 365_

![Ilustración de la relación entre redes y servicios](media/Qos-in-Teams-Image1.png "La relación entre las redes de una organización y los servicios de Microsoft 365 u Office 365: la red local y los dispositivos se conectan con una red interconectada que, a su vez, se conecta con los servicios de Audioconferencia y Voz en la nube de Microsoft 365 u Office 365.")

## <a name="qos-implementation-checklist"></a>Lista de comprobación de implementación de QoS

En un nivel alto, haga lo siguiente para implementar QoS:

1. [Asegúrate de que tu red esté preparada](#make-sure-your-network-is-ready)

1. [Seleccionar un método de implementación de QoS](#select-a-qos-implementation-method)

1. [Elegir rangos de puertos iniciales para cada tipo de medio](#choose-initial-port-ranges-for-each-media-type)

1. Implementar la configuración de QoS:
   1. En clientes que usan un objeto de directiva de grupo (GPO) para establecer los intervalos de puertos y las marcas de [los dispositivos de cliente](QoS-in-Teams-clients.md)
   2. En enrutadores (consulte la documentación del fabricante) u otros dispositivos de red. Esto puede incluir listas de control de acceso (ACL) basadas en puertos o simplemente definir las colas de QoS y los marcados de DSCP, o todos ellos.

      > [!IMPORTANT]
      > Se recomienda implementar estas directivas de QoS mediante los puertos de origen del cliente y una dirección IP de origen y destino de "cualquiera". Esto detectará el tráfico de medios entrantes y salientes en la red interna.  

   3. [Establecer cómo desea controlar el tráfico multimedia de las reuniones de Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Valide la implementación de QoS](#validate-your-qos-implementation) analizando el tráfico de Teams en la red.

Cuando se prepare para implementar QoS, tenga en cuenta las siguientes instrucciones:

- La ruta de acceso más corta a Microsoft 365 es la mejor
- El cierre de puertos solo provocará una degradación de la calidad
- No se recomiendan los obstáculos entre sí, como los servidores proxy.
- Limite el número de saltos:
  - Cliente al perímetro de red: de 3 a 5 saltos
  - ISP al perímetro de la red de Microsoft: 3 saltos
  - Perímetro de la red de Microsoft al destino final: irrelevante

Para obtener información sobre cómo configurar puertos de firewall, vaya a direcciones URL e [intervalos IP de Office 365.](office-365-urls-ip-address-ranges.md)

## <a name="make-sure-your-network-is-ready"></a>Asegúrate de que tu red esté preparada

Si está pensando en una implementación de QoS, ya debería haber determinado los requisitos de ancho de banda y otros requisitos [de red.](prepare-network.md)
  
La congestión del tráfico en la red afectará muy negativamente a la calidad de medios. La falta de ancho de banda provoca una degradación del rendimiento y una mala experiencia del usuario. A medida que aumenta el uso y la adopción de Teams, use [informes,](use-call-analytics-to-troubleshoot-poor-call-quality.md)análisis de llamadas por usuario y panel de calidad de llamadas [(CQD)](turning-on-and-using-call-quality-dashboard.md) para identificar problemas y, a continuación, realizar ajustes con QoS y adiciones selectivas de ancho de banda.

### <a name="vpn-considerations"></a>Consideraciones de VPN

QoS solo funciona según lo esperado al implementarse en todos los vínculos entre autores de llamadas. Si usa QoS en una red interna y un usuario inicia sesión desde una ubicación remota, solo puede priorizar dentro de su red interna administrada. Aunque las ubicaciones remotas pueden recibir una conexión administrada implementando una red privada virtual (VPN), una VPN agrega intrínsecamente una sobrecarga de paquetes y crea retrasos en el tráfico en tiempo real. Le recomendamos que evite ejecutar tráfico de comunicaciones en tiempo real a través de una VPN.

En una organización global con vínculos administrados que abarcan continentes, recomendamos Encarecidamente QoS, ya que el ancho de banda de esos vínculos está limitado en comparación con la LAN.

## <a name="introduction-to-qos-queues"></a>Introducción a las colas de QoS

Para proporcionar QoS, los dispositivos de red deben tener una manera de clasificar el tráfico y deben ser capaces de distinguir la voz o el vídeo de otro tráfico de red.

Cuando el tráfico de red entra en un enrutador, el tráfico se coloca en una cola. Si no se configura una directiva de QoS, solo hay una cola y todos los datos se tratan como de primer en primer lugar y en primer lugar con la misma prioridad. Eso significa que el tráfico de voz (que es muy sensible a los retrasos) puede quedarse atascado detrás del tráfico, donde un retraso de unos pocos milisegundos adicionales no sería un problema.

Al implementar QoS, defina varias colas usando una de las diversas características de administración de congestión, como las colas de prioridad de Cisco, la cola justa ponderada basada en [clases (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) y las características de evitación de congestión, como la detección anticipada ponderada aleatoria [(WRED).](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_Figura 2. Ejemplos de colas de QoS_

![Ilustración de colas de QoS y división de ancho de banda](media/Qos-in-Teams-Image2.png "El ancho de banda total disponible se divide entre varias colas (audio, vídeo y otro tráfico) que tienen asignadas distintas prioridades.")

Una simple analógica es que QoS crea "calles de uso compartido del automóvil" virtuales en su red de datos para que algunos tipos de datos nunca o rara vez se encuentren con un retraso. Una vez que haya creado esos calles, puede ajustar su tamaño relativo y administrar de forma mucho más eficaz el ancho de banda de conexión que tiene, a la vez que ofrece experiencias de categoría empresarial para los usuarios de su organización.

## <a name="select-a-qos-implementation-method"></a>Seleccionar un método de implementación de QoS

Puede implementar QoS a través de etiquetado basado en puertos, usando listas de control de acceso (ACL) en los enrutadores de su red. El etiquetado basado en puertos es el método más confiable porque funciona en entornos mixtos de Windows, Mac y Linux y es el más sencillo de implementar. Los clientes móviles no proporcionan un mecanismo para marcar el tráfico mediante valores de DSCP, por lo que necesitarán este método.  

Con el etiquetado basado en puertos, el enrutador de la red examina un paquete entrante y, si el paquete ha llegado con un puerto o un intervalo de puertos determinados, lo identifica como un determinado tipo de medio y lo coloca en la cola para ese tipo, agregando una marca [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada al encabezado de paquetes IP para que otros dispositivos puedan reconocer su tipo de tráfico y darle prioridad en su cola.

Aunque el etiquetado basado en puertos funciona en todas las plataformas, solo marca el tráfico en el borde de WAN (no en todo el camino al equipo cliente) y crea una sobrecarga de administración. Consulte la documentación proporcionada por el fabricante del enrutador para obtener instrucciones sobre cómo implementar este método.

### <a name="insert-dscp-markers"></a>Insertar marcadores de DSCP

También puede implementar QoS mediante un objeto de directiva de grupo (GPO) para dirigir a los dispositivos cliente a insertar un marcador DSCP en encabezados de paquetes IP que lo identifiquen como tipo de tráfico determinado (por ejemplo, voz). Los enrutadores y otros dispositivos de red se pueden configurar para reconocerlo y colocar el tráfico en una cola separada de mayor prioridad.

Aunque este escenario es completamente válido, solo funcionará para clientes Windows unidos a un dominio. Los dispositivos que no sean clientes de Windows unidos a un dominio no se habilitarán para el etiquetado de DSCP. Clientes como Mac OS tienen etiquetas codificadas de forma inetiqueta y siempre etiquetarán el tráfico.

En el lado positivo, controlar el marcado de DSCP a través de GPO garantiza que todos los equipos unidos a un dominio reciban la misma configuración y que solo un administrador pueda administrarlos. Los clientes que pueden usar GPO se etiquetarán en el dispositivo de origen y, a continuación, los dispositivos de red configurados pueden reconocer la transmisión en tiempo real mediante el código de DSCP y darle una prioridad adecuada.

### <a name="best-practice"></a>Procedimientos recomendados

Si es posible, se recomienda una combinación de marcas DSCP en el punto de conexión y de direcciones ACL basadas en puertos en enrutadores. El uso de un GPO para capturar a la mayoría de los clientes y, además, el etiquetado de DSCP basado en puertos garantizará que los dispositivos móviles, Mac y otros clientes seguirán teniendo el tratamiento de QoS (al menos parcialmente).

Las marcas de DSCP se pueden parecer a marcas de envío que indican a los trabajadores postales lo urgente que es la entrega y la mejor manera de ordenarla para una entrega rápida. Una vez que haya configurado la red para dar prioridad a las transmisiones multimedia en tiempo real, los paquetes perdidos y los paquetes retrasados deberían disminuir considerablemente.

Una vez que todos los dispositivos de la red usan las mismas clasificaciones, marcados y prioridades, es posible reducir o eliminar los retrasos, los paquetes descartados y la vibración cambiando el tamaño de los intervalos de puertos asignados a las colas utilizadas para cada tipo de tráfico. Desde la perspectiva de Teams, el paso de configuración más importante es la clasificación y el marcado de paquetes. Sin embargo, para que qoS de un extremo a otro se pueda completar correctamente, también debe alinear cuidadosamente la configuración de la aplicación con la configuración de red subyacente. Una vez que QoS se haya implementado completamente, la administración continua es la necesidad de ajustar los intervalos de puertos asignados a cada tipo de tráfico en función de las necesidades de su organización y el uso real.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Elegir rangos de puertos iniciales para cada tipo de medio

El valor de DSCP indica a una red configurada correctamente qué prioridad asignar a un paquete o transmisión, si los clientes asignan la marca DSCP o la propia red en función de la configuración ACL. Cada carga de trabajo multimedia obtiene su propio valor de DSCP (es posible que otros servicios permitan que las cargas de trabajo compartan un marcado DSCP y Teams no) y un intervalo de puertos definido e independiente que se usa para cada tipo de medio. Es posible que en otros entornos haya una estrategia de QoS existente, que le ayudará a determinar la prioridad de las cargas de trabajo de red.

El tamaño relativo de los intervalos de puertos para las diferentes cargas de trabajo de streaming en tiempo real establece la proporción del ancho de banda total disponible dedicado a esa carga de trabajo. Para volver a nuestra analógica postal anterior: es posible que una carta con una marca "Air Mail" se reciba en una hora hasta el aeropuerto más cercano, mientras que un pequeño paquete marcado con la marca "Correo masivo" puede esperar un día antes de viajar por tierra en una serie de vuelos.

_Intervalos de puertos iniciales recomendados_

|Tipo de tráfico de medios | Rango de puertos de origen del cliente  |Protocolo|Valor de DSCP|Clase DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50 000 – 50 019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50 020 – 50 039|TCP/UDP|34|Desvío garantizado (AF41)|
|Aplicación/Compartir pantalla| 50 040 – 50 059|TCP/UDP|18|Desvío garantizado (AF21)|
||||||

Tenga en cuenta lo siguiente cuando use esta configuración:

- Si tiene previsto implementar ExpressRoute en el futuro y aún no ha implementado QoS, le recomendamos que siga las instrucciones para que los valores de DSCP sean los mismos del remitente al receptor.
- Todos los clientes, incluidos los clientes móviles y los dispositivos de Teams, usarán estos intervalos de puertos y se verán afectados por cualquier directiva de DSCP que implemente que use estos intervalos de puertos de origen. Los únicos clientes que seguirán usando puertos dinámicos son los clientes basados en explorador (clientes que permiten a los participantes unirse a las reuniones mediante sus exploradores).
- Aunque el cliente Mac usa los mismos intervalos de puertos, también usa valores codificados de forma inefi¿Para audio (EF) y vídeo (AF41). Estos valores no se pueden configurar.
- Si más adelante necesita ajustar los intervalos de puertos para mejorar la experiencia del usuario, los intervalos de puertos no se pueden superponer y deben ser adyacentes.

## <a name="migrate-qos-to-teams"></a>Migrar QoS a Teams

Si ya implementó anteriormente Skype Empresarial Online, incluidos los intervalos de puertos y etiquetado de QoS, y ahora se está implementando. Teams, teams respetará la configuración existente y utilizará los mismos intervalos de puertos y etiquetado que el cliente de Skype Empresarial. En la mayoría de los casos, no será necesaria ninguna configuración adicional.

> [!NOTE]
> Si usa el etiquetado de QoS del nombre de aplicación a través de la directiva de grupo, debe agregar una Teams.exe como el nombre de la aplicación.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementar QoS en Teams en Windows con PowerShell

**Establecer QoS para el audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Configurar QoS para el vídeo**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Configurar QoS para compartir**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Administrar puertos de origen en el Centro de administración de Teams

En Teams, los puertos de origen de QoS usados por las diferentes cargas de trabajo deben administrarse activamente y ajustarse según sea necesario. Haciendo referencia a la tabla en Elegir intervalos de [puertos](#choose-initial-port-ranges-for-each-media-type)iniciales para cada tipo de medio, los intervalos de puertos son ajustables, pero no se pueden configurar las marcas de DSCP. Una vez que haya implementado esta configuración, es posible que descubra que se necesitan más o menos puertos para un determinado tipo de medio. [El](use-call-analytics-to-troubleshoot-poor-call-quality.md) análisis de llamadas por usuario y el panel de calidad de llamadas [(CQD)](turning-on-and-using-call-quality-dashboard.md) deben usarse para tomar una decisión para ajustar los intervalos de puertos después de implementar Teams y, periódicamente, según cambien las necesidades.

> [!NOTE]
> Si ya configuró QoS en función de los intervalos de puerto de origen y las marcas DSCP de Skype Empresarial Online, se aplicará la misma configuración a Teams y no será necesario realizar más cambios en la asignación de clientes o redes, aunque puede que tenga que establecer los [intervalos](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) que se usan en Teams para que coincidan con lo configurado para Skype Empresarial Online.

Si ya ha implementado Skype Empresarial Server localmente, es posible que tenga que volver a examinar las directivas de QoS. Ajuste las directivas para que coincidan con las configuraciones de intervalo de puertos que haya comprobado que proporcionan una experiencia de usuario de calidad para Teams.

## <a name="validate-your-qos-implementation"></a>Validar la implementación de QoS

Para que QoS sea eficaz, el valor de DSCP establecido por el GPO debe estar presente en ambos extremos de una llamada. Analizando el tráfico generado por el cliente de Teams, puede comprobar que el valor de DSCP no cambia o se quita cuando el tráfico de carga de trabajo de Teams se desplaza por la red.

Preferiblemente, capture el tráfico en el punto de salida de la red. Puede usar la creación de reflejo de puertos en un conmutador o enrutador para ayudarle.

## <a name="implement-qos-for-other-devices"></a>Implementar QoS para otros dispositivos

Lea estos temas para obtener información sobre cómo implementar QoS para Intune, Surface, iOS, Android y Mac

- [QoS para Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [QoS para Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [QoS para iOS, Android y Mac](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Temas relacionados

- [Vídeo: Planeamiento de red](https://aka.ms/teams-networking)

- [Preparar la red de la organización para Microsoft Teams](prepare-network.md)

- [Implementar QoS en el cliente de Teams](QoS-in-Teams-clients.md)

---
title: Implementar Calidad de servicio en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Obtenga información sobre cómo preparar la red de su organización para la Calidad de servicio (QoS) en Microsoft Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: 6015c7b7cf1e7be5bc6b9b3e1fe0577a7f707377
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564148"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar la calidad de servicio (QoS) en Microsoft Teams

La calidad de servicio (QoS) en Microsoft Teams permite que el tráfico de red en tiempo real que sea sensible a los retrasos en la red (por ejemplo, las transmisiones de voz o vídeo) se "corte en línea" delante del tráfico que sea menos sensible (como descargar una nueva aplicación, donde descargar un segundo adicional no es importante). QoS usa objetos de Windows directiva de grupo y listas de Access Control basadas en puertos para identificar y marcar todos los paquetes en secuencias en tiempo real. Esto ayuda a la red a proporcionar a las secuencias de voz, vídeo y pantalla compartida una parte dedicada del ancho de banda de red.

Si es compatible con un gran grupo de usuarios que experimentan alguno de los problemas descritos en este artículo, es probable que necesite implementar QoS. Es posible que una pequeña empresa con pocos usuarios no necesite QoS, pero incluso ahí debería ser útil.

Sin alguna forma de QoS, es posible que vea los siguientes problemas de calidad en voz y vídeo:

- Vibración: paquetes multimedia que llegan a distintas velocidades, lo que puede provocar que falten palabras o sílabas en las llamadas.
- Pérdida de paquetes: paquetes descartados, lo que también puede resultar en una menor calidad de voz y voz difícil de entender
- Tiempo de ida y vuelta con retraso : los paquetes multimedia tardan mucho tiempo en llegar a sus destinos, lo que provoca retrasos perceptibles entre dos partes en una conversación y hace que las personas se hablen entre sí

La forma menos compleja de solucionar estos problemas es aumentar el tamaño de las conexiones de datos, tanto interna como internamente, a Internet. Dado que esto suele ser prohibitivo a menudo, QoS proporciona una forma de administrar de forma más eficaz los recursos que tiene en lugar de agregar ancho de banda. Para solucionar problemas de calidad, le recomendamos que primero use QoS y, después, agregue el ancho de banda solo cuando sea necesario.

Para que QoS sea eficaz, debe aplicar una configuración coherente de QoS en toda la organización. Cualquier parte de la ruta que no admita sus prioridades de QoS puede degradar la calidad de las llamadas, el vídeo y el uso compartido de la pantalla. Esto incluye aplicar la configuración a todos los equipos o dispositivos de usuario, conmutadores de red, enrutadores a Internet y el servicio de Teams.

_Figura 1. La relación entre las redes de una organización y los servicios de Microsoft 365 o Office 365_

![Ilustración de la relación entre redes y servicios.](media/Qos-in-Teams-Image1.png "La relación entre las redes de una organización y los servicios de Microsoft 365 o Office 365: la red local y los dispositivos se conectan con una red interconectada que, a su vez, se conecta con los servicios de Microsoft 365 o Office 365 Cloud Voice y Audioconferencia.")

## <a name="qos-implementation-checklist"></a>Lista de comprobación de implementación de QoS

A un nivel alto, haga lo siguiente para implementar QoS:

1. [Asegúrate de que la red esté lista](#make-sure-your-network-is-ready).

1. [Seleccione un método de implementación de QoS](#select-a-qos-implementation-method).

1. [Elija los intervalos de puertos iniciales para cada tipo de medio](#choose-initial-port-ranges-for-each-media-type).

1. Implementar la configuración de QoS:
   1. En clientes que usan un objeto de directiva de grupo (GPO) para [establecer intervalos de puertos de dispositivo de cliente y marcas](QoS-in-Teams-clients.md).
   2. En enrutadores (consulta la documentación del fabricante) u otros dispositivos de red. Esto puede incluir listas de Access Control basadas en puertos (ACL) o simplemente definir las colas de QoS y los marcados de DSCP, o todos ellos.

      > [!IMPORTANT]
      > Se recomienda implementar estas directivas de QoS mediante los puertos de origen del cliente y una dirección IP de origen y destino de "cualquiera". Esto detectará el tráfico multimedia entrante y saliente en la red interna.  

   3. [Establezca cómo desea controlar el tráfico multimedia de las reuniones de Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).

5. [Valide la implementación de QoS](#validate-your-qos-implementation) analizando el tráfico de Teams en la red.

A medida que se prepare para implementar QoS, tenga en cuenta las siguientes directrices:

- La ruta más corta a Microsoft 365 es la mejor.
- Cerrar los puertos solo provocará una degradación de la calidad.
- No se recomiendan obstáculos intermedios, como servidores proxy.
- Limitar el número de saltos:
  - Cliente al perímetro de la red: de 3 a 5 saltos
  - ISP al perímetro de la red de Microsoft: 3 saltos
  - Perímetro de red de Microsoft hasta el destino final: irrelevante

Para obtener información sobre la configuración de puertos de firewall, vaya a [Office 365 direcciones URL e intervalos IP](office-365-urls-ip-address-ranges.md).

## <a name="make-sure-your-network-is-ready"></a>Asegúrate de que la red esté lista

Si está pensando en una implementación de QoS, ya debería haber determinado los requisitos de ancho de banda y otros [requisitos de red](prepare-network.md).
  
La congestión del tráfico en toda la red afectará enormemente a la calidad de los medios. La falta de ancho de banda provoca una degradación del rendimiento y una mala experiencia del usuario. A medida que aumenta la adopción y el uso de Teams, use los informes, el [análisis de llamadas por usuario](use-call-analytics-to-troubleshoot-poor-call-quality.md) y el [Panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md) para identificar problemas y, a continuación, realizar ajustes con QoS y adiciones selectivas de ancho de banda.

### <a name="vpn-considerations"></a>Consideraciones sobre VPN

QoS solo funciona según lo esperado cuando se implementa en todos los vínculos entre los autores de llamadas. Si usa QoS en una red interna y un usuario inicia sesión desde una ubicación remota, solo puede establecer prioridades dentro de su red interna administrada. Aunque las ubicaciones remotas pueden recibir una conexión administrada mediante la implementación de una red privada virtual (VPN), una VPN agrega intrínsecamente una sobrecarga de paquetes y crea retrasos en el tráfico en tiempo real. Te recomendamos que evites ejecutar el tráfico de comunicaciones en tiempo real a través de una VPN.

En una organización global con vínculos administrados que abarcan continentes, recomendamos encarecidamente QoS porque el ancho de banda para esos vínculos está limitado en comparación con la LAN.

## <a name="introduction-to-qos-queues"></a>Introducción a las colas de QoS

Para proporcionar QoS, los dispositivos de red deben tener una forma de clasificar el tráfico y deben poder distinguir la voz o el vídeo de otro tráfico de red.

Cuando el tráfico de red entra en un router, el tráfico se coloca en una cola. Si no se configura una directiva de QoS, solo hay una cola y todos los datos se tratan como de primero en entrar y de salida con la misma prioridad. Esto significa que el tráfico de voz (que es muy sensible a los retrasos) podría quedarse atascado detrás del tráfico donde un retraso de unos pocos milisegundos adicionales no sería un problema.

Cuando implementa QoS, usted define las colas múltiples usando una de varias características de administración de la congestión, tales como la cola de prioridad de Cisco y la [cola justa ponderada basada en clases (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) y las características de evitar la congestión, como la [detección temprana aleatoria ponderada (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).

_Figura 2. Ejemplos de colas de QoS_

![Ilustración de colas de QoS y división de ancho de banda.](media/Qos-in-Teams-Image2.png "El ancho de banda total disponible se divide entre varias colas (audio, vídeo y otro tráfico) a las que se han asignado diferentes prioridades.")

Una analogía sencilla es que QoS crea "carriles de uso compartido del automóvil" virtual en la red de datos para que algunos tipos de datos nunca o rara vez encuentren un retraso. Una vez creados esos carriles, puede ajustar su tamaño relativo y administrar de forma mucho más eficaz el ancho de banda de conexión que tiene, a la vez que ofrece experiencias de nivel empresarial para los usuarios de su organización.

## <a name="select-a-qos-implementation-method"></a>Seleccionar un método de implementación de QoS

Puede implementar QoS mediante etiquetado basado en puertos, mediante listas de Access Control (ACL) en los enrutadores de su red. El etiquetado basado en puertos es el método más confiable porque funciona en entornos mixtos de Windows, Mac y Linux y es el más fácil de implementar. Los clientes móviles no proporcionan un mecanismo para marcar el tráfico mediante valores DSCP, por lo que necesitarán este método.  

Con etiquetado basado en puertos, el enrutador de su red examina un paquete entrante y, si el paquete llegó con un determinado puerto o rango de puertos, lo identifica como un determinado tipo de medio y lo coloca en la cola para ese tipo, agregando una marca [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada al encabezado de paquete IP para que otros dispositivos puedan reconocer su tipo de tráfico y asignarle prioridad en su cola.

Aunque el etiquetado basado en puertos funciona entre plataformas, solo marca el tráfico en el borde WAN (no hasta el equipo cliente) y crea una sobrecarga de administración. Consulte la documentación proporcionada por el fabricante del router para obtener instrucciones sobre cómo implementar este método.

### <a name="insert-dscp-markers"></a>Insertar marcadores DSCP

También puede implementar QoS mediante un objeto de directiva de grupo (GPO) para dirigir a los dispositivos cliente para que inserten un marcador DSCP en encabezados de paquetes IP que lo identifiquen como un tipo determinado de tráfico (por ejemplo, voz). Los enrutadores y otros dispositivos de red se pueden configurar para reconocerlo y colocar el tráfico en una cola separada de prioridad más alta.

Aunque este escenario es totalmente válido, solo funcionará para los clientes Windows unidos a un dominio. Cualquier dispositivo que no sea un cliente de Windows unido a un dominio no se habilitará para el etiquetado de DSCP. Otros clientes, como los que ejecutan macOS, tienen etiquetas codificadas de forma hard y siempre etiquetarán el tráfico.

En el lado más, controlar el marcado de DSCP a través de GPO garantiza que todos los equipos unidos a un dominio reciban la misma configuración y que solo un administrador pueda administrarlas. Los clientes que pueden usar GPO se etiquetarán en el dispositivo de origen y, después, los dispositivos de red configurados podrán reconocer la transmisión en tiempo real mediante el código DSCP y asignarle una prioridad adecuada.

### <a name="best-practice"></a>Procedimiento recomendado

Recomendamos, si es posible, una combinación de marcas dscp en el extremo y ACL basadas en puertos en enrutadores. Usar un GPO para capturar la mayoría de los clientes y también usar etiquetado DSCP basado en puertos garantizará que los clientes móviles, Mac y otros clientes seguirán recibiendo tratamiento de QoS (al menos parcialmente).

Las marcas dscp pueden ser similares a sellos postales que indican a los trabajadores postales lo urgente que es la entrega y cuál es la mejor manera de ordenarla para una entrega rápida. Una vez que haya configurado la red para dar prioridad a las transmisiones multimedia en tiempo real, los paquetes perdidos y los paquetes tardíos deberían disminuir considerablemente.

Una vez que todos los dispositivos de la red usan las mismas clasificaciones, marcas y prioridades, es posible reducir o eliminar los retrasos, los paquetes perdidos y la vibración cambiando el tamaño de los intervalos de puertos asignados a las colas que se usan para cada tipo de tráfico. Desde el punto de vista de Teams, el paso de configuración más importante es la clasificación y el marcado de paquetes. Sin embargo, para que QoS de un extremo a otro sea correcto, también debe alinear cuidadosamente la configuración de la aplicación con la configuración de red subyacente. Una vez que QoS se implementa por completo, la administración continua es una cuestión de ajustar los intervalos de puertos asignados a cada tipo de tráfico en función de las necesidades de su organización y el uso real.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Elegir intervalos de puertos iniciales para cada tipo de medio

El valor de DSCP indica a una red configurada de forma correspondiente qué prioridad dar a un paquete o flujo, si los clientes o la propia red asignan la marca DSCP en función de la configuración acl. Cada carga de trabajo multimedia obtiene su propio valor único de DSCP (otros servicios podrían permitir que las cargas de trabajo compartan un marcado de DSCP, Teams no lo hace) y un intervalo de puertos definido e independiente que se usa para cada tipo de medio. Otros entornos podrían tener una estrategia de QoS existente, que le ayudará a determinar la prioridad de las cargas de trabajo de red.

El tamaño relativo de los intervalos de puertos para distintas cargas de trabajo de streaming en tiempo real establece la proporción del ancho de banda total disponible dedicado a esa carga de trabajo. Para volver a nuestra analogía postal anterior: una carta con un sello de "Correo aéreo" podría llevarse en una hora al aeropuerto más cercano, mientras que un pequeño paquete marcado con la marca "Correo masivo" puede esperar un día antes de viajar por tierra en una serie de camiones.

_Intervalos de puertos iniciales recomendados_

|Tipo de tráfico de medios | Rango de puertos de origen del cliente  |Protocolo|Valor de DSCP|Clase DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50 000 – 50 019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50 020 – 50 039|TCP/UDP|34|Desvío garantizado (AF41)|
|Aplicación/Compartir pantalla| 50 040 – 50 059|TCP/UDP|18|Desvío garantizado (AF21)|
||||||

Tenga en cuenta lo siguiente al usar esta configuración:

- Si tiene previsto implementar ExpressRoute en el futuro y aún no ha implementado QoS, le recomendamos que siga las instrucciones para que los valores DSCP sean los mismos de remitente a receptor.

- Todos los clientes, incluidos los clientes móviles y los dispositivos de Teams, usarán estos intervalos de puertos y se verán afectados por cualquier directiva de DSCP que implemente que use estos intervalos de puertos de origen. Los únicos clientes que seguirán usando puertos dinámicos son los clientes basados en exploradores (clientes que permiten a los participantes unirse a reuniones mediante sus exploradores).

- Aunque el cliente de Mac usa los mismos intervalos de puertos, también usa valores codificados de forma rígida para audio (EF) y vídeo (AF41). Estos valores no se pueden configurar.

- Si más adelante necesita ajustar los intervalos de puertos para mejorar la experiencia del usuario, los intervalos de puertos no se pueden superponer y deben ser adyacentes entre sí.

## <a name="migrate-qos-to-teams"></a>Migrar QoS a Teams

Si ya ha implementado anteriormente Skype Empresarial Online, incluidos los intervalos de puertos y etiquetado de QoS, y ahora lo está implementando. Teams, Teams respetará la configuración existente y usará los mismos intervalos de puertos y etiquetado que el cliente de Skype Empresarial. En la mayoría de los casos, no se necesitará ninguna configuración adicional.

> [!NOTE]
> Si usa el etiquetado de QoS de nombre de aplicación a través de directiva de grupo, debe agregar Teams.exe como el nombre de la aplicación.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementar QoS en Teams en Windows con PowerShell

**Establecer QoS para audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Establecer QoS para vídeo**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Establecer QoS para compartir**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Administrar puertos de origen en el Centro de administración de Teams

En Teams, los puertos de origen de QoS que usan las distintas cargas de trabajo deben administrarse activamente y ajustarse según sea necesario. Haciendo referencia a la tabla en [Elegir intervalos de puertos iniciales para cada tipo de medio](#choose-initial-port-ranges-for-each-media-type), los intervalos de puertos son ajustables, pero las marcas de DSCP no se pueden configurar. Una vez que haya implementado esta configuración, es posible que descubra que se necesitan más o menos puertos para un determinado tipo de medio. [El análisis de llamadas por usuario](use-call-analytics-to-troubleshoot-poor-call-quality.md) y el [panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md) deben usarse para tomar una decisión para ajustar los intervalos de puertos después de implementar Teams y, periódicamente, a medida que cambian las necesidades.

> [!NOTE]
> Si ya ha configurado QoS en función de los intervalos de puertos de origen y las marcas de DSCP para Skype Empresarial Online, la misma configuración se aplicará a Teams y no será necesario realizar ningún cambio en la asignación de red o en el cliente, aunque es posible que tenga que [establecer los intervalos que se usan en Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) para que coincidan con lo que se configuró para Skype Empresarial Online.

Si ya ha implementado anteriormente Skype Empresarial Server local, es posible que deba volver a examinar las directivas de QoS. Ajuste las directivas para que coincidan con la configuración del intervalo de puertos que ha comprobado para proporcionar una experiencia de usuario de calidad para Teams.

## <a name="validate-your-qos-implementation"></a>Validar la implementación de QoS

Para que QoS sea eficaz, el valor de DSCP establecido por el GPO debe estar presente en los dos extremos de una llamada. Al analizar el tráfico generado por el cliente de Teams, puede comprobar que el valor de DSCP no se cambia ni se quita cuando el tráfico de carga de trabajo de Teams se mueve a través de la red.

Preferiblemente, se captura el tráfico en el punto de salida de la red. Puedes usar la creación de reflejo de puertos en un conmutador o enrutador para ayudar con esto.

## <a name="implement-qos-for-other-devices"></a>Implementar QoS para otros dispositivos

Lea estos temas para obtener información sobre cómo implementar QoS para Intune, Surface, iOS, Android y Mac.

- [QoS para Surface Hub 2S](/surface-hub/surface-hub-2s-manage-intune)

- [QoS para Surface Hub](/surface-hub/surface-hub-qos)

- [QoS para iOS, Android y Mac](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Temas relacionados

- [Vídeo: Planeamiento de red](https://aka.ms/teams-networking)

- [Preparar la red de la organización para Microsoft Teams](prepare-network.md)

- [Implementar QoS en el cliente de Teams](QoS-in-Teams-clients.md)
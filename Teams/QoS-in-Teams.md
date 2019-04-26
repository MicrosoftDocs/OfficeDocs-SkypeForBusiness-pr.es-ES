---
title: Implementar Calidad de servicio en Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Prepare la red de su organización para la calidad de servicio (QoS) en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.qos
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f1df731f7ff21d246f9b92e028fe3e7ae367509
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304424"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar la calidad de servicio (QoS) en los equipos de Microsoft

En este artículo le ayudará a preparar la red de su organización para calidad de servicio (QoS) en Microsoft Teams. Si dispone de un grupo grande de usuarios y se experimentar con alguno de los problemas que se mencionan a continuación, probablemente necesite implementar QoS. Una empresa pequeña con pocos usuarios que no sea necesario QoS, pero existe incluso debe ser útil.

QoS es una forma para permitir el tráfico de red en tiempo real (por ejemplo, secuencias de voz o vídeo) que es sensible a retrasos en la red "recortar en línea" delante del tráfico que es menos sensible (al igual que la descarga de una aplicación nueva, donde un segundo adicional para descargar no es muy importante). QoS identifica y marca todos los paquetes en secuencias en tiempo real (mediante objetos de directiva de grupo de Windows y una característica de enrutamiento denominada basado en el puerto Access Control Lists, más información acerca los es inferior a) que, a continuación, ayuda a la red para proporcionar la voz, vídeo y secuencias de recurso compartido de pantalla un parte dedicada de ancho de banda de red.

Sin algún tipo de QoS, es posible que vea los siguientes problemas de calidad de voz y vídeo:

- Vibración – paquetes de medios que llegan a diferentes velocidades, lo que pueden provocar que faltan palabras o sílabas en las llamadas.
- Pérdida de paquetes – paquetes descartados, lo que también puede provocar menor calidad de voz y disco duro para comprender la voz.
- Retrasa el tiempo de ida y vuelta (RTT) – los paquetes multimedia tarda mucho tiempo para llegar a sus destinos, que da como resultado retrasos notables entre dos partes en una conversación, lo que provoca que las personas a hablar a través de los otros.

La forma menos compleja para solucionar estos problemas es aumentar el tamaño de las conexiones de datos, tanto internamente y de salida a internet. Ya que a menudo es costo sumamente elevado, QoS proporciona una forma de administrar los recursos que posee en lugar de agregar nuevos recursos de forma más eficaz. Para resolver totalmente los problemas de calidad sería utilizar QoS en la implementación y luego agregar conectividad sólo cuando sea absolutamente necesario.

Para que QoS ser eficaces, debe aplicar la configuración de QoS coherente a fin de la organización (que incluye todos los equipos de usuario, conmutadores de red y los enrutadores a internet), porque puede afectar negativamente al cualquier parte de la ruta de acceso que se produce un error para admitir sus prioridades QoS el calidad de las llamadas, vídeo y recursos compartidos de la pantalla.

_En la figura 1. La relación entre una organización redes y servicios de Office 365_

![La relación entre una organización redes y servicios de Office 365: local de red y dispositivos que se conectan con una red de interconexión, lo que a su vez se conecta con los servicios de voz de Office 365 en la nube y conferencias de Audio.](media/Qos-in-Teams-Image1.png)

En la mayoría de los casos, la red conectar su empresa a la nube será una red no administrada donde no podrá establecer las opciones de QoS de forma confiable. Una opción disponible para QoS to-end de direcciones es [ExpressRoute de Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/), pero aún se recomienda que implemente QoS en la red local. Esto aumentará la calidad de las cargas de trabajo de comunicación en tiempo real en toda la implementación y mitigar los puntos de restricción.

## <a name="verify-your-network-is-ready"></a>Compruebe que la red está preparada

Si está pensando en una implementación de QoS, debe ya ha determinado los requisitos de ancho de banda y otros [requisitos de red](prepare-network.md). Los cálculos de ancho de banda para Microsoft Teams son complejos y para ayudar a con esto, se ha creado una calculadora. Para obtener acceso a la Calculadora, vaya al [Organizador de la red](https://aka.ms/bwcalc/) en MyAdvisor.
  
  Congestión del tráfico a través de una red tendrá un impacto en gran medida calidad de los medios. Falta de ancho de banda tiene las siguientes consecuencias degradación del rendimiento y una experiencia de usuario deficiente. A medida que crece el uso y la adopción de los equipos, use de informes, [análisis de llamadas y llamar al panel de calidad](difference-between-call-analytics-and-call-quality-dashboard.md) para identificar posibles problemas y, a continuación, realice ajustes con QoS y adiciones de ancho de banda selectiva.

### <a name="vpn-considerations"></a>Consideraciones de VPN

QoS sólo funciona según lo esperado cuando se implementa en todos los vínculos entre los autores de llamadas. Si utiliza QoS en una red interna y un usuario inicia sesión desde una ubicación remota, sólo puede dar prioridad a dentro de la red interna, administrada. Aunque las ubicaciones remotas pueden recibir una conexión administrada mediante la implementación de una red privada virtual (VPN), una red privada virtual inherente agrega sobrecarga de paquetes y crea los retrasos en el tráfico en tiempo real. Se recomienda que evite la ejecución de tráfico de comunicaciones en tiempo real a través de una red privada virtual.

> [!NOTE]
> Los usuarios remotos conectados por VPN deben implementar túnel dividido para maximizar la calidad de la experiencia del usuario. El documento [Deploy de orientación-VPN dividido túnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) está disponible desde MyAdvisor y dispone de más información.

En una organización global con vínculos administradas que abarcan continentes, se recomienda encarecidamente QoS debido a que el ancho de banda para esos vínculos es limitado en comparación con la LAN.

## <a name="introduction-to-qos-queues"></a>Introducción a las colas de QoS

Para proporcionar QoS, dispositivos de red deben tener una forma de clasificar el tráfico y deben ser capaz de distinguir de voz o vídeo desde otro tráfico de red.

Cuando el tráfico de red entra en un enrutador, el tráfico se coloca en una cola. Si no se ha configurado una directiva de QoS, hay sólo una cola, y todos los datos se tratan como, primero en salir con la misma prioridad. Esto significa que el tráfico de voz (que es muy sensible a los retrasos) es posible que se bloquee detrás de tráfico donde un retraso de unos milisegundos adicionales sería un problema.

Cuando se implementan QoS, definir varias colas con uno de varias características de administración de congestión (por ejemplo, de Cisco colas de prioridad y basada en la clase promedio ponderado razonable Queueing [CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)) y las características de prevención de congestión (como pronto ponderado aleatorio detección de [WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)).

_La figura 2. Ejemplos de colas de QoS_

![El ancho de banda disponible total se divide entre varias colas: audio, vídeo y otro tipo de tráfico, que se han asignado prioridades diferentes.] (media/Qos-in-Teams-Image2.png "El ancho de banda disponible total se divide entre varias colas: audio, vídeo y otro tipo de tráfico, que se han asignado prioridades diferentes.")

Una simple analogía es que QoS crea virtual "pistas de automóviles de uso compartido" en los datos de la red para algunos tipos de datos nunca o con muy poca frecuencia encontrar un retraso. Una vez crear esos calles, puede ajustar su tamaño relativo y administrar de forma mucho más eficaz el ancho de banda de conexión que tiene, al tiempo que ofrecen experiencias profesional para los usuarios de su organización.

## <a name="select-a-qos-implementation-method"></a>Seleccione un método de implementación de QoS

Podría implementar QoS a través de basado en el puerto etiquetado, uso de listas de Control de acceso (ACL) en los enrutadores de su red. Basado en el puerto etiquetado es el método más confiable porque funciona en entornos mixtos de Windows y Mac y es más fácil de implementar. Los clientes móviles no proporcionan un mecanismo para marcar el tráfico mediante el uso de los valores DSCP, por lo que requieren este método.  

Con este método, enrutador de su red examina un paquete entrante, y si el paquete ha llegado con un puerto o un intervalo de puertos determinados, identifica como un tipo de medios determinado y lo coloca en la cola para ese tipo, agregar una marca de [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada a la dirección IP Encabezado de paquetes para que pueden reconocer su tipo de tráfico y dar prioridad en su cola de otros dispositivos.

Aunque esto funciona a través de plataformas, sólo marca el tráfico en el borde WAN (no hasta el equipo cliente) y crea la sobrecarga de administración. Se debe hacer referencia a la documentación proporcionada por el fabricante del enrutador para obtener instrucciones sobre la implementación de este método.

* * *

También podría implementar implementada mediante el uso de un objeto de directiva de grupo (GPO) para dirigir los dispositivos de cliente de QoS para insertar un marcador DSCP en encabezados de paquetes IP que lo identifique como un tipo concreto de tráfico (por ejemplo, voz). Enrutadores y otros dispositivos de red pueden configurarse para que reconozca esto y colocar el tráfico en una cola independiente, una mayor prioridad.

Aunque este escenario es totalmente válido, sólo funciona para los clientes Unidos a un dominio de Windows. Cualquier dispositivo que no es un cliente de Windows unido a un dominio no estará activado para DSCP etiquetado. Los clientes como Mac OS tienen etiquetas codificado de forma rígida y siempre va a marcar el tráfico.

En el signo más lado, controlar el marcado a través de GPO de DSCP se asegura de que todos los equipos unidos a un dominio reciben la misma configuración y que sólo un administrador puede administrarlos. Los clientes que pueden usar GPO se etiquetará en el dispositivo de origen y, a continuación, los dispositivos de red configuradas pueden reconocer la secuencia en tiempo real por el código DSCP y asignarle una prioridad adecuado.

* * *

Se recomienda una combinación de marcado de DSCP en el extremo y las ACL basadas en puerto en los enrutadores, si es posible. Uso de un objeto de directiva de grupo para detectar la mayoría de los clientes y también usando un etiquetado de DSCP de puerto-based asegurará que mobile, Mac y otros clientes seguirán recibiendo tratamiento de QoS (por lo menos parcialmente).

Marcados de DSCP pueden asemejarse a las marcas de franqueo que indican a los trabajadores postales cómo urgentes es la entrega y la mejor manera de ordenar para la entrega rápida. Una vez que haya configurado la red para dar prioridad a las secuencias multimedia en tiempo real, pérdida de paquetes y las últimas paquetes deben disminuir considerablemente.

Una vez que todos los dispositivos en la red usan el mismo clasificaciones, marcas y prioridades, es posible reducir o eliminar los retrasos, paquetes descartados y vibración cambiando el tamaño de los intervalos de puerto asignado a las colas que se usa para cada tipo de tráfico. Desde la perspectiva de los equipos, el paso de configuración más importante es la clasificación y el marcado de paquetes, pero para que QoS to-end a realizarse correctamente también necesita alinear cuidadosamente la configuración de la aplicación con la configuración de red subyacente. Una vez que se ha implementado completamente QoS, administración continuada es una pregunta de ajuste de los intervalos de puertos asignados a cada tipo de tráfico según las necesidades de su organización y el uso real.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Elija los intervalos de puertos inicial para cada tipo de medio

El valor de DSCP indica que una red configurada en consecuencia a qué prioridad para proporcionar un paquete o una secuencia, si la marca de DSCP se asigna por los clientes o la red basándose en la configuración de la ACL. Cada carga de trabajo de medios obtiene su propio valor DSCP único (otros servicios podrían permitir las cargas de trabajo compartir el marcado DSCP, los equipos no lo hace) y un intervalo de puertos definido e independiente utilizado para cada tipo de medio. Otros entornos podrían tener una estrategia de QoS existente en su lugar, que le ayudarán a determinar la prioridad de las cargas de trabajo de la red.

El tamaño relativo de los intervalos de puertos para diferentes cargas de trabajo de transmisión por secuencias en tiempo real establece la proporción del ancho de banda disponible total dedicada para esa carga de trabajo. Para volver a nuestra analogía postal anteriormente: una letra con una marca de "Correo aire" obtener es posible que realizada dentro de una hora para el aeropuerto más cercano, mientras que un paquete pequeño marcados "Correo masivo" marca puede esperar a que un día antes de viaje a través de tierra en una serie de camiones.

La siguiente tabla muestran las marcas DSCP necesarias para los equipos con ExpressRoute y los puertos asociados para las colas de carga de trabajo. Estos intervalos pueden servir como un buen punto de partida para los clientes que no están seguro de qué se va a utilizar en sus propios entornos. Para obtener más información, lea [Requisitos de QoS ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Se recomienda intervalos de puertos inicial_

|Tipo de tráfico de medios| Intervalo de puertos de origen de cliente |Protocolo|Valor de DSCP|Clase de DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000 – 50,019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50,020 – 50,039|TCP/UDP|34|Desvío garantizado (AF41)|
|Uso compartido de aplicaciones o pantalla| 50,040 – 50,059|TCP/UDP|18|Reenvío (AF21) asegurado|
||||||

Tenga en cuenta lo siguiente cuando se usa esta configuración:

- Si piensa implementar ExpressRoute en el futuro y aún no ha implementado QoS, se recomienda que siga las instrucciones para que los valores DSCP son los mismos del remitente al receptor.
- Todos los clientes, incluidos los clientes móviles y dispositivos de los equipos, va a usar estos intervalos de puertos y se verán afectados por implementar cualquier directiva DSCP que usa estos intervalos de puerto de origen. Los únicos clientes que seguirán usando puertos dinámicos son los clientes basados en explorador (es decir, los clientes que permiten que los participantes unirse a reuniones mediante sus exploradores).
- Aunque el cliente de Mac usa los mismos intervalos de puertos, también usa valores codificado de forma rígida para (EF) de audio y vídeo (AF41). Estos valores no son configurables.
- Si más adelante necesita ajustar los intervalos de puertos para mejorar la experiencia del usuario, los intervalos de puertos no se pueden superponer y deben ser adyacentes entre sí.

## <a name="migrate-qos-to-teams"></a>Migración de QoS para equipos

Si se ha implementado anteriormente Skype para profesionales en línea, incluidos QoS etiquetado y los intervalos de puertos y ahora la implementación de los equipos, los equipos respetarán la configuración existente y va a usar el mismo intervalos de puertos y etiquetado como el Skype para clientes empresariales. En la mayoría de los casos, no se necesitarán ninguna configuración adicional.

> [!NOTE]
> Si utiliza QoS de nombre de aplicación de etiquetas temáticas a través de directiva de grupo, debe agregar Teams.exe como el nombre de la aplicación.

## <a name="qos-implementation-steps"></a>Pasos de implementación de QoS

En un nivel muy alto, la implementación de QoS requiere estos pasos:

1. [Compruebe que la red está preparada](#verify-your-network-is-ready)
2. [Seleccione un método de implementación de QoS](#select-a-qos-implementation-method)
3. [Elija los intervalos de puertos inicial para cada tipo de medio](#choose-initial-port-ranges-for-each-media-type)
4. Implementar la configuración de QoS:
   1. En los clientes utilizando un GPO para [establecer los intervalos de puertos del dispositivo de cliente y marcas](QoS-in-Teams-clients.md)
   2. En los enrutadores (vea la documentación del fabricante) u otros dispositivos de red. Esto puede incluir las ACL basadas en puerto o simplemente defina las colas de QoS y marcados de DSCP o todos ellos.

      > [!IMPORTANT]
      > Se recomienda implementar estas directivas de QoS con los puertos de origen del cliente y una dirección IP de origen y de destino de "cualquiera". Esta forma detectará tanto el tráfico de medios entrantes y salientes en la red interna.  

   3. En el [Centro de administración de equipos](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)
5. [Validar la implementación de QoS](#validate-the-qos-implementation) mediante el análisis de tráfico de los equipos de la red.

Preparación para implementar QoS, tenga en cuenta las siguientes instrucciones:

- La ruta de acceso más corta a Office 365 es mejor.
- Cierre de los puertos sólo llevará a degradación de la calidad.
- Cualquier obstáculo intermedias, como los servidores proxy, no se recomienda.
- Limitar el número de saltos de:
  - Cliente de perímetro de red – saltos de 3 a 5.
  - ISP para el perímetro de red de Microsoft – 3 saltos
  - Perímetro de red de Microsoft a un destino final – irrelevante

Para obtener información acerca de cómo configurar los puertos de firewall, vaya a [las direcciones URL de Office 365 e intervalos IP](office-365-urls-ip-address-ranges.md).

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Administración de puertos de origen en el centro de administración de equipos

En los equipos, los puertos de origen de QoS usados por las diferentes cargas de trabajo deberían estar activamente administrado y ajustan según sea necesario. Hacer referencia a la tabla en [intervalos de puertos y marcados de DSCP](#port-ranges-and-dscp-markings), los intervalos de puertos están ajustables, pero las marcas DSCP no son configurables. Una vez que ha implementado estas configuraciones, es posible que encuentre que más o menos los puertos necesarios para un tipo de medio determinado. [Análisis de llamadas y panel de calidad de llamada](difference-between-call-analytics-and-call-quality-dashboard.md) debe usarse en tomar una decisión para ajustar los intervalos de puertos después de que los equipos se ha implementado y periódicamente conforme cambian las necesidades.

> [!NOTE]
> Si ya ha configurado QoS en función de los intervalos de puertos de origen y de marcado de DSCP de Skype para profesionales en línea, se aplicará la misma configuración a los equipos y ninguna otra cliente o cambios en la red para la asignación se requerirán, aunque es posible que haya a [establecido los intervalos usado en el centro de administración de equipos de](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) para que coincida con lo que se configuró para Skype para profesionales en línea.

Si ha implementado anteriormente Skype para Business Server local, es posible que necesite volver a examinar las directivas de QoS y que los ajuste según sea necesario para que coincida con la configuración de intervalo de puertos que haya comprobado que proporcionan una experiencia de usuario de calidad para los equipos.

## <a name="validate-the-qos-implementation"></a>Validar la implementación de QoS

Para QoS para ser eficaces, el valor de DSCP de valor conjunto por el objeto de directiva de grupo debe estar presente en ambos extremos de una llamada. Al analizar el tráfico generado por el cliente de los equipos, puede comprobar que el valor de DSCP no está cambiado o se eliminan cuando el tráfico de carga de trabajo de los equipos recorre los movimientos a través de la red.

Preferiblemente, capturar el tráfico en el punto de salida de la red. Puede utilizar la duplicación de puertos en un conmutador o enrutador para ayudar con esto.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Utilice el Monitor de red para comprobar los valores DSCP

Monitor de red es una herramienta que se puede [descargar de Microsoft](https://www.microsoft.com/download/4865) para analizar el tráfico de red.

1. En el PC que ejecuta el Monitor de red, conecte con el puerto en el que se ha configurado para la creación de reflejo de puerto y capturar paquetes de inicio.

2. Realizar una llamada mediante el cliente de los equipos. Asegúrese de que se ha establecido medios antes de colgar la llamada.

3. Detenga la captura.

4. En el campo de **Filtro de presentación** , utilice la dirección IP de origen del PC que realizó la llamada y refinar el filtro mediante la definición de valor DSCP 46 (hex 0xb8) como criterios de búsqueda, como se muestra en el ejemplo siguiente:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8

    ![Captura de pantalla del cuadro de diálogo Filtro de visualización en el Monitor de red, que muestra los filtros que se debe aplicar.] (media/Qos-in-Teams-Image4.png "Captura de pantalla del cuadro de diálogo Filtro de visualización en el Monitor de red, que muestra los filtros que se debe aplicar.")

5. Seleccione **Aplicar** para activar el filtro.

6. En la ventana de **Marco de resumen** , seleccione el primer paquete de UDP.

7. En la ventana de **Marco de detalles** , expanda el elemento de lista IPv4 y tenga en cuenta el valor al final de la línea que comienza con **DSCP**.

    ![Captura de pantalla del cuadro de diálogo Detalles de las tramas en el Monitor de red, el resaltado de configuración DSCP.] (media/Qos-in-Teams-Image5.png "Captura de pantalla del cuadro de diálogo Detalles de las tramas en el Monitor de red, el resaltado de configuración DSCP.")

En este ejemplo, se establece el valor de DSCP a 46. Esto es correcto, debido a que el puerto de origen usado es 50019, lo que indica que se trata de una carga de trabajo de voz.

Repita la verificación para cada carga de trabajo que marque el GPO.

## <a name="more-information"></a>Más información

[Vídeo: Planeación de red](https://aka.ms/teams-networking)

[Preparar la red de la organización para Microsoft Teams](prepare-network.md)

[Requisitos de ExpressRoute QoS](https://docs.microsoft.com/azure/expressroute/expressroute-qos)

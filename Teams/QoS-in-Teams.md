---
title: Implementar Calidad de servicio en Microsoft Teams
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 972b997a7258ce4961fe4f94af37595846aac19b
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548887"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar calidad de servicio (QoS) en Microsoft Teams

Este artículo le ayudará a preparar la red de su organización de calidad de servicio (QoS) en Microsoft Teams. Si está dando soporte técnico a un grupo grande de usuarios y experimenta alguno de los problemas que se mencionan a continuación, probablemente necesite implementar QoS. Es posible que una pequeña empresa con pocos usuarios no necesite QoS, pero incluso allí debería ser útil.

QoS es una forma de permitir el tráfico de red en tiempo real (como las transmisiones de voz o vídeo) que es sensible a los retrasos de la red para "cortar en línea" frente al tráfico menos sensible (como descargar una nueva aplicación, donde un extra adicional para descargar no es una gran oferta). QoS identifica y marca todos los paquetes en las transmisiones en tiempo real (mediante los objetos de directiva de grupo de Windows y una característica de enrutamiento denominada listas de control de acceso basado en puertos, más información sobre los siguientes), que ayuda a la red a proporcionar transmisiones de voz, vídeo y compartir la pantalla a parte dedicada del ancho de banda de la red.

Sin alguna forma de QoS, es posible que vea los siguientes problemas de calidad en la voz y el vídeo:

- Vibración: paquetes multimedia que llegan a tarifas diferentes, lo que puede provocar que falten palabras o sílabas en las llamadas.
- Pérdida de paquetes: paquetes descartados, que también pueden dar lugar a una menor calidad de voz y difíciles de comprender.
- Tiempo de ida y vuelta retrasada (RTT): los paquetes multimedia tardan mucho en llegar a sus destinos, lo que produce retrasos evidentes entre dos partes en una conversación, lo que provoca que las personas se comuniquen entre sí.

La manera menos compleja de solucionar estos problemas es aumentar el tamaño de las conexiones de datos, tanto internamente como fuera de Internet. Como esto suele ser prohibitiva, QoS proporciona una forma más eficaz de administrar los recursos que tiene en lugar de agregar nuevos recursos. Para solucionar problemas de calidad completa, debería usar QoS en la implementación y, a continuación, agregar conectividad solo cuando sea absolutamente necesario.

Para que QoS sea efectivo, tendrá que aplicar la configuración coherente de QoS de principio a fin en su organización (esto incluye a todos los equipos de usuario, conmutadores de red y routers a Internet), porque cualquier parte de la ruta de acceso que no admita las prioridades de QoS puede degradar el calidad de las llamadas, video y pantalla compartida.

_Ilustración 1. La relación entre las redes de una organización y los servicios de Office 365_

![Ilustración de la relación entre redes y servicios] (media/Qos-in-Teams-Image1.png "Relación entre las redes de una organización y los servicios de Office 365: red local y dispositivos Conéctese a una red de interconexión que, a su vez, se conecta con los servicios de conferencia de nube y voz de nube de Office 365.")

En la mayoría de los casos, la red que conecta su empresa con la nube será una red no administrada, en la que no podrá establecer opciones de QoS de manera fiable. Una opción disponible para tratar QoS de extremo a extremo es [Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/), pero le recomendamos que implemente QoS en su red local. Esto incrementará la calidad de las cargas de trabajo de comunicación en tiempo real en toda la implementación y aliviará chokepoints.

## <a name="verify-your-network-is-ready"></a>Comprobar que su red está lista

Si está pensando en una implementación de QoS, ya debe haber determinado cuáles son los requisitos de ancho de banda y otros [requisitos de red](prepare-network.md). Los cálculos de ancho de banda para Microsoft Teams son complejos y para ayudarlo, se ha creado una calculadora. Para obtener acceso a la calculadora, vaya a planificador de [red](https://aka.ms/bwcalc/) en mi Asesor.
  
  La gestión del tráfico en toda la red afectará enormemente la calidad de los medios. La falta de ancho de banda conlleva la degradación del rendimiento y una mala experiencia del usuario. A medida que aumentan la adopción y el uso de equipos, use los informes, [análisis de llamadas y panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md) para identificar los problemas y, después, realice ajustes con QoS y adiciones selectivas de ancho de banda.

### <a name="vpn-considerations"></a>Consideraciones sobre VPN

QoS solo funciona como se espera cuando se implementa en todos los vínculos entre las personas que llaman. Si usa QoS en una red interna y un usuario inicia sesión desde una ubicación remota, solo puede priorizar en su red administrada interna. Aunque las ubicaciones remotas pueden recibir una conexión administrada al implementar una red privada virtual (VPN), una VPN agrega de forma inherente sobrecarga de paquetes y crea retrasos en el tráfico en tiempo real. Le recomendamos que evite ejecutar tráfico de comunicaciones en tiempo real a través de una VPN.

> [!NOTE]
> Los usuarios remotos conectados por VPN deben implementar túneles divididos para maximizar la calidad de la experiencia del usuario. El [túnel de implementación de documentos-guía-túnel dividido de VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) está disponible en mi Asesor y tiene más información.

En una organización internacional con vínculos administrados que abarcan continentes, recomendamos encarecidamente QoS porque el ancho de banda de esos vínculos está limitado en comparación con la LAN.

## <a name="introduction-to-qos-queues"></a>Introducción a las colas de QoS

Para proporcionar QoS, los dispositivos de red deben tener una forma de clasificar el tráfico y deben poder diferenciar la voz o el video de otro tráfico de red.

Cuando el tráfico de red entra en un enrutador, el tráfico se coloca en una cola. Si una directiva QoS no está configurada, solo hay una cola y todos los datos se tratan como "primero en estar", primero en salir con la misma prioridad. Eso significa que el tráfico de voz (que es muy sensible a los retrasos) puede demorarse tras el tráfico, en el que un retraso de algunos milisegundos adicionales no sería un problema.

Al implementar QoS, se definen varias colas con una de varias características de administración de congestión (como la cola de prioridades de Cisco y las características de puesta en cola [CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)) basadas en clases y de prevención de congestión (como la ponderación de la carga anticipada). detección de [WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)).

_Ilustración 2. Ejemplos de colas de QoS_

![Ilustración de las colas de QoS y la división de ancho de banda] El (media/Qos-in-Teams-Image2.png "ancho de banda total disponible se divide entre varias colas (audio, vídeo y otros tipos de tráfico) a las que se les ha asignado prioridades diferentes.")

Una analogía simple es que QoS crea "carriles de autousos" virtuales en su red de datos para que algunos tipos de datos nunca se encuentren con un retraso. Una vez que cree esos carriles, puede ajustar su tamaño relativo y, de forma más eficaz, el ancho de banda de la conexión que tiene, sin dejar de ofrecer experiencias empresariales para los usuarios de su organización.

## <a name="select-a-qos-implementation-method"></a>Seleccione un método de implementación de QoS

Puede implementar QoS mediante el etiquetado basado en el puerto, mediante listas de control de acceso (ACL) en los enrutadores de su red. El etiquetado basado en puertos es el método más confiable porque funciona en entornos Windows y Mac mixtos y es el más fácil de implementar. Los clientes móviles no proporcionan un mecanismo para marcar el tráfico mediante valores de DSCP, por lo que necesitarán este método.  

Con este método, el enrutador de la red examina un paquete entrante y, si el paquete llegó con un determinado puerto o intervalo de puertos, lo identifica como un tipo de medio determinado y lo coloca en la cola para ese tipo, agregando una marca de [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada a la dirección IP Encabezado de paquete para que otros dispositivos puedan reconocer su tipo de tráfico y darle prioridad a su cola.

Aunque esto funciona en todas las plataformas, solo marca el tráfico en la periferia de la WAN (no en el equipo cliente) y crea un overhead de administración. Para obtener instrucciones sobre cómo implementar este método, consulte la documentación proporcionada por el fabricante del router.

* * *

También puede implementar QoS implementada mediante un objeto de directiva de grupo (GPO) para indicar a los dispositivos de cliente que inserten un marcador de DSCP en los encabezados de paquetes IP que lo identifiquen como un tipo de tráfico determinado (por ejemplo, voz). Los enrutadores y otros dispositivos de red se pueden configurar para que reconozcan esto y pongan el tráfico en una cola independiente de mayor prioridad.

Aunque este escenario es completamente válido, solo funcionará para clientes de Windows Unidos a un dominio. Cualquier dispositivo que no sea un cliente de Windows unido a un dominio no se habilitará para el etiquetado de DSCP. Los clientes como Mac OS tienen etiquetas codificadas y siempre marcan el tráfico.

En la parte más, el control del marcado de DSCP mediante GPO garantiza que todos los equipos Unidos a un dominio reciban la misma configuración y que solo un administrador pueda administrarlos. Los clientes que pueden usar un objeto de directiva de grupo se etiquetarán en el dispositivo de origen y, a continuación, los dispositivos de red podrán reconocer el flujo en tiempo real por el código DSCP y darle una prioridad adecuada.

* * *

Recomendamos una combinación de marcas de DSCP en el extremo y las ACL basadas en Puerto en los enrutadores, si es posible. Usar un objeto de directiva de grupo para detectar la mayoría de los clientes, además de usar el etiquetado de DSCP basado en el puerto, garantizará que los clientes móviles, Mac y otros clientes seguirán teniendo el tratamiento de QoS (al menos parcialmente).

Los marcadores de DSCP se pueden likened a sellos postales que indican a los trabajadores postales lo urgente que es la entrega y cuál es el mejor de clasificarla para su entrega rápida. Una vez que haya configurado su red para dar prioridad a las transmisiones de medios en tiempo real, los paquetes perdidos y los paquetes retrasados deberían disminuir enormemente.

Una vez que todos los dispositivos de la red usen las mismas clasificaciones, marcas y prioridades, es posible reducir o eliminar retrasos, paquetes perdidos y vibración cambiando el tamaño de los intervalos de puertos asignados a las colas usadas para cada tipo de tráfico. Desde la perspectiva de Teams, el paso de configuración más importante es la clasificación y el marcado de paquetes, pero para que el QoS se complete correctamente, también tiene que alinear cuidadosamente la configuración de la aplicación con la configuración de red subyacente. Una vez que QoS se ha implementado completamente, la administración continua es una pregunta de ajustar los intervalos de puertos asignados a cada tipo de tráfico según las necesidades de la organización y el uso real.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Elegir intervalos de puertos iniciales para cada tipo de medio

El valor DSCP indica a la red configurada de forma correspondiente la prioridad de dar un paquete o una transmisión por secuencias, ya sea que los clientes o la propia red asignen la marca de DSCP, en función de la configuración de ACL. Cada carga de trabajo multimedia obtiene su propio valor exclusivo de DSCP (otros servicios podrían permitir que las cargas de trabajo compartan un marcado de DSCP, Teams no) y un intervalo de puertos definido e independiente usado para cada tipo de medio. Otros entornos pueden tener una estrategia de QoS existente, lo que le ayudará a determinar la prioridad de las cargas de trabajo de la red.

El tamaño relativo de los intervalos de puertos para las distintas cargas de trabajo de streaming en tiempo real establece la proporción del ancho de banda total disponible dedicado a esa carga de trabajo. Para volver a la analogía de los mensajes anteriores: una carta con un sello de "correo aéreo" puede tomarse dentro de una hora en el aeropuerto más cercano, mientras que un paquete pequeño marcado como "correo masivo" puede esperar un día antes de viajar por tierra en una serie de camiones.

En la tabla siguiente se muestran las marcas de DSCP necesarias para los equipos con ExpressRoute y los puertos asociados para las colas de carga de trabajo. Estos intervalos pueden servir como un buen punto de partida para los clientes que no están seguros de qué usar en sus propios entornos. Para obtener más información, lea [Requisitos de QoS ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Intervalos de puerto iniciales recomendados_

|Tipo de tráfico multimedia| Intervalo de puertos de origen del cliente |Protocolo|Valor de DSCP|Clase de DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50000 – 50019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50,020–50,039|TCP/UDP|34|Desvío garantizado (AF41)|
|Aplicación/pantalla compartida| 50,040–50,059|TCP/UDP|18|Reenvío asegurado (AF21)|
||||||

Tenga en cuenta lo siguiente cuando use esta configuración:

- Si planea implementar ExpressRoute en el futuro y aún no ha implementado QoS, le recomendamos que siga las instrucciones para que los valores DSCP sean los mismos del remitente al destinatario.
- Todos los clientes, incluidos los dispositivos de equipos y clientes móviles, usarán estos intervalos de puertos y se verán afectados por cualquier directiva de DSCP que implemente que use estos intervalos de puertos de origen. Los únicos clientes que seguirán usando puertos dinámicos son los clientes basados en el explorador (es decir, aquellos clientes que permiten a los participantes unirse a reuniones con sus exploradores).
- Aunque el cliente de Mac usa los mismos intervalos de puertos, también usa los valores de código de audio (EF) y vídeo (AF41). Estos valores no se pueden configurar.
- Si posteriormente necesita ajustar los intervalos de puertos para mejorar la experiencia del usuario, los intervalos de puertos no pueden superponerse y deben estar adyacentes entre sí.

## <a name="migrate-qos-to-teams"></a>Migrar QoS a teams

Si ha implementado previamente Skype empresarial online, incluidos los etiquetados QoS y los intervalos de puertos, y ahora está implementando Teams, Teams respetará la configuración existente y usará los mismos intervalos de puertos y etiquetado que el cliente de Skype empresarial. En la mayoría de los casos, no será necesario realizar ninguna configuración adicional.

> [!NOTE]
> Si usa el etiquetado QoS de nombre de aplicación a través de la Directiva de grupo, debe agregar Teams. exe como nombre de la aplicación.

## <a name="qos-implementation-steps"></a>Pasos de la implementación de QoS

En un nivel muy alto, la implementación de QoS requiere estos pasos:

1. [Comprobar que su red está lista](#verify-your-network-is-ready)
2. [Seleccione un método de implementación de QoS](#select-a-qos-implementation-method)
3. [Elegir intervalos de puertos iniciales para cada tipo de medio](#choose-initial-port-ranges-for-each-media-type)
4. Implementar la configuración de QoS:
   1. En los clientes que usan un GPO para [establecer los intervalos de puertos y marcas](QoS-in-Teams-clients.md) de los dispositivos de cliente
   2. En los enrutadores (consulte la documentación del fabricante) u otros dispositivos de red. Esto puede incluir ACL basadas en puertos o simplemente definir las colas de QoS y las marcas de DSCP, o todas ellas.

      > [!IMPORTANT]
      > Recomendamos implementar estas directivas de QoS con los puertos de origen del cliente y una dirección IP de origen y destino de "cualquiera". Esto capturará el tráfico multimedia entrante y saliente en la red interna.  

   3. En el [centro de administración](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) de Teams
5. [Valide la implementación de QoS mediante el](#validate-the-qos-implementation) análisis del tráfico de Teams en la red.

Mientras prepara la implementación de QoS, tenga en cuenta las siguientes pautas:

- La ruta más corta a Office 365 es la mejor.
- Cerrar puertos solo provocará una degradación de la calidad.
- No se recomienda ningún obstáculo, como servidores proxy.
- Limitar el número de saltos:
  - Del cliente al perímetro de la red: 3 a 5 saltos.
  - Proveedor de servicios de Internet a Microsoft Network Edge: 3 saltos
  - Perímetro de la red de Microsoft en el destino final: irrelevante

Para obtener información sobre cómo configurar puertos de firewall, vaya a [Office 365 URL e intervalos IP](office-365-urls-ip-address-ranges.md).

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Administración de puertos de origen en el centro de administración de Teams

En Teams, los puertos de origen QoS usados por las diferentes cargas de trabajo deben administrarse activamente y ajustarse según sea necesario. Al hacer referencia a la tabla en [elegir los intervalos de puerto iniciales para cada tipo de medio](#choose-initial-port-ranges-for-each-media-type), los intervalos de puertos son ajustables, pero los marcadores de DSCP no se pueden configurar. Una vez que haya implementado esta configuración, puede encontrarse con que se necesitan más o menos puertos para un tipo de medio determinado. El [Panel de análisis de llamadas y el panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md) se debe usar para tomar la decisión de ajustar los intervalos de puertos después de la implementación de equipos y periódicamente a medida que cambian las necesidades.

> [!NOTE]
> Si ya ha configurado QoS en función de los intervalos de puertos de origen y las marcas de DSCP para Skype empresarial online, se aplicará la misma configuración a teams y no se requerirán cambios adicionales en el cliente o la red para la asignación, aunque es posible que tenga que [establecer los intervalos se usa en el centro de administración](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) de Teams para coincidir con lo que se ha configurado para Skype empresarial online.

Si ha implementado previamente Skype empresarial Server local, es posible que tenga que volver a examinar las directivas de QoS y ajustarlas según sea necesario para que coincidan con la configuración de intervalo de puertos que ha verificado ofrezca una experiencia de calidad a los usuarios de los equipos.

## <a name="validate-the-qos-implementation"></a>Validar la implementación de QoS

Para que QoS sea efectivo, el valor de DSCP establecido por el objeto de directiva de grupo debe estar presente en ambos extremos de una llamada. Al analizar el tráfico generado por el cliente de Teams, puede comprobar que el valor de DSCP no se cambia o no se elimina cuando el tráfico de la carga de trabajo del equipo se mueve por la red.

Preferiblemente, capturas el tráfico en el punto de salida de la red. Para ayudarlo, puede usar el reflejo de puertos en un switch o un router.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Usar el monitor de red para comprobar los valores de DSCP

Monitor de red es una herramienta que puede [Descargar de Microsoft](https://www.microsoft.com/download/4865) para analizar el tráfico de red.

1. En el equipo que ejecuta el monitor de red, conéctese al puerto que se ha configurado para el reflejo de puertos y empiece a capturar paquetes.

2. Realice una llamada usando el cliente de Teams. Asegúrate de que se haya establecido el medio antes de colgar la llamada.

3. Detener la captura.

4. En el campo **filtro de visualización** , use la dirección IP de origen del equipo que realizó la llamada y perfeccione el filtro definiendo el valor de DSCP 46 (hex 0xb8) como criterio de búsqueda, como se muestra en el siguiente ejemplo:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8

    ![Filtros de captura de pantalla en el cuadro de diálogo Mostrar filtro.] (media/Qos-in-Teams-Image4.png "Cuadro de diálogo filtro de visualización en monitor de red, que muestra los filtros que se van a aplicar.")

5. Seleccione **aplicar** para activar el filtro.

6. En la ventana **Resumen** de tramas, seleccione el primer paquete UDP.

7. En la ventana **detalles del marco** , expanda el elemento de lista de IPv4 y anote el valor al final de la línea que comienza con **DSCP**.

    ![Captura de pantalla que muestra la configuración de DSCP en el cuadro de diálogo Detalles del marco.] (media/Qos-in-Teams-Image5.png "Cuadro de diálogo Detalles del marco en monitor de red, resaltando la configuración de DSCP.")

En este ejemplo, el valor de DSCP se establece en 46. Esto es correcto porque el puerto de origen usado es 50019, lo que indica que se trata de una carga de trabajo de voz.

Repita la verificación para cada carga de trabajo que marque el GPO.

## <a name="more-information"></a>Más información

[Vídeo: planificación de red](https://aka.ms/teams-networking)

[Preparar la red de la organización para Microsoft Teams](prepare-network.md)

[Requisitos de QoS de ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos)

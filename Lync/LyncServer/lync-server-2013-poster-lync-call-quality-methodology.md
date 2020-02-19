---
title: 'Lync Server 2013: póster: metodología de calidad de llamadas de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35627633839f294cebced6df47a90919e7fc5ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Metodología de calidad de llamadas de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-06-24_

Este artículo es un complemento del póster [metodología de calidad de llamadas de Lync](https://go.microsoft.com/fwlink/?linkid=391841) , que se puede descargar desde el centro de descarga.

![Póster que describe el proceso de CQM](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Póster que describe el proceso de CQM")

Puede usar este póster para obtener información sobre CQM, la metodología de calidad de llamadas para Lync 2013 y 2010, que le ayuda a encontrar y eliminar problemas que afectan a la calidad de las llamadas y a la experiencia del usuario para las implementaciones de Lync que incluyen características de telefonía IP empresarial. La metodología de calidad de llamadas es un nuevo marco de solución de problemas y administración de servicios que puede centrar mejor los esfuerzos para mejorar los servicios de Enterprise Voice en Lync. En este artículo, puede obtener más información sobre CQM, los tipos de servidores y soluciones que se supervisan, y qué hacer con los datos de telemetría recopilados.

Si tiene preguntas sobre cómo usar CQM, puede enviar sus preguntas a cqmfeedback@microsoft.com.

En el póster se explican las siguientes áreas:

  - ¿Qué es Lync CQM?

  - Priorizar: ejecutar consultas de tendencias

  - PCD

  - Administrada/no administrada

  - Carretera de la planta de servidor

  - La carretera del último kilómetro

  - La carretera de los puntos finales

  - Administración de servicios

  - Reglas del juego de placas

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>¿Qué es Lync CQM?

La metodología de calidad de llamadas es un nuevo marco de solución de problemas y administración de servicios que puede centrar mejor los esfuerzos para mejorar los servicios de Enterprise Voice en Lync. Cuando se usa CQM, se necesita menos esfuerzo para garantizar la calidad de las llamadas y la satisfacción del usuario en los servicios de telefonía IP empresarial. CQM se explica más detalladamente en la [metodología de calidad de llamadas](https://go.microsoft.com/fwlink/p/?linkid=615208). Este artículo y el póster son resúmenes de ese contenido.

CQM divide la solución de problemas del sistema en tres rutas o "carreteras". Estos son los siguientes: la planta de servidor, que examina los servidores y los vínculos entre ellos, los puntos finales de la carretera, que analizan los dispositivos de usuario y medios usados para llevar llamadas y la calle del pasado kilómetro, que se ocupa de la integración de llamadas de red telefónicas conmutadas tradicionales.

Cada carretera se divide en varios segmentos relacionados con un área o tema específicos, y en cada segmento se realizan definiciones sobre qué es un nivel de calidad aceptable, se realizan acciones para lograr ese nivel de calidad y se establece un plan de administración de servicios para mantener ese nivel de calidad antes de pasar al siguiente tema.

El póster presenta Lync CQM como un juego de mesa para tres jugadores, cada uno de los cuales pasará por una de las carreteras. Las tarjetas incluidas con la descarga se usan para simular impedimentos para la calidad de la llamada que deben superarse. Las sugerencias y sugerencias sobre los objetivos y cómo lograrlos se incluyen en las tres rutas, así como instrucciones de priorización para las cuales la carretera debe llegar en primer lugar en las aplicaciones reales (en el juego, las tres carreteras se abordan en paralelo).

¿Cómo funciona CQM en versiones anteriores de Lync? CQM es nuevo para Lync 2013, pero la mayor parte de este se puede adaptar para usarlo con Lync 2010. CQM puede funcionar hasta cierto punto con Microsoft Office Communicator, pero no se ha probado y no es compatible.

Si tiene preguntas sobre cómo usar CQM, puede enviar sus preguntas a cqmfeedback@microsoft.com.

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>Priorizar: ejecutar consultas de tendencias

El primer paso de CQM es ejecutar cada una de las consultas de tendencias durante dos semanas y, a continuación, analizar los resultados. Dar prioridad a las acciones correctivas por el colaborador de Stream más grande, la proporción de flujo deficiente más alta y las áreas administradas (las que usted controle).Si la unidad de control de audio/vídeo de varios puntos (MCU AV) o las consultas de mediación muestran resultados deficientes, comience en la carretera del servidor o el rojo o del vegetal del servidor.Si las consultas con cable o inalámbricas muestran resultados deficientes, empiece por el azul o la carretera del último kilómetro.Si la VPN o las consultas externas muestran resultados deficientes, comience en los puntos de la carretera verde o final.

Después de elegir un camino para empezar, defina un objetivo para cada área (aserción), trabaje para cumplir ese objetivo (lograr) y, a continuación, implemente los procedimientos para seguir el objetivo (mantener). También puede usar este póster como un juego para comprender los principios que hay detrás de CQM.

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

La herramienta de diagnóstico de llamada anterior (PCD) le ayudará a identificar y diagnosticar problemas en la red perimetral (la base de datos de QoE no recopila información en su periferia o en la red perimetral) y también para solucionar problemas de conexiones en el último kilómetro. La herramienta está disponible como aplicación moderna de Windows 8 o en una aplicación de escritorio de http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88Windows en.

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Administrada/no administrada

La implementación de Lync Server y la infraestructura de red normalmente pueden dividirse en espacios administrados y no administrados. El espacio administrado incluye todo en su infraestructura de red y servidor cableada. El espacio no administrado es la infraestructura inalámbrica y la infraestructura de red externa.

Esta distinción aumenta la claridad de los datos y ayuda a su organización a centrarse en las cargas de trabajo que tendrán un impacto medible en la calidad de vídeo y voz de los usuarios. Los usuarios tienen una expectativa distinta de calidad si la llamada se aplica a una infraestructura de la que es propietario (administrada) frente a la infraestructura que se encuentra en parte bajo el control de otra entidad (no administrada). Esto no quiere decir que los usuarios inalámbricos se dejan a sus propios dispositivos para tener experiencias excelentes de Lync Server.

Para mejorar la calidad de la voz en el espacio no administrado, es necesario tener una calidad alta en el espacio administrado. Si se considera que la red inalámbrica (Wi-Fi) es un espacio administrado o no administrado en su organización. Las técnicas para lograr un entorno saludable son diferentes en los dos espacios, al igual que las soluciones.

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>Carretera de la planta de servidor

El segmento 1 de la planta de servidor se dirige a los servidores reales de la implementación de Lync. Recopilar datos de KHI sobre el propio servidor y su rol en la implementación y analizar el resultado. Si la acción está garantizada, corrija los problemas encontrados. Encontrará más información sobre este tema en el artículo sobre los [indicadores de estado clave en Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) que acompaña al póster KHI.

El siguiente segmento trata las secuencias de medios entre el servidor de la MCU AV y el servidor de mediación. Para empezar, determine los destinos para los umbrales de transmisión deficientes. Las secuencias defectuosas suelen \> ser PacketLossRate .01 \> o PacketLossRateMax. 05. Otro destino deseable es \< PoorStreamsRatio 2%. A continuación, use consultas detalladas para buscar pares de AVMCU y servidores de mediación con flujos de baja calidad, investigar la causa de las secuencias defectuosas, mirar el equipo de red en las rutas de flujo deficientes, corregir secuencias defectuosas y definir una configuración óptima o "Gold" para la red. Equipamiento. Para mantener su logro, implemente procesos y herramientas para administrar el desplazamiento de la configuración e informar sobre nuevas áreas de problemas.

A continuación, examine los flujos de medios entre el servidor de mediación y la puerta de enlace de red telefónica conmutada (RTC). Para empezar, determine los destinos para los umbrales de transmisión deficientes. Las secuencias defectuosas suelen \> ser PacketLossRate .01 \> o PacketLossRateMax. 05. Otro destino deseable es \< PoorStreamsRatio 2%. A continuación, use consultas detalladas para encontrar pares de servidores de mediación y puertas de enlace con secuencias deficientes, investigar la causa de las secuencias defectuosas, mirar el equipo de red en las rutas de flujo deficientes, corregir las secuencias defectuosas y definir una configuración óptima o "Gold" para la red. Equipamiento. Para mantener su logro, implemente procesos y herramientas para administrar el desplazamiento de la configuración e informar sobre nuevas áreas de problemas.

Por último, examine las métricas de estado de la puerta de enlace RTC. Identificar las estadísticas que muestran el estado y definir los objetivos contra ellos. No se proporcionan instrucciones específicas porque se pueden usar muchas puertas de enlace posibles. Una vez que se hayan establecido los objetivos, corrija lo que sea necesario para lograr el destino; en el proceso, es probable que defina una configuración "Gold" o una configuración óptima para la puerta de enlace. Para mantener su logro, implemente procesos y herramientas para administrar el desplazamiento de la configuración e informar sobre nuevas áreas de problemas. Tenga en cuenta que las actualizaciones de firmware y software pueden alterar la configuración o llevarle a cambiar la definición de la configuración "Gold", por lo que debe enfocar estas actividades con cuidado.

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>La carretera del último kilómetro

De las dos formas en las que los clientes se conectan a la red, se espera que la conexión cableada ofrezca la calidad más alta y, en su caso, este debe ser el primer foco para los últimos problemas de kilómetros. Use la consulta cableada CQM (\_LastMile\_0 con cable) y los datos de la proporción de flujo deficiente que proporciona. Se recomienda definir un PoorStreamsRatio \< de destino del 5% para \> los sitios con transmisiones 300). Para lograr sus objetivos, corrija las subredes ordenadas de peor a mejor e implemente QoS.

Después de optimizar la calidad de las conexiones cableadas, mejorar la calidad inalámbrica es más fácil porque la infraestructura inalámbrica se basa en el núcleo con cable en cada ubicación. Las secuencias inalámbricas deficientes en un sitio con buena calidad de cable deben atribuirse a los componentes inalámbricos específicos. La consulta inalámbrica CQM (LastMile\_1\_Wireless) funciona en un intervalo de fechas y devolverá todas las secuencias inalámbricas internas de su entorno desde los clientes de Lync hacia o desde servidores de conferencias o servidores de mediación. Se recomienda definir un PoorStreamsRatio \< de destino del 5% para \> los sitios con transmisiones 300). Para lograr sus objetivos, corrija las subredes ordenadas de peor a mejor e implemente QoS.

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>La carretera de los puntos finales

Comience las consultas en los puntos finales de la carretera con los auriculares y otros dispositivos que se sabe que producen calidad aceptable cuando se usan con Lync. Se recomienda un destino AvgSendListen MOS \> 3,6 para implementaciones con más de 100 secuencias.) Obtenga el destino identificando los dispositivos problemáticos y corríjalos o reemplácelos.

A continuación, examine el dispositivo o el equipo que procesa el audio para las llamadas de usuario final. Una métrica de calidad de destino sugerida \<es un AudioMicGlitchRate = 1. A medida que se identifican las configuraciones de sistema óptimas para los sistemas de usuario, defina una configuración de equipo "Golden", incluidas las versiones de los controladores.

Examine ahora la ruta de red que toma una secuencia de audio de un sistema de punto de conexión de Lync, lo que puede provocar una calidad de audio deficiente. Si el audio se transmite a través de una conexión VPN, es posible que vea problemas de latencia. Si un cliente de Lync interno no puede establecer un flujo de medios directo a otro cliente de Lync interno para una llamada de dos o de punto a punto, se revertirá a una ruta de acceso que retransmitirá a través de un servidor perimetral de Lync, con lo que se obtendrán problemas de latencia, así como un mayor potencial para pérdida y vibración. Le recomendamos que defina una métrica de calidad de 0% de medios a través de VPN. A medida que se corrige para lograr el destino establecido, identifique las subredes problemáticas y investigue las reglas de firewall, los forma de paquetes y otra configuración de equipamiento de red relevante.

Los paquetes IP pueden usar el protocolo de control de transmisión (TCP) o el protocolo de datagramas de usuario (UDP). TCP es óptimo para las secuencias de datos. UDP es sin conexión y es más eficaz para los medios, ya que los mecanismos de recuperación de TCP no pueden resolver la pérdida en los medios en tiempo real. Lync siempre prefiere UDP, pero se revertirá a TCP si no se puede establecer una sesión UDP. Las sesiones multimedia a través de TCP mostrarán una calidad deficiente que a través de UDP. Se recomienda una definición de calidad de 0% de conexiones sobre TCP. A medida que se corrige para lograr el destino establecido, identifique las subredes problemáticas y investigue las reglas de firewall, los forma de paquetes y otra configuración de equipamiento de red relevante.

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>Administración de servicios

La administración de servicios es el estado final de CQM y el destino de las tres carreteras. Para mantener altos niveles de calidad de llamadas, supervise estas áreas:

1.  Las actividades de corrección de **los usuarios** deben mostrar un aumento medible en la satisfacción del usuario. Este problema se puede medir mediante tickets de problemas u otros mecanismos de comentarios. También puede publicar métricas de calidad.

2.  **Proceso** : defina procesos diarios, semanales y mensuales para operar CQM. El ritmo de supervisión comienza con una frecuencia mayor mientras se está corrigiendo (diariamente) y se mueve a una frecuencia más baja (mensual) mientras se estabiliza.

3.  **Herramientas** : identifique las herramientas para la medida y la corrección. Puede que le resulte útil para automatizar la ejecución de las consultas de CQM para que sean compatibles con los procesos. La corrección puede requerir herramientas adicionales, por ejemplo, para aplicar configuraciones estandarizadas en los elementos de la red o solucionar problemas de pérdida en flujos deficientes.

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>Reglas del juego de placas

Puede usar este póster como referencia a una implementación de CQM o como un juego para practicar los conceptos. Para jugar, necesitará un dado del lado de 1 6 y las tarjetas que se proporcionan. Hay disponible una versión descargable de las tarjetas para imprimir en las tarjetas de presentación estándar Avery 5871.

El juego es para 3 jugadores. Hay tres caminos que los jugadores pueden usar para lograr la calidad deseada y llegar al estado central de administración del servicio: planta del servidor, punto final y último kilómetro. Cada ruta de acceso se detiene a lo largo de la forma en que se imponen objetivos de calidad, se alcanzan los objetivos y se mantiene un aspecto del sistema. Ponga las cartas en el área indicada arriba y, a continuación, dibuje 5 cartas. Revise las tarjetas que ha dibujado y colóquelas en el segmento correspondiente de la placa. Cada jugador se desplaza por las tarjetas en su ruta paso a paso, afirmando los objetivos de calidad, logrando esos objetivos y manteniendo los niveles de servicio. El juego se completa cuando todos los jugadores alcanzan el centro del estado de administración del servicio. Se proporcionan reglas más detalladas con la descarga de la tarjeta de juego.

Para **declarar** un objetivo de calidad, revise los parámetros aplicables a ese destino e indique en voz alta lo que quiere aceptar. Se han recomendado puntos de inicio, pero debe realizar la última llamada. La excepción son los datos de KHI, en los que se deben usar los estándares establecidos por Microsoft. Vea el póster KHI adjunto.

Para **obtener** el juego, use las tarjetas proporcionadas en el espacio de datos de KHI y consultas del sistema. Si, al principio del juego, no dibujaste una carta relacionada con un aspecto determinado, puedes continuar a la última. Si hay una carta relevante, desplace el chip. Si ha revertido el número indicado en la tarjeta, ha realizado correctamente. Si gira el número indicado o lo supera, debe dibujar otra tarjeta desde la baraja. Si la tarjeta indica que dos o más jugadores deben desplazarse, deben revertirse correctamente.

Para **mantenerlo** en el juego, indique en alto el plan de administración de servicios que se refiere al aspecto del entorno de Lync.

</div>

<div>

## <a name="see-also"></a>Vea también


[Guía de redes de Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicadores de estado clave: la base para mantener servidores de Lync en buen estado](https://go.microsoft.com/fwlink/?linkid=391838)  
[Metodología de calidad de llamadas de Lync](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


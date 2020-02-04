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
ms.openlocfilehash: 95105501d0403600e88d01ad5fa84363c1e81785
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Metodología de calidad de llamadas de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-06-24_

Este artículo es un complemento del póster [metodología de calidad de llamadas de Lync](http://go.microsoft.com/fwlink/?linkid=391841) , que puede descargar desde el centro de descarga.

![Póster que describe el proceso de CQM](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Póster que describe el proceso de CQM")

Puede usar este póster para obtener más información sobre CQM, la metodología de calidad de las llamadas de Lync 2013 y 2010 que le ayuda a buscar y eliminar problemas que afectan a la calidad de las llamadas y a la experiencia del usuario para las implementaciones de Lync que incluyen características de telefonía IP empresarial. La metodología de la calidad de las llamadas es un nuevo marco de solución de problemas y administración de servicios que puede concentrar mejor los esfuerzos para mejorar los servicios de voz empresariales en Lync. En este artículo, puede obtener más información sobre CQM, los tipos de servidores y soluciones que se supervisan y qué hacer con los datos de telemetría recopilados.

Si tienes preguntas sobre cómo usar CQM, puedes enviar tus preguntas a cqmfeedback@microsoft.com.

En el póster se explican las siguientes áreas:

  - ¿Qué es Lync CQM?

  - Priorizar: ejecutar consultas de tendencias

  - PCD

  - Administrada/no administrada

  - La planta de servidor

  - La carretera del último kilómetro

  - La carretera de los puntos finales

  - Administración de servicios

  - Reglas del juego de tablero

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>¿Qué es Lync CQM?

La metodología de la calidad de las llamadas es un nuevo marco de solución de problemas y administración de servicios que puede concentrar mejor los esfuerzos para mejorar los servicios de voz empresariales en Lync. Cuando se usa CQM, se necesita menos esfuerzo para garantizar la calidad de las llamadas y la satisfacción del usuario para los servicios de voz empresariales. CQM se explica más detalladamente en la metodología de la calidad de las [llamadas](http://go.microsoft.com/fwlink/p/?linkid=615208). Este artículo y el póster son resúmenes de ese contenido.

CQM divide la solución de problemas del sistema en tres paths o "carreteras". Estos son: la planta de servidor, que consulta los servidores y los vínculos entre ellos, el extremo de la carretera, que consulta los dispositivos de los usuarios y medios usados para transportar llamadas, y la carretera del último kilómetro, que trata la integración de llamadas de redes telefónicas conmutadas tradicionales.

Cada carretera se divide en varios segmentos relacionados con un área o un tema específico, y en cada segmento se realizan definiciones sobre qué nivel de calidad es aceptable, se realizan acciones para lograr ese nivel de calidad, y se pone en marcha un plan de administración de servicios para mantener ese nivel de calidad antes de pasar al siguiente tema.

El póster presenta Lync CQM como un juego de mesa para tres jugadores, cada uno de los cuales irá a través de una de las carreteras. Las tarjetas incluidas con la descarga se usan para simular impedimentos para la calidad de las llamadas que deben superarse. Las sugerencias y sugerencias sobre objetivos y cómo lograrlos se incluyen en los tres caminos, así como pautas de priorización para las cuales el camino hacia el primer lugar en aplicaciones reales (en el juego, las tres carreteras se tratan en paralelo).

¿Cómo funciona CQM en versiones anteriores de Lync? CQM es nuevo para Lync 2013, pero la mayoría de ellos puede adaptarse para usar con Lync 2010. CQM puede funcionar hasta cierto punto con Microsoft Office Communicator, pero esto no está probado y no es compatible.

Si tienes preguntas sobre cómo usar CQM, puedes enviar tus preguntas a cqmfeedback@microsoft.com.

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>Priorizar: ejecutar consultas de tendencias

El primer paso de CQM es ejecutar cada una de las consultas de tendencias durante dos semanas y, a continuación, analizar los resultados. Priorizar la acción correctiva por el colaborador de streams más grande, la relación de transmisión insuficiente más alta y las áreas administradas (las que usted controle).Si la unidad de control de audio/vídeo de varios puntos (MCU AV) o las consultas de mediación muestran resultados deficientes, comience en la carretera de la planta roja o del servidor.Si las consultas con cable o inalámbricas muestran resultados deficientes, comienzan el azul o el último kilómetro.Si las consultas de VPN o externas muestran resultados deficientes, empiece en la carretera de los puntos verdes o verdes.

Después de elegir un camino para empezar, defina un objetivo para cada área (Assert), trabaje para conocer ese objetivo (lograr) y, a continuación, implemente procedimientos para estar en objetivo (mantener). También puede usar este póster como un juego para comprender los principios de CQM.

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

La herramienta de diagnóstico de PRELLAMADA (PCD) le ayudará a identificar y diagnosticar problemas en su red perimetral (la base de datos de QoE no recopila información sobre su periferia o red perimetral) y también para solucionar problemas de conexión en el último kilómetro. La herramienta está disponible como una aplicación moderna de Windows 8 o una aplicación de escritorio de http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88Windows en.

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Administrada/no administrada

La implementación de Lync Server y la infraestructura de red generalmente se pueden dividir en espacios administrados y no administrados. El espacio administrado incluye toda la infraestructura de servidor y la red cableada. El espacio no administrado es la infraestructura inalámbrica y la infraestructura de red externa.

Al hacer esta distinción, aumenta la claridad de los datos y ayuda a su organización a centrarse en las cargas de trabajo que tendrán un impacto medible en la calidad de voz y vídeo de los usuarios. Los usuarios tienen una expectativa diferente en cuanto a la calidad si la llamada se aplica a la infraestructura que posee (administrada) frente a la infraestructura que está en parte bajo el control de alguna otra entidad (no administrada). Esto no quiere decir que los usuarios de tecnología inalámbrica se queden en sus propios dispositivos para tener experiencias excelentes de Lync Server.

Para mejorar la calidad de la voz en el espacio no administrado debes tener alta calidad en el espacio administrado. Si se considera que la conexión inalámbrica (Wi-Fi) es de administración o no administrada en su organización. Las técnicas para lograr un entorno saludable son diferentes en los dos espacios, al igual que las soluciones.

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>La planta de servidor

El segmento 1 de la planta de servidor se dirige a los servidores reales de la implementación de Lync. Recopilar datos de KHI relacionados con el propio servidor y su rol en la implementación y analizar el resultado. Si la acción es justificada, corrija los problemas que encuentre. En el artículo sobre los [indicadores de estado clave de Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) que se incluyen en el póster de KHI se presenta más información sobre este tema.

El segmento siguiente trata las transmisiones de medios entre el servidor AV MCU y el servidor de mediación. Para empezar, determina los destinos de los umbrales de flujo deficiente. Los flujos deficientes suelen \> ser PacketLossRate .01 \> o PacketLossRateMax. 05. Otro destino deseable es \< PoorStreamsRatio 2%. A continuación, use consultas detalladas para buscar pares de servidores de AVMCU y mediación con secuencias deficientes, investigar la causa de las transmisiones deficientes, mirar el equipo de red en las rutas de flujo deficientes, corregir las secuencias deficientes y definir una configuración óptima o "Gold" para la red. ofimáticos. Para mantener su logro, implemente procesos y herramientas para administrar el desplazamiento de la configuración y para informar de nuevas áreas problemáticas.

A continuación, examine las transmisiones multimedia entre el servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC). Para empezar, determina los destinos de los umbrales de flujo deficiente. Los flujos deficientes suelen \> ser PacketLossRate .01 \> o PacketLossRateMax. 05. Otro destino deseable es \< PoorStreamsRatio 2%. A continuación, use consultas detalladas para encontrar pares de servidores de mediación y de puerta de enlace con secuencias deficientes, investigar la causa de las transmisiones deficientes, mirar el equipo de red en las rutas de flujo deficientes, corregir las secuencias deficientes y definir una configuración óptima o "Gold" para la red. ofimáticos. Para mantener su logro, implemente procesos y herramientas para administrar el desplazamiento de la configuración y para informar de nuevas áreas problemáticas.

Por último, examine las métricas de estado de la puerta de enlace RTC. Identifique las estadísticas que muestran el estado y defina los objetivos con ellos. No se proporcionan directrices específicas porque se pueden usar muchas puertas de enlace posibles. Una vez que se hayan establecido los objetivos, remediar según sea necesario para alcanzar el objetivo; en el proceso probablemente definirá una configuración "Gold" o una configuración óptima para la puerta de enlace. Para mantener su logro, implemente procesos y herramientas para administrar el desplazamiento de la configuración y para informar de nuevas áreas problemáticas. Tenga en cuenta que el firmware y las actualizaciones de software pueden alterar su configuración o llevarle a cambiar la definición de la configuración "Gold", por lo que debe enfocar estas actividades con cuidado.

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>La carretera del último kilómetro

De las dos formas en las que los clientes se conectan a la red, se espera que los cables cumplan la mejor calidad y, de forma correspondiente, deben ser el foco inicial para los problemas de la última milla. Use la consulta cableada CQM (\_LastMile\_0 cableada) y los datos de la relación de transmisión deficiente que proporciona. Le sugerimos que defina un \< 5% de destino para \> los sitios con transmisiones de 300 PoorStreamsRatio). Para alcanzar sus objetivos, remediar las subredes ordenadas de peor a mejor e implementar QoS.

Después de optimizar la calidad de las conexiones por cable, mejorar la calidad de la conexión inalámbrica es más fácil porque la infraestructura inalámbrica se encuentra sobre el núcleo con cable en cada ubicación. Las secuencias inalámbricas deficientes en un sitio con una buena calidad de conexión deben ser atribuidos a los componentes inalámbricos específicos. La consulta inalámbrica CQM (conexión\_inalámbrica\_de LastMile 1) funciona en un intervalo de fechas y devolverá todas las transmisiones inalámbricas internas en su entorno desde clientes de Lync a o desde servidores de conferencias o servidores de mediación. Le sugerimos que defina un \< 5% de destino para \> los sitios con transmisiones de 300 PoorStreamsRatio). Para alcanzar sus objetivos, remediar las subredes ordenadas de peor a mejor e implementar QoS.

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>La carretera de los puntos finales

Comience las consultas en los puntos finales de la carretera con los auriculares con micrófono y otros dispositivos que se sabe que producen calidad aceptable cuando se usan con Lync. Sugerimos un objetivo AvgSendListen MOS \> 3,6 para implementaciones con más de 100 transmisiones.) Logre el objetivo identificando los dispositivos problemáticos y corríjalos o reemplácelos.

Después, examine el dispositivo o el equipo que procesa el audio para las llamadas de usuario final. Una métrica de calidad de objetivo sugerida \<es una AudioMicGlitchRate = 1. A medida que identifique las configuraciones óptimas del sistema para los sistemas de usuario, defina una configuración para el PC de "oro", incluidas las versiones del controlador.

Ahora examine la ruta de acceso de red que toma una secuencia de audio de un sistema de puntos de conexión de Lync, que puede causar una mala calidad de audio. Si el audio viaja a través de una conexión VPN, es posible que vea problemas de latencia. Si un cliente interno de Lync no puede establecer una secuencia de multimedia directa para otro cliente interno de Lync para una llamada de dos o de par a par, revertirá a una ruta de acceso que se retransmitirá a través de un servidor perimetral de Lync, lo que provocará problemas de latencia, así como un aumento potencial para pérdida y vibración. Le sugerimos que defina una métrica de calidad de 0% de soporte por VPN. A medida que se remedie para lograr el objetivo establecido, identifique las subredes problemáticas y investigue las reglas de firewall, los formantes de paquetes y otra configuración relevante del equipo de red.

Los paquetes IP pueden usar el protocolo de control de transmisión (TCP) o el protocolo de datagramas de usuario (UDP). TCP es óptimo para las secuencias de datos. UDP es sin conexión y es más eficaz para los medios ya que los mecanismos de recuperación de TCP no pueden perder la pérdida en los medios en tiempo real. Lync siempre prefiere UDP, pero se revertirá a TCP si no se puede establecer una sesión UDP. Las sesiones multimedia por TCP tendrán una calidad deficiente a la de UDP. Recomendamos una definición de calidad de conexiones del 0% por TCP. A medida que se remedie para lograr el objetivo establecido, identifique las subredes problemáticas y investigue las reglas de firewall, los formantes de paquetes y otra configuración relevante del equipo de red.

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>Administración de servicios

La administración de servicios es el estado final de CQM y el destino de las tres carreteras. Para mantener altos niveles de calidad de las llamadas, supervisa estas áreas:

1.  **Usuarios** : las actividades de corrección deberían mostrar un aumento medible en la satisfacción del usuario. Esto se puede medir por tickets de problemas u otros mecanismos de comentarios. También puede publicar métricas de calidad.

2.  **Proceso** : defina procesos diarios, semanales y mensuales para operar CQM. El ritmo de supervisión comienza con una frecuencia superior mientras se está corrigiendo (diariamente) y pasa a una frecuencia menor (mensual) mientras se estabiliza.

3.  **Herramientas** : identifique las herramientas para medir y corregir. Es posible que le resulte útil para automatizar la ejecución de las consultas de CQM para admitir sus procesos. La corrección puede requerir herramientas adicionales, por ejemplo, para forzar la aplicación de configuraciones estandarizadas en elementos de red o la pérdida de secuencias deficientes.

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>Reglas del juego de tablero

Puede usar este póster como referencia a una implementación de CQM o como un juego para practicar los conceptos. Para jugar, necesitará un dado de 1 6 y las tarjetas proporcionadas. Hay disponible una versión descargable de las tarjetas para imprimirlas en tarjetas de presentación estándar Avery 5871.

El juego es para 3 jugadores. Existen tres caminos que pueden usar los jugadores para lograr la calidad deseada y alcanzar el estado de administración del servicio central: planta de servidor, punto final y último kilómetro. Cada ruta se detiene a lo largo del modo en que declara objetivos de calidad, logra objetivos y mantiene un aspecto del sistema. Coloque las tarjetas en el área indicada arriba y, a continuación, dibuje 5 cartas. Revise las tarjetas que ha dibujado y colóquelas en el segmento correspondiente del panel. Cada jugador pasa por las tarjetas en sus rutas paso a paso, afirmando objetivos de calidad, consecución de esos objetivos y manteniendo los niveles de servicio. El juego se completará cuando todos los jugadores alcancen el centro de administración del servicio. Con la descarga de la tarjeta de juego se proporcionan reglas más detalladas.

Para **declarar** un objetivo de calidad, revise los parámetros que se aplican a ese objetivo y, a continuación, indique en voz alta lo que usted y no elija Aceptar. Hemos recomendado puntos iniciales, pero debes hacer la llamada final. La excepción son los datos de KHI, en los que debe utilizarse la normativa establecida por Microsoft. Vea el póster de KHI adjunto.

Para **obtener** el juego, use las tarjetas proporcionadas en lugar de las consultas de datos y del sistema de KHI. Si al principio del juego no dibujaste una tarjeta relacionada con un aspecto determinado, puedes continuar después de la misma. Si hay una tarjeta relevante, desplace el chip. Si has revertido el número que figura en la tarjeta, significa que has tenido éxito. Si retiras el número indicado, deberás dibujar otra tarjeta desde la baraja. Si la tarjeta indica que dos o más jugadores tienen que desplazarse, deben reponerse correctamente.

Para **mantenerlo** en el juego, indique en alto el plan de administración de servicios que se refiere al aspecto del entorno de Lync.

</div>

<div>

## <a name="see-also"></a>Vea también


[Guía de redes de Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicadores clave de estado: la base para mantener los servidores de Lync en buen estado](http://go.microsoft.com/fwlink/?linkid=391838)  
[Metodología de calidad de llamadas de Lync](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


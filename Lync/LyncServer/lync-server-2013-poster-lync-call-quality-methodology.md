---
title: Metodología de calidad de llamadas en Lync Server 2013
TOCTitle: 'Póster: Metodología de calidad de llamadas en Lync'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084821
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Metodología de calidad de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Este artículo es complementario al póster [Metodología de calidad de llamadas en Lync](http://go.microsoft.com/fwlink/?linkid=391841), que puede descargar del Centro de descarga.

![Póster en el que se describe el proceso de CQM](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Póster en el que se describe el proceso de CQM")

En este póster se presenta la Metodología de calidad de llamadas (CQM) para Lync 2013 y 2010, una herramienta que ayuda a detectar y eliminar problemas que afectan a la calidad de la llamada y la experiencia del usuario en las implementaciones de Lync que incluyen la característica de telefonía IP empresarial. La Metodología de calidad de llamadas es un nuevo marco para la solución de problemas y la administración de servicios que dirige y centra los esfuerzos por mejorar los servicios de telefonía IP empresarial en Lync. En este artículo, obtendrá más información sobre la CQM, los tipos de servidores y soluciones que se supervisan y qué hacer con los datos telemétricos obtenidos.

Puede enviar sus preguntas acerca de cómo usar la CQM a cqmfeedback@microsoft.com.

En el póster se explican los siguientes puntos:

  - ¿Qué es la CQM de Lync?

  - Establecer prioridades: ejecutar consultas sobre tendencias

  - PCD

  - Administrado/no administrado

  - La ruta de la planta del servidor

  - La ruta de la última milla

  - La ruta de los extremos

  - Administración de servicios

  - Reglas del juego de mesa

## ¿Qué es la CQM de Lync?

La Metodología de calidad de llamadas (CQM) es un nuevo marco para la solución de problemas y la administración de servicios que dirige y centra los esfuerzos por mejorar los servicios de telefonía IP empresarial en Lync. Cuando se utiliza la CQM, se requieren menos esfuerzos para garantizar la calidad de la llamada y la satisfacción del usuario con los servicios de telefonía IP empresarial. La CQM se explica minuciosamente en la [Guía para la conexión de redes de Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677). Este artículo y el póster son un resumen del contenido de la guía.

La CQM desglosa la solución de problemas del sistema en tres grupos o "rutas", que son: la ruta de la planta del servidor, centrada en los servidores y las conexiones entre ellos; la ruta de los extremos, centrada en los dispositivos de los usuarios y los medios utilizados para mantener las llamadas, y la ruta de la última milla, que se encarga de la integración de las llamadas de redes telefónicas conmutadas tradicionales.

Cada ruta se divide en varios segmentos relacionados con un punto o tema específico. Y en cada segmento se define qué se considera un nivel de calidad aceptable, las medidas que se tomarán para alcanzar ese nivel de calidad y un plan de administración de servicios para mantener el nivel de calidad antes de pasar al siguiente tema.

En el póster se presenta la CQM de Lync como un juego de mesa para tres jugadores, cada uno de los cuales seguirá una de las rutas. Se utilizan las cartas incluidas en la descarga para simular los obstáculos que habrá que superar para alcanzar una buena calidad de llamada. A lo largo de estas tres rutas se ofrecen sugerencias y consejos sobre los objetivos y cómo conseguirlos, así como directrices para establecer el orden de prioridad y saber qué ruta seguir en primer lugar en las aplicaciones reales (en el juego, las tres rutas se siguen paralelamente).

¿Cómo funciona la CQM en versiones anteriores de Lync? La CQM es novedad en Lync 2013, pero buena parte de esta herramienta se puede adaptar para utilizarla con Lync 2010. La CQM puede funcionar en cierta medida con Microsoft Office Communicator, pero no se ha probado y no es compatible.

Puede enviar sus preguntas acerca de cómo usar la CQM a cqmfeedback@microsoft.com.

## Establecer prioridades: ejecutar consultas sobre tendencias

El primer paso en la CQM es ejecutar cada una de las consultas de tendencias durante dos semanas para después analizar los resultados. Establezca la prioridad de las medidas correctivas en función del elemento que más contribuya a la transmisión, la relación más alta de una transmisión deficiente y las áreas administradas (las que usted controla). Si la consulta de la Unidad de control multipunto de audio y vídeo (AV MCU) o de mediación arrojan unos resultados deficientes, inicie la ruta roja, también conocida como la ruta de la planta de servidor. Si las consultas de conexión por cable o las consultas inalámbricas arrojan unos resultados deficientes, inicie la ruta azul o ruta de la última milla. Si las consultas de VPN o externas arrojan unos resultados deficientes, comience la ruta verde o de extremos.

Cuando haya elegido la ruta por la que comenzará, defina un objetivo para cada área (Declarar), trabaje para alcanzar el objetivo (Alcanzar) e implemente procedimientos para permanecer en el objetivo (Mantener). También puede usar este póster como un juego a través del cual conocer los principios básicos de la CQM.

## PCD

La herramienta de diagnóstico previo a la llamada (PCD) sirve para identificar y diagnosticar problemas en la red perimetral (la base de datos QoE no recopila información sobre la red perimetral), así como para solucionar problemas de conexiones en la última milla. La herramienta se encuentra disponible en la forma de aplicación moderna para Windows 8 o aplicación de escritorio para Windows en http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.

## Administrado/no administrado

La implementación y la infraestructura de red de Lync Server suele estar dividida en espacios administrados y no administrados. El espacio administrado incluye todas las conexiones de red interna por cable y la infraestructura de servidores. Mientras que el espacio no administrado es la infraestructura inalámbrica y la infraestructura de red exterior.

Establecer esta distinción arroja luz a los datos y ayuda a una empresa a centrarse en las cargas de trabajo que tendrán un impacto cuantificable en la calidad de las llamadas de voz y vídeo de los usuarios. Los usuarios suelen tener expectativas diferentes de lo que es la calidad de la llamada según esta se realice por infraestructuras propias (administradas) o infraestructuras que dependen en parte de alguna otra entidad (no administradas). Por no hablar de los usuarios de conexiones inalámbricas, que dependen de sus propios dispositivos para tener experiencias excelentes en Lync Server.

Mejorar la calidad de voz en el espacio no administrado exige máxima calidad en el espacio administrado. Si las redes inalámbricas (Wi-Fi) se consideran parte del espacio administrado o no administrado depende de su empresa. Las técnicas empleadas para conseguir un entorno en buen estado son diferentes en los dos espacios, como también lo son las soluciones.

## La ruta de la planta del servidor

El segmento 1 de la ruta de la planta del servidor se centra en los servidores de la implementación de Lync. Recopile datos de KHI relativos al servidor y a su rol en la implementación y analice el resultado. Si se garantiza la acción, corrija los problemas que encuentre. Este tema se expone en mayor detalle en el artículo sobre [Indicadores clave de estado de Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) que complementa al póster sobre KHI.

El siguiente segmento se centra en las transmisiones de medios entre el servidor de AV MCU y el servidor de mediación. Comience determinando los objetivos para los umbrales de transmisiones deficientes. Las transmisiones deficientes suelen ser PacketLossRate \> .01 o PacketLossRateMax \> .05. Otro objetivo deseable es PoorStreamsRatio \< 2%. A continuación, use las consultas detalladas para detectar los pares de servidores de AVMCU y mediación con transmisiones deficientes, investigue la causa de estas deficiencias, analice el equipo de la red en las rutas de transmisiones deficientes y defina la configuración óptima u "oro" para el equipo de la red. Para mantener los logros, implemente procesos y herramientas para administrar las desviaciones de la configuración y para informar de las nuevas áreas problemáticas.

A continuación, examine las transmisiones de medios entre el servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC). Comience determinando los objetivos para los umbrales de transmisiones deficientes. Las transmisiones deficientes suelen ser PacketLossRate \> .01 o PacketLossRateMax \> .05. Otro objetivo deseable es PoorStreamsRatio \< 2%. A continuación, utilice las consultas detalladas para identificar pares de servidor de mediación y puerta de enlace con transmisiones deficientes, investigue la causa de las transmisiones deficientes, analice el equipo de la red en las rutas de transmisiones deficientes, corrija las transmisiones deficientes y defina la configuración óptima u "oro" para el equipo de red. Para mantener los logros, implemente procesos y herramientas para administrar las desviaciones de la configuración y para informar de las nuevas áreas problemáticas.

Por último, examine las métricas de estado de la puerta de enlace RTC. Identifique las estadísticas que muestran el estado y defina los objetivos en función de esos valores. No se dan directrices específicas porque son muchas las puertas de enlace que se pueden utilizar. Cuando se hayan establecido los objetivos, haga las modificaciones necesarias para alcanzar el objetivo. En el proceso, probablemente definirá una configuración "oro" u óptima para la puerta de enlace. Para mantener los logros, implemente procesos y herramientas para administrar las desviaciones de la configuración y para informar de las nuevas áreas problemáticas. Tenga en cuenta que las actualizaciones de software y hardware pueden alterar la configuración o exigir cabios en la definición de configuración "oro". Tenga cuidado al abordar estas actividades.

## La ruta de la última milla

De las dos formas en las que los clientes se pueden conectar a la red, se espera que la conexión a red por cable sea la de máxima calidad y, por ello, debe ser su principal foco de atención a la hora de abordar los problemas de la última milla. Utilice la consulta conexión por cable de la CQM (LastMile\_0\_Wired) y los datos de la relación de transmisiones deficientes que proporciona. Recomendamos que se defina un objetivo de PoorStreamsRatio \< 5% para los sitios con \> 300 transmisiones. Para alcanzar sus objetivos, subsane los problemas de las subredes en orden, de la peor a la mejor, e implemente QoS.

Después de optimizar la calidad de las conexiones de red por cable, mejorar la calidad de las redes inalámbricas resulta más fácil porque la infraestructura inalámbrica se asienta sobre el núcleo cableado en cada ubicación. Las transmisiones inalámbricas deficientes en un sitio con buena calidad de conexiones por cable se deben atribuir a componentes inalámbricos específicos. La consulta de conexiones inalámbricas de CQM (LastMile\_1\_Wireless) actúa en un intervalo de fechas y devolverá todas las transmisiones de redes inalámbricas internas del entorno desde los clientes de Lync a o desde servidores de conferencia o servidores de mediación. Recomendamos que se defina un objetivo de PoorStreamsRatio \< 5% para los sitios con \> 300 transmisiones.

## La ruta de los extremos

Comience examinando la ruta de los extremos con auriculares y otros dispositivos que se sepa que producen una calidad aceptable cuando se usan con Lync. Recomendamos un objetivo de AvgSendListen MOS \> 3.6 para implementaciones de más de 100 transmisiones.) Alcance el objetivo identificando los dispositivos problemáticos y repárelos o sustitúyalos.

A continuación, examine el dispositivo o el equipo que está procesando el audio de las llamadas de usuario final. Un objetivo recomendado para la métrica de calidad es AudioMic GlitchRate \> 1. Cuando identifique las configuraciones óptimas del sistema para los sistemas de los usuarios, defina una configuración "oro" de equipo que incluya las versiones de los controladores.

A continuación, examine la ruta de red que sigue una transmisión de audio desde un sistema de extremo de Lync que puede causar deficiencias en la calidad del audio. Si el audio viaja por una conexión VPN, podría encontrar problemas de latencia. Si un cliente de Lync interno no puede establecer una transmisión de medios directa a otro cliente de Lync interno para una llamada de dos partes o de punto a punto, volverá a una ruta que dependa de un servidor perimetral de Lync, lo que también provoca problemas de latencia, así como una mayor probabilidad de pérdida y de vibración. Recomendamos definir una métrica de calidad de 0% Media en una VPN. Cuando haga las modificaciones necesarias para conseguir el objetivo que se ha marcado, identifique problemas en subredes y estudie las reglas de los firewalls, conformadores de paquetes y otras configuraciones de equipos de red pertinentes.

Los paquetes IP pueden usar el Protocolo de control de transmisión (TCP) o bien el Protocolo de datagramas de usuario (UDP). El TCP es óptimo para las transmisiones de datos. El UDP no tiene conexiones por lo que es más eficiente para las transmisiones multimedia, ya que los mecanismos de recuperación del TCP no pueden solucionar las pérdidas en las transmisiones multimedia en tiempo real. Lync siempre prefiere el UDP, pero recurrirá al TCP si no puede establecer una sesión UDP. Las sesiones multimedia en TCP son de calidad inferior a las sesiones en UDP. Recomendamos definir la calidad en 0% para conexiones en TCP. Cuando haga las modificaciones necesarias para conseguir el objetivo que se ha marcado, identifique problemas en subredes y estudie las reglas de los firewalls, conformadores de paquetes y otras configuraciones de equipos de red pertinentes.

## Administración de servicios

La administración de servicios es el estado final de la CQM y el destino de las tres rutas. Para mantener niveles elevados de calidad en las llamadas, supervise las siguientes áreas:

1.  **Usuarios:** las actividades de reparación deben conducir a un aumento cuantificable en la satisfacción del usuario. Puede medir la satisfacción mediante vales de problemas u otros mecanismos de envío de comentarios. También puede publicar las métricas de calidad.

2.  **Proceso:** defina procesos diarios, semanales y mensuales para que la CQM sea operativa. La pauta de supervisión comienza con la máxima frecuencia mientras se solucionan problemas (diariamente) y reduce la frecuencia (mensualmente) en la medida en que se estabiliza.

3.  **Herramientas:** determine qué herramientas necesita para medir y solucionar problemas. Le resultará útil para automatizar la ejecución de las consultas de la CQM necesarias para los procesos. La solución de problemas puede requerir herramientas adicionales como, por ejemplo, para aplicar configuraciones normalizadas en elementos de red o para solucionar las pérdidas en transmisiones deficientes.

## Reglas del juego de mesa

Puede utilizar este póster como fuente de referencia para la implementación de la CQM o como un juego con el que poner en práctica algunos conceptos. Para jugar necesitará un dado de seis caras y las cartas suministradas. Puede imprimir una versión descargable de las cartas en el tamaño estándar de tarjetas comerciales Avery 5871.

Se trata de un juego para tres jugadores. Hay tres rutas que los jugadores pueden utilizar para conseguir la calidad deseada y alcanzar el estado de Administración de servicios del centro: planta de servidores, extremos y última milla. En las tres rutas hay paradas a lo largo del camino en las que se "declaran" los objetivos de calidad, se "alcanzan" los objetivos y se "mantiene" un aspecto del sistema. Coloque las cartas en el área indicada más arriba y, a continuación, reparta 5 cartas. Revise las cartas que le han tocado y colóquelas en el segmento del tablero correspondiente. Cada jugador se mueve por las cartas de su ruta paso a paso, declarando los objetivos de calidad, alcanzándolos y manteniendo los niveles de servicio. El juego termina cuando todos los jugadores llegan al estado de Administración de servicios. Encontrará las reglas detalladas en la descarga de las cartas del juego.

Para **declarar** un objetivo de calidad, revise los parámetros aplicables a ese objetivo y diga en voz alta qué decide aceptar o no. Hemos recomendado unos puntos de partida, pero usted decide por dónde comenzar, salvo en el caso de los datos de KHI, en los que se han de utilizar los estándares publicados por Microsoft. Consulte el póster complementario de KHI.

Para **alcanzar** los objetivos del juego, utilice las cartas suministradas en lugar de los datos de KHI y las consultas del sistema. Si al principio del juego no ha extraído una carta relacionada con un aspecto concreto, puede continuar. Si hay una carta relevante, tire el dado. Si saca el número indicado en la carta, gana. Si saca el número o lo supera, deberá coger otra carta del montón. Si la carta indica que deben tirar el dado dos o más jugadores, todos ellos deberán sacar el número correcto.

Para **mantener** los objetivos del juego, explique en voz alta el plan de administración del servicio relativo a ese aspecto del entorno de Lync.

## Vea también

#### Otros recursos

[Guía para la conexión de redes de Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicadores de estado clave: La Fundación para el mantenimiento de Lync Server en buen estado](http://go.microsoft.com/fwlink/?linkid=391838)  
[Metodología para la calidad de llamadas en Lync](http://go.microsoft.com/fwlink/?linkid=391841)


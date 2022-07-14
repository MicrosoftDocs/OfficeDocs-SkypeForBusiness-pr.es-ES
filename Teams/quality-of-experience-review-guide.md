---
title: Usar el CQD para administrar la calidad de las llamadas y reuniones en Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Aprenda a analizar y administrar el rendimiento multimedia en tiempo real en Microsoft Teams con el Panel de calidad de llamadas.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 182cd98825948a4d7732513c9f2eb3a884539354
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794588"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Usar el CQD para administrar la calidad de las llamadas y reuniones en Microsoft Teams 

Este artículo le ayudará , el administrador o el departamento de soporte técnico y el ingeniero del departamento de soporte técnico de Teams, a desarrollar un proceso de supervisión y mantenimiento de la calidad de las llamadas y reuniones de su organización mediante el Panel de calidad de llamadas (CQD) de Microsoft Teams. Nuestra guía hace hincapié en los escenarios de calidad de audio, ya que cualquier mejora de la red que realice para mejorar la experiencia de audio se traducirá en mejoras en el vídeo y el uso compartido.

Clave de esta guía son las dos [plantillas del CQD protegidas](https://aka.ms/QERtemplates) : le recomendamos que las descargue antes de seguir las instrucciones de este artículo.

En este artículo se supone que ya ha [configurado el CQD](turning-on-and-using-call-quality-dashboard.md).


## <a name="categories-to-monitor-and-maintain"></a>Categorías para supervisar y mantener

Una vez que haya implementado las reuniones y la voz en Teams, necesitará un plan de supervisión y mantenimiento continuos. Si lo hace, se asegurará de que Teams siempre funciona de forma óptima. Este plan debe incluir las áreas clave enumeradas a continuación. También debe establecer objetivos de métricas de calidad y un plan para solucionar y aislar problemas cuando se produzcan.

<table>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Calidad de la llamada</strong></td>
<td>
<p>Desglosar las métricas por llamadas internas (dentro de su organización, como VPN, WiFi, por cable) o llamadas externas</p>
<p>Desglosar las métricas mediante la creación o la red</p>
<p>Llamadas VPN</p>
<p>Llamadas con TCP, UDP o proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Confiabilidad de llamadas</strong></td>
<td><p>Identificar y corregir cualquier problema de red o firewall</p>
<p>Obtenga información sobre los porcentajes de errores de colocación y configuración de llamadas</p>
<p>Obtenga información sobre dónde se producen la mayoría de los errores de colocación y de configuración de llamadas</p>
</td>
</tr>
<tr class="odd">
<td><strong>Encuesta de usuario</strong></td>
<td>
<p>Usar Calificar los datos de mi llamada para obtener información sobre la experiencia real de los usuarios</p>
<p>¿Dónde se producen las malas experiencias?</p>
<p>Correlacionar la mala experiencia con la calidad, la confiabilidad y los dispositivos de las llamadas</p>
</td>
</tr>
<tr class="even">
<td><strong>Dispositivos</strong></td>
<td><p>Obtén información sobre qué micrófonos y altavoces se usan con más frecuencia y su impacto en la calidad de las llamadas</p>
<p>¿Se revisan periódicamente los controladores auxiliares de audio, vídeo, USB y WiFi?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clientes</strong></td>
<td>
<p>Obtenga información sobre los tipos de cliente y versiones que se usan y su impacto en la calidad y confiabilidad de las llamadas  </p>
</ol></td>
</tr>
</tbody>
</table>

Si evalúa y corrige continuamente las áreas descritas en este artículo, puede reducir su potencial para afectar negativamente a los usuarios. La mayoría de los problemas de usuario se pueden agrupar en las siguientes categorías:

-   Una configuración de proxy o firewall incompleta
-   Una cobertura Wi-Fi insuficiente
-   Un ancho de banda insuficiente
-   VPN
-   Versiones y controladores de cliente incoherentes u obsoletos
-   Dispositivos de audio no estimulados o integrados
-   Dispositivos de red o subred problemáticos

A través de una planificación y un diseño adecuados antes de implementar Teams o Skype Empresarial Online, puede reducir la cantidad de esfuerzo que se requerirá para mantener experiencias de alta calidad.

Este artículo se centra en usar el Panel de calidad de llamadas (CQD) en línea como la herramienta principal para informar e investigar cada área, con un énfasis especial en el audio para maximizar la adopción y el impacto. Las mejoras realizadas en la red para mejorar la experiencia de audio también se traducirán directamente en mejoras en el uso compartido de vídeo y escritorio.

Para acelerar la evaluación, se proporcionan [dos plantillas del CQD protegidas](https://aka.ms/qertemplates) : una es para administrar todas las redes y la otra se filtra solo para redes administradas (internas). Aunque los informes de la plantilla Todas las redes están configurados para mostrar información de compilación y de red, se pueden seguir usando mientras se trabaja para recopilar y cargar información de compilación. Cargar información de compilación en el CQD permite al servicio mejorar la creación de informes agregando información personalizada de compilación, red y ubicación, diferenciando las subredes internas de las externas. Para obtener más información, lea [Creación de asignaciones](CQD-building-mapping.md).

### <a name="intended-audience"></a>Público al que se dirige

Este artículo está pensado para que lo usen las partes interesadas de partners y clientes con roles como Jefe de proyecto/arquitecto de colaboración, Consultor, Especialista en administración y adopción de cambios, jefe de soporte/departamento de soporte técnico, jefe de red, jefe de escritorio y Administración de TI.

Este artículo también está pensado para ser utilizado por los expertos de calidad designados. Para obtener más información, consulte [el rol Campeón de calidad](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>¿Qué es la calidad?

En este contexto, la calidad es una combinación de métricas de servicio y experiencia del usuario.


### <a name="service-metrics"></a>Métricas de servicio

Las métricas de servicio constan de métricas específicas basadas en el cliente. Durante cada llamada, el cliente recopila telemetría para la llamada y envía un informe al final de cada llamada a la que se puede acceder más adelante en el CQD o en análisis de [llamadas por usuario](set-up-call-analytics.md). Estas métricas incluyen (pero no se limitan a):

-   Mala transmisión (entrante y saliente)
-   Tasa de errores de configuración
-   Drop Failure Rate


#### <a name="poor-stream-rate"></a>Velocidad de transmisión deficiente

La mala velocidad de transmisión (PSR) representa el porcentaje general de transmisiones de la organización que tienen mala calidad. Esta métrica está pensada para resaltar las áreas en las que su organización puede concentrar sus esfuerzos para tener el mayor impacto en la reducción de este valor y la mejora de la experiencia del usuario, por lo que [las redes administradas](#managed-versus-unmanaged-networks) son el foco principal cuando se mira el PSR. Los usuarios externos también son importantes, pero la investigación difiere en función de la organización. Considere la posibilidad de proporcionar procedimientos recomendados para usuarios externos e investigar llamadas externas de forma independiente de la organización en general.

La medición real en el CQD varía según la carga de trabajo, pero para los fines de este artículo, nos centramos principalmente en la medición del _porcentaje de mala calidad de audio_ . PSR se compone de los cinco promedios de métricas de red descritos en la tabla siguiente. Para que una transmisión se clasifique como mala, solo es necesario que una métrica supere el umbral definido. El CQD proporciona el "Poor Due To..." para comprender mejor qué condición provocó que la transmisión se clasificara como mala. Para obtener más información, lea [Clasificación de stream en el CQD](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> El CQD proporciona el "Mala debido a..." para comprender mejor qué condición provocó que la transmisión se clasificara como mala.


##### <a name="audio-poor-quality-metrics"></a>Métricas de calidad deficiente de audio

| Promedio métrico     | Descripción     | Experiencia de usuario |
|-------------|-----------------|-----------------|
| Vibración \>30 ms        | Este es el cambio medio en el retraso entre paquetes sucesivos. Teams y Skype Empresarial pueden adaptarse a algunos niveles de vibración mediante el almacenamiento en búfer. Solo cuando la vibración excede el búfer, un participante observa los efectos de la vibración.      | Los paquetes que llegan a diferentes velocidades hacen que la voz de un altavoz suene robótica.   |
| Índice de pérdida de \>paquetes 10% o 0,1        | Esto se define a menudo como un porcentaje de paquetes que se pierden. La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individualmente que casi no tienen impacto a pérdidas de ráfagas posteriores que hacen que el audio se corte por completo.     | Los paquetes se descartan y no llegan a su destino deseado provocan lagunas en los medios, lo que produce sílabas y palabras perdidas, y vídeo entrecortado y uso compartido. |
| Tiempo de ida \>y vuelta 500 ms        | Este es el tiempo que se tarda en obtener un paquete IP desde el punto A hasta el punto B y volver al punto A. Este retraso de propagación de red está vinculado a la distancia física entre los dos puntos y la velocidad de la luz, e incluye una sobrecarga adicional tomada por los diversos dispositivos en la ruta de red.      | Los paquetes tardan demasiado tiempo en llegar a su destino provocan un efecto walkie-talkie.   |


##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>¿Por qué preferimos usar transmisiones en lugar de llamadas?

Las transmisiones nos permiten saber qué tramo concreto de la llamada era deficiente: saliente o entrante. Cuando esté analizando el análisis de llamadas de una llamada mala, determine si la llamada mala se debe a la secuencia de ese autor de la llamada (saliente) o a la secuencia del destinatario de la llamada (de entrada). Determinar qué transmisión afecta a la calidad de las llamadas es aún más importante para las conferencias. Si solo está mirando los datos de las llamadas, verá cuántas conferencias participa una persona, pero no verá qué personas son hablantes activos, haciendo la mayoría del uso compartido de la pantalla.

Los datos de llamadas proporcionan métricas de uso, pero no necesariamente le llevarán a la causa raíz de la mala calidad de las llamadas. Al observar la dirección de la transmisión, puede identificar factores como una llamada que no está en una red administrada, una llamada de un no empleado (por ejemplo, un proveedor o alguien de una red diferente). En estos casos, si la conexión de red de la otra persona era mala, toda la llamada se marcará como mala. No puede hacer nada sobre factores externos, por lo que estos datos no son útiles.

La dirección de Stream también puede ayudarle a identificar los dispositivos o clientes problemáticos.

 - Por ejemplo, si tiene un presupuesto limitado para dispositivos y desea proporcionar dispositivos solo para usuarios de audio pesado, use el informe de uso de audio (VoIP) y filtre para las transmisiones salientes y las conferencias. Busque usuarios de audio de alto volumen que estén hablando en micrófonos integrados: esto puede correlacionarse con una calidad de llamada menor (y es posible que desee proporcionar dispositivos de audio para estas personas). Para mayor claridad, puede filtrar por el uso de paquetes, lo que le permitirá dirigirse especialmente a usuarios de audio de alto volumen. 

  - Otro ejemplo implica el uso compartido de la pantalla. Si un cliente usa un cliente antiguo de Teams, el rendimiento del uso compartido de la pantalla puede verse afectado. Para solucionar este problema, priorice las actualizaciones de los clientes para las personas que hacen mucho uso compartido de la pantalla.

 - Al identificar qué dirección de transmisión está causando mala calidad de llamada, puede determinar si tiene un problema de QoS o de ancho de banda. Si no ha implementado por completo QoS, o si solo marca paquetes en el cliente y no en la transmisión de entrada, es posible que vea una calidad de llamada menor. Al observar la dirección de la transmisión, puede obtener una vista más pormenorizada de la pérdida de paquetes, la latencia o la vibración en una dirección específica. 

   - Por ejemplo, supongamos que un usuario se queja del audio robótico mientras está conectado con cable (vibración). Al analizar la transmisión y la dirección, puede determinar que el problema se produce en la transmisión entrante, solo para un conjunto específico de subredes. Después de proporcionar esta información a su equipo de redes, pueden rastrearlo hasta un acelerador WAN mal configurado que no omitía el tráfico multimedia. Una vez que el equipo de red vuelve a configurar el acelerador wan, la vibración desaparece y mejora la calidad de la llamada. 


#### <a name="setup-failure-rate"></a>Tasa de errores de configuración

La tasa de errores de configuración, también conocida como la medida _Porcentaje de errores de configuración de llamada total_ en el CQD, es el número de transmisiones en las que no se pudo establecer la ruta de acceso multimedia entre los puntos de conexión al comienzo de la llamada.

Esto representa cualquier transmisión multimedia que no se haya podido establecer. Dada la gravedad del impacto de este problema en la experiencia del usuario, el objetivo es reducir este valor a un valor lo más próximo posible a cero. Un valor alto para esta métrica es más común en las nuevas implementaciones con reglas de firewall incompletas que en una implementación para adultos, pero sigue siendo importante vigilarla periódicamente.

Esta métrica se calcula tomando el número total de transmisiones que no se pudo configurar dividido por el número total de transmisiones que enviaron un registro de detalles de llamada correcto (CDR):

-   **Setup Failure Rate** = Total Call Setup Failed Stream Count /Total CDR Available Stream Count

#### <a name="drop-failure-rate"></a>Drop Failure Rate

La tasa de error de caída, también conocida como la medición _De porcentaje de errores perdidos de llamada total_ en el CQD, es el porcentaje de transmisiones establecidas correctamente donde la ruta de acceso a medios no finalizó con normalidad.

Esto representa cualquier transmisión multimedia que finalice inesperadamente. Aunque el impacto de esto no es tan grave como una transmisión que no se pudo configurar, sigue afectando negativamente a la experiencia del usuario. Las caídas de medios repentinas y frecuentes no solo pueden tener un impacto grave en la experiencia del usuario, sino que provocan la necesidad de que los usuarios se vuelvan a conectar, lo que produce una pérdida de productividad (por no mencionar la frustración).

La métrica se calcula tomando el número total de transmisiones caídas divididas por el recuento total de transmisiones que se configuraron correctamente:

-   **Drop Failure Rate** = Total Call Dropped Stream Count / Total Call Setup Succeeded Stream Count

### <a name="define-your-target-metrics"></a>Definir las métricas de destino

En esta sección se describen algunas de las métricas del servicio principal que usamos para evaluar el estado de los servicios. Al evaluar e impulsar continuamente los esfuerzos para mantener estas métricas por debajo de los objetivos definidos, ayudará a garantizar que los usuarios experimenten una calidad de llamada coherente y confiable. Como punto de partida, use los destinos sugeridos en la tabla siguiente. Ajuste los objetivos según sea necesario para cumplir los objetivos empresariales.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo de red</th><th rowspan="1">Objetivos de calidad</th><th colspan="2">Objetivos de confiabilidad</th></tr>
<tr><th>Audio Poor Stream Rate</th><th>Tasa de errores de configuración</th><th>Drop Failure Rate</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>General</td><td>3.0%</td><td>1.0%</td><td>3.0%</td></tr>
<tr><td rowspan="5"><strong>Conferencia</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Interno cableado</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>interno de Wi-Fi 5 GHz</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>interno de Wi-Fi 2,4 GHz</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>General</td><td>2.0%</td><td>0.5%</td><td>3.0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Interno con cable/Wi-Fi de 5 GHz</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Cableada/Wi-Fi 5 GHz en general</td><td>2.0%</td><td>1.0%</td><td>1.0%</td></tr>
<tr><td>General</td><td>2.0%</td><td>1.0%</td><td>3.0%</td></tr>
</table>

### <a name="user-experience"></a>Experiencia de usuario

Analizar la experiencia del usuario es más arte que ciencia, porque las métricas recopiladas aquí no siempre significan que hay un problema con la red o el servicio, sino que simplemente indican que el usuario percibe un problema. El CQD incluye un mecanismo de encuesta integrado, Rate My Call (RMC), que ayuda a evaluar la experiencia general del usuario. RMC le proporcionará información sobre las siguientes preguntas desde la perspectiva de los usuarios:

-   ¿Sé cómo usar la solución?
-   ¿Es la solución fácil de usar e intuitiva, y es compatible con mis necesidades de comunicación diarias?
-   ¿La solución me ayuda a hacer mi trabajo?
-   ¿Cuál es mi percepción general de la solución?
-   ¿Puedo usar la solución en cualquier momento, independientemente de dónde me encuentre?
-   ¿Puedo configurar y mantener una llamada?

#### <a name="rate-my-call"></a>Calificar mi llamada 

Calificar mi llamada (RMC) está integrado en Teams y Skype Empresarial. Aparece automáticamente después de una de cada 10 llamadas o el 10 por ciento. En esta breve encuesta se pide al usuario que califique la llamada y proporcione un poco de contexto para conocer por qué la calidad de la llamada podría haber sido deficiente. Una calificación uno o dos se considera mala, tres a cuatro es buena, y cinco es excelente. Aunque es algo atrasado, esta es una métrica útil para descubrir problemas que las métricas de servicio pueden perderse.

> [!Note]
> El factor humano: los usuarios a menudo ignoran la encuesta cuando la calidad de la llamada es buena y la rellenan cuando la calidad de la llamada es mala. Como resultado, los informes de RMC podrían quedar sesgados al lado pobre incluso mientras las métricas de servicio son buenas.

Puede usar el CQD para informar sobre las respuestas de los usuarios de RMC, y los informes de ejemplo se incluyen en la plantilla del CQD. Sin embargo, no se describen en detalle en este artículo. 

#### <a name="client-and-device-readiness"></a>Disponibilidad de clientes y dispositivos

Necesita una estrategia sólida de clientes y dispositivos para ayudar a garantizar que los usuarios tengan una experiencia de usuario coherente y positiva. Algunos principios clave impulsan cada estrategia de preparación.

##### <a name="client-readiness"></a>Disponibilidad del cliente

Mantener actualizado al cliente de Teams garantiza que los usuarios siempre obtengan la mejor experiencia posible. Microsoft publica [actualizaciones frecuentes para el cliente de Teams](teams-client-update.md) (la actualización se instala en segundo plano a menos que haya desactivado esta funcionalidad, que no se recomienda). También es importante recordar parchear los controladores de red, vídeo, USB y audio, ya que a menudo se pasan por alto y pueden afectar a la calidad de las llamadas y reuniones. Considere la posibilidad de agregar controladores de red, Wi-Fi, vídeo, USB y audio a su proceso de administración de revisiones actual.


##### <a name="device-readiness"></a>Preparación del dispositivo

Ninguna estrategia única puede afectar a la experiencia del usuario más que la estrategia de preparación del dispositivo. Por ejemplo, los usuarios que dependen de los altavoces y el micrófono de su portátil experimentarán una gran cantidad de ruido de fondo en las llamadas y reuniones. Teams está diseñado para funcionar con casi cualquier dispositivo, pero si tiene problemas relacionados con el dispositivo, consulte [Teléfono para Teams](./devices/phones-for-teams.md).


### <a name="categories-of-quality"></a>Categorías de calidad

Poner en funcionamiento un conjunto de prácticas de gestión de calidad: esto le ofrece la mejor oportunidad de una buena calidad de llamadas y reuniones. Un buen plan de gestión de calidad aborda estas categorías:

-   **Red:** La calidad de audio se centra en la métrica Poor Stream Ratio (PSR), el uso de TCP, las subredes cableadas e inalámbricas, y la identificación del uso de servidores proxy HTTP y VPN

-   **Extremos:** Dispositivos de audio y clientes actualizados

-   **Administración de servicios:** Esta categoría consta de dos secciones:

    -   En primer lugar, es responsabilidad de Microsoft administrar y mantener los servicios de Teams y Skype Empresarial Online.

    -   En segundo lugar, las tareas que su organización administra para garantizar un acceso confiable al servicio, como actualizar la información de compilación y mantener los firewalls para las nuevas direcciones IP de Office 365 a medida que se agrega infraestructura al servicio.

![Gráfico de las categorías de calidad de una organización.](media/qerguide-image-categories.png "Las categorías de calidad de una organización: administración de servicios, puntos de conexión y la red.")

Revise la siguiente lista de tareas recomendadas para mantener la calidad. Debería realizar estas tareas periódicamente, por ejemplo, semanalmente.

#### <a name="service-management-tasks"></a>Tareas de administración de servicios

Estas tareas van desde garantizar que haya ancho de banda suficiente para llegar al servicio sin saturar los vínculos a Internet, validar la calidad del servicio (QoS) en todas las áreas de red administradas y mantenerse al tanto de [Office 365 intervalos IP en los firewalls](/microsoft-365/enterprise/urls-and-ip-address-ranges).

#### <a name="network-tasks"></a>Tareas de red

Hay dos categorías de tareas de red: confiabilidad y calidad. La confiabilidad se centra en medir la capacidad del usuario para realizar llamadas correctamente y mantenerse conectado. La calidad se centra en la telemetría agregada enviada a Teams y Skype Empresarial online por el cliente del usuario durante la llamada y una vez finalizada. 

Dada la incidencia crítica que la confiabilidad tiene en la experiencia del usuario, le recomendamos que evalúe e investigue las métricas de confiabilidad antes de profundizar en la calidad. 

#### <a name="endpoints-tasks"></a>Tareas de puntos de conexión

La tarea principal de esta categoría quitando todos los obstáculos a [las actualizaciones normales del cliente de Teams](teams-client-update.md). De forma predeterminada, Teams se actualiza automáticamente periódicamente (a menos que desactive esa configuración, que no se recomienda). 

También debes supervisar los dispositivos y proporcionar actualizaciones siempre que identifiques problemas relacionados con un dispositivo.

## <a name="use-cqd-to-manage-call-quality"></a>Usar el CQD para administrar la calidad de las llamadas

Una vez que haya [configurado el CQD](turning-on-and-using-call-quality-dashboard.md), estará listo para empezar a usarlo para administrar la calidad de las llamadas y reuniones de su organización.

La mayoría de los problemas con el rendimiento de Teams se dividen en las siguientes categorías:

-   Una configuración de proxy o firewall incompleta
-   Una cobertura Wi-Fi insuficiente
-   Un ancho de banda insuficiente
-   VPN
-   Versiones y controladores de cliente incoherentes u obsoletos
-   Dispositivos de audio no estimulados o integrados
-   Dispositivos de red o subred problemáticos

Si se toma el tiempo antes de implementar Teams para evaluar estas áreas y corregir las deficiencias, reducirá el esfuerzo necesario para mantener una experiencia de Teams de alta calidad para todos los usuarios. Para obtener ayuda para evaluar la red en preparación de la implementación de Teams, lea [Asesor de Teams](use-advisor-teams-roll-out.md) y [Preparar la red para Teams](prepare-network.md).

### <a name="expectations-using-cqd"></a>Expectativas al usar el CQD

Use el Panel de calidad de llamadas (CQD) para obtener información sobre la calidad de las llamadas realizadas con Teams y Skype Empresarial servicios. El CQD se ha diseñado para ayudar a Teams y a Skype Empresarial administradores e ingenieros de red a optimizar la red y vigilar de cerca la calidad, la confiabilidad y la experiencia del usuario. El CQD examina la telemetría agregada para toda una organización, donde los patrones generales pueden hacerse evidentes; esto le permite realizar evaluaciones informadas y planear la corrección. El CQD proporciona informes de métricas que proporcionan información sobre la calidad general, la confiabilidad y la experiencia del usuario.

El CQD, aunque es útil para analizar tendencias y subredes, no siempre proporciona una causa específica para un escenario determinado. Es importante entender esto y establecer las expectativas correctas al usar el CQD:

-   El CQD no proporcionará la causa raíz para cada escenario
-   El CQD no contendrá las transmisiones del sistema telefónico o de audioconferencia
-   el CQD destacará áreas para futuras investigaciones basadas en tendencias

### <a name="cqd-reports-overview"></a>Información general de los informes del CQD

Use el menú desplegable de la parte superior de la pantalla para abrir un informe. Para obtener una lista de los datos proporcionados en cada informe, lea [Datos disponibles en informes del CQD](CQD-data-and-reports.md#data-available-in-cqd-reports).

Novedades de enero de 2020: [Descargar plantillas de consulta de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Plantillas personalizables de Power BI que puede usar para analizar e informar de los datos del CQD.


### <a name="teams-vs-skype-for-business"></a>Teams frente a Skype Empresarial

El CQD puede informar sobre Teams y Skype Empresarial. Sin embargo, es posible que en ocasiones desee desarrollar un informe para ver la telemetría de Teams independientemente de Skype Empresarial.

#### <a name="summary-reports"></a>Informes de resumen

Para modificar la página de informes de resumen y ver solo teams o Skype Empresarial, seleccione el menú desplegable **Filtro** de producto en la parte superior de la pantalla y, a continuación, seleccione el producto que desee.

![Captura de pantalla del menú desplegable que muestra las opciones de filtro.](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Informes detallados

Para filtrar todos los informes detallados, en la barra del explorador, anexe lo siguiente al final de la dirección URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Ejemplo:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obtener más información sobre los filtros de dirección URL, lea [Filtrar informes](CQD-data-and-reports.md#report-filters) más adelante en esta sección.

Para filtrar un informe detallado individual, agregue el filtro ``Is Teams`` al informe y establéctalo en Verdadero o Falso.

![Captura de pantalla de la página Agregar filtro.](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Redes administradas frente a no administradas

De forma predeterminada, todos los puntos de conexión del CQD se clasifican como externos. Tan pronto como se presenta un archivo de compilación, podemos empezar a ver los datos administrados del punto de conexión. Como se ha comentado anteriormente, las redes en el CQD se definen como:

-   Una _red administrada_, a menudo denominada interna o interna, puede ser influenciada y controlada por la organización. Esto incluye la LAN interna, la WAN remota y la VPN.
-   Una _red no administrada_, a menudo denominada externa o externa, no puede ser influenciada ni controlada por la organización. Un ejemplo de una red no administrada es una red de hotel o aeropuerto.

### <a name="dimensions-measures-and-filters"></a>Dimensiones, medidas y filtros

Una consulta del CQD bien formada contiene los tres parámetros siguientes:

-   **Dimensión:** Cómo quiero dinamizar los datos.

-   **Medida:** Sobre lo que quiero informar.

-   **Filtro:** Cómo quiero reducir el conjunto de datos que devuelve la consulta.

Otra forma de mirar esto es que una _dimensión_ es la función de agrupación, una _medida_ son los datos que me interesan y un _filtro_ es cómo quiero limitar los resultados a los que son relevantes para mi consulta.

Un ejemplo de una consulta con formato correcto es **Mostrar mis transmisiones malas [Medida] por Subred [Dimensión] para El edificio 6 [Filtro]**. Para obtener más información, vea [Dimensiones y medidas disponibles en el CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="first-vs-second"></a>Primero frente a segundo 

Muchas de las dimensiones y medidas del CQD se clasifican como primeras o segundas. El CQD no usa campos de autor de llamada o destinatario: se les ha cambiado el nombre _en primer_ lugar y _en segundo lugar_ porque hay pasos intermedios entre el autor de la llamada y el destinatario de la llamada. La siguiente lógica determina qué punto de conexión implicado se etiqueta como primero:

-   **En primer lugar** , siempre será un punto de conexión de servidor (servidor de conferencia, servidor de mediación, etc.) si un servidor está implicado en la transmisión o la llamada.

-   **En segundo lugar** , siempre habrá un punto de conexión de cliente a menos que la transmisión se encuentre entre dos puntos de conexión de servidor.

-   Si ambos puntos de conexión son del mismo tipo, la elección de estos primeros se basa en el orden interno de la categoría de agente de usuario. De este modo se asegura que el orden es coherente.

Para obtener más información sobre cómo determinar el primer punto de conexión o el segundo punto de conexión cuando ambos son iguales, vea [Dimensiones y medidas disponibles en el CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="stream-vs-call"></a>Transmisión frente a llamada

Debe comprender la diferencia entre una llamada y una transmisión para elegir correctamente qué dimensiones o medidas verá en el CQD. Aunque el foco principal del CQD está en las transmisiones, también están disponibles las medidas basadas en llamadas.

-   **Corriente:** Solo hay una _transmisión_ entre dos puntos de conexión. Solo hay una transmisión para cada dirección y se necesitan dos transmisiones para la comunicación. Las transmisiones son útiles para investigar edificios, redes o subredes. En algunos casos, tanto la llamada como la transmisión se usan en el nombre de la medida (por ejemplo, Secuencia de configuración de llamadas o Secuencia de llamadas caídas). Siguen estando clasificados como transmisiones.

-   **Llamar:** Una _llamada_ es una agrupación de todas las transmisiones de todos los participantes. Una llamada consiste, como mínimo, en dos transmisiones. Una sola llamada tendrá al menos dos puntos de conexión, cada uno con un mínimo de una transmisión.

Para obtener instrucciones adicionales sobre si la dimensión o medida hace referencia a una llamada o a una transmisión, vea [Dimensiones y medidas disponibles en el CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="good-poor-and-unclassified-calls"></a>Llamadas buenas, malas y sin clasificar

Una llamada se clasifica como buena, mala o sin clasificar. Dedíquemos un momento para hablar de cada uno con más detalle.

-   **Bueno o malo:** Una llamada buena o mala consiste en una llamada que contiene un conjunto completo de métricas de servicio, para las que el servicio ha generado y recibido un informe completo de QoE. Determinar si una transmisión es buena o mala se describe [anteriormente en este artículo](#poor-stream-rate).

-   **Sin clasificar:** Una transmisión sin clasificar no contiene un conjunto completo de métricas de servicio. Pueden ser llamadas breves (normalmente menos de 60 segundos) en las que no se pudieron calcular los promedios y no se generó un informe de QoE. La razón más común para que las llamadas se desclasifiquen es que no había poco o ningún uso de paquetes. Un ejemplo de esto sería un participante que se une a una reunión en silencio y nunca habla. El participante recibe, pero no transmite, medios de comunicación. Sin la transmisión de medios, no habrá ninguna métrica disponible para que el CQD las use para clasificar la transmisión multimedia saliente del punto de conexión.

Para obtener más información, lea [Clasificación de stream en el CQD](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Subredes comunes

Las subredes comunes son subredes privadas específicas que usan hoteles, redes domésticas, puntos de acceso y áreas similares. Estas subredes son difíciles de evaluar debido a su uso generalizado. Si su organización usa una de estas subredes comunes, le recomendamos que mueva esa red a otra subred. Esto facilitará la creación de informes en el CQD. Cuando se indica, los informes de la plantilla Todas las redes se han configurado para excluir estas subredes para eliminarlas como un origen de mala calidad. A continuación se definen subredes comunes; su impacto variará según la organización.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Al investigar una red administrada que usa una subred común, tendrá que usar la dimensión IP local Second Reflexive para agrupar subredes. Esta dimensión contiene la dirección IP pública del punto de conexión.


## <a name="reliability-investigations"></a>Investigaciones de confiabilidad

El primer paso para mejorar la calidad es evaluar el estado de fiabilidad en toda la organización. Dado que la confiabilidad es vital para una experiencia de usuario positiva, comenzamos con los dos componentes que miden la fiabilidad:

1.  **Errores de configuración:** No se pudo establecer la llamada.

2.  **Errores de colocación:** La llamada se estableció y finalizó inesperadamente.

A lo largo de esta sección, trataremos los métodos para investigar ambas áreas.

> [!NOTE]
> No todos los informes incluidos en las plantillas se tratan en este artículo. Sin embargo, los métodos de investigación explicados a continuación siguen siendo aplicables. Consulte la descripción individual del informe para obtener más información.


### <a name="setup-failures"></a>Errores de configuración

Priorice primero la corrección de errores de configuración en esta área, ya que estos errores tienen un impacto negativo significativo en la experiencia del usuario.

Comience la investigación evaluando el porcentaje de errores de configuración general para la organización y, a continuación, priorice las áreas de investigación en función del porcentaje más alto por compilación o red. 

#### <a name="setup-failure-trend-analysis"></a>Análisis de tendencias de errores de instalación

Este informe muestra la cantidad total de transmisiones, errores de configuración de la transmisión y la tasa de errores de configuración de la transmisión. Seleccione cualquiera de las columnas para mostrar sus valores individuales. 

##### <a name="analysis"></a>Análisis

Al usar este informe, puede responder a las siguientes preguntas y determinar su siguiente curso de acción:

-   ¿Cuál es el porcentaje total de errores de configuración de llamadas para el mes actual?

-   ¿Está el porcentaje total de errores de configuración de llamada por debajo o por encima de la métrica de destino definida?

-   ¿La tendencia de fracasos es peor o mejor que el mes anterior?

-   ¿Está aumentando, estable o disminuyendo la tendencia de errores?

Independientemente de las respuestas a estas preguntas, tómese el tiempo necesario para investigar más a través de los informes secundarios complementarios para buscar edificios individuales o subredes que puedan necesitar corrección. Aunque la tasa de errores general podría estar por debajo de la métrica objetivo, las tasas de fracaso de uno o más edificios o redes podrían estar por encima de la métrica objetivo y necesitan investigación.

#### <a name="setup-failure-investigations"></a>Investigaciones de errores de instalación 

Este informe resumido se usa para detectar y aislar los edificios o redes que podrían necesitar corrección.

> [!NOTE]
> Asegúrese de ajustar el filtro del informe Mes del año al mes actual. Seleccione **Editar** y ajuste el filtro de informe **Mes año** para guardar el nuevo mes predeterminado.

##### <a name="remediation"></a>Remediación 

Centre sus primeros esfuerzos de corrección en edificios o subredes que tienen el mayor volumen de errores. Esto maximizará el impacto en la experiencia del usuario y ayudará a reducir rápidamente la tasa de errores de configuración de llamadas de la organización. En la tabla siguiente se enumeran las dos razones para los errores de configuración según lo notificado por el CQD.

| Motivo de errores en la configuración de llamadas       | Causa típica                    |
|----------------------------------|----------------------------------|
| Falta la regla de exenciones para la inspección profunda de paquetes del fw | Indica que el equipo de red a lo largo de la ruta ha impedido establecer la ruta de acceso a medios debido a las reglas de inspección profunda de paquetes. Es probable que esto se deba a que las reglas del firewall no se han configurado correctamente. En este escenario, el enlace TCP se realizó correctamente, pero el enlace SSL no lo consiguió.      |
| Falta la regla de excepción de bloque de IP del fw      | Indica que el equipo de red a lo largo de la ruta de acceso ha impedido que se estableciera la ruta de acceso de medios a la red de Microsoft 365 o Office 365. Esto puede deberse a que las reglas del firewall o el proxy no se han configurado correctamente para permitir el acceso a las direcciones IP y los puertos usados para Teams y el tráfico de Skype Empresarial. |

Cuando empiece la corrección, puede centrar sus esfuerzos en un edificio o subred determinados. Como se muestra en la tabla anterior, estos problemas se deben a configuraciones de proxy o firewall. Revise las opciones de la tabla siguiente para ver las acciones de corrección.

|      Remediación      |Instrucciones  |
|-----------------------|----------|
| Configurar firewalls | Trabaje con su equipo de red y compruebe la configuración de los firewalls en [la lista de direcciones IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).<br><br>Compruebe que las [subredes de medios y los puertos están incluidos](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) en las reglas del firewall. <br><br>Compruebe que los [puertos necesarios](prepare-network.md) están abiertos en el firewall. Udp debe tener prioridad porque TCP se considera un protocolo de conmutación por error para el audio, el vídeo y el uso compartido de la pantalla basado en vídeo, y su uso afectará a la calidad de la llamada. El uso compartido de aplicaciones RDP heredado solo usa TCP.|

### <a name="drop-failures"></a>Errores de colocación

A diferencia de los códigos de error de configuración, el CQD no tiene ningún código de error de caída para indicar por qué se producen errores de caída, que hace que sea difícil aislar una causa raíz específica. Para mejorar los errores de las caídas de evaluación, use un enfoque deducido. Al corregir las áreas de interés para los medios, aplicar revisiones a clientes y controladores e impulsar el uso de dispositivos certificados para Teams y Skype Empresarial, es posible que se rechace la caída de errores.

#### <a name="drop-failure-trend-analysis"></a>Análisis de tendencia de error de caída

Este informe muestra la cantidad total de transmisiones de audio, los errores de caída totales y la tasa de errores de caída. Seleccione cualquiera de las columnas para mostrar sus valores. 


##### <a name="analysis"></a>Análisis

Al usar este tipo de informe, puede responder a las siguientes preguntas:

-   ¿Cuál es la tasa actual de errores de caída?
-   ¿Está la tasa de errores de caída por debajo de la métrica de destino definida?
-   ¿La tendencia de fracasos es peor o mejor que el mes anterior?
-   ¿Está aumentando, estable o disminuyendo la tendencia de errores?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo necesario para investigar utilizando los informes secundarios para buscar edificios o redes que puedan necesitar corrección. Aunque la tasa general de errores de caída podría estar por debajo de la métrica objetivo, la tasa de error de caída para uno o más edificios o redes podría estar por encima de la métrica objetivo y necesita investigación.

#### <a name="drop-failure-investigations"></a>Descartar investigaciones de errores

Los errores notificados aquí indican que la llamada se interrumpió inesperadamente y resultó en una experiencia de usuario negativa. A diferencia de los informes de tendencias, estos informes proporcionan información adicional sobre subredes específicas que necesitan una investigación más exhaustiva.


##### <a name="remediation"></a>Remediación

Con los informes de tabla incluidos, puede aislar áreas problemáticas en la red donde la tasa de caída está por encima de la métrica de destino que ha definido. Centre sus primeros esfuerzos de corrección en edificios o subredes que tienen el mayor recuento total de transmisiones, para lograr el mayor impacto.

Causas comunes de caídas de llamadas:

-   Red subprovisionada o salida de Internet
-   No hay QoS configurado en redes restringidas
-   Versiones de cliente anteriores
-   Comportamiento del usuario

Después de descubrir las áreas problemáticas, puede usar el [análisis de llamadas por usuario](use-call-analytics-to-troubleshoot-poor-call-quality.md) para revisar más a fondo los usuarios de ese edificio en busca de problemas específicos. El análisis de llamadas contiene datos euii adicionales y puede ser útil para aislar aún más los posibles motivos de los errores de caída.

Independientemente de su paso siguiente, se recomienda notificar al departamento de soporte técnico que se ha detectado un problema con edificios o subredes específicos. Esto permite al departamento de soporte técnico responder rápidamente a las llamadas entrantes y evaluar a los usuarios de forma más eficaz. A continuación, los usuarios marcados pueden ser informados de nuevo al equipo de ingeniería para una investigación posterior.

En la tabla siguiente se enumeran algunos métodos comunes para administrar y corregir errores de colocación.

| Remediación                              | Instrucciones                      |
|------------------------------------------|-------------------------------|
| **Red/Internet**                         | **Congestión**: trabaje con el equipo de red para supervisar el ancho de banda en compilaciones o subredes específicas para confirmar que hay problemas con la sobreutilización. Si confirma que hay congestión de red, considere la posibilidad de aumentar el ancho de banda para esa compilación o aplicar QoS. Use los [informes de resumen de Quality Poor Stream](#quality-investigations) que se incluyen para revisar las subredes del problema en busca de problemas con vibración, latencia y pérdida de paquetes, ya que suelen preceder a una transmisión caída.<br><br>**QoS**: Si aumentar el ancho de banda no es práctico o resulta prohibitivo, considere la posibilidad de implementar QoS. Esta herramienta es muy eficaz para administrar el tráfico congestionado y puede garantizar que los paquetes multimedia de la red administrada tienen prioridades por encima del tráfico no multimedia. Como alternativa, si no hay evidencia clara de que el ancho de banda sea el culpable, considere estas soluciones:<ul><li>[Instrucciones de QoS de Microsoft Teams](qos-in-teams.md)</li></ul><br>**Realizar una evaluación de preparación de red**: una evaluación de red proporciona detalles sobre el uso de ancho de banda esperado, cómo hacer frente a los cambios de ancho de banda y red, y prácticas de red recomendadas para Teams y Skype Empresarial. Si usa la tabla anterior como origen, tiene una lista de edificios o subredes que son excelentes candidatos para una evaluación.<ul><li>[Preparar la red de la organización para Microsoft Teams](prepare-network.md)</li></ul> |
| **Clientes (solo Skype Empresarial en línea)** | Algunos clientes de Skype Empresarial más antiguos han conocido problemas documentados con la confiabilidad de los medios. Revise los informes de análisis de llamadas de varios usuarios afectados o cree un informe personalizado de la tabla Versión del cliente en el CQD filtrado por compilaciones o subredes específicas con la medida % de error total de llamadas interrumpidas. Esta información le ayudará a comprender si existe una relación entre las llamadas cae en esa compilación específica y una versión específica del cliente.     |
| **Dispositivos**                                  |Si los dispositivos son los responsables de los problemas de calidad de las llamadas, considere la posibilidad de actualizar los dispositivos infractores. Lea [Teléfonos para Teams para](./devices/phones-for-teams.md) obtener más información. |
| **Comportamiento del usuario**                            | Si determina que ni la red, los dispositivos ni los clientes son el problema, considere la posibilidad de desarrollar una estrategia de adopción de usuarios para educar a los usuarios sobre la mejor manera de unirse a reuniones y salir de ellas. Un usuario de Teams y Skype Empresarial más inteligente producirá una mejor experiencia de usuario para todos los participantes de la reunión. Por ejemplo, un usuario que pone su portátil en suspensión (cerrando la tapa) sin salir de la reunión se clasificará como una llamada inesperada.   |

## <a name="quality-investigations"></a>Investigaciones de calidad

El siguiente paso para evaluar el estado de la calidad del audio en toda la organización es investigar el uso de proxy, TCP y velocidad de transmisión mala (PSR). Es importante recordar que los datos del CQD no le proporcionan una causa raíz específica, sino que le proporcionan áreas de problemas probables para iniciar una conversación de colaboración con los equipos adecuados para las actividades de corrección. 

> [!NOTE]
> No todos los informes incluidos en las plantillas se tratan en este artículo; sin embargo, los métodos de investigación que se explican a continuación seguirán aplicándose para esos informes. Consulte la descripción del informe individual para obtener más información. 

### <a name="quality"></a>Calidad

Los porcentajes de PSR se usan para indicar si la organización cumple los objetivos métricos definidos para un área de enfoque determinada. Es importante tener en cuenta que incluso si los porcentajes de alto nivel están dentro del objetivo definido, las subredes o edificios individuales podrían no cumplir los objetivos definidos y, por lo tanto, necesitan una investigación más exhaustiva. Por ejemplo, si el porcentaje general de PSR de audio es del 2 por ciento en abril, lo que cumple el objetivo de muestra, los edificios individuales y subredes podrían seguir teniendo experiencias deficientes, dependiendo de la distribución general de ese 2 por ciento. 

Para evaluar el porcentaje de transmisiones malas, use los informes de calidad. Se proporcionan varios informes de calidad para revisar las métricas de las salas generales, de conferencias, de dos partes, llamadas RTC, VPN y salas de reuniones. Se proporcionan informes mensuales, semanales y diarios para ayudar en este proceso. Los informes semanales y diarios se limitan a la plantilla Redes administradas para aumentar su eficacia y reducir el ruido. 

#### <a name="quality-trend-analysis"></a>Análisis de tendencias de calidad

Los informes de tendencias muestran información de calidad a lo largo del tiempo y se usan para ayudar a identificar y comprender las tendencias de calidad dentro de cada área de interés. Como se mencionó anteriormente, hay árboles de informes incluidos en las plantillas para investigar la calidad; conferencias, llamadas RTC, VPN y salas de reuniones. Para analizar la calidad, el proceso de investigación es el mismo. Sin embargo, le recomendamos que empiece con las conferencias primero, ya que cualquier mejora en la calidad de la conferencia también afectará positivamente a todas las demás áreas. 

> [!Note]
> Investigar llamadas RTC, llamadas de dos partes y salas de reuniones es similar a investigar conferencias. El objetivo es aislar los edificios o subredes que tienen la peor calidad e identificar el motivo de la mala calidad.

> [!Important]
> Los informes basados en VPN se filtran mediante la dimensión Second VPN. Esta dimensión requiere que el adaptador de red VPN se registre correctamente como un adaptador de acceso remoto. Los proveedores de VPN no usan esta marca de forma confiable y su kilometraje variará en función del proveedor de VPN implementado en su organización. Modifique los informes de [VPN](CQD-upload-tenant-building-data.md#vpn) si es necesario usando el nombre de la red o del edificio.

##### <a name="investigation"></a>Investigación

Al usar estos informes, puede responder a las siguientes preguntas:

-   ¿Cuál es el PSR total del mes actual?
-   ¿El PSR está por debajo de la métrica de objetivo definida?
-   ¿El PSR es peor o mejor que el mes anterior?
-   ¿La tendencia de PSR está aumentando, estable o disminuyendo?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo necesario para investigar utilizando los informes secundarios para buscar edificios o subredes que puedan necesitar investigación. Aunque el PSR general podría estar por debajo de la métrica objetivo, a menudo el PSR para uno o más edificios o redes está por encima de la métrica y necesita corrección.

#### <a name="quality-investigations"></a>Investigaciones de calidad

Los informes de resumen de calidad ofrecen una visión más profunda de lo que ha contribuido a que las transmisiones se clasifiquen como malas y ayudan a aislar áreas problemáticas en la red administrada.

Aunque las dimensiones utilizadas pueden diferir ligeramente entre informes, cada informe incluirá medidas para las transmisiones totales, las transmisiones malas totales, el PSR y la mala calidad debido a. Se han creado informes para cada área de interés: conferencias, llamadas RTC, VPN y salas de reuniones. La plantilla Red administrada incluye informes adicionales para aprovechar la información de ubicación cargada a través del archivo de compilación.


> [!Note]
> Las subredes comunes son difíciles de evaluar debido a su uso generalizado. Se ha agregado un informe independiente que muestra la IP pública del cliente (Second Reflexive Local IP) a la plantilla Todas las redes para ayudar con la corrección de oficinas que usan redes comunes.


![Captura de pantalla que muestra el resumen de secuencia de audio deficiente.](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Remediación

Centre sus esfuerzos de corrección en edificios o subredes que tienen el mayor volumen de transmisiones, ya que esto maximizará el impacto y ayudará a mejorar la experiencia del usuario rápidamente. Use las mediciones de vibración, pérdida de paquetes y tiempo de ida y vuelta (RTT) para comprender lo que está contribuyendo a la mala calidad (es posible que haya más de un problema):

-   **Vibración**: Los paquetes multimedia llegan a diferentes velocidades, lo que hace que un altavoz suene robótico.
-   **Pérdida de paquetes**: los paquetes multimedia se eliminan, lo que crea el efecto de que falten palabras o sílabas.
-   **RTT**: Los paquetes multimedia tardan mucho tiempo en llegar a su destino, lo que crea un efecto walkie-talkie.

Para ayudar a investigar problemas de calidad, use el [análisis de llamadas por usuario](use-call-analytics-to-troubleshoot-poor-call-quality.md). Con Análisis de llamadas, puede ver el informe de llamadas de un usuario o una conferencia específica. Este informe contendrá datos EUII/PII y es útil cuando busque la causa de un error. Después de saber qué edificio se ve afectado, debería ser sencillo localizar a los usuarios de ese edificio. 

No olvide comunicar a su departamento de soporte técnico que estas redes están experimentando problemas de calidad, por lo que pueden evaluar y responder rápidamente a las llamadas entrantes.

| Remediación                              | Instrucciones                         |
|------------------------------------------|----------------------------------|
| **Redes**                                 | **Congestión**: una red sobreutilizada o poco aprovisionada puede causar problemas con la calidad de los medios. Trabaje con el equipo de red para determinar si las conexiones de red desde el usuario al punto de salida de Internet tienen suficiente ancho de banda como para admitir medios. <br><br>**Realizar una evaluación de preparación de red**: una evaluación de red proporciona detalles sobre el uso de ancho de banda esperado, cómo hacer frente a los cambios de ancho de banda y red, y prácticas de red recomendadas para Teams y Skype Empresarial. Si usa la tabla anterior como origen, tiene una lista de edificios o subredes que son excelentes candidatos para una evaluación.<ul><li>[Preparar la red de la organización para Microsoft Teams](prepare-network.md)</li></ul>|
| **Calidad de servicio (QoS)**  | QoS es una herramienta probada que ayuda a priorizar paquetes en una red congestionada para asegurarse de que llegan a su destino intacto y puntual. Considere la posibilidad de implementar QoS en toda la organización para maximizar la calidad de la experiencia del usuario cuando se limite el ancho de banda. QoS ayudará a resolver problemas que suelen estar asociados con altos niveles de pérdida de paquetes y, en menor medida, la vibración y los tiempos de ida y vuelta.<ul><li>[Instrucciones de QoS de Teams](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | Wi-Fi pueden tener un impacto significativo en la calidad de las llamadas. Wi-Fi implementaciones no suelen tener en cuenta los requisitos de red para los servicios VoIP y suelen ser un origen de mala calidad. Para obtener más información sobre la optimización de la infraestructura de Wi-Fi, vea [este artículo sobre la planificación de Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Controlador de red inalámbrica**: asegúrate de que los controladores de red inalámbrica estén actualizados. Esto ayudará a mitigar la mala experiencia del usuario relacionada con un controlador obsoleto. Muchas organizaciones no incluyen controladores de red inalámbrica en sus ciclos de revisión y estos controladores pueden dejar de compartirse durante años. Muchos problemas de conexión inalámbrica se resuelven asegurándose de que los controladores de red inalámbrica estén actualizados.<br><br>**WMM**: Las extensiones multimedia inalámbricas (WMM), también conocidas como Wi-Fi Multimedia, proporcionan características básicas de QoS a las redes inalámbricas. Las redes inalámbricas modernas deben admitir muchos dispositivos. Estos dispositivos compiten por el ancho de banda y pueden producir problemas de calidad para los servicios VoIP, donde la velocidad y latencia son esenciales. Consulte a su proveedor de servicios inalámbricos para obtener información específica y considere la posibilidad de implementar WMM en su red inalámbrica para priorizar los medios de Skype Empresarial y Teams.<br><br>**Densidad de puntos de acceso**: los puntos de acceso pueden estar demasiado separados o no estar en una ubicación ideal. Para minimizar las posibles interferencias, coloque puntos de acceso adicionales en salas de conferencias y en ubicaciones que no estén obstruidas por paredes u otros objetos donde la señal de Wi-Fi sea débil.<br><br>**2,4 GHz frente a 5 GHz**: 5 GHz proporciona menos interferencias en segundo plano y velocidades más altas, y debe priorizarse al implementar VoIP a través de Wi-Fi. Sin embargo, 5 GHz no es tan fuerte como 2,4 GHz y no penetra en las paredes tan fácilmente. Revise el diseño del edificio para determinar en qué frecuencia puede confiar para obtener la mejor conexión. |
|**Dispositivo de red** | Las organizaciones más grandes podrían tener cientos de dispositivos repartidos por la red. Trabaje con su equipo de red para asegurarse de que los dispositivos de red desde el usuario a Internet se mantengan y estén actualizados. |
| **VPN**  | Tradicionalmente, los dispositivos VPN no están diseñados para administrar las cargas de trabajo de medios en tiempo real. Algunas configuraciones de VPN prohíben el uso de UDP (que es el protocolo preferido para medios) y dependen solo de TCP. Considere la posibilidad de implementar una solución de túnel dividido de VPN para ayudar a reducir la VPN como fuente de mala calidad. |
| **Clientes** <br>(solo Skype Empresarial en línea) | Asegúrese de que todos los clientes se actualizan periódicamente. |
| **Dispositivos** | Si los dispositivos son los responsables de los problemas de calidad de las llamadas, considere la posibilidad de actualizar los dispositivos infractores. Lea [Teléfonos para Teams para](./devices/phones-for-teams.md) obtener más información. |
| **Controladores** | Los controladores de red de parches (Ethernet y Wi-Fi), audio, vídeo y USB deben formar parte de tu estrategia general de administración de revisiones. Muchos problemas de calidad se resuelven actualizando los controladores. |
| **Salas de reuniones en Wi-Fi** | Recomendamos encarecidamente que los dispositivos de la sala de reuniones estén conectados a la red mediante al menos una conexión Ethernet de 1 Gbps. Los dispositivos de salas de reuniones suelen incluir varias secuencias de audio y vídeo, junto con el contenido de la reunión, como el uso compartido de la pantalla, y tienen requisitos de red más altos que otros equipos o puntos de conexión de Skype Empresarial. Las salas de reuniones son, por definición, dispositivos fijos en los que Wi-Fi ofrecen un beneficio solo durante la instalación.<br><br>Las salas de reuniones deben tratarse con más cuidado y atención para garantizar que la experiencia con estos dispositivos cumpla o supere las expectativas. Por lo general, los problemas de calidad con las salas de reuniones se van a escalar rápidamente, ya que a menudo los usa el personal de nivel superior.<br><br>Con todas las cosas siendo iguales (aparte de la comodidad), Wi-Fi rendimiento es a menudo menor que una conexión por cable. Con el auge de las directivas "traer tu propio dispositivo" y la proliferación de portátiles, los puntos de acceso Wi-Fi a menudo se sobreutilizan. Es posible que no se prioricen los medios en tiempo real en las redes Wi-Fi, lo que puede provocar problemas de calidad durante los picos de uso. Este uso intensivo puede coincidir con una reunión en la que podría haber una docena de personas a la asistencia, cada una con su propio portátil y smartphone, todos conectados al mismo punto de acceso Wi-Fi que el dispositivo de la sala de reuniones.<br><br>Wi-Fi solo debe considerarse como una solución temporal, para una instalación móvil o cuando Wi-Fi se haya aprovisionado correctamente para admitir medios basados en tiempo real y de clase empresarial. |


### <a name="tcp"></a>TCP 

El Protocolo de control de transmisión (TCP) se considera un transporte de conmutación por error y no el transporte principal que desea para medios en tiempo real. La razón por la que se trata de un transporte de conmutación por error se debe a la naturaleza estatal de TCP. Por ejemplo, si se realiza una llamada en una red latente y se retrasan los paquetes multimedia, entonces los paquetes de hace unos pocos segundos, que ya no son útiles, compiten por el ancho de banda para llegar al receptor, lo que puede empeorar una mala situación. Esto hace que el sanador de audio cose y estire el audio, lo que produce artefactos audibles, a menudo en forma de vibración.

Los informes de esta sección no distinguen entre transmisiones buenas y malas. Dado que UDP es el preferido, los informes buscan el uso de TCP para el uso compartido de pantalla basado en audio, vídeo y vídeo (VBSS). Se proporcionan velocidades de transmisión deficientes para ayudar a comparar la calidad UDP y la calidad de TCP, de modo que pueda centrar sus esfuerzos en los que el impacto sea mayor. El uso de TCP se debe principalmente a reglas de firewall incompletas. Para obtener más información sobre las reglas de firewall para Teams y Skype Empresarial Online, consulte [Microsoft 365 y Office 365 DIRECCIONES URL e intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).

> [!Note]
> Audio, vídeo y VBSS prefieren UDP como su transporte principal. La carga de trabajo de uso compartido de aplicaciones RDP heredada solo usa TCP.

#### <a name="tcp-usage"></a>Uso de TCP

Los informes TCP indican el uso total de TCP en los últimos siete meses. Todos los informes adicionales de esta sección se centrarán en restringir edificios y subredes específicos en los que se utiliza con más frecuencia TCP. Los informes independientes están disponibles tanto para las transmisiones de conferencia como para las de dos entidades.

![Gráfico que muestra el porcentaje de transmisiones de audio que usan TCP.](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Investigación

Al usar este informe, puede responder a las siguientes preguntas:

-   ¿Cuál es el volumen total de transmisiones TCP del mes actual?
-   ¿Es peor o mejor que el mes anterior?
-   ¿Aumenta, mantiene o disminuye la tendencia de uso de TCP?
-   ¿Es lo mismo el PSR TCP que mi PSR general?

Si observa que la tendencia del uso de TCP está aumentando o por encima del uso mensual normal, tómese el tiempo necesario para investigar usando los subinformulario para buscar edificios o redes que puedan necesitar corrección. Lo ideal es que desee tantas sesiones de audio basadas en TCP como sea posible en la red administrada.

#### <a name="tcp-vs-udp"></a>TCP frente a UDP

Este informe identifica el volumen de informes de uso de TCP frente a UDP del último mes para el uso compartido de pantalla basado en audio, vídeo y vídeo (VBSS). 

![Informe que muestra el volumen de transmisiones que usan TCP frente a UDP.](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Análisis

Aunque quiere que el uso de TCP sea lo más bajo posible, es posible que vea un poco de uso de TCP en una implementación en buen estado. TCP por sí mismo no contribuye a una llamada deficiente, por lo que se proporcionan tarifas de transmisión para ayudar a identificar si el uso de TCP es un factor que contribuye a la mala calidad. 

#### <a name="tcp-investigations"></a>Investigaciones TCP

En las plantillas proporcionadas del CQD, vaya a los informes de secuencias TCP por compilación y subred mediante la plantilla Redes administradas o Todas las redes. Para investigar el uso de TCP, el proceso es el mismo, por lo que centraremos la discusión aquí en la conferencia.


##### <a name="remediation"></a>Remediación

Este informe identifica edificios y subredes específicos que contribuyen al volumen de uso de TCP. También se incluye un informe adicional para identificar la IP de Microsoft Relay que se usó en la llamada para ayudar a aislar las reglas de firewall que faltan. Centre los esfuerzos de corrección en los edificios que tienen el mayor volumen de transmisiones TCP para maximizar el impacto.

La causa más habitual del uso de TCP es que faltan reglas de excepción en firewalls o servidores proxy. En la siguiente sección hablaremos de servidores proxy, por lo que por ahora puede centrar sus esfuerzos en los firewalls. Mediante el edificio o la subred proporcionada, puede determinar qué firewall debe actualizarse.

| Remediación        | Instrucciones     |
|--------------------|--------------------------------------|
| Configurar el firewall | Comprueba que [los puertos y las direcciones IP de Microsoft 365 o Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) están excluidos del firewall. En el caso de problemas de TCP relacionados con los medios, centre sus esfuerzos iniciales en lo siguiente:<ul><li>Compruebe que las subredes multimedia del cliente 13.107.64.0/18 y 52.112.0.0/14 están en las reglas del firewall.</li><li>Los puertos UDP 3478-3481 son los puertos multimedia necesarios y deben abrirse; de lo contrario, el cliente volverá a fallar al puerto TCP 443.</li></ul> |
| Verificar             | Use la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si hay problemas con la conectividad a direcciones IP y puertos específicos de Microsoft 365 o Office 365 del edificio o subred afectados.    |

### <a name="http-proxy"></a>Proxy HTTP

Los servidores proxy HTTP no son la ruta preferida para establecer sesiones multimedia por una gran variedad de razones. Muchas contienen características de inspección profunda de paquetes que pueden impedir que se completen las conexiones al servicio e introducir interrupciones. Además, casi todos los servidores proxy fuerzan TCP en lugar de permitir UDP, que se recomienda para una calidad de audio óptima.

Siempre le recomendamos que configure el cliente para conectarse directamente a Teams y Skype Empresarial servicios. Esto es especialmente importante para el tráfico basado en medios.


> [!IMPORTANT]
> Le recomendamos que cargue un [archivo de compilación válido](CQD-upload-tenant-building-data.md) para que pueda distinguir entre secuencias de audio externas al analizar el uso de proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

El informe de secuencia de proxy HTTP en esta sección de la plantilla es muy similar a los informes TCP. No se comprueba si las llamadas son malas o buenas, sino si la llamada está conectada a través de HTTP.

![Captura de pantalla del informe de transmisiones de audio que usan HTTP.](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Análisis

Quieres ver tantas transmisiones multimedia HTTP como sea posible. Si tiene transmisiones que atraviesan el proxy, consulte a su equipo de red para asegurarse de que se aplican las exclusiones adecuadas de manera que los clientes se rediringan directamente a Teams o Skype Empresarial subredes multimedia en línea.

Si solo tiene un proxy de Internet en su organización, compruebe las [direcciones URL de Microsoft 365 o Office 365 correctas y las exclusiones de intervalo de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Si hay más de un proxy de Internet configurado en su organización, utilice el subinformulario HTTP para aislar qué compilación o subred se ve afectada.

Para las organizaciones que no pueden omitir el proxy, asegúrese de que el cliente de Skype Empresarial está configurado para iniciar sesión correctamente cuando está situado detrás de un proxy, como se describe en el artículo [Skype Empresarial debe usar el servidor proxy para iniciar sesión en lugar de intentar la conexión directa](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Investigaciones de proxy HTTP

Este informe identifica edificios y subredes específicos que contribuyen al uso de HTTP.


##### <a name="remediation"></a>Remediación

Se [recomienda](proxy-servers-for-skype-for-business-online.md) omitir siempre servidores proxy para Skype Empresarial y Teams, especialmente el tráfico multimedia. Los servidores proxy no hacen que Skype Empresarial sean más seguros, ya que su tráfico ya está cifrado. Los problemas relacionados con el rendimiento se pueden introducir en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos producirán una experiencia negativa con el audio, el vídeo y el uso compartido de la pantalla, donde las transmisiones en tiempo real son esenciales.

La causa más habitual del uso de HTTP es que faltan reglas de excepción en los servidores proxy. Mediante el uso de la compilación o subred proporcionada, puede determinar rápidamente qué proxy debe configurarse para la omisión de medios.

Compruebe que los [FQDN de Microsoft 365 o Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) necesarios se agregan a una lista de permitidos en el proxy.

## <a name="endpoint-investigations"></a>Investigaciones de puntos de conexión

Esta sección se centra en las tareas de creación de informes sobre las versiones de cliente y el uso de dispositivos certificados. Los informes están disponibles para describir el uso de las versiones de cliente, el tipo de cliente, los dispositivos de captura y los controladores (micrófono), los dispositivos de captura de vídeo y las versiones de proveedor y controlador de Wi-Fi.

> [!NOTE]
> No todos los informes incluidos en las plantillas se tratan en este artículo; sin embargo, los métodos de investigación explicados a continuación siguen siendo aplicables. Consulte la descripción del informe individual para obtener más información.

### <a name="client-versions"></a>Versiones de cliente

Estos informes se centran en identificar Skype Empresarial versiones de cliente en uso y su volumen relativo en el entorno.

> [!IMPORTANT]
> Actualmente, los clientes de Teams se distribuyen y actualizan automáticamente a través de azure Content Delivery Network y se mantendrán actualizados por el servicio. Como resultado, no es necesario supervisar las versiones de cliente de Teams (a menos que desactive la actualización automática, que no se recomienda).

A menos que excluya los datos de los participantes federados, estos informes incluirán telemetría de cliente de los puntos de conexión federados. Para excluir los puntos de conexión federados, debe agregar un filtro de consulta para el Segundo id. de inquilino establecido en el id. de [inquilino](CQD-data-and-reports.md#how-to-find-your-tenant-id) de su organización. Como alternativa, puede usar un [filtro de dirección URL](CQD-data-and-reports.md#url-filters) para excluir la telemetría de participantes federados.



#### <a name="remediation"></a>Remediación

Una parte esencial de la conducción de experiencias de usuario de alta calidad es garantizar que los clientes administrados estén ejecutando versiones actualizadas de Skype Empresarial, además de garantizar que los controladores de audio, vídeo, red y USB compatibles estén actualizados. Esto ofrece varios beneficios, entre ellos: 

-   Es más fácil administrar algunas versiones que muchas versiones.
-   Proporciona un nivel de coherencia de la experiencia.
-   Facilita la solución de problemas de calidad y facilidad de uso de las llamadas.
-   Microsoft realiza continuamente mejoras generales y optimizaciones en todo el producto. Garantizar que los usuarios reciban estas actualizaciones reduce el riesgo de que se  creen en un problema que ya se ha resuelto.

Limitar la implementación a versiones de cliente con menos de seis meses de antigüedad mejorará la experiencia general del usuario y mejorará la capacidad de administración al reducir el número de versiones que necesitan ser compatibles.

Si solo usa Hacer clic y ejecutar de Office, estará automáticamente dentro de la ventana de seis meses. No es necesario realizar ninguna otra acción.

Si tiene una combinación de paquetes de Hacer clic y ejecutar e instalador (MSI), puede usar el informe para comprobar que los clientes MSI se actualizan periódicamente. Si observa que los clientes se están retrasando, trabaje con el equipo responsable de administrar las actualizaciones de Office y asegúrese de que aprueban e implementan revisiones de cliente periódicamente.

También es importante tener en cuenta y asegurarse de que los controladores de red, vídeo, USB y audio también se estén aplicando revisiones. Puede ser fácil pasar por alto estos controladores y no incluirlos en su estrategia de administración de parches.

Los números de versión de Skype Empresarial pueden encontrarse a través de los siguientes vínculos:

-   [Información de la versión de las actualizaciones de Aplicaciones Microsoft 365](/officeupdates/release-notes-office365-proplus)
-   [Historial de actualizaciones de Aplicaciones Microsoft 365 para empresas](/officeupdates/update-history-office365-proplus-by-date)
-   [Descargas y actualizaciones de Skype Empresarial](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivos

Para usar el informe de dispositivo de micrófono, necesitamos entender el concepto de la puntuación de opinión media (MOS). MOS es la medición de oro estándar para medir la calidad de audio percibida. Se representa como una clasificación entera de 0 a 5.

La base de todas las medidas de calidad de la voz es la forma en que una persona percibe la calidad de la voz. Debido a que se ve afectado por la percepción humana, es intrínsecamente subjetiva. Existen varias metodologías diferentes para las pruebas subjetivas. La mayoría de las medidas de calidad de voz se basan en una escala de clasificación de categorización absoluta (ACR).

En una prueba subjetiva de ACR, un número estadísticamente significativo de personas valora su calidad de experiencia en una escala de 1 (mala) a 5 (excelente). El promedio de las puntuaciones es el MOS. El MOS resultante depende de la gama de experiencias que se expusieron al grupo y del tipo de experiencia que se va a clasificar.

Dado que no es práctico realizar pruebas subjetivas de calidad de voz para un sistema de comunicación en directo, Microsoft Teams y Skype Empresarial generar valores MOS mediante algoritmos avanzados para predecir objetivamente los resultados de una prueba subjetiva.

El conjunto disponible de MOS y métricas asociadas proporciona una vista de la calidad de la experiencia que un dispositivo de audio entrega a los usuarios. 

Al proporcionar a los usuarios dispositivos certificados para Teams y Skype Empresarial, reduce la probabilidad de encontrar experiencias negativas debido al propio dispositivo (que es más probable, por ejemplo, con altavoces y micrófonos de portátil integrados). Para obtener más información, consulta estos artículos sobre el [programa de certificación](/SkypeForBusiness/certification/overview) y el [catálogo de soluciones de partners](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Los informes de dispositivos se usan para evaluar el uso del dispositivo por volumen y puntuación MOS (solo audio), y se pueden encontrar en las plantillas que acompañan en Clientes & Dispositivos. 

> [!IMPORTANT]
> A menos que excluya los datos de los participantes federados, estos informes incluirán telemetría de cliente de los puntos de conexión federados. Para excluir los puntos de conexión federados, debe agregar un filtro de consulta para **el Segundo id** . de inquilino establecido en el id. de [inquilino](CQD-data-and-reports.md#how-to-find-your-tenant-id) de su organización. ALternatively, you can use a [URL filter](CQD-data-and-reports.md#url-filters) to exclude federated participant telemetry.


> [!Note]
> Es posible que al ver este informe observes que ves el mismo dispositivo notificado varias veces. Esto se debe a la forma en que se notifica que el dispositivo se notifica al CQD. Las diferencias en la configuración regional del hardware y del sistema operativo provocan diferencias en la forma en que se notifican los datos del dispositivo.

##### <a name="remediation"></a>Remediación

Por lo general, tendrás que detectar y eliminar gradualmente los dispositivos no certificados y reemplazarlos por dispositivos certificados. Algunas consideraciones al revisar los informes del dispositivo son:

-   ¿Los dispositivos en uso están certificados para Teams y Skype Empresarial? 
-   Puede identificar los usuarios de un dispositivo específico mediante el [análisis de llamadas por usuario](use-call-analytics-to-troubleshoot-poor-call-quality.md). Comprueba que tienen los controladores de dispositivo más recientes y que su dispositivo no está conectado a través de un concentrador USB o una base de acoplamiento. 
-   ¿Cuántas versiones diferentes de varios controladores están en uso? ¿Se les revisa periódicamente? Garantizar que los controladores de audio, vídeo y Wi-Fi se revisan periódicamente ayudará a eliminar estos controladores como fuente de problemas de calidad y a hacer que la experiencia del usuario sea más predecible y coherente.

##### <a name="audio"></a>Audio

La siguiente tarea es determinar el uso general de [los dispositivos de audio certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Recomendamos que al menos el 80 % de todas las transmisiones de audio usen un dispositivo de audio certificado. Esto se consigue mejor exportando el informe de dispositivos de micrófono a Excel para calcular el uso de dispositivos certificados o aprobados. Las organizaciones suelen mantener una lista de todos los dispositivos aprobados, por lo que filtrar y ordenar los datos debería ser sencillo.

##### <a name="video"></a>Vídeo

Los controladores de vídeo también son importantes para mantenerse actualizados. Garantizar que las tarjetas de vídeo se revisan periódicamente ayudará a excluir los controladores de vídeo como fuente de mala calidad para las transmisiones de vídeo. El uso de [dispositivos de vídeo certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) le ayudará a garantizar una experiencia de usuario fluida y de alta calidad. Es preferible usar dispositivos de vídeo que admitan codificación nativa H.264 para reducir el uso de la CPU durante las videoconferencias.

##### <a name="wi-fi"></a>Wi-Fi

Wi-Fi controladores también deben ser parcheados en una cadencia regular y deben incluirse en su estrategia de administración de parches. Muchos problemas de calidad se pueden corregir manteniendo los controladores Wi-Fi actualizados. Para obtener más información sobre la optimización de la infraestructura de Wi-Fi, vea [este artículo sobre la planificación de Wi-Fi](/skypeforbusiness/certification/networking-wifi).


## <a name="related-topics"></a>Temas relacionados

[Usar Advisor para Teams](use-advisor-teams-roll-out.md)

[Preparar la red para Teams](prepare-network.md)

[Principios de conectividad de red Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Análisis e informes de Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Administrar los dispositivos en Teams](./devices/device-management.md)

[Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar datos de inquilinos y compilación](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)

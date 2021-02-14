---
title: Usar el CQD para administrar la calidad de las llamadas y reuniones en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Obtenga información sobre cómo analizar y administrar el rendimiento multimedia en tiempo real en Microsoft Teams mediante el panel de calidad de llamadas (CQD).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: f4221b08742d27b4dbe360dfd345142795640588
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581191"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Usar el CQD para administrar la calidad de las llamadas y reuniones en Microsoft Teams 

Este artículo le ayudará (el administrador o el soporte técnico y los ingenieros del departamento de soporte técnico) a desarrollar un proceso para supervisar y mantener la calidad de las llamadas y reuniones de su organización mediante el Panel de calidad de llamadas (CQD) de Microsoft Teams. Nuestras instrucciones hacen hincapié en los escenarios de calidad de audio, ya que las mejoras de red que realice para mejorar la experiencia de audio se traducirán en mejoras en vídeo y en uso compartido.

Clave de esta guía son las dos plantillas [del CQD](https://aka.ms/QERtemplates) seleccionadas ( se recomienda que las descargue antes de seguir las instrucciones de este artículo).

En este artículo se supone que ya ha [configurado el CQD.](turning-on-and-using-call-quality-dashboard.md)


## <a name="categories-to-monitor-and-maintain"></a>Categorías para supervisar y mantener

Una vez que haya lanzado las reuniones y voz en Teams, necesitará un plan para la supervisión y mantenimiento continuos. Si lo hace, se asegurará de que Teams siempre funciona correctamente. Este plan debe incluir las áreas clave que se muestran a continuación. También debe establecer objetivos de métricas de calidad y un plan para la solución de problemas y la solución de problemas cuando se tienen.

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
<p>Dividir las métricas por llamadas internas (dentro de la organización, como VPN, WiFi, cableada) o llamadas externas</p>
<p>Dividir las métricas mediante creación o red</p>
<p>Llamadas VPN</p>
<p>Llamadas con TCP, UDP o proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Confiabilidad de llamadas</strong></td>
<td><p>Identificar y corregir cualquier problema de red o firewall</p>
<p>Obtenga información sobre los porcentajes de configuración de llamadas y errores de entrega</p>
<p>Obtenga información sobre dónde se producen la mayoría de los errores de configuración y colocación de llamadas</p>
</td>
</tr>
<tr class="odd">
<td><strong>Encuesta de usuario</strong></td>
<td>
<p>Usar Calificar mis datos de llamada para obtener información sobre la experiencia real de los usuarios</p>
<p>¿Dónde están teniendo lugar las malas experiencias?</p>
<p>Correlacionar la mala experiencia con la calidad, la confiabilidad y los dispositivos de las llamadas</p>
</td>
</tr>
<tr class="even">
<td><strong>Dispositivos</strong></td>
<td><p>Saber qué micrófonos y altavoces se usan con más frecuencia y su impacto en la calidad de la llamada</p>
<p>¿Se revisan periódicamente los controladores compatibles de audio, vídeo, USB y WiFi?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clientes</strong></td>
<td>
<p>Información sobre los tipos y versiones de cliente que se usan y su impacto en la calidad y la confiabilidad de las llamadas  </p>
</ol></td>
</tr>
</tbody>
</table>

Al evaluar y corregir continuamente las áreas descritas en este artículo, puede reducir su potencial para afectar negativamente a los usuarios. La mayoría de los problemas de usuario se pueden agrupar en las siguientes categorías:

-   Una configuración de proxy o firewall incompleta
-   Una cobertura Wi-Fi insuficiente
-   Un ancho de banda insuficiente
-   VPN
-   Controladores y versiones de cliente incoherentes o obsoletas
-   Dispositivos de audio integrados o sin optimizar
-   Dispositivos de red o subred problemáticos

Mediante una correcta planificación y diseño antes de implementar Teams o Skype Empresarial Online, puede reducir la cantidad de esfuerzo que será necesario para mantener experiencias de alta calidad.

Este artículo se centra en usar el panel de calidad de llamadas (CQD) en línea como herramienta principal para informar e investigar cada área, con un énfasis especial en el audio para maximizar la adopción y el impacto. Las mejoras realizadas en la red para mejorar la experiencia de audio también se traducirán directamente en mejoras en el uso compartido de escritorio y vídeo.

Para acelerar la evaluación, se proporcionan dos plantillas [del CQD](https://aka.ms/qertemplates) seleccionadas: una es para administrar todas las redes y la otra solo se filtra para redes administradas (internas). Aunque los informes de plantilla Todas las redes están configurados para mostrar la información de creación y red, aún se pueden usar mientras trabaja para recopilar y cargar información de creación. La carga de información de creación en el CQD permite al servicio mejorar la creación de informes agregando información personalizada de construcción, red y ubicación al diferenciar las subredes internas de las externas. Para obtener más información, lea [Asignación de creación.](CQD-building-mapping.md)

### <a name="intended-audience"></a>Público previsto

Este artículo está destinado a las partes interesadas de los clientes y asociados con roles como, por ejemplo, responsable de colaboración/arquitecto, consultor, especialista en administración y adopción de cambios, jefe de soporte técnico, cliente potencial de red, jefe de escritorio y administrador de TI.

Este artículo también está diseñado para ser utilizado por los campeones de calidad designados. Para obtener más información, consulte [el rol de Campeón de calidad.](4-envision-plan-my-service-management.md#the-quality-champion-role)


## <a name="what-is-quality"></a>¿Qué es la calidad?

En este contexto, la calidad es una combinación de métricas de servicio y experiencia del usuario.


### <a name="service-metrics"></a>Métricas de servicio

Las métricas del servicio constan de métricas específicas basadas en clientes. Durante cada llamada, el cliente recopila la telemetría de la llamada y envía un informe al final de cada llamada, al que posteriormente se puede acceder en el CQD o en el análisis de llamadas por [usuario.](set-up-call-analytics.md) Estas métricas incluyen (pero no están limitadas a):

-   Poor Stream (entrante y saliente)
-   Setup Failure Rate
-   Tasa de errores de colocación


#### <a name="poor-stream-rate"></a>Poor stream rate

La tasa de transmisión deficiente (PSR) representa el porcentaje general de transmisiones que tienen mala calidad en la organización. Esta métrica está pensada para resaltar las áreas en las que su organización puede concentrar el esfuerzo [](#managed-versus-unmanaged-networks) para lograr el mayor impacto en la reducción de este valor y la mejora de la experiencia del usuario. Por eso las redes administradas son el principal foco en la búsqueda de PSR. Los usuarios externos también son importantes, pero la investigación difiere en función de la organización. Considere la posibilidad de proporcionar procedimientos recomendados para usuarios externos e investigar llamadas externas de forma independiente de la organización general.

La medición real del CQD varía según la carga de trabajo, pero  para el propósito de este artículo, nos centramos principalmente en la medición del porcentaje de audio deficiente. PSR está compuesta por las cinco medias de la métrica de red que se describen en la tabla siguiente. Para que una transmisión se clasifique como mala, solo una métrica debe superar el umbral definido. El CQD proporciona el estado "Poor Due To..." (Debido a..." medidas para comprender mejor qué condición ha provocado que la transmisión se clasificara como mala. Para obtener más información, lea [la clasificación de stream en el CQD.](stream-classification-in-call-quality-dashboard.md)

> [!Note]
> El CQD proporciona "Poor due to..." (Mala información sobre..." medidas para comprender mejor qué condición ha provocado que la transmisión se clasificara como mala.


##### <a name="audio-poor-quality-metrics"></a>Métricas de calidad deficiente de audio

| Promedio métrico     | Descripción     | Experiencia de usuario |
|-------------|-----------------|-----------------|
| Jitter \> 30 ms        | Este es el cambio medio de retraso entre paquetes sucesivos. Teams y Skype Empresarial se pueden adaptar a algunos niveles de vibración a través del almacenamiento en búfer. Solo cuando la vibración supera el almacenamiento en búfer, un participante observa los efectos de la vibración.      | Los paquetes que llegan a diferentes velocidades hacen que la voz del orador suene envolvente.   |
| Porcentaje de pérdida de \> paquetes del 10 % o 0,1        | Esto se suele definir como un porcentaje de paquetes que se pierden. La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individuales que casi no tienen ningún impacto a las pérdidas de ráfagas de un solo vistazo que provocan el corte completamente del audio.     | Los paquetes que se descartan y no llegan al destino previsto provocan espacios en los medios, lo que provoca sílabas y palabras perdidas, y vídeo entrecortado y uso compartido. |
| Tiempo de ida y vuelta \> 500 ms        | Este es el tiempo que se tarda en obtener un paquete IP del punto A al punto B y volver al punto A. Este retraso en la propagación de red está vinculado a la distancia física entre los dos puntos y a la velocidad de luz, e incluye gastos generales adicionales de los distintos dispositivos en la ruta de red.      | Los paquetes tardan demasiado tiempo en llegar a su destino y provocan un efecto walkie-talkie.   |
| Media de degradación NMOS \> 1,0         | Media [de degradación de la puntuación de opinión media (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) de la red durante la transmisión. Representa qué cantidad de vibración y pérdida de red ha afectado a la calidad del audio recibido que ha provocado que el NMOS se bajara en más de un punto. | Se trata de una combinación de vibración, pérdida de paquetes y, en un menor grado, mayor tiempo de ida y vuelta. El usuario puede estar experimentando una combinación de estos síntomas.   |
| Relación media de muestras ocultas \> 7 % o 0,07 | Relación media entre el número de tramas de audio con muestras ocultas generadas por la pérdida de paquetes y el número total de tramas de audio. Una muestra de audio oculta es una técnica que se usa para suavizar la transición udp que normalmente se causaría por paquetes de red descartados.      | Los valores altos indican que se aplicaron niveles significativos de ocultación de pérdidas que provocaron audio distorsionado o perdido.     |

##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>¿Por qué preferimos usar las transmisiones en lugar de las llamadas?

Las transmisiones nos permiten saber cuál de las etapas de la llamada era mala: entrantes o salientes. Cuando esté analizando el análisis de llamadas para una llamada deficiente, determine si la llamada mala se debe a la transmisión (saliente) o a la secuencia del destinatario de la llamada (entrante). Determinar qué transmisión afecta a la calidad de la llamada es aún más importante para las conferencias. Si solo analiza los datos de las llamadas, verá cuántas conferencias participa una persona, pero no verá qué personas están activas, ya que comparten la mayor parte de la pantalla.

Los datos de llamadas le proporcionan métricas de uso, pero no necesariamente le llevan a la causa principal de la mala calidad de las llamadas. Al mirar la dirección de la transmisión, puede identificar factores como una llamada que no está en una red administrada, una llamada de un no empleado (por ejemplo, un proveedor o alguien de una red diferente). En estos casos, si la conexión de red de la otra persona era mala, toda la llamada se marcará como mala. No puede hacer nada con los factores externos, por lo que estos datos no son útiles.

La dirección de stream también puede ayudarle a identificar clientes o dispositivos problemáticos.

 - Por ejemplo, si tiene un presupuesto limitado para dispositivos y desea proporcionar dispositivos solo para usuarios de audio pesado, use el informe de uso de audio (VoIP) y filtre para las transmisiones salientes y conferencias. Busque usuarios de audio de alto volumen que hablen por micrófonos integrados. Estos pueden correlacionarse con una calidad de llamada más deficiente (y es posible que desee proporcionar dispositivos de audio para estas personas). Para mayor claridad, puede filtrar por el uso de paquetes, lo que le permitirá dirigirse especialmente a los usuarios de audio de gran volumen. 

  - Otro ejemplo implica el uso compartido de la pantalla. Si un cliente usa un cliente antiguo de Teams, el rendimiento de pantalla compartida puede verse afectado. Para solucionar este problema, prioriza las actualizaciones de cliente para las personas que hacen mucho uso compartido de la pantalla.

 - Al identificar qué dirección de una transmisión está causando una mala calidad de llamada, puede determinar si tiene una QoS o un problema relacionado con el ancho de banda. Si no ha implementado completamente QoS o si solo marca paquetes en el cliente y no en la transmisión entrante, es posible que vea una calidad de llamada más deficiente. Al mirar la dirección de la transmisión, puede obtener una vista más granular de la pérdida de paquetes, la latencia o la vibración en una dirección específica. 

   - Por ejemplo, supongamos que un usuario se quejan del audio vibración cuando está conectado a una conexión por cable (vibración). Al mirar la transmisión y la dirección, puede determinar que el problema se produce en la transmisión entrante, solo para un conjunto específico de subredes. Después de proporcionar esta información a su equipo de redes, podrán localizarla con una aceleración WAN mal configurada que no omitía el tráfico multimedia. Una vez que el equipo de red vuelva a configurar la aceleración WAN, desaparecerá la vibración y mejorará la calidad de las llamadas. 


#### <a name="setup-failure-rate"></a>Setup Failure Rate

La tasa de error de  configuración, que en caso contrario se conoce como medición del porcentaje de errores en la configuración de llamadas totales en el CQD, es el número de transmisiones en las que no se pudo establecer la ruta de acceso a medios entre los puntos de conexión al comienzo de la llamada.

Esto representa cualquier transmisión multimedia que no se pudo establecer. Dada la gravedad del impacto de este problema en la experiencia del usuario, el objetivo es reducir este valor al nivel de cero lo más cerca posible. Un valor alto para esta métrica es más común en las nuevas implementaciones con reglas de firewall incompletas que en una implementación para el adulto, pero es importante tenerla en cuenta periódicamente.

Esta métrica se calcula tomando el número total de transmisiones que no han podido configurarse divididas por el número total de transmisiones en las que se ha enviado correctamente el registro de detalles de la llamada (CDR):

-   **Setup Failure Rate** = Total Call Setup Failed Stream Count /Total CDR Available Stream Count

#### <a name="drop-failure-rate"></a>Tasa de errores de colocación

La tasa de error de  colocación, que en caso contrario se conoce como medición del porcentaje de errores en la llamada total en el CQD, es el porcentaje de transmisiones establecidas correctamente donde la ruta de acceso a los medios no finalizó con normalidad.

Esto representa cualquier transmisión multimedia que finalice inesperadamente. Aunque el impacto de esta secuencia no es tan grave como una transmisión que no se pudo configurar, sigue afectando negativamente a la experiencia del usuario. Las gotas multimedia frecuentes y repentinas no solo pueden tener un gran impacto en la experiencia del usuario, sino que necesitan que los usuarios vuelvan a conectarse, lo que provoca pérdida de productividad (sin mencionar frustraciones).

La métrica se calcula tomando el número total de transmisiones descartadas divididas por el recuento total de transmisiones que se han configurado correctamente:

-   **Drop Failure Rate** = Total Call Dropped Stream Count /Total Call Setup Succeeded Stream Count

### <a name="define-your-target-metrics"></a>Definir las métricas de destino

En esta sección se analizan algunas de las métricas básicas del servicio que usamos para evaluar el estado de los servicios. Al evaluar e impulsar continuamente los esfuerzos para mantener estas métricas por debajo de sus objetivos definidos, le ayudará a garantizar que sus usuarios experimenten una calidad de llamada coherente y fiable. Como punto de partida, use los destinos sugeridos en la tabla siguiente. Ajuste los objetivos según sea necesario para alcanzar los objetivos empresariales.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo de red</th><th rowspan="1">Objetivos de calidad</th><th colspan="2">Destinos de confiabilidad</th></tr>
<tr><th>Audio Poor Stream Rate</th><th>Setup Failure Rate</th><th>Tasa de errores de colocación</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>General</td><td>3.0%</td><td>1.0%</td><td>3.0%</td></tr>
<tr><td rowspan="5"><strong>Conferencia</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Interno cableado</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi interno de 5 GHz</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi interno de 2,4 GHz</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>General</td><td>2.0%</td><td>0.5%</td><td>3.0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Interno de Cableada/Wi-Fi de 5 GHz</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>En general cableada o Wi-Fi de 5 GHz</td><td>2.0%</td><td>1.0%</td><td>1.0%</td></tr>
<tr><td>General</td><td>2.0%</td><td>1.0%</td><td>3.0%</td></tr>
</table>

### <a name="user-experience"></a>Experiencia de usuario

Analizar la experiencia del usuario es más arte que ciencia, porque las métricas que se recopilan aquí no siempre significan que hay un problema con la red o el servicio, sino que simplemente indican que el usuario percibe un problema. El CQD incluye un mecanismo de encuesta integrado (Calificar mi llamada (RMC) para ayudar a evaluar la experiencia general del usuario. RMC le dará información sobre las siguientes preguntas desde la perspectiva de los usuarios:

-   ¿Sé cómo usar la solución?
-   ¿La solución es fácil de usar e intuitiva y admite mis necesidades de comunicación diarias?
-   ¿La solución me ayuda a hacer mi trabajo?
-   ¿Cuál es mi visión general de la solución?
-   ¿Puedo usar la solución en cualquier momento, independientemente de dónde me encuentro?
-   ¿Puedo configurar y mantener una llamada?

#### <a name="rate-my-call"></a>Calificar mi llamada 

Rate My Call (RMC) está integrado en Teams y Skype Empresarial. Aparece automáticamente después de una en cada 10 llamadas, o un 10 por ciento. Esta breve encuesta le pide al usuario que mida la llamada y proporcione un poco de contexto sobre por qué la calidad de la llamada ha sido deficiente. Una o dos calificación se considera mala, de tres a cuatro es buena y cinco es excelente. Aunque se trata de un indicador de retraso, es una métrica útil para detectar problemas que las métricas del servicio pueden perderse.

> [!Note]
> El factor humano: los usuarios a menudo ignoran la encuesta cuando la calidad de la llamada es buena y la rellenan cuando la calidad de la llamada es mala. Como resultado, sus informes de RMC pueden estar sesgados hacia la parte mala aunque las métricas del servicio sean buenas.

Puede usar el CQD para informar sobre las respuestas de los usuarios de RMC, y los informes de muestra se incluyen en la plantilla CQD. Sin embargo, no se detallan en este artículo. 

#### <a name="client-and-device-readiness"></a>Disponibilidad del cliente y dispositivo

Necesita una estrategia sólida de cliente y dispositivos para garantizar que los usuarios tengan una experiencia de usuario coherente y positiva. Algunos principios clave impulsan cada estrategia de preparación.

##### <a name="client-readiness"></a>Disponibilidad del cliente

Mantener actualizado el cliente de Teams garantiza que los usuarios siempre disfruten de la mejor experiencia posible. Microsoft publica actualizaciones frecuentes para el cliente de [Teams](teams-client-update.md) (la actualización se instala en segundo plano a menos que haya desactivado esta funcionalidad, algo que no recomendamos). También es importante recordar los controladores de red, vídeo, USB y audio, porque a menudo se pasan por alto y pueden afectar a la calidad de las llamadas y reuniones. Considere la posibilidad de agregar controladores de red, Wi-Fi, vídeo, USB y audio a su proceso de administración de revisiones actual.


##### <a name="device-readiness"></a>Preparación del dispositivo

Ninguna estrategia puede afectar a la experiencia del usuario más que a la estrategia de preparación del dispositivo. Por ejemplo, los usuarios que dependen de los altavoces y el micrófono de su portátil experimentarán una gran cantidad de ruido de fondo en las llamadas y las reuniones. Teams está diseñado para funcionar con casi cualquier dispositivo, pero si tiene problemas relacionados con el dispositivo, consulte [Teléfono para Teams.](phones-for-teams.md)


### <a name="categories-of-quality"></a>Categorías de calidad

Poner en funcionamiento un conjunto de prácticas de administración de calidad: esto le ofrece la mejor oportunidad de una buena calidad de llamada y reunión. Un buen plan de administración de la calidad se ocupa de estas categorías:

-   **Red:** Calidad de audio centrada en la métrica Poor Stream Ratio (PSR), el uso de TCP, las subredes cableadas y inalámbricas, e identificar el uso de servidores proxy HTTP y VPN

-   **Puntos de conexión:** Dispositivos de audio y clientes actualizados

-   **Administración de servicios:** Esta categoría consta de dos secciones:

    -   En primer lugar, es responsabilidad de Microsoft la administración y el mantenimiento de los servicios de Teams y Skype Empresarial Online.

    -   En segundo lugar están las tareas que su organización administra para garantizar un acceso confiable al servicio, como actualizar la información de creación de información y mantener firewalls para las nuevas direcciones IP de Office 365 a medida que se agrega infraestructura al servicio.

![Gráfico de las categorías de calidad de una organización](media/qerguide-image-categories.png "Las categorías de calidad de una organización: administración de servicios, puntos de conexión y red.")

Revise la siguiente lista de tareas recomendadas para mantener la calidad. Debe realizar estas tareas periódicamente, por ejemplo, semanalmente.

#### <a name="service-management-tasks"></a>Tareas de administración de servicios

Estas tareas van desde garantizar que haya ancho de banda suficiente para llegar al servicio sin vínculos de Internet saturados, validar la calidad del servicio (QoS) en todas las áreas de red administradas y mantenerse al tanto de los intervalos IP de [Office 365](https://aka.ms/o365ips)en los firewalls.

#### <a name="network-tasks"></a>Tareas de red

Existen dos categorías de tareas de red: confiabilidad y calidad. La confiabilidad se centra en medir la capacidad del usuario para realizar llamadas correctamente y mantenerse conectado. La calidad se centra en la telemetría agregada que el cliente del usuario envía a Teams y Skype Empresarial Online durante la llamada y después de que haya finalizado. 

Dado el impacto crítico que tiene la confiabilidad en la experiencia del usuario, le recomendamos que evalúe e investigue las métricas de confiabilidad antes de profundizar en la calidad. 

#### <a name="endpoints-tasks"></a>Tareas de puntos de conexión

La tarea principal de esta categoría elimina los obstáculos a las actualizaciones periódicas [del cliente de Teams.](teams-client-update.md) De forma predeterminada, Teams se actualiza periódicamente automáticamente (a menos que desactive esa configuración, algo que no recomendamos). 

También debe supervisar los dispositivos y proporcionar actualizaciones siempre que identifique problemas relacionados con un dispositivo.

## <a name="use-cqd-to-manage-call-quality"></a>Usar el CQD para administrar la calidad de la llamada

Una vez que haya [configurado el CQD,](turning-on-and-using-call-quality-dashboard.md)estará listo para empezar a usarlo para administrar la calidad de las llamadas y reuniones de su organización.

La mayoría de los problemas con el rendimiento de Teams se divide en las siguientes categorías:

-   Una configuración de proxy o firewall incompleta
-   Una cobertura Wi-Fi insuficiente
-   Un ancho de banda insuficiente
-   VPN
-   Controladores y versiones de cliente incoherentes o obsoletas
-   Dispositivos de audio integrados o sin optimizar
-   Dispositivos de red o subred problemáticos

Si se toma el tiempo antes de la implementación de Teams para evaluar estas áreas y corregir los problemas, reducirá la cantidad de esfuerzo necesario para mantener una experiencia de Teams de alta calidad para todos los usuarios. Si necesita ayuda para evaluar su red en preparación para la implementación de Teams, lea Asesor para [Teams](use-advisor-teams-roll-out.md) y [Preparar la red para Teams.](prepare-network.md)

### <a name="expectations-using-cqd"></a>Expectativas con el CQD

Use el panel de calidad de llamadas para obtener información sobre la calidad de las llamadas realizadas mediante los servicios de Teams y Skype Empresarial. El CQD está diseñado para ayudar a los administradores de Teams y Skype Empresarial a optimizar la red y a los ingenieros de red, así como a vigilar la calidad, la confiabilidad y la experiencia del usuario. El CQD analiza la telemetría agregada de toda la organización, donde pueden ser evidentes los patrones generales; esto le permite realizar evaluaciones informadas y planear la corrección. El CQD proporciona informes de métricas que ofrecen información sobre la calidad general, la confiabilidad y la experiencia del usuario.

Aunque es útil para analizar tendencias y subredes, el CQD no siempre proporciona una causa específica para un escenario determinado. Es importante comprender esto y establecer las expectativas correctas al usar el CQD:

-   El CQD no proporcionará la causa raíz de cada escenario
-   El CQD no contendrá transmisiones de Sistema telefónico o Audioconferencia
-   El CQD llamará áreas para una investigación más exhaustiva basada en tendencias

### <a name="cqd-reports-overview"></a>Información general de los informes del CQD

Use el menú desplegable de la parte superior de la pantalla para abrir un informe. Para obtener una lista de los datos proporcionados en cada informe, lea [Datos disponibles en los informes del CQD.](CQD-data-and-reports.md#data-available-in-cqd-reports)

Novedades de enero de 2020: Descargar plantillas de consulta [de Power BI para el CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Las plantillas personalizables de Power BI que puede usar para analizar e informar sobre los datos del CQD.


### <a name="teams-vs-skype-for-business"></a>Teams frente a Skype Empresarial

El CQD puede informar sobre Teams y Skype Empresarial. Sin embargo, es posible que en ocasiones desee desarrollar un informe para ver la telemetría de Teams independientemente de Skype Empresarial.

#### <a name="summary-reports"></a>Informes de resumen

Para modificar la página de informes de resumen y ver  solo Teams o Skype Empresarial, seleccione el menú desplegable Filtro de producto en la parte superior de la pantalla y, después, seleccione el producto que desee.

![Captura de pantalla del menú desplegable que muestra las opciones de filtro](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Informes detallados

Para filtrar todos los informes detallados, en la barra del explorador, anexa lo siguiente al final de la dirección URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Ejemplo:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obtener más información sobre los filtros de dirección URL, lea [Informes de filtrado](CQD-data-and-reports.md#report-filters) más adelante en esta sección.

Para filtrar un informe detallado individual, agregue el filtro al informe y esta opción ``Is Teams`` lo establezca en Verdadero o Falso.

![Captura de pantalla de la página Agregar filtro](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Redes administradas frente a no administradas

De forma predeterminada, todos los puntos de conexión del CQD se clasifican como externos. Tan pronto como se introduzca un archivo de creación, podemos empezar a ver los datos de punto de conexión administrados. Como se ha comentado anteriormente, las redes del CQD se definen como:

-   Una _red administrada,_ a menudo denominada interna o interna, puede ser influida y controlada por la organización. Esto incluye la LAN interna, la WAN remota y la VPN.
-   Una _red no administrada,_ a menudo denominada externa o externa, no puede ser influida ni controlada por la organización. Un ejemplo de red no administrada es la red de un hotel o aeropuerto.

### <a name="dimensions-measures-and-filters"></a>Dimensiones, medidas y filtros

Una consulta CQD bien formada contiene los tres parámetros siguientes:

-   **Dimensión:** Cómo deseo dinamr los datos.

-   **Medida:** Información sobre la que deseo informar.

-   **Filtro:** Cómo deseo reducir el conjunto de datos que devuelve la consulta.

Otra forma de ver esto es que una dimensión  es la función de agrupamiento,  una medida son los datos que me interesan y un filtro es cómo deseo limitar los resultados _a_ aquellos que son relevantes para mi consulta.

Un ejemplo de consulta bien formada es Mostrarme transmisiones malas [Medida] por subred [dimensión] para el edificio **6 [Filtro].** Para obtener más información, vea [Dimensiones y medidas disponibles en el CQD.](https://aka.ms/cqd-dm)

### <a name="first-vs-second"></a>Primero frente a segundo 

Muchas de las dimensiones y medidas del CQD se clasifican como primeras o segundas. El CQD no usa campos del autor de  la  llamada o el destinatario de la llamada: se les ha cambiado el nombre en primer lugar y en segundo lugar porque hay pasos de intervención entre el autor de la llamada y el destinatario de la llamada. La siguiente lógica determina qué punto de conexión implicado se etiqueta como primero:

-   **En** primer lugar siempre habrá un punto de conexión de servidor (servidor de conferencias, servidor de mediación, y así sucesivamente) si un servidor está implicado en la transmisión o la llamada.

-   **El segundo** siempre será un punto de conexión de cliente a menos que la transmisión se haga entre dos puntos de conexión de servidor.

-   Si ambos puntos de conexión son del mismo tipo, la elección de los cuales primero se basa en el orden interno de la categoría de agente de usuario. De este modo se asegura que el orden es coherente.

Para obtener más información sobre cómo determinar el primer punto de conexión o el segundo cuando ambos son iguales, vea Dimensiones y medidas disponibles [en el CQD.](https://aka.ms/cqd-dm)

### <a name="stream-vs-call"></a>Transmisión frente a llamada

Debe comprender la diferencia entre una llamada y una transmisión para elegir correctamente las dimensiones o medidas que verá en el CQD. Aunque el foco principal del CQD se encuentra en las transmisiones, las medidas basadas en llamadas también están disponibles.

-   **Stream:** Existe _una transmisión_ entre solo dos puntos de conexión. Solo hay una transmisión por cada dirección y se necesitan dos transmisiones para la comunicación. Las transmisiones son útiles para investigar edificios, redes o subredes. En algunos casos, tanto la llamada como la transmisión se usan en el nombre de la medición (por ejemplo, Secuencia de configuración de llamadas o Secuencia de llamada descartada). Estos se siguen clasificando como transmisiones.

-   **Llamar:** Una _llamada_ es un grupo de todas las transmisiones de todos los participantes. Una llamada consiste, como mínimo, en dos transmisiones. Una sola llamada tendrá al menos dos puntos de conexión, cada uno con un mínimo de una transmisión.

Para obtener instrucciones adicionales sobre si la dimensión o medida hace referencia a una llamada o a una transmisión, vea Dimensiones y medidas disponibles [en el CQD.](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Llamadas buenas, malas y sin clasificar

Una llamada se clasifica como buena, mala o sin clasificar. Dedijemos un momento para hablar de cada una con más detalle.

-   **Buena o mala:** Una llamada buena o mala consiste en una llamada que contiene un conjunto completo de métricas del servicio, para las que el servicio generó y recibió un informe completo de QoE. Determinar si una transmisión es buena o mala se describe [anteriormente en este artículo.](#poor-stream-rate)

-   **Unclassified:** Una transmisión sin clasificar no contiene un conjunto completo de métricas de servicio. Pueden ser llamadas cortas (normalmente menos de 60 segundos) en las que no se pudieron calcular los promedios y no se generó un informe de QoE. La razón más común por la que las llamadas se desclasifiquen es que apenas se utilizaba paquetes. Un ejemplo sería un participante que se une a una reunión silenciada y no habla nunca. El participante recibe, pero no transmite, los medios. Sin que se transmitan medios, no habrá métricas disponibles para que las use el CQD para clasificar la transmisión multimedia saliente del punto de conexión.

Para obtener más información, lea [la clasificación de stream en el CQD.](stream-classification-in-call-quality-dashboard.md)

### <a name="common-subnets"></a>Subredes comunes

Las subredes comunes son subredes privadas específicas que usan los hoteles, redes locales, puntos de acceso y áreas similares. Estas subredes son difíciles de tener en cuenta debido a su uso de wi arrasa. Si su organización usa una de estas subredes comunes, le recomendamos que mueva esa red a otra subred. Esto facilitará la creación de informes en el CQD. Cuando se indican, los informes de la plantilla Todas las redes se han configurado para excluir estas subredes y eliminarlas como una fuente de mala calidad. A continuación se definen subredes comunes; su impacto variará según la organización.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Al investigar una red administrada que usa una subred común, tendrá que usar la dimensión IP local de reflexión segunda para agrupar subredes. Esta dimensión contiene la dirección IP pública del punto de conexión.


## <a name="reliability-investigations"></a>Investigaciones de confiabilidad

El primer paso para mejorar la calidad es evaluar el estado de confiabilidad en toda la organización. Como la confiabilidad es fundamental para una experiencia de usuario positiva, empezamos con los dos componentes que miden la confiabilidad:

1.  **Errores de configuración:** No se pudo establecer la llamada.

2.  **Errores de entrega:** La llamada se ha establecido y finalizado inesperadamente.

A lo largo de esta sección, trataremos los métodos para investigar ambas áreas.

> [!NOTE]
> No todos los informes incluidos en las plantillas se tratan en este artículo. Sin embargo, los métodos de investigación explicados a continuación siguen a aplicarse. Consulte la descripción del informe individual para obtener más información.


### <a name="setup-failures"></a>Errores de configuración

Priorizar primero los errores de configuración de corrección en esta área, ya que estos errores tienen un impacto negativo importante en la experiencia del usuario.

Empiece la investigación evaluando el porcentaje de errores de configuración generales de la organización y, a continuación, priorice las áreas de investigación en función del porcentaje más alto a partir de la creación o la red. 

#### <a name="setup-failure-trend-analysis"></a>Análisis de tendencia de errores de configuración

Este informe muestra la cantidad total de transmisiones, los errores de configuración de la transmisión y la tasa de errores de configuración de la transmisión. Apunte a cualquiera de las columnas para mostrar sus valores individuales. 

##### <a name="analysis"></a>Análisis

Mediante este informe, puede responder a las siguientes preguntas y determinar su próximo curso de acción:

-   ¿Cuál es el porcentaje total de errores en la configuración de llamadas del mes actual?

-   ¿Es el porcentaje de error de configuración de llamada total por debajo o por encima de la métrica de destino definida?

-   ¿Es la tendencia de fracasos peor o mejor que el mes anterior?

-   ¿Está aumentando, estable o disminuyendo la tendencia de fracasos?

Con independencia de las respuestas a estas preguntas, dedúgase el tiempo necesario para investigar más a fondo mediante los sub informes complementarios para buscar los edificios individuales o subredes que puedan necesitar corrección. Aunque la tasa general de errores podría estar por debajo del sistema métrico objetivo, las tasas de error de uno o más edificios o redes podrían estar por encima de la métrica objetivo y es necesario investigar.

#### <a name="setup-failure-investigations"></a>Investigaciones de errores de configuración 

Este informe de resumen se usa para detectar y aislar edificios o redes que puedan necesitar corrección.

> [!NOTE]
> Asegúrese de ajustar el filtro del informe Month Year al mes actual. Seleccione **Editar** y ajuste el filtro **del informe Month Year** para guardar el nuevo mes predeterminado.

##### <a name="remediation"></a>Corrección 

Centre los primeros esfuerzos de corrección en los edificios o subredes que tienen el mayor volumen de errores. Esto maximizará el impacto en la experiencia del usuario y le ayudará a reducir rápidamente la tasa de errores en la configuración de llamadas de la organización. En la tabla siguiente se enumeran los dos motivos de los errores de configuración notificados por el CQD.

| Motivo por el que se produce un error en la configuración de llamadas       | Causa típica                    |
|----------------------------------|----------------------------------|
| Falta la regla de exenciones para la inspección profunda de paquetes del fw | Indica que el equipo y la ruta de red han impedido que se estableciera la ruta de acceso a medios debido a las reglas de inspección profunda de paquetes. Es probable que se deba a que las reglas del firewall no se han configurado correctamente. En este escenario, el enlace TCP se ha hecho correctamente, pero el enlace SSL no lo ha hecho.      |
| Falta la regla de excepción de bloque de IP del fw      | Indica que el equipo de red a lo largo de la ruta ha impedido que se estableciera la ruta de acceso a medios con la red de Microsoft 365 u Office 365. Esto puede deberse a que las reglas del firewall o el proxy no se han configurado correctamente para permitir el acceso a los puertos y las direcciones IP que se usan para el tráfico de Teams y Skype Empresarial. |

Cuando empiece la corrección, puede centrar sus esfuerzos en una edificio o subred determinados. Como se muestra en la tabla anterior, estos problemas se deben a configuraciones de proxy o firewall. Revise las opciones de la tabla siguiente para ver las acciones de corrección.

|      Corrección      |Instrucciones  |
|-----------------------|----------|
| Configurar firewalls | Trabaje con su equipo de red y compruebe la configuración de firewalls [con la lista de direcciones IP de Office 365.](https://aka.ms/o365ips)<br><br>Compruebe que las [subredes multimedia y](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) los puertos están incluidos en las reglas del firewall. <br><br>Compruebe que los [puertos necesarios](prepare-network.md) estén abiertos en el firewall. UDP debe tener prioridad porque tcp se considera un protocolo de conmutación por error para el uso compartido de pantalla basado en vídeo, vídeo y audio, y su uso afectará a la calidad de la llamada. El uso compartido de aplicaciones RDP heredado usa solo TCP.|

### <a name="drop-failures"></a>Errores de colocación

A diferencia de los códigos de error de configuración, el CQD no tiene ningún código de error de colocación para indicar por qué se producen errores de colocación, lo que hace difícil aislar una causa raíz específica. Para mejorar los errores de bloqueo de errores, use un enfoque deducido. Al corregir cualquier área de interés para los medios, revisiones de clientes y controladores e impulsar el uso de dispositivos certificados para Teams y Skype Empresarial, puede esperar que se rechace el sistema.

#### <a name="drop-failure-trend-analysis"></a>Análisis de tendencia de error de colocación

Este informe muestra la cantidad total de transmisiones de audio, los errores totales y la tasa de errores. Apunte a cualquiera de las columnas para mostrar sus valores. 


##### <a name="analysis"></a>Análisis

Mediante este tipo de informe, puede responder a las siguientes preguntas:

-   ¿Cuál es la tasa de error actual?
-   ¿Está la tasa de error de colocación por debajo de la métrica de destino definida?
-   ¿Es la tendencia de fracasos peor o mejor que el mes anterior?
-   ¿Está aumentando, estable o disminuyendo la tendencia de fracasos?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo necesario para investigar el uso de los sub informes para buscar edificios o redes que puedan necesitar corrección. Aunque la tasa de error general podría estar por debajo de la métrica objetivo, la tasa de error de colocación de uno o más edificios o redes podría estar por encima de la métrica objetivo y es necesario investigar.

#### <a name="drop-failure-investigations"></a>Investigaciones de errores de entrega

Los errores notificados aquí indican que la llamada se perdió inesperadamente y se ha producido una experiencia de usuario negativa. A diferencia de los informes de tendencias, estos informes proporcionan información adicional sobre subredes específicas que necesitan investigar más a fondo.


##### <a name="remediation"></a>Corrección

Con los informes de tabla incluidos, puede aislar las áreas de problemas de la red donde la tasa de colocación está por encima de la métrica de destino que ha definido. Centre los primeros esfuerzos de corrección en los edificios o subredes que tengan el mayor recuento total de transmisiones para lograr el mayor impacto.

Causas comunes de las llamadas quitadas:

-   Salida de Internet o de red no aprovisionada
-   No se configuró QoS en redes restringidas
-   Versiones anteriores del cliente
-   Comportamiento del usuario

Después de descubrir las áreas [](use-call-analytics-to-troubleshoot-poor-call-quality.md) problemáticas, puede usar el análisis de llamadas por usuario para revisar más a los usuarios en ese edificio para ver si hay problemas específicos. El análisis de llamadas contiene datos EUII adicionales y puede ser útil para aislar aún más los posibles motivos de los fallos en las llamadas.

Independientemente del paso siguiente, es una buena práctica notificar al departamento de soporte técnico que se ha detectado un problema con determinadas construcciones o subredes. Esto permite al departamento de soporte técnico responder rápidamente a las llamadas entrantes y a administrar a los usuarios de forma más eficaz. Los usuarios marcados pueden devolverse al equipo de ingeniería para una investigación más exhaustiva.

En la tabla siguiente se enumeran algunos métodos comunes para administrar y corregir errores de colocación.

| Corrección                              | Instrucciones                      |
|------------------------------------------|-------------------------------|
| **Red/Internet**                         | **Congestión:** trabaje con el equipo de red para supervisar el ancho de banda en edificios o subredes específicos para confirmar que hay problemas con la sobreutilización. Si confirma que hay congestión de la red, considere aumentar el ancho de banda para ese edificio o aplicar QoS. Use los informes de resumen de [Quality Poor Stream](#quality-investigations) incluidos para revisar las subredes del problema en caso de problemas de vibración, latencia y pérdida de paquetes, ya que estos suelen preceder a una transmisión en secuencias perdidas.<br><br>**QoS:** si aumentar el ancho de banda no es práctico o rentable, considere la posibilidad de implementar QoS. Esta herramienta es muy eficaz para administrar el tráfico congestionado y puede garantizar que los paquetes multimedia de la red administrada se prioricen por encima del tráfico no multimedia. Como alternativa, si no hay ninguna evidencia clara de que el responsable del ancho de banda es el ancho de banda, tenga en cuenta estas soluciones:<ul><li>[Guía de QoS de Microsoft Teams](qos-in-teams.md)</li></ul><br>**Realizar** una evaluación de la preparación de red: una evaluación de red proporciona detalles sobre el uso de ancho de banda esperado, cómo hacer frente a los cambios en el ancho de banda y la red, y prácticas de redes recomendadas para Teams y Skype Empresarial. Con la tabla anterior como origen, tiene una lista de edificios o subredes que son excelentes candidatos para una evaluación.<ul><li>[Preparar la red de la organización para Microsoft Teams](prepare-network.md)</li></ul> |
| **Clientes (solo para Skype Empresarial Online)** | Algunos clientes antiguos de Skype Empresarial han conocido problemas documentados con la confiabilidad de medios. Revise los informes de Análisis de llamadas de varios usuarios afectados o cree un informe personalizado de tabla de versiones de cliente en el CQD filtrado por edificios o subredes específicos con la medida Total Call Dropped Failure %. Esta información le ayudará a comprender si existe una relación entre las llamadas que se quitan en ese edificio específico y una versión específica del cliente.     |
| **Dispositivos**                                  |Si los dispositivos son los responsables de los problemas de calidad de las llamadas, considere la posibilidad de actualizar los dispositivos infractores. Lea [teléfonos para Teams](phones-for-teams.md) para obtener más información. |
| **Comportamiento del usuario**                            | Si determina que ni la red, los dispositivos o los clientes son el problema, considere desarrollar una estrategia de adopción del usuario para concienciar a los usuarios sobre cómo unirse a las reuniones y salir de estas. Un usuario de Teams y Skype Empresarial más inteligente producirá una mejor experiencia de usuario para todos los participantes de la reunión. Por ejemplo, un usuario que pone su portátil en suspensión (cerrando la tapa) sin salir de la reunión se clasificará como una llamada inesperada.   |

## <a name="quality-investigations"></a>Investigaciones de calidad

El siguiente paso para evaluar el estado de la calidad de audio en toda la organización es investigar el uso de SECUENCIAS deficiente (PSR), TCP y proxy. Es importante recordar que los datos del CQD no proporcionan una causa raíz específica, sino que le proporcionan, en su lugar, áreas de problemas probables para iniciar una conversación de colaboración con los equipos adecuados para las actividades de corrección. 

> [!NOTE]
> No todos los informes incluidos en las plantillas se tratan en este artículo; sin embargo, los métodos de investigación que se explican a continuación se seguirán aplicando a esos informes. Consulte la descripción del informe individual para obtener más información. 

### <a name="quality"></a>Calidad

Los porcentajes de PSR se usan para indicar si la organización está cumplir los objetivos métricos definidos para un área en la que centrarse. Es importante tener en cuenta que, aunque los porcentajes de alto nivel estén dentro del destino definido, es posible que las subredes individuales o los edificios no cumplan los objetivos definidos y, por lo tanto, necesiten investigar más a fondo. Por ejemplo, si el porcentaje total de PSR de audio es del 2 por ciento en abril, que cumple con el destino de la muestra, es posible que los edificios individuales y subredes todavía tengan experiencias malas, dependiendo de la distribución general de ese 2 por ciento. 

Para evaluar el porcentaje de transmisiones malas, use los informes de calidad. Se proporcionan varios informes de calidad para revisar las métricas de general, conferencias, dos partes, llamadas RTC, VPN y salas de reuniones. Se proporcionan informes mensuales, semanales y diarios para ayudar en este proceso. Los informes semanales y diarios se limitan a la plantilla de redes administradas para aumentar su eficacia y reducir el ruido. 

#### <a name="quality-trend-analysis"></a>Análisis de tendencia de calidad

Los informes de tendencias muestran información de calidad a lo largo del tiempo y se usan para ayudar a identificar y comprender las tendencias de calidad dentro de cada área de interés. Como se indicó anteriormente, se incluyen árboles de informe en las plantillas para investigar la calidad; conferencias, dos partes, llamadas RTC, VPN y salas de reuniones. Para el propósito de analizar la calidad, el proceso investigativo es el mismo. Sin embargo, se recomienda comenzar con las conferencias en primer lugar, ya que las mejoras en la calidad de las conferencias también afectarán de forma positiva a todas las demás áreas. 

> [!Note]
> Investigar conferencias entre dos partes, las llamadas RTC y las salas de reuniones es similar a investigar las conferencias. El foco es aislar los edificios o subredes que tienen la peor calidad e identificar el motivo de la mala calidad.

> [!Important]
> Los informes basados en VPN se filtran mediante la dimensión de la segunda VPN. Esta dimensión requiere que el adaptador de red VPN se registre correctamente como adaptador de acceso remoto. Los proveedores de VPN no usan este indicador de forma fiable y su kilometraje variará en función del proveedor de VPN implementado en su organización. Modifique los [informes VPN,](CQD-upload-tenant-building-data.md#vpn) si es necesario, usando el nombre del edificio o la red.

##### <a name="investigation"></a>Investigación

Mediante estos informes, puede responder a las siguientes preguntas:

-   ¿Cuál es el PSR total del mes actual?
-   ¿El PSR está por debajo de la métrica de destino definida?
-   ¿Es PSR peor o mejor que el mes anterior?
-   ¿Aumenta, se mantiene o disminuye la tendencia del PSR?

Con independencia de las respuestas a las preguntas anteriores, tómese el tiempo necesario para investigar con los sub informes para buscar edificios o subredes que puedan necesitar una investigación. Aunque el PSR general puede estar por debajo de la métrica objetivo, a menudo el PSR de uno o más edificios o redes está por encima de la métrica y necesita corrección.

#### <a name="quality-investigations"></a>Investigaciones de calidad

Los informes de resumen de calidad proporcionan información más detallada sobre lo que ha contribuido a que las transmisiones se hayan clasificado como malas y ayuda a aislar las áreas problemáticas de la red administrada.

Aunque las dimensiones usadas pueden diferir ligeramente entre el informe, cada informe incluirá medidas para el total de transmisiones, transmisiones totales con mala calidad, PSR y calidad deficiente debido a. Se han creado informes para cada área de interés: conferencias, dos partes, llamadas RTC, VPN y salas de reuniones. La plantilla de red administrada incluye informes adicionales para aprovechar la información de ubicación que se carga a través del archivo de creación.


> [!Note]
> Las subredes comunes son difíciles de tener en cuenta debido a su uso de wi arrasa. Se ha agregado un informe independiente que muestra la IP pública del cliente (Second Reflexive Local IP) a la plantilla Todas las redes para ayudar a corregir las oficinas que usan redes comunes.


![Captura de pantalla que muestra el resumen de flujo de audio deficiente](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Corrección

Centre los esfuerzos de corrección en los edificios o subredes que tengan el mayor volumen de transmisiones, ya que esto maximizará el impacto y ayudará a mejorar la experiencia del usuario rápidamente. Use las medidas de vibración, pérdida de paquetes y tiempo de ida y vuelta (RTT) para comprender qué contribuye a la mala calidad (es posible que haya más de un problema):

-   **Vibración:** los paquetes multimedia llegan a diferentes velocidades, lo que provoca que un altavoz suene.
-   **Pérdida de paquetes:** se descartan paquetes multimedia, lo que crea el efecto de falta de palabras o sílabas.
-   **RTT:** los paquetes multimedia tardan mucho tiempo en llegar a su destino, lo que crea un efecto walkie-talkie.

Para ayudar a la investigación sobre problemas de calidad, use [el análisis de llamadas por usuario.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Con Análisis de llamadas, puede ver una conferencia específica o el informe de llamadas del usuario. Este informe contendrá datos EUII/PII y es útil para buscar la causa de un error. Después de saber qué edificio se ve afectado, debería ser sencillo localizar a los usuarios de ese edificio. 

No olvide dejar que su departamento de soporte técnico sepa que estas redes están experimentando problemas de calidad, para que puedan resolver rápidamente y responder a las llamadas entrantes.

| Corrección                              | Instrucciones                         |
|------------------------------------------|----------------------------------|
| **Redes**                                 | **Congestión:** una red que se usa en exceso o no está aprovisionada puede causar problemas con la calidad de medios. Trabaje con el equipo de red para determinar si las conexiones de red desde el usuario al punto de salida de Internet tienen suficiente ancho de banda para admitir los medios. <br><br>**Realizar** una evaluación de la preparación de red: una evaluación de red proporciona detalles sobre el uso de ancho de banda esperado, cómo hacer frente a los cambios en el ancho de banda y la red, y prácticas de redes recomendadas para Teams y Skype Empresarial. Con la tabla anterior como origen, tiene una lista de edificios o subredes que son excelentes candidatos para una evaluación.<ul><li>[Preparar la red de la organización para Microsoft Teams](prepare-network.md)</li></ul>|
| **Calidad de servicio (QoS)**  | QoS es una herramienta demostrada que ayuda a priorizar paquetes en una red congestionada para asegurarse de que llegan a su destino intactos y a tiempo. Considere la posibilidad de implementar QoS en toda la organización para maximizar la calidad de la experiencia del usuario donde el ancho de banda está restringido. QoS le ayudará a resolver problemas normalmente asociados con altos niveles de pérdida de paquetes y, en un menor grado, vibración y tiempos de ida y vuelta.<ul><li>[Instrucciones de QoS de Teams](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | Wi-Fi pueden tener un impacto significativo en la calidad de la llamada. Wi-Fi las implementaciones no suelen tener en cuenta los requisitos de red para los servicios VoIP y suelen ser un origen de mala calidad. Para obtener más información sobre la optimización de Wi-Fi infraestructura de almacenamiento, vea [este artículo sobre Wi-Fi planeamiento.](/skypeforbusiness/certification/plan-wifi)<br><br>**Controlador inalámbrico:** asegúrate de que los controladores inalámbricos estén actualizados. Esto ayudará a mitigar cualquier experiencia de usuario deficiente relacionada con un controlador obsoleto. Muchas organizaciones no incluyen controladores inalámbricos en sus ciclos de revisión y estos controladores pueden pasar desajustados durante años. Muchos problemas inalámbricos se solucionan asegurándose de que los controladores inalámbricos estén actualizados.<br><br>**WMM**: Extensiones multimedia inalámbricas (WMM), también conocidas como Wi-Fi Multimedia, proporciona características básicas de QoS a las redes inalámbricas. Las redes inalámbricas modernas deben admitir muchos dispositivos. Estos dispositivos compiten por el ancho de banda y pueden causar problemas de calidad para los servicios VoIP, donde la velocidad y la latencia son fundamentales. Consulte con su proveedor de servicios inalámbricos para obtener información específica y considere la posibilidad de implementar WMM en su red inalámbrica para priorizar los medios de Skype Empresarial y Teams.<br><br>**Densidad de punto de** acceso: los puntos de acceso pueden estar demasiado separados o no en una ubicación ideal. Para minimizar las posibles interferencias, coloque puntos de acceso adicionales en las salas de conferencias y en ubicaciones que no se obstaculicen por las paredes u otros objetos en los que la señal Wi-Fi es débil.<br><br>**2,4 GHz frente a 5 GHz:** 5 GHz proporciona menos interferencias en segundo plano y mayores velocidades, y debe priorizarse al implementar VoIP a través de Wi-Fi. Sin embargo, 5 GHz no es tan fuerte como 2,4 GHz y no es tan fácil. Revise el diseño del edificio para determinar en qué frecuencia se puede basar para obtener la mejor conexión. |
|**Dispositivo de red** | Las organizaciones más grandes podrían tener cientos de dispositivos distribuidos por la red. Trabaje con su equipo de red para asegurarse de que los dispositivos de red desde el usuario a Internet se mantienen y están actualizados. |
| **VPN**  | Los dispositivos VPN no están tradicionalmente diseñados para controlar las cargas de trabajo de medios en tiempo real. Algunas configuraciones VPN prohíben el uso de UDP (que es el protocolo preferido para los medios) y dependen solo de TCP. Considere la posibilidad de implementar una solución de túnel dividido de VPN para ayudar a reducir la VPN como un origen de mala calidad. |
| **Clientes** <br>(Solo Skype Empresarial Online) | Asegúrese de que todos los clientes se actualizan periódicamente. |
| **Dispositivos** | Si los dispositivos son los responsables de los problemas de calidad de las llamadas, considere la posibilidad de actualizar los dispositivos infractores. Lea [teléfonos para Teams](phones-for-teams.md) para obtener más información. |
| **Controladores** | Los controladores de red de revisiones (Ethernet y Wi-Fi), audio, vídeo y USB deben formar parte de su estrategia general de administración de revisiones. Muchos problemas de calidad se solucionan actualizando los controladores. |
| **Salas de reuniones en Wi-Fi** | Recomendamos encarecidamente que los dispositivos de las salas de reuniones estén conectados a la red mediante, al menos, una conexión Ethernet de 1 gbps. Los dispositivos de salas de reuniones suelen incluir varias transmisiones de audio y vídeo, junto con el contenido de la reunión (como el uso compartido de la pantalla) y tienen requisitos de red más elevados que otros puntos de conexión de Teams o Skype Empresarial. Las salas de reuniones son, por definición, dispositivos Wi-Fi permitir una ventaja solo durante la instalación.<br><br>Las salas de reuniones deben tratarse con más cuidado y atención para asegurarse de que la experiencia con estos dispositivos se está cumpliendo o sobrepasando las expectativas. Los problemas de calidad con las salas de reuniones suelen agravarse rápidamente, ya que los suele usar el personal de nivel superior.<br><br>Cuando todo es igual (aparte de la comodidad), Wi-Fi rendimiento suele ser menor que una conexión por cable. Con el auge de las directivas "Traer su propio dispositivo" y la difusión de portátiles, Wi-Fi de acceso a los equipos se suelen usar en exceso. Es posible que los medios en tiempo real no se prioricen en Wi-Fi de contenido, lo que puede provocar problemas de calidad en los momentos de mayor uso. Este uso pesado puede coincidir con una reunión en la que puede haber una docena de personas en asistencia, cada una con su propio portátil y smartphone, todos conectados al mismo punto de acceso Wi-Fi que el dispositivo de la sala de reuniones.<br><br>Wi-Fi debe considerarse solo como una solución temporal, para una instalación móvil o cuando Wi-Fi se ha aprovisionado correctamente para admitir medios basados en tiempo real y de clase empresarial. |


### <a name="tcp"></a>TCP 

El Protocolo de control de transmisión (TCP) se considera un transporte de conmutación por error y no el transporte principal que se desea para los medios en tiempo real. El motivo por el que se trata de un transporte de conmutación por error se debe a la naturaleza con estado de TCP. Por ejemplo, si se realiza una llamada en una red latente y se retrasan paquetes multimedia, los paquetes de hace unos segundos (que ya no son útiles) compiten por que el ancho de banda llegue al receptor, lo que puede hacer que una mala situación sea peor. Esto hace que el audio sea cada vez más integrador y estirar el audio, lo que produce artefactos audibles, a menudo en forma de vibración.

Los informes de esta sección no distinguen entre transmisiones buenas y malas. Dado que UDP es preferido, los informes buscan el uso de TCP para el uso compartido de pantalla basado en vídeo, vídeo y audio (VBSS). Se proporcionan tasas de transmisión deficientes para ayudar a comparar la calidad udp frente a la calidad de TCP para que pueda centrar sus esfuerzos donde el impacto sea mayor. El uso de TCP se debe principalmente a reglas de firewall incompletas. Para obtener más información sobre las reglas de firewall para Teams y Skype Empresarial Online, vea las DIRECCIONES URL e intervalos de direcciones IP de [Microsoft 365 y Office 365.](https://aka.ms/o365ips)

> [!Note]
> Audio, vídeo y VBSS prefieren UDP como su transporte principal. La carga de trabajo de uso compartido de aplicaciones RDP heredada solo usa TCP.

#### <a name="tcp-usage"></a>Uso de TCP

Los informes TCP indican el uso total de TCP durante los últimos siete meses. El resto de los informes de esta sección se centrarán en restringir edificios y subredes específicos donde se usa con más frecuencia el protocolo TCP. Hay informes independientes disponibles tanto para conferencias como para transmisiones de dos partes.

![Gráfico que muestra el porcentaje de transmisiones de audio que usan TCP](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Investigación

Mediante este informe, puede responder a las siguientes preguntas:

-   ¿Cuál es el volumen total de transmisiones TCP del mes actual?
-   ¿Es peor o mejor que el mes anterior?
-   ¿Aumenta, se mantiene o disminuye la tendencia de uso de TCP?
-   ¿El PSR TCP es el mismo que el PSR general?

Si observa que la tendencia de uso de TCP aumenta o está por encima del uso mensual normal, tómese el tiempo necesario para investigar mediante los sub informes para buscar edificios o redes que puedan necesitar corrección. Lo ideal es que desee el menor número de sesiones de audio basado en TCP posibles en la red administrada.

#### <a name="tcp-vs-udp"></a>UDP y TCP

Este informe identifica el volumen de informes de uso TCP frente a UDP del último mes de uso compartido de pantalla basado en vídeo, vídeo y audio (VBSS). 

![Informe que muestra el volumen de transmisiones que usan TCP frente a UDP](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Análisis

Aunque desea que el uso de TCP sea lo más bajo posible, es posible que vea un poco de uso de TCP en una implementación en buen estado. Tcp por sí mismo no contribuye a una llamada deficiente, por lo que se proporcionan tarifas de transmisión para ayudar a identificar si el uso de TCP es un colaborador de mala calidad. 

#### <a name="tcp-investigations"></a>Investigaciones TCP

En las plantillas del CQD proporcionadas, navegue hasta las transmisiones TCP con la plantilla Crear y Subred con la plantilla Redes administradas o Todas las redes. Para investigar el uso de TCP, el proceso es el mismo, por lo que nos centraremos aquí en la conferencia.


##### <a name="remediation"></a>Corrección

Este informe identifica edificios y subredes específicos que contribuyen al volumen de uso de TCP. También se incluye un informe adicional para identificar la DIRECCIÓN IP de Microsoft Relay que se usó en la llamada para ayudar a aislar las reglas de firewall que faltan. Centre los esfuerzos de corrección en los edificios con el mayor volumen de transmisiones TCP para maximizar el impacto.

La causa más habitual del uso de TCP es que faltan reglas de excepción en firewalls o servidores proxy. Hablaremos de servidores proxy en la siguiente sección, así que por ahora centre sus esfuerzos en los firewalls. Mediante la generación o subred proporcionada, puede determinar qué firewall es necesario actualizar.

| Corrección        | Instrucciones     |
|--------------------|--------------------------------------|
| Configurar firewall | Compruebe que los puertos y las direcciones IP de [Microsoft 365 u Office 365](https://aka.ms/o365ips) están excluidos del firewall. En el caso de problemas de TCP relacionados con medios, centre sus esfuerzos iniciales en lo siguiente:<ul><li>Compruebe que las subredes multimedia del cliente 13.107.64.0/18 y 52.112.0.0/14 están en las reglas del firewall.</li><li>Los puertos UDP 3478-3481 son los puertos multimedia necesarios y deben abrirse, de lo contrario, el cliente volverá a fallar al puerto TCP 443.</li></ul> |
| Comprobar             | Use la Herramienta de evaluación de red de [Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si hay problemas de conectividad a direcciones IP y puertos específicos de Microsoft 365 u Office 365 desde el edificio o la subred afectados.    |

### <a name="http-proxy"></a>Proxy HTTP

Los servidores proxy HTTP no son la ruta preferida para establecer sesiones multimedia, por una multitud de motivos. Muchas contienen características de inspección de paquetes profundas que pueden evitar que se completen las conexiones con el servicio e introducir interrupciones. Además, casi todos los servidores proxy fuerzan TCP en lugar de permitir UDP, lo que se recomienda para obtener una calidad de audio óptima.

Siempre recomendamos que configure el cliente para conectarse directamente a los servicios de Teams y Skype Empresarial. Esto es especialmente importante para el tráfico basado en medios.


> [!IMPORTANT]
> Le recomendamos que cargue un archivo de creación [válido](CQD-upload-tenant-building-data.md) para poder distinguir dentro de las secuencias de audio externas al analizar el uso de proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

El informe de secuencia de proxy HTTP de esta sección de la plantilla es muy parecido a los informes TCP. No se trata de comprobar si las llamadas son malas o buenas, sino de si la llamada está conectada a través de HTTP.

![Captura de pantalla del informe de transmisiones de audio que usan HTTP](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Análisis

Desea ver el menor número de transmisiones multimedia HTTP posibles. Si tiene transmisiones que pasen por el servidor proxy, póngase en contacto con su equipo de redes para asegurarse de que se aplican las exclusiones adecuadas para que los clientes se enrutar directamente a subredes de medios de Teams o Skype Empresarial Online.

Si solo tiene un proxy de Internet en su organización, compruebe las direcciones URL de [Microsoft 365 u Office 365](https://aka.ms/o365ips)adecuadas y las exclusiones de intervalos de direcciones IP. Si su organización tiene configurado más de un proxy de Internet, use el sub informe HTTP para aislar qué edificio o subred se ve afectada.

Para las organizaciones que no pueden omitir el proxy, asegúrese de que el cliente de Skype Empresarial esté configurado para iniciar sesión correctamente cuando se encuentra detrás de un proxy, como se describe en el artículo Skype Empresarial debe usar el servidor [proxy](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin)para iniciar sesión en lugar de intentar la conexión directa. 


#### <a name="http-proxy-investigations"></a>Investigaciones de proxy HTTP

Este informe identifica determinadas construcciones y subredes que contribuyen al uso de HTTP.


##### <a name="remediation"></a>Corrección

Le [recomendamos](proxy-servers-for-skype-for-business-online.md) que siempre omita servidores proxy para Skype Empresarial y Teams, especialmente el tráfico multimedia. Los servidores proxy no hacen que Skype Empresarial sea más seguro, porque su tráfico ya está cifrado. Los problemas relacionados con el rendimiento pueden introducirse en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos darán como resultado una experiencia negativa con el audio, el vídeo y el uso compartido de la pantalla, donde las transmisiones en tiempo real son esenciales.

La causa más habitual del uso de HTTP son las reglas de excepción que hay en los servidores proxy. Mediante la creación o subred proporcionada, puede determinar rápidamente qué proxy es necesario configurar para la omisión de medios.

Compruebe que los [FQDN de Microsoft 365 u Office 365](https://aka.ms/o365ips) necesarios están en la lista blanca en el proxy.

## <a name="endpoint-investigations"></a>Investigaciones de extremos

Esta sección se centra en las tareas para informar sobre las versiones de cliente y el uso de dispositivos certificados. Los informes están disponibles para hacer un esquema del uso de las versiones del cliente, el tipo de cliente, los dispositivos de captura y los controladores (micrófono), los dispositivos de captura de vídeo y Wi-Fi del proveedor y controlador.

> [!NOTE]
> No todos los informes incluidos en las plantillas se tratan en este artículo; sin embargo, aún se aplican los métodos de investigación explicados a continuación. Consulte la descripción del informe individual para obtener más información.

### <a name="client-versions"></a>Versiones de cliente

Estos informes se centran en la identificación de las versiones de cliente de Skype Empresarial en uso y su volumen relativo en el entorno.

> [!IMPORTANT]
> Actualmente, los clientes de Teams se distribuyen y actualizan automáticamente a través de la red de entrega de contenido de Azure y el servicio los mantiene actualizados. Como resultado, no es necesario supervisar las versiones de cliente de Teams (a menos que desactive la actualización automática, lo que no recomendamos).

A menos que excluya los datos de participantes federados, estos informes incluirán telemetría de cliente de puntos de conexión federados. Para excluir puntos de conexión federados, debe agregar un filtro de consulta para el segundo id. de inquilino establecido al id. de inquilino [de su organización.](CQD-data-and-reports.md#how-to-find-your-tenant-id) Como alternativa, puede usar un filtro [de dirección URL para](CQD-data-and-reports.md#url-filters) excluir la telemetría de participantes federados.



#### <a name="remediation"></a>Corrección

Una parte esencial del desarrollo de experiencias de usuario de alta calidad es garantizar que los clientes administrados estén ejecutando versiones actualizadas de Skype Empresarial, además de garantizar que los controladores de audio, vídeo, red y USB compatibles estén actualizados. Esto proporciona varias ventajas, entre ellas: 

-   Es más fácil administrar unas pocas versiones y varias.
-   Proporciona un nivel de coherencia de la experiencia.
-   Facilita la solución de problemas de calidad y facilidad de uso de las llamadas.
-   Microsoft realiza continuamente mejoras generales y optimizaciones en todo el producto. Garantizar que los usuarios reciban estas actualizaciones reduce el riesgo de que se teme un problema que ya se haya resuelto.

Limitar la implementación a las versiones de cliente con menos de seis meses de antigüedad mejorará la experiencia general del usuario y mejorará la capacidad de administración al reducir el número de versiones que necesitan ser compatibles.

Si usa solo Hacer clic y ejecutar de Office, estará automáticamente en la ventana de seis meses. No es necesario realizar ninguna acción adicional.

Si tiene una combinación de Hacer clic y ejecutar y paquetes del instalador (MSI), puede usar el informe para comprobar que los clientes MSI se actualizan periódicamente. Si observa que los clientes se están quedado atrás, trabaje con el equipo responsable de administrar las actualizaciones de Office y asegúrese de que aprueban e implementan revisiones de cliente con regularidad.

También es importante tener en cuenta y asegurarse de que los controladores de red, vídeo, USB y audio también se están revisión. Puede ser fácil pasar por alto estos controladores y no incluirlos en su estrategia de administración de revisiones.

Los números de versión de Skype Empresarial se pueden encontrar a través de los siguientes vínculos:

-   [Información de la versión de las actualizaciones de las aplicaciones de Microsoft 365](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Historial de actualizaciones de las aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Descargas y actualizaciones de Skype Empresarial](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivos

Para usar el informe del dispositivo del micrófono, necesitamos comprender el concepto de la puntuación de opinión media (MOS). MOS es la medida gold-standard para medir la calidad de audio que se percibe. Se representa como una clasificación entera de 0 a 5.

La base de todas las medidas de calidad de voz es la forma en que una persona percibe la calidad del discurso. Como se ve afectado por la implicación humana, es intrínsecamente subjetivo. Existen varias metodologías diferentes para pruebas subjetivales. La mayoría de las medidas de calidad de voz se basan en una escala de clasificación de categorización absoluta (ACR).

En una prueba subjetiva ACR, un número estadísticamente significativo de personas valoran su calidad de experiencia en una escala de 1 (mala) a 5 (excelente). El promedio de las puntuaciones es el MOS. El MOS resultante depende del rango de experiencias que se han expuesto al grupo y del tipo de experiencia que se va a evaluar.

Como no resulta práctico realizar pruebas subjetivas de calidad de voz para un sistema de comunicación en directo, Microsoft Teams y Skype Empresarial generan valores MOS mediante algoritmos avanzados que pronostican de forma objetivo los resultados de una prueba subjetiva.

El conjunto de MOS y métricas asociados disponibles ofrecen una vista de la calidad de la experiencia que se entrega a los usuarios mediante un dispositivo de audio. 

Al proporcionar a los usuarios dispositivos certificados para Teams y Skype Empresarial, reduce la probabilidad de encontrar experiencias negativas debido al propio dispositivo (que es más probable, por ejemplo, con altavoces y micrófonos integrados de portátiles). Para obtener más información, consulte estos artículos sobre el programa [de certificación y](/SkypeForBusiness/certification/overview) el catálogo de soluciones de [partners.](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

Los informes de dispositivos se usan para evaluar el uso del dispositivo por volumen y la puntuación de MOS (solo audio), y se pueden encontrar en las plantillas que acompañan en Clientes & Dispositivos. 

> [!IMPORTANT]
> A menos que excluya los datos de participantes federados, estos informes incluirán telemetría de cliente de puntos de conexión federados. Para excluir puntos de conexión federados, debe agregar un filtro de consulta para el segundo **id.** de inquilino establecido al id. de inquilino [de su organización.](CQD-data-and-reports.md#how-to-find-your-tenant-id) A la vez, puede usar un filtro [de dirección URL para](CQD-data-and-reports.md#url-filters) excluir la telemetría de participantes federados.


> [!Note]
> Es posible que al ver este informe vea que el mismo dispositivo se ha notificado varias veces. Esto se debe a la forma en que se notifica que el dispositivo se notifica al CQD. Las diferencias en la configuración regional del hardware y del sistema operativo provocan diferencias en la forma en que se notifican los datos del dispositivo.

##### <a name="remediation"></a>Corrección

Normalmente, necesitará detectar y utilizar fases de los dispositivos no certificados y reemplazarlos por dispositivos certificados. Algunas consideraciones al revisar los informes de dispositivo son:

-   ¿Están certificados los dispositivos en uso para Teams y Skype Empresarial? 
-   Puede identificar usuarios de un dispositivo específico mediante el análisis [de llamadas por usuario.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Compruebe que tiene los controladores de dispositivo más recientes y que su dispositivo no está conectado a través de un concentrador USB o una estación de acoplamiento. 
-   ¿Cuántas versiones diferentes de varios controladores están en uso? ¿Se revisan periódicamente? Garantizar que los controladores de audio, vídeo y Wi-Fi se revisan periódicamente le ayudará a eliminar estos como origen de problemas de calidad y a que la experiencia del usuario sea más predecible y coherente.

##### <a name="audio"></a>Audio

La siguiente tarea es determinar el uso general de dispositivos [de audio certificados.](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) Se recomienda que al menos el 80 por ciento de todas las transmisiones de audio usen un dispositivo de audio certificado. Para ello, exporte el informe de dispositivos del micrófono a Excel y calcule el uso de dispositivos certificados o aprobados. Las organizaciones suelen tener una lista de todos los dispositivos aprobados, por lo que filtrar y ordenar los datos debería ser sencillo.

##### <a name="video"></a>Vídeo

Los controladores de vídeo también son importantes para mantenerse actualizados. Garantizar que las tarjetas de vídeo se revisan periódicamente ayudará a excluir los controladores de vídeo como origen de mala calidad en las transmisiones de vídeo. El [uso de dispositivos de](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) vídeo certificados le ayudará a garantizar una experiencia de usuario fluida y de alta calidad. Los dispositivos de vídeo que admiten la codificación nativa H.264 son preferidos, para reducir el uso de la CPU durante las videoconferencias.

##### <a name="wi-fi"></a>Wi-Fi

Wi-Fi los controladores también necesitan revisión con una cadencia regular y deben incluirse en su estrategia de administración de revisiones. Muchos problemas de calidad se pueden corregir manteniendo actualizados los controladores de Wi-Fi calidad. Para obtener más información sobre la optimización de Wi-Fi infraestructura de almacenamiento, vea [este artículo sobre Wi-Fi planeamiento.](/skypeforbusiness/certification/networking-wifi)


## <a name="related-topics"></a>Temas relacionados

[Usar Asesor para Teams](use-advisor-teams-roll-out.md)

[Preparar la red para Teams](prepare-network.md)

[Principios de conectividad de red de Office 365](https://aka.ms/pnc)

[Análisis e informes de Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Administrar los dispositivos en Teams](device-management.md)

[Mejorar y supervisar la calidad de las llamadas en Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar datos de inquilino y de edificio](CQD-upload-tenant-building-data.md)

[Informes y datos del CQD](CQD-data-and-reports.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)

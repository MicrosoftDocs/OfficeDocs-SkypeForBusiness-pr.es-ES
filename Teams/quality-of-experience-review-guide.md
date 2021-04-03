---
title: Usar CQD para administrar la calidad de las llamadas y reuniones en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Obtenga información sobre cómo analizar y administrar el rendimiento multimedia en tiempo real en Microsoft Teams mediante el Panel de calidad de llamadas (CQD).
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
ms.openlocfilehash: 85b860965c7883d5df9bc734bc336fb2d24a5ed8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574149"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Usar CQD para administrar la calidad de las llamadas y reuniones en Microsoft Teams 

Este artículo le ayudará a desarrollar un proceso para supervisar y mantener la calidad de las llamadas y reuniones de su organización mediante el Panel de calidad de llamadas (CQD) de Microsoft Teams. Nuestras instrucciones hacen hincapié en los escenarios de calidad de audio, ya que las mejoras de red que realice para mejorar la experiencia de audio se traducirán en mejoras en vídeo y uso compartido.

Clave de esta guía son las dos plantillas [de CQD](https://aka.ms/QERtemplates) seleccionadas: le recomendamos que las descargue antes de seguir las instrucciones de este artículo.

En este artículo se supone que ya ha [configurado CQD.](turning-on-and-using-call-quality-dashboard.md)


## <a name="categories-to-monitor-and-maintain"></a>Categorías para supervisar y mantener

Una vez que haya lanzado reuniones y voz en Teams, necesitará un plan para la supervisión y el mantenimiento continuos. Al hacerlo, se asegurará de que Teams siempre funciona de forma óptima. Este plan debe incluir las áreas clave que se muestran a continuación. También debe establecer objetivos para métricas de calidad y un plan para solucionar problemas y aislarlos cuando se den.

<table>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Calidad de llamada</strong></td>
<td>
<p>Dividir las métricas mediante llamadas internas (dentro de su organización, como VPN, WiFi, por cable) o llamadas externas</p>
<p>Dividir las métricas mediante la creación o la red</p>
<p>Llamadas VPN</p>
<p>Llamadas con TCP, UDP o proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Confiabilidad de llamadas</strong></td>
<td><p>Identificar y corregir cualquier problema de red o firewall</p>
<p>Obtener información sobre los porcentajes de errores de configuración y colocación de llamadas</p>
<p>Obtenga información sobre dónde se producen la mayoría de los errores de configuración y colocación de llamadas</p>
</td>
</tr>
<tr class="odd">
<td><strong>Encuesta de usuario</strong></td>
<td>
<p>Usar los datos de Calificar mi llamada para obtener información sobre la experiencia real de los usuarios</p>
<p>¿Dónde se producen las malas experiencias?</p>
<p>Correlacionar la mala experiencia con la calidad de las llamadas, la confiabilidad y los dispositivos</p>
</td>
</tr>
<tr class="even">
<td><strong>Dispositivos</strong></td>
<td><p>Obtenga información sobre los micrófonos y altavoces que se usan con más frecuencia y su impacto en la calidad de la llamada</p>
<p>¿Se revisan periódicamente los controladores de audio, vídeo, USB y WiFi compatibles?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clientes</strong></td>
<td>
<p>Obtenga información sobre los tipos de cliente y las versiones que se usan y su impacto en la calidad y confiabilidad de las llamadas  </p>
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

A través de la planeación y el diseño adecuados antes de implementar Teams o Skype Empresarial Online, puede reducir la cantidad de esfuerzo necesario para mantener experiencias de alta calidad.

Este artículo se centra en usar el Panel de calidad de llamadas (CQD) Online como la herramienta principal para informar e investigar cada área, con un énfasis especial en el audio para maximizar la adopción y el impacto. Las mejoras realizadas en la red para mejorar la experiencia de audio también se traducirán directamente en mejoras en el uso compartido de vídeo y escritorio.

Para acelerar la evaluación, se proporcionan dos plantillas [de CQD](https://aka.ms/qertemplates) seleccionadas: una es para administrar todas las redes y la otra se filtra solo para redes administradas (internas). Aunque los informes de plantilla Todas las redes están configurados para mostrar información de creación y red, aún se pueden usar mientras trabaja para recopilar y cargar información del edificio. Cargar información de creación en CQD permite al servicio mejorar la creación de informes agregando información personalizada de creación, red y ubicación, al tiempo que diferencia las subredes internas de las externas. Para obtener más información, lea [Asignación de creación.](CQD-building-mapping.md)

### <a name="intended-audience"></a>Público previsto

Este artículo está destinado a ser usado por partes interesadas de partners y clientes con roles como Jefe de colaboración/arquitecto, Consultor, Especialista en administración de cambios y adopción, Jefe de soporte y asistencia, Cliente potencial de red, Cliente potencial de escritorio y Administrador de TI.

Este artículo también está destinado a ser usado por los campeones de calidad designados. Para obtener más información, vea [el rol Campeón de calidad](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>¿Qué es la calidad?

En este contexto, la calidad es una combinación de métricas de servicio y experiencia de usuario.


### <a name="service-metrics"></a>Métricas de servicio

Las métricas de servicio constan de métricas específicas basadas en clientes. Durante cada llamada, el cliente recopila telemetría para la llamada y envía un informe al final de cada llamada a la que posteriormente se puede acceder en CQD o en análisis de llamadas por [usuario.](set-up-call-analytics.md) Estas métricas incluyen (pero no se limitan a):

-   Poor Stream (entrante y saliente)
-   Tasa de errores de configuración
-   Tasa de errores de colocación


#### <a name="poor-stream-rate"></a>Tasa de transmisión deficiente

La tasa de transmisión deficiente (PSR) representa el porcentaje general de transmisiones de la organización que tienen mala calidad. Esta métrica está destinada a resaltar las áreas en las que su organización puede concentrar esfuerzos para [](#managed-versus-unmanaged-networks) tener el mayor impacto en reducir este valor y mejorar la experiencia del usuario, por lo que las redes administradas son el foco principal al ver LAP. Los usuarios externos también son importantes, pero la investigación difiere en función de la organización. Considere la posibilidad de proporcionar procedimientos recomendados para usuarios externos e investigar llamadas externas de forma independiente de la organización general.

La medición real de CQD varía según la carga de trabajo, pero para los fines de este artículo, nos centramos principalmente en la medición de _porcentaje_ de audio deficiente. PSR está compuesta por los cinco promedios de métricas de red que se describen en la tabla siguiente. Para que una transmisión se clasifique como mala, solo una métrica debe superar el umbral definido. CQD proporciona el "Poor Due To..." medidas para comprender mejor qué condición hizo que la transmisión se clasificara como mala. Para obtener más información, lea [Clasificación de transmisión en CQD](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> CQD proporciona el "Poor due to..." medidas para comprender mejor qué condición hizo que la transmisión se clasificara como mala.


##### <a name="audio-poor-quality-metrics"></a>Métricas de mala calidad del audio

| Promedio de métricas     | Descripción     | Experiencia de usuario |
|-------------|-----------------|-----------------|
| Vibración \> 30 ms        | Este es el cambio promedio de retraso entre paquetes sucesivos. Teams y Skype Empresarial pueden adaptarse a algunos niveles de vibración a través del almacenamiento en búfer. Solo cuando el vibración supera el almacenamiento en búfer, un participante observa los efectos de la vibración.      | Los paquetes que llegan a diferentes velocidades hacen que la voz de un orador suene robotizada.   |
| Tasa de pérdida de paquetes \> 10% o 0,1        | Esto suele definirse como un porcentaje de paquetes que se pierden. La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individuales que casi no tienen ningún impacto a las pérdidas de ráfagas de back-to-back que hacen que el audio se corte por completo.     | Los paquetes que se caen y no llegan a su destino previsto provocan espacios en los medios, lo que provoca sílabas y palabras perdidas, y vídeo y uso compartido entrecortados. |
| Tiempo de ida y vuelta \> 500 ms        | Este es el tiempo que se tarda en obtener un paquete IP desde el punto A hasta el punto B y volver al punto A. Este retraso de propagación de red está vinculado a la distancia física entre los dos puntos y la velocidad de la luz, e incluye una sobrecarga adicional realizada por los distintos dispositivos en la ruta de red.      | Los paquetes que tardan demasiado en llegar a su destino provocan un efecto walkie-talkie.   |
| Promedio de degradación de NMOS \> 1,0         | Degradación [media de la puntuación de opinión media de red (NMOS)](/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) para la transmisión. Representa cuánto ha afectado la pérdida de red y el vibración a la calidad del audio recibido que hizo que el NMOS bajara en más de un punto. | Se trata de una combinación de vibración, pérdida de paquetes y, en menor medida, aumento del tiempo de ida y vuelta. Es posible que el usuario esté experimentando una combinación de estos síntomas.   |
| Relación media de muestras ocultas \> 7% o 0,07 | Relación media del número de tramas de audio con muestras ocultas generadas por la recuperación de pérdida de paquetes con el número total de tramas de audio. Una muestra de audio oculta es una técnica que se usa para suavizar la transición brusca que suele deberse a paquetes de red eliminados.      | Los valores altos indican que se aplicaron niveles significativos de ocultación de pérdidas y que resultaron en audio distorsionado o perdido.     |

##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>¿Por qué preferimos usar transmisiones en lugar de llamadas?

Las transmisiones nos permiten saber qué tramo concreto de la llamada era deficiente: saliente o entrante. Cuando esté buscando análisis de llamadas para una llamada deficiente, determine si la llamada mala se debió a la transmisión (saliente) o a la transmisión del destinatario (entrante). Determinar qué transmisión está afectando a la calidad de las llamadas es aún más importante para las conferencias. Si solo está mirando los datos de las llamadas, verá cuántas conferencias participa una persona, pero no verá en qué personas están activas, lo que hace el máximo uso compartido de pantalla.

Los datos de llamadas le proporcionan métricas de uso, pero no necesariamente le conducirán a la causa raíz de la mala calidad de las llamadas. Al ver la dirección de la transmisión, puede identificar factores como una llamada que no está en una red administrada, una llamada de un no empleado (por ejemplo, un proveedor o alguien de una red diferente). En estos casos, si la conexión de red de la otra persona era mala, toda la llamada se marcará como mala. No puede hacer nada con los factores externos, por lo que estos datos no son útiles.

La dirección de transmisión también puede ayudarle a identificar dispositivos o clientes problemáticos.

 - Por ejemplo, si tiene un presupuesto limitado para dispositivos y desea proporcionar dispositivos solo para usuarios de audio pesado, use el informe de uso de audio (VoIP) y filtre para las transmisiones salientes y las conferencias. Busque usuarios de audio de alto volumen que hablen en micrófonos integrados: estos pueden correlacionarse con una calidad de llamada más baja (y es posible que desee proporcionar dispositivos de audio para estas personas). Para mayor claridad, puede filtrar por el uso de paquetes, lo que le permitirá dirigirse especialmente a usuarios de audio de alto volumen. 

  - Otro ejemplo implica el uso compartido de pantalla. Si un cliente usa un cliente de Teams antiguo, el rendimiento de uso compartido de pantalla puede verse afectado. Puede solucionar este problema priorizando las actualizaciones de cliente para las personas que hacen una gran cantidad de uso compartido de pantalla.

 - Al identificar qué dirección de una transmisión está causando mala calidad de llamada, puede determinar si tiene un problema de QoS o de ancho de banda. Si no ha implementado completamente QoS, o si solo marca los paquetes en el cliente y no en la transmisión entrante, es posible que vea una calidad de llamada más baja. Al ver la dirección de la transmisión, puede obtener una vista más granular de la pérdida de paquetes, latencia o vibración en una dirección específica. 

   - Por ejemplo, supongamos que un usuario se queja del audio robotizado mientras está conectado a una conexión por cable (vibración). Al ver la transmisión y la dirección, puede determinar que el problema se produce en la transmisión entrante, solo para un conjunto específico de subredes. Después de proporcionar esta información a su equipo de redes, pueden rastrearla hasta un acelerador WAN mal configurado que no omitía el tráfico multimedia. Una vez que el equipo de red vuelva a configurar el acelerador WAN, el vibración desaparecerá y la calidad de las llamadas mejorará. 


#### <a name="setup-failure-rate"></a>Tasa de errores de configuración

La tasa de errores de configuración, también conocida como la medida Porcentaje de errores de configuración _total_ de llamadas en CQD, es el número de transmisiones en las que no se pudo establecer la ruta de acceso multimedia entre los puntos de conexión al comienzo de la llamada.

Esto representa cualquier transmisión multimedia que no se pudo establecer. Dada la gravedad del impacto de este problema en la experiencia del usuario, el objetivo es reducir este valor a lo más próximo a cero posible. Un valor alto para esta métrica es más común en las nuevas implementaciones con reglas de firewall incompletas que en una implementación madura, pero sigue siendo importante ver periódicamente.

Esta métrica se calcula tomando el número total de transmisiones que no se han configurado divididas por el número total de transmisiones que enviaron un registro de detalles de llamada (CDR) correcto:

-   **Setup Failure Rate** = Total Call Setup Failed Stream Count / Total CDR Available Stream Count

#### <a name="drop-failure-rate"></a>Tasa de errores de colocación

La tasa de errores de  colocación, también conocida como la medida Porcentaje total de errores de llamada descartada en CQD, es el porcentaje de transmisiones establecidas correctamente en las que la ruta de acceso multimedia no terminaba normalmente.

Esto representa cualquier transmisión multimedia que terminó inesperadamente. Aunque el impacto de esto no es tan grave como una transmisión que no se pudo configurar, sigue afectando negativamente a la experiencia del usuario. Las caídas repentinas y frecuentes de los medios no solo pueden tener un impacto grave en la experiencia del usuario, sino que se traducen en la necesidad de que los usuarios vuelvan a conectarse, lo que provoca la pérdida de productividad (sin mencionar la frustración).

La métrica se calcula tomando el número total de transmisiones descartadas divididas por el recuento total de transmisiones que se configuraron correctamente:

-   **Drop Failure Rate** = Total Call Dropped Stream Count / Total Call Setup Succeeded Stream Count

### <a name="define-your-target-metrics"></a>Definir las métricas de destino

En esta sección se debatieron algunas de las métricas principales del servicio que usamos para evaluar el estado de los servicios. Al evaluar e impulsar continuamente los esfuerzos para mantener estas métricas por debajo de sus objetivos definidos, ayudará a garantizar que los usuarios experimenten una calidad de llamada coherente y confiable. Como punto de partida, use los destinos sugeridos en la tabla siguiente. Ajuste los objetivos según sea necesario para cumplir sus objetivos empresariales.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo de red</th><th rowspan="1">Objetivos de calidad</th><th colspan="2">Objetivos de confiabilidad</th></tr>
<tr><th>Audio Poor Stream Rate</th><th>Tasa de errores de configuración</th><th>Tasa de errores de colocación</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>General</td><td>3.0%</td><td>1.0%</td><td>3.0%</td></tr>
<tr><td rowspan="5"><strong>Conferencia</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Interna cableada</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi 5 GHz interna</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi 2,4 GHz interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>General</td><td>2.0%</td><td>0.5%</td><td>3.0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Cableada/Wi-Fi 5 GHz interna</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Cableada/Wi-Fi 5 GHz en general</td><td>2.0%</td><td>1.0%</td><td>1.0%</td></tr>
<tr><td>General</td><td>2.0%</td><td>1.0%</td><td>3.0%</td></tr>
</table>

### <a name="user-experience"></a>Experiencia de usuario

Analizar la experiencia del usuario es más artístico que científico, ya que las métricas recopiladas aquí no siempre significan que hay un problema con la red o el servicio, sino que simplemente indican que el usuario percibe un problema. CQD incluye un mecanismo de encuesta integrado ( Calificar mi llamada (RMC) - para ayudar a evaluar la experiencia general del usuario. RMC le dará información sobre las siguientes preguntas desde la perspectiva de los usuarios:

-   ¿Sé cómo usar la solución?
-   ¿La solución es fácil de usar e intuitiva y es compatible con mis necesidades de comunicación diarias?
-   ¿La solución me ayuda a realizar mi trabajo?
-   ¿Cuál es mi percepción general de la solución?
-   ¿Puedo usar la solución en cualquier momento, independientemente de dónde estoy?
-   ¿Puedo configurar y mantener una llamada?

#### <a name="rate-my-call"></a>Calificar mi llamada 

Calificar mi llamada (RMC) está integrado en Teams y Skype Empresarial. Aparece automáticamente después de una de cada 10 llamadas, o 10 por ciento. En esta breve encuesta se pide al usuario que la tasa de la llamada y proporcione un poco de contexto para saber por qué la calidad de la llamada podría haber sido mala. Una calificación de uno o dos se considera mala, de tres a cuatro es buena y cinco es excelente. Aunque es algo así como un indicador de retraso, esta es una métrica útil para descubrir problemas que las métricas de servicio pueden perderse.

> [!Note]
> El factor humano: los usuarios suelen ignorar la encuesta cuando la calidad de la llamada es buena y la rellenan cuando la calidad de la llamada es mala. Como resultado, los informes de RMC pueden estar sesgados al lado malo, incluso aunque las métricas de servicio sean buenas.

Puede usar CQD para informar sobre las respuestas de usuario de RMC y los informes de ejemplo se incluyen en la plantilla CQD. Sin embargo, no se debate en detalle en este artículo. 

#### <a name="client-and-device-readiness"></a>Preparación del cliente y del dispositivo

Necesita una estrategia sólida de cliente y dispositivo para garantizar que los usuarios tengan una experiencia de usuario coherente y positiva. Algunos principios clave impulsan cada estrategia de preparación.

##### <a name="client-readiness"></a>Preparación del cliente

Mantener el cliente de Teams actualizado garantiza que los usuarios siempre estén obteniendo la mejor experiencia posible. Microsoft publica actualizaciones frecuentes para el cliente [de Teams](teams-client-update.md) (la actualización se instala en segundo plano a menos que haya desactivado esta funcionalidad, que no se recomienda). También es importante recordar la revisión de controladores de red, vídeo, USB y audio, ya que a menudo se pasan por alto y pueden afectar a la calidad de las llamadas y las reuniones. Considere la posibilidad de agregar controladores de red, Wi-Fi, vídeo, USB y audio al proceso de administración de revisiones actual.


##### <a name="device-readiness"></a>Preparación del dispositivo

Ninguna sola estrategia puede afectar a la experiencia del usuario más que la estrategia de preparación del dispositivo. Por ejemplo, los usuarios que dependen de los altavoces y el micrófono de su portátil experimentarán una gran cantidad de ruido de fondo en llamadas y reuniones. Teams está diseñado para trabajar con casi cualquier dispositivo, pero si tiene problemas relacionados con el dispositivo, consulte [Teléfono para Teams.](./devices/phones-for-teams.md)


### <a name="categories-of-quality"></a>Categorías de calidad

Poner en marcha un conjunto de prácticas de administración de calidad: esto le ofrece la mejor oportunidad de una buena calidad de llamada y reunión. Un buen plan de administración de calidad trata estas categorías:

-   **Red:** Calidad de audio centrada en la métrica de relación de transmisión deficiente (PSR), el uso de TCP, subredes cableadas e inalámbricas e identificación del uso de servidores proxy HTTP y VPN

-   **Puntos de conexión:** Dispositivos de audio y clientes actualizados

-   **Administración de servicios:** Esta categoría consta de dos secciones:

    -   En primer lugar, es responsabilidad de Microsoft administrar y mantener los servicios de Teams y Skype Empresarial Online.

    -   En segundo lugar, se encuentran las tareas que su organización administra para garantizar un acceso confiable al servicio, como actualizar la información de creación y mantener firewalls para las nuevas direcciones IP de Office 365 a medida que se agrega infraestructura al servicio.

![Gráfico de las categorías de calidad de una organización](media/qerguide-image-categories.png "Las categorías de calidad de una organización: administración de servicios, puntos de conexión y la red.")

Revise la siguiente lista de tareas recomendadas para mantener la calidad. Debe realizar estas tareas periódicamente, por ejemplo, semanalmente.

#### <a name="service-management-tasks"></a>Tareas de administración de servicios

Estas tareas van desde asegurarse de que hay ancho de banda suficiente para llegar al servicio sin saturar los vínculos a Internet, validar la calidad del servicio (QoS) en todas las áreas de red administradas y mantenerse al tanto de los intervalos IP de [Office 365 en firewalls.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

#### <a name="network-tasks"></a>Tareas de red

Hay dos categorías de tareas de red: confiabilidad y calidad. La confiabilidad se centra en medir la capacidad del usuario para realizar llamadas correctamente y mantenerse conectado. La calidad se centra en la telemetría agregada enviada a Teams y Skype Empresarial Online por el cliente del usuario durante la llamada y después de que haya finalizado. 

Dado el impacto crítico que la confiabilidad tiene en la experiencia del usuario, le recomendamos que evalúe e investigue las métricas de confiabilidad antes de profundizar en la calidad. 

#### <a name="endpoints-tasks"></a>Tareas de puntos de conexión

La tarea principal de esta categoría quitando los obstáculos a las actualizaciones de cliente [de Teams normales.](teams-client-update.md) De forma predeterminada, Teams se actualiza automáticamente periódicamente (a menos que desactive esa configuración, que no se recomienda). 

También debe supervisar dispositivos y proporcionar actualizaciones siempre que identifique problemas relacionados con un dispositivo.

## <a name="use-cqd-to-manage-call-quality"></a>Usar CQD para administrar la calidad de las llamadas

Una vez que haya [configurado CQD,](turning-on-and-using-call-quality-dashboard.md)estará listo para empezar a usarlo para administrar la calidad de las llamadas y las reuniones de su organización.

La mayoría de los problemas con el rendimiento de Teams se divide en las siguientes categorías:

-   Una configuración de proxy o firewall incompleta
-   Una cobertura Wi-Fi insuficiente
-   Un ancho de banda insuficiente
-   VPN
-   Controladores y versiones de cliente incoherentes o obsoletas
-   Dispositivos de audio integrados o sin optimizar
-   Dispositivos de red o subred problemáticos

Si se toma el tiempo antes de la implementación de Teams para evaluar estas áreas y corregir las deficiencias, reducirá la cantidad de esfuerzo necesario para mantener una experiencia de Teams de alta calidad para todos los usuarios. Para obtener ayuda para evaluar la red en preparación para la implementación de Teams, lea [Asesor para Teams](use-advisor-teams-roll-out.md) y Preparar su red para [Teams.](prepare-network.md)

### <a name="expectations-using-cqd"></a>Expectativas con CQD

Use el Panel de calidad de llamadas (CQD) para obtener información sobre la calidad de las llamadas realizadas mediante Teams y los servicios de Skype Empresarial. CQD está diseñado para ayudar a los administradores de Teams y Skype Empresarial y a los ingenieros de red a optimizar la red y mantener un seguimiento de la calidad, la confiabilidad y la experiencia del usuario. CQD examina telemetría agregada para toda una organización, donde los patrones generales pueden ser evidentes; esto le permite realizar evaluaciones fundamentadas y planear la corrección. CQD proporciona informes de métricas que proporcionan información sobre la calidad general, la confiabilidad y la experiencia del usuario.

CQD, aunque es útil para analizar tendencias y subredes, no siempre proporciona una causa específica para un escenario determinado. Es importante comprender esto y establecer la expectativa correcta al usar CQD:

-   CQD no proporcionará la causa raíz para cada escenario
-   CQD no contendrá transmisiones de sistema telefónico o audioconferencia
-   CQD llamará a áreas para investigar más a partir de tendencias

### <a name="cqd-reports-overview"></a>Información general sobre informes CQD

Use el menú desplegable de la parte superior de la pantalla para abrir un informe. Para obtener una lista de los datos proporcionados en cada informe, lea [Datos disponibles en informes CQD](CQD-data-and-reports.md#data-available-in-cqd-reports).

Nuevo en enero de 2020: Descargar plantillas de consulta [de Power BI para CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Plantillas de Power BI personalizables que puede usar para analizar e informar de los datos de CQD.


### <a name="teams-vs-skype-for-business"></a>Teams vs. Skype Empresarial

CQD puede informar tanto en Teams como en Skype Empresarial. Sin embargo, es posible que haya ocasiones en las que quiera desarrollar un informe para ver telemetría de Teams independiente de Skype Empresarial.

#### <a name="summary-reports"></a>Informes de resumen

Para modificar la página de informes de resumen para ver  solo Teams o Skype Empresarial, seleccione el menú desplegable Filtro de producto de la parte superior de la pantalla y, a continuación, seleccione el producto que desee.

![Captura de pantalla del menú desplegable que muestra las opciones de filtro](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Informes detallados

Para filtrar todos los informes detallados, en la barra del explorador, anexe lo siguiente al final de la dirección URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Ejemplo:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obtener más información sobre los filtros de dirección URL, lea [Filtrar informes](CQD-data-and-reports.md#report-filters) más adelante en esta sección.

Para filtrar un informe detallado individual, agregue el filtro al informe y establezca el filtro ``Is Teams`` en Verdadero o Falso.

![Captura de pantalla de la página Agregar filtro](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Redes administradas frente a redes no administradas

De forma predeterminada, todos los puntos de conexión de CQD se clasifican como externos. Tan pronto como se introduce un archivo de creación, podemos empezar a ver los datos de punto de conexión administrados. Como se ha comentado anteriormente, las redes en CQD se definen como:

-   Una _red administrada,_ a menudo denominada interna o interna, puede ser influenciada y controlada por la organización. Esto incluye la LAN interna, la WAN remota y la VPN.
-   Una _red no administrada,_ a menudo denominada externa o externa, no puede ser influenciada ni controlada por la organización. Un ejemplo de una red no administrada es una red de hotel o aeropuerto.

### <a name="dimensions-measures-and-filters"></a>Dimensiones, medidas y filtros

Una consulta CQD bien formada contiene los tres parámetros siguientes:

-   **Dimensión:** Cómo quiero pivotar sobre los datos.

-   **Medida:** Sobre lo que quiero informar.

-   **Filtro:** Cómo quiero reducir el conjunto de datos que devuelve la consulta.

Otra forma de ver esto es que una dimensión  es la función de agrupación,  una medida son los datos que me interesan y un filtro es cómo quiero restringir los resultados _a_ los que son relevantes para mi consulta.

Un ejemplo de una consulta bien formada es **Mostrarme transmisiones deficientes [Medida]** por subred [Dimensión] para el edificio 6 [Filtro]. Para obtener más información, vea [Dimensiones y medidas disponibles en CQD.](./dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="first-vs-second"></a>First vs. second 

Muchas de las dimensiones y medidas de CQD se clasifican como primero o segundo. CQD no usa los campos de llamada o  llamada,  que se han cambiado de nombre primero y segundo porque hay pasos de intervención entre el autor de la llamada y el destinatario. La siguiente lógica determina qué punto de conexión implicado se etiqueta como primero:

-   **En** primer lugar, siempre será un punto de conexión de servidor (servidor de conferencias, servidor de mediación, entre otros) si un servidor está implicado en la transmisión o llamada.

-   **El** segundo siempre será un punto de conexión de cliente a menos que la transmisión esté entre dos puntos de conexión de servidor.

-   Si ambos puntos de conexión son del mismo tipo, la elección de los cuales primero se basa en el orden interno de la categoría de agente de usuario. De este modo se asegura que el orden es coherente.

Para obtener más información sobre cómo determinar el primer punto de conexión o el segundo cuando ambos son iguales, vea Dimensiones y [medidas disponibles en CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="stream-vs-call"></a>Stream vs. call

Debe comprender la diferencia entre una llamada y una transmisión para elegir correctamente qué dimensiones o medidas verá en CQD. Aunque el foco principal de CQD está en las transmisiones, las medidas basadas en llamadas también están disponibles.

-   **Transmisión en secuencia:** Existe _una transmisión_ entre solo dos puntos de conexión. Solo hay una transmisión en cada dirección y se necesitan dos transmisiones para la comunicación. Las transmisiones son útiles para investigar edificios, redes o subredes. En algunos casos, tanto la llamada como la transmisión se usan en el nombre de la medida (por ejemplo, Secuencia de configuración de llamadas o Transmisión de llamadas descartada). Estos siguen estando clasificados como transmisiones.

-   **Llamar:** Una _llamada_ es una agrupación de todas las transmisiones de todos los participantes. Una llamada consta, como mínimo, de dos transmisiones. Una sola llamada tendrá al menos dos puntos de conexión, cada uno con un mínimo de una transmisión.

Para obtener instrucciones adicionales sobre si la dimensión o medida hace referencia a una llamada o una transmisión, vea Dimensiones y [medidas disponibles en CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="good-poor-and-unclassified-calls"></a>Llamadas buenas, malas y sin clasificar

Una llamada se clasifica como buena, mala o sin clasificar. Tomemos un momento para hablar de cada uno con más detalle.

-   **Bueno o malo:** Una llamada buena o mala consiste en una llamada que contiene un conjunto completo de métricas de servicio, para las que el servicio generó y recibió un informe completo de QoE. Determinar si una transmisión es buena o mala se describe [anteriormente en este artículo.](#poor-stream-rate)

-   **Sin clasificar:** Una transmisión sin clasificar no contiene un conjunto completo de métricas de servicio. Pueden ser llamadas cortas (normalmente menos de 60 segundos), en las que no se pudieron calcular los promedios y no se generó un informe de QoE. La razón más común para que las llamadas no se clasificaron es que había poco o ningún uso de paquetes. Un ejemplo de esto sería un participante que se une a una reunión en silencio y nunca habla. El participante recibe, pero no transmite, los medios. Sin la transmisión de medios, no habrá ninguna métrica disponible para que CQD la use para clasificar la transmisión multimedia saliente del punto de conexión.

Para obtener más información, lea [Clasificación de transmisión en CQD](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Subredes comunes

Las subredes comunes son subredes privadas específicas que se usan en hoteles, redes particulares, zonas activas y áreas similares. Estas subredes son difíciles de triage debido a su uso generalizado. Si su organización usa una de estas subredes comunes, le recomendamos que mueva esa red a otra subred. Esto facilitará la creación de informes en CQD. Cuando se indica, los informes de la plantilla Todas las redes se han configurado para excluir estas subredes para eliminarlas como una fuente de mala calidad. Las subredes comunes se definen a continuación; su impacto variará según la organización.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Al investigar una red administrada que usa una subred común, deberá usar la segunda dimensión IP local reflexiva para agrupar subredes. Esta dimensión contiene la dirección IP pública del punto de conexión.


## <a name="reliability-investigations"></a>Investigaciones de confiabilidad

El primer paso para mejorar la calidad es evaluar el estado de confiabilidad en toda la organización. Dado que la confiabilidad es vital para una experiencia de usuario positiva, empezamos con los dos componentes que miden la confiabilidad:

1.  **Errores de configuración:** No se pudo establecer la llamada.

2.  **Errores de colocación:** La llamada se estableció y se rescindió inesperadamente.

En esta sección, se tratarán los métodos para investigar ambas áreas.

> [!NOTE]
> No todos los informes incluidos en las plantillas se tratan en este artículo. Sin embargo, los métodos de investigación que se explican a continuación siguen siendo aplicables. Para obtener más información, consulte la descripción del informe individual.


### <a name="setup-failures"></a>Errores de configuración

Priorice primero la corrección de errores de configuración en esta área, ya que estos errores tienen un impacto negativo significativo en la experiencia del usuario.

Comience la investigación evaluando el porcentaje de errores generales de configuración de la organización y, a continuación, priorice las áreas de investigación en función del porcentaje más alto por creación o red. 

#### <a name="setup-failure-trend-analysis"></a>Análisis de tendencia de errores de configuración

Este informe muestra la cantidad total de transmisiones, los errores de configuración de la transmisión y la tasa de errores de configuración de la transmisión. Apunte a cualquiera de las columnas para mostrar sus valores individuales. 

##### <a name="analysis"></a>Análisis

Con este informe, puede responder a las siguientes preguntas y determinar su siguiente curso de acción:

-   ¿Cuál es el porcentaje total de errores de configuración de llamadas del mes actual?

-   ¿El porcentaje total de errores de configuración de llamadas está por debajo o por encima de la métrica de destino definida?

-   ¿Es la tendencia de fracaso peor o mejor que el mes anterior?

-   ¿La tendencia de errores está aumentando, estable o disminuyendo?

Independientemente de las respuestas a estas preguntas, tómese el tiempo necesario para investigar más a fondo con los subamens complementarios para buscar edificios o subredes individuales que necesiten corrección. Aunque la tasa general de errores podría estar por debajo de la métrica de destino, las tasas de error de uno o varios edificios o redes podrían estar por encima de la métrica de destino y necesitan una investigación.

#### <a name="setup-failure-investigations"></a>Investigaciones de errores de configuración 

Este informe de resumen se usa para detectar y aislar los edificios o redes que puedan necesitar corrección.

> [!NOTE]
> Asegúrese de ajustar el filtro de informe Año del mes al mes actual. Seleccione **Editar** y ajuste el filtro de informe **Año** del mes para guardar el nuevo mes predeterminado.

##### <a name="remediation"></a>Corrección 

Centre sus primeros esfuerzos de corrección en los edificios o subredes que tienen el mayor volumen de errores. Esto maximizará el impacto en la experiencia del usuario y ayudará a reducir rápidamente la tasa de errores de configuración de llamadas de la organización. En la tabla siguiente se enumeran los dos motivos por los que se han producido errores de configuración, tal y como ha informado CQD.

| Motivo de errores de configuración de llamadas       | Causa típica                    |
|----------------------------------|----------------------------------|
| Falta la regla de exención de inspección profunda de paquetes FW | Indica que el equipo de red a lo largo de la ruta de acceso impidió que se estableciera la ruta de acceso multimedia debido a reglas de inspección de paquetes profundas. Es probable que esto se deba a que las reglas de firewall no se han configurado correctamente. En este escenario, el apretón de manos TCP se ha hecho correctamente, pero el apretón de manos SSL no lo escribió.      |
| Falta la regla de excepción de bloque IP DE FW      | Indica que el equipo de red a lo largo de la ruta de acceso impedía que se estableciera la ruta de acceso multimedia a la red de Microsoft 365 u Office 365. Esto puede deberse a que las reglas de proxy o firewall no están configuradas correctamente para permitir el acceso a direcciones IP y puertos usados para el tráfico de Teams y Skype Empresarial. |

Al comenzar la corrección, puede centrar sus esfuerzos en un edificio o subred en particular. Como se muestra en la tabla anterior, estos problemas se deben a configuraciones de firewall o proxy. Revise las opciones de la tabla siguiente para ver las acciones de corrección.

|      Corrección      |Instrucciones  |
|-----------------------|----------|
| Configurar firewalls | Trabaje con su equipo de red y compruebe la configuración de firewalls en la lista de direcciones [IP de Office 365.](/microsoft-365/enterprise/urls-and-ip-address-ranges)<br><br>Compruebe que las [subredes multimedia y](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) los puertos están incluidos en las reglas del firewall. <br><br>Compruebe que los [puertos necesarios](prepare-network.md) están abiertos en el firewall. Udp debe tener prioridad porque TCP se considera un protocolo de conmutación por recuperación para el uso compartido de pantalla basado en audio, vídeo y vídeo, y su uso afectará a la calidad de la llamada. El uso compartido de aplicaciones RDP heredado solo usa TCP.|

### <a name="drop-failures"></a>Errores de colocación

A diferencia de los códigos de error de configuración, CQD no tiene ningún código de error de colocación para indicar por qué se producen errores de colocación, lo que dificulta aislar una causa raíz específica. Para mejorar los errores de colocación de triage, use un enfoque inferido. Al corregir cualquier área de interés para los medios, la revisión de clientes y controladores y el uso de dispositivos certificados para Teams y Skype Empresarial, puede esperar que los errores de colocación se rechace.

#### <a name="drop-failure-trend-analysis"></a>Análisis de tendencia de error de colocación

Este informe muestra la cantidad total de transmisiones de audio, los errores totales de colocación y la tasa de errores de colocación. Señale cualquiera de las columnas para mostrar sus valores. 


##### <a name="analysis"></a>Análisis

Con este tipo de informe, puede responder a las siguientes preguntas:

-   ¿Cuál es la tasa de errores de gota actual?
-   ¿La tasa de error de colocación está por debajo de la métrica de destino definida?
-   ¿Es la tendencia de fracaso peor o mejor que el mes anterior?
-   ¿La tendencia de errores está aumentando, estable o disminuyendo?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo necesario para investigar usando los sub-informes para buscar edificios o redes que puedan necesitar corrección. Aunque la tasa general de errores de colocación podría estar por debajo de la métrica de destino, la tasa de errores de colocación de uno o más edificios o redes podría estar por encima de la métrica de destino y necesita investigación.

#### <a name="drop-failure-investigations"></a>Investigaciones de errores de colocación

Los errores notificados aquí indican que la llamada se ha eliminado inesperadamente y ha dado como resultado una experiencia de usuario negativa. A diferencia de los informes de tendencias, estos informes proporcionan información adicional sobre subredes específicas que necesitan una investigación más exhaustiva.


##### <a name="remediation"></a>Corrección

Con los informes de tabla incluidos, puede aislar áreas problemáticas de la red donde la tasa de colocación está por encima de la métrica de destino que ha definido. Céntrate en los primeros esfuerzos de corrección en los edificios o subredes que tengan el mayor número total de transmisiones, para lograr el mayor impacto.

Causas comunes de los descensos de llamadas:

-   Salida de Internet o red no aprovisionada
-   Sin QoS configurado en redes restringidas
-   Versiones de cliente anteriores
-   Comportamiento del usuario

Después de descubrir las áreas problemáticas, puede usar [análisis](use-call-analytics-to-troubleshoot-poor-call-quality.md) de llamadas por usuario para revisar aún más los usuarios de esa creación para ver si hay problemas específicos. El análisis de llamadas contiene datos adicionales de EUII y puede ser útil para aislar aún más los posibles motivos de los errores de colocación.

Independientemente del paso siguiente, es una buena práctica notificar a su departamento de soporte técnico que se ha detectado un problema con edificios o subredes específicos. Esto permite que el departamento de soporte técnico responda rápidamente a las llamadas entrantes y a los usuarios de las preguntas y respuestas de forma más eficiente. Los usuarios marcados pueden volver a ser notificados al equipo de ingeniería para una investigación más exhaustiva.

En la tabla siguiente se enumeran algunos métodos comunes para administrar y corregir errores de colocación.

| Corrección                              | Instrucciones                      |
|------------------------------------------|-------------------------------|
| **Red/Internet**                         | **Congestión:** trabaje con su equipo de red para supervisar el ancho de banda en edificios o subredes específicos para confirmar que hay problemas con la sobreutilización. Si confirma que hay congestión de red, considere aumentar el ancho de banda a ese edificio o aplicar QoS. Use los informes de resumen [de](#quality-investigations) flujo deficiente de calidad incluidos para revisar las subredes del problema en busca de problemas de vibración, latencia y pérdida de paquetes, ya que estos suelen preceder a una transmisión descartada.<br><br>**QoS:** Si aumentar el ancho de banda es poco práctico o prohibitivo para el costo, considere la posibilidad de implementar QoS. Esta herramienta es muy eficaz para administrar el tráfico congestionado y puede garantizar que los paquetes multimedia de la red administrada se prioricen por encima del tráfico no multimedia. Como alternativa, si no hay evidencia clara de que el ancho de banda es el culpable, tenga en cuenta estas soluciones:<ul><li>[Instrucciones de QoS de Microsoft Teams](qos-in-teams.md)</li></ul><br>**Realizar una** evaluación de preparación de red: una evaluación de red proporciona detalles sobre el uso esperado del ancho de banda, cómo hacer frente a los cambios en el ancho de banda y la red, y prácticas de red recomendadas para Teams y Skype Empresarial. Con la tabla anterior como origen, tiene una lista de edificios o subredes que son excelentes candidatos para una evaluación.<ul><li>[Preparar la red de la organización para Microsoft Teams](prepare-network.md)</li></ul> |
| **Clientes (solo Skype Empresarial Online)** | Algunos clientes antiguos de Skype Empresarial han conocido y documentado problemas con la confiabilidad de los medios. Revise los informes de Análisis de llamadas de varios usuarios afectados o cree un informe de tabla de versión de cliente personalizado en CQD filtrado a edificios o subredes específicos con la medida % de error total de llamada descartada. Esta información le ayudará a comprender si existe una relación entre las llamadas caídas en ese edificio específico y una versión específica del cliente.     |
| **Dispositivos**                                  |Si los dispositivos son el culpable de los problemas de calidad de las llamadas, considere la posibilidad de actualizar los dispositivos infractores. Lea [Teléfonos para Teams](./devices/phones-for-teams.md) para obtener más información. |
| **Comportamiento del usuario**                            | Si determina que ni la red, los dispositivos ni los clientes son el problema, considere la posibilidad de desarrollar una estrategia de adopción de usuarios para educar a los usuarios sobre cómo unirse y salir mejor de las reuniones. Un usuario de Teams y Skype Empresarial más inteligente producirá una mejor experiencia de usuario para todos los participantes de la reunión. Por ejemplo, un usuario que pone su portátil en suspensión (cerrando la tapa) sin salir de la reunión se clasificará como una llamada inesperada.   |

## <a name="quality-investigations"></a>Investigaciones de calidad

El siguiente paso para evaluar el estado de la calidad de audio en toda la organización es investigar la tasa de transmisión deficiente (PSR), TCP y el uso de proxy. Es importante recordar que los datos de CQD no le proporcionan una causa raíz específica, sino que le proporciona áreas de problemas probables para iniciar una conversación de colaboración con los equipos adecuados para las actividades de corrección. 

> [!NOTE]
> No todos los informes incluidos en las plantillas se tratan en este artículo; sin embargo, los métodos de investigación que se explican a continuación seguirán siendo aplicables a esos informes. Consulte la descripción del informe individual para obtener más información. 

### <a name="quality"></a>Calidad

Los porcentajes de PSR se usan para indicar si la organización está con los objetivos de métrica definidos para un área de enfoque determinada. Es importante tener en cuenta que, incluso si los porcentajes de alto nivel están dentro del destino definido, es posible que las subredes individuales o los edificios no cumplan los objetivos definidos y, por lo tanto, necesiten una investigación más exhaustiva. Por ejemplo, si el porcentaje global de AUDIO PSR es 2 por ciento en abril, que cumple el objetivo de muestra, es posible que edificios individuales y subredes todavía tengan malas experiencias, dependiendo de la distribución global de ese 2 por ciento. 

Para evaluar el porcentaje de transmisiones deficientes, use los informes de calidad. Se proporcionan varios informes de calidad para revisar las métricas de general, conferencias, dos partes, llamadas RTC, VPN y salas de reuniones. Se proporcionan informes mensuales, semanales y diarios para ayudar en este proceso. Los informes semanales y diarios se limitan a la plantilla Redes administradas para aumentar su eficacia y reducir el ruido. 

#### <a name="quality-trend-analysis"></a>Análisis de tendencia de calidad

Los informes de tendencias muestran información de calidad a lo largo del tiempo y se usan para ayudar a identificar y comprender tendencias de calidad dentro de cada área de interés. Como se ha indicado anteriormente, hay árboles de informe incluidos en las plantillas para investigar la calidad; conferencias, dos partes, llamadas RTC, VPN y salas de reuniones. A efectos de analizar la calidad, el proceso de investigación es el mismo. Sin embargo, le recomendamos que empiece primero con las conferencias, ya que las mejoras en la calidad de la conferencia también afectarán positivamente al resto de áreas. 

> [!Note]
> Investigar las dos partes, las llamadas RTC y las salas de reuniones son similares a investigar conferencias. El foco es aislar edificios o subredes que tengan la peor calidad e identificar el motivo de la mala calidad.

> [!Important]
> Los informes basados en VPN se filtran con la segunda dimensión VPN. Esta dimensión requiere que el adaptador de red VPN se registre correctamente como adaptador de acceso remoto. Los proveedores de VPN no usan esta marca de forma confiable y su kilometraje variará según el proveedor de VPN implementado en su organización. Modifique los [informes de VPN](CQD-upload-tenant-building-data.md#vpn) si es necesario con el nombre de la red o el edificio.

##### <a name="investigation"></a>Investigación

Al usar estos informes, puede responder a las siguientes preguntas:

-   ¿Cuál es el PSR total del mes actual?
-   ¿Está el PSR por debajo de la métrica de destino definida?
-   ¿Es el PSR peor o mejor que el mes anterior?
-   ¿Está aumentando, estable o disminuyendo la tendencia del PSR?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo necesario para investigar usando los sub-informes para buscar los edificios o subredes que puedan necesitar investigación. Aunque el PSR general puede estar por debajo de la métrica de destino, a menudo el PSR para uno o varios edificios o redes está por encima de la métrica y necesita corrección.

#### <a name="quality-investigations"></a>Investigaciones de calidad

Los informes de resumen de calidad le proporcionan información más detallada sobre lo que contribuyó a que las transmisiones se clasificaran como malas y ayuda a aislar áreas problemáticas en la red administrada.

Aunque las dimensiones usadas pueden diferir ligeramente entre el informe, cada informe incluirá medidas para el total de transmisiones, el total de transmisiones deficientes, ELS y la mala calidad debido a. Se han creado informes para cada área de interés: conferencias, dos partes, llamadas RTC, VPN y salas de reuniones. La plantilla Red administrada incluye informes adicionales para aprovechar la información de ubicación cargada a través del archivo de creación.


> [!Note]
> Las subredes comunes son difíciles de recortar debido a su uso generalizado. Se ha agregado un informe independiente que muestra la IP pública del cliente (SECOND Reflexive Local IP) a la plantilla Todas las redes para ayudar a corregir las oficinas que usan redes comunes.


![Captura de pantalla que muestra el resumen de la transmisión de audio deficiente](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Corrección

Centre sus esfuerzos de corrección en los edificios o subredes que tienen el mayor volumen de transmisiones, ya que esto maximizará el impacto y ayudará a mejorar la experiencia del usuario rápidamente. Use las medidas de vibración, pérdida de paquetes y tiempo de ida y vuelta (RTT) para comprender lo que contribuye a la mala calidad (es posible que haya más de un problema):

-   **Vibración:** los paquetes multimedia llegan a diferentes velocidades, lo que hace que un altavoz suene robotizado.
-   **Pérdida de paquetes:** se están descartando los paquetes multimedia, lo que crea el efecto de falta de palabras o sílabas.
-   **RTT:** Los paquetes multimedia tardan mucho tiempo en llegar a su destino, lo que crea un efecto walkie-talkie.

Para ayudar a su investigación en problemas de calidad, use análisis de llamadas por [usuario.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Con Análisis de llamadas, puede ver una conferencia específica o el informe de llamadas del usuario. Este informe contendrá datos EUII/PII y es útil cuando busca la causa de un error. Una vez que sepa qué edificio se ve afectado, debería ser sencillo realizar un seguimiento de los usuarios de ese edificio. 

No olvide hacer saber a su departamento de soporte técnico que estas redes están experimentando problemas de calidad, por lo que pueden realizar una triaje y responder rápidamente a las llamadas entrantes.

| Corrección                              | Instrucciones                         |
|------------------------------------------|----------------------------------|
| **Redes**                                 | **Congestión:** una red sobreusada o no aprovisionada puede causar problemas con la calidad de los medios. Trabaje con el equipo de red para determinar si las conexiones de red del usuario al punto de salida de Internet tienen suficiente ancho de banda para admitir medios. <br><br>**Realizar una** evaluación de preparación de red: una evaluación de red proporciona detalles sobre el uso esperado del ancho de banda, cómo hacer frente a los cambios en el ancho de banda y la red, y prácticas de red recomendadas para Teams y Skype Empresarial. Con la tabla anterior como origen, tiene una lista de edificios o subredes que son excelentes candidatos para una evaluación.<ul><li>[Preparar la red de la organización para Microsoft Teams](prepare-network.md)</li></ul>|
| **Calidad de servicio (QoS)**  | QoS es una herramienta comprobada para ayudar a priorizar los paquetes en una red congestionada para asegurarse de que llegan a su destino intactos y a tiempo. Considere la posibilidad de implementar QoS en toda la organización para maximizar la calidad de la experiencia de usuario en la que el ancho de banda está restringido. QoS le ayudará a resolver problemas normalmente asociados con altos niveles de pérdida de paquetes y, en menor medida, con la vibración y los tiempos de ida y vuelta.<ul><li>[Instrucciones de QoS de Teams](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | Wi-Fi puede tener un impacto significativo en la calidad de las llamadas. Wi-Fi las implementaciones no suelen tener en cuenta los requisitos de red para los servicios VoIP y suelen ser una fuente de mala calidad. Para obtener más información sobre cómo optimizar su Wi-Fi infraestructura, vea este artículo sobre [Wi-Fi planificación.](/skypeforbusiness/certification/plan-wifi)<br><br>**Controlador inalámbrico:** Asegúrese de que los controladores inalámbricos estén actualizados. Esto ayudará a mitigar cualquier mala experiencia de usuario relacionada con un controlador obsoleto. Muchas organizaciones no incluyen controladores inalámbricos en sus ciclos de revisión y estos controladores pueden desajustar durante años. Muchos problemas inalámbricos se resuelven asegurándose de que los controladores inalámbricos estén actualizados.<br><br>**WMM:** Las extensiones multimedia inalámbricas (WMM), también conocidas como Wi-Fi Multimedia, proporcionan características básicas de QoS a las redes inalámbricas. Las redes inalámbricas modernas deben admitir muchos dispositivos. Estos dispositivos compiten por el ancho de banda y pueden provocar problemas de calidad para los servicios VoIP, donde la velocidad y la latencia son vitales. Consulte a su proveedor de servicios inalámbricos para obtener información específica y considere la posibilidad de implementar WMM en su red inalámbrica para priorizar los medios de Skype Empresarial y Teams.<br><br>**Densidad de puntos de** acceso: los puntos de acceso pueden estar demasiado separados o no en una ubicación ideal. Para minimizar posibles interferencias, coloque puntos de acceso adicionales en salas de conferencias y en ubicaciones que no estén obstruidas por paredes u otros objetos en los que la señal Wi-Fi es débil.<br><br>**2,4 GHz frente a 5 GHz:** 5 GHz proporciona menos interferencias de fondo y velocidades más altas, y se debe priorizar al implementar VoIP a través de Wi-Fi. Sin embargo, 5 GHz no es tan fuerte como 2,4 GHz y no penetra paredes tan fácilmente. Revise el diseño del edificio para determinar en qué frecuencia puede confiar para obtener la mejor conexión. |
|**Dispositivo de red** | Las organizaciones más grandes pueden tener cientos de dispositivos repartidos por toda la red. Trabaje con su equipo de red para asegurarse de que los dispositivos de red desde el usuario a Internet se mantienen y están actualizados. |
| **VPN**  | Los dispositivos VPN no están diseñados tradicionalmente para administrar cargas de trabajo multimedia en tiempo real. Algunas configuraciones de VPN prohíben el uso de UDP (que es el protocolo preferido para los medios) y solo se basan en TCP. Considere la posibilidad de implementar una solución de túnel dividido de VPN para ayudar a reducir la VPN como fuente de mala calidad. |
| **Clientes** <br>(Solo Skype Empresarial Online) | Asegúrese de que todos los clientes se actualizan periódicamente. |
| **Dispositivos** | Si los dispositivos son el culpable de los problemas de calidad de las llamadas, considere la posibilidad de actualizar los dispositivos infractores. Lea [Teléfonos para Teams](./devices/phones-for-teams.md) para obtener más información. |
| **Controladores** | La red de revisiones (Ethernet y Wi-Fi), los controladores de audio, vídeo y USB deben formar parte de su estrategia general de administración de revisiones. Muchos problemas de calidad se resuelven actualizando controladores. |
| **Salas de reuniones en Wi-Fi** | Recomendamos encarecidamente que los dispositivos de la sala de reuniones estén conectados a la red mediante al menos una conexión Ethernet de 1 Gbps. Los dispositivos de salas de reuniones suelen incluir varias transmisiones de audio y vídeo, junto con el contenido de la reunión, como el uso compartido de pantalla, y tienen requisitos de red más altos que otros puntos de conexión de Teams o Skype Empresarial. Las salas de reuniones son, por definición, dispositivos estacionarias donde Wi-Fi ofrece una ventaja solo durante la instalación.<br><br>Las salas de reuniones deben tratarse con especial cuidado y atención para asegurarse de que la experiencia de uso de estos dispositivos es de reunión o supera las expectativas. Por lo general, los problemas de calidad con las salas de reuniones se van a incrementar rápidamente, ya que suelen ser usados por el personal de nivel superior.<br><br>Con todas las cosas iguales (aparte de la comodidad), Wi-Fi rendimiento suele ser menor que una conexión por cable. Con el auge de las directivas de "traer su propio dispositivo" y la proliferación de portátiles, los puntos de acceso Wi-Fi a menudo se sobreutilizó. Es posible que los medios en tiempo real no se prioricen en Wi-Fi redes, lo que puede provocar problemas de calidad durante las horas de uso máximo. Este uso pesado puede coincidir con una reunión en la que puede haber una decena de personas presentes, cada una con su propio portátil y smartphone, todas conectadas al mismo punto de acceso Wi-Fi que el dispositivo de la sala de reuniones.<br><br>Wi-Fi debe considerarse solo como una solución temporal, para una instalación móvil o cuando Wi-Fi se haya aprovisionado correctamente para admitir medios basados en tiempo real y de clase empresarial. |


### <a name="tcp"></a>TCP 

El protocolo de control de transmisión (TCP) se considera un transporte con conmutación por recuperación y no el transporte principal que desea para medios en tiempo real. La razón por la que se trata de un transporte con conmutación por recuperación se debe a la naturaleza con estado de TCP. Por ejemplo, si una llamada se realiza en una red latente y los paquetes multimedia se retrasan, los paquetes de hace unos segundos ,que ya no son útiles, compiten por el ancho de banda para llegar al receptor, lo que puede empeorar una mala situación. Esto hace que el sanador de audio sume y estire el audio, lo que produce artefactos audibles, a menudo en forma de vibración.

Los informes de esta sección no distinguen entre transmisiones buenas y malas. Dado que udp es preferible, los informes buscan el uso de TCP para el uso compartido de pantalla basado en audio, vídeo y vídeo (VBSS). Se proporcionan tasas de transmisión deficientes para ayudar a comparar la calidad UDP con la calidad TCP para que pueda centrar sus esfuerzos donde el impacto sea mayor. El uso de TCP se debe principalmente a reglas de firewall incompletas. Para obtener más información sobre las reglas de firewall para Teams y Skype Empresarial Online, vea Direcciones URL e intervalos de direcciones IP de [Microsoft 365 y Office 365.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

> [!Note]
> Audio, vídeo y VBSS prefieren UDP como su transporte principal. La carga de trabajo de uso compartido de aplicaciones RDP heredada solo usa TCP.

#### <a name="tcp-usage"></a>Uso de TCP

Los informes TCP indican el uso total de TCP en los últimos siete meses. Todos los informes lejos de esta sección se centrarán en restringir edificios y subredes específicos en los que se usa con mayor frecuencia TCP. Hay informes independientes disponibles para conferencias y transmisiones de dos partes.

![Gráfico que muestra el porcentaje de transmisiones de audio que usan TCP](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Investigación

Con este informe, puede responder a las siguientes preguntas:

-   ¿Cuál es el volumen total de transmisiones TCP del mes actual?
-   ¿Es peor o mejor que el mes anterior?
-   ¿La tendencia de uso tcp está aumentando, estable o disminuyendo?
-   ¿El TCP PSR es el mismo que mi PSR general?

Si observa que la tendencia de uso de TCP está aumentando o por encima del uso mensual normal, tómese el tiempo necesario para investigar usando los sub-informes para buscar cualquier edificio o red que pueda necesitar corrección. Lo ideal es que desee el menor número de sesiones de audio basadas en TCP posible en la red administrada.

#### <a name="tcp-vs-udp"></a>TCP vs. UDP

Este informe identifica el volumen de informes de uso TCP frente a UDP del último mes para el uso compartido de pantalla basado en audio, vídeo y vídeo (VBSS). 

![Informe que muestra el volumen de transmisiones que usan TCP frente a UDP](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Análisis

Aunque desea que el uso de TCP sea lo más bajo posible, es posible que vea un poco de uso de TCP en una implementación en buen estado. TCP por sí mismo no contribuye a una llamada deficiente, por lo que se proporcionan tarifas de transmisión para ayudar a identificar si el uso de TCP contribuye a la mala calidad. 

#### <a name="tcp-investigations"></a>Investigaciones tcp

En las plantillas CQD proporcionadas, vaya a los informes Transmisiones TCP por creación y subred mediante la plantilla Redes administradas o Todas las redes. Con el fin de investigar el uso de TCP, el proceso es el mismo, por lo que centraremos la discusión aquí en conferencias.


##### <a name="remediation"></a>Corrección

Este informe identifica edificios y subredes específicos que contribuyen al volumen de uso de TCP. También se incluye un informe adicional para identificar la IP de Retransmisión de Microsoft que se usó en la llamada para ayudar a aislar las reglas de firewall que faltan. Centre sus esfuerzos de corrección en aquellos edificios que tienen el mayor volumen de transmisiones TCP para maximizar el impacto.

La causa más común de uso de TCP es que faltan reglas de excepción en firewalls o servidores proxy. Hablaremos de servidores proxy en la siguiente sección, por lo que por ahora centra tus esfuerzos en los firewalls. Al usar la creación o subred proporcionada, puede determinar qué firewall debe actualizarse.

| Corrección        | Instrucciones     |
|--------------------|--------------------------------------|
| Configurar firewall | Compruebe que los puertos y direcciones [IP de Microsoft 365 u Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) están excluidos del firewall. Para los problemas tcp relacionados con los medios, centre sus esfuerzos iniciales en lo siguiente:<ul><li>Compruebe que las subredes multimedia del cliente 13.107.64.0/18 y 52.112.0.0/14 están en las reglas de firewall.</li><li>Los puertos UDP 3478-3481 son los puertos multimedia necesarios y deben abrirse, de lo contrario, el cliente no podrá volver al puerto TCP 443.</li></ul> |
| Comprobar             | Use la [Herramienta de](https://www.microsoft.com/download/details.aspx?id=53885) evaluación de red de Microsoft para comprobar si hay problemas con la conectividad a direcciones IP y puertos específicos de Microsoft 365 u Office 365 desde el edificio o subred afectado.    |

### <a name="http-proxy"></a>Proxy HTTP

Los servidores proxy HTTP no son la ruta preferida para establecer sesiones multimedia, por una gran variedad de razones. Muchos contienen características de inspección profunda de paquetes que pueden impedir que se completen las conexiones al servicio e introducir interrupciones. Además, casi todos los servidores proxy fuerzan TCP en lugar de permitir UDP, que se recomienda para una calidad de audio óptima.

Siempre le recomendamos que configure el cliente para que se conecte directamente a Teams y a los servicios de Skype Empresarial. Esto es especialmente importante para el tráfico basado en medios.


> [!IMPORTANT]
> Le recomendamos que cargue un [archivo de creación](CQD-upload-tenant-building-data.md) válido para que pueda distinguir dentro de las transmisiones de audio externas al analizar el uso de proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

El informe de secuencias de proxy HTTP en esta sección de la plantilla es muy parecido a los informes TCP. No mira si las llamadas son malas o buenas, pero si la llamada está conectada a través de HTTP.

![Captura de pantalla del informe de transmisiones de audio que usan HTTP](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Análisis

Desea ver el menor número de transmisiones multimedia HTTP posibles. Si tiene transmisiones que atraviesan el proxy, consulte a su equipo de red para asegurarse de que se han puesto en marcha las exclusiones adecuadas para que los clientes estén enrutando directamente a subredes multimedia de Teams o Skype Empresarial Online.

Si solo tiene un proxy de Internet en su organización, compruebe las exclusiones de direcciones IP y URL de [Microsoft 365 u Office 365 adecuadas.](/microsoft-365/enterprise/urls-and-ip-address-ranges) Si hay más de un proxy de Internet configurado en su organización, use el sub-informe HTTP para aislar qué edificio o subred se ve afectado.

Para las organizaciones que no pueden omitir el proxy, asegúrese de que el cliente de Skype Empresarial está configurado para iniciar sesión correctamente cuando se encuentra detrás de un proxy, como se describe en el artículo Skype Empresarial debe usar el servidor proxy para iniciar sesión en lugar de intentar la conexión [directa.](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin) 


#### <a name="http-proxy-investigations"></a>Investigaciones de proxy HTTP

Este informe identifica edificios y subredes específicos que contribuyen al uso de HTTP.


##### <a name="remediation"></a>Corrección

Se [recomienda omitir](proxy-servers-for-skype-for-business-online.md) siempre los servidores proxy para Skype Empresarial y Teams, especialmente el tráfico multimedia. Los servidores proxy no hacen que Skype Empresarial sea más seguro, ya que su tráfico ya está cifrado. Los problemas relacionados con el rendimiento se pueden introducir en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos darán como resultado una experiencia negativa con el uso compartido de audio, vídeo y pantalla, donde las transmisiones en tiempo real son esenciales.

La causa más común de uso de HTTP es que faltan reglas de excepción en servidores proxy. Al usar la creación o subred proporcionada, puede determinar rápidamente qué proxy debe configurarse para la omisión de medios.

Compruebe que los [FQDN de Microsoft 365 u Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) necesarios se agregan a una lista de permitidos en el proxy.

## <a name="endpoint-investigations"></a>Investigaciones de punto de conexión

Esta sección se centra en las tareas para informar sobre versiones de cliente y el uso de dispositivos certificados. Los informes están disponibles para describir el uso de versiones de cliente, tipo de cliente, dispositivos de captura y controladores (micrófono), dispositivos de captura de vídeo y versiones Wi-Fi proveedor y controlador.

> [!NOTE]
> No todos los informes incluidos en las plantillas se tratan en este artículo; sin embargo, los métodos de investigación que se explican a continuación siguen siendo aplicables. Consulte la descripción del informe individual para obtener más información.

### <a name="client-versions"></a>Versiones de cliente

Estos informes se centran en identificar las versiones de cliente de Skype Empresarial en uso y su volumen relativo en el entorno.

> [!IMPORTANT]
> Actualmente, los clientes de Teams se distribuyen y actualizan automáticamente a través de la Red de entrega de contenido de Azure y el servicio lo mantendrá actualizado. Como resultado, no es necesario supervisar las versiones de cliente de Teams (a menos que desactive la actualización automática, que no se recomienda).

A menos que excluya los datos de los participantes federados, estos informes incluirán telemetría de cliente de puntos de conexión federados. Para excluir puntos de conexión federados, debe agregar un filtro de consulta para el id. de inquilino segundo establecido al id. de [inquilino de su organización.](CQD-data-and-reports.md#how-to-find-your-tenant-id) Como alternativa, puede usar un filtro [de dirección URL](CQD-data-and-reports.md#url-filters) para excluir la telemetría de participantes federados.



#### <a name="remediation"></a>Corrección

Una parte crítica de impulsar experiencias de usuario de alta calidad es garantizar que los clientes administrados estén ejecutando versiones actualizadas de Skype Empresarial, además de garantizar que los controladores de audio, vídeo, red y USB compatibles estén actualizados. Esto proporciona varias ventajas, entre ellas: 

-   Es más fácil administrar unas pocas versiones frente a muchas versiones.
-   Proporciona un nivel de coherencia de experiencia.
-   Facilita la solución de problemas con la calidad de las llamadas y la facilidad de uso.
-   Microsoft realiza continuamente mejoras generales y optimizaciones en todo el producto. Asegurarse de que los usuarios reciban estas actualizaciones reduce el riesgo de que se ejecute un problema que ya se ha resuelto.

Limitar la implementación a versiones cliente que tienen menos de seis meses de antigüedad mejorará la experiencia general del usuario y mejorará la capacidad de administración reduciendo el número de versiones que deben ser compatibles.

Si usa solo Hacer clic y ejecutar de Office, estará automáticamente dentro de la ventana de seis meses. No es necesario realizar ninguna acción adicional.

Si tiene una combinación de paquetes de hacer clic y ejecutar e instalador (MSI), puede usar el informe para comprobar que los clientes MSI se actualizan periódicamente. Si observa que los clientes se están quedando atrás, trabaje con el equipo responsable de administrar las actualizaciones de Office y asegúrese de que aprueban e implementan revisiones de cliente periódicamente.

También es importante tener en cuenta y asegurarse de que la red, el vídeo, el USB y los controladores de audio también están siendo parcheados. Puede ser fácil pasar por alto estos controladores y no incluirlos en la estrategia de administración de revisiones.

Los números de versión de Skype Empresarial se pueden encontrar a través de los siguientes vínculos:

-   [Información de publicación de actualizaciones de aplicaciones de Microsoft 365](/officeupdates/release-notes-office365-proplus)
-   [Historial de actualizaciones de aplicaciones de Microsoft 365 para empresas](/officeupdates/update-history-office365-proplus-by-date)
-   [Descargas y actualizaciones de Skype Empresarial](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivos

Para usar el informe del dispositivo del micrófono, necesitamos comprender el concepto de la puntuación media de opinión (MOS). MOS es la medida estándar de oro para medir la calidad de audio percibida. Se representa como una clasificación de enteros de 0 a 5.

La base de todas las medidas de calidad de voz es cómo una persona percibe la calidad del habla. Como se ve afectada por la percepción humana, es intrínsecamente subjetiva. Existen varias metodologías diferentes para las pruebas subjetivas. La mayoría de las medidas de calidad de voz se basan en una escala de clasificación de categorización absoluta (ACR).

En una prueba subjetiva de ACR, un número estadísticamente significativo de personas califica su calidad de experiencia en una escala de 1 (mala) a 5 (excelente). El promedio de las puntuaciones es el MOS. El MOS resultante depende del rango de experiencias que se han expuesto al grupo y del tipo de experiencia que se va a evaluar.

Como no es práctico realizar pruebas subjetivas de calidad de voz para un sistema de comunicación en directo, Microsoft Teams y Skype Empresarial generan valores MOS mediante algoritmos avanzados para predecir objetivamente los resultados de una prueba subjetiva.

El conjunto disponible de MOS y las métricas asociadas proporcionan una vista de la calidad de la experiencia que un dispositivo de audio entrega a los usuarios. 

Al proporcionar a los usuarios dispositivos certificados para Teams y Skype Empresarial, se reduce la probabilidad de que se produzcan experiencias negativas debido al propio dispositivo (que es más probable, por ejemplo, con altavoces y micrófonos integrados para portátiles). Para obtener más información, vea estos artículos sobre el programa [de certificación y](/SkypeForBusiness/certification/overview) el catálogo de soluciones de [partners.](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

Los informes de dispositivo se usan para evaluar el uso del dispositivo por volumen y la puntuación de MOS (solo audio), y se pueden encontrar en las plantillas que acompañan en Clientes & Dispositivos. 

> [!IMPORTANT]
> A menos que excluya los datos de los participantes federados, estos informes incluirán telemetría de cliente de puntos de conexión federados. Para excluir puntos de conexión federados, debe agregar un filtro de consulta para el **id.** de inquilino segundo establecido al id. de [inquilino de su organización.](CQD-data-and-reports.md#how-to-find-your-tenant-id) De forma provisional, puede usar un filtro [de dirección URL](CQD-data-and-reports.md#url-filters) para excluir la telemetría de participantes federados.


> [!Note]
> Es posible que observe al ver este informe que ve el mismo dispositivo notificado varias veces. Esto se debe a la forma en que se notifica que el dispositivo se notifica a CQD. Las diferencias en el hardware y la configuración regional del sistema operativo provocan diferencias en la forma en que se notifican los datos del dispositivo.

##### <a name="remediation"></a>Corrección

Por lo general, deberá descubrir y eliminación gradual de dispositivos no certificados y reemplazarlos por dispositivos certificados. Algunas consideraciones al revisar los informes del dispositivo son:

-   ¿Están certificados los dispositivos en uso para Teams y Skype Empresarial? 
-   Puede identificar usuarios de un dispositivo específico mediante el análisis de llamadas por [usuario.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Compruebe que tienen los controladores de dispositivo más recientes y que su dispositivo no está conectado a través de un concentrador USB o una estación de acoplamiento. 
-   ¿Cuántas versiones diferentes de varios controladores están en uso? ¿Se están revisando periódicamente? Garantizar que los controladores de audio, vídeo y Wi-Fi se revisan periódicamente ayudará a eliminar estos controladores como fuente de problemas de calidad y a hacer que la experiencia del usuario sea más predecible y coherente.

##### <a name="audio"></a>Audio

La siguiente tarea es determinar el uso general de [dispositivos de audio certificados.](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) Se recomienda que al menos el 80 por ciento de todas las transmisiones de audio usen un dispositivo de audio certificado. Esto se logra mejor exportando el informe de dispositivos de micrófono a Excel para calcular el uso de dispositivos certificados o aprobados. Las organizaciones suelen mantener una lista de todos los dispositivos aprobados, por lo que filtrar y ordenar los datos debe ser sencillo.

##### <a name="video"></a>Vídeo

Los controladores de vídeo también son importantes para mantenerse actualizados. Asegurarse de que las tarjetas de vídeo se revisan periódicamente ayudará a excluir los controladores de vídeo como fuente de mala calidad para las transmisiones de vídeo. El [uso de dispositivos de](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) vídeo certificados ayudará a garantizar una experiencia de usuario fluida y de alta calidad. Se prefieren los dispositivos de vídeo compatibles con la codificación nativa H.264 para reducir el uso de LA CPU durante las videoconferencias.

##### <a name="wi-fi"></a>Wi-Fi

Wi-Fi los controladores de revisión también deben estar parcheados en una cadencia regular y deben incluirse en la estrategia de administración de revisiones. Se pueden corregir muchos problemas de calidad manteniendo los controladores de Wi-Fi actualizados. Para obtener más información sobre cómo optimizar su Wi-Fi infraestructura, vea este artículo sobre [Wi-Fi planificación.](/skypeforbusiness/certification/networking-wifi)


## <a name="related-topics"></a>Temas relacionados

[Usar asesor para Teams](use-advisor-teams-roll-out.md)

[Preparar la red para Teams](prepare-network.md)

[Principios de conectividad de red de Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Análisis e informes de Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Administrar los dispositivos en Teams](./devices/device-management.md)

[Mejorar y supervisar la calidad de las llamadas de Teams](monitor-call-quality-qos.md)

[¿Qué es CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar datos de inquilino y creación](CQD-upload-tenant-building-data.md)

[Datos e informes de CQD](CQD-data-and-reports.md)

[Dimensiones y medidas disponibles en CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de secuencias en CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos CQD](CQD-Power-BI-query-templates.md)
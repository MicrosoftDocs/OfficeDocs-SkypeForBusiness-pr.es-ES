---
title: Usar el CQD para administrar la calidad de las llamadas y reuniones en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Aprenda a analizar y administrar el rendimiento de los medios en tiempo real en Microsoft Teams mediante el panel de calidad de llamadas (CQD).
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

Este artículo le ayudará a la administración de Teams o al ingeniero de soporte técnico y del Departamento de soporte técnico para desarrollar un proceso de supervisión y mantenimiento de la calidad de las llamadas y reuniones de su organización mediante el panel de calidad de llamadas de Microsoft Teams (CQD). Nuestra orientación enfatiza escenarios de calidad de audio porque cualquier mejora en la red que realices para mejorar la experiencia de audio se traducirá en mejoras en el video y el uso compartido.

La clave de esta guía son las dos [plantillas del CQD de protegida](https://aka.ms/QERtemplates) : le recomendamos que las Descargue antes de seguir las instrucciones de este artículo.

En este artículo se presupone que ya ha [configurado el CQD](turning-on-and-using-call-quality-dashboard.md).


## <a name="categories-to-monitor-and-maintain"></a>Categorías para supervisar y mantener

Una vez que haya implementado las reuniones y la voz en Teams, necesitará un plan de supervisión y mantenimiento continuos. De este modo, se asegurará de que Teams siempre se esté ejecutando de manera óptima. Este plan debe incluir las áreas clave que se indican a continuación. También debe establecer objetivos para las métricas de calidad y un plan de solución de problemas y aislamiento de problemas cuando se produzcan.

<table>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Calidad de las llamadas</strong></td>
<td>
<p>Desglosar las métricas por llamadas internas (dentro de tu organización, como VPN, WiFi, con cable) o llamadas externas</p>
<p>Dividir las métricas por edificio o red</p>
<p>Llamadas de VPN</p>
<p>Llamadas con TCP, UDP o proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Confiabilidad de las llamadas</strong></td>
<td><p>Identificar y corregir cualquier problema de red o firewall</p>
<p>Obtener información sobre los porcentajes de errores de configuración y colocación de llamadas</p>
<p>Aprenda dónde se produce la mayoría de los errores de configuración y colocación de la llamada</p>
</td>
</tr>
<tr class="odd">
<td><strong>Encuesta de usuario</strong></td>
<td>
<p>Usar la clasificación de mis datos de llamadas para obtener información sobre la experiencia real de los usuarios</p>
<p>¿Dónde están las experiencias deficientes?</p>
<p>Correlaciona la mala experiencia con la calidad de las llamadas, la fiabilidad y los dispositivos</p>
</td>
</tr>
<tr class="even">
<td><strong>Dispositivos</strong></td>
<td><p>Aprender qué micrófonos y altavoces se usan con mayor frecuencia y su impacto en la calidad de las llamadas</p>
<p>¿Se revisan regularmente los drivers de audio, vídeo, USB e WiFi?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clientes</strong></td>
<td>
<p>Obtenga información sobre qué tipos de clientes y versiones se usan y su impacto en la calidad y la confiabilidad de las llamadas.  </p>
</ol></td>
</tr>
</tbody>
</table>

Al evaluar y corregir continuamente las áreas descritas en este artículo, puede reducir su potencial de afectar negativamente a sus usuarios. La mayoría de los problemas de los usuarios se pueden agrupar en las siguientes categorías:

-   Una configuración de proxy o firewall incompleta
-   Una cobertura Wi-Fi insuficiente
-   Un ancho de banda insuficiente
-   VPN
-   Versiones y drivers de cliente incoherentes o anticuados
-   Dispositivos de audio integrados o no optimizados
-   Dispositivos de red o subred problemáticos

A través de una planificación y un diseño adecuados antes de implementar Teams o Skype empresarial online, puede reducir la cantidad de esfuerzo que se necesitará para mantener experiencias de alta calidad.

Este artículo se centra en el uso del panel de calidad de llamadas (CQD) en línea como la herramienta principal para denunciar e investigar cada área, con un énfasis especial en el audio para maximizar la adopción y el impacto. Cualquier mejora hecha en la red para mejorar la experiencia de audio también se traducirá directamente a mejoras en el uso compartido de vídeo y escritorio.

Para acelerar su evaluación, se proporcionan [dos plantillas de CQD de protegida](https://aka.ms/qertemplates) : una es para administrar todas las redes y la otra se filtra solo para las redes administradas (internas). Aunque los informes de plantillas All Networks están configurados para mostrar la información de compilación y de red, aún se pueden usar mientras trabaja para recopilar y cargar información de compilación. Cargar información de compilación en CQD permite al servicio mejorar los informes agregando la creación, la red y la información de ubicación personalizados mientras se diferencian entre las subredes externas. Para obtener más información, lea [asignación de creación](CQD-building-mapping.md).

### <a name="intended-audience"></a>Audiencia prevista

Este artículo está pensado para que lo utilicen las partes interesadas de los socios y clientes con roles como liderazgo/arquitecto de colaboración, consultor, especialista en administración/adopción de cambios, responsable de soporte/asistencia, cable de red, responsable de escritorio y administrador de ti.

Este artículo está destinado a ser usado por el preparador de calidad designado (s). Para obtener más información, consulte [el rol de calidad de experto](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>¿Qué es la calidad?

En este contexto, la calidad es una combinación de las métricas de servicio y la experiencia del usuario.


### <a name="service-metrics"></a>Métricas de servicio

Las métricas de servicio se componen de métricas específicas basadas en el cliente. Durante cada llamada, el cliente recopila la telemetría de la llamada y envía un informe al final de cada llamada al que se puede acceder más adelante en el CQD o en el [análisis de llamadas por usuario](set-up-call-analytics.md). Estas métricas incluyen (pero no se limitan a):

-   Flujo deficiente (entrante y saliente)
-   Tasa de error de configuración
-   Tasa de errores de caída


#### <a name="poor-stream-rate"></a>Mala velocidad de transmisión

La mala tarifa de transmisión por secuencias (PSR) representa el porcentaje general de las transmisiones de baja calidad de la organización. Este sistema métrico resalta las áreas en las que su organización puede concentrar el esfuerzo para tener el mayor impacto en la reducción de este valor y en la mejora de la experiencia del usuario, razón por la cual las [redes administradas](#managed-versus-unmanaged-networks) son el principal enfoque al mirar a PSR. Los usuarios externos también son importantes, pero la investigación difiere en cada organización. Considere la posibilidad de proporcionar procedimientos recomendados para usuarios externos e investigue las llamadas externas independientemente de la organización general.

La medición real en el CQD varía según la carga de trabajo, pero a los fines de este artículo, nos centramos principalmente en la medición de _porcentaje deficiente de audio_ . PSR consta de los cinco promedio métricos de red que se describen en la tabla siguiente. Para que una secuencia se clasifique como mala, solo una métrica debe superar el umbral definido. El CQD proporciona el "mala debido a..." medidas para comprender mejor qué condición causó que la secuencia se clasifique como mala. Para obtener más información, lea [clasificación de la secuencia en el CQD](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> El CQD proporciona el "mala debido a..." medidas para comprender mejor qué condición causó que la secuencia se clasifique como mala.


##### <a name="audio-poor-quality-metrics"></a>Métricas de baja calidad de audio

| Promedio de la métrica     | Descripción     | Experiencia de usuario |
|-------------|-----------------|-----------------|
| Vibración \> 30 ms        | Este es el cambio medio en el retraso entre paquetes sucesivos. Los equipos y Skype empresarial pueden adaptarse a algunos niveles de vibración a través del almacenamiento en búfer. Solo cuando la vibración supera el búfer que un participante advierte de los efectos de la vibración.      | Los paquetes que llegan a velocidades diferentes hacen que la voz del orador suene robótica.   |
| Porcentaje de pérdida \> de paquetes 10% o 0,1        | Esto se suele definir como un porcentaje de paquetes que se pierden. La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individuales que apenas tienen impacto en las pérdidas de ráfagas en el fondo que hacen que el audio se recorte por completo.     | Los paquetes que se descartan y que no llegan a su destino, causan lagunas en los medios, lo que da lugar a sílabas y palabras perdidas, así como vídeo y uso compartido entrecortado. |
| Tiempo de ida y vuelta \> 500 ms        | Este es el tiempo que se tarda en obtener un paquete IP desde el punto a al punto B y volver al punto a. Este retraso de propagación de red está vinculado a la distancia física entre los dos puntos y la velocidad de luz, e incluye una sobrecarga adicional realizada por los distintos dispositivos en la ruta de acceso a la red.      | Los paquetes que tardan demasiado tiempo en llegar a su destino causan un efecto de walkie-talkie.   |
| Degradación de NMOS promedio \> 1,0         | Degradación media de [opinión de media de red (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) de la transmisión. Representa el grado en que la pérdida y la vibración de la red han afectado a la calidad del audio recibido que causó que el método NMOS se colocara en más de un punto. | Esta es una combinación de vibración, pérdida de paquetes y, a menor grado, aumentos en el tiempo de ida y vuelta. Es posible que el usuario esté experimentando una combinación de estos síntomas.   |
| Relación media entre el \> 7% o 0,07 de las muestras ocultas | Relación media entre el número de marcos de audio con muestras ocultas generada por la recuperación de pérdida de paquetes para el número total de marcos de audio. Una muestra de audio oculta es una técnica usada para suavizar la transición abrupta, que normalmente se producía por paquetes de red perdidos.      | Los valores altos indican que se aplicaron niveles significativos de ocultación de pérdida y dieron como resultado una distorsión o pérdida de audio.     |

##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>¿Por qué preferimos usar secuencias en lugar de llamadas?

Las transmisiones nos informan sobre qué pierna determinada de la llamada fue de mala salida o entrante. Si está buscando una mala llamada en el análisis de llamadas, determine si la llamada deficiente se debió a la transmisión por secuencias de la persona que llama (salida) o a la transmisión de la llamada (entrante). Determinar qué transmisión afecta la calidad de las llamadas es aún más importante para las conferencias. Si solo está viendo los datos de la llamada, verá cuántas conferencias en las que participa una persona, pero no verá qué personas son oradores activos, lo que hace la mayor parte de la pantalla.

Los datos de la llamada le proporcionan métricas de uso, pero no necesariamente le conducen a la causa principal de la mala calidad de las llamadas. Al mirar la dirección de la transmisión, puede identificar factores como una llamada que no está en una red administrada, una llamada de un no empleado (por ejemplo, un proveedor o un usuario de otra red). En estos casos, si la conexión de red de la otra persona era deficiente, toda la llamada se marcará como mala. No puede hacer nada sobre factores externos, por lo que estos datos no son útiles.

La dirección de la transmisión también puede ayudarle a identificar dispositivos o clientes problemáticos.

 - Por ejemplo, si tiene un presupuesto limitado para dispositivos y desea proporcionar dispositivos solo para usuarios de audio de alta densidad, use el informe de uso de audio (VoIP) y filtre los flujos de salida y las conferencias. Busque usuarios de audio de gran volumen que estén hablando por micrófonos integrados, ya que pueden correlacionar con la calidad de las llamadas más deficientes (y es posible que desee proporcionar dispositivos de audio para estas personas). Para una mayor claridad, puedes filtrar el uso de paquetes, que te permitirá dirigirte especialmente a usuarios de audio de gran volumen. 

  - Otro ejemplo implica la pantalla compartida. Si un cliente está usando un cliente de equipos antiguo, la pantalla de uso compartido puede verse afectada. Puede solucionar este problema si prioriza las actualizaciones de los clientes que tienen una gran cantidad de pantalla compartida.

 - Al identificar la dirección de una transmisión que está causando una mala calidad de la llamada, puede determinar si tiene un problema de QoS o de ancho de banda. Si no ha implementado totalmente QoS, o si solo marca paquetes en el cliente y no en el flujo entrante, es posible que vea calidad de llamada deficiente. Al mirar la dirección de la transmisión, puede obtener una vista más detallada de la pérdida de paquetes, latencia o vibración en una dirección específica. 

   - Por ejemplo, supongamos que un usuario se queja del audio robótico mientras está en una conexión cableada (vibración). Al mirar la secuencia y la dirección, puede determinar que el problema se produce en la transmisión entrante, solo para un conjunto específico de subredes. Después de proporcionar esta información a su equipo de redes, pueden realizar un seguimiento de un acelerador de WAN mal configurado que no pasa por alto el tráfico de medios. Una vez que el equipo de red vuelve a configurar el acelerador de WAN, desaparece la vibración y mejora la calidad de las llamadas. 


#### <a name="setup-failure-rate"></a>Tasa de error de configuración

La tasa de error de configuración, que también se conoce como la medición del _porcentaje total de errores de configuración de llamadas_ en el CQD, es el número de transmisiones en las que no se pudo establecer la ruta de acceso a medios entre los puntos de conexión al inicio de la llamada.

Esto representa cualquier flujo de medios que no se pudo establecer. Dada la gravedad del impacto de este problema en la experiencia del usuario, el objetivo es reducir este valor a cero como sea posible. Un valor elevado para esta métrica es más común en nuevas implementaciones con reglas de Firewall incompletas que una implementación madura, pero sigue siendo importante vigilar de forma periódica.

Esta métrica se calcula al tomar el número total de transmisiones que no se pudieron configurar divididas por el número total de transmisiones que enviaron un registro de detalles de la llamada (CDR) correctamente:

-   **Tasa de errores de configuración** = error en la configuración de la llamada total de streams, número total de streams disponibles de CDR

#### <a name="drop-failure-rate"></a>Tasa de errores de caída

La tasa de error de caída, que también se conoce como la medida de _porcentaje total de llamadas perdidas_ en el CQD, es el porcentaje de transmisiones correctamente que la ruta de acceso a los medios no finalizó con normalidad.

Esto representa cualquier flujo de medios que haya finalizado de forma inesperada. Aunque el impacto de esto no es tan grave como un flujo que no se ha podido configurar, sigue afectando negativamente a la experiencia del usuario. Los medios repentinos y repentinos no solo pueden tener un impacto grave en la experiencia del usuario, ya que hacen que los usuarios tengan que volver a conectarse, lo que provoca pérdida de productividad (sin mencionar la frustración).

La métrica se calcula aprovechando el número total de flujos colocados dividido por el recuento total de transmisiones que se han configurado correctamente:

-   **Tasa de errores de caída** = número total de flujos de llamadas interrumpidas/total de llamadas correctas

### <a name="define-your-target-metrics"></a>Definir las métricas de destino

En esta sección se describen algunas de las métricas de servicio básicas que usamos para evaluar el estado de los servicios. Al evaluar y promover los esfuerzos para mantener estas métricas a partir de los destinos definidos, te ayudará a garantizar que tus usuarios disfruten de una calidad de llamada coherente y fiable. Como punto de partida, use los destinos sugeridos en la tabla siguiente. Ajuste los objetivos según sea necesario para cumplir con los objetivos de la empresa.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo de red</th><th rowspan="1">Dianas de calidad</th><th colspan="2">Objetivos de confiabilidad</th></tr>
<tr><th>Velocidad de flujo de audio de mala calidad</th><th>Tasa de error de configuración</th><th>Tasa de errores de caída</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>General</td><td>3,0%</td><td>1,0%</td><td>3,0%</td></tr>
<tr><td rowspan="5"><strong>Conferencia</strong></td><td>Interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Cable interno</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Wi-Fi 5 GHz interno</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Wi-Fi 2,4 GHz interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>General</td><td>2,0%</td><td>0,5%</td><td>3,0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Interno por cable o Wi-Fi de 5 GHz</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>General por cable/Wi-Fi de 5 GHz</td><td>2,0%</td><td>1,0%</td><td>1,0%</td></tr>
<tr><td>General</td><td>2,0%</td><td>1,0%</td><td>3,0%</td></tr>
</table>

### <a name="user-experience"></a>Experiencia de usuario

Analizar la experiencia del usuario es más arte que la ciencia, ya que las métricas que se recopilan aquí no siempre significan que hay un problema con la red o el servicio, sino que simplemente indican que el usuario percibe un problema. El CQD incluye un mecanismo de encuesta integrado (califica mi llamada (RMC)) para ayudar a medir la experiencia general del usuario. RMC le dará una idea de las siguientes preguntas desde la perspectiva de sus usuarios:

-   ¿Sé cómo usar la solución?
-   ¿La solución es fácil de usar e intuitiva, y es compatible con mis necesidades de comunicación cotidianas?
-   ¿Me puede ayudar la solución a hacer mi trabajo?
-   ¿Cuál es la percepción general de la solución?
-   ¿Puedo usar la solución en cualquier momento, independientemente de dónde soy?
-   ¿Puedo configurar y mantener una llamada?

#### <a name="rate-my-call"></a>Calificar mi llamada 

Calificar mi llamada (RMC) está integrado en Teams y en Skype empresarial. Aparece automáticamente después de una llamada por cada 10 llamadas o un 10 por ciento. Esta breve encuesta le pide al usuario que clasifique la llamada y proporciona un poco de contexto por el que es posible que la calidad de la llamada sea deficiente. Una o dos calificaciones se consideran deficientes, tres a cuatro es buena y cinco es excelente. Aunque es algo de un indicador atrasado, esta es una métrica útil para descubrir problemas que las métricas de servicio pueden perder.

> [!Note]
> El factor humano: a menudo, los usuarios ignoran la encuesta cuando la calidad de la llamada es buena y la rellenan cuando la calidad de la llamada es mala. Como resultado, los informes de RMC podrían sesgarse en el lado deficiente, incluso mientras las métricas de servicio son buenas.

Puede usar el CQD para denunciar las respuestas de los usuarios de RMC y los informes de muestra se incluyen en la plantilla de CQD. Sin embargo, no se tratan en detalle en este artículo. 

#### <a name="client-and-device-readiness"></a>Preparación de dispositivos y clientes

Para ayudar a que los usuarios tengan una experiencia de usuario coherente y positiva, necesita una estrategia de cliente y dispositivo sólida. Algunos principios clave impulsan cada estrategia de preparación.

##### <a name="client-readiness"></a>Preparación del cliente

Mantener al cliente de los equipos actualizado garantiza que los usuarios siempre obtienen la mejor experiencia posible. Microsoft publica [actualizaciones frecuentes en el cliente de Teams](teams-client-update.md) (la actualización se instala en segundo plano, a menos que haya desactivado esta funcionalidad, lo cual no se recomienda). También es importante recordar la corrección de los drivers de red, vídeo, USB y audio, ya que a menudo se les suele pasar por alta y pueden afectar la calidad de la llamada y de la reunión. Considere la posibilidad de agregar controladores de red, Wi-Fi, vídeo, USB y audio a su proceso de administración de revisiones actual.


##### <a name="device-readiness"></a>Preparación del dispositivo

Una sola estrategia puede afectar a la experiencia del usuario más que la estrategia de preparación de dispositivos. Por ejemplo, los usuarios que dependen de sus altavoces y micrófono de equipos portátiles experimentarán un gran ruido de fondo en las llamadas y las reuniones. Teams está diseñado para funcionar con casi cualquier dispositivo, pero si tiene problemas relacionados con el dispositivo, consulte [teléfono para equipos](phones-for-teams.md).


### <a name="categories-of-quality"></a>Categorías de calidad

Cómo operar un conjunto de prácticas de administración de calidad: le da la mejor oportunidad de buena calidad en llamadas y reuniones. Un buen plan de administración de calidad se dirige A estas categorías:

-   **Red:** Calidad de audio centrada en la métrica de la proporción de flujo deficiente (PSR), el uso de TCP, las subredes con cable e inalámbricas y la identificación del uso de proxy HTTP y VPN

-   **Puntos de conexión:** Dispositivos de audio y clientes actualizados

-   **Administración de servicios:** Esta categoría comprende dos secciones:

    -   En primer lugar, es responsabilidad de Microsoft administrar y mantener los equipos y los servicios de Skype empresarial online.

    -   En segundo lugar, las tareas que la organización administra para garantizar un acceso confiable al servicio, como la actualización de la información de generación y el mantenimiento de firewalls para las nuevas direcciones IP de Office 365, a medida que se agrega una infraestructura al servicio.

![Gráfico de las categorías de calidad en una organización](media/qerguide-image-categories.png "Las categorías de calidad de una organización: administración de servicios, puntos de conexión y la red.")

Revise la siguiente lista de tareas recomendadas para mantener la calidad. Debe realizar estas tareas regularmente, por ejemplo, semanalmente.

#### <a name="service-management-tasks"></a>Tareas de administración de servicios

Estas tareas van desde asegurar que hay suficiente ancho de banda para alcanzar el servicio sin saturar los vínculos de Internet, validar que la calidad del servicio (QoS) esté en su lugar en todas las áreas de red administradas y mantener el nivel superior de los [intervalos de IP de Office 365 en los firewalls](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Tareas de red

Existen dos categorías de tareas de red: fiabilidad y calidad. La confiabilidad se centra en medir la capacidad del usuario para hacer llamadas correctamente y permanecer conectada. La calidad se centra en la telemetría agregada que se envía a teams y Skype empresarial online por el cliente del usuario durante la llamada y después de que haya finalizado. 

Dado el impacto crítico que tiene la confiabilidad en la experiencia del usuario, le recomendamos que evalúe e investigue las métricas de confiabilidad antes de que profundice en la calidad. 

#### <a name="endpoints-tasks"></a>Tareas de puntos finales

La tarea principal de esta categoría elimina cualquier obstáculo para [las actualizaciones de clientes normales de Teams](teams-client-update.md). De forma predeterminada, Teams actualiza de forma automática regularmente (a menos que desactives esa configuración, lo que no recomendamos). 

También debe supervisar los dispositivos y proporcionar actualizaciones siempre que identifique problemas relacionados con un dispositivo.

## <a name="use-cqd-to-manage-call-quality"></a>Usar CQD para administrar la calidad de las llamadas

Una vez que haya [configurado el CQD](turning-on-and-using-call-quality-dashboard.md), estará listo para empezar a usarlo para administrar la calidad de las llamadas y las reuniones de su organización.

La mayoría de los problemas con el rendimiento de Teams se dividen en las siguientes categorías:

-   Una configuración de proxy o firewall incompleta
-   Una cobertura Wi-Fi insuficiente
-   Un ancho de banda insuficiente
-   VPN
-   Versiones y drivers de cliente incoherentes o anticuados
-   Dispositivos de audio integrados o no optimizados
-   Dispositivos de red o subred problemáticos

Si se toma el tiempo antes de implementar Teams para evaluar estas áreas y corregir cualquier deficiencia, se reducirá la cantidad de esfuerzo necesario para mantener una experiencia de equipos de alta calidad para todos los usuarios. Para ayudarle a evaluar su red como preparación para el lanzamiento de su equipo, lea el [Asesor de equipos](use-advisor-teams-roll-out.md) y [Prepare su red para Teams](prepare-network.md).

### <a name="expectations-using-cqd"></a>Expectativas con el CQD

Use el panel de calidad de llamadas (CQD) para obtener información sobre la calidad de las llamadas realizadas mediante el uso de Teams y servicios de Skype empresarial. El CQD está diseñado para ayudar a equipos y administradores de Skype empresarial e ingenieros de red a optimizar la red y mantener un vistazo a la calidad, la confiabilidad y la experiencia del usuario. El CQD comprueba la telemetría de la totalidad de la organización, en la que se pueden aparentar patrones generales; Esto le permite realizar evaluaciones con conocimiento y planificar la corrección. El CQD proporciona informes de métricas que proporcionan una perspectiva de la calidad general, la confiabilidad y la experiencia del usuario.

El CQD, aunque es útil para analizar tendencias y subredes, no siempre proporciona una causa específica para un escenario determinado. Es importante comprender esto y establecer la expectativa correcta al usar el CQD:

-   El CQD no proporcionará la causa de origen para cada escenario
-   El CQD no contendrá secuencias de audio o de sistema telefónico
-   El CQD llamará a las áreas para una mayor investigación según las tendencias

### <a name="cqd-reports-overview"></a>Información general de los informes de CQD

Use el menú desplegable en la parte superior de la pantalla para abrir un informe. Para obtener una lista de los datos proporcionados en cada informe, lea los [datos disponibles en los informes de CQD](CQD-data-and-reports.md#data-available-in-cqd-reports).

Novedades de enero de 2020: [Descargue las plantillas de consulta de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Plantillas de Power BI personalizables que puede usar para analizar y notificar los datos de CQD.


### <a name="teams-vs-skype-for-business"></a>Teams frente a Skype empresarial

El CQD puede denunciar tanto a los equipos como a Skype empresarial. Sin embargo, puede haber ocasiones en las que desee desarrollar un informe para ver la telemetría de Teams independiente de Skype empresarial.

#### <a name="summary-reports"></a>Informes de Resumen

Para modificar la página informes de resumen para ver solo equipos o Skype empresarial, seleccione el menú desplegable **filtro de producto** en la parte superior de la pantalla y, a continuación, seleccione el producto que quiera.

![Captura de pantalla del menú desplegable que muestra las opciones de filtro](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Informes detallados

Para filtrar todos los informes detallados, en la barra del explorador, agregue lo siguiente al final de la dirección URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Ejemplo**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obtener más información sobre filtros URL, lea [informes de filtrado](CQD-data-and-reports.md#report-filters) más adelante en esta sección.

Para filtrar un informe detallado individual, agregue el filtro ``Is Teams`` al informe y establézcalo en verdadero o falso.

![Captura de pantalla de la página Agregar filtro](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Redes administradas y no administradas

De forma predeterminada, todos los puntos de conexión del CQD se clasifican como externos. Tan pronto como se introduce un archivo de compilación, podemos empezar a consultar los datos de los extremos administrados. Como se ha explicado anteriormente, las redes del CQD se definen como:

-   La organización puede influir y controlar una _red administrada_, que a menudo se denomina interna o interna. Esto incluye la LAN interna, la WAN remota y VPN.
-   La organización no puede influir ni controlar una _red no administrada_, que a menudo se denomina externa o externa. Un ejemplo de una red no administrada es una red de hoteles o aeropuertos.

### <a name="dimensions-measures-and-filters"></a>Dimensiones, medidas y filtros

Una consulta del CQD con formato correcto contiene los tres parámetros siguientes:

-   **Dimensión:** Cómo quiero dinamizar los datos.

-   **Medir:** Qué quiero denunciar.

-   **Filtrar:** Cómo quiero reducir el conjunto de resultados de la consulta.

Otra forma de ver esto es que una _dimensión_ es la función de agrupación, una _medida_ son los datos que me interesan y un _filtro_ es cómo quiero restringir los resultados a los que son relevantes para mi consulta.

Un ejemplo de una consulta bien formada es **Mostrar secuencias deficientes [medida] por subred [dimensión] para edificio 6 [filtro]**. Para obtener más información, consulte [dimensiones y medidas disponibles en el CQD](https://aka.ms/cqd-dm).

### <a name="first-vs-second"></a>Primer comparado con el segundo 

Muchas de las dimensiones y medidas del CQD se clasifican como primera o segunda. El CQD no usa los campos de llamador y destinatario: se les ha cambiado el nombre _primero_ y _segundo_ porque hay pasos que intervienen entre quien llama y quien llama. La siguiente lógica determina qué extremo implicado está etiquetado como en primer lugar:

-   En **primer lugar** siempre será un extremo del servidor (servidor de conferencia, servidor de media, etc.) si un servidor está implicado en la transmisión o la llamada.

-   El **segundo** siempre será un extremo de cliente, a menos que la secuencia se entre dos puntos de conexión de servidor.

-   Si ambos puntos de conexión son del mismo tipo, la elección de los cuales se calcula en primer lugar depende de la ordenación interna de la categoría de agente de usuario. De este modo se asegura que el orden es coherente.

Para obtener más información sobre cómo determinar el primer o el segundo punto de conexión cuando ambos son iguales, consulte [dimensiones y medidas disponibles en el CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Stream VS. Call

Debe comprender la diferencia entre una llamada y una secuencia para elegir correctamente las dimensiones o medidas que va a consultar en el CQD. Aunque el foco principal del CQD está en las transmisiones, también están disponibles las medidas basadas en llamadas.

-   **Flujo:** Existe una _secuencia_ entre dos puntos de conexión. Solo hay una secuencia para cada dirección, y se necesitan dos secuencias para la comunicación. Las secuencias son útiles para investigar edificios, redes o subredes. En algunos casos, tanto la llamada como la secuencia se usan en el nombre de la medida (por ejemplo, la secuencia de configuración de llamadas o el flujo de llamada interrumpida). Aún se clasifican como transmisiones.

-   **Llamar:** Una _llamada_ es una agrupación de todas las transmisiones de todos los participantes. Una llamada consiste en, como mínimo, en dos secuencias. Una sola llamada tendrá al menos dos puntos de conexión, cada uno con un mínimo de una secuencia.

Para obtener más información sobre si la dimensión o medida hace referencia a una llamada o una secuencia, consulte [dimensiones y medidas disponibles en el CQD](https://aka.ms/cqd-dm) .

### <a name="good-poor-and-unclassified-calls"></a>Llamadas no clasificadas, muy pobres y buenas

Una llamada se clasifica como buena, mala o no clasificada. Dediquemos un momento a hablar sobre cada uno con más detalles.

-   **Bueno o malo:** Una buena o mala llamada consiste en una llamada que contiene un conjunto completo de parámetros de servicio, para los que el servicio ha generado y recibido un informe de QoE de calidad completo. La determinación de si una secuencia es buena o mala se describe [anteriormente en este artículo](#poor-stream-rate).

-   Sin **clasificar:** Una transmisión sin clasificar no contiene un conjunto completo de métricas de servicio. Pueden ser llamadas breves, generalmente de menos de 60 segundos, donde los promedios no se han calculado y no se ha generado un informe de QoE. La razón más común para que las llamadas sean no clasificadas es que no haya ninguna utilización de paquetes. Un ejemplo de esto sería un participante que se une a una reunión al silenciar y nunca habla. El participante recibe, pero no transmite, los medios. Sin transmitir los medios, no habrá ninguna métrica disponible para que el CQD los use para clasificar la secuencia multimedia saliente del punto de conexión.

Para obtener más información, lea [clasificación de la secuencia en el CQD](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Subredes comunes

Las subredes comunes son subredes privadas específicas que se usan en hoteles, redes domésticas, puntos de acceso público y áreas similares. Estas subredes son difíciles de clasificar debido a su uso generalizado. Si su organización usa una de estas subredes comunes, le recomendamos que mueva esa red a otra subred. Esto facilitará los informes en el CQD. Cuando se indica, los informes de la plantilla todas las redes se han configurado para excluir estas subredes para eliminarlas como fuente de baja calidad. Las subredes comunes se definen a continuación; su impacto variará según la organización.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Al investigar una red administrada que usa una subred común, tendrá que usar la segunda dimensión IP local reflexiva para agrupar subredes. Esta dimensión contiene la dirección IP pública del punto de conexión.


## <a name="reliability-investigations"></a>Investigaciones de confiabilidad

El primer paso para mejorar la calidad es evaluar el estado de confiabilidad en toda la organización. Puesto que la confiabilidad es vital para una experiencia de usuario positiva, comenzamos con los dos componentes que miden la confiabilidad:

1.  **Errores de configuración:** No se pudo establecer la llamada.

2.  **Errores de colocación:** La llamada se estableció y terminó de forma inesperada.

En esta sección, cubriremos métodos para investigar las dos áreas.

> [!NOTE]
> En este artículo no se tratan todos los informes incluidos en las plantillas. Sin embargo, siguen aplicándose los métodos de investigación explicados a continuación. Para obtener más información, consulta la descripción del informe individual.


### <a name="setup-failures"></a>Errores de configuración

Dé prioridad a la corrección de errores de configuración en esta área en primer lugar, porque estos errores tienen un impacto negativo significativo en la experiencia del usuario.

Empiece la investigación evaluando el porcentaje de errores generales de configuración de la organización y, a continuación, establezca prioridades en las áreas de investigación según el porcentaje más alto en la creación o la red. 

#### <a name="setup-failure-trend-analysis"></a>Análisis de tendencias de errores de configuración

Este informe muestra la cantidad total de flujos, errores de configuración de la transmisión por secuencias y la tasa de errores de configuración de la transmisión. Apunte a cualquiera de las columnas para mostrar sus valores individuales. 

##### <a name="analysis"></a>Análisis

Con este informe, puede responder a las siguientes preguntas y determinar el siguiente curso de acción:

-   ¿Cuál es el porcentaje total de errores de configuración de llamadas del mes actual?

-   ¿El porcentaje total del error de configuración de la llamada está por debajo o por encima de la métrica objetivo definida?

-   ¿La tendencia del error es peor o superior que el mes anterior?

-   ¿El aumento, la estabilidad o la disminución de la tendencia del error?

Independientemente de sus respuestas a estas preguntas, dedique el tiempo de investigar con los subinformes complementarios para buscar edificios o subredes individuales que puedan requerir corrección. A pesar de que la tasa de error general puede estar por debajo de la métrica de destino, las tarifas de error para uno o más edificios o redes pueden estar por encima de la métrica de destino y necesitan investigación.

#### <a name="setup-failure-investigations"></a>Investigaciones de errores de configuración 

Este informe de resumen se usa para descubrir y aislar cualquier edificio o red que pueda necesitar corrección.

> [!NOTE]
> Asegúrese de ajustar el filtro de informe de año mensual al mes en curso. Seleccione **Editar**y ajuste el filtro de informe **mes de año** para guardar el nuevo mes predeterminado.

##### <a name="remediation"></a>Corrección 

Centre el primer esfuerzo de corrección en edificios o subredes que tengan el mayor volumen de errores. Esto maximizará el impacto en la experiencia del usuario y ayudará a reducir rápidamente la tasa de errores de configuración de las llamadas de la organización. En la tabla siguiente se enumeran los dos motivos de errores de configuración notificados por el CQD.

| Motivo de errores de configuración de llamadas       | Causa típica                    |
|----------------------------------|----------------------------------|
| Regla de exención de inspección de paquetes profundos de FW ausente | Indica que el equipo de red de la ruta impidió que se establecera la ruta de medios debido a reglas de inspección de paquetes en profundidad. Probablemente se deba a que las reglas de Firewall no se han configurado correctamente. En este escenario, el protocolo de enlace TCP tuvo éxito pero el protocolo de enlace SSL no.      |
| Falta la regla de excepción de bloqueo IP de FW      | Indica que el equipo de red de la ruta ha impedido que la ruta de acceso a los medios se establezca en la red de Microsoft 365 o de Office 365. Esto puede deberse a que las reglas de proxy o de Firewall no se han configurado correctamente para permitir el acceso a las direcciones IP y los puertos que se usan para los equipos y el tráfico de Skype empresarial. |

Al empezar su corrección, puede concentrar sus esfuerzos en un edificio o una subred en particular. Como se muestra en la tabla anterior, estos problemas se deben a configuraciones de firewall o proxy. Revise las opciones de la tabla siguiente para ver las acciones de corrección.

|      Corrección      |Instrucciones  |
|-----------------------|----------|
| Configurar firewalls | Trabaje con el equipo de red y Compruebe la configuración de los firewalls con [la lista de direcciones IP de Office 365](https://aka.ms/o365ips).<br><br>Compruebe que las [subredes](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) y los puertos de medios estén incluidos en las reglas de Firewall. <br><br>Compruebe que los [puertos necesarios](prepare-network.md) están abiertos en el firewall. Se debe dar prioridad a UDP porque TCP se considera un protocolo de conmutación por recuperación para el audio, el vídeo y la pantalla compartida basada en vídeo, y su uso afectará a la calidad de la llamada. RDP heredado el uso compartido de aplicaciones usa solo TCP.|

### <a name="drop-failures"></a>Errores de colocación

A diferencia de los códigos de error de configuración, el CQD no tiene código de error de colocación para indicar por qué se producen errores de colocación, lo que hace que sea difícil aislar una causa raíz específica. Para mejorar la evaluación de errores, use un enfoque deducido. Si corrige las áreas de interés de los medios, aplica revisiones a los clientes y los drivers y, por ello, impulsa el uso de dispositivos certificados para equipos y Skype empresarial, puede esperar que se produzcan errores de rechazo.

#### <a name="drop-failure-trend-analysis"></a>Análisis de tendencias de errores de eliminación

Este informe muestra la cantidad total de transmisiones de audio, los errores de eliminación total y la tasa de errores al colocar. Apunte a cualquiera de las columnas para mostrar sus valores. 


##### <a name="analysis"></a>Análisis

Al usar este tipo de informe, puede responder a las siguientes preguntas:

-   ¿Cuál es la tasa de errores de caída actuales?
-   ¿La tasa de error de colocación está por debajo de la métrica de destino definida?
-   ¿La tendencia del error es peor o superior que el mes anterior?
-   ¿El aumento, la estabilidad o la disminución de la tendencia del error?

Independientemente de las respuestas a las preguntas anteriores, dedique el tiempo de investigar el uso de los subinformes para buscar edificios o redes que puedan necesitar corrección. Aunque la tasa general de errores de colocación puede estar por debajo de la métrica de destino, la tasa de errores de caída para uno o varios edificios o redes podría estar por encima de la métrica de destino y necesita investigar.

#### <a name="drop-failure-investigations"></a>Eliminar investigaciones de errores

Los errores notificados aquí indican que la llamada se ha interrumpido de forma inesperada y resultó en una experiencia de usuario negativa. A diferencia de los informes de tendencias, estos informes proporcionan información adicional sobre subredes específicas que necesitan más investigación.


##### <a name="remediation"></a>Corrección

Con los informes de tabla incluidos, puede aislar las áreas problemáticas de la red donde la tasa de colocación está por encima de la métrica de objetivo que ha definido. Centre el primer esfuerzo de corrección en edificios o subredes que tengan la cantidad máxima de flujo total, para lograr el mayor impacto.

Causas comunes de caídas de llamadas:

-   Salida de red o de Internet aprovisionada
-   No hay ninguna QoS configurada en redes restringidas
-   Versiones de cliente anteriores
-   Comportamiento del usuario

Una vez que haya descubierto las áreas problemáticas, puede usar el [análisis de llamadas por usuario](use-call-analytics-to-troubleshoot-poor-call-quality.md) para revisar aún más los usuarios de la creación para problemas específicos. Los análisis de llamadas contienen datos de EUII adicionales y pueden ser útiles para aislar aún más posibles causas de los errores de colocación.

Independientemente del próximo paso, es recomendable notificar al Departamento de soporte técnico que se ha detectado un problema con edificios o subredes específicas. Esto permite que el servicio de asistencia al usuario responda rápidamente a las llamadas entrantes y clasifique los usuarios de manera más eficaz. Los usuarios marcados pueden ser devueltos al equipo de ingeniería para obtener más investigación.

En la tabla siguiente se enumeran algunos métodos comunes para administrar y corregir errores de Drop.

| Corrección                              | Instrucciones                      |
|------------------------------------------|-------------------------------|
| **Red e Internet**                         | **Congestión**: trabaje con su equipo de red para controlar el ancho de banda en edificios o subredes específicos para confirmar que hay problemas de sobreutilización. Si confirma que hay congestión en la red, considere la posibilidad de aumentar el ancho de banda a la creación o la aplicación de QoS. Use los [informes de Resumen de calidad deficiente](#quality-investigations) incluidos para revisar las subredes problemáticas para problemas de vibración, latencia y pérdida de paquetes, porque normalmente precederán a una transmisión.<br><br>**QoS**: Si el aumento de ancho de banda no es práctico o es prohibitiva, considere la posibilidad de implementar QoS. Esta herramienta es muy eficaz en la administración del tráfico congestionado y puede garantizar que los paquetes multimedia de la red administrada estén clasificados por encima del tráfico no multimedia. Como alternativa, si no hay evidencia clara de que el puesto de ancho de banda sea el culpable, considere estas soluciones:<ul><li>[Guía de QoS de Microsoft Teams](qos-in-teams.md)</li></ul><br>**Realizar una evaluación**de la preparación para la red: una evaluación de la red proporciona detalles sobre el uso esperado de ancho de banda, cómo hacer frente a los cambios de ancho de banda y red, así como prácticas recomendadas de redes para equipos y Skype empresarial. Con la tabla anterior como origen, tiene una lista de edificios o subredes que son candidatos excelentes para una evaluación.<ul><li>[Preparar la red de la organización para Microsoft Teams](prepare-network.md)</li></ul> |
| **Clientes (solo Skype empresarial online)** | Algunos de los clientes más antiguos de Skype empresarial han conocido problemas documentados con la confiabilidad de los medios. Revise los informes de análisis de llamadas de varios usuarios afectados o cree un informe de tabla de versiones de cliente personalizado en el CQD filtrado para edificios o subredes específicas con error total de llamadas% en medida. Esta información le ayudará a comprender si existe una relación entre las caídas de llamadas de ese edificio específico y una versión específica del cliente.     |
| **Dispositivos**                                  |Si los dispositivos son la causa de los problemas de calidad de la llamada, considere la posibilidad de actualizar los dispositivos ofensivos. Para obtener más información, lea [teléfonos para Teams](phones-for-teams.md) . |
| **Comportamiento del usuario**                            | Si determina que ninguna red, dispositivo o cliente es el problema, considere la posibilidad de desarrollar una estrategia de adopción de usuarios para educar a los usuarios a unirse y salir de las reuniones mejor. Un equipo más inteligente y un usuario de Skype empresarial producirá una mejor experiencia de usuario para todos los participantes de la reunión. Por ejemplo, un usuario que pone el equipo portátil en modo de suspensión (cerrando la tapa) sin salir de la reunión se clasificará como una llamada inesperada.   |

## <a name="quality-investigations"></a>Investigaciones de calidad

El siguiente paso para evaluar el estado de la calidad de audio en toda la organización es investigar la mala tasa de transmisión (PSR), TCP y el uso del proxy. Es importante recordar que los datos del CQD no le proporcionan una causa raíz específica, sino que le proporcionan posibles problemas para comenzar una conversación colaborativa con los equipos apropiados para las actividades de corrección. 

> [!NOTE]
> En este artículo no se tratan todos los informes incluidos en las plantillas; sin embargo, los métodos de investigación explicados a continuación seguirán aplicándose para esos informes. Para obtener más información, consulte la descripción del informe individual. 

### <a name="quality"></a>Compra

Los porcentajes de VECPRD se usan para indicar si la organización está a la reunión de objetivos métricos definidos para un área de enfoque determinada. Es importante tener en cuenta que, incluso si los porcentajes de alto nivel están dentro del objetivo definido, las subredes o los edificios individuales pueden no cumplir los objetivos definidos y, por consiguiente, necesitan más investigación. Por ejemplo, si el total de los VECPRD es el 2 por ciento en abril, que cumple con el destino de la muestra, es posible que los edificios y subredes individuales sigan teniendo una mala experiencia en función de la distribución general de ese 2 por ciento. 

Para evaluar el porcentaje de transmisiones deficientes, use los informes de calidad. Se proporcionan diversos informes de calidad para revisar las métricas generales, de conferencia, de dos, llamadas RTC, VPN y salas de reuniones. Se proporcionan informes mensuales, semanales y diarios para ayudar en este proceso. Los informes semanales y diarios se limitan a la plantilla redes administradas para aumentar su eficacia y reducir el ruido. 

#### <a name="quality-trend-analysis"></a>Análisis de tendencias de calidad

Los informes de tendencias muestran información sobre la calidad a lo largo del tiempo y se usan para ayudar a identificar y comprender las tendencias de calidad dentro de cada área de interés. Como se mencionó anteriormente, hay árboles de informes incluidos en las plantillas para la investigación de calidad. conferencias, llamadas RTC, VPN y salas de reuniones de dos partes. Para el análisis de la calidad, el proceso de investigación es el mismo. Sin embargo, le recomendamos que empiece con conferencias en primer lugar, porque cualquier mejora en la calidad de la Conferencia también afectará de forma positiva a todas las demás áreas. 

> [!Note]
> La investigación de dos entidades, la de llamadas RTC y las salas de reuniones son similares a las de investigación. El foco es aislar edificios o subredes que tengan la peor calidad e identificar el motivo de la mala calidad.

> [!Important]
> Los informes basados en VPN se filtran mediante la segunda dimensión VPN. Esta dimensión requiere que el adaptador de red VPN esté correctamente registrado como un adaptador de acceso remoto. Los proveedores de VPN no usan de forma confiable esta marca y su kilometraje varía según el proveedor de VPN implementado en su organización. Modifique los informes de [VPN](CQD-upload-tenant-building-data.md#vpn) si es necesario con el nombre de la red o el edificio.

##### <a name="investigation"></a>Puso

Con estos informes, puede responder a las siguientes preguntas:

-   ¿Cuál es el total de los VECPRD para el mes en curso?
-   ¿El PSR se encuentra debajo de la métrica de destino definida?
-   ¿Es PSR peor o mejor que el mes anterior?
-   ¿El aumento, la estabilidad o la disminución de la tendencia de los VECPRD?

Independientemente de las respuestas a las preguntas anteriores, dedique tiempo a investigar usando los subinformes para buscar edificios o subredes que puedan necesitar investigación. Aunque los VECPRD pueden estar por debajo de la métrica del objetivo, a menudo los VECPRD de uno o más edificios o redes están por encima de la métrica y necesita corrección.

#### <a name="quality-investigations"></a>Investigaciones de calidad

Los informes de Resumen de calidad proporcionan una perspectiva más profunda de lo que ha contribuido a clasificar las transmisiones como malas y ayudan a aislar las áreas problemáticas de la red administrada.

A pesar de que las dimensiones utilizadas pueden variar ligeramente entre informes, cada informe incluirá medidas para las transmisiones totales, las secuencias deficientes totales, los VECPRD y la mala calidad debido a. Se han creado informes para cada área de interés: conferencias, llamadas RTC, VPN y salas de reuniones. La plantilla de red administrada incluye informes adicionales para aprovechar la información de ubicación cargada a través del archivo de creación.


> [!Note]
> Las subredes comunes son difíciles de clasificar debido a su uso generalizado. Se ha agregado a la plantilla todas las redes un informe independiente que muestra la dirección IP pública del cliente (segundo IP local reflexiva) para ayudarle a corregir las oficinas que usan redes comunes.


![Captura de pantalla que muestra el Resumen de flujo de audio deficiente](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Corrección

Centre sus esfuerzos de corrección en edificios o subredes que tengan el mayor volumen de secuencias, porque esto maximizará el impacto y ayudará a mejorar la experiencia del usuario rápidamente. Use las medidas de vibración, pérdida de paquetes y tiempo de ida y vuelta (RTT) para comprender qué contribuye a la mala calidad (es posible que no haya más de un problema):

-   **Vibración**: los paquetes multimedia llegan a velocidades diferentes, lo que hace que un altavoz suene de forma robótica.
-   **Pérdida de paquetes**: los paquetes multimedia se pierden, lo que crea el efecto de que faltan palabras o sílabas.
-   **RTT**: los paquetes multimedia tardan mucho tiempo en llegar a su destino, lo que crea un efecto walkie-talkie.

Para ayudar a la investigación en problemas de calidad, use [análisis de llamadas por usuario](use-call-analytics-to-troubleshoot-poor-call-quality.md). Con el análisis de llamadas, puede consultar una conferencia determinada o un informe de llamadas de usuario. Este informe contendrá datos EUII/PII y es útil cuando busca la causa de un error. Una vez que sepa qué edificio se verá afectado, debe realizar un seguimiento sencillo de los usuarios de ese edificio. 

No olvides avisar al Helpdesk de que estas redes experimentan problemas de calidad, de modo que puedan clasificar y responder rápidamente a las llamadas entrantes.

| Corrección                              | Instrucciones                         |
|------------------------------------------|----------------------------------|
| **Las**                                 | **Congestión**: una red sobreutilizada o con aprovisionamiento puede causar problemas con la calidad de los medios. Trabaje con el equipo de red para determinar si las conexiones de red entre el usuario y el punto de salida de Internet tienen suficiente ancho de banda para admitir medios. <br><br>**Realizar una evaluación**de la preparación para la red: una evaluación de la red proporciona detalles sobre el uso esperado de ancho de banda, cómo hacer frente a los cambios de ancho de banda y red, así como prácticas recomendadas de redes para equipos y Skype empresarial. Con la tabla anterior como origen, tiene una lista de edificios o subredes que son candidatos excelentes para una evaluación.<ul><li>[Preparar la red de la organización para Microsoft Teams](prepare-network.md)</li></ul>|
| **Calidad de servicio (QoS)**  | QoS es una herramienta comprobada para ayudar a priorizar paquetes en una red congestionada para asegurarse de que lleguen a su destino intacto y a tiempo. Considere la posibilidad de implementar QoS en toda la organización para maximizar la calidad de la experiencia del usuario donde se restringe el ancho de banda. QoS le ayudará a resolver problemas típicamente relacionados con los altos niveles de pérdida de paquetes y, a menor grado, la vibración y los tiempos de ida y vuelta.<ul><li>[Guía de equipos con QoS](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | La Wi-Fi puede tener un impacto significativo en la calidad de las llamadas. Por lo general, las implementaciones de Wi-Fi no tienen en cuenta los requisitos de red de los servicios de VoIP y suelen ser una fuente de mala calidad. Para obtener más información sobre cómo optimizar su infraestructura Wi-Fi, consulte [este artículo sobre la planificación de Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Controlador inalámbrico**: Asegúrese de que los drivers inalámbricos estén actualizados. Esto ayudará a reducir cualquier experiencia de usuario deficiente relacionada con un controlador anticuado. Muchas organizaciones no incluyen drivers inalámbricos en los ciclos de las revisiones, y estos drivers pueden desplazarse por años. Muchos problemas de conexión inalámbrica se resuelven asegurándose de que los drivers inalámbricos estén actualizados.<br><br>**WMM**: las extensiones multimedia inalámbricas (WMM), también conocidas como Wi-Fi multimedia, proporcionan características básicas de QoS para redes inalámbricas. Las redes inalámbricas modernas deben admitir muchos dispositivos. Estos dispositivos compiten por el ancho de banda y pueden provocar problemas de calidad en los servicios de VoIP, donde la velocidad y la latencia son fundamentales. Consulta a tu proveedor de telefonía móvil para conocer los detalles y considera la posibilidad de implementar WMM en tu red inalámbrica para priorizar Skype empresarial y los equipos multimedia.<br><br>**Densidad**de puntos de acceso: es posible que los puntos de acceso estén demasiado alejados o no estén en una ubicación ideal. Para minimizar posibles interferencias, coloque puntos de acceso adicionales en salas de conferencias y en ubicaciones que no estén obstruidas por paredes u otros objetos en los que la señal Wi-Fi es débil.<br><br>**2,4 GHz frente a 5 GHz**: 5 GHz proporciona menos interferencias de fondo y velocidades superiores, y se debe priorizar al implementar VoIP a través de Wi-Fi. Sin embargo, 5 GHz no es tan fuerte como 2,4 GHz y no penetra en paredes con facilidad. Revise el diseño del edificio para determinar en qué frecuencia puede confiar para la mejor conexión. |
|**Dispositivo de red** | Las organizaciones más grandes pueden tener cientos de dispositivos repartidos en toda la red. Trabaje con su equipo de red para asegurarse de que los dispositivos de red del usuario a Internet se mantengan y estén actualizados. |
| **VPN**  | Los equipos VPN no están diseñados tradicionalmente para admitir cargas de trabajo de medios en tiempo real. Algunas configuraciones de VPN prohíben el uso de UDP (que es el protocolo preferido para los medios) y dependen únicamente de TCP. Considere la posibilidad de implementar una solución de túnel dividido de VPN para ayudar a reducir la VPN como una fuente de baja calidad. |
| **Clientes** <br>(Solo Skype empresarial online) | Asegúrese de que todos los clientes se actualizan regularmente. |
| **Dispositivos** | Si los dispositivos son la causa de los problemas de calidad de la llamada, considere la posibilidad de actualizar los dispositivos ofensivos. Para obtener más información, lea [teléfonos para Teams](phones-for-teams.md) . |
| **Conductores** | La actualización de la red (Ethernet y Wi-Fi), los drivers de audio, vídeo y USB deben formar parte de la estrategia general de administración de revisiones. La actualización de los drivers resuelve muchos problemas de calidad. |
| **Salas de reuniones en Wi-Fi** | Recomendamos encarecidamente que los dispositivos de la sala de reuniones se conecten a la red mediante al menos una conexión Ethernet de 1 Gbps. Los dispositivos de la sala de reuniones suelen incluir varias transmisiones de audio y vídeo, además de contenido de la reunión, como la pantalla compartida, y tienen más requisitos de red que otros equipos o puntos de conexión de Skype empresarial. Los salones de reunión son, por definición, dispositivos fijos en los que las Wi-Fi ofrecen una ventaja únicamente durante la instalación.<br><br>Las salas de reuniones deben ser tratadas con cuidado y atención adicionales para asegurarse de que la experiencia con estos dispositivos está cumpliendo o superando las expectativas. Por lo general, los problemas de calidad con salas de reuniones se escalan rápidamente, ya que a menudo son utilizadas por personal de nivel superior.<br><br>Con todas las cosas iguales (aparte de la comodidad), el rendimiento de Wi-Fi suele ser menor que una conexión por cable. Con el aumento de las políticas de "traiga sus propios dispositivos" y la proliferación de equipos portátiles, los puntos de acceso Wi-Fi suelen estar sobreutilizados. Es posible que los medios en tiempo real no tengan prioridad en las redes Wi-Fi, lo que puede provocar problemas de calidad durante los períodos de uso máximo. Este uso intensivo puede coincidir con una reunión en la que puede haber una docena de personas en la asistencia, cada una con su propio portátil y smartphone, todos conectados al mismo punto de acceso Wi-Fi que el dispositivo de la sala de reuniones.<br><br>Wi-Fi solo debe considerarse una solución temporal, para una instalación móvil o cuando Wi-Fi se ha aprovisionado correctamente para admitir medios de clase empresarial y en tiempo real. |


### <a name="tcp"></a>TCP 

El protocolo de control de transmisión (TCP) se considera un transporte de conmutación por recuperación y no el transporte principal que desea para medios en tiempo real. La razón por la que se trata de un transporte de failback es debido a la naturaleza de estado de TCP. Por ejemplo, si una llamada se realiza en una red latente y los paquetes multimedia se retrasan, los paquetes desde hace unos segundos, que ya no son útiles, compite por el ancho de banda para llegar al receptor, lo cual puede empeorar la situación. Esto hace que el avisador de audio ditire y expanda el audio, lo que da como resultado artefactos audibles, generalmente en forma de vibración.

Los informes de esta sección no distinguen entre buenas y malas transmisiones. Dado que se prefiere UDP, los informes buscan el uso de TCP para el uso compartido de pantalla basado en vídeo, audio y vídeo (VBSS). Las tarifas de flujo deficientes se proporcionan para ayudar a comparar la calidad de UDP frente a la de TCP, de modo que pueda centrar sus esfuerzos cuando el impacto sea el más alto. El uso de TCP se debe principalmente a las reglas incompletas del firewall. Para obtener más información sobre las reglas de Firewall para Teams y Skype empresarial online, consulte [direcciones URL e intervalos de direcciones IP de Microsoft 365 y Office 365](https://aka.ms/o365ips).

> [!Note]
> El audio, el vídeo y el de VBSS prefieren UDP como transporte principal. La carga de trabajo de uso compartido de aplicaciones RDP heredada solo usa TCP.

#### <a name="tcp-usage"></a>Uso de TCP

Informes TCP indica el uso general de TCP en los últimos siete meses. Todos los demás informes de esta sección se centrarán en reducir los edificios y subredes específicos en los que se usa con más frecuencia. Hay informes independientes disponibles para las conferencias y las secuencias de dos partes.

![Gráfico que muestra el porcentaje de transmisiones de audio que usan TCP](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Puso

Con este informe, puede responder a las siguientes preguntas:

-   ¿Cuál es el volumen total de transmisiones TCP para el mes en curso?
-   ¿Es peor o mejor que el mes anterior?
-   ¿El aumento, la estabilidad o la disminución de la tendencia de uso de TCP?
-   ¿El TCP PSR es el mismo que el de mi PSR en general?

Si observa que la tendencia de uso de TCP está aumentando o superado el uso mensual normal, dedique tiempo a investigar con los subinformes para buscar edificios o redes que puedan necesitar corrección. Lo ideal es que desees las sesiones de audio basadas en TCP como sea posible en la red administrada.

#### <a name="tcp-vs-udp"></a>TCP frente a UDP

Este informe identifica el volumen de los informes de uso de TCP frente al UDP el mes más reciente para la pantalla compartida basada en vídeo, audio y vídeo (VBSS). 

![Informe que muestra el volumen de transmisiones que usan TCP frente a UDP](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Análisis

Aunque desea que el uso de TCP sea lo más bajo posible, es posible que vea un poco de uso de TCP en una implementación en buen estado. Por sí solo TCP no contribuye a una mala llamada, por lo que se proporcionan tarifas de flujo para ayudar a identificar si el uso de TCP es un colaborador de baja calidad. 

#### <a name="tcp-investigations"></a>Investigaciones de TCP

En las plantillas de CQD proporcionadas, navegue hasta las transmisiones por secuencias de TCP mediante la creación de informes de subred o redes administradas. Con el fin de investigar el uso de TCP, el proceso es el mismo, por lo que centraremos el debate aquí en conferencias.


##### <a name="remediation"></a>Corrección

Este informe identifica edificios y subredes específicos que están contribuyendo al volumen de uso de TCP. También se incluye un informe adicional para identificar la IP de Microsoft Relay que se usó en la llamada para ayudar a aislar las reglas de firewall que faltan. Centre sus esfuerzos de corrección en aquellos edificios que tengan el mayor volumen de transmisiones TCP para maximizar el impacto.

La causa más común del uso de TCP es la falta de reglas de excepción en firewalls o servidores proxy. Hablaremos sobre los servidores proxy en la siguiente sección, así que para centrar sus esfuerzos en los firewalls. Al usar el edificio o la subred proporcionados, puede determinar qué Firewall necesita actualizarse.

| Corrección        | Instrucciones     |
|--------------------|--------------------------------------|
| Configurar el Firewall | Verifique que los [puertos y las direcciones IP Microsoft 365 u Office 365](https://aka.ms/o365ips) estén excluidos de su firewall. Para problemas de TCP relacionados con los medios, Centre sus esfuerzos iniciales en lo siguiente:<ul><li>Compruebe que las subredes de medios del cliente 13.107.64.0/18 y 52.112.0.0/14 estén en las reglas del firewall.</li><li>Puertos UDP 3478:3481 son los puertos de medios necesarios y deben abrirse; de lo contrario, el cliente no podrá recuperar el puerto TCP 443.</li></ul> |
| Verificar             | Use la [herramienta de evaluación de redes de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si hay problemas de conectividad con las direcciones y puertos IP específicos de Microsoft 365 u Office 365 de la subred o el edificio afectado.    |

### <a name="http-proxy"></a>Proxy HTTP

Los proxies HTTP no son la ruta preferida para establecer sesiones de medios, por un gran variedad de motivos. Muchos contienen características de inspección de paquetes en profundidad que pueden impedir que se completen las conexiones al servicio e introducir interrupciones. Además, casi todos los servidores proxy fuerzan a TCP en lugar de permitir UDP, lo que se recomienda para una óptima calidad de audio.

Siempre recomendamos que configure el cliente para que se conecte directamente a teams y a los servicios de Skype empresarial. Esto es especialmente importante para el tráfico basado en elementos multimedia.


> [!IMPORTANT]
> Le recomendamos que cargue un [archivo de compilación válido](CQD-upload-tenant-building-data.md) para que pueda distinguir dentro de las transmisiones de audio externas al analizar el uso del proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

El informe de la secuencia de proxy HTTP de esta sección de la plantilla es muy similar a los informes TCP. Sin embargo, no se muestra si las llamadas son deficientes o buenas, pero si la llamada está conectada a través de HTTP.

![Captura de pantalla del informe de transmisiones de audio que usan HTTP](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Análisis

Desea ver la menor cantidad posible de transmisiones por medio de HTTP. Si tiene secuencias que atraviesan su proxy, consulte con su equipo de redes para asegurarse de que se encuentran las exclusiones apropiadas para que los clientes se enruten directamente a teams o a las subredes de multimedia de Skype empresarial online.

Si solo tiene un proxy de Internet en su organización, verifique las [direcciones URL y las exclusiones de intervalos de direcciones IP de Microsoft 365 u Office 365](https://aka.ms/o365ips). Si hay más de un proxy de Internet configurado en su organización, use el subinforme HTTP para aislar qué compilación o subred se verá afectada.

Para las organizaciones que no pueden eludir el proxy, asegúrese de que el cliente de Skype empresarial está configurado para iniciar sesión correctamente cuando se encuentra detrás de un proxy, como se describe en el artículo, [Skype empresarial debe usar Proxy Server para iniciar sesión en lugar de probar la conexión directa](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Investigaciones de proxy HTTP

Este informe identifica los edificios y subredes específicos que están contribuyendo al uso de HTTP.


##### <a name="remediation"></a>Corrección

Le [recomendamos](proxy-servers-for-skype-for-business-online.md) que Evite siempre los servidores proxy de Skype empresarial y Teams, especialmente el tráfico de medios. Los servidores proxy no hacen que Skype empresarial sea más seguro, ya que su tráfico ya está cifrado. Los problemas relacionados con el rendimiento pueden introducirse en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos provocarán una experiencia negativa con el audio, el vídeo y la pantalla compartida, en el que son esenciales las secuencias en tiempo real.

La causa más común del uso de HTTP es que faltan reglas de excepción en los servidores proxy. Mediante el edificio o la subred proporcionados, puede determinar rápidamente qué proxy debe configurarse para la omisión de medios.

Compruebe que los [FQDN de Microsoft 365 o de Office 365](https://aka.ms/o365ips) están en la lista blanca en el proxy.

## <a name="endpoint-investigations"></a>Investigaciones de extremo

Esta sección se centra en las tareas de informes sobre las versiones de cliente y el uso de dispositivos certificados. Los informes están disponibles para esquematizar el uso de las versiones de cliente, el tipo de cliente, los dispositivos de captura y los drivers (micrófono), los dispositivos de captura de vídeo y las versiones de proveedores y controladores de Wi-Fi.

> [!NOTE]
> En este artículo no se tratan todos los informes incluidos en las plantillas; sin embargo, siguen aplicándose los métodos de investigación explicados a continuación. Para obtener más información, consulte la descripción del informe individual.

### <a name="client-versions"></a>Versiones de cliente

Estos informes se centran en identificar las versiones de cliente de Skype empresarial en uso y su volumen relativo en el entorno.

> [!IMPORTANT]
> Actualmente, los clientes de equipos se distribuyen y actualizan automáticamente a través de la red de entrega de contenido de Azure y el servicio lo mantendrá actualizado. Como resultado, no es necesario que supervise las versiones del cliente de Teams (a menos que desactive la actualización automática, lo que no recomendamos).

A menos que excluya los datos de los participantes federados, estos informes incluirán telemetría de cliente de puntos de conexión federados. Para excluir puntos de conexión federados, debe agregar un filtro de consulta para el segundo identificador de inquilino establecido en el [identificador de inquilino](CQD-data-and-reports.md#how-to-find-your-tenant-id)de su organización. Como alternativa, puede usar un [filtro de URL](CQD-data-and-reports.md#url-filters) para excluir la telemetría de participantes federados.



#### <a name="remediation"></a>Corrección

Una parte crítica de las experiencias de usuario de alta calidad es garantizar que los clientes administrados ejecutan versiones actualizadas de Skype empresarial, además de garantizar que los drivers compatibles con audio, vídeo, red y USB estén actualizados. Esto ofrece varias ventajas, entre ellas: 

-   Es más fácil administrar algunas versiones, en lugar de muchas versiones.
-   Proporciona un nivel de coherencia de la experiencia.
-   Es más fácil solucionar problemas con la calidad de las llamadas y la capacidad de uso.
-   Microsoft realiza continuamente mejoras y optimizaciones generales en todo el producto. Asegurarse de que los usuarios reciban estas actualizaciones reducen el riesgo de que se produzca un problema que ya se ha resuelto.

Limitar la implementación a versiones de cliente con menos de seis meses de antigüedad mejorará la experiencia general del usuario y mejorará la facilidad de administración al reducir el número de versiones que deben ser compatibles.

Si está usando solo hacer clic y ejecutar de Office, se encontrará automáticamente en la ventana de seis meses. No es necesario realizar ninguna otra acción.

Si tiene una mezcla de hacer clic y ejecutar y paquetes de instalación (MSI), puede usar el informe para comprobar que los clientes MSI se actualizan regularmente. Si detecta que los clientes están retrasados, trabaje con el equipo responsable de administrar las actualizaciones de Office y asegúrese de que están aprobando e implementando regularmente las revisiones de cliente.

También es importante tener en cuenta y garantizar que los drivers de red, vídeo, USB y audio también se revisan. Puede ser fácil pasar por alto estos drivers y no incluirlos en la estrategia de administración de revisiones.

Los números de versión de Skype empresarial se pueden encontrar a través de los siguientes vínculos:

-   [Información de versión para las actualizaciones de las aplicaciones de Microsoft 365](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Historial de actualizaciones de las aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Descargas y actualizaciones de Skype Empresarial](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivos

Para usar el informe de dispositivo de micrófono, necesitamos comprender el concepto de la puntuación de opinión media (MOS). MOS es la medición estándar de oro para medir la calidad de audio percibida. Se representa como una clasificación de entero de 0 a 5.

La base de todas las medidas de calidad de voz es cómo percibe una persona la calidad de la voz. Debido a que se ve afectado por la percepción humana, es subjetivo de forma inherente. Existen diferentes metodologías para las pruebas subjetivas. La mayoría de las medidas de calidad de voz se basan en una escala de clasificación de categorización absoluta (ACR).

En una prueba de subjetivo de ACR, un número estadísticamente significativo de personas califica la calidad de la experiencia en una escala de 1 (mala) a 5 (excelente). El promedio de las puntuaciones es el MOS. El MOS resultante depende de la variedad de experiencias que se hayan expuesto al grupo y del tipo de experiencia que se esté clasificando.

Puesto que no es práctico realizar pruebas subjetivas de la calidad de voz para un sistema de comunicación en vivo, Microsoft Teams y Skype empresarial generan valores de OP mediante algoritmos avanzados para predecir de manera objetiva los resultados de una prueba subjetiva.

El conjunto disponible de MOS y las métricas relacionadas proporcionan una vista de la calidad de la experiencia que se envía a los usuarios a través de un dispositivo de audio. 

Al proporcionar a los usuarios los dispositivos certificados para equipos y Skype empresarial, se reduce la posibilidad de que se produzcan experiencias negativas debido al propio dispositivo (lo cual es más probable, por ejemplo, con micrófonos y altavoces de equipos portátiles integrados). Para obtener más información, consulte estos artículos en el [programa de certificación](/SkypeForBusiness/certification/overview) y el catálogo de soluciones de [socios](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Los informes de dispositivos se usan para evaluar el uso del dispositivo por volumen y la puntuación de MOS (solo audio), y se pueden encontrar en las plantillas correspondientes de clientes & dispositivos. 

> [!IMPORTANT]
> A menos que excluya los datos de los participantes federados, estos informes incluirán telemetría de cliente de puntos de conexión federados. Para excluir puntos de conexión federados, debe agregar un filtro de consulta para el **segundo identificador de inquilino** establecido en el [identificador de inquilino](CQD-data-and-reports.md#how-to-find-your-tenant-id)de su organización. Como alternativa, puede usar un [filtro de URL](CQD-data-and-reports.md#url-filters) para excluir la telemetría de participantes federados.


> [!Note]
> Es posible que se muestre al ver este informe que vea el mismo dispositivo que se ha notificado varias veces. Esto se debe a la forma en que se informa al producto del CQD. Las diferencias en el hardware y la configuración regional del sistema operativo causan diferencias en el modo en que se notifican los datos del dispositivo.

##### <a name="remediation"></a>Corrección

Por lo general, tendrá que descubrir y salir de los dispositivos no certificados y reemplazarlos con dispositivos certificados. Algunas consideraciones al revisar los informes de dispositivos incluyen:

-   ¿Los dispositivos están en uso certificados para Teams y Skype empresarial? 
-   Puede identificar los usuarios de un dispositivo específico mediante [análisis de llamadas por usuario](use-call-analytics-to-troubleshoot-poor-call-quality.md). Asegúrate de que tengan los drivers más recientes del dispositivo y de que el dispositivo no esté conectado a través de un concentrador USB o una estación de acoplamiento. 
-   ¿Cuántas versiones diferentes de varios drivers están en uso? ¿Se les revisan regularmente? Asegurarse de que los drivers de audio, vídeo y Wi-Fi se revisan regularmente le ayudarán a eliminarlos como fuente de problemas de calidad y hacer que la experiencia del usuario sea más predecible y coherente.

##### <a name="audio"></a>Audio

La siguiente tarea es determinar el uso general de los [dispositivos de audio certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Recomendamos que al menos 80 por ciento de todas las transmisiones de audio usen un dispositivo de audio certificado. Para ello, se recomienda exportar el informe de dispositivos de micrófono a Excel para calcular el uso de los dispositivos certificados o aprobados. Normalmente, las organizaciones conservan una lista de todos los dispositivos aprobados, por lo que filtrar y ordenar los datos debería ser sencillo.

##### <a name="video"></a>Vídeo

Los drivers de video son importantes para mantenerte actualizado. Asegurarse de que las tarjetas de vídeo se revisan regularmente le ayudará a excluir los drivers de video como fuente de baja calidad para las transmisiones de video. El uso de [dispositivos de video certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) le ayudará a garantizar una experiencia de usuario fluida y de alta calidad. Se prefieren los dispositivos de vídeo que admiten la codificación nativa H. 264, para reducir el uso de la CPU durante las videoconferencias.

##### <a name="wi-fi"></a>Wi-Fi

Además, los drivers Wi-Fi también necesitan parches de forma regular y deben incluirse en la estrategia de administración de revisiones. Muchos problemas de calidad pueden corregirse manteniendo los drivers Wi-Fi actualizados. Para obtener más información sobre cómo optimizar su infraestructura Wi-Fi, consulte [este artículo sobre la planificación de Wi-Fi](/skypeforbusiness/certification/networking-wifi).


## <a name="related-topics"></a>Temas relacionados

[Usar asesor para equipos](use-advisor-teams-roll-out.md)

[Preparar la red para Teams](prepare-network.md)

[Principios de conectividad de red de Office 365](https://aka.ms/pnc)

[Análisis e informes de Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Administrar los dispositivos en Teams](device-management.md)

[Mejorar y supervisar la calidad de las llamadas de los equipos](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar inquilino y datos de compilación](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de flujo en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar los datos del CQD](CQD-Power-BI-query-templates.md)

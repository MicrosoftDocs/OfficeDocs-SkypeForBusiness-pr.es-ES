---
title: Guía de revisión de la experiencia de calidad de Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Guía para analizar el rendimiento de los medios en tiempo real para Microsoft Teams mediante el panel de calidad de llamadas (CQD).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91a4cda0cb7f16363f3fa90deb0358bf5600330a
ms.sourcegitcommit: 43a17ce6fea3951719b55bfbda03c500cef4816c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41580907"
---
# <a name="quality-of-experience-review-guide"></a>Guía de revisión de la experiencia de calidad

<!-- Note that this link to the Word doc is intentionally NOT the aka.ms/qerquide link -->
Esta guía trata sobre la fase de valor de unidad para Microsoft Teams y Skype empresarial online. Puede [descargar una versión de Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) de esta guía.

## <a name="introduction"></a>Introducción

Para tener el mayor impacto en la mejora de la experiencia del usuario, las organizaciones necesitan el funcionamiento de las áreas clave que se muestran en la siguiente ilustración. Entre las áreas adicionales se incluyen la identificación de tareas operativas, el establecimiento de objetivos de métrica de calidad, la determinación de las métricas que se usarán para medir el éxito organizacional y la reducción de las áreas de investigación según sea necesario.


![Áreas clave para la calidad de la experiencia de usuario](media/qerguide-image-keyareas.png "Las áreas clave para la calidad de la experiencia de usuario incluyen el audio, la confiabilidad, las encuestas de usuarios, los dispositivos y los clientes.")

_Figura 1: áreas de funcionamiento clave cubiertas en esta guía_

Al evaluar y corregir continuamente las áreas descritas en esta guía, puede reducir su potencial de afectar negativamente a la calidad de la experiencia de los usuarios. La mayoría de problemas que se encuentran en la experiencia de usuario de una implementación se pueden agrupar en las siguientes categorías:

-   Una configuración de proxy o firewall incompleta
-   Una cobertura Wi-Fi insuficiente
-   Un ancho de banda insuficiente
-   VPN
-   Versiones y drivers de cliente incoherentes o anticuados
-   Dispositivos de audio integrados o no optimizados
-   Dispositivos de red o subred problemáticos

A través de una planificación y un diseño adecuados antes de implementar Teams o Skype empresarial online, puede reducir la cantidad de esfuerzo que se necesitará para mantener experiencias de alta calidad.

Esta guía se centra en usar el panel de calidad de llamadas (CQD) en línea como la herramienta principal para denunciar e investigar cada área, con un énfasis especial en el audio para maximizar la adopción y el impacto. Cualquier mejora hecha en la red para mejorar la experiencia de audio también se traducirá directamente a mejoras en el uso compartido de vídeo y escritorio.

Para acelerar su evaluación, se proporcionan [dos plantillas de CQD de protegida](https://aka.ms/qertemplates) : una es para administrar todas las redes y la otra se filtra solo para las redes administradas (internas). Aunque los informes de plantillas All Networks están configurados para mostrar la información de compilación y de red, aún se pueden usar mientras trabaja para recopilar y cargar información de compilación. Cargar información de compilación en CQD permite al servicio mejorar los informes agregando la creación, la red y la información de ubicación personalizados mientras se diferencian entre las subredes externas. Para obtener más información, consulte [creación de asignaciones](#building-mapping) más adelante en esta guía.

### <a name="intended-audience"></a>Audiencia prevista

Esta guía está pensada para su uso por parte de las partes interesadas del cliente y del socio, como responsable de la colaboración, arquitecto, consultor, especialista en administración/adopción de cambios, responsable de soporte/asistencia, cable de red, responsable de escritorio y administrador de ti.

Esta guía también está pensada para ser usada por el preparador de calidad designado (s). Para obtener más información, consulte [el rol de calidad de experto](4-envision-plan-my-service-management.md#the-quality-champion-role).

## <a name="assign-roles-for-accessing-cqd"></a>Asignar roles para acceder al CQD

Antes de usar esta guía, asegúrese de tener asignados los [roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) de inquilino adecuados para poder obtener acceso al CQD.

En esta tabla se muestra lo que cada rol puede hacer en el CQD:


|  |Ver informes  |Ver campos de EUII  |Crear informes  |Cargar datos de compilación  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador global de Office 365     |Sí          |Sí          |Sí          |Sí          |
|Administrador de servicios de Teams     |Sí          |Sí          |Sí          |Sí          |
|Administrador de comunicaciones de Teams     |Sí          |Sí          |Sí          |Sí          |
|Ingeniero de soporte en comunicaciones de Teams     |Sí          |Sí          |Sí         |No         |
|Especialista de soporte técnico de comunicaciones de Teams     |Sí         |No         |Sí         |No         |
|Administrador de Skype empresarial     |Sí          |Sí          |Sí          |Sí          |
|Lector global de Azure AD |Sí          |Sí          |Sí         |No         |
|Lector de informes de Office 365<sup>1</sup>     |Sí         |No         |Sí         |No         |

<sup>1</sup> además de leer los informes de CQD, el lector de informes de Office 365 puede ver todos los [informes de actividades](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración y los informes del paquete de contenido de [adopción de Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Si no ve EUII (información identificable por el usuario final) y tiene una de las funciones que pueden ver esta información, tenga en cuenta que el CQD solo mantiene el EUII por 30 días. Se eliminarán los que tengan más de 30 días.

## <a name="what-is-quality"></a>¿Qué es la calidad?

Al discutir la calidad en Teams y Skype empresarial, es importante definir el término para lograr una comprensión común. La calidad, tal como se define aquí, es una combinación de las métricas de servicio y la experiencia del usuario.

<!-- Note: need to update graphic-->
![Ilustración de las métricas de servicio y la experiencia de usuario](media/qerguide-image-whatisquality.png "Las métricas de servicio se componen de mala velocidad de transmisión, fiabilidad, puntos de conexión, dispositivos y versiones de cliente. La experiencia de usuario consta de la percepción del usuario de la calidad del servicio.")

_Ilustración 2: ¿Qué es la calidad?_

### <a name="service-metrics"></a>Métricas de servicio

Las métricas de servicio se componen de métricas específicas basadas en el cliente. Durante cada llamada, el cliente recopila información de telemetría sobre la llamada y envía un informe al final de cada llamada al que se puede obtener acceso más adelante mediante el análisis del CQD o de [llamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Estas métricas incluyen:

-   Mala velocidad de transmisión
-   Tasa de error de configuración
-   Tasa de errores de caída


#### <a name="poor-stream-rate"></a>Mala velocidad de transmisión

La mala tarifa de transmisión por secuencias (PSR) representa el porcentaje general de las transmisiones de baja calidad de la organización. Este sistema métrico resalta las áreas en las que su organización puede concentrar el esfuerzo para tener el mayor impacto en la reducción de este valor y en la mejora de la experiencia del usuario, razón por la cual las [redes administradas](#managed-vs-unmanaged-networks) son el principal enfoque al mirar a PSR. Los usuarios externos también son importantes, pero la investigación difiere en cada organización. Considere la posibilidad de proporcionar procedimientos recomendados para usuarios externos e investigue las llamadas externas independientemente de la organización general.

La medición real del CQD varía según la carga de trabajo, pero a los fines de la revisión de la experiencia de calidad nos centramos principalmente en la medición del _porcentaje de audio deficiente_ . PSR consta de los cinco promedio métricos de red que se describen en la tabla siguiente. Para que una secuencia se clasifique como mala, solo una métrica debe superar el umbral definido. Para obtener más información sobre el proceso de clasificación de secuencias, consulte [este artículo](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> El CQD proporciona el "mala debido a..." medidas para comprender mejor qué condición causó que la secuencia se clasifique como mala.


_Tabla 1: métricas de baja calidad de audio_

| Promedio de la métrica     | Descripción     | Experiencia de usuario |
|-------------|-----------------|-----------------|
| Vibración \>30 ms        | Este es el cambio medio en el retraso entre paquetes sucesivos. Los equipos y Skype empresarial pueden adaptarse a algunos niveles de vibración a través del almacenamiento en búfer. Solo cuando la vibración supera el búfer que un participante advierte de los efectos de la vibración.      | Los paquetes que llegan a velocidades diferentes hacen que la voz del orador suene robótica.   |
| Porcentaje \>de pérdida de paquetes 10% o 0,1        | Esto se suele definir como un porcentaje de paquetes que se pierden. La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individuales que apenas tienen impacto en las pérdidas de ráfagas en el fondo que hacen que el audio se recorte por completo.     | Los paquetes que se descartan y que no llegan a su destino, causan lagunas en los medios, lo que da lugar a sílabas y palabras perdidas, así como vídeo y uso compartido entrecortado. |
| Tiempo \>de ida y vuelta 500 ms        | Este es el tiempo que se tarda en obtener un paquete IP desde el punto a al punto B y volver al punto a. Este retraso de propagación de red está vinculado a la distancia física entre los dos puntos y la velocidad de luz, e incluye una sobrecarga adicional realizada por los distintos dispositivos en la ruta de acceso a la red.      | Los paquetes que tardan demasiado tiempo en llegar a su destino causan un efecto de walkie-talkie.   |
| Degradación de NMOS \>promedio 1,0         | Degradación media de [opinión de media de red (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) de la transmisión. Representa el grado en que la pérdida y la vibración de la red han afectado a la calidad del audio recibido que causó que el método NMOS se colocara en más de un punto. | Esta es una combinación de vibración, pérdida de paquetes y, a menor grado, aumentos en el tiempo de ida y vuelta. Es posible que el usuario esté experimentando una combinación de estos síntomas.   |
| Relación media entre el 7% \>o 0,07 de las muestras ocultas | Relación media entre el número de marcos de audio con muestras ocultas generada por la recuperación de pérdida de paquetes para el número total de marcos de audio. Una muestra de audio oculta es una técnica usada para suavizar la transición abrupta, que normalmente se producía por paquetes de red perdidos.      | Los valores altos indican que se aplicaron niveles significativos de ocultación de pérdida y dieron como resultado una distorsión o pérdida de audio.     |

#### <a name="setup-failure-rate"></a>Tasa de error de configuración

La tasa de error de configuración, que también se conoce como la medición del _porcentaje total de errores de configuración de llamadas_ en el CQD, es el número de transmisiones en las que no se pudo establecer la ruta de acceso a medios entre los puntos de conexión al inicio de la llamada.

Esto representa cualquier flujo de medios que no se pudo establecer. Dada la gravedad del impacto en la experiencia del usuario que se mide aquí, el objetivo es reducir este valor a cero como sea posible. Un valor elevado para esta métrica es más común en nuevas implementaciones con reglas de Firewall incompletas que una implementación madura, pero sigue siendo importante vigilar de forma periódica.

Esta métrica se calcula al tomar el número total de transmisiones que no se pudieron configurar divididas por el número total de transmisiones que enviaron un registro de detalles de la llamada (CDR) correctamente:

-   **Tasa de errores de configuración** = error en la configuración de la llamada total de streams, número total de streams disponibles de CDR

#### <a name="drop-failure-rate"></a>Tasa de errores de caída

La tasa de error de caída, que también se conoce como la medida de _porcentaje total de llamadas perdidas_ en el CQD, es el porcentaje de transmisiones correctamente que la ruta de acceso a los medios no finalizó con normalidad.

Esto representa cualquier flujo de medios que haya finalizado de forma inesperada. Aunque el impacto de esto no es tan grave como un flujo que no se pudo configurar, afectará negativamente a la experiencia del usuario. Los medios repentinos y repentinos no solo pueden tener un impacto grave en la experiencia del usuario, ya que hacen que los usuarios tengan que volver a conectarse, lo que produce una pérdida de productividad.

La métrica se calcula aprovechando el número total de flujos colocados dividido por el recuento total de transmisiones que se han configurado correctamente:

-   **Tasa de errores de caída** = número total de flujos de llamadas interrumpidas/total de llamadas correctas

### <a name="define-your-target-metrics"></a>Definir las métricas de destino

En esta sección se describen algunas de las métricas de servicio básicas que usamos para evaluar el estado de la experiencia de los servicios. Al evaluar y promover los esfuerzos para mantener estas métricas a partir de los destinos definidos, te ayudará a garantizar que tus usuarios disfruten de una calidad de llamada coherente y fiable. Para empezar, se proporcionan los siguientes destinos.

_Tabla 2: métricas básicas de evaluación de la salud de destino_
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


Es importante analizar y definir los objetivos de su organización para cumplir con los objetivos de su negocio.

### <a name="user-experience"></a>Experiencia de usuario

Analizar la experiencia del usuario es más arte que la ciencia, ya que las métricas que se recopilan aquí no siempre significan que hay un problema con la red o el servicio, sino que simplemente indican que el usuario percibe un problema. Microsoft ofrece un mecanismo de encuesta integrado, conocido como calificar mi llamada (RMC), para ayudar a medir la experiencia general del usuario. RMC le ayudará a contestar las siguientes preguntas desde la perspectiva de sus usuarios:

-   ¿Sé cómo usar la solución?
-   ¿La solución es fácil de usar e intuitiva, y es compatible con mis necesidades de comunicación cotidianas?
-   ¿Me puede ayudar la solución a hacer mi trabajo?
-   ¿Cuál es la percepción general de la solución?
-   ¿Puedo usar la solución en cualquier momento, independientemente de dónde soy?
-   ¿Puedo configurar y mantener una llamada?

#### <a name="rate-my-call"></a>Calificar mi llamada 

Calificar mi llamada (RMC) está integrada en Teams y Skype empresarial, y se configura automáticamente para que se muestre al participante después de una o un 10 por ciento. Esta breve encuesta le pide al usuario que clasifique la llamada y proporciona un poco de contexto por el que es posible que la calidad de la llamada sea deficiente. Una o dos calificaciones se consideran deficientes, tres a cuatro es buena y cinco es excelente. Aunque es algo de un indicador atrasado, esta es una métrica útil para descubrir problemas que las métricas de servicio pueden perder.

> [!Note]
> Hasta que los usuarios sean educados para responder a las encuestas de RMC, además de la mala respuesta, normalmente volverán a ser muy negativas. La mayoría de los usuarios solo responde cuando la calidad de la llamada es mala. Por este motivo, los informes de RMC podrían ser sesgados en el lado deficiente, incluso cuando los indicadores de servicio son buenos.

Puede usar el CQD para denunciar las respuestas de los usuarios de RMC y los informes de muestra se incluyen en la plantilla de CQD. Sin embargo, no se tratan en detalle en esta guía. Para obtener más información sobre RMC en Skype empresarial online y orientación para educar a los usuarios para que proporcionen respuestas de RMC útiles, consulte [esta entrada de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

#### <a name="client-and-device-readiness"></a>Preparación de dispositivos y clientes

Para ayudar a que los usuarios tengan una experiencia de usuario coherente y positiva, necesita una estrategia de cliente y dispositivo sólida. Algunos principios clave impulsan cada estrategia de preparación.

##### <a name="client-readiness"></a>Preparación del cliente

Una sólida estrategia de preparación de clientes garantiza que los usuarios estén ejecutando la versión más reciente del cliente y disfruten de la mejor experiencia posible. Microsoft revisa regularmente el cliente de Skype empresarial; asegurarte de mantenerlo actualizado en tu entorno es vital para tu éxito general. También es importante recordar la corrección de los drivers de red, vídeo, USB y audio, ya que a menudo se les suele pasar por más y pueden afectar a la experiencia del usuario. Considere la posibilidad de agregar controladores de red, Wi-Fi, vídeo, USB y audio a su proceso de administración de revisiones actual.

Le recomendamos que no permita que las versiones de su cliente caigan en más de seis meses. Si está usando hacer clic y ejecutar de Office, el servicio ya se está actualizando. Use las [versiones de cliente](#client-versions)incluidas, según se describe más adelante en esta guía, para ayudarle en este proceso. También puedes aprovechar la tarifa de mis informes de muestra de llamadas para mejorar aún más la estrategia de preparación de los clientes.

> [!IMPORTANT]
> Actualmente, los clientes de equipos se distribuyen y actualizan automáticamente a través de la red de entrega de contenido de Azure y el servicio lo mantendrá actualizado. Por ello, las actividades de preparación de clientes y de investigación no son aplicables a los equipos.


##### <a name="device-readiness"></a>Preparación del dispositivo

Una sola estrategia puede afectar a la experiencia del usuario más que la estrategia de preparación de dispositivos. La mayoría de las organizaciones se alegran de quitar los dispositivos que no son necesarios (por ejemplo, teléfonos de escritorio u otros dispositivos de audio dedicados), y esto suele ser una justificación empresarial básica para cambiar a equipos o a Skype empresarial. Sin embargo, a veces esas mismas organizaciones dudan en proporcionar dispositivos de sustitución, incluso si esos dispositivos son menos caros. Los equipos portátiles y equipos modernos, aunque equipados con micrófono y altavoz incorporados, no están optimizados para la voz sobre IP (VoIP) de clase empresarial. Esto a menudo crea una mala experiencia para todos los participantes, especialmente si el orador está en un entorno ruidoso. El programa de certificación de dispositivos de Microsoft garantiza que cuando un usuario participe en una llamada telefónica usando cualquier dispositivo certificado para equipos o Skype empresarial, genera una experiencia que es superior a un dispositivo no certificado. 

Siempre recomendamos que los usuarios de Skype y Skype empresarial usen auriculares con micrófono o un altavoz certificado cuando participen en una llamada de voz a través del cliente de escritorio. Para obtener más información acerca de los dispositivos certificados por Microsoft, revise estos artículos sobre el [programa de certificación](/SkypeForBusiness/certification/overview) y vea el [Catálogo de soluciones para socios](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Use el [Informe dispositivos](#devices), que se describe más adelante en esta guía, para obtener ayuda con la administración de los dispositivos.


### <a name="categories-of-quality"></a>Categorías de calidad

El éxito de la operación de implementar una implementación de alta calidad y confiable depende de la eficacia operativa de tu edificio. Específicamente, preste especial atención a las tres categorías que se muestran en la siguiente ilustración; Este es el foco de esta guía:

-   **Red:** Calidad de audio centrada en la métrica de la relación de flujo deficiente (PSR), el uso de TCP, las subredes con cable e inalámbricas y la identificación del uso de proxy HTTP y VPN.

-   **Puntos de conexión:** Dispositivos de audio y versiones de cliente (solo para Skype empresarial).

-   **Administración de servicios:** Esta categoría comprende dos secciones:

    -   En primer lugar, es responsabilidad de Microsoft administrar y mantener los equipos y los servicios de Skype empresarial online.

    -   El segundo son las tareas que su organización debe administrar para garantizar un acceso confiable al servicio, como la actualización de la información de generación y el mantenimiento de los firewalls para las nuevas direcciones IP de Office 365, a medida que se agrega una infraestructura al servicio.

![Gráfico de las categorías de calidad en una organización](media/qerguide-image-categories.png "Las categorías de calidad de una organización: administración de servicios, puntos de conexión y la red.")

_Figura 3: categorías críticas para la implementación de Teams y Skype empresarial online_

En el siguiente gráfico se describen las tareas que debe ejecutar para cada categoría. Le recomendamos que ejecute estas tareas una vez por semana, como mínimo.

La primera vez que realice estas tareas, tendrá más esfuerzo que las iteraciones posteriores, porque muchas de estas categorías requieren que valide las configuraciones de implementación. Una vez que haya conseguido el estado que desea al cumplir los objetivos que ha definido, estas tareas le ayudarán a mantener ese estado.

<!--  This is a net new graphic, never was included in the online article. OOPS! -->
![Lista de tareas semanales por categoría de calidad](media/qerguide-image-tasks.png "Lista de tareas semanales por categoría de calidad")

#### <a name="service-management-tasks"></a>Tareas de administración de servicios

En una nube-primer mundo, debe realizar ciertas tareas de administración de servicios para mantener experiencias de usuario de alta calidad. Estas tareas van desde asegurar que hay suficiente ancho de banda para alcanzar el servicio sin saturar los vínculos de Internet, validar que la calidad de servicio (QoS) esté en su lugar en todas las áreas de red administradas y, por último, mantenerse en la parte superior de los [intervalos de IP de Office 365 en los firewalls](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Tareas de red

Existen dos categorías de tareas de red: fiabilidad y calidad. La confiabilidad se centra en medir la capacidad del usuario para hacer llamadas correctamente y permanecer conectada. La calidad se centra en la telemetría agregada que se envía a teams y Skype empresarial online por el cliente del usuario durante la llamada y después de que haya finalizado. 

Dado el impacto crítico que la confiabilidad tiene en la experiencia del usuario, es importante comenzar a evaluar y investigar esas métricas antes de profundizar en la calidad. 

#### <a name="endpoints-tasks"></a>Tareas de puntos finales

La tarea principal de esta categoría es la validación de las versiones de cliente que ejecutan Skype empresarial en las compilaciones de escritorio de los últimos seis meses, para garantizar que los usuarios obtienen la ventaja de las optimizaciones continuas realizadas en el cliente de escritorio de Skype empresarial. Además, esto simplifica las tareas generales de administración de clientes y proporciona una experiencia de usuario coherente.

El otro área importante es supervisar qué dispositivos son predominantes en su implementación y impulsar el uso de dispositivos certificados para proporcionar la mejor experiencia para el usuario.


> [!IMPORTANT]
> Actualmente, los clientes de equipos se distribuyen y actualizan automáticamente a través de la red de entrega de contenido de Azure y el servicio lo mantendrá actualizado. La preparación de los clientes y las actividades de investigación no son aplicables a los equipos.

## <a name="cqd-basics"></a>Conceptos básicos del CQD

En esta sección se describen los conceptos básicos del trabajo con el CQD. Se proporcionan directrices para los temas siguientes:

-   ¿Qué es el CQD?
-   Expectativas con el CQD
-   Buscar el identificador de inquilino
-   Informes sobre Microsoft Teams frente a Skype empresarial
-   Comparación entre la segunda y la segunda
-   Dimensiones, medidas y filtros
-   Llamadas en comparación con llamadas
-   Llamadas no clasificadas, muy pobres y buenas
-   Subredes comunes

Para obtener recursos y aprendizajes más detallados, consulte el [Apéndice](#other-resources).

### <a name="what-is-cqd"></a>¿Qué es el CQD?

El panel de calidad de llamadas (CQD) se usa para obtener información sobre la calidad de las llamadas realizadas mediante el uso de Teams y los servicios de Skype empresarial. El CQD está diseñado para ayudar a los administradores y ingenieros de redes de Skype empresarial y a optimizar la red y mantener un vistazo a la calidad, la confiabilidad y la experiencia del usuario. El CQD examina el encargado de la telemetría de una organización en la que se pueden aparentar patrones generales, lo que permite que el personal realice evaluaciones con conocimiento y planifique actividades de corrección para maximizar el impacto. El CQD proporciona informes de métricas que proporcionan una perspectiva de la calidad general, la confiabilidad y la experiencia del usuario.

Esta guía le ayudará a comprender los conceptos básicos del CQD para ayudar a maximizar el impacto que puede tomar para mejorar la experiencia de los usuarios con Teams o Skype empresarial online. Encontrará más recursos del CQD en el [Apéndice](#other-resources).

### <a name="expectations-using-cqd"></a>Expectativas con el CQD

El CQD, aunque es útil para analizar tendencias y subredes, no siempre proporciona una causa específica para un escenario determinado. Es importante comprender esto y establecer la expectativa correcta al usar el CQD:

-   El CQD no proporcionará la causa de origen para todos los escenarios.
-   El CQD no contendrá secuencias de audio o de sistema telefónico.
-   El CQD llamará a las áreas para una mayor investigación según las tendencias.

### <a name="report-editions"></a>Ediciones de informes

Hay dos ediciones de informes en el CQD online: Resumen y detalles. Use el menú desplegable que se encuentra en la barra de la parte superior de la pantalla para abrir una edición de informe. El nombre de la edición de informes seleccionada se muestra en la parte superior de la pantalla.

-   Los informes de resumen son estáticos y no se pueden editar, descargar o exportar. 
-   Los informes detallados son totalmente personalizables y se pueden descargar en un archivo CSV, exportar o duplicar.

Para obtener una descripción completa de la diferencia entre las dos ediciones, consulte [este artículo](turning-on-and-using-call-quality-dashboard.md).

Novedades de enero de 2020: [Descargue las plantillas de consulta de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD Power BI query templates.zip?raw=true). Plantillas de Power BI personalizables que puede usar para analizar y notificar los datos de CQD.

_Figura 4: categorías de informes de CQD_

Los informes de resumen se dividen en cuatro categorías:

-   Los **informes de Resumen** se centran en analizar tendencias de calidad con informes diarios, mensuales y de tabla para ayudar a identificar subredes que tengan una mala calidad. Esta es la página de aterrizaje predeterminada la primera vez que inicias sesión en el CQD online.
-   Los **informes de ubicación mejorada** se centran en analizar tendencias de calidad según la información de ubicación. Para usar estos informes, debe haber cargado un archivo de creación.
-   Los **informes de confiabilidad** se centran en analizar tendencias de confiabilidad para el uso compartido de pantalla basado en vídeo, vídeo y audio (VBSS) y aplicaciones compartidas.
-   Los informes sobre la **calidad de la experiencia** son una versión de "Slimmed" de las plantillas detalladas de QER, centrándose en las áreas clave para analizar la calidad de audio y la fiabilidad.

### <a name="report-types"></a>Tipos de informes

Puede elegir entre dos tipos de informes en el CQD, en función de cómo desee ver los datos. Aunque esta guía no cubre las características específicas de la creación de un tipo de informe en lugar de otra, las plantillas de CQD de QER proporcionan una combinación de informes de tablas y gráficos personalizables para que los use:

-   Informes de gráficos cree gráficos de barras gráficas para representar datos en un formato visual. Los informes de gráficos son idóneos para visualizar datos en un período de tiempo determinado.
-   Los informes de tabla son útiles para mirar medidas y dimensiones individuales al exportar los informes a archivos CSV para su manipulación en Microsoft Excel.

### <a name="tenant-id"></a>IDENTIFICADOR de inquilino

Algunos informes de CQD requieren que incluya un filtro para su identificador de inquilino. Debido a la forma en que el CQD agrega datos, se incluye telemetría de participantes federados. Aunque esto puede ser de gran valor al analizar tendencias, los informes de clientes y dispositivos requieren que filtre los datos a un inquilino específico para excluir la telemetría de participantes federados. Si no conoce su identificador de inquilino, puede usar uno de los siguientes métodos para encontrarlo.

> [!Note]
> Estos métodos requieren los siguientes permisos:<ul><li>Función de administrador global</li><li>Rol de administrador de Skype empresarial</li></ul>

#### <a name="azure-portal"></a>Portal de Azure

1.  Inicie sesión en el portal de Microsoft Azure:<https://portal.azure.com>

2.  Seleccione **Azure Active Directory**.

3.  En **administrar**, seleccione **propiedades**. El identificador de inquilino se muestra en el cuadro **identificador de directorio** .

#### <a name="azure-powershell"></a>Azure PowerShell

1. [Instale el módulo de administración del servicio Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2. Abra una ventana de comandos de Azure PowerShell y ejecute el siguiente script, especificando sus credenciales de 365 de Office cuando se le solicite: 

   ```PowerShell
   Login-AzureRmAccount
   ```

3. El identificador de inquilino se muestra en la salida.

#### <a name="skype-for-business-online-admin-center"></a>Centro de administración de Skype empresarial online

1.  Vaya a <https://portal.office.com>.

2.  Inicie sesión con su cuenta de la organización de administrador de inquilinos.

3.  Seleccione **Skype empresarial** en **centros de administración**.

4.  El identificador de inquilino se muestra como identificador de la **organización** en la Página principal.

#### <a name="skype-for-business-online-using-powershell"></a>Skype empresarial online con PowerShell

1. [Configure su equipo para Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Ejecute el siguiente comando:

   ```PowerShell
   (Get-cstenant).tenantid
   ```

3. El identificador de inquilino se muestra como un GUID.

### <a name="teams-vs-skype-for-business"></a>Teams frente a Skype empresarial

El CQD puede denunciar tanto los equipos como la telemetría de Skype empresarial. Sin embargo, puede haber ocasiones en las que desee desarrollar un informe para ver la telemetría de Teams independiente de Skype empresarial.

#### <a name="summary-reports"></a>Informes de Resumen

Para modificar la página informes de resumen para ver solo equipos o Skype empresarial, seleccione el menú desplegable **filtro de producto** en la parte superior de la pantalla y, a continuación, seleccione el producto que quiera.

![Captura de pantalla del menú desplegable que muestra las opciones de filtro](media/qerguide-image-productfilter.png)

_Figura 5: seleccionar un filtro de producto_

#### <a name="detailed-reports"></a>Informes detallados

Para filtrar todos los informes detallados, en la barra del explorador, agregue lo siguiente al final de la dirección URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Ejemplo**

```https://cqd.lync.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obtener más información sobre los filtros de URL, consulte [filtrar informes](#filtering-reports) más adelante en esta sección.

Para filtrar un informe detallado individual, agregue el ``Is Teams`` filtro al informe y establézcalo en verdadero o falso. Para obtener más información, consulte [editar informes](#editing-reports) más adelante en esta sección.

![Captura de pantalla de la página Agregar filtro](media/qerguide-image-addteamsfilter.png)

_Figura 6: agregar un filtro de Microsoft Teams a un informe_


### <a name="managed-vs-unmanaged-networks"></a>Redes administradas frente a redes no administradas

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

-   **Bueno o malo:** Una buena o mala llamada consiste en una llamada que contiene un conjunto completo de parámetros de servicio, para los que el servicio ha generado y recibido un informe de QoE de calidad completo. La determinación de si una secuencia es buena o mala se describe [anteriormente en esta guía](#poor-stream-rate).

-   Sin **clasificar:** Una transmisión sin clasificar no contiene un conjunto completo de métricas de servicio. Pueden ser llamadas breves, generalmente de menos de 60 segundos, donde los promedios no se han calculado y no se ha generado un informe de QoE. La razón más común para que las llamadas sean no clasificadas es que no haya ninguna utilización de paquetes. Un ejemplo de esto sería un participante que se une a una reunión al silenciar y nunca habla. El participante recibe, pero no transmite, los medios. Sin transmitir los medios, no habrá ninguna métrica disponible para que el CQD los use para clasificar la secuencia multimedia saliente del punto de conexión.

Para obtener más información sobre el proceso de clasificación de secuencias, consulte [este artículo](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Subredes comunes

Las subredes comunes son subredes privadas específicas que se usan en hoteles, redes domésticas, puntos de acceso público y áreas similares. Estas subredes son difíciles de clasificar debido a su uso generalizado. Si su organización usa una de estas subredes comunes, le recomendamos que mueva esa red a otra subred. Esto facilitará los informes en el CQD. Cuando se indica, los informes de la plantilla todas las redes se han configurado para excluir estas subredes para eliminarlas como fuente de baja calidad. Las subredes comunes se definen a continuación; su impacto variará según la organización.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Al investigar una red administrada que usa una subred común, tendrá que usar la segunda dimensión IP local reflexiva para agrupar subredes. Esta dimensión contiene la dirección IP pública del punto de conexión.

## <a name="cqd-online"></a>CQD online

En esta sección se describen los conceptos básicos del acceso al CQD. Se proporcionan directrices para los temas siguientes:

-   Acceso a CQD online
-   Introducción al CQD
-   Editar informes en el CQD
-   Filtrar informes en el CQD
-   Importar informes en el CQD

Para obtener recursos y aprendizajes más detallados, consulte el [Apéndice](#other-resources).

### <a name="access-cqd-online"></a>Acceder al CQD en línea

Puede obtener acceso al CQD de tres maneras:

-   Vaya a <https://cqd.lync.com>.

-   Vaya al **centro de administración de Microsoft Teams** y seleccione el vínculo al CQD, como se muestra en la siguiente ilustración.

![Captura de pantalla del panel de calidad de llamadas seleccionado.](media/qerguide-image-mopo.png "En el panel de navegación izquierdo, está seleccionado el vínculo a panel de calidad de llamadas.")

_Figura 7: acceso al CQD a través del centro de administración de Microsoft Teams_

-   Vaya a las > **herramientas**del **centro de administración de Skype empresarial**heredado y seleccione el vínculo al CQD, como se muestra en la siguiente ilustración.

![Captura de pantalla del CQD seleccionado en el panel principal.](media/qerguide-image-legacyui.png "Herramientas está seleccionada en el panel de navegación izquierdo y el vínculo a CQD está seleccionado en el panel principal.")

_Figura 8: acceso al CQD a través del centro de administración de Skype empresarial_


### <a name="getting-started"></a>Introducción

La primera vez que vaya al CQD, verá la página informes de resumen. La mayoría de los informes descritos en esta guía son informes detallados personalizados. Para empezar a usar los informes detallados, seleccione **informes de Resumen** en la parte superior de la página y, a continuación, elija **informes detallados**.

![Captura de pantalla que muestra los tipos de informes disponibles en el CQD](media/qerguide-image-choosereports.png)

_Ilustración 9: desplazarse a informes detallados_

La página informes detallados del CQD es similar a la siguiente ilustración.

![captura de pantalla que ilustra elementos que conforman un informe detallado](media/qerguide-image-detailedreportspage.png)

|             |           |
| ------------|-----------|
| ![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/qerguide-image-callout1.png "una") | El panel Resumen muestra el contexto del conjunto de informes que aparece a la derecha. |
| ![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/qerguide-image-callout2.png "segunda") | Puede seleccionar **Editar** en el panel Resumen para establecer las propiedades de nivel de informe (incluyendo el alto eje y) y para importar nuevas plantillas. |
| ![Icono del número 3, que hace referencia a una llamada en la captura de pantalla anterior](media/qerguide-image-callout3.png "tres") | La ruta de navegación ayuda a los usuarios a identificar su ubicación actual en la jerarquía del conjunto de informes. |
| ![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior](media/qerguide-image-callout4.png "cinco") | Los informes que contienen informes secundarios se muestran con un vínculo azul. Al seleccionar el vínculo, puede desglosar los informes secundarios. |

_Figura 10: Página informes detallados_

Seleccione gráficos de barras y líneas de tendencia en el informe para mostrar valores detallados. El informe que tiene el foco mostrará el menú de acciones: **Editar**, **clonar**, **eliminar**, **Descargar**y **exportar árbol de informes**.

### <a name="editing-reports"></a>Editar informes

Al seleccionar **Editar** en el menú de acciones de un informe, abrirá el editor de consultas. Cada informe está respaldado por una consulta al CQD. Un informe es una visualización de los datos devueltos por su consulta. El editor de consultas es una interfaz de usuario para editar estas consultas, además de las opciones de presentación del informe, como se muestra en la siguiente ilustración.

![Captura de pantalla que ilustra elementos que conforman un informe que se está editando.](media/qerguide-image-queryeditor.png)

|             |           |
| ------------|-----------|
| ![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/qerguide-image-callout1.png "una") | Puede elegir dimensiones, medidas y filtros en el panel izquierdo. Si se apunta a un valor existente, se muestra un botón de cierre (**X**) que puede seleccionar para quitar el valor.<ul><li>Al seleccionar la dimensión o la medida, puede cambiar el título modificando el campo **título** . También puede cambiar el orden seleccionando las flechas hacia arriba o hacia abajo de color azul en el panel superior.</li><li>Si selecciona**+**() junto a un encabezado, se abre el cuadro de diálogo para agregar una nueva dimensión, medida o filtro.</li><li>Escriba las primeras letras de la dimensión, medida o filtro en el campo **Buscar un** campo para filtrar la lista para facilitar la búsqueda.</li></ul> |
| ![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/qerguide-image-callout2.png "segunda") | En el panel superior se muestran las opciones de personalización de gráficos. |
| ![Icono del número 3, que hace referencia a una llamada en la captura de pantalla anterior](media/qerguide-image-callout3.png "tres") | El editor de consultas muestra una vista previa del informe. |
| ![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior](media/qerguide-image-callout4.png "cinco") | Use el cuadro de **edición** de la parte inferior de la pantalla para crear o editar una descripción detallada del informe. |

_Figura 11: editor de consultas_

### <a name="filtering-reports"></a>Filtrar informes

Las plantillas proporcionadas incluyen varias consultas integradas y filtros de informe. En las siguientes secciones se describen los filtros más comunes que se usan en las plantillas.

#### <a name="url-filter"></a>Filtro de dirección URL

Puede usar un filtro de URL para filtrar cada informe para una dimensión específica. Los filtros de URL más comunes se usan para filtrar los informes para excluir la telemetría de participantes federados o centrarse en Teams o Skype empresarial online. Le recomendamos que, al usar los filtros, los marcadores se marquen para facilitar la referencia. 

La exclusión de datos federados de informes de CQD es útil cuando se corrigen edificios administrados o redes en las que los puntos de conexión federados pueden influir en los informes.

Para implementar un filtro de URL, en la barra de direcciones del explorador, agregue lo siguiente al final de la dirección URL:

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Ejemplo  

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Para filtrar los informes de Teams o Skype empresarial, agregue lo siguiente al final de la dirección URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

Ejemplo

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Is Teams]|[TRUE]```


> [!NOTE]
> Los ejemplos de direcciones URL anteriores son solo para representación visual. Usa el vínculo predeterminado del CQD de <https://cqd.lync.com>.


#### <a name="query-filters"></a>Filtros de consulta

Los filtros de consultas se implementan mediante el editor de consultas del CQD. Estos filtros se usan para reducir el número de registros devueltos por el CQD, lo que minimiza el tamaño global y los tiempos de consulta del informe. Esto es especialmente útil para filtrar las redes no administradas. Los filtros que se muestran en la tabla siguiente usan expresiones regulares (RegEx).

_Tabla 3-filtros de consultas_

| Filtro         | Descripción          | Ejemplo de filtro de consulta de CQD      |
|----------------|----------------------|-------------------------------|
| No hay valores en blanco   | Algunos filtros no tienen la opción de filtrar por valores en blanco. Para filtrar los valores en blanco manualmente, use la expresión en blanco y establezca el filtro en es igual a o no es igual, en función de sus necesidades.      | \< \> Nombre \^del \\segundo edificio s\*\$                       |
| Excluir subredes comunes | Sin un archivo de compilación válido para separar administrado de redes no administradas, las redes domésticas se incluirán en los informes. Estas subredes domésticas están fuera del alcance de su control y se pueden excluir rápidamente de un informe. Las subredes comunes, según se define en esta guía, son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | Segunda subred \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Ver solo dentro de  | Se usa para filtrar un informe por administrado (interno) o no administrado (externo). La plantilla de CQD administrada ya está preconfigurada con estos filtros.       | En el segundo Corp = Inside        |

#### <a name="report-filters"></a>Filtros de informe

Los filtros de informe se implementan agregando un filtro al informe representado en el editor de consultas o directamente al informe. Los siguientes filtros de informe se usan en toda la plantilla.

_Tabla 4: filtros de informe_

| Filtro     | Descripción                            | Ejemplo de filtro de informe de CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Empiece por el primer año y luego por el mes. | 2017-10                           |
| Alfabético | Filtra cualquier carácter alfabético. | [a-z]                             |
| Alfanumérico    | Filtra por cualquier carácter numérico.    | [0-9]                             |
| Porcentaje | Filtra por un porcentaje.              | ([3-9]\\). \|([3-9])\|([1-9] [0-9]) |

## <a name="import-the-cqd-templates"></a>Importar las plantillas del CQD

Esta guía incluye [dos plantillas de CQD de protegida](https://aka.ms/qertemplates). Estas plantillas aceleran el uso de CQD y le brindan una oportunidad de aprovechar rápidamente las capacidades del CQD para influir en los equipos de los usuarios o en la experiencia de Skype empresarial. La plantilla todas las redes, aunque optimizada para trabajar con un archivo de datos de creación, se puede usar mientras trabaja para recopilar y cargar información de compilación en el CQD, como se describe en la siguiente sección.

**Para importar las plantillas (. CQDX) en Internet de CQD**

1. Vaya a <https://cqd.lync.com>.

2. Autenticar con sus credenciales administrativas de Office 365.

   > [!NOTE]
   > Para obtener acceso al CQD, debe tener el rol de administrador global de Office 365, administrador de Skype empresarial o lector de informes. 

3. Seleccione el menú **informes de Resumen** en la parte superior de la página y, a continuación, elija **informes detallados**.

4. En el panel Resumen, seleccione **importar**. Vaya a la ubicación guardada CQDX, seleccione la plantilla CQDX y, a continuación, seleccione **abrir**.

5. Una vez que se cargue la plantilla, aparecerá una ventana emergente en la que se muestra el mensaje "la importación del informe se realizó correctamente". Seleccione **Aceptar.**

   ![Captura de pantalla de notificación de importación correcta](media/qerguide-image-importmessage.png "Notificación de que la plantilla se ha importado correctamente")

6. Repita los pasos 4 y 5 para la segunda plantilla de CQD.

> [!NOTE]
> Las plantillas de CQD se importan por usuario. Si otros usuarios necesitan usar el informe, deben iniciar sesión e importar las plantillas a su instancia de CQD. 


## <a name="building-mapping"></a>Asignación de creación

En una implementación de Teams o Skype empresarial online, todos los clientes son externos. Esto tiene la implicación de que, de forma predeterminada, todos los clientes se notifiquen como fuera del CQD en línea, independientemente de si el cliente se conectó a una red corporativa interna.

Al trabajar con el CQD, debe conocer la ubicación de un extremo y si se ha conectado a una red que puede administrar o a una red que no puede administrar; se supone que solo puede mejorar las redes que puede administrar. Al cargar la subred y la información de compilación en el CQD en línea, se habilita el CQD para determinar si el punto de conexión se ha conectado a una red interna corporativa o administrada o a una red externa o no administrada.

### <a name="building-data-file-structure"></a>Creación de una estructura de archivo de datos

El formato del archivo de datos que cargue debe cumplir los siguientes requisitos para pasar la comprobación de validación antes de cargarlo.

-   El archivo debe ser un archivo TSV, lo que significa que, para cada fila, cada columna está separada por un carácter de tabulación o un archivo CSV en el que cada columna está separada por una coma.

-   El archivo no puede tener más de 50 MB.

-   El contenido del archivo de datos *no debe incluir encabezados de tabla*. En otras palabras, la primera línea del archivo de datos debe ser datos reales, no encabezados de columna, como "red".

-   Para cada columna, el tipo de datos solo puede ser String, Number o bool. Si el tipo de datos es número, el valor debe ser un valor numérico; Si es bool, el valor debe ser 0 o 1.

-   Para cada columna, si el tipo de datos es una cadena, los datos pueden estar vacíos (pero deben estar separados por un delimitador adecuado, es decir, un carácter de tabulación o una coma). Esto simplemente asigna a ese campo un valor de cadena vacía.

-   Debe haber 14 columnas por cada fila. Cada columna debe tener el tipo de datos que se describe en la tabla siguiente y las columnas deben estar en el orden en que aparecen en la tabla.

_Tabla 5-creación de una estructura de archivos_

| Nombre de columna        | Tipo de datos | Ejemplo                   | Instrucciones    |
|--------------------|-----------|---------------------------|-------------|
| Red            | String    | 192.168.1.0               | Obligatorio    |
| Red        | String    | Estados Unidos/Seattle/SEATTLE-mar-1 | Obligatorio\*  |
| NetworkRange       | Número    | 26                        | Obligatorio    |
| BuildingName       | String    | SEATTLE-MAR-1             | Obligatorio\*  |
| Propiedad      | String    | Dpto                   | Opcional    |
| Edificio       | String    | Finalización de ti            | Opcional    |
| BuildingOfficeType | String    | Integración               | Opcional    |
| Ciudad               | String    | Seattle                   | Recomendado |
| ZipCode            | String    | 98001                     | Recomendado |
| Tercer            | String    | DÉJEN                        | Recomendado |
| Estado              | String    | WA                        | Recomendado |
| Region             | String    | MSUS                      | Recomendado |
| InsideCorp         | Booleano      | 1                         | Obligatorio    |
| ExpressRoute       | Booleano      | ,0                         | Obligatorio    |

\*Si bien el CQD no lo necesita, las plantillas se configuran para mostrar la creación y el nombre de red.

#### <a name="supernetting"></a>Superredes

Puede usar superredes, denominadas comúnmente enrutamiento entre dominios con clases (CIDR), en lugar de definir cada subred. Una *superred* es una combinación de varias subredes que comparten un único prefijo de enrutamiento. En lugar de agregar una entrada para cada subred, puede usar la dirección de superredes. Es compatible con la superredes, pero no recomendamos que lo uses.

Por ejemplo, la creación de marketing de Contoso está formada por las subredes siguientes:

-   10.1.0.0/24 — primer piso
-   10.1.1.0/24, segundo piso
-   10.1.2.0/24, tercer piso
-   10.1.3.0/24, cuarto piso

En lugar de agregar una entrada para cada subred, puede usar la dirección de superredes, en este ejemplo, 10.1.0.0/22.

-   Network = 10.1.0.0
-   Intervalo de red = 22

Estas son algunas cosas que debe tener en cuenta antes de implementar la superredes:

-   La superredes solo se puede usar en una asignación de subred con una máscara de 8 bits a 28 bits.

-   La superredes tarda menos tiempo en cargarse, pero es el costo de reducir la riqueza de los datos. Supongamos que hay un problema de calidad que afecta a la subred 200.1.2.0. Si ha implementado la superredes, no sabrá en qué lugar de la creación se encuentra la subred ni qué tipo de red (por ejemplo, un laboratorio). Si definiste todas las subredes para un edificio y cargó información de ubicación del piso, podrás ver esa distinción.

-   Es importante asegurarse de que la dirección de superredes sea correcta y de que no se detecte ninguna subred no deseada.

-   Es muy común buscar 192.168.0.0 en los datos. Para muchas organizaciones, esto indica que el usuario está en casa. Para otros, este es el esquema de dirección IP de una oficina satélite. Si su organización tiene oficinas que usan esta configuración, no la incluya en el archivo de creación porque es difícil distinguir entre las redes domésticas y domésticas mediante subredes comunes. Consulte la sección sobre [subredes comunes](#common-subnets), anteriormente en esta guía.

> [!IMPORTANT]
> El intervalo de red se puede usar para representar un superred. Todas las nuevas cargas de archivos de datos de creación se verificarán para los intervalos superpuestos. Si ha cargado previamente un archivo de compilación, debe descargar el archivo actual y cargarlo de nuevo para identificar cualquier solapamiento y corregir el problema. Cualquier solapamiento de los archivos cargados previamente puede dar lugar a asignaciones erróneas de subredes a edificios de los informes.

#### <a name="vpn"></a>VPN

Los datos de la calidad de la experiencia (QoE) que los clientes envían a Office 365, desde donde se han origen los datos del CQD, incluye una marca de VPN. El CQD verá esto como la primera dimensión VPN y del segundo. Sin embargo, esta marca depende de los informes de proveedores de VPN para Windows que el adaptador de red VPN registrado es un adaptador de acceso remoto. No todos los proveedores de VPN registran correctamente adaptadores de acceso remoto. Por este motivo, es posible que no pueda usar los filtros de consulta de VPN integrados. Existen dos enfoques para acomodar las subredes VPN en el archivo de información de creación:

- Defina un **nombre de red** con el texto "VPN" en este campo para subredes VPN.

  ![Captura de pantalla de informe de QCD que muestra una VPN con el nombre de red](media/qerguide-image-vpnnetworkname.png)

  _Ilustración 12: VPN con nombre de red_

- Defina un **nombre de edificio** usando el texto "VPN" en este campo para subredes VPN.

  ![Captura de pantalla de informe de QCD que muestra una VPN con el nombre de creación](media/qerguide-image-vpnbuildingname.png)

  _Figura 13-red privada virtual (VPN) con nombre de creación_

> [!IMPORTANT]
> Ciertas implementaciones de VPN no informan con precisión la información de subred. Si esto sucede en sus informes, le recomendamos que, al agregar una subred VPN al archivo de creación, en lugar de una entrada para la subred, agregue entradas independientes para cada dirección de la subred VPN como una red de 32 bits independiente. Cada fila puede tener los mismos metadatos de compilación. Por ejemplo, en lugar de una fila para 172.16.18.0/24, tiene 253 filas, con una fila para cada dirección de 172.16.18.1/32 a 172.16.18.254/32, ambos incluidos.


> [!NOTE]
> Se sabe que las conexiones VPN no identifican la conexión de red como cableada cuando la conexión a Internet subyacente es inalámbrica. Al mirar la calidad de las conexiones VPN, no puede dar por sentado que el tipo de conexión se ha identificado correctamente.

### <a name="uploading-building-information"></a>Cargar información de compilación

El panel informes de resumen del CQD incluye una página de **carga de datos de inquilino** , a la que se tiene acceso seleccionando la etiqueta de vínculo de carga de datos de **inquilino** en la esquina superior derecha (busque el icono de engranaje). Esta página se usa para que los administradores carguen su propia información, como la asignación de la dirección IP y la información geográfica, la asignación de cada punto de acceso inalámbrico y su dirección MAC, etc.

1. Vaya a el CQD en línea buscando en <https://cqd.lync.com>.

2. Seleccione el icono de engranaje en la esquina superior derecha y elija **carga de datos de inquilino** en la página informes de **Resumen** .

   ![Captura de pantalla del cuadro de diálogo que aparece mientras se cargan los datos](media/qerguide-image-tenantdataupload.png)

   _Figura 14: menú de carga de datos de inquilino_

3. Como alternativa, si esta es la primera vez que visita el CQD, se le pedirá que cargue los datos de compilación. Puede seleccionar **cargar ahora** para desplazarse rápidamente a la página de **carga de datos de inquilino** .

   ![Captura de pantalla de un banner que notifica a un usuario que debe cargar datos de compilación](media/qerguide-image-buildingdatauploadbanner.png)

   _Ilustración 15: crear una pancarta de carga de datos_

4. En la página **carga de datos de inquilino** , seleccione **examinar** para elegir un archivo de datos.

5. Después de seleccionar un archivo de datos, especifique **fecha de inicio** y, opcionalmente, especifique una fecha de finalización.

6. Después de seleccionar **fecha de inicio**, seleccione **cargar** para cargar el archivo en el CQD. <br><br>Antes de que se cargue el archivo, se valida. Si se produce un error en la validación, se muestra un mensaje de error en el que se le pide que corrija el archivo. En la siguiente ilustración se muestra un error que se produce cuando el número de columnas del archivo de datos es incorrecto.

   ![Ejemplo de cuadro de diálogo que muestra un error de carga de datos de compilación](media/qerguide-image-buildingdatauploaderror.png)
 
   _Figura 16: generación de un error de carga de datos_

7. Si no se producen errores durante la validación, la carga del archivo se realizará correctamente. Puede ver el archivo de datos cargado en la tabla **mis cargas** , que muestra la lista completa de todos los archivos cargados para el inquilino actual en la parte inferior de la página.

> [!NOTE]
> Puede demorar hasta cuatro horas en finalizar el procesamiento del archivo de creación. <br><br> Si ya ha cargado un archivo de compilación y necesita agregar subredes que puedan haberse perdido o excluido, modifique el archivo original agregando las nuevas subredes, quite el archivo actual y vuelva a cargar el archivo recién editado. Solo puede haber un archivo de datos de construcción activo en el CQD. 


### <a name="updating-a-building-file"></a>Actualizar un archivo de creación

Al recopilar la información de creación y de subred, los administradores cargarán el archivo de compilación en varias iteraciones a lo largo del tiempo, agregando nuevas subredes y la información de compilación cuando esté disponible. Cuando esto sucede, tendrá que volver a cargar el archivo de compilación. Este proceso es como la carga inicial según se describe en la sección anterior, con algunas excepciones, tal y como se indica en la siguiente sección.

> [!Important]
> Solo puede haber un archivo de compilación activo cada vez. No se acumulan varios archivos de compilación.

#### <a name="adding-net-new-subnets"></a>Agregar subredes nuevas

En ocasiones, tendrá que agregar subredes nuevas a el CQD que no eran parte de su topología de red. Para agregar subredes nuevas, haga lo siguiente en el portal de carga de datos del inquilino de CQD:

1.  Edite el archivo de creación original y proporcione una fecha de finalización que se produzca al menos un día antes de que se hayan adquirido las nuevas subredes.
2.  Descargue el archivo original, si aún no tiene una copia actualizada.
3.  Anexe las subredes nuevas al archivo de creación original.
4.  Cargue el archivo de compilación recién modificado siguiendo el mismo proceso que se indica anteriormente y establezca la fecha de inicio de un día a la que finaliza el archivo de compilación anterior.

#### <a name="updating-the-current-building-file"></a>Actualizar el archivo de compilación actual

Si ya se ha cargado un archivo de compilación pero necesita agregar subredes que faltan, haga lo siguiente en el portal de carga de datos del inquilino de CQD:

1.  Descargue el archivo original, si aún no tiene una copia actualizada.
2.  Quitar el archivo actual del CQD.
3.  Anexe las nuevas subredes al archivo original.
4.  Cargue el archivo de creación. Asegúrese de establecer la fecha de inicio al menos ocho meses antes para que el CQD procese los datos históricos.

### <a name="missing-subnets"></a>Faltan subredes

Después de cargar la información de creación para redes administradas, cada red administrada debe tener una asociación de compilación. Sin embargo, esto no siempre será así; Normalmente, se pierden algunas subredes. En esta sección se explica cómo validar las redes que faltan.

Vaya a la página **informes detallados** del CQD en línea y navegue hasta el **Informe de subred perdida** incluido en las plantillas del CQD. Esto presenta todas las subredes con 10 o más flujos de audio que no se definen en el archivo de datos de compilación y se marcan como externos. Asegúrese de que no hay redes administradas en esta lista. Si faltan subredes, actualice el archivo de datos de creación original y vuelva a cargarlo en el CQD.

> [!IMPORTANT]
> Tendrá que agregar su identificador de inquilino como filtro de consulta para el **segundo identificador de inquilino** a este informe para filtrar el informe para ver solo los datos de inquilinos de su organización. En caso contrario, el informe mostrará subredes federadas.

> [!NOTE] 
> Asegúrese de ajustar el filtro de informe de año mensual al mes en curso. Seleccione **Editar**y ajuste el filtro de informe **mes de año** para guardar el nuevo mes predeterminado.

![Captura de pantalla que muestra el informe de subred que falta](media/qerguide-image-missingbuildingreport.png)

_Ilustración 17: falta el informe de compilación_

### <a name="building-mapping-tools"></a>Creación de herramientas de asignación

Vamos a cara, la asignación de subredes en su organización puede ser difícil. Las redes globales grandes son muy complejas, con diferentes equipos que administran sus regiones respectivas y es posible que no haya un único origen de verdad para la topología de red. Hay dos herramientas disponibles para ayudarle a iniciar el ejercicio de la asignación de edificios, que se describe en las secciones siguientes.

#### <a name="cqd-tools"></a>Herramientas de CQD

Estas herramientas se basan en PowerShell y pueden aprovechar los sitios y servicios de Active Directory (AD) y los servicios DHCP de Microsoft para ayudarle a rellenar previamente el archivo de compilación.  Estas herramientas le ayudarán a realizar las siguientes tareas:

1.  Consultar sitios y servicios de AD y crear un archivo de compilación basado en la información contenida en él.
2.  Consulte un servidor o servidores DHCP de Microsoft para extraer la información de subred y crear automáticamente un archivo de creación.
3.  Validar un archivo de compilación existente, comprobando si existen duplicados y superposiciones.
4.  Busque subredes sin asignar en el CQD.

Para obtener más información sobre esta herramienta, vea [esta entrada de blog](https://aka.ms/cqdtools).

#### <a name="network-planner"></a>Planificador de red

El planificador de redes determina y organiza los requisitos de red para su implementación de voz en la nube en solo unos pocos pasos. Al proporcionar los detalles de red de su organización y el uso de la voz de nube, puede obtener un cálculo aproximado de los requisitos de red para su implementación de voz en la nube, administrar y exportar estos detalles para los informes y las áreas de visualización para una mayor investigación y los siguientes pasos.

Aunque el planificador de redes no automatiza el proceso de asignación de la creación por completo, una vez que la información de la red se introduce en el planificador de la red, se puede exportar a un archivo de compilación listo para cargarlo.

## <a name="reliability-investigations"></a>Investigaciones de confiabilidad

El primer paso para mejorar la calidad es evaluar el estado de confiabilidad en toda la organización. Puesto que la confiabilidad es vital para una experiencia de usuario positiva, comenzamos con los dos componentes que miden la confiabilidad:

1.  **Errores de configuración:** No se pudo establecer la llamada.

2.  **Errores de colocación:** La llamada se estableció y terminó de forma inesperada.

En esta sección, cubriremos métodos para investigar las dos áreas.

> [!NOTE]
> En esta guía no se tratan todos los informes incluidos en las plantillas.  Sin embargo, siguen aplicándose los métodos de investigación explicados a continuación. Para obtener más información, consulta la descripción del informe individual.


### <a name="setup-failures"></a>Errores de configuración

Dé prioridad a la corrección de errores de configuración en esta área en primer lugar, porque estos errores tienen un impacto negativo significativo en la experiencia del usuario.

Empiece la investigación evaluando el porcentaje de errores generales de configuración de la organización y, a continuación, establezca prioridades en las áreas de investigación según el porcentaje más alto en la creación o la red. 

#### <a name="setup-failure-trend-analysis"></a>Análisis de tendencias de errores de configuración

Este informe muestra la cantidad total de flujos, errores de configuración de la transmisión por secuencias y la tasa de errores de configuración de la transmisión. Apunte a cualquiera de las columnas para mostrar sus valores individuales, como se muestra en la siguiente ilustración. 

![Gráfico que muestra el porcentaje de errores de configuración de la secuencia](media/qerguide-image-streamsetupfailures.png)

_Ilustración 19: confiabilidad de audio: errores de configuración de la secuencia_

##### <a name="analysis"></a>Análisis

Con este informe, puede responder a las siguientes preguntas y determinar el siguiente curso de acción:

-   ¿Cuál es el porcentaje total de errores de configuración de llamadas del mes actual?

-   ¿El porcentaje total del error de configuración de la llamada está por debajo o por encima de la métrica objetivo definida?

-   ¿La tendencia del error es peor o superior que el mes anterior?

-   ¿El aumento, la estabilidad o la disminución de la tendencia del error?

Independientemente de las respuestas anteriores, dedique el tiempo de investigar con los subinformes complementarios para buscar cualquier edificio o subred que pueda necesitar corrección. A pesar de que la tasa de error general puede estar por debajo de la métrica de destino, las tarifas de error para uno o más edificios o redes pueden estar por encima de la métrica de destino y necesitan investigación.

#### <a name="setup-failure-investigations"></a>Investigaciones de errores de configuración 

Este informe de resumen se usa para descubrir y aislar cualquier edificio o red que pueda necesitar corrección.

> [!NOTE]
> Asegúrese de ajustar el filtro de informe de año mensual al mes en curso. Seleccione **Editar**y ajuste el filtro de informe **mes de año** para guardar el nuevo mes predeterminado.


![Captura de pantalla que muestra errores de configuración](media/qerguide-image-setupfailuresbysubnet.png)

_Figura 20: errores de configuración de audio por subred_

##### <a name="remediation"></a>Corrección 

Centre el primer esfuerzo de corrección en edificios o subredes que tengan el mayor volumen de errores. Esto maximizará el impacto en la experiencia del usuario y ayudará a reducir rápidamente la tasa de errores de configuración de las llamadas de la organización. En la tabla siguiente se enumeran los dos motivos de errores de configuración notificados por el CQD.

_Tabla 7: razones para errores de configuración de llamadas_

| Motivo de errores de configuración de llamadas       | Causa típica                    |
|----------------------------------|----------------------------------|
| Regla de exención de inspección de paquetes profundos de FW ausente | Indica que el equipo de red de la ruta impidió que se establecera la ruta de medios debido a reglas de inspección de paquetes en profundidad. Probablemente se deba a que las reglas de Firewall no se han configurado correctamente. En este escenario, el protocolo de enlace TCP tuvo éxito pero el protocolo de enlace SSL no.      |
| Falta la regla de excepción de bloqueo IP de FW      | Indica que el equipo de red a lo largo de la ruta ha impedido que la ruta de medios se establezca en la red de Office 365. Esto puede deberse a que las reglas de proxy o de Firewall no se han configurado correctamente para permitir el acceso a las direcciones IP y los puertos que se usan para los equipos y el tráfico de Skype empresarial. |

Ahora, cuando empiece su corrección, podrá centrar sus esfuerzos en un edificio o una subred en particular. Como se muestra en la tabla anterior, estos problemas se deben a configuraciones de firewall o proxy. Revise las opciones de la tabla siguiente para ver las acciones de corrección.

_Tabla 8: pasos siguientes para la corrección de errores de configuración de llamadas_


|      Corrección      |                                                                                                                                                                                                                                                                                                                                                                   Instrucciones                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar firewalls | Trabaje con su equipo de red y Compruebe la configuración del firewall en [la lista de direcciones IP de Office 365](https://aka.ms/o365ips).<br><br>Compruebe que las [subredes](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) y los puertos de medios estén incluidos en las reglas de Firewall. <br><br>Verifique que los puertos necesarios (enumerados a continuación) se abran en el firewall. Se debe dar prioridad a UDP porque TCP se considera un protocolo de conmutación por recuperación para el audio, el vídeo y la pantalla compartida basada en vídeo, y su uso afectará a la calidad de la llamada. RDP heredado el uso compartido de aplicaciones usa solo TCP.<br><ul><li>Puerto **TCP:** 443</li><li>**UDP:** puertos 3478:3481</li><ul> |
|        Verificar         |                                                                                                                                                                                                                                                                 Use la [herramienta de evaluación de redes de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar la conectividad de la creación o subred afectada mediante la función de comprobación de conectividad.                                                                                                                                                                                                                                                                  |

### <a name="drop-failures"></a>Errores de colocación

A diferencia de los códigos de error de configuración, CDQ no tiene código de error de eliminación para indicar por qué se producen errores de colocación, lo que hace que sea difícil aislar una causa raíz específica. Para mejorar la evaluación de errores, use un enfoque deducido. Si corrige las áreas de interés de los medios, aplica revisiones a los clientes y los drivers y, por ello, impulsa el uso de dispositivos certificados para equipos y Skype empresarial, puede esperar que se produzcan errores de rechazo.

#### <a name="drop-failure-trend-analysis"></a>Análisis de tendencias de errores de eliminación

Este informe muestra la cantidad total de transmisiones de audio, los errores de eliminación total y la tasa de errores al colocar. Apunte a cualquiera de las columnas para mostrar sus valores, como se muestra en la siguiente ilustración. 

![Gráfico que muestra el porcentaje de secuencias que se han quitado](media/qerguide-image-droppedstreamrate.png)

_Ilustración 21: velocidad de Stream interrumpida_

##### <a name="analysis"></a>Análisis

Al usar este tipo de informe, puede responder a las siguientes preguntas:

-   ¿Cuál es la tasa de errores de caída actuales?
-   ¿La tasa de error de colocación está por debajo de la métrica de destino definida?
-   ¿La tendencia del error es peor o superior que el mes anterior?
-   ¿El aumento, la estabilidad o la disminución de la tendencia del error?

Independientemente de las respuestas a las preguntas anteriores, dedique el tiempo de investigar el uso de los subinformes para buscar edificios o redes que puedan necesitar corrección. Aunque la tasa general de errores de colocación puede estar por debajo de la métrica de destino, la tasa de errores de caída para uno o varios edificios o redes podría estar por encima de la métrica de destino y necesita investigar.

#### <a name="drop-failure-investigations"></a>Eliminar investigaciones de errores

Los errores notificados aquí indican que la llamada se ha interrumpido de forma inesperada y resultó en una experiencia de usuario negativa. A diferencia de los informes de tendencias, estos informes proporcionan información adicional sobre subredes específicas que necesitan más investigación.

> [!NOTE]
> Asegúrese de ajustar el filtro de año mensual al mes en curso. Seleccione **Editar**y ajustar **mes del año** para guardar el nuevo mes predeterminado.


![Informe que muestra el número y el porcentaje de errores de colocación](media/qerguide-image-dropfailuresbysubnet.png)

_Figura 22 – errores de colocación por subred_

##### <a name="remediation"></a>Corrección

Con los informes de tabla incluidos, puede aislar las áreas problemáticas de la red donde la tasa de colocación está por encima de la métrica de objetivo que ha definido. Centre el primer esfuerzo de corrección en edificios o subredes que tengan la cantidad máxima de flujo total, para lograr el mayor impacto.

Causas comunes de caídas de llamadas:

-   Salida de red o de Internet aprovisionada
-   No hay ninguna QoS configurada en redes restringidas
-   Versiones de cliente anteriores
-   Comportamiento del usuario

Una vez que haya descubierto las áreas problemáticas, puede usar el [análisis de llamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) para revisar aún más los usuarios de esa creación para problemas específicos. Los análisis de llamadas contienen datos PII adicionales y pueden ser útiles para aislar aún más los posibles motivos de los errores de colocación.

Independientemente del próximo paso, es recomendable notificar al Departamento de soporte técnico que se ha detectado un problema con edificios o subredes específicas. De esta manera, pueden responder rápidamente a las llamadas entrantes y evaluar los usuarios de forma más eficaz. Los usuarios marcados pueden ser devueltos al equipo de ingeniería para obtener más investigación.

En la tabla siguiente se enumeran algunos métodos comunes para administrar y corregir errores de Drop.

_Tabla 9: pasos siguientes para la corrección de la llamada_

| Corrección                              | Instrucciones                      |
|------------------------------------------|-------------------------------|
| **Red e Internet**                         | **Congestión**: trabaje con su equipo de red para controlar el ancho de banda en edificios o subredes específicos para confirmar que hay problemas de sobreutilización. Si confirma que hay congestión en la red, considere la posibilidad de aumentar el ancho de banda a la creación o la aplicación de QoS. Use los [informes de Resumen de calidad deficiente](#quality-investigations) incluidos para revisar las subredes problemáticas para problemas de vibración, latencia y pérdida de paquetes, porque normalmente precederán a una transmisión.<br><br>**QoS**: Si el aumento de ancho de banda no es práctico o es prohibitiva, considere la posibilidad de implementar QoS. Esta herramienta es muy eficaz en la administración del tráfico congestionado y puede garantizar que los paquetes multimedia de la red administrada estén clasificados por encima del tráfico no multimedia. Como alternativa, si no hay evidencia clara de que el puesto de ancho de banda sea el culpable, considere estas soluciones:<ul><li>[Guía de QoS de Microsoft Teams](qos-in-teams.md)</li></ul><br>**Realizar una evaluación**de la preparación para la red: una evaluación de la red proporciona detalles sobre el uso esperado de ancho de banda, cómo hacer frente a los cambios de ancho de banda y red, así como prácticas recomendadas de redes para equipos y Skype empresarial. Con la tabla anterior como origen, tiene una lista de edificios o subredes que son candidatos excelentes para una evaluación.<ul><li>[Evaluación de la disponibilidad de redes de Microsoft Teams](3-envision-evaluate-my-environment.md#test-the-network)</li></ul><br>**Herramienta de evaluación de redes de Microsoft:** Use esta herramienta para realizar una prueba sencilla del rendimiento de la red con el fin de determinar la eficacia de la red para una llamada de equipo o de Skype empresarial online. La herramienta le ayuda a evaluar el rendimiento de una subred y a validar la preparación de la red frente a [los requisitos](https://aka.ms/performancerequirements)de rendimiento de Microsoft.<ul><li>[Descargar la herramienta de evaluación de redes](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul> |
| **Clientes (solo Skype empresarial online)** | Algunos clientes más antiguos han conocido problemas documentados con la confiabilidad de los medios. Revise los informes de análisis de llamadas de varios usuarios afectados o cree un informe de tabla de versiones de cliente personalizado en el CQD filtrado para edificios o subredes específicas con error total de llamadas% en medida. Esta información le ayudará a comprender si existe una relación entre las caídas de llamadas de ese edificio específico y una versión específica del cliente.     |
| **Dispositivos**                                  | Recomendamos que todos los usuarios que estén experimentando interrupciones en las llamadas o llamadas incorrectas en general, y que usen dispositivos integrados, tengan un suministro de [auriculares con micrófono o un teléfono con manos libres](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) para eliminar esto como una fuente potencial de baja calidad y fiabilidad. |
| **Comportamiento del usuario**                            | Si determina que ninguna red, dispositivo o cliente es el problema, considere la posibilidad de desarrollar una estrategia de adopción de usuarios para educar a los usuarios a unirse y salir de las reuniones mejor. Un equipo más inteligente y un usuario de Skype empresarial producirá una mejor experiencia de usuario para todos los participantes de la reunión. Un usuario que pone el portátil en modo de suspensión (cerrando la tapa) sin salir de la reunión se clasificará como una llamada inesperada.   |

## <a name="quality-investigations"></a>Investigaciones de calidad

El siguiente paso para evaluar el estado de la calidad de audio en toda la organización es investigar la mala tasa de transmisión (PSR), TCP y el uso del proxy. Es importante recordar que los datos del CQD no le proporcionan una causa raíz específica, sino que le proporcionan posibles problemas para comenzar una conversación colaborativa con los equipos apropiados para las actividades de corrección. 

> [!NOTE]
> En esta guía no se tratan todos los informes incluidos en las plantillas; sin embargo, los métodos de investigación explicados a continuación seguirán aplicándose para esos informes. Para obtener más información, consulte la descripción del informe individual. 

### <a name="quality"></a>Compra

Los porcentajes de VECPRD se usan para indicar si la organización está a la reunión de objetivos métricos definidos para un área de enfoque determinada. Es importante tener en cuenta que, incluso si los porcentajes de alto nivel están dentro del objetivo definido, las subredes o los edificios individuales pueden no cumplir los objetivos definidos y, por consiguiente, necesitan más investigación. Por ejemplo, si el total de los VECPRD es el 2 por ciento en abril, que cumple con el destino de la muestra, es posible que los edificios y subredes individuales sigan teniendo una mala experiencia en función de la distribución general de ese 2 por ciento. 

Para evaluar el porcentaje de transmisiones deficientes, use los informes de calidad. Se proporcionan diversos informes de calidad para revisar las métricas generales, de conferencia, de dos, llamadas RTC, VPN y salas de reuniones. Se proporcionan informes mensuales, semanales y diarios para ayudar en este proceso. Los informes semanales y diarios se limitan a la plantilla redes administradas para aumentar su eficacia y reducir el ruido. 

#### <a name="quality-trend-analysis"></a>Análisis de tendencias de calidad

Los informes de tendencias muestran información sobre la calidad a lo largo del tiempo y se usan para ayudar a identificar y comprender las tendencias de calidad dentro de cada área de interés. Como se mencionó anteriormente, hay árboles de informes incluidos en las plantillas para la investigación de calidad. conferencias, llamadas RTC, VPN y salas de reuniones de dos partes. Para el análisis de la calidad, el proceso de investigación es el mismo. Sin embargo, le recomendamos que empiece con conferencias en primer lugar, porque cualquier mejora en la calidad de la Conferencia también afectará de forma positiva a todas las demás áreas. 

> [!Note]
> La investigación de dos entidades, la de llamadas RTC y las salas de reuniones son similares a las de investigación. El foco es isloate edificios o subredes que tengan la peor calidad e identifiquen el motivo de la mala calidad.

> [!Important]
> Los informes basados en VPN se filtran mediante la segunda dimensión VPN. Esta dimensión requiere que el adaptador de red VPN esté correctamente registrado como un adaptador de acceso remoto. Los proveedores de VPN no usan de forma confiable esta marca y su kilometraje varía según el proveedor de VPN implementado en su organización. Siga las instrucciones descritas [anteriormente en esta guía](#vpn) para modificar los informes de VPN si es necesario con el nombre de red o edificio.

![Gráfico que muestra el porcentaje de flujos de baja calidad](media/qerguide-image-audioqualityconferencing.png)

_Ilustración 23: conferencias de calidad de audio_

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

> [!NOTE]
> Asegúrese de ajustar el filtro de año mensual al mes en curso. Seleccione **Editar**y ajustar **mes del año** para guardar el nuevo mes predeterminado.

> [!Note]
> Las subredes comunes son difíciles de clasificar debido a su uso generalizado. Se ha agregado a la plantilla todas las redes un informe independiente que muestra la dirección IP pública del cliente (segundo IP local reflexiva) para ayudarle a corregir las oficinas que usan redes comunes.


![Captura de pantalla que muestra el Resumen de flujo de audio deficiente](media/qerguide-image-poorqualitysummary.png)

_Ilustración 24: Resumen de las secuencias de audio de mala calidad mediante la creación de conferencias de subred_

##### <a name="remediation"></a>Corrección

Centre sus esfuerzos de corrección en edificios o subredes que tengan el mayor volumen de secuencias, porque esto maximizará el impacto y ayudará a mejorar la experiencia del usuario rápidamente. Use las medidas de vibración, pérdida de paquetes y tiempo de ida y vuelta (RTT) para comprender qué contribuye a la mala calidad (es posible que no haya más de un problema):

-   **Vibración**: los paquetes multimedia llegan a velocidades diferentes, lo que hace que un altavoz suene de forma robótica.
-   **Pérdida de paquetes**: los paquetes multimedia se pierden, lo que crea el efecto de que faltan palabras o sílabas.
-   **RTT**: los paquetes multimedia tardan mucho tiempo en llegar a su destino, lo que crea un efecto walkie-talkie.

Para ayudar a su investigación en problemas de calidad, puede aprovechar el [análisis de llamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Con el análisis de llamadas, puede consultar una conferencia específica o un informe detallado de las llamadas de los usuarios. Este informe contendrá datos PII y es útil cuando está buscando la causa de un error. Una vez que sepa qué edificio se verá afectado, debe realizar un seguimiento sencillo de los usuarios de ese edificio. 

No olvides avisar al Helpdesk de que estas redes experimentan problemas de calidad, de modo que puedan clasificar y responder rápidamente a las llamadas entrantes.

_Tabla 10-contribuidores comunes a los altos VECPRD_

| Corrección                              | Instrucciones                         |
|------------------------------------------|----------------------------------|
| **Las**                                 | **Congestión**: una red sobreutilizada o con aprovisionamiento puede causar problemas con la calidad de los medios. Trabaje con el equipo de red para determinar si las conexiones de red entre el usuario y el punto de salida de Internet tienen suficiente ancho de banda para admitir medios. <br><br>**Realizar una evaluación**de la preparación para la red: una evaluación de la red proporciona detalles sobre el uso esperado de ancho de banda, cómo hacer frente a los cambios de ancho de banda y red, así como prácticas recomendadas de redes para equipos y Skype empresarial. Con la tabla anterior como origen, tiene una lista de edificios o subredes que son candidatos excelentes para una evaluación.<ul><li>[Evaluación de la disponibilidad de redes de Microsoft Teams](3-envision-evaluate-my-environment.md#test-the-network)</li></ul><br>**Herramienta de evaluación de redes de Microsoft:** Use esta herramienta para realizar una prueba sencilla del rendimiento de la red con el fin de determinar la eficacia de la red para una llamada de equipo o de Skype empresarial online. La herramienta le ayuda a evaluar el rendimiento de una subred y a validar la preparación de la red frente a [los requisitos](https://aka.ms/performancerequirements)de rendimiento de Microsoft.<ul><li>[Descargar la herramienta de evaluación de redes](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul><br> |
| **Calidad de servicio (QoS)**  | QoS es una herramienta comprobada para ayudar a priorizar paquetes en una red congestionada para asegurarse de que lleguen a su destino intacto y a tiempo. Considere la posibilidad de implementar QoS en toda la organización para maximizar la calidad de la experiencia del usuario donde se restringe el ancho de banda. QoS le ayudará a resolver problemas típicamente relacionados con los altos niveles de pérdida de paquetes y, a menor grado, la vibración y los tiempos de ida y vuelta.<ul><li>[Guía de QoS de Microsoft Teams](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | La Wi-Fi puede tener un impacto significativo en la calidad de las llamadas. Por lo general, las implementaciones de Wi-Fi no tienen en cuenta los requisitos de red de los servicios de VoIP y suelen ser una fuente de mala calidad. Para obtener más información sobre cómo optimizar su infraestructura Wi-Fi, consulte [este artículo sobre la planificación de Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Controlador inalámbrico**: Asegúrese de que los drivers inalámbricos estén actualizados. Esto ayudará a reducir cualquier experiencia de usuario deficiente relacionada con un controlador anticuado. Muchas organizaciones no incluyen drivers inalámbricos en los ciclos de las revisiones, y estos drivers pueden desplazarse por años. Muchos problemas de conexión inalámbrica se resuelven asegurándose de que los drivers inalámbricos estén actualizados.<br><br>**WMM**: las extensiones multimedia inalámbricas (WMM), también conocidas como Wi-Fi multimedia, proporcionan características básicas de QoS para redes inalámbricas. Las redes inalámbricas modernas deben admitir muchos dispositivos. Estos dispositivos compiten por el ancho de banda y pueden provocar problemas de calidad en los servicios de VoIP, donde la velocidad y la latencia son fundamentales. Consulta a tu proveedor de telefonía móvil para conocer los detalles y considera la posibilidad de implementar WMM en tu red inalámbrica para priorizar Skype empresarial y los equipos multimedia.<br><br>**Densidad**de puntos de acceso: es posible que los puntos de acceso estén demasiado alejados o no estén en una ubicación ideal. Para minimizar posibles interferencias, coloque puntos de acceso adicionales en salas de conferencias y en ubicaciones que no estén obstruidas por paredes u otros objetos en los que la señal Wi-Fi es débil.<br><br>**2,4 GHz frente a 5 GHz**: 5 GHz proporciona menos interferencias de fondo y velocidades superiores, y se debe priorizar al implementar VoIP a través de Wi-Fi. Sin embargo, 5 GHz no es tan fuerte como 2,4 GHz y no penetra en paredes con facilidad. Revise el diseño del edificio para determinar en qué frecuencia puede confiar para la mejor conexión. |
|**Dispositivo de red** | Las organizaciones más grandes pueden tener cientos de dispositivos repartidos en toda la red. Trabaje con su equipo de red para asegurarse de que los dispositivos de red del usuario a Internet se mantengan y estén actualizados. |
| **VPN**  | Los equipos VPN no están diseñados tradicionalmente para admitir cargas de trabajo de medios en tiempo real. Algunas configuraciones de VPN prohíben el uso de UDP (que es el protocolo preferido para los medios) y dependen únicamente de TCP. Considere la posibilidad de implementar una solución de túnel dividido de VPN para ayudar a reducir la VPN como una fuente de baja calidad. |
| **Clientes** <br>(Solo Skype empresarial online) | Asegúrese de que todos los clientes se actualizan regularmente. |
| **Dispositivos** | El uso de [dispositivos optimizados](https://partnersolutions.skypeforbusiness.com/solutionscatalog) puede ayudar a mejorar significativamente la experiencia del usuario. Con todas las cosas iguales, los dispositivos optimizados están diseñados para maximizar la experiencia del usuario con Teams y Skype empresarial, y producen una calidad superior. |
| **Conductores** | La actualización de la red (Ethernet y Wi-Fi), los drivers de audio, vídeo y USB deben formar parte de la estrategia general de administración de revisiones. La actualización de los drivers resuelve muchos problemas de calidad. |
| **Salas de reuniones en Wi-Fi** | Recomendamos encarecidamente que los dispositivos de la sala de reuniones se conecten a la red mediante al menos una conexión Ethernet de 1 Gbps. Los dispositivos de la sala de reuniones suelen incluir varias transmisiones de audio y vídeo, además de contenido de la reunión, como la pantalla compartida, y tienen más requisitos de red que otros equipos o puntos de conexión de Skype empresarial. Los salones de reunión son, por definición, dispositivos fijos en los que las Wi-Fi ofrecen una ventaja únicamente durante la instalación.<br><br>Las salas de reuniones deben ser tratadas con cuidado y atención adicionales para asegurarse de que la experiencia con estos dispositivos está cumpliendo o superando las expectativas. Por lo general, los problemas de calidad con salas de reuniones se escalan rápidamente, ya que a menudo son utilizadas por personal de nivel superior.<br><br>Con todas las cosas iguales (aparte de la comodidad), el rendimiento de Wi-Fi suele ser menor que una conexión por cable. Con el aumento de las políticas de "traiga sus propios dispositivos" y la proliferación de equipos portátiles, los puntos de acceso Wi-Fi suelen estar sobreutilizados. Es posible que los medios en tiempo real no tengan prioridad en las redes Wi-Fi, lo que puede provocar problemas de calidad durante los períodos de uso máximo. Este uso intensivo puede coincidir con una reunión en la que puede haber una docena de personas en la asistencia, cada una con su propio portátil y smartphone, todos conectados al mismo punto de acceso Wi-Fi que el dispositivo de la sala de reuniones.<br><br>Wi-Fi solo debe considerarse una solución temporal, para una instalación móvil o cuando Wi-Fi se ha aprovisionado correctamente para admitir medios de clase empresarial y en tiempo real. |


### <a name="tcp"></a>TCP

TCP se considera un transporte de conmutación por recuperación y no el transporte principal que desea para los medios en tiempo real. La razón por la que se trata de un transporte de failback es debido a la naturaleza de estado de TCP. Por ejemplo, si una llamada se realiza en una red latente y los paquetes multimedia se retrasan, los paquetes desde hace unos segundos, que ya no son útiles, compite por el ancho de banda para llegar al receptor, lo cual puede empeorar la situación. Esto hace que el avisador de audio ditire y expanda el audio, lo que da como resultado artefactos audibles, generalmente en forma de vibración.

Los informes de esta sección no distinguen entre buenas y malas transmisiones. Dado que se prefiere UDP, los informes buscan el uso de TCP para el uso compartido de pantalla basado en vídeo, audio y vídeo (VBSS). Las tarifas de flujo deficientes se proporcionan para ayudar a comparar la calidad de UDP frente a la de TCP, de modo que pueda centrar sus esfuerzos cuando el impacto sea el más alto. El uso de TCP se debe principalmente a las reglas incompletas del firewall. Para obtener más información sobre las reglas de Firewall para Teams y Skype empresarial online, consulte [direcciones URL e intervalos de direcciones IP de Office 365](https://aka.ms/o365ips).

> [!Important]
> Se recomienda encarecidamente tener un [archivo de compilación válido](#building-mapping) cargado para que pueda distinguir rápidamente entre las transmisiones externas al mirar el uso de TCP.

> [!Note]
> El audio, el vídeo y el de VBSS prefieren UDP como transporte principal. La carga de trabajo de uso compartido de aplicaciones RDP heredada solo usa TCP.

#### <a name="tcp-usage"></a>Uso de TCP

Informes TCP indica el uso general de TCP en los últimos siete meses. Todos los demás informes de esta sección se centrarán en reducir los edificios y subredes específicos en los que se usa con más frecuencia. Hay informes independientes disponibles para las conferencias y las secuencias de dos partes.

![Gráfico que muestra el porcentaje de transmisiones de audio](media/qerguide-image-audiostreamswithtcp.png)
que usan TCP _, Ilustración 25, transmisiones de audio con uso de TCP_


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

_Ilustración 26: TCP frente a UDP-conferencias_

##### <a name="analysis"></a>Análisis

Aunque desea que el uso de TCP sea lo más bajo posible, es posible que vea un poco de uso de TCP en una implementación en buen estado. Por sí solo TCP no contribuye a una mala llamada, por lo que se proporcionan tarifas de flujo para ayudar a identificar si el uso de TCP es un colaborador de baja calidad. 

#### <a name="tcp-investigations"></a>Investigaciones de TCP

En las plantillas de CQD proporcionadas, navegue hasta las transmisiones por secuencias de TCP mediante la creación de informes de subred o redes administradas. Con el fin de investigar el uso de TCP, el proceso es el mismo, por lo que centraremos el debate aquí en conferencias.

> [!IMPORTANT]
> Se recomienda tener un [archivo de compilación](#building-mapping) válido cargado para poder distinguir rápidamente dentro de las transmisiones externas al mirar el uso de TCP. 

> [!NOTE]
> Asegúrese de ajustar el filtro de año mensual al mes en curso. Seleccione **Editar**y ajustar **mes del año** para guardar el nuevo mes predeterminado.                                  |

![Captura de pantalla del uso de TCP mediante la construcción y la subred](media/qerguide-image-tcpstreams.png)

_Figura 27: secuencias de TCP por construcción y Conferencia de subred_

##### <a name="remediation"></a>Corrección

Este informe identifica edificios y subredes específicos que están contribuyendo al volumen de uso de TCP. También se incluye un informe adicional para identificar la IP de Microsoft Relay que se usó en la llamada para ayudar a aislar las reglas de firewall que faltan. Centre sus esfuerzos de corrección en aquellos edificios que tengan el mayor volumen de transmisiones TCP para maximizar el impacto.

La causa más común del uso de TCP es la falta de reglas de excepción en firewalls o servidores proxy. Hablaremos sobre los servidores proxy en la siguiente sección, así que para centrar sus esfuerzos en los firewalls. Al usar el edificio o la subred proporcionados, puede determinar qué Firewall necesita actualizarse.


_Tabla 11: Guía de corrección para las transmisiones de TCP mediante la creación y la subred_

| Corrección        | Instrucciones     |
|--------------------|--------------------------------------|
| Configurar el Firewall | Compruebe que los [puertos y las direcciones IP de Office 365](https://aka.ms/o365ips) están excluidos de su firewall. Para problemas de TCP relacionados con los medios, Centre sus esfuerzos iniciales en lo siguiente:<ul><li>Compruebe que las subredes de medios del cliente 13.107.64.0/18 y 52.112.0.0/14 estén en las reglas del firewall.</li><li>Puertos UDP 3478:3481 son los puertos de medios necesarios y deben abrirse; de lo contrario, el cliente no podrá recuperar el puerto TCP 443.</li></ul> |
| Verificar             | Use la [herramienta de evaluación de redes de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si hay problemas de conectividad con direcciones IP y puertos específicos de Office 365 desde la creación o subred afectada.    |

### <a name="http-proxy"></a>Proxy HTTP

Los proxies HTTP no son la ruta preferida para establecer sesiones de medios, por un gran variedad de motivos. Muchos contienen características de inspección de paquetes en profundidad que pueden impedir que se completen las conexiones al servicio e introducir interrupciones. Además, casi todos los servidores proxy fuerzan a TCP en lugar de permitir UDP, lo que se recomienda para una óptima calidad de audio.

Siempre recomendamos que configure el cliente para que se conecte directamente a teams y a los servicios de Skype empresarial. Esto es especialmente importante para el tráfico basado en elementos multimedia.


> [!IMPORTANT]
> Disponer de un [archivo de creación](#building-mapping) válido cargado hace que sea más fácil distinguir correctamente entre las transmisiones de audio externas al analizar el uso del proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

El informe de la secuencia de proxy HTTP de esta sección de la plantilla es muy similar a los informes TCP. Sin embargo, no se muestra si las llamadas son deficientes o buenas, pero si la llamada está conectada a través de HTTP.

![Captura de pantalla del informe de transmisiones de audio que usan HTTP](media/qerguide-image-audiostreamswithhttp.png)

_Ilustración 28: transmisiones de audio con uso de proxy HTTP_

##### <a name="analysis"></a>Análisis

Desea ver las pequeñas secuencias de medios HTTP como sea posible. Si tiene secuencias que atraviesan su proxy, consulte con su equipo de redes para asegurarse de que se encuentran las exclusiones apropiadas para que los clientes se enruten directamente a teams o a las subredes de multimedia de Skype empresarial online.

Si solo tiene un proxy de Internet en su organización, compruebe las [direcciones URL y las exclusiones de intervalos de direcciones IP de Office 365](https://aka.ms/o365ips). Si hay más de un proxy de Internet configurado en su organización, use el subinforme HTTP para aislar qué compilación o subred se verá afectada.

Para las organizaciones que no pueden eludir el proxy, asegúrese de que el cliente de Skype empresarial está configurado para iniciar sesión correctamente cuando se encuentra detrás de un proxy, como se describe en el artículo, [Skype empresarial debe usar Proxy Server para iniciar sesión en lugar de probar la conexión directa](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Investigaciones de proxy HTTP

Este informe identifica los edificios y subredes específicos que están contribuyendo al uso de HTTP.

> [!IMPORTANT]
> Disponer de un [archivo de creación](#building-mapping) válido cargado hace que sea más fácil distinguir correctamente entre las transmisiones de audio externas al analizar el uso del proxy.

> [!NOTE]
> Asegúrese de ajustar el filtro de año mensual al mes en curso. Seleccione **Editar**y ajustar **mes del año** para guardar el nuevo mes predeterminado.

![Sreen captura de un informe de uso de proxy HTTP por construcción y subred](media/qerguide-image-httpproxyusage.png)

_Ilustración 29: uso de proxy HTTP por construcción y subred_

##### <a name="remediation"></a>Corrección

Le [recomendamos](proxy-servers-for-skype-for-business-online.md) que Evite siempre los servidores proxy de Skype empresarial y Teams, especialmente el tráfico de medios. Los servidores proxy no hacen que Skype empresarial sea más seguro, ya que su tráfico ya está cifrado. Los problemas relacionados con el rendimiento pueden introducirse en el entorno a través de la latencia y la pérdida de paquetes. Problemas como estos provocarán una experiencia negativa con el audio, el vídeo y la pantalla compartida, en el que son esenciales las secuencias en tiempo real.

La causa más común del uso de HTTP es que faltan reglas de excepción en los servidores proxy. Mediante el edificio o la subred proporcionados, puede determinar rápidamente qué proxy debe configurarse para la omisión de medios.

Compruebe que los [FQDN de Office 365](https://aka.ms/o365ips) necesarios están en la lista blanca en el proxy.

Para obtener más información sobre el uso de proxies con Skype empresarial online y Teams, consulte [este artículo](proxy-servers-for-skype-for-business-online.md).

## <a name="endpoint-investigations"></a>Investigaciones de extremo

Esta sección se centra en las tareas de informes sobre las versiones de cliente y el uso de dispositivos certificados. Los informes están disponibles para esquematizar el uso de las versiones de cliente, el tipo de cliente, los dispositivos de captura y los drivers (micrófono), los dispositivos de captura de vídeo y las versiones de proveedores y controladores de Wi-Fi.

> [!NOTE]
> En esta guía no se tratan todos los informes incluidos en las plantillas; sin embargo, siguen aplicándose los métodos de investigación explicados a continuación. Para obtener más información, consulte la descripción del informe individual.

### <a name="client-versions"></a>Versiones de cliente

Los informes de este espacio se centran en identificar las versiones de cliente de Skype empresarial en uso y su volumen relativo en el entorno.

> [!IMPORTANT]
> Actualmente, los clientes de equipos se distribuyen y actualizan automáticamente a través de la red de entrega de contenido de Azure y el servicio lo mantendrá actualizado. La preparación de los clientes y las actividades de investigación no son aplicables a los equipos.

> [!Important]
> A menos que excluya los datos de los participantes federados, estos informes incluirán telemetría de cliente de puntos de conexión federados. Para excluir puntos de conexión federados, debe agregar un [filtro de consulta](#query-filters) para el segundo identificador de inquilino establecido en el identificador de [inquilino](#tenant-id)de su organización. Como alternativa, puede usar un [filtro de URL](#url-filter) para excluir la telemetría de participantes federados.

> [!NOTE]
> Asegúrese de ajustar el filtro de año mensual al mes en curso. Seleccione **Editar**y ajustar **mes del año** para guardar el nuevo mes predeterminado.

![Captura de pantalla del informe de cliente y dispositivos](media/qerguide-image-clientversionreport.png)

_Figura 30-informe de versión del cliente_

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

-   [Información de versión para las actualizaciones de Office ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Historial de actualizaciones de Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
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
> A menos que excluya los datos de los participantes federados, estos informes incluirán telemetría de cliente de puntos de conexión federados. Para excluir puntos de conexión federados, debe agregar un filtro de consulta para el **segundo identificador de inquilino** establecido en el [identificador de inquilino](#tenant-id)de su organización. Como alternativa, puede usar un [filtro de URL](#url-filter) para excluir la telemetría de participantes federados.

> [!NOTE] 
> Asegúrese de ajustar el filtro de año mensual al mes en curso. Seleccione **Editar**y ajustar **mes del año** para guardar el nuevo mes predeterminado.

> [!Note]
> Es posible que se muestre al ver este informe que vea el mismo dispositivo que se ha notificado varias veces. Esto se debe a la forma en que se informa al producto del CQD. Las diferencias en el hardware y la configuración regional del sistema operativo causan diferencias en el modo en que se notifican los datos del dispositivo.

![Captura de pantalla del informe dispositivos (micrófono)](media/qerguide-image-devicesmicrophone.png)

_Figura 31-informe de dispositivos (micrófono)_

##### <a name="remediation"></a>Corrección

Por lo general, tendrá que descubrir y salir de los dispositivos no certificados y reemplazarlos con dispositivos certificados. Algunas consideraciones al revisar los informes de dispositivos incluyen:

-   ¿Los dispositivos están en uso certificados para Teams y Skype empresarial? 
-   Puede identificar los usuarios de un dispositivo específico a través de [análisis de llamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Asegúrate de que tengan los drivers más recientes del dispositivo y de que el dispositivo no esté conectado a través de un concentrador USB o una estación de acoplamiento. 
-   ¿Cuántas versiones diferentes de varios drivers están en uso? ¿Se les revisan regularmente? Asegurarse de que los drivers de audio, vídeo y Wi-Fi se revisan regularmente le ayudarán a eliminarlos como fuente de problemas de calidad y hacer que la experiencia del usuario sea más predecible y coherente.

##### <a name="audio"></a>Audio

La siguiente tarea es determinar el uso general de los [dispositivos de audio certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Recomendamos que al menos 80 por ciento de todas las transmisiones de audio usen un dispositivo de audio certificado. Para ello, se recomienda exportar el informe de dispositivos de micrófono a Excel para calcular el uso de los dispositivos certificados o aprobados. Normalmente, las organizaciones conservan una lista de todos los dispositivos aprobados, por lo que filtrar y ordenar los datos debería ser sencillo.

##### <a name="video"></a>Vídeo

Los drivers de video son importantes para mantenerte actualizado. Asegurarse de que las tarjetas de vídeo se revisan regularmente le ayudará a excluir los drivers de video como fuente de baja calidad para las transmisiones de video. El uso de [dispositivos de video certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) le ayudará a garantizar una experiencia de usuario fluida y de alta calidad. Se prefieren los dispositivos de vídeo que admiten la codificación nativa H. 264, para reducir el uso de la CPU durante las videoconferencias.

##### <a name="wi-fi"></a>Wi-Fi

Además, los drivers Wi-Fi también necesitan parches de forma regular y deben incluirse en la estrategia de administración de revisiones. Muchos problemas de calidad pueden corregirse manteniendo los drivers Wi-Fi actualizados. Para obtener más información sobre cómo optimizar su infraestructura Wi-Fi, consulte [este artículo sobre la planificación de Wi-Fi](/skypeforbusiness/certification/networking-wifi).

## <a name="appendix"></a>Apéndice 

### <a name="office-365-network-connectivity-principles"></a>Principios de conectividad de red de Office 365

Antes de empezar a planificar la red para la conectividad de red de Office 365, es importante comprender los principios de conectividad para administrar de forma segura el tráfico de Office 365 y obtener el mejor rendimiento posible. El artículo siguiente le ayudará a comprender las directrices más recientes para optimizar de manera segura la conectividad de red de Office 365:

[Principios de conectividad de red de Office 365](https://aka.ms/pnc)

### <a name="planning-for-wi-fi"></a>Planificación de Wi-Fi

El enfoque de Microsoft para impulsar la calidad y la agilidad de las redes inalámbricas viene en tres partes: Planeación de principio a fin, procedimientos recomendados para la implementación y mantenimiento y operaciones proactivos. Esta breve descripción de la solución le guiará a través de este proceso para garantizar una experiencia de Skype empresarial inalámbrica de categoría empresarial:

[Garantizar una experiencia de Skype empresarial inalámbrica de clase empresarial](https://www.microsoft.com/download/details.aspx?id=47257)

### <a name="lync-networking-guide"></a>Guía de redes de Lync

Para obtener más información sobre los equipos y los conceptos de redes de Skype empresarial y fundamento de su importancia a la calidad, la [Guía de redes de Lync Server 2013](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) sigue vigente.

### <a name="network-performance-requirements"></a>Requisitos de rendimiento de red

La calidad de los medios en tiempo real (audio, vídeo y uso compartido de aplicaciones) en IP se ve enormemente afectado por la calidad de la conectividad de red completa. Para lograr equipos óptimos o la calidad de los medios de Skype empresarial, su red debe cumplir con las siguientes métricas de rendimiento de red.

_Tabla 12: requisitos de rendimiento de red_

| Métrica                            | Cliente a Microsoft Edge           | Borde del cliente a Microsoft Edge    |
|-----------------------------------|------------------------------------|------------------------------------|
| Latencia (unidireccional)                 | \<50 ms                            | \<30 ms                            |
| Latencia (RTT o tiempo de ida y vuelta) | \<100 ms                           | \<60 ms                            |
| Pérdida de paquetes en ráfagas                 | \<10% durante cualquier intervalo de 200-ms   | \<1% durante cualquier intervalo de 200-ms    |
| Pérdida de paquetes                       | \<1% durante cualquier intervalo de 15-sec    | \<0,1% durante cualquier intervalo de 15-sec  |
| Vibración de llegada entre paquetes       | \<30 ms durante cualquier intervalo de 15-sec | \<15 ms durante cualquier intervalo de 15-sec |
| Reordenación de paquetes                    | \<0,05% de paquetes desordenados       | \<0,01% de paquetes desordenados      |

Para obtener más información, vea [este artículo sobre la calidad de medios y el rendimiento](https://aka.ms/performancerequirements) de la red de Teams y Skype empresarial online.

### <a name="other-resources"></a>Otros recursos

#### <a name="building-data-file"></a>Generando archivo de datos

-   [Activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype empresarial online](turning-on-and-using-call-quality-dashboard.md)

#### <a name="cqd-training"></a>Aprendizaje de CQD

-   <https://aka.ms/sof-cqd>

-   [Introducción a](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) la guía y el taller de CQD

-   [Dimensiones y medidas disponibles en el Panel de calidad de llamadas](https://aka.ms/cqd-dm)

### <a name="call-analytics-training"></a>Aprendizaje de análisis de llamadas

-   [Presentación de análisis de llamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurar el Análisis de llamadas](set-up-call-analytics.md)

-   [Diferencia entre el análisis de llamadas y el Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

-   [Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

### <a name="call-analytics-support"></a>Soporte técnico de análisis de llamadas

-   Comunidad: [programa de Skype para empresas Preview](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

### <a name="devices"></a>Dispositivos

-   [Catálogo de soluciones de Skype para empresas & equipos de PC](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Informes de inquilino

-   [Paquete de contenido de adopción de Office 365](https://www.microsoft.com/microsoft-365/blog/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Análisis de uso de Microsoft 365](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)

-   [Creación de informes en Skype Empresarial Online](/SkypeForBusiness/skype-for-business-online-reporting/skype-for-business-online-reporting)

-   [Informes de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)

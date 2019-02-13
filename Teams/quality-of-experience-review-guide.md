---
title: Guía de revisión de la experiencia de calidad de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guía para analizar el rendimiento de medios en tiempo real para Microsoft Teams utilizando el panel de calidad de llamadas (CQD).
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b19fe5dce5c728880c54321e5d6dbb1901d0aac
ms.sourcegitcommit: 327fe807b461aff18b06449f06b9e51ce393c4bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "29964453"
---
# <a name="quality-of-experience-review-guide"></a>Calidad de experiencia consulte la Guía

<!-- Note that this link to the Word doc is intentionally NOT the aka.ms/qerquide link -->Esta guía es acerca de la fase de valor de unidad para Microsoft Teams y Skype para profesionales en línea. Puede [descargar una versión de Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) de esta guía.

## <a name="introduction"></a>Introducción

Para que el mayor impacto sobre cómo mejorar la experiencia del usuario, las organizaciones necesitan que controle las áreas clave que se muestran en la ilustración siguiente. Áreas adicionales incluyen la identificación de las tareas operativas, establecimiento de los objetivos de métricas de calidad, determinar las métricas para utilizar para medir el éxito organizativo y áreas de investigación de restricción según sea necesario.


![Áreas clave para la calidad de la experiencia de usuario incluyen audio, confiabilidad, encuestas al usuario, dispositivos y clientes.] (media/qerguide-image-keyareas.png "Áreas clave para la calidad de la experiencia de usuario incluyen audio, confiabilidad, encuestas al usuario, dispositivos y clientes.")

_En la figura 1 - áreas operativas clave tratadas a lo largo de esta guía_

Al continuamente evaluar y solucionar relativos a las áreas que se describen en esta guía, puede reducir su potencial de afectar negativamente a la calidad de la experiencia de los usuarios. Mayoría de experiencia de usuario los problemas encontrada en una implementación puede agruparse en las siguientes categorías:

-   Configuración de firewall o proxy incompleto
-   Cobertura Wi-Fi deficiente
-   Ancho de banda insuficiente
-   VPN
-   Controladores y versiones de cliente incoherentes o no actualizada
-   Dispositivos de audio integrados o no optimizados
-   Subredes problemáticas o dispositivos de red

A través de planear y diseñar correctamente antes de implementar los equipos o Skype para profesionales en línea, puede reducir la cantidad de esfuerzo que será necesarios para mantener experiencias de alta calidad.

Esta guía se centra en usar el panel de calidad de llamadas (CQD) Online como la principal herramienta para notificar e investigar cada área, con especial hincapié en audio para maximizar la adopción y el impacto. Todas las mejoras realizadas a la red para mejorar la experiencia de audio traducirá también directamente a las mejoras en uso compartido de escritorio y de vídeo.

Para acelerar la evaluación, se proporcionan [dos plantillas CQD curated](https://aka.ms/qertemplates) : uno es para la administración de todas las redes y la otra se filtra para administrada sólo redes (internas). Aunque los informes de la plantilla de todas las redes están configurados para mostrar información de la red y la creación, aún se pueden usar mientras trabaja hacia la recopilación y la carga de información de creación. Cargar información en CQD de compilación, habilita el servicio mejorar la creación de informes mediante la adición de información de creación, la red y la ubicación personalizada mientras diferenciar interno de subredes externas. Para obtener más información, vea [asignación de creación](#building-mapping) más adelante en esta guía.

### <a name="intended-audience"></a>Público objetivo

Esta guía está destinada a ser utilizada por las partes interesadas de clientes y socios con funciones como arquitecto o jefe de colaboración, consultor, especialista en administración y adopción de cambio, jefe de soporte técnico y ayuda de asistencia al cliente, potenciales de red, potenciales de escritorio y Admin de TI.

Esta guía también está pensada para usarse por la champion(s) calidad designada. Para obtener más información, vea [la función de los pesos pesados calidad](4-envision-plan-my-service-management.md#the-quality-champion-role).

## <a name="prerequisites"></a>Requisitos previos

Antes de usar a esta guía, asegúrese de que tiene el inquilino adecuados [roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) asignados por lo que puede tener acceso a CQD.

-   **Función de administrador Global de office 365:** Tiene acceso a todas las características administrativas en el conjunto de aplicaciones de Office 365 de servicios en el plan, incluyendo Skype para la empresa.

-   **Skype para el rol de administrador empresarial:** Configura Skype para la empresa para su organización y puede ver todos los [informes de actividad](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración de Office 365. Esta función es necesaria, incluso si se implementación sólo los equipos.

Como alternativa, puede asignar la siguiente función a una cuenta de usuario de Office 365 para permitir el acceso a sólo las características de informes.

-   **Lector de informes:** Puede ver todos los [informes de actividad](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración de Office 365, los informes desde el [paquete de contenido de Office 365 adopción](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)e informes CQD.

## <a name="what-is-quality"></a>¿Qué es la calidad?

Al hablar de calidad en los equipos y Skype para la empresa, es importante definir el término para lograr una comprensión común. Calidad, tal como se define aquí, es una combinación de la experiencia de usuario y las métricas de servicio.

<!-- Note: need to update graphic-->
Métricas de servicio ![se componen de relación de secuencia deficiente, confiabilidad, extremos y a los dispositivos y las versiones de cliente. La experiencia del usuario se compone de la percepción del usuario de la calidad del servicio.] Métricas de servicio (media/qerguide-image-whatisquality.png "se componen de relación de secuencia deficiente, confiabilidad, extremos y a los dispositivos y las versiones de cliente. La experiencia del usuario se compone de la percepción del usuario de la calidad del servicio.")

_La figura 2: ¿qué es la calidad?_

### <a name="service-metrics"></a>Métricas de servicio

Métricas de servicio constan de las medidas específicas basadas en cliente. Durante cada llamada, el cliente recopila información de telemetría acerca de la llamada y envía un informe al final de cada llamada que se puede tener acceso más adelante a través de CQD o [Llame al análisis](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Estas métricas incluyen:

-   Tasa de secuencia deficiente
-   Porcentaje de errores de instalación
-   Porcentaje de errores de entrega


#### <a name="poor-stream-rate"></a>Tasa de secuencia deficiente

La tasa de secuencia deficiente (PSR) representa el porcentaje general de la organización de secuencias que tienen una calidad deficiente. Esta métrica está pensada para resaltar áreas donde puedan concentrarse en esfuerzo tengan el impacto más sólido hacia reducir este valor y mejora de la experiencia del usuario, que es la razón por la organización [administrados redes](#managed-vs-unmanaged-networks) son el foco principal cuando se mira región Determinada. Los usuarios externos son importantes demasiado, pero difiere de investigación de forma organizativa. Considere la posibilidad de proporcionar procedimientos recomendados para los usuarios externos e investigar las llamadas externas independientemente de la organización global.

La medida real en CQD varía según la carga de trabajo, pero para los fines de la revisión de la experiencia de calidad se centran principalmente en la medida de _Porcentaje de Audio deficiente_ . Región Determinada se compone de los cinco promedios de métrica de red que se describen en la siguiente tabla. Para que un objeto stream se clasifican como deficiente, sólo una métrica necesita supere el umbral definido. Para obtener más información sobre el proceso de clasificación de secuencia, vea [este artículo](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> CQD proporciona "Deficiente debido a..." las medidas mejor comprender qué condición provocó la secuencia se clasifican como deficientes.


_Tabla 1 - métricas de un servicio deficiente_

| Promedio de métrico     | Descripción     | Experiencia de usuario |
|-------------|-----------------|-----------------|
| Vibración \>30 ms        | Éste es el cambio promedio de retraso entre envíos sucesivos de paquetes. Los equipos y Skype para la empresa pueden adaptarse a algunos niveles de vibración a través de almacenamiento en búfer. Es sólo cuando la vibración supera el almacenamiento en búfer que un participante avisos de los efectos de vibración.      | Los paquetes que llegan a diferentes velocidades provocarán voz de un altavoz se oye robótica.   |
| Tasa de pérdida de paquetes \>0,1 o 10%        | A menudo se define como un porcentaje de paquetes que se pierden. Pérdida de paquetes afecta directamente a la calidad de audio: desde pequeñas, individual los paquetes perdidos que no tienen casi afectar a las pérdidas de ráfagas opuesta que causa el audio para recortar completamente.     | Los paquetes se perdidos y que no llegan a su destino previsto provocarán diferencias en los medios, resultantes en palabras y sílabas perdidas y entrecortados vídeo y uso compartidos. |
| Tiempo de ida y vuelta \>500 ms        | Esto es el tiempo necesario para obtener un paquete IP de punto A punto b y volver al punto A. Este retraso de propagación de red está asociado a la distancia física entre los dos puntos y la velocidad de la luz e incluye una sobrecarga adicional realizada por los diversos dispositivos en la ruta de acceso de red.      | Los paquetes tarda mucho tiempo para llegar a su destino causar un efecto transmisor-receptor portátil.   |
| Promedio de degradación de NMOS \>1.0         | Promedio de degradación de [Puntuación de opinión Media de red (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) de la secuencia. Representa cómo mucho la pérdida de la red y vibración ha afectado la calidad del audio recibido que ha provocado el NMOS colocar por más de un punto. | Esto es una combinación de vibración, la pérdida de paquetes, y, en menor grado, aumenta el tiempo de ida y vuelta. El usuario puede haber una combinación de estos síntomas.   |
| Relación media de muestras ocultas \>7% o 0,07 | Relación media del número de marcos de audioconferencias con muestras ocultas generadas por la pérdida de resolución de problemas y el número total de marcos de audioconferencias. Un ejemplo de audio oculto es una técnica que se utiliza para emparejar la abrupta transición que normalmente podría deberse a paquetes de red perdidos.      | Los valores altos indican que niveles significativos de ocultación de pérdida se han aplicado y esperó audio distorsionado o pierden.     |

#### <a name="setup-failure-rate"></a>Porcentaje de errores de instalación

La tasa de errores del programa de instalación, que también se conoce como la medida de _Total de llamadas porcentaje de errores de instalación_ en CQD, es el número de secuencias de donde se no se pudo establecer la ruta de acceso de medios entre los extremos en el inicio de la llamada.

Esto representa cualquier secuencia de medios que no se ha podido establecerse. Dada la gravedad del impacto en la experiencia del usuario que se mide aquí, el objetivo es reducir este valor para como cercanos a cero como sea posible. Un valor alto para que esta métrica es más frecuente en las nuevas implementaciones con reglas de firewall incompletos que una implementación consolidada, pero sigue siendo importante inspeccionar de forma regular.

Esta métrica se calcula restando el número total de secuencias que no se pudo establecer dividido por el número total de secuencias que han enviado un registro de detalles de llamada correcta (CDR):

-   **Porcentaje de errores de instalación** = llamada Total del programa de instalación con error secuencia recuento / CDR Total disponible en secuencia de recuento

#### <a name="drop-failure-rate"></a>Porcentaje de errores de entrega

La tasa de errores de entrega, en caso contrario, conocida como la medida de _Total de llamadas colocada porcentaje de errores_ en CQD, es el porcentaje de secuencias correctamente establecidas donde la ruta de acceso de medios no finaliza correctamente.

Esto representa cualquier secuencia de medios que terminó de forma inesperada. Aunque el impacto de esto no es tan grave como una secuencia que no se pudo establecer, afectará negativamente la experiencia del usuario. Gotas de medios repentino y frecuentes no sólo pueden tener un impacto grave en la experiencia del usuario, pueden provocar que la necesidad de los usuarios para volver a conectar, lo que produce una pérdida en la productividad.

La métrica se calcula restando el número total de secuencias descartados dividido por la cantidad total de secuencias que configurado correctamente:

-   **Porcentaje de errores de colocar** = llamada Total colocada recuento de secuencia / llamada Total el programa de instalación se ha realizado correctamente el recuento de secuencia

### <a name="define-your-target-metrics"></a>Definir las métricas de destino

En esta sección se describe algunas de las métricas de servicio principal que usamos para evaluar cómo servicios experimentan mantenimiento. Al continuamente evaluar y que dirigen los esfuerzos para mantener estas métricas debajo de sus destinos definidos, ayudaremos a asegurarse de que los usuarios de experimentan de calidad de la llamada coherente y confiable. Para comenzar, se proporcionan los siguientes objetivos.

_Tabla 2 - medidas de evaluación de estado de destino principales_
<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo de red</th><th rowspan="1">Objetivos de calidad</th><th colspan="2">Objetivos de confiabilidad</th></tr>
<tr><th>Tasa de audio Stream deficiente</th><th>Porcentaje de errores de instalación</th><th>Porcentaje de errores de entrega</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>% de 2.0</td><td>0,5%</td><td>% de 2.0</td></tr>
<tr><td>General</td><td>% de 3.0</td><td>1.0%</td><td>% de 3.0</td></tr>
<tr><td rowspan="5"><strong>Conferencia</strong></td><td>Interno</td><td>% de 2.0</td><td>0,5%</td><td>% de 2.0</td></tr>
<tr><td>Con cable interno</td><td>1.0%</td><td>0,5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi 5 GHz interno</td><td>1.0%</td><td>0,5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi 2,4 GHz interno</td><td>% de 4.0</td><td>0,5%</td><td>% de 2.0</td></tr>
<tr><td>General</td><td>% de 2.0</td><td>0,5%</td><td>% de 3.0</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>% de 2.0</td><td>0,5%</td><td>% de 2.0</td></tr>
<tr><td>Con cable, Wi-Fi 5 GHz interno</td><td>1.0%</td><td>0,5%</td><td>1.0%</td></tr>
<tr><td>Con cable, Wi-Fi 5 GHz general</td><td>% de 2.0</td><td>1.0%</td><td>1.0%</td></tr>
<tr><td>General</td><td>% de 2.0</td><td>1.0%</td><td>% de 3.0</td></tr>
</table>


Es importante discutir y definir los objetivos de la organización para cumplir los objetivos del negocio.

### <a name="user-experience"></a>Experiencia de usuario

Análisis de la experiencia del usuario es más que science, debido a que las métricas se recopilan aquí no siempre significa que hay un problema con la red o servicio, pero en su lugar, simplemente indican que el usuario percibe un problema. Microsoft ofrece un mecanismo de encuesta integrada, conocido como tasa Mis llamadas (RMC): para ayudar a medir la experiencia global del usuario. RMC le ayudarán a responder a las preguntas siguientes desde la perspectiva de los usuarios:

-   ¿Sabe cómo usar la solución?
-   ¿Es la solución intuitiva y fácil de usar, y es compatible con las necesidades de comunicación diarias?
-   ¿La solución me ayuda a realizar mi trabajo?
-   ¿Qué es mi percepción general de la solución?
-   ¿Puedo usar la solución en cualquier momento en el tiempo, independientemente de donde estoy?
-   ¿Puedo configurar y mantener una llamada?

#### <a name="rate-my-call"></a>Tasa de mi llamada 

Tasa de Mis llamadas entonces se basa en equipos y Skype para la empresa y se configura automáticamente para que se muestre para el participante después de que uno en todas las llamadas de 10, o 10 por ciento. En este breve encuesta pregunta al usuario para valorar la llamada y proporcionar un contexto poco de por qué la calidad de la llamada es posible que han sido deficiente. Una clasificación de uno o dos se considera mala, es buena tres o cuatro y cinco es excelente. Aunque es un poco de un indicador al retraso, esto es una métrica útil para descubrir problemas que pueden pasar por alto las métricas de servicio.

> [!Note]
> Hasta que los usuarios conozcan para responder a encuestas RMC por darnos su opinión buena además de las respuestas incorrectos, normalmente volveremos como muy negativos. La mayoría de los usuarios sólo responden cuando es mala calidad de la llamada. Por este motivo, los informes RMC podrían ser asimétrica hasta el lado deficiente incluso mientras las métricas de servicio son una buena opción.

Puede usar CQD para informar sobre las respuestas del usuario RMC, y se incluyen informes de muestra en la plantilla de CQD. Sin embargo, no se analizan detalladamente en esta guía. Para obtener más información sobre RMC en Skype para profesionales en línea y orientación para indicar a los usuarios dar respuestas RMC útiles, consulte [esta entrada de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

#### <a name="client-and-device-readiness"></a>Preparación de clientes y dispositivos

Se necesita una estrategia de cliente y dispositivo sólida para ayudar a garantizar que los usuarios tengan una experiencia de usuario coherente y positiva. Unos principios claves de cada estrategia de preparación para la unidad.

##### <a name="client-readiness"></a>Preparación del cliente

Una estrategia de preparación de cliente seguro garantiza que los usuarios están ejecutando la versión más reciente del cliente disfrutando de la mejor experiencia posible. Microsoft revisiones rutinariamente el Skype para clientes empresariales; asegurarse de que la mantenga actualizados en su entorno es vital para el éxito general. También es importante recordar a red de revisión, vídeo, USB y los controladores de audioconferencias, porque está a menudo se pasa por alto y pueden afectar a la experiencia del usuario. Considere la posibilidad de agregar vídeo en red, Wi-Fi, USB y los controladores de audioconferencias para el proceso de administración de revisiones actual.

Se recomienda que no permita que sus versiones de cliente se dividen por más de seis meses. Si está utilizando Office Click-to-Run, está ya que se mantiene actualizados por el servicio. Use las incluye [las versiones de cliente](#client-versions), tal como se describe más adelante en esta guía, para ayudarle con este proceso. También puede aprovechar los informes de ejemplo tasa Mis llamadas para mejorar aún más la estrategia de preparación del cliente.

> [!IMPORTANT]
> Actualmente, los clientes de los equipos se distribuye y se actualizan automáticamente a través de la red de entrega de contenido de Azure y se mantengan actualizados por el servicio. Debido a esto, preparación de cliente y las actividades de investigación no son aplicables a los equipos.


##### <a name="device-readiness"></a>Preparación de dispositivo

No hay una estrategia de único puede afectar a la experiencia del usuario más que la estrategia de preparación del dispositivo. La mayoría de las organizaciones están satisfechos quitar los dispositivos innecesarios (por ejemplo, teléfonos de escritorio u otros dispositivos de audioconferencias dedicadas) de los usuarios y suele ser una justificación del negocio principales para cambiar a los equipos o Skype para la empresa. Sin embargo, esas organizaciones mismas dudan a veces para proporcionar dispositivos de sustitución, incluso si esos dispositivos son menos costosas. Equipos portátiles moderna y PCs, aunque dispongan de micrófono y altavoz, no están optimizados para voz de clase empresarial sobre IP (VoIP). A menudo esto crea una mala experiencia para todos los participantes, especialmente si el altavoz está en un entorno con mucho ruido. Programa de certificación de dispositivo de Microsoft se asegura de que, cuando un usuario participa en una llamada telefónica mediante el uso de cualquier dispositivo certificado para los equipos o Skype para la empresa, genera una experiencia que es superior de un dispositivo no certificados. 

Siempre se recomienda que los equipos y Skype para usuarios profesionales usar un certificado de auriculares con micrófono o altavoz cuando participa en una llamada de voz a través del cliente de escritorio. Para obtener más información acerca de los dispositivos de certificación de Microsoft, revise estos artículos sobre el [programa de certificación](/SkypeForBusiness/certification/overview) y ver el [catálogo de soluciones de socios](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Use el [informe de dispositivos](#devices), que se describen más adelante en esta guía, para obtener ayuda con la administración de los dispositivos.


### <a name="categories-of-quality"></a>Categorías de calidad

El éxito de una implementación de alta calidad y confiable en marcha depende de la exactitud operativas de creación. En concreto, preste especial atención a las tres categorías que se muestra en la figura siguiente; Estos son el enfoque de esta guía:

-   **Red:** Calidad de audio centrado en la métrica de relación de secuencia deficiente (PSR), el uso TCP, subredes con cable e inalámbricas e identificar el uso de servidores proxy HTTP y VPN.

-   **Extremos:** Dispositivos de audio y versiones de cliente (Skype para la empresa sólo).

-   **Administración de servicios:** Esta categoría compone de dos secciones:

    -   En primer lugar, es responsabilidad de Microsoft para administrar y mantener los equipos y Skype para servicios en línea de negocio.

    -   En segundo lugar las tareas que debe administrar su organización para garantizar un acceso confiable a del servicio, como actualizar la información de creación y mantenimiento de firewalls para nuevas direcciones IP de Office 365 como infraestructura se agrega al servicio.

![Las categorías de calidad de una organización: servicio de administración, extremos y la red.] (media/qerguide-image-categories.png "Las categorías de calidad de una organización: servicio de administración, extremos y la red.")

_La figura 3 - categorías críticas para los equipos y Skype para la implementación empresarial en línea_

El gráfico siguiente describen las tareas que debe ejecutar para cada categoría. Le recomendamos que ejecute estas tareas una vez por semana, como mínimo.

La primera vez que realice estas tareas le llevará más esfuerzo que las iteraciones posteriores, debido a que muchas de estas categorías requieren que validar las configuraciones de implementación. Una vez que haya alcanzado el estado que desea con las reuniones de los destinos que ha definido, llevar a cabo estas tareas le ayudará a mantener ese estado.

<!--  This is a net new graphic, never was included in the online article. OOPS! -->
![Lista de tareas semanales por categoría de calidad] (media/qerguide-image-tasks.png "Lista de tareas semanales por categoría de calidad")

#### <a name="service-management-tasks"></a>Tareas de administración de servicio

En un mundo de la nube en primer lugar, debe realizar ciertas tareas de administración de servicio para mantener experiencias de usuario de alta calidad. Estas tareas oscilar entre asegurarse de que hay suficiente ancho de banda ponerse en contacto con el servicio sin saturar vínculos de internet, validar que la calidad de servicio (QoS) en lugar de todas las áreas de la red administrada, y, por último: permanecer en la parte superior [rangos IP de Office 365 en los servidores de seguridad](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Tareas de red

Existen dos categorías de tareas de red: confiabilidad y calidad. Confiabilidad se centra en la medición de la capacidad del usuario para realizar llamadas correctamente y permanecer conectado. Calidad se centra en la telemetría agregada enviada a los equipos y Skype para profesionales en línea por el cliente del usuario durante la llamada y después de haya terminado. 

Dado el impacto crítico que disponga de confiabilidad en la experiencia del usuario, es importante empezar a evaluar e investigar estas métricas antes de comenzar con la calidad. 

#### <a name="endpoints-tasks"></a>Tareas de extremos

La tarea principal en esta categoría está validando qué versiones de cliente ejecutan Skype para la empresa en generaciones de escritorio de los últimos seis meses, para asegurarse de que los usuarios reciben la ventaja de las optimizaciones continuas realizadas a la Skype para el cliente de escritorio empresarial. Además, esto simplifica las tareas de administración de cliente general y proporciona una experiencia de usuario coherente.

La otra área importante es qué dispositivos son frecuentes en su implementación de supervisión y que dirigen el uso de dispositivos certificados para proporcionar la mejor experiencia de usuario.


> [!IMPORTANT]
> Actualmente, los clientes de los equipos se distribuye y se actualizan automáticamente a través de la red de entrega de contenido de Azure y se mantengan actualizados por el servicio. Preparación de cliente y las actividades de investigación no son aplicables a los equipos.

## <a name="cqd-basics"></a>Conceptos básicos CQD

En esta sección se describe los aspectos básicos del trabajo con CQD. Se proporcionan directrices para los siguientes temas:

-   ¿Qué es CQD?
-   Expectativas con CQD
-   Buscar el identificador de inquilino
-   Creación de informes en los equipos de Microsoft frente a Skype para la empresa
-   En primer lugar frente a clasificaciones de segundo
-   Dimensiones, medidas y filtros
-   Secuencias frente a las llamadas
-   Llamadas de buena, deficientes y sin clasificar
-   Subredes comunes

Para obtener información más detallada sobre recursos de aprendizaje y recursos, consulte el [Apéndice](#other-resources).

### <a name="what-is-cqd"></a>¿Qué es CQD?

Use el panel de calidad de llamadas (CQD) para obtener información sobre la calidad de las llamadas realizadas mediante el uso de los equipos y Skype para servicios de negocios. CQD está diseñado para ayudar a Skype para profesionales y los equipos de los administradores y los ingenieros de red optimización la red y mantenerse al tanto de calidad, confiabilidad y la experiencia del usuario. CQD examina telemetría agregado para toda una organización donde patrones generales pueden convertirse en evidentes, lo que permite personal realizar las evaluaciones informadas y planear las actividades de corrección para maximizar el impacto. CQD proporciona informes de métricas que proporcionan una visión de calidad total, la confiabilidad y la experiencia del usuario.

> [!Note]
> CQD no contiene información de identificación personal (PII). PII es información que puede usar en su propio o con otra información para identificar, póngase en contacto con o busque a una sola persona, o para identificar a un individuo en contexto.

Esta guía le ayudará a comprender los conceptos básicos de CQD para ayudar a maximizar el impacto que puede realizar en la mejora de la experiencia de los usuarios con los equipos o Skype para profesionales en línea. Recursos adicionales de CQD pueden encontrarse en el [Apéndice](#other-resources).

### <a name="expectations-using-cqd"></a>Expectativas con CQD

CQD, aunque útil para analizar las tendencias y subredes, no siempre proporciona una causa específica para un escenario determinado. Es importante comprender esto y defina las expectativas correcta cuando se usa CQD:

-   CQD no ofrecerá la causa raíz para cada escenario.
-   CQD no contienen secuencias del sistema de teléfono o las conferencias de Audio.
-   CQD llamará a las áreas para una mayor investigación en función de las tendencias.
-   CQD no contiene ningún PII.

### <a name="report-editions"></a>Ediciones de informe

Hay dos ediciones de informe en CQD Online: resumen y detallado. Use el menú desplegable que se encuentra en la barra de color azul en la parte superior de la pantalla para abrir una edición de informe. El nombre de la edición de informe seleccionado se muestra en la parte superior de la pantalla.

-   Informes de resumen son estáticos y no se puede editar, descargado o exportado. 
-   Informes detallados son totalmente personalizables y se pueden descargar a un archivo CSV, exportado o clonar.

Para obtener una descripción completa de la diferencia entre las dos ediciones, vea [este artículo](turning-on-and-using-call-quality-dashboard.md).

![Menú desplegable con los informes de resumen seleccionado](media/qerguide-image-reportcategories.png)

_La figura 4 - categorías de informe CQD_

Los informes de resumen se dividen en cuatro categorías:

-   **Informes de resumen** se centran en analizar las tendencias de calidad con diaria, mensual y los informes de tabla para ayudarle a identificar subredes que tienen una calidad deficiente. Esta es la página de inicio de forma predeterminada al primero iniciar sesión CQD en línea.
-   **Informes de Location-Enhanced** se centran en analizar las tendencias de calidad según la información de ubicación. Para usar estos informes, debe haber cargado un archivo de creación.
-   **Informes de confiabilidad** se centran en analizar las tendencias de confiabilidad de audio, vídeo y basada en vídeo de pantalla de uso compartido (VBSS) y uso compartido de aplicaciones.
-   **Informes de calidad de experiencia** son una versión "simplificada de abajo" de las plantillas de QER detalladas, centrándose en las áreas clave para analizar la confiabilidad y calidad de audio.

### <a name="report-types"></a>Tipos de informe

Puede elegir entre dos tipos de informes en CQD, dependiendo de cómo desea ver los datos. Aunque esta guía no cubre los detalles de la creación de un tipo de informe sobre otra, las plantillas de QER CQD proporcionan una combinación de los informes de gráfico y tabla personalizables que puede utilizar:

-   Los informes de gráfico creación gráficos de barras gráficos para representar los datos en un formato visual. Los informes de gráfico mejor se usan para visualizar los datos a través de un período de tiempo determinado.
-   Informes de tabla son útiles para mirar las dimensiones y medidas individuales al exportar los informes a los archivos CSV para la manipulación en Microsoft Excel.

### <a name="tenant-id"></a>Identificador de inquilino

Algunos informes CQD requieren que incluir un filtro para el identificador del inquilino. Debido a la forma que CQD agrega datos, se incluye telemetría participante federado. Aunque esto puede resultar valiosa al analizar las tendencias, informes de cliente y dispositivo requieren que filtrar datos para un inquilino específico para excluir telemetría participante federado. Si no conoce su identificador de inquilino, puede usar uno de los métodos siguientes para encontrarlo.

> [!Note]
> Estos métodos requieren los permisos siguientes:<ul><li>Función de administrador global</li><li>Skype para el rol de administrador de negocio</li></ul>

#### <a name="azure-portal"></a>Portal de Azure

1.  Inicie sesión el portal de Microsoft Azure:<https://portal.azure.com>

2.  Seleccione **Azure Active Directory**.

3.  En **Administrar**, seleccione **Propiedades**. El identificador de inquilino se muestra en el cuadro **Identificador de directorio** .

#### <a name="azure-powershell"></a>PowerShell de Azure

1. [Instalar el módulo de administración de servicio de Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2. Abra una ventana de comandos de Windows Azure PowerShell y ejecute el siguiente script, escribir las credenciales de Office 365 cuando se le solicite: 

   ```
   Login-AzureRmAccount
   ```

3. El identificador de inquilino aparece en el resultado.

#### <a name="skype-for-business-online-admin-center"></a>Skype para el centro de administración en línea de negocio

1.  Vaya a <https://portal.office.com>.

2.  Inicie sesión con su cuenta profesional de administrador de inquilinos.

3.  Seleccione **Skype para la empresa** en **Centros de administrador**.

4.  El identificador de inquilino aparece como **Identificador de organización** en la página de bienvenida.

#### <a name="skype-for-business-online-using-powershell"></a>Skype para profesionales Online mediante PowerShell

1. [Configurar el equipo de Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Ejecute el siguiente comando:

   ```
   (Get-cstenant).tenantid
   ```

3. El identificador de inquilino se muestra como un GUID.

### <a name="teams-vs-skype-for-business"></a>Los equipos frente a Skype para la empresa

CQD puede informar sobre los equipos y Skype para telemetría empresarial. Sin embargo, puede haber ocasiones cuando desea desarrollar un informe que mirar telemetría equipos independiente de Skype para la empresa.

#### <a name="summary-reports"></a>Informes de resumen

Para modificar la página de informes de resumen para ver sólo los equipos o Skype para la empresa, seleccione el menú desplegable de **Filtro del producto** desde la parte superior de la pantalla y, a continuación, seleccione el producto que desee.

![Menú de lista desplegable que muestra la opción para filtrar los informes CQD por la carga de trabajo](media/qerguide-image-productfilter.png)

_La figura 5 - seleccionar un filtro de producto_

#### <a name="detailed-reports"></a>Informes detallados

Para filtrar todos los informes detallados, en la barra de explorador, anexe lo siguiente al final de la dirección URL:

```
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Ejemplo:**

```https://cqd.lync.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obtener más información acerca de los filtros de dirección URL, vea [informes de filtrado](#filtering-reports) más adelante en esta sección.

Para filtrar un informe detallado individual, agregue el filtro ``Is Teams`` para el informe y establecer en True o False. Para obtener más información, vea [informes de edición](#editing-reports) más adelante en esta sección.

![Agregar un filtro a un informe detallado.](media/qerguide-image-addteamsfilter.png)

_La figura 6 - agregar un filtro de Microsoft Teams a un informe_


### <a name="managed-vs-unmanaged-networks"></a>Recursos administrados frente a redes no administradas

De forma predeterminada, todos los extremos en CQD se clasifican como externa. Tan pronto como se presenta un archivo de creación, podemos empezar a mirar los datos administrados extremo. Como se explicó anteriormente, redes en CQD se definen como:

-   Una _administrada de red_, a menudo conoce como interno o dentro de, puede ser influenciado y controlado por la organización. Esto incluye la LAN interna, WAN remoto y VPN.
-   Una _red no administrada_, a menudo conoce como externo o fuera de, no puede ser influenciado o controlado por la organización. Un ejemplo de una red no administrada es una red de hotel o un aeropuerto.

### <a name="dimensions-measures-and-filters"></a>Dimensiones, medidas y filtros

Una consulta CQD bien formada contiene las tres de los siguientes parámetros:

-   **Dimensión:** ¿Cómo desea en los datos de tabla dinámica.

-   **Medida:** ¿Qué deseo informar sobre.

-   **Filtro:** ¿Cómo deseo reducir el conjunto de datos de la consulta devuelve.

Otra forma de analizar esto es que una _dimensión_ es la función de agrupación, una _medida_ es los datos que me interesa y un _filtro_ es cómo desea restringir los resultados a aquellos que son relevantes para la consulta.

Un ejemplo de una consulta con formato correcto es **deficiente secuencias Mostrarme [medir] por subred [dimensión] para 6 de creación [filtro]**. Para obtener más información, vea [las dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm).

### <a name="first-vs-second"></a>En primer lugar frente a segundo 

Muchas de las dimensiones y medidas en CQD se clasifican como primera o segunda. CQD no usar los campos de autor de la llamada y el destinatario, éstas han sido cuyo nombre ha cambiado _en primer lugar_ y el _segundo_ porque hay pasos intermedios entre el autor de la llamada y el destinatario de la llamada. La lógica siguiente determina qué extremo implicados se etiqueta como primer:

-   **Primer** siempre será un extremo de servidor (servidor de conferencia, el servidor de mediación etc.) si un servidor está involucrado en la secuencia o la llamada.

-   **Segundo** siempre será un extremo de cliente a menos que la secuencia se encuentra entre dos extremos de un servidor.

-   Si ambos extremos son del mismo tipo, la elección de los cuales es el primera se basa en orden interno de la categoría de agente de usuario. De este modo se asegura que el orden es coherente.

Para obtener más información acerca de cómo determinar el extremo de la primero o segundo cuando están ambos el mismo, vea [las dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Secuencia frente a la llamada

Es necesario comprender la diferencia entre una llamada y una secuencia correctamente elegir qué dimensiones o medidas que se utilizan en CQD. Aunque el enfoque principal del CQD es en secuencias, también están disponibles las medidas en función de llamada.

-   **Secuencia:** Existe una _secuencia de_ entre solo dos extremos. Hay sólo una secuencia para cada dirección, y dos secuencias son necesarias para la comunicación. Las secuencias son útiles para investigar los edificios, las redes o subredes. En algunos casos, llamada y stream se usan en nombre de la medida (por ejemplo, secuencia de llamada del programa de instalación o secuencia de llamada de texto). Estos aún se clasifican como secuencias.

-   **De llamadas:** Una _llamada_ es una agrupación de todas las secuencias de todos los participantes. Consta de una llamada de, como mínimo, dos secuencias. Una sola llamada tendrá al menos dos extremos, cada uno con un mínimo de una secuencia.

Para obtener instrucciones adicionales sobre si la dimensión o medida es cómo hacer referencia a una llamada o una secuencia, vea [las dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Llamadas de buena, deficientes y sin clasificar

Una llamada se categoriza ya sea como una buena, deficiente o sin clasificar. Hablemos un poco para hablar de cada uno de ellos con más detalle.

-   **Buena o mala:** Una llamada buena o mala consta de una llamada que contiene un conjunto completo de las métricas de servicio, para que un informe de QoE completo generado y recibido por el servicio. Determinar si una secuencia es buena o mala es descritas [anteriormente en esta guía](#poor-stream-rate).

-   **Sin clasificar:** Una secuencia sin clasificar no contiene un conjunto completo de las métricas de servicio. Pueden ser llamadas breves, normalmente menos de 60 segundos: donde no se ha podido calcular promedios y no se genera un informe de QoE. La razón más común para las llamadas a ser sin clasificar es que hubo muy poca o ninguna utilización de paquetes. Un ejemplo de esto sería un participante que se une a una reunión en silencio y nunca habla. El participante es recibir, pero no transmitir, medios. Sin medios que se transmiten, no habrá ningún métricas disponibles para CQD a usar para clasificar secuencia de medios de salida del extremo.

Para obtener más información sobre el proceso de clasificación de secuencia, vea [este artículo](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Subredes comunes

Subredes comunes son subredes privadas específicas que se usan por hoteles, redes particulares, puntos de conexión y áreas similares. Estas subredes son difíciles de evaluación de errores debido a su uso extendido. Si su organización utiliza una de estas subredes comunes, se recomienda que mueva esa red a otra subred. Esto hará que sea más fácil de informes en CQD. Cuando se ha indicado, se han configurado para excluir estas subredes para eliminar el como el origen de mala calidad de informes en la plantilla de todas las redes. Subredes comunes se definen a continuación; su impacto variarán según la organización.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Al investigar una red administrada que usa una subred común, debe usar la dimensión de la segunda dirección IP Local reflexiva a subredes de grupo. Esta dimensión contiene la dirección IP pública del extremo.

## <a name="cqd-online"></a>CQD en línea

En esta sección se describe los aspectos básicos de acceso a CQD. Se proporcionan directrices para los siguientes temas:

-   Obtener acceso a CQD en línea
-   Introducción a CQD
-   Edición de informes en CQD
-   Filtrado de informes en CQD
-   Importación de informes en CQD

Para obtener información más detallada sobre recursos de aprendizaje y recursos, consulte el [Apéndice](#other-resources).

### <a name="access-cqd-online"></a>Acceso CQD en línea

Puede tener acceso a CQD de tres maneras:

-   Vaya a <https://cqd.lync.com>.

-   Vaya a **Centro de administración de equipos de Microsoft** y seleccione el vínculo a CQD, como se muestra en la siguiente ilustración.

![En el panel de la barra de navegación izquierda, se selecciona el vínculo al panel de calidad de llamada.] (media/qerguide-image-mopo.png "En el panel de la barra de navegación izquierda, se selecciona el vínculo al panel de calidad de llamada.")

_La figura 7: acceso a CQD a través del centro de administración de Microsoft Teams_

-   Vaya a la heredado **Skype para el centro de administración de negocio** > **Herramientas**y seleccione el vínculo a CQD, como se muestra en la siguiente ilustración.

![Herramientas está seleccionado en el panel de la barra de navegación izquierda y el vínculo a CQD está seleccionado en el panel principal.] (media/qerguide-image-legacyui.png "Herramientas está seleccionado en el panel de la barra de navegación izquierda y el vínculo a CQD está seleccionado en el panel principal.")

_La figura 8 - acceso a CQD mediante la Skype para el centro de administración de negocio_


### <a name="getting-started"></a>Introducción

Cuando en primer lugar, vaya a CQD, verá la página informes de resumen. La mayoría de los informes que se describen en esta guía están personalizados informes detallados. Para empezar a usar los informes detallados, seleccione **Informes de resumen** en la parte superior de la página y, a continuación, elija **Informes detallados**.

![Distintos tipos de informes que están disponibles en CQD](media/qerguide-image-choosereports.png)

_En la figura 9 - explorar a informes detallados_

La página de informes detallados en CQD el aspecto en la siguiente ilustración.

![Distintos elementos que componen un informe detallado.](media/qerguide-image-detailedreportspage.png)

|             |           |
| ------------|-----------|
| ![uno] (media/qerguide-image-callout1.png "uno") | El panel Resumen muestra contexto para el conjunto de informe que aparece a la derecha. |
| ![dos] (media/qerguide-image-callout2.png "dos") | Puede seleccionar **Editar** en el panel Resumen para establecer propiedades de nivel de informe (incluido el alto del eje y) y para importar plantillas de nuevo. |
| ![tres] (media/qerguide-image-callout3.png "tres") | La ruta de exploración ayuda a los usuarios a identificar su ubicación actual en la jerarquía del conjunto de informe. |
| ![cuatro] (media/qerguide-image-callout4.png "cuatro") | Informes que tienen informes secundarios se muestran con un vínculo azul. Al seleccionar el vínculo, puede desglosar los informes secundarios. |

_La figura 10 - página de informes detallados_

Elija los gráficos de barras y líneas de tendencia en el informe para mostrar los valores detallados. El informe que tiene el foco mostrará el menú Acción: **Editar**, **clon**, **Eliminar**, **Descargar**y **Exportar informe de árbol**.

### <a name="editing-reports"></a>Edición de informes

Cuando seleccione **Editar** en el menú Acción de un informe, podrá abrir Editor de consultas. Cada informe se respaldados por una consulta a CQD. Un informe es una visualización de los datos devueltos por su consulta. El Editor de consultas es una interfaz de usuario para su edición estas consultas además de las opciones de presentación para el informe, como se muestra en la ilustración siguiente.

![Distintos elementos que componen un informe cuando el informe se está editando.](media/qerguide-image-queryeditor.png)

|             |           |
| ------------|-----------|
| ![uno] (media/qerguide-image-callout1.png "uno") | Elija filtros, medidas y dimensiones desde el panel izquierdo. Apuntar a un valor existente, muestra un botón Cerrar (**X**), que puede optar por quitar el valor.<ul><li>Mediante la selección de la dimensión o medida, puede cambiar el título mediante la edición en el campo **título** . También puede cambiar el orden seleccionando el azul hacia arriba o hacia abajo flechas en el panel superior.</li><li>Selección (**+**) junto a un título, se abre el cuadro de diálogo para agregar una nueva dimensión, una medida o un filtro.</li><li>Escriba las primeras letras de la dimensión, una medida o un filtro en la **Buscar un** campo para filtrar la lista para facilitar su búsqueda.</li></ul> |
| ![dos] (media/qerguide-image-callout2.png "dos") | El panel superior muestra las opciones para la personalización de gráfico. |
| ![tres] (media/qerguide-image-callout3.png "tres") | El Editor de consultas, se muestra una vista previa del informe. |
| ![cuatro] (media/qerguide-image-callout4.png "cuatro") | Use el cuadro de **Edición** en la parte inferior de la pantalla para crear o editar una descripción detallada del informe. |

_La figura 11 - Editor de consultas_

### <a name="filtering-reports"></a>Filtrado de informes

Las plantillas incluyen varias consultas integradas y filtros del informe. En las secciones siguientes se describen los filtros más comunes que se utilizan a lo largo de las plantillas.

#### <a name="url-filter"></a>Filtro de URL

Puede usar una dirección URL de filtro para filtrar todos los informes de una dimensión específica. Los filtros de dirección URL más comunes se utilizan para filtrar los informes para excluir telemetría participante federado o centrarse en los equipos o Skype para profesionales en línea. Se recomienda que al usar filtros, se define un marcador ellos para facilitar la referencia. 

Exclusión de datos federados de informes CQD es útil cuando está solucionar relativos a los edificios administrados o redes donde extremos asociados externos pueden influir en los informes.

Para implementar un filtro de dirección URL, en la barra de direcciones del explorador, anexe lo siguiente al final de la dirección URL:

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Ejemplo:  

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Para filtrar los informes para los equipos o Skype para la empresa, anexe lo siguiente al final de la dirección URL:

```
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

Ejemplo:

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Is Teams]|[TRUE]```


> [!NOTE]
> Los ejemplos de dirección URL anteriores son para obtener sólo la representación visual. Utilice el vínculo CQD predeterminado de <https://cqd.lync.com>.


#### <a name="query-filters"></a>Filtros de consulta

Filtros de consulta se implementan mediante el Editor de consultas en CQD. Estos filtros se utilizan para reducir el número de registros devueltos por CQD, lo cual se minimiza el informe tamaño general y tiempos de consulta. Esto es especialmente útil para el filtrado de redes no administradas. Los filtros que aparecen en la siguiente tabla se usan expresiones regulares (RegEx).

_Tabla 3 - filtros de consulta_

| Filtro         | Descripción          | Ejemplo de filtro de consulta CQD      |
|----------------|----------------------|-------------------------------|
| No hay valores en blanco   | Algunos filtros no tienen la opción para filtrar los valores en blanco. Para filtrar manualmente valores en blanco, use la expresión en blanco y establezca el filtro en es igual a o no es igual a, según sus necesidades.      | Nombre del segundo edificio \< \> \^ \\s\*\$                       |
| Excluir subredes comunes | Sin un archivo de creación válido para separar administrada desde redes no administradas, redes particulares se incluirá en los informes. Estas subredes particulares están fuera del ámbito del control de TI y pueden excluirse rápidamente de un informe. Subredes comunes, como se define en esta guía, son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | Segunda subred \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Ver solo dentro de  | Se usa para filtrar un informe para (inside) administrado o no administrado (externa). La plantilla CQD administrada ya está preconfigurada con estos filtros.       | En segundo lugar dentro de Corp = dentro de        |

#### <a name="report-filters"></a>Filtros del informe

Filtros del informe se implementan mediante la adición de un filtro en el informe representado, ya sea en el Editor de consultas o directamente en el informe. Los siguientes filtros de informes se usan en toda la plantilla.

_Tabla 4 - filtros del informe_

| Filtro     | Descripción                            | Ejemplo de filtro de informe CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Empiece con el año inicial y, a continuación, mes. | 10 de 2017                           |
| Alfabéticos | Filtra todos los caracteres alfabéticos. | [a-z]                             |
| Numérico    | Filtra todos los caracteres numéricos.    | [0-9]                             |
| Porcentaje | Filtra por un porcentaje.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importar las plantillas CQD

Esta guía consta de [dos plantillas de CQD curated](https://aka.ms/qertemplates). Estas plantillas aceleran su uso de CQD y proporcionan una oportunidad de aprovechar rápidamente las capacidades del CQD para realizar un impacto en los equipos o Skype de los usuarios para que la experiencia empresarial. La plantilla de todas las redes, aunque optimizado para trabajar con un edificio se puede usar el archivo de datos, mientras se trabaja hacia la recopilación y la carga de información de creación en CQD, tal como se describe en la siguiente sección.

**Para importar las plantillas (. CQDX) en CQD en línea**

1. Vaya a <https://cqd.lync.com>.

2. Realice la autenticación mediante el uso de las credenciales administrativas de Office 365.

   > [!NOTE]
   > Debe tener Office 365 administrador Global, Skype para Administrador empresarial o rol de lectores de informes tener acceso a CQD. 

3. Seleccione el menú de **Informes de resumen** en la parte superior de la página y, a continuación, elija **Informes detallados**.

4. En el panel Resumen, seleccione **Importar**. Vaya a la ubicación de guardado de CQDX, seleccione la plantilla CQDX y, a continuación, seleccione **Abrir**.

5. Después de carga la plantilla, como una ventana emergente mostrará el mensaje "importación de informe fue correcta". Seleccione **Aceptar.**

   ![Notificación de que la plantilla se ha importado correctamente] (media/qerguide-image-importmessage.png "Notificación de que la plantilla se ha importado correctamente")

6. Repita los pasos 4 y 5 para la segunda plantilla CQD.

> [!NOTE]
> Las plantillas CQD se importan por usuario. Si necesitan usar el informe de usuarios adicionales, debe iniciar sesión en e importar las plantillas a su instancia CQD. 


## <a name="building-mapping"></a>Asignación de creación

En un equipo o Skype para la implementación empresarial en línea, todos los clientes son externos. Que tiene la implicación que de forma predeterminada, todos los clientes son conocida como fuera de CQD en línea, independientemente de si el cliente se ha conectado en una red corporativa interna.

Cuando se trabaja con CQD, necesita conocer la ubicación de un extremo y si estaba conectado a una red puede administrar o una red no se puede administrar: la suposición de que se va a que solo puede mejorar las redes puede administrar. Al cargar subred y la información de creación a CQD Online, habilitar CQD determinar si el extremo se ha conectado a una red interna corporativa o administrados o a una red externa y no administrado.

### <a name="building-data-file-structure"></a>Estructura de archivos de datos de creación

El formato del archivo de datos que se carga debe cumplir los siguientes requisitos para pasar la comprobación de validación antes de cargarlas.

-   El archivo debe ser un archivo TSV, lo que significa que, para cada fila, cada columna viene separada por un carácter de tabulación, o un archivo CSV en el que cada columna viene separada por una coma.

-   El archivo no se puede tener más de 50 MB.

-   El contenido de los datos de archivo *no debe incluir los encabezados de tabla*. En otras palabras, la primera línea del archivo de datos debe ser datos reales, no los encabezados de columna, como "Red".

-   Para cada columna, el tipo de datos sólo puede ser cadena, número o Bool. Si el tipo de datos es el número, el valor debe ser un valor numérico; Si es Bool, el valor debe ser 0 o 1.

-   Para cada columna, si el tipo de datos es la cadena, los datos pueden estar vacíos (pero aún deben estar separados por un delimitador adecuado, es decir, un carácter de tabulación o una coma). Esto sólo asigna ese campo un valor de cadena vacía.

-   Debe haber 14 columnas para cada fila. Cada columna debe tener el tipo de datos que se describen en la siguiente tabla y las columnas deben estar en el orden indicado en la tabla.

_Tabla 5: creación de la estructura de archivos_

| Nombre de columna        | Tipo de datos | Ejemplo                   | Instrucciones    |
|--------------------|-----------|---------------------------|-------------|
| Network            | Cadena    | 192.168.1.0               | Requerido    |
| NetworkName        | Cadena    | Estados Unidos/Seattle/SEATTLE-mar-1 | Requerido\*  |
| NetworkRange       | Número    | 26                        | Requerido    |
| BuildingName       | Cadena    | SEATTLE-MAR-1             | Requerido\*  |
| OwnershipType      | Cadena    | Contoso                   | Opcional     |
| BuildingType       | Cadena    | Terminación de TI            | Opcional     |
| BuildingOfficeType | Cadena    | De ingeniería               | Opcional     |
| Ciudad               | Cadena    | Seattle                   | Recomendado |
| ZipCode            | Cadena    | 98001                     | Recomendado |
| País            | Cadena    | NOSOTROS                        | Recomendado |
| Estado              | Cadena    | WA                        | Recomendado |
| Region             | Cadena    | MSUS                      | Recomendado |
| InsideCorp         | Booleano      | 1                         | Requerido    |
| ExpressRoute       | Booleano      | 0                         | Requerido    |

\*Si bien no es necesario por CQD, las plantillas están configuradas para mostrar la generación y red nombre.

#### <a name="supernetting"></a>Creación de superredes

Puede usar la creación de superredes, denominado habitualmente enrutamiento de interdominios sin clases (CIDR), en lugar de definir cada subred. Una *supernet* es una combinación de varias subredes que comparten un solo prefijo de enrutamiento. En lugar de agregar una entrada para cada subred, puede usar la dirección de superredes. Se admite la creación de superredes, pero no se recomienda usarlo.

Por ejemplo, la creación de marketing de Contoso se compone de las subredes que aparece a continuación:

-   10.1.0.0/24—First piso
-   10.1.1.0/24—Second piso
-   10.1.2.0/24—Third piso
-   10.1.3.0/24—Fourth piso

En lugar de agregar una entrada para cada subred, puede usar la dirección de superredes: en este ejemplo, 10.1.0.0/22.

-   Red = red dividida 10.1.0.0
-   Intervalo de red = 22

A continuación presentamos algunas cosas que se deben considerar antes de implementar la creación de superredes:

-   Creación de superredes sólo puede utilizarse en una asignación de subred con máscara de bits de 8 a 28 bits.

-   Creación de superredes tarda menos tiempo front-, pero lo que respecta a costa de la reducción de la flexibilidad de los datos. Supongamos que hay un problema de calidad que implican subred 200.1.2.0. Si implementa la creación de superredes, no sabrá donde se encuentra la subred en el edificio o qué tipo de red es (por ejemplo, un laboratorio). Si se hubiera definido todas las subredes de un edificio y cargar información de ubicación de planta, podrá vea esa distinción.

-   Es importante para asegurarse de que la dirección de superredes es correcta y no captura de subredes no deseadas.

-   Es un proceso bastante común para buscar 192.168.0.0 en los datos. Para muchas organizaciones, esto indica que el usuario está en casa. Para otras personas, éste es el esquema de direcciones IP de una oficina satélite. Si su organización tiene oficinas que usan esta configuración, no incluirlo en su archivo de creación porque es difícil distinguir entre las redes domésticas e internas mediante el uso de subredes comunes. Vea la sección acerca de las [subredes comunes](#common-subnets), anteriormente en esta guía.

> [!IMPORTANT]
> El intervalo de red puede usarse para representar un supernet. Creación de todas las nuevas cargas de archivos de datos se comprobarán para cualquier intervalos superpuestos. Si anteriormente ha cargado un archivo de creación, debe descargar el archivo actual y cargar nuevo para identificar cualquier superposiciones y solucionar el problema. Cualquier superposición en los archivos cargados previamente puede provocar en las asignaciones de incorrectos de subredes a edificios en los informes.

#### <a name="vpn"></a>VPN

La calidad de los datos de la experiencia (QoE) que los clientes de envían a Office 365, que es donde se proceden de datos CQD: incluye una marca VPN. CQD verá lo siguiente como las dimensiones de la VPN de primera y segunda VPN. Sin embargo, esta marca se basa en proveedores de VPN informar a Windows de que el adaptador de red VPN registrado es un adaptador de acceso remoto. No todos los proveedores de VPN registran correctamente los adaptadores de acceso remoto. Por este motivo, es posible que no pueda utilizar los filtros de consulta integrados de VPN. Existen dos enfoques para adaptación a subredes VPN en la creación del archivo de información:

- Definir un **Nombre de red** mediante el texto "VPN" en este campo para subredes VPN.

  ![Informe CQD que define cómo crear una subred VPN](media/qerguide-image-vpnnetworkname.png)

  _La figura 12 - VPN mediante el nombre de red_

- Para definir un **Nombre del edificio** , con el texto "VPN" en este campo para subredes VPN.

  ![Informe CQD que define cómo crear una definición de creación que consta de una subred VPN.](media/qerguide-image-vpnbuildingname.png)

  _La figura 13 - VPN mediante el nombre del edificio_

> [!IMPORTANT]
> Algunas implementaciones de VPN no notificar con precisión la información de subred. Si esto ocurre en la creación de informes, que se recomienda que cuando se agrega una subred VPN para el archivo de creación, en lugar de una entrada para la subred, agregar entradas independientes para cada dirección de la subred VPN como una red independiente de 32 bits. Cada fila puede tener los mismos metadatos de creación. Por ejemplo, en lugar de una fila por 172.16.18.0/24, tiene 253 filas, con una fila por cada dirección de 172.16.18.1/32 a través de 172.16.18.254/32, ambos inclusive.


> [!NOTE]
> Se sabe que las conexiones VPN identificar incorrectamente la conexión de red como por cable cuando la conexión a internet subyacente es inalámbrica. Cuando se mira calidad a través de conexiones VPN, no se puede suponer que el tipo de conexión se ha identificado con precisión.

### <a name="uploading-building-information"></a>Cargar información de creación

El panel de informes de resumen de CQD incluye una página **Inquilino la carga de datos** , puede tener acceso seleccionando la etiqueta de vínculo **Inquilino la carga de datos** en la esquina superior derecha (busque el icono del engranaje). Esta página se usa para los administradores para cargar su propia información, como la asignación de dirección IP y la información geográfica, asignación de cada punto de acceso inalámbrico y su dirección MAC y así sucesivamente.

1. Vaya a CQD Online buscando en <https://cqd.lync.com>.

2. Seleccione el icono del engranaje en la esquina superior derecha y elija el **Inquilino al cargar los datos** desde la página **Informes de resumen** .

   ![Cuadro de diálogo que aparece mientras se está cargando datos](media/qerguide-image-tenantdataupload.png)

   _La figura 14 - menú cargar datos de inquilinos_

3. Como alternativa, si se trata de la primera vez que visita CQD, se solicitará a cargar los datos de creación. Puede seleccionar **Cargar ahora** para navegar rápidamente a la página de **Carga de datos de inquilinos** .

   ![Pancarta que notifica a un usuario para cargar datos de creación](media/qerguide-image-buildingdatauploadbanner.png)

   _Figura 15: creación de pancarta de carga de datos_

4. En la página de **Carga de datos de inquilinos** , seleccione **Examinar** para elegir un archivo de datos.

5. Después de seleccionar un archivo de datos, especifique la **fecha de inicio** y, opcionalmente, especifique una fecha de finalización.

6. Después de seleccionar la **fecha de inicio**, seleccione la opción **cargar** para cargar el archivo en CQD. <br><br>Antes de que se carga el archivo, se valida. Si se produce un error de validación, se muestra un mensaje de error que solicita que se corrija el archivo. La siguiente ilustración muestra un error que se producen cuando el número de columnas en el archivo de datos es incorrecto.

   ![Ejemplo de un cuadro de diálogo que muestra un mensaje de error al importar los datos de creación](media/qerguide-image-buildingdatauploaderror.png)
 
   _La figura 16 - error de carga de datos de creación_

7. Si no se producen errores durante la validación, la carga de archivos se realizará correctamente. A continuación, puede ver el archivo de datos que se cargan en la tabla **Mis cargas** , que muestra la lista completa de todos los archivos que se cargan para el inquilino actual en la parte inferior de la página.

> [!NOTE]
> Puede tardar hasta cuatro horas para finalizar el procesamiento del archivo de creación. <br><br> Si ya se ha cargado un archivo de creación y necesita para agregar subredes que es posible que se han cumplido o excluidos, modifique el archivo original mediante la adición de las nuevas subredes, quite el archivo actual y volver a cargar el archivo recién editado. Puede haber creación activo sólo un archivo de datos en CQD. 


### <a name="updating-a-building-file"></a>Actualización de un archivo de creación

Mientras la recopilación de información de subred y la creación, los administradores a menudo van a cargar el archivo de creación en varias iteraciones a través del tiempo, agregando nuevas subredes y su información de creación, tal como se esté disponible. Cuando esto ocurre, debe volver a cargar el archivo de creación. Este proceso es como la carga inicial tal como se describe en la sección anterior, con algunas excepciones como se indicó en la sección siguiente.

> [!Important]
> Creación de un solo archivo puede estar activo a la vez. Varios archivos de creación no son acumulativos.

#### <a name="adding-net-new-subnets"></a>Agregar nuevas subredes netos

Hay veces cuando que necesitará para agregar nuevas subredes netos a CQD que no estaba originalmente parte de la topología de red. Para agregar nuevas subredes netos, realice lo siguiente en el portal de la carga de datos del inquilino de CQD:

1.  Editar el archivo original de creación y proporcionar una fecha de finalización que se produce al menos un día antes de la nueva red subredes se han adquirido.
2.  Descargue el archivo original, si aún no tiene una copia actualizada.
3.  Anexe el netos nuevas subredes al archivo original de creación.
4.  Cargar el archivo recién modificado creación siguiendo el mismo proceso que el anterior y establecer la fecha de inicio para un día después de que finalice el archivo anterior de creación.

#### <a name="updating-the-current-building-file"></a>Actualización del archivo actual de creación

Si ya está cargado un archivo de creación, pero necesita agregar subredes que faltan, haga lo siguiente en el portal de la carga de datos del inquilino de CQD:

1.  Descargue el archivo original, si aún no tiene una copia actualizada.
2.  Quitar el archivo actual en CQD.
3.  Anexe las subredes nuevo al archivo original.
4.  Cargue el archivo de creación. Asegúrese de establecer la fecha de inicio en al menos ocho meses anteriores para que CQD procesará los datos históricos.

### <a name="missing-subnets"></a>Subredes que faltan

Después de cargar información de creación para redes administradas, cada red administrada debe tener una asociación de creación. Sin embargo, esto no siempre será el caso; Normalmente, se pierden algunas subredes. En esta sección, se explica cómo validar las redes que faltan.

Vaya a la página de **Informes detallados** en CQD en línea y navegue hasta el **Informe de subred falta** incluidas en las plantillas CQD. Esto presenta todas las subredes con secuencias de 10 o más audio que no se definen en los datos de creación de archivos y que se están marcados como externa. Asegúrese de que no hay ninguna red administrada en esta lista. Si faltan subredes, actualice la creación original del archivo de datos y volver a cargarla a CQD.

> [!IMPORTANT]
> Debe agregar el identificador de inquilino como un filtro de consulta para el **Segundo identificador de inquilino** a este informe para filtrar el informe para ver sólo los datos de inquilino de su organización. De lo contrario, el informe mostrará subredes federadas.

> [!NOTE] 
> Asegúrese de ajustar el filtro de informe de año mes al mes actual. Seleccione **Editar**y ajustar el filtro de informe de **Mes año** para guardar el nuevo mes predeterminado.

![Informe que muestra las subredes no se incluye en el archivo de datos de creación de CQD que muestran el uso.](media/qerguide-image-missingbuildingreport.png)

_La figura 17 - falta el informe de creación_

### <a name="building-mapping-tools"></a>Herramientas de creación de asignación

Seamos realistas, asignación de subredes de la organización puede ser difícil. Redes globales de gran tamaño son muy complejas, con diferentes equipos que administran sus respectivos regiones, y no puede haber ningún origen único de verdad para la topología de red. Existen dos herramientas disponibles para ayudarle con iniciar el ejercicio de asignación de creación, que se describen en las secciones siguientes.

#### <a name="cqd-tools"></a>Herramientas CQD

Estas herramientas se basan en PowerShell y pueden sacar provecho de los sitios de Active Directory (AD) y servicios y para ayudar a rellenar previamente su archivo de creación de servicios de Microsoft DHCP.  Estas herramientas le ayudará a con las siguientes tareas:

1.  Sitios de AD y servicios de consulta y crear un archivo de creación basado en la información contenida dentro de.
2.  Un servidor DHCP de Microsoft o los servidores para extraer información de subred y crear automáticamente un archivo de creación de consultas.
3.  Validar un archivo existente de creación, comprobación de duplicados y se superpone.
4.  Busque las subredes no asignadas en CQD.

Para obtener más información acerca de esta herramienta, vea [esta entrada de blog](https://aka.ms/cqdtools).

#### <a name="network-planner"></a> Planificador de red

El organizador de la red determina y organiza los requisitos de red para la implementación de voz en la nube en unos pocos pasos sencillos. Al proporcionar que la organización de la red de detalles y uso de voz en la nube, puede obtener un cálculo aproximado de los requisitos de red para la implementación de voz en la nube, administrar y exportar estos detalles para informes y ver áreas para la investigación adicional y los pasos siguientes.

Si bien el organizador de la red no automatizar el proceso de asignación de creación en su totalidad, después de especificar información de la red en el organizador de la red, a continuación, pueden exportarse a un archivo de creación listo para la carga.

Se recomienda encarecidamente aprovechar el organizador de la red al implementar las cargas de trabajo de medios en la red para evaluar el impacto global. Para obtener más información sobre el planificador de red, visite [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).


## <a name="diagnostic-alerts"></a>Alertas de diagnósticos

Microsoft proactivamente supervisa la telemetría CQD para crear alertas de diagnósticos de problemas conocidos que afectar negativamente a la experiencia del usuario. Estas alertas, a continuación, se envían automáticamente al administrador de servicio mediante el centro de mensajes. En la siguiente tabla se describe las alertas de diagnósticos que se muestran en el centro de mensajes, junto con vínculos para obtener más información.

_Tabla 6 - alertas de diagnósticos_

| La alerta                                                                | Más información             |
|----------------------------------------------------------------------|------------------------------|
| Conocidos bajo rendimiento versiones de cliente están en uso                   | [Versiones de cliente](#client-versions)              |
| Controladores de audio que provocan gotas de llamada                                 | [Dispositivos](#devices)                      |
| Restricciones en el servidor de seguridad que provocan errores del programa de instalación de llamadas         | [Investigaciones de error del programa de instalación](#setup-failure-investigations) |
| Inspección profunda del paquete es la causa de errores de llamadas del programa de instalación                | [Investigaciones de error del programa de instalación](#setup-failure-investigations) |
| Dispositivos para salas de reuniones en redes Wi-Fi que producen una calidad deficiente llamada | [Investigaciones de calidad](#quality-investigations)       |
| El tráfico UDP se encuentra limitado, lo que hace que la calidad de llamada deficiente         | [TCP](#tcp)                          |
| Uso VPN está afectando a la calidad de la llamada                                  | [Investigaciones de calidad](#quality-investigations)       |


### <a name="message-center"></a>Centro de mensajes

El centro de mensajes de las alertas sobre nuevas actualizaciones, características o problemas. El centro de mensajes está disponible en el centro de administración de Office 365 a los administradores de servicios. Cada entrada proporciona una descripción general de cómo la actualización, la característica o el problema afecta a los usuarios y proporciona vínculos a información más detallada.

Para abrir el centro de mensajes, en el centro de administración de Office 365, vaya a **Mantenimiento** > **Centro de mensajes**, o seleccione la ficha del centro de mensaje en **el panel** . El panel muestra los tres últimos mensajes que se contabilizaron y vínculos a la página del centro de mensaje completo.
 

![La ficha del centro de mensajes muestra los tres últimos mensajes que se contabilizaron](media/qerguide-image-messagecentercard.png)

_La figura 18 - ficha del centro de mensaje_

También puede usar la [aplicación de administración de Office 365](https://go.microsoft.com/fwlink/p/?linkid=627216) en su dispositivo móvil para ver el centro de mensajes, que es una excelente manera de mantenerse al día con las notificaciones de inserción. Para obtener más información, vea [este artículo](https://support.office.com/article/Message-center-in-Office-365-38FB3333-BFCC-4340-A37B-DEDA509C2093).

## <a name="reliability-investigations"></a>Investigaciones de confiabilidad

El primer paso para mejorar la calidad es para evaluar el estado de confiabilidad en toda la organización. Debido a que la confiabilidad es vital para una experiencia de usuario positivo, empezamos con los dos componentes que miden la confiabilidad:

1.  **Errores del programa de instalación:** No se ha podido establecerse la llamada.

2.  **Colocar errores:** La llamada se haya establecido y finalizado de forma inesperada.

En esta sección, trataremos métodos para investigar ambas áreas.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía.  Sin embargo, se siguen aplican los métodos de investigación que se explica a continuación. La descripción del informe individuales para obtener más información, consulte.


### <a name="setup-failures"></a>Errores del programa de instalación

Establecer prioridades de solucionar errores del programa de instalación en esta área en primer lugar, ya que estos errores tienen un impacto negativo significativo en la experiencia del usuario.

Comenzar su investigación evaluando el porcentaje de errores en la instalación general para la organización y, a continuación, asignar prioridades a las áreas de investigación según el porcentaje más alto mediante la creación o la red. 

#### <a name="setup-failure-trend-analysis"></a>Análisis de tendencias de error del programa de instalación

Este informe muestra la cantidad total de secuencias, errores de secuencia del programa de instalación y la tasa de errores de secuencia del programa de instalación. Seleccione cualquiera de las columnas para mostrar sus valores individuales, como se muestra en la ilustración siguiente. 

![Gráfico que muestra el porcentaje de secuencia de errores del programa de instalación](media/qerguide-image-streamsetupfailures.png)

_Errores de la figura 19 - confiabilidad de Audio - secuencia del programa de instalación_

##### <a name="analysis"></a>Análisis

Mediante el uso de este informe, puede responder a las siguientes preguntas y determinar el curso de acción siguiente:

-   ¿Qué es el porcentaje de error del programa de instalación de llamada total para el mes actual?

-   ¿Es el porcentaje de errores de llamada total del programa de instalación por debajo o por encima de la métrica de destino definido?

-   ¿Es la tendencia de error peor o mejor que el mes pasado?

-   ¿La tendencia de errores aumenta, steady, o disminuye?

Independientemente de las respuestas anteriores, tómese tiempo para investigar más mediante el uso de los informes de subcaracterística complementarios para buscar cualquier edificios individuales o subredes que podrían necesitar corrección. Aunque es posible que el porcentaje de errores generales por debajo de la métrica de destino, las tasas de error para uno o varios de los edificios o redes podrían ser superior a la métrica de destino y deben investigarse.

#### <a name="setup-failure-investigations"></a>Investigaciones de error del programa de instalación 

Este informe de resumen se usa para detectar y aislar los edificios o las redes que necesiten corrección.

> [!NOTE]
> Asegúrese de ajustar el filtro de informe de año mes al mes actual. Seleccione **Editar**y ajustar el filtro de informe de **Mes año** para guardar el nuevo mes predeterminado.


![Una lista de los motivos para errores de llamadas del programa de instalación, organizados por la creación, la red y la subred al mes](media/qerguide-image-setupfailuresbysubnet.png)

_La figura 20 - errores de configuración de Audio por subred_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Si ha recibido una alerta de diagnóstico "Restricciones en el servidor de seguridad están causando errores del programa de instalación de llamadas" o "inspección profunda del paquete está causando errores del programa de instalación de llamadas," centrar los esfuerzos de corrección en los que identifica subredes en primer lugar. La alerta ha identificado subredes que afectan negativamente a confiabilidad de la llamada. Puede usar los informes de errores del programa de instalación que se encuentran en la sección de confiabilidad para ayudarle con la corrección.

##### <a name="remediation"></a>Corrección 

Centrar los esfuerzos de corrección primera en edificios o subredes que tienen el mayor volumen de errores. Esto maximizar el impacto en la experiencia del usuario y ayudan a reducir rápidamente la tasa de errores de llamada organizativa del programa de instalación. En la siguiente tabla se enumera las dos razones para los errores del programa de instalación beneficiarán de acuerdo con CQD.

_Tabla 7: razones para errores de llamadas del programa de instalación_

| Llamar a causa de errores en la instalación       | Causa típica                    |
|----------------------------------|----------------------------------|
| Falta una regla de exención de inspección RV profunda del paquete | Indica que el equipo de red a lo largo de la ruta de acceso impide que la ruta de acceso de medios está estableciendo debido a las reglas de inspección profunda del paquete. Esto es probable que debido a las reglas de firewall no está configuradas correctamente. En este escenario, el protocolo de enlace TCP se ha realizado correctamente, pero no el protocolo de enlace SSL.      |
| Falta una regla de excepción del bloque RV IP      | Indica que el equipo de red a lo largo de la ruta de acceso impide que la ruta de acceso de medios está estableciendo a la red de Office 365. Esto puede resultar debido a las reglas de proxy o firewall no está configuradas correctamente para permitir el acceso a direcciones IP y los puertos usados para los equipos y Skype para el tráfico de negocio. |

Ahora cuando comience la corrección, puede Centrar los esfuerzos de un determinado edificio o subred. Como se muestra en la tabla anterior, estos problemas son debido a las configuraciones de firewall o proxy. Revise las opciones en la tabla siguiente para las acciones de corrección.

_Tabla 8: pasos siguientes para llamada de corrección de error del programa de instalación_


|      Corrección      |                                                                                                                                                                                                                                                                                                                                                                   Instrucciones                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar servidores | Trabajar con el equipo de red y comprobar la configuración de servidores frente a [la lista de direcciones IP de Office 365](https://aka.ms/o365ips).<br><br>Compruebe que las [subredes de medios](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) y puertos se encuentran en las reglas de firewall. <br><br>Compruebe que se abren los puertos necesarios (enumerados a continuación) en el servidor de seguridad. UDP debe tener prioridad debido a que TCP se considera un protocolo de la conmutación por recuperación para el audio, vídeo, y el uso compartido de pantalla basados en vídeo y su uso afectará a la calidad de la llamada. Compartir aplicaciones de RDP heredado sólo utilice TCP.<br><ul><li>**TCP:** el puerto 443</li><li>**UDP:** puertos 3478 – 3481</li><ul> |
|        Comprobar         |                                                                                                                                                                                                                                                                 Usar la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar la conectividad de la creación afectado o subred mediante el uso de la función de comprobación de conectividad.                                                                                                                                                                                                                                                                  |

### <a name="drop-failures"></a>Errores de entrega

A diferencia de los códigos de error del programa de instalación, CDQ no tiene ningún código de error de colocación para indicar por qué buzón se producen errores, lo que hace difícil aislar a una causa concreta. Para evaluar mejor desplegable errores, usa un enfoque inferido. Por solucionar relativos a las áreas de interés para los medios, los clientes de la aplicación de revisiones y controladores y el uso de fuerzas de dispositivos certificados para equipos y Skype para la empresa, que se pueden esperar errores de colocación para rechazar.

#### <a name="drop-failure-trend-analysis"></a>Colocar el análisis de tendencias de errores

Este informe muestra la cantidad total de secuencias de audio, errores de total del buzón y la tasa de errores de entrega. Seleccione cualquiera de las columnas para mostrar sus valores, como se muestra en la ilustración siguiente. 

![Gráfico que muestra el porcentaje de secuencias que se han quitado](media/qerguide-image-droppedstreamrate.png)

_La figura 21: tasa de secuencia perdidos_

##### <a name="analysis"></a>Análisis

Mediante el uso de este tipo de informe, puede responder a las siguientes preguntas:

-   ¿Qué es la tasa de errores de entrega actual?
-   ¿Es la tasa de errores de colocar debajo de la métrica de destino definido?
-   ¿Es la tendencia de error peor o mejor que el mes pasado?
-   ¿La tendencia de errores aumenta, steady, o disminuye?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo para investigar utilizando los subinformes para buscar cualquier edificios o redes que podrían necesitar corrección. Aunque es posible que el porcentaje de errores generales de colocar debajo de la métrica de destino, la tasa de errores de entrega para uno o varios de los edificios o redes podría ser superior a la métrica de destino y deben investigarse.

#### <a name="drop-failure-investigations"></a>DROP investigaciones de error

Los errores que se notifiquen aquí indican que la llamada se ha colocado de forma inesperada y resulta en una experiencia de usuario negativo. A diferencia de los informes de tendencias, estos informes proporcionan adicional entendimiento subredes específicas que necesitan más investigación.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.


![Que el número de listas y el porcentaje de errores de entrega, organizadas por subred al mes, red y creación de informes](media/qerguide-image-dropfailuresbysubnet.png)

_La figura 22 – errores de buzón por subred_

##### <a name="remediation"></a>Corrección

Uso de los informes de tabla incluye puede aislar el problema áreas en la red donde la tasa de buzón está por encima de la métrica de destino han definido. Centrar los esfuerzos de corrección primera en edificios o subredes que tienen el número de secuencia total más alto, para obtener el mayor impacto.

Causas habituales de gotas de llamada:

-   Salida de red o de internet en aprovisionado
-   Sin QoS configurado en redes limitadas
-   Versiones anteriores de cliente
-   Comportamiento de usuario

Después de detectar las áreas de problema, puede usar [Análisis llamar](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) para revisar aún más los usuarios de dicho edificio problemas específicos. Análisis de llamada contiene datos PII y pueden ser útil para aislar aún más los posibles motivos de los errores de entrega.

Independientemente del siguiente paso, es una práctica recomendada para notificar el departamento de soporte técnico que se ha detectado un problema con los edificios específicos o subredes. De este modo, rápidamente pueden responder a las llamadas entrantes y clasificar los usuarios de forma más eficaz. Los usuarios marcados se pueden, a continuación, notificar al equipo de ingeniería para una mayor investigación.

En la siguiente tabla se enumera algunos métodos comunes para administrar y corregir errores de entrega.

_Tabla 9 - pasos siguientes para llamada drop corrección_

| Corrección                              | Instrucciones                      |
|------------------------------------------|-------------------------------|
| **Red o a internet**                         | **Congestión**: trabajar con su equipo de red para supervisar el ancho de banda de los edificios/subredes específicas para confirmar que no hay problemas con sobreutilización. Si confirma que hay congestión de la red, tenga en cuenta el aumento de ancho de banda para dicho edificio o aplicar QoS. Use incluye [informes de resumen de calidad deficiente secuencia](#quality-investigations) para revisar las subredes de problema de problemas de vibración, latencia y pérdida de paquetes, porque a menudo, estos preceden una secuencia descartada.<br><br>También puede usar la [Herramienta de planeación de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) para ayudar a comprender mejor las necesidades de ancho de banda de su organización.<br><br>**QoS**: si cada vez mayor ancho de banda no es práctico o costo sumamente elevado, considere la implementación de QoS. Esta herramienta es muy eficaz al administrar el tráfico de congestionada y puede garantizar que los paquetes de multimedia en la red administrada se priorizan encima el tráfico de medios que no sean. Como alternativa, si no hay ninguna evidencia borrar que dicho ancho de banda es el punto de entrada, tenga en cuenta estas soluciones:<ul><li>[Instrucciones de QoS de los equipos de Microsoft](qos-in-teams.md)</li><li>[Skype para obtener instrucciones de QoS de negocio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Realizar una evaluación de disponibilidad de red**: una evaluación de la red proporciona información detallada sobre el uso del ancho de banda esperado, cómo lidiar con ancho de banda y de la red cambia y redes procedimientos recomendados para los equipos y Skype para la empresa. Uso de la tabla anterior como su origen, tener una lista de los edificios o subredes que son candidatos excelentes para una evaluación.<ul><li>[Evaluación de preparación de redes de equipos de Microsoft](3-envision-evaluate-my-environment.md#test-the-network)</li><li>[Skype para evaluación de preparación para la red empresarial](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Herramienta de evaluación de la red de Microsoft:** Use esta herramienta para una prueba simple de rendimiento de la red para determinar el grado en que debería realizar la red para los equipos de un o Skype para llamadas en línea de negocio. La herramienta le ayuda a evaluar el rendimiento de una subred y validar la preparación de la red frente a [requisitos](https://aka.ms/performancerequirements)de rendimiento de Microsoft.<ul><li>[Descargar la herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul> |
| **Los clientes (Skype para la empresa sólo en línea)** | Algunos clientes más antiguos tienen conocidos, documentan problemas con la confiabilidad de los medios. Revisar los informes de análisis de llamadas desde varios usuarios afectados o crear un informe de tabla de versión de cliente personalizado en CQD filtrado a edificios específicos o subredes con medida % de error Total de llamadas colocada. Esta información le ayudará a comprender si existe una relación entre gotas de llamada en dicho edificio específico y una versión específica del cliente.     |
| **Dispositivos**                                  | Se recomienda que todos los usuarios que están experimentando llamar gotas — o deficientes llama en general: y son el uso de dispositivos integrados debe ser aprovisionar un [certificado auriculares con micrófono o altavoz](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) para eliminarlo como una fuente potencial de mala calidad y la confiabilidad. |
| **Comportamiento de usuario**                            | Si determina que ni de red, dispositivos o clientes son el problema, considere la posibilidad de contratar [Asesor de mi](https://aka.ms/myadvisor) para obtener orientación en el desarrollo de una estrategia de adopción de usuario para enseñar a los usuarios cómo procedimientos unirse y salir de las reuniones. Una manera más eficaz los equipos y Skype para usuarios de empresa generarán una mejor experiencia de usuario para todos los participantes de la reunión. Un usuario que pone a su equipo portátil en modo de suspensión (cerrando la tapa) sin salir de la reunión se clasifica como un buzón de llamada inesperada.   |

## <a name="quality-investigations"></a>Investigaciones de calidad

El siguiente paso para evaluar el estado de calidad de audio en toda la organización es investigar la tasa de secuencia deficiente (PSR), TCP y uso de proxy. Es importante recordar que datos CQD no proporcionan una causa concreta, sino que proporcionan con áreas de problema es probable que para iniciar una conversación de colaboración con los equipos adecuados para las actividades de corrección. 

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía; Sin embargo, los métodos de investigación que se explica a continuación seguirá siendo aplicable para los informes. Hacer referencia a la descripción del informe individuales para obtener más información. 

### <a name="quality"></a>Calidad

Los porcentajes de la región Determinada se utilizan para indicar si la organización cumple los objetivos de métrica definidos para un área de foco determinado. Es importante tener en cuenta que incluso si los porcentajes de alto nivel son dentro del destino definido, subredes individuales o edificios podrían no cumplir los objetivos definidos y, por lo tanto, necesita más investigación. Por ejemplo, si el porcentaje de la región Determinada general del audio es % 2 en abril, que cumple con el destino de ejemplo, los edificios individuales y subredes podría ser teniendo una mala experiencia, dependiendo de la distribución general de ese 2 por ciento. 

Para evaluar el porcentaje de secuencias deficientes, use los informes de calidad. Se proporcionan varios informes de calidad para revisar las métricas para general, conferencias, entre dos participantes, RTC de llamada, VPN y las salas de reuniones. Informes diarios, semanales y mensuales se proporcionan para ayudar en este proceso. Informes de diarios y semanales se limitan a la plantilla de redes administradas para aumentar su eficacia y reducir el ruido. 

#### <a name="quality-trend-analysis"></a>Análisis de tendencias de calidad

Informes de tendencias de mostrar información sobre la calidad a través del tiempo y se usan para ayudar a identificar y comprender las tendencias de calidad dentro de cada área de interés. Tal y como se mencionó anteriormente, hay árboles de informe incluidos en las plantillas para investigar la calidad; conferencia, entre dos participantes, las llamadas RTC, VPN y las salas de reuniones. Para los fines de analizar la calidad, el proceso de investigación es el mismo. Sin embargo, se recomienda iniciar en primer lugar, con la conferencia porque cualquier mejoras en la calidad de la conferencia también positiva afectará a todas las demás áreas. 

> [!Note]
> Investigar entre dos participantes, las llamadas RTC y las salas de reuniones son similares a investigar la conferencia. El objetivo es isloate edificios o subredes que tienen el peor calidad e identifican el motivo de la mala calidad.

> [!Important]
> Informes basados en VPN se filtran mediante el uso de la dimensión de segundo VPN. Esta dimensión requiere que el adaptador de red VPN se ha registrado correctamente como un adaptador de acceso remoto. Proveedores de VPN confiable no utilice esta marca y su pueden variar según el proveedor de VPN implementado en la organización. Siga las instrucciones descritas [anteriormente en esta guía](#vpn) para modificar la VPN informes si es necesario usando el nombre de creación o de red.

![Gráfico que muestra el porcentaje de secuencias de mala calidad](media/qerguide-image-audioqualityconferencing.png)

_La figura 23: calidad de Audio - conferencia_

##### <a name="investigation"></a>Investigación

Mediante el uso de estos informes, puede responder a las siguientes preguntas:

-   ¿Qué es la región Determinada total para el mes actual?
-   ¿Es la región Determinada por debajo de la métrica de destino definido?
-   ¿Es la región Determinada peor o mejor que el mes pasado?
-   ¿La tendencia de la región Determinada aumenta, steady, o disminuye?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo para investigar mediante el uso de los subinformes para buscar cualquier edificios o subredes que es posible que deben investigarse. Aunque es posible que la región Determinada general por debajo de la métrica de destino, a menudo la región Determinada para uno o varios de los edificios o redes está por encima de la métrica y necesita corrección.

#### <a name="quality-investigations"></a>Investigaciones de calidad

La calidad de los informes de resumen proporcionan una idea más profunda en qué contribuido a las secuencias que se clasificó como deficiente y ayuda a aislar las áreas con problemas en la red administrada.

Aunque las dimensiones utilizadas podrían variar ligeramente entre informe, cada informe incluirá las medidas encaminadas a número total de secuencias, secuencias deficientes totales, región Determinada y calidad deficiente debido a. Los informes se han creado para cada área de interés: salas de conferencia, entre dos participantes, RTC de llamada, VPN y de la reunión. La plantilla de red administrada incluye informes adicionales para aprovechar la información de ubicación que se cargan mediante el archivo de creación.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.

> [!Note]
> Subredes comunes son difíciles de evaluación de errores debido a su uso extendido. Se ha agregado un informe independiente que muestra IP pública del cliente (IP Local reflexiva segundo) a la plantilla de todas las redes para ayudar a solucionar las oficinas que utilizan redes comunes.


![Secuencia de audio deficiente resumen](media/qerguide-image-poorqualitysummary.png)

_En la figura 24 – resumen de secuencia de Audio deficiente mediante la generación de - y subred conferencia_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Si ha recibido un diagnóstico alerta "dispositivos para salas de reuniones en redes Wi-Fi están causando una calidad deficiente llamada," incluir y asignar prioridades a los dispositivos de sus esfuerzos de reparación. La alerta ha identificado las salas de reuniones en Wi-Fi que contribuyen activamente a la calidad de la llamada deficiente.

Si recibe una alerta de diagnóstico "uso VPN está afectando a la calidad de llamadas," investigar una solución de túnel dividido para omitir el dispositivo VPN y permitir que los medios para conectarse directamente al servicio. Ha identificado la alerta que VPN negativamente está afectando a la calidad de la llamada.

##### <a name="remediation"></a>Corrección

Centrar los esfuerzos de corrección en los edificios o subredes que tienen el mayor volumen de secuencias, ya que esto maximizar el impacto y ayudar a mejorar la experiencia del usuario rápidamente. Use la vibración, la pérdida de paquetes y las medidas de tiempo de ida y vuelta (RTT) para comprender lo que contribuye a la calidad deficiente (es posible que haya más de un problema):

-   **Vibración**: los paquetes multimedia llegan a diferentes velocidades, lo que provoca un altavoz se oye robótica.
-   **Pérdida de paquetes**: se está quitando los paquetes multimedia, que crea el efecto de ausencia de palabras o sílabas.
-   **RTT**: los paquetes multimedia tardan mucho tiempo para llegar a su destino, que crea un efecto transmisor-receptor portátil.

Para ayudar a la investigación de problemas de calidad, puede aprovechar [Análisis de llamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Con el análisis de llamadas, puede buscar en una conferencia concreta o informe detallado de llamadas de los usuarios. Este informe contendrá datos PII y es útil cuando se busca la causa de un error. Después de que sabe qué edificio se ve afectada, debe ser un proceso sencillo realizar un seguimiento de los usuarios de dicho edificio. 

No olvide que el departamento de soporte técnico sepan que estas redes están experimentando problemas de calidad, para que puedan detectar y responder a las llamadas entrantes rápidamente.

_Tabla 10 - colaboradores comunes en alta producidos en regiones determinadas_

| Corrección                              | Instrucciones                         |
|------------------------------------------|----------------------------------|
| **Redes**                                 | **Congestión**: una sobreutilizados o aprovisionado en la red puede provocar problemas con la calidad de medios. Trabajo con el equipo de red para determinar si las conexiones de red desde el usuario a la salida de internet señalan tiene suficiente ancho de banda para admitir los medios. El [Organizador de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) pueden ayudarle a comprender mejor las necesidades de ancho de banda de su organización.<br><br>**Realizar una evaluación de disponibilidad de red**: una evaluación de la red proporciona información detallada sobre el uso del ancho de banda esperado, cómo lidiar con ancho de banda y de la red cambia y redes procedimientos recomendados para los equipos y Skype para la empresa. Uso de la tabla anterior como su origen, tener una lista de los edificios o subredes que son candidatos excelentes para una evaluación.<ul><li>[Evaluación de preparación de redes de equipos de Microsoft](3-envision-evaluate-my-environment.md#test-the-network)</li><li>[Skype para evaluación de preparación para la red empresarial](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Herramienta de evaluación de la red de Microsoft:** Use esta herramienta para una prueba simple de rendimiento de la red para determinar el grado en que debería realizar la red para los equipos de un o Skype para llamadas en línea de negocio. La herramienta le ayuda a evaluar el rendimiento de una subred y validar la preparación de la red frente a [requisitos](https://aka.ms/performancerequirements)de rendimiento de Microsoft.<ul><li>[Descargar la herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul><br> |
| **Calidad de servicio (QoS)**  | QoS es una herramienta probada para dar prioridad a los paquetes en una red congestionada para asegurarse de que llegan a su destino intacta y en el tiempo. Considere la implementación de QoS en toda la organización para maximizar la calidad de la experiencia del usuario donde se limita el ancho de banda. QoS le ayudará a solucionar problemas asociados normalmente con niveles altos de pérdida de paquetes, y, en menor grado, tiempos de ida y vuelta y vibración.<ul><li>[Instrucciones de QoS de los equipos de Microsoft](qos-in-teams.md)</li><li>[Skype para obtener instrucciones de QoS de negocio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul> |
| **Wi-Fi**               | Wi-Fi puede tener un impacto significativo en la calidad de la llamada. Las implementaciones de Wi-Fi normalmente no tendrán en cuenta los requisitos de red para servicios de VoIP y a menudo son una fuente de mala calidad. Para obtener más información sobre la optimización de la infraestructura de Wi-Fi, consulte [este artículo acerca de la planeación de Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Controlador inalámbricos**: asegúrese de que los controladores inalámbricos estén actualizados. Esto le ayudará a mitigar cualquier experiencia de usuario deficiente relacionado con un controlador anticuado. Muchas organizaciones no incluyen controladores inalámbricos en sus ciclos de revisión, y pueden ir sin revisión estos controladores para años. Inalámbricas muchos de los problemas se resuelven al garantizar que los controladores inalámbricos estén actualizados.<br><br>**WMM**: extensiones de Multimedia inalámbricos (WMM), también conocido como Wi-Fi Multimedia, proporciona características básicas de QoS para redes inalámbricas. Redes inalámbricas modernas deben admitir muchos dispositivos. Estos dispositivos compiten por el ancho de banda y pueden dar lugar a problemas de calidad para los servicios de VoIP, donde la velocidad y la latencia son vitales. Consulte a su proveedor inalámbrico para obtener información específica y considere la posibilidad de implementar WMM en su red inalámbrica para dar prioridad a Skype para los medios de negocios y los equipos.<br><br>**Densidad de puntos de acceso**: puntos de acceso podrían ser demasiado alejados o no en una ubicación ideal. Para minimizar las posibles interferencias, coloque los puntos de acceso adicionales en salas de conferencias y en ubicaciones que no están obstruidas por paredes u otros objetos donde la señal Wi-Fi es débil.<br><br>**2,4 GHz frente a 5 GHz**: 5 GHz proporciona menos interferencias de fondo y velocidades superiores y se debe asignar prioridad al implementar VoIP a través de Wi-Fi. Sin embargo, 5 GHz no es tan fuerte como a 2,4 GHz y no entrar en las paredes como fácilmente. Revise el diseño de creación para determinar qué frecuencia puede depender de la conexión de procedimientos. |
|**Dispositivo de red** | Las organizaciones más grandes deberían cientos de dispositivos repartidos por la red. Trabaje con su equipo de red para asegurarse de que los dispositivos de red desde el usuario a internet se conservan y actualizados. |
| **VPN**  | Dispositivos VPN tradicionalmente no están diseñados para administrar cargas de trabajo de medios en tiempo real. Algunas configuraciones de VPN prohibirán el uso de UDP (que es el protocolo preferido para los medios) y sólo se basan en TCP. Considere la posibilidad de implementar una [solución de división túnel VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) para ayudar a reducir la VPN como el origen de mala calidad. |
| **Clientes** <br>(Skype para la empresa sólo en línea) | Se sabe que los clientes más antiguos provocar problemas con los medios. Asegúrese de que los clientes se se revisen dentro de seis meses a partir de la versión. Usar [MyAdvisor](https://aka.ms/myadvisor) para obtener instrucciones sobre el desarrollo de una estrategia de preparación de cliente e implementación de [Click-to-Run](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus). |
| **Dispositivos** | El uso de [optimizado dispositivos](https://partnersolutions.skypeforbusiness.com/solutionscatalog) puede ayudar a mejorar considerablemente la experiencia del usuario. Con todos los componentes iguales, los dispositivos optimizados están diseñados para maximizar la experiencia del usuario con los equipos y Skype para la empresa y producir una calidad superior. Use [MyAdvisor](https://aka.ms/myadvisor) para obtener instrucciones sobre el desarrollo de una estrategia de preparación del dispositivo. |
| **Controladores** | Aplicación de revisiones de red (Ethernet y Wi-Fi), audio, vídeo y controladores USB debe formar parte de su estrategia general de administración de la revisión. Muchos de los problemas de calidad se resuelven mediante la actualización de controladores. |
| **Salas de reuniones en Wi-Fi** | Se recomienda encarecidamente que reunión dispositivos para salas de estar conectado a la red mediante el uso de al menos una conexión de Ethernet de 1 Gbps. Dispositivos para salas de reuniones normalmente incluyen varias secuencias de audio y vídeos, junto con el contenido de la reunión como uso compartido de pantalla y tienen mayores requisitos de red que otros equipos o Skype para los extremos de negocio. Salas de reuniones son, por definición, fondo dispositivos donde Wi-Fi le ofrece una ventaja sólo durante la instalación.<br><br>Las salas de reuniones se deben tratar con especial cuidado y atención para asegurarse de que la experiencia de uso de estos dispositivos se cumple o supera las expectativas. Problemas de calidad con las salas de reuniones normalmente va a trasladarse rápidamente, porque a menudo se utilizan por el personal de nivel superior.<br><br>Con todo lo que se va a igual (aparte de comodidad), Wi-Fi rendimiento suele ser menor que una conexión por cable. Con el aumento de las directivas de "poner su propio dispositivo" y la proliferación de equipos portátiles, los puntos de acceso Wi-Fi a menudo se utilizan un exceso. No se puede prioriza multimedia en tiempo real en redes Wi-Fi, que pueden dar lugar a problemas de calidad durante las horas de uso. Este uso intenso puede coinciden con una reunión donde pueden existir doce personas en asistencia, cada uno con sus propios portátiles y smartphone, todos los conectadas al mismo punto de acceso Wi-Fi como la reunión dispositivo de sala.<br><br>Wi-Fi sólo debe considerarse como una solución temporal, para una instalación móvil, o cuando se ha creado correctamente Wi-Fi para admitir los medios de clase empresarial, basado en tiempo real. |


### <a name="tcp"></a>TCP

TCP se considera un transporte de la conmutación por recuperación y no el transporte principal que desee para multimedia en tiempo real. La razón es un transporte de la conmutación por recuperación es debido a la naturaleza con estado de TCP. Por ejemplo, si se realiza una llamada en una red latente y tienen un retraso de los paquetes multimedia, a continuación, los paquetes desde hace unos segundos, que ya no son útiles: compiten por el ancho de banda llegar al receptor, que puede hacer que un peor situación incorrecta. Esto hace que el punto de muestra de audio y el audio estiramiento, resultante en audibles artefactos, a menudo en forma de vibración.

Los informes de esta sección no realiza una distinción entre las secuencias de buenas y mala. Dado que UDP es preferido, busque los informes para el uso de TCP para audio, vídeo y vídeo-based pantalla uso compartido (VBSS). Tasas de secuencia deficiente se proporcionan para ayudar a comparar calidad UDP frente a la calidad TCP para que pueda centrarse los esfuerzos donde el impacto es el mayor. Uso TCP principalmente está causado por las reglas de firewall incompleta. Para obtener más información acerca de las reglas de firewall para los equipos y Skype para profesionales en línea, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips).

> [!Important]
> Se recomienda disponer de un [archivo de creación válido](#building-mapping) cargado por lo que puede distinguir rápidamente dentro de secuencias externas cuando se examina el uso TCP.

> [!Note]
> Audio, vídeo y VBSS prefiere UDP como su transporte principal. La carga de trabajo de uso compartido de aplicaciones de RDP heredado sólo usa TCP.

#### <a name="tcp-usage"></a>Uso TCP

Informes TCP indica el uso general de TCP a través de los últimos siete meses. Todos los otros informes en esta sección se centrarán en restringir hacia abajo los edificios específicos y subredes donde TCP se usa con más frecuencia. Informes independientes están disponibles para las conferencias y secuencias de dos partes.

![Gráfico que muestra el porcentaje de secuencias de audio que utilice TCP](media/qerguide-image-audiostreamswithtcp.png)
_figura 25 – secuencias de Audio con un uso de TCP_


##### <a name="investigation"></a>Investigación

Mediante el uso de este informe, puede responder a las siguientes preguntas:

-   ¿Qué es el volumen total de secuencias TCP para el mes actual?
-   ¿Es mejor que el mes anterior o peor?
-   ¿La tendencia de uso TCP aumenta, steady, o disminuye?
-   ¿Es el PSR TCP el mismo que mi región Determinada general?

Si observa que está aumentando la tendencia de uso TCP o por encima del uso mensual normal, tómese el tiempo para investigar mediante el uso de los subinformes para buscar cualquier edificios o redes que podrían necesitar corrección. Idealmente, desea que tan solo sesiones de audio basados en TCP como sea posible en la red administrada.

#### <a name="tcp-vs-udp"></a>TCP y UDP

Este informe identifica el volumen de TCP en lugar de en el último mes para audio, vídeo y vídeo-based pantalla (VBSS) de uso compartido de informes de uso UDP. 

![Informe que muestra el volumen de secuencias que use TCP en lugar de UDP](media/qerguide-image-tcpvsudp.png)

_La figura 26 – TCP y UDP - conferencia_

##### <a name="analysis"></a>Análisis

Aunque desea que el uso TCP para ser lo más baja como sea posible, es posible que vea un bit de uso TCP en una implementación correcto en caso contrario. TCP por sí solo no contribuye a una llamada deficiente, por lo que las tasas de secuencia se proporcionan para ayudar a identificar si el uso TCP es un colaborador de mala calidad. 

#### <a name="tcp-investigations"></a>Investigaciones de TCP

En las plantillas proporcionadas CQD, vaya a las secuencias TCP por subred y creación de informes mediante el uso de la plantilla de redes administradas o de todas las redes. Con el fin de investigar el uso TCP, el proceso es el mismo, por lo que nos centraremos la discusión aquí en la conferencia.

> [!IMPORTANT]
> Se recomienda la tener un válido de [creación de archivo](#building-mapping) cargado por lo que puede distinguir rápidamente dentro de secuencias externas cuando se examina el uso TCP. 

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.                                  |

![Uso TCP mediante la creación y la subred](media/qerguide-image-tcpstreams.png)

_La figura 27 – secuencias TCP mediante la generación de - y subred conferencia_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Si recibe una alerta de diagnóstico "tráfico UDP se encuentra limitado, lo que provoca una calidad deficiente llamada," centrar los esfuerzos de corrección de TCP en esas subredes en primer lugar. La alerta ha identificado subredes donde el uso de TCP está afectando negativamente a la calidad de llamada.

##### <a name="remediation"></a>Corrección

Este informe identifica los edificios específicos y subredes que contribuyen al volumen de uso TCP. También se incluye un informe de adicional para identificar la dirección IP de retransmisión de Microsoft que se usó en la llamada para ayudar a aislar las reglas de firewall que faltan. Centrar los esfuerzos de corrección en los edificios que tienen el mayor volumen de secuencias TCP para maximizar el impacto.

La causa más común de uso TCP falta reglas de excepción en los servidores de seguridad o servidores proxy. Vamos a ser hablando acerca de los servidores proxy en la siguiente sección, por lo que por ahora centrar los esfuerzos en los servidores de seguridad. Mediante la creación o subred proporcionado, puede determinar qué servidor de seguridad debe actualizarse.


_Tabla 11 - instrucciones de corrección para las secuencias de TCP mediante la creación y la subred_

| Corrección        | Instrucciones     |
|--------------------|--------------------------------------|
| Configuración del firewall | Compruebe que [las direcciones y puertos IP de Office 365](https://aka.ms/o365ips) se excluyen desde el servidor de seguridad. Para problemas relacionados con los medios TCP, centrar los esfuerzos de iniciales en lo siguiente:<ul><li>Compruebe que el cliente medios subredes 13.107.64.0/18 y 52.112.0.0/14 están en las reglas de firewall.</li><li>Puertos UDP 3478 – 3481 son los puertos de medios necesarios y deben abrirse, en caso contrario, se producirá un error del cliente al puerto TCP 443.</li></ul> |
| Comprobar             | Use la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para buscar problemas con la conectividad a determinadas direcciones IP de Office 365 y puertos desde la creación afectado o subred.    |

### <a name="http-proxy"></a>Proxy HTTP

Servidores proxy HTTP no son la ruta de acceso preferida para establecer sesiones de medios, para un gran número de razones. Muchos contienen características de inspección profunda del paquete que pueden impedir conexiones con el servicio se completen y se presentan las interrupciones. Además, casi todos los servidores proxy forzar TCP en lugar de Permitir UDP, que se recomienda para la calidad de audio óptima.

Siempre se recomienda que configure el cliente para conectarse directamente a los equipos y Skype para servicios de negocios. Esto es especialmente importante para el tráfico de medios.


> [!IMPORTANT]
> Tener un válido de [creación de archivo](#building-mapping) cargado facilita distinguir correctamente dentro de secuencias de audio externas al analizar el uso de proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

El informe de secuencia de proxy HTTP de esta sección de la plantilla es muy similar a los informes TCP. No tiene el aspecto en si las llamadas son una buena o mala, pero si la llamada se conecta a través de HTTP.

![Informe de secuencias de audio que utilizan HTTP](media/qerguide-image-audiostreamswithhttp.png)

_En la figura 28 – secuencias de Audio con un uso de Proxy HTTP_

##### <a name="analysis"></a>Análisis

Desea ver como poca secuencias HTTP como sea posible. Si tiene secuencias de recorrido de su proxy, consulte a su equipo de red para asegurarse de que las exclusiones adecuadas en su lugar para que los clientes se enrutamiento directamente a los equipos o Skype para subredes de medios en línea de negocio.

Si tiene un solo proxy de internet de la organización, compruebe la correcta [las direcciones URL de Office 365 y las exclusiones de intervalo de direcciones IP](https://aka.ms/o365ips). Si más de un proxy de internet está configurado en su organización, use el HTTP subcaracterísticas informar a aislar qué edificio o subred se ve afectada.

Para las organizaciones que no se pueden omitir al servidor proxy, asegúrese de que la Skype para clientes empresariales está configurado para iniciar sesión correctamente cuando se encuentra detrás de un proxy, tal como se describe en el artículo [Skype para la empresa debe usar servidor proxy para iniciar sesión en lugar de intentar directa conexión](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Investigaciones de proxy HTTP

Este informe identifica los edificios específicos y subredes que contribuyen al uso HTTP.

> [!IMPORTANT]
> Tener un válido de [creación de archivo](#building-mapping) cargado facilita distinguir correctamente dentro de secuencias de audio externas al analizar el uso de proxy.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.

![Informe de uso de Proxy HTTP mediante la generación y subred](media/qerguide-image-httpproxyusage.png)

_Figura 29 – uso de Proxy HTTP mediante la generación y subred_

##### <a name="remediation"></a>Corrección

Se [recomienda](proxy-servers-for-skype-for-business-online.md) omitir siempre los servidores proxy de Skype para profesionales y los equipos, especialmente el tráfico de medios. Los servidores proxy no realiza Skype para la empresa más seguro, porque el tráfico ya está cifrado. Se pueden introducir problemas relacionados con el rendimiento en el entorno a través de latencia y pérdida de paquetes. Cuestiones como éstas dará como resultado una experiencia negativa con audio, vídeo y uso compartido de pantalla, donde las secuencias en tiempo real son esenciales.

La causa más común de uso HTTP falta reglas de excepción en los servidores proxy. Mediante el uso de la creación o subred siempre puede determinar rápidamente qué proxy debe configurarse para los medios de desvío.

Compruebe que los necesarios [Y los FQDN de Office 365](https://aka.ms/o365ips) están en la lista blanca en el proxy.

Para obtener más información acerca del uso de los servidores proxy con Skype para profesionales en línea y los equipos, vea [este artículo](proxy-servers-for-skype-for-business-online.md).

## <a name="endpoint-investigations"></a>Investigaciones de extremo

En esta sección se centra en las tareas de informes de versiones de cliente y el uso de dispositivos certificados. Los informes están disponibles para uso de versiones de cliente, tipo de cliente, dispositivos de captura y controladores (micrófono), los dispositivos de captura de vídeo y versiones de controlador y el proveedor de Wi-Fi de esquema.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía; Sin embargo, se siguen aplican los métodos de investigación que se explica a continuación. Hacer referencia a la descripción del informe individuales para obtener más información.

### <a name="client-versions"></a>Versiones de cliente

Los informes de este espacio de centran en la identificación de Skype para las versiones de cliente de negocio en uso y su volumen relativa en el entorno.

> [!IMPORTANT]
> Actualmente, los clientes de los equipos se distribuye y se actualizan automáticamente a través de la red de entrega de contenido de Azure y se mantengan actualizados por el servicio. Preparación de cliente y las actividades de investigación no son aplicables a los equipos.

> [!Important]
> A menos que excluir datos participantes federados, estos informes incluirán telemetría de cliente desde los extremos federados. Para excluir los extremos federados, debe agregar un [filtro de consulta](#query-filters) para el segundo identificador de inquilino establecida en el [identificador de inquilino](#tenant-id)de su organización. Como alternativa, puede utilizar un [filtro para direcciones URL](#url-filter) para excluir telemetría participante federado.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.

![Informe de cliente y dispositivos](media/qerguide-image-clientversionreport.png)

_La figura 30 - informe de versiones de cliente_

#### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Si ha recibido un diagnóstico alerta "conocidos bajo rendimiento versiones de cliente están en uso", céntrese en la actualización de los clientes en primer lugar. Ha identificado la alerta de que estos clientes afectan negativamente a la calidad de la llamada. Puede usar el informe de dispositivos (mostrado anteriormente) para ayudar a garantizar que ya no se actualizan los clientes que presentan problemas conocidos de cliente &.

#### <a name="remediation"></a>Corrección

Una parte fundamental de fuerzas experiencias de usuario de alta calidad es asegurarse de que los clientes administrados ejecutan versiones actualizadas de Skype para la empresa, además de garantizar el apoyo de audio, vídeo, red y controladores USB estén actualizados. Esto proporciona varios beneficios, entre ellos: 

-   Es más fácil administrar versiones unas frente a número de versiones.
-   Proporciona un nivel de coherencia de la experiencia.
-   Resulta más fácil solucionar los problemas con la calidad de las llamadas y facilidad de uso.
-   Microsoft no otorga continuamente las optimizaciones y mejoras generales en todo el producto. Para que los usuarios reciban estas actualizaciones, reduce sus riesgos de ejecutar un problema que ya se ha resuelto.

Limitar la implementación a las versiones de cliente que son menos de seis meses a mejorar la experiencia global del usuario y mejorar la manejabilidad reduciendo el número de versiones que deben ser compatibles.

Si utiliza sólo Office Click-to-Run, podrá automáticamente dentro de la ventana de seis meses. Se requiere ninguna acción adicional.

Si tiene una mezcla de Click-to-Run y paquetes de installer (MSI), puede usar el informe para comprobar que se actualizan con regularidad los clientes MSI. Si observa que los clientes se están quedando anticuados, trabaje con el equipo responsable de administrar las actualizaciones de Office y asegurarse de que está aprobando y la implementación de revisiones de cliente con regularidad.

También es importante tener en cuenta y asegúrese de que la red, vídeo, USB y los controladores de audioconferencias se se revisen así como. Puede ser fácil de pase por alto estos controladores y no los incluya en su estrategia de administración de revisiones.

Pueden encontrar los números de versión de Skype para la empresa a través de los siguientes vínculos:

-   [Información sobre actualizaciones de Office ProPlus la versión](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Historial de actualizaciones de Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Skype para la empresa, descargas y actualizaciones](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivos

Para hacer uso del informe de dispositivos de micrófono, es necesario comprender el concepto de la puntuación de opinión Media (MOS). MOS es la medida estándar de oro para evaluar la calidad de audio detectada. Se representa como una clasificación de número entero de 0 a 5.

La base de todas las medidas de calidad de voz es cómo una persona percibe la calidad de voz. Debido a que se ve afectada por la percepción humana, es esencialmente subjetiva. Hay varias metodologías diferentes para probar subjetiva. La mayoría de las medidas de calidad de voz se basan en una escala de clasificación (ACR) de la categorización absoluta.

En una prueba ACR subjetiva, un número estadísticamente significativo de personas valora la calidad de la experiencia en una escala del 1 (incorrecta) a 5 (excelente). El promedio de las puntuaciones es el MOS. El MOS resultante depende del intervalo de experiencias que se exponen para el grupo y el tipo de la experiencia que se clasificaron.

Debido a que no resulta práctico para realizar pruebas subjetivas de calidad de voz para un sistema de comunicación live, Microsoft Teams y Skype para la empresa generan valores MOS mediante el uso de algoritmos avanzados para predecir objetiva de los resultados de una prueba subjetiva.

El conjunto disponible de MOS y métricas asociadas proporcionan una vista a la calidad de la experiencia de entregarse a los usuarios por un dispositivo de audio. 

Al proporcionar a los usuarios con los dispositivos certificados para los equipos y Skype para la empresa, se reduce la probabilidad de que se produzcan experiencias negativas debido al propio dispositivo (que es más probable, por ejemplo, con micrófonos y altavoces portátil integrada). Para obtener más información, vea estos artículos en el [programa de certificación](/SkypeForBusiness/certification/overview) y el [catálogo de soluciones de socios](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Los informes de dispositivo se usan para evaluar el uso del dispositivo por volumen y MOS puntuación (solo audio) y pueden encontrarse en las plantillas en los clientes & dispositivos que lo acompaña. 

> [!IMPORTANT]
> A menos que excluir datos participantes federados, estos informes incluirán telemetría de cliente desde los extremos federados. Para excluir los extremos federados, debe agregar un filtro de consulta para el **Segundo identificador de inquilino** establecida en el [identificador de inquilino](#tenant-id)de su organización. Como alternativa, puede utilizar un [filtro para direcciones URL](#url-filter) para excluir telemetría participante federado.

> [!NOTE] 
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.

> [!Note]
> Es posible que tenga en cuenta cuando la visualización de este informe que ve el mismo dispositivo registrada varias veces. Esto es debido a la forma en que el dispositivo se indica que se notifiquen al CQD. Las diferencias en hardware y la configuración regional del SO provocar diferencias en cómo se informa de los datos del dispositivo.

![Informe de dispositivos (micrófono)](media/qerguide-image-devicesmicrophone.png)

_Figura 31 - informan de dispositivos (micrófono)_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Si recibe una alerta de diagnóstico "controladores de Audio están causando gotas de llamada," centrarse en solucionar relativos a dichos controladores en primer lugar. La alerta ha identificado que controladores defectuosos conocidos que provocan las llamadas colocar y afectan negativamente a confiabilidad de la llamada. Puede usar el informe controladores de micrófono (mostrado anteriormente), que se encuentra en la sección de dispositivos de cliente &, para ayudar con el proceso.

##### <a name="remediation"></a>Corrección

Normalmente, necesitará para detectar y la fase de dispositivos que no sean certificados y reemplazarlos con los dispositivos de certificado. Se incluyen algunas consideraciones para la revisión de los informes de dispositivo:

-   ¿Son los dispositivos usan certificados para los equipos y Skype para la empresa? 
-   Puede identificar a los usuarios de un dispositivo específico a través de [Análisis de llamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Compruebe para asegurarse de que disponen de los controladores de dispositivo más recientes y que su dispositivo no está conectado a través de un concentrador USB o una estación de acoplamiento. 
-   ¿Cuántas versiones diferentes de varios controladores están en uso? ¿Se va a revisar con regularidad? Asegurarse de que audio, vídeo y controladores Wi-Fi se va a revisar con regularidad le ayudará a eliminar estos como el origen de los problemas de calidad y hacer que el usuario la experiencia más coherente y predecible.

##### <a name="audio"></a>Audio

La siguiente tarea es determinar el uso general de [certified dispositivos de audio](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Se recomienda que al menos el 80% de todas las secuencias de audioconferencias usar un dispositivo de audio certificado. Esto se logra mejor al exportar el informe de dispositivos de micrófono a Excel para calcular el uso de dispositivos certificados o aprobados. Las organizaciones normalmente mantenga una lista de todos los dispositivos aprobados, para poder filtrar y ordenar los datos deben ser un proceso sencillo.

##### <a name="video"></a>Vídeo

Controladores de vídeo que son importantes para mantener actualizado también. Asegurarse de que las tarjetas de vídeo son se revisen con regularidad le ayudará a excluir controladores de vídeo como el origen de mala calidad para las secuencias de vídeo. Uso de [certificados de los dispositivos de vídeo](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) le ayudará a garantizar una experiencia de usuario sin problemas y de alta calidad. Los dispositivos de vídeo que admita la codificación nativo de H.264 se preferido, para reducir el uso de CPU durante una conferencia de vídeo.

##### <a name="wi-fi"></a>Wi-Fi

Controladores Wi-Fi también se deben revisar en así como una cadencia regular y se deben incluir en su estrategia de administración de revisiones. Muchos de los problemas de calidad pueden corregirse al mantener actualizados controladores Wi-Fi. Para obtener más información sobre la optimización de la infraestructura de Wi-Fi, consulte [este artículo acerca de la planeación de Wi-Fi](/skypeforbusiness/certification/networking-wifi).

## <a name="appendix"></a>Apéndice 

### <a name="office-365-network-connectivity-principles"></a>Principios de conectividad de red de Office 365

Antes de empezar a planear la red para la conectividad de red de Office 365, es importante comprender los principios de conectividad para administrar de forma segura el tráfico de Office 365 y obtener el mejor rendimiento posible. El artículo siguiente le ayudará a comprender las instrucciones más reciente para optimizar la conectividad de red de Office 365 de forma segura:

[Principios de conectividad de red de Office 365](https://aka.ms/pnc)

### <a name="planning-for-wi-fi"></a>Planeación de Wi-Fi

Enfoque de Microsoft para la calidad de las unidades y la agilidad en las redes inalámbricas se presenta en tres partes: planeación de un extremo a otro, de procedimientos recomendados de implementación y mantenimiento proactivo y las operaciones. Este informe breve sobre la solución le guiará a través de este proceso para garantizar un Skype inalámbrico de clase empresarial para que la experiencia empresarial:

[Garantizar un Skype inalámbrico de clase empresarial para que la experiencia empresarial](https://www.microsoft.com/download/details.aspx?id=47257)

### <a name="lync-networking-guide"></a>Guía de redes de Lync

Para obtener más información sobre los equipos y Skype para conceptos de redes empresariales y la lógica tras su importancia a la calidad, la [Guía de redes de Lync Server 2013](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) sigue siendo aplicable.

### <a name="network-performance-requirements"></a>Requisitos de rendimiento de red

La calidad de medios en tiempo real (audio, vídeo y uso compartido de aplicaciones) a través de IP depende en gran medida la calidad de la conectividad de red de extremo a otro. Óptima equipos o Skype para calidad de los medios empresariales, de la red debe cumplir las siguientes métricas de rendimiento de red.

_Tabla 12 - requisitos de rendimiento de red_

| Métrica                            | Cliente a Microsoft Edge           | Perímetro de cliente a Microsoft Edge    |
|-----------------------------------|------------------------------------|------------------------------------|
| Latencia (unidireccional)                 | \<50 ms                            | \<30 ms                            |
| Latencia (RTT o tiempo de ida y vuelta) | \<100 ms                           | \<60 ms                            |
| Pérdida de paquetes de ráfaga                 | \<10% durante un intervalo de 200 ms   | \<% 1 durante cualquier intervalo de 200 ms    |
| Pérdida de paquetes                       | \<% 1 durante cualquier intervalo de 15 segundos    | \<0,1% durante un intervalo de 15 segundos  |
| Vibración entre llegadas de paquetes       | \<30 ms durante un intervalo de 15 segundos | \<15 ms durante un intervalo de 15 segundos |
| Reordenamiento de paquetes                    | \<paquetes de salida de orden 0,05%       | \<paquetes de salida de orden 0,01%      |

Para obtener más información, vea [este artículo acerca del rendimiento de red y de calidad de medios](https://aka.ms/performancerequirements) para los equipos y Skype para profesionales en línea.

### <a name="other-resources"></a>Otros recursos

#### <a name="building-data-file"></a>Archivo de datos de creación

-   [Activar y con el panel de calidad de llamadas para Microsoft Teams y Skype para profesionales en línea](turning-on-and-using-call-quality-dashboard.md)

#### <a name="cqd-training"></a>Formación de CQD

-   <https://aka.ms/sof-cqd>

-   Taller y Guía de [Introducción a CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment)

-   [Dimensiones y medidas disponibles en el Panel de calidad de llamadas](https://aka.ms/cqd-dm)

### <a name="call-analytics-training"></a>Aprendizaje de análisis de llamada

-   [Introducción a la llamada de análisis](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurar el Análisis de llamadas](set-up-call-analytics.md)

-   [Diferencia entre el análisis de llamadas y el Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

-   [Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

### <a name="call-analytics-support"></a>Soporte de análisis de llamada

-   [Skype para el programa de vista previa de negocio](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram) de la Comunidad:

-   Para obtener soporte técnico, inicie sesión en nuestro [www.skypepreview.com](http://www.skypepreview.com)de vista previa del portal, seleccione **informe de un problema**y usar la opción **Crear nuevo error** para notificar un problema. Tenga en cuenta que los ingenieros de soporte técnico están disponibles para proporcionar compatibilidad con del lunes al viernes, entre las horas de 6 AM y 9 P.M. hora (Estados Unidos). Las solicitudes fuera de las horas se va a evaluar el día siguiente.

### <a name="devices"></a>Dispositivos

-   [Skype para Business Solutions catálogo periféricos Personal & PCs](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Creación de informes de inquilinos

-   [Paquete de contenido de adopción de Office 365](https://www.microsoft.com/microsoft-365/blog/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Análisis de uso de Microsoft 365](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)

-   [Creación de informes en Skype Empresarial Online](/SkypeForBusiness/skype-for-business-online-reporting/skype-for-business-online-reporting)

-   [Teams Microsoft reporting](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)

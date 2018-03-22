---
title: Documentar el plan de éxito de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Elegir un modelo de implementación, desarrollar una matriz (RACI) responsable-responsable-consultado-informado, crear los planes de ejecución y la gobernanza.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8352608eca00062ed2b8dbdce4682e7bdd437351
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="document-my-success-plan"></a>Documentar el plan de éxito

## <a name="execution-planning"></a>Planificación de ejecución 

Después de definir cómo se implementa el sistema de teléfono o conferencias de Audio con la solución de plano de llamar a en su organización, debe planear la ejecución del proyecto de implementación.

Si su organización tiene sólo uno o dos sitios, no tendrá que completar todos los detalles proporcionados en este artículo, pero debe leer a través de él para guiar su enfoque.

<!--ENDOFSECTION-->

## <a name="deployment-model"></a>Modelo de implementación 

Como con cualquier implementación de tecnología que transforma la forma personas trabajan en su organización, la elección de la forma correcta para llevar a cabo la implementación influirá mucho en el éxito de su implementación de voz de la nube.

Modelos de implementación posibles son las siguientes:

-   **Por sitio:** Este modelo es el adecuado para los casos donde la organización está dispersos geográficamente y bifurcaciones tienen un número significativo de empleados. Sin embargo, este modelo de implementación potencialmente puede interrumpir la comunicación dentro de los departamentos, donde los empleados del departamento están repartidos en varias ubicaciones.

-   **Por división**: este modelo suele ser la mejor opción para compañías de tamaño mediano y garantiza que los departamentos involucrados tengan la misma experiencia.

-   **Toda la empresa a la vez:** Este modelo suele ser la mejor opción para compañías pequeñas, donde todos los empleados Obtén la misma experiencia desde el primer día de la implementación.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir el modelo de ejecución de despliegue de equipos es aplicable a su organización.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar el modelo de ejecución de despliegue de equipos que ha elegido e incluyen las justificaciones empresarial y técnica.</li></ul></td></tr></table>

##<a name="raci-modeling"></a>Modelado de RACI

Para asegurarse de que tiene una mayor claridad para quién es responsable de lo que en el proyecto, utilice una matriz de asignación de responsabilidades (también conocido como una RACI — encargado, responsable, consultado e informado: matriz). Lista de la persona o grupo que es responsable y partícipe de cada tarea, junto con las partes interesadas que deban ser consultadas en el proceso de toma de decisiones y los participantes para estar informado de cada decisión y acción a lo largo de la ejecución del proyecto.

El siguiente es un ejemplo de una matriz RACI para una implementación de voz de la nube.

| Función/actividad                                         | Responsable de proyecto | Arquitecto/responsable de colaboración | Consultor | Especialista en adopción/administración de cambios | Representantes de la unidad de negocio |
|-------------------------------------------------------|--------------|------------------------------|------------|---------------------------------------|-------------------------------|
| Llamada puesta en marcha del programa de presentación                     | R, A         | C                            |            |                                       |                               |
| Configurar el panel de calidad llamar                         | I            | C                            | R, A       |                                       |                               |
| Compartir el cuestionario de descubrimiento durante las llamadas de puesta en marcha | I            | C                            | R, A       |                                       |                               |
| EnVision lanzamiento de fase                                | R, A         | C                            |            |                                       |                               |
| Taller de casos de uso de negocios                           | A            |                              |            | R                                     | C                             |
| Revisar el cuestionario de descubrimiento                    |              | R, A                         | C          |                                       |                               |
| Taller de arquitectura                                 | I            | R, A                         | C          |                                       |                               |
| Taller de fase de adopción usuario escenarios Envision       | C            | I                            | A          | R                                     |                               |
| Taller de éxito de adopción                             |              |                              | R, A       | C                                     |                               |
| Taller de preparación de cliente y dispositivos                  | I            |                              | R, A       | C                                     |                               |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir las actividades y funciones relevantes para el proyecto de implementación de voz de nube.</li><li>Decidir los equipos o personas que se asignará a la matriz de asignación de responsabilidad (matriz RACI) del proyecto de implementación de voz de nube.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documente la matriz RACI.</li></ul></td></tr></table>

## <a name="quarterly-execution-plan"></a>Plan de ejecución trimestral

Para ejecutar la implementación de voz de la nube en fragmentos manejables de trabajo, recomendamos que cree un plan de ejecución trimestralmente basándose en los resultados clave objetivos (OKRs), el modelo de implementación elegido y la capacidad de ejecución del proyecto de la organización.

Este modo puede realizar el seguimiento del progreso trimestralmente, revisar el plan si es necesario e implementar capacidades de voz de nube basadas en la capacidad de su organización para ejecutar.

Si su organización tiene sólo uno o dos sitios, no tendrá un plan de ejecución trimestral porque esperaría estar distribuido por completo en un corto período de tiempo.

El siguiente es un ejemplo de un plan de ejecución trimestral para la fase de previsión de una implementación de voz de la nube.

| Sitio/división                            | Número de empleados | Audioconferencia | Sistema telefónico                    | Trimestre para ejecutar |
|------------------------------------------|---------------------|--------------------|---------------------------------|--------------------|
| Estados Unidos: Nueva York                             | 2000                | Sí                | Sistema telefónico con Planes de llamada | Q1 CY2018          |
| Irlanda: Dublín                          | 300                 | Sí                | Sistema telefónico con Planes de llamada | Q1 CY2018          |
| Austria: Viena                          | 500                 | Sí                | N/D                             | CY2018 Q2          |
| Italia: Milán                             | 200                 | Sí                | N/D                             | CY2018 Q2          |
| América del sur: Brasil                    | 1500                | Sí                | N/D                             | CY2018 Q2          |
| India: Delhi                             | 7000                | Sí                | N/D                             | T3 CY2018          |


<table>

<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir el plan de ejecución trimestral para conseguir los resultados clave objetivos (OKRs).</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar el plan de ejecución trimestral.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="communications-and-governance-plan"></a>Comunicaciones y planeación de los controles

Para mantener los participantes del proyecto actualizado con el progreso de la implementación, debe establecer un plan de cómo communications tendrá lugar entre los principales miembros del equipo del proyecto y con las partes interesadas para debatir las cuestiones relacionadas con el estado del proyecto, tecla hitos, bloqueadores y varias revisiones del proyecto contra KSIs establecidos, mediciones operacionales y objetivos estratégicos.

El siguiente es un ejemplo de un plan de comunicaciones y control que puede aprovechar en el proyecto de implementación de voz de nube.

| Tipo                                        | Objetivos                                                                                                                                                      | Participantes | Días y hora                                     | Ubicación             | Propietario de la reunión |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|-----------------------------------------------|----------------------|---------------|
| Llamadas diaria del proyecto                       | Sincronización en el estado del proyecto, realizar un seguimiento de los bloqueadores e hitos clave                                                                                           | Por añadir          | Lunes, el martes, el miércoles, el jueves 5 P.M. PST | Virtual              | Por añadir           |
| Comité directivo semanal                   | Estado de revisión del proyecto voz de nube, informe a los ejecutivos, plantean problemas que requieren ayuda de ejecutivo para resolver                                        | Por añadir          | Viernes, 11 A.M. hora del Pacífico                        | Virtual              | Por añadir           |
| Revisión mensual de proyecto operacionales y de negocios | Comprobar el estado del proyecto con los participantes extendidos, principales puntos de contacto y patrocinadores ejecutivos; revisar el plan de implementación, KSIs y métricas operacionales | Por añadir          | Segundo martes del mes                       | Virtual o en persona | Por añadir           |
| Revisión de negocios trimestral (QBR)             | Compruebe el estado del proyecto y revisar el progreso en relación con los objetivos estratégicos, KSIs y métricas operacionales; Revisar los planes si es necesario                                 | Por añadir          | Último jueves de cada trimestre                | En persona            | Por añadir           |


<table>

<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir las comunicaciones y la planeación de los controles, incluida la frecuencia de estado regular actualizaciones (diaria, semanal, mensual o trimestral), métodos para llevar a cabo las reuniones de actualización de estado y el propietario de cada reunión.</li></ul></td></tr>

<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar el plan de comunicaciones y control corporativo.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="finalize-my-success-plan"></a>Finalizar mi plan de éxito

Un plan de éxito es el resumen de la documentación que creó en la fase de previsión.

El plan de éxito proporciona al equipo del proyecto, que puede incluir FastTrack o un socio de implementación, información suficiente para realizar los objetivos de su organización con la implementación de la conferencia de Audio o el sistema de teléfono con el servicio de llamada a Plan.

En general, un plan de éxito contiene los siguientes apartados principales, muchos que habrá tratado en la fase de previsión:

-   Caso de negocio

-   Preparación del servicio

-   Decisiones de servicio

-   Plan de ejecución

-   Plan de adopción

-   Plan operativo

### <a name="business-case"></a>Caso de negocio

Casos de uso del negocio, la lista de participantes, OKRs y KSIs, registros de riesgos y plazos de los proyectos constituyen normalmente la mayor parte de la información necesaria para un caso de negocios. Debe documentar como parte de su plan de éxito.

### <a name="service-readiness"></a>Preparación del servicio

La evaluación medioambiental proporciona la información inicial necesaria para determinar la preparación técnica de su organización para implementar conferencias de Audio o sistema de teléfono con el Plan para llamar.

Aquí incluye la evaluación de disponibilidad de servicio y el plan para tratar las áreas que necesiten corrección que descubre a través de la evaluación medioambiental.

### <a name="service-decisions"></a>Decisiones de servicio

Documente cómo planificar el sistema de teléfono o conferencias de Audio con una llamada a planear la implementación técnica de servicio para la organización.

### <a name="execution-plan"></a>Plan de ejecución

Documente cómo planificar la ejecución del proyecto para implementar la solución en toda la organización.

### <a name="adoption-plan"></a>Plan de adopción

Después de realizar la evaluación de disponibilidad de adopción, el equipo del proyecto necesita elaborar un conjunto completo de planes de comunicación, un plan de capacitación y planes de lanzamiento preliminar, inicio y posterior al iniciar actividades de adopción.

Identificar recursos para apoyar las actividades de adopción como prospectos, recepción de correos electrónicos y materiales de capacitación, junto con las personalizaciones que deberá cumplir los requisitos de su organización.

Descargar plantillas para actividades de adopción desde el [Kit de éxito de Microsoft los equipos cliente](https://www.microsoft.com/download/details.aspx?id=54244).

### <a name="operational-plan"></a>Plan operativo

Se establecerá el ejercicio de funciones operativas de asignación de roles y responsabilidades y los equipos asignados a cada función operativa, que se necesita para soportar la implementación de conferencias de Audio.

Hay que completarlo e incluir el plan operativo como parte del plan de éxito para garantizar la preparación operativa de la solución.

<table>

<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir cómo documentará su plan de éxito todo para entregar las cargas de trabajo de la voz de la nube.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Confirme que todos los componentes de su plan de éxito han sido documentados.</li><li>Agregar componentes individuales de su plan de éxito en un solo documento de resumen (opcional).</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

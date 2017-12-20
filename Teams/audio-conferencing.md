---
title: Audioconferencia en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Guía práctica para implementar la audioconferencia en Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5a65f305d924c5e5e6dac01d2391a62d8abd1243
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a>Audioconferencia en Microsoft Teams
=====================================

> [!IMPORTANT]
> Las funciones de audioconferencia se encuentran en la versión preliminar pública. Está disponible para usuarios pioneros y clientes de la versión preliminar. No es una versión definitiva, sino que podría ir cambiando conforme haya nuevas versiones o actualizaciones.

Audioconferencia en Office 365 (anteriormente conocida como Conferencia RTC) permite a los participantes unirse a las reuniones desde cualquier teléfono. Por el momento, esta característica se encuentra en Microsoft Teams (en la versión preliminar pública) y, con ella, los usuarios se pueden unir a las reuniones de Microsoft Teams a través de sus teléfonos. En las instrucciones prácticas que se detallan en este artículo, se revisan con usted todas las fases que conforman el recorrido de cliente de FastTrack para Office 365 hasta llegar a Audioconferencia: Enfoque, Incorporación y Nuevos valores.

Esto es lo que conseguirá con [Audioconferencia](https://go.microsoft.com/fwlink/?linkid=858992) en Office 365.

> [!NOTE]
> Audioconferencia es compatible con Microsoft Teams y Skype Empresarial Online. En este momento, las interfaces administrativas que controlan este servicio se encuentran en el Centro de administración de Skype Empresarial y PowerShell remoto.


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

Enfoque <a name="Envision_AudioConferencing"> </a>
=========

En la fase de Enfoque, se define el recorrido que tendrá que hacer el cliente de Office 365 y se aplicará a todo tipo de cargas de trabajo, como la de Audioconferencia.

En esta fase se definen los objetivos empresariales, con la participación de todas las partes interesadas del proyecto, para, por último, presentar:

-   un plan de éxito de gran nivel que contenga casos de uso de empresas, las principales partes interesadas, objetivos y resultados principales, indicadores de éxito principales, riesgos, evaluación del entorno, preparación para la adopción y plan operativo;

-   y, posteriormente, un plan detallado de implementación técnica de Audioconferencia para conseguir el estado final deseado.

<a name="define-business-use-cases-for-audio-conferencing"></a>Definir casos de uso de empresas para Audioconferencia
------------------------------------------------

Audioconferencia proporciona a las organizaciones unos puntos de entrada adicionales a reuniones que están programadas. Para ello, los participantes se unen a través de RTC llamando con teléfonos móviles, PBX o fijos tradicionales.

Resulta muy útil cuando el organizador o los participantes no tienen delante un ordenador o cuando no hay conexiones de datos o estas no soportan las comunicaciones por voz; por ejemplo, cuando el participante se encuentra en un área remota con una cobertura de datos móviles muy irregular o si se conecta a un servicio de red Wi-Fi público y gratuito con ancho de banda limitado, o bien cuando los participantes de la reunión prefieren acceder a ella por teléfono mediante puntos de conexión de telefonía de fácil acceso.

En este paso, los principales participantes del proyecto definirán casos de uso de empresas que admitan la implementación de Audioconferencia.

Los casos de uso de empresa se aportan con la intención de definir y documentar los resultados que se esperan y que se pueden medir. Incluyen lo siguiente:

-   Descripción del proceso de negocio actual.

-   Retos que se deben conseguir con el proceso de negocio actual definido.

-   De qué manera la tecnología puede ayudar a alcanzar estos retos.

-   Los resultados de empresa que se esperan y que se pueden medir si se alcanzan los retos impuestos anteriormente.

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><strong>Descripción del proceso de negocio actual</strong></p>
<p>Contoso utiliza en estos momentos los servicios de Conferencia RTC que ofrece el proveedor de telefonía local que le corresponde y que se cobran por minutos de reunión en reuniones internas y reuniones en las que participan usuarios externos.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><strong>Retos que se deben conseguir con el proceso de negocio actual definido</strong></p>
<p>A Contoso, el servicio de Conferencia RTC actual le supone aproximadamente 1 millón de USD al año, de donde el 75 % del coste incurrido es para reuniones internas.</p>
<p>El uso de los puntos de conexión de telefonía tradicional para unirse a las reuniones que aloja el servicio de Conferencia RTC no está en línea con el plan que está desarrollando la empresa para adoptar Microsoft Teams como plataforma de colaboración y comunicaciones moderna.</p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><strong>De qué manera la tecnología puede ayudar a alcanzar estos retos</strong></p>
<p>Al adoptar Microsoft Teams como plataforma de colaboración y comunicaciones moderna, los usuarios internos podrán fundamentalmente unirse a las reuniones con sus PC, equipados con auriculares y dispositivos de salas de reuniones adecuados. Audioconferencia estará disponible para los usuarios externos o para situaciones en las que a los participantes internos no les vaya bien el audio del PC.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><strong>Propósitos y medición de los resultados de negocio</strong></p>
<p>El cambio a Microsoft Teams como plataforma de colaboración y comunicaciones moderna, junto con el servicio de Audioconferencia, reducirá enormemente el coste que tiene el servicio de Conferencia RTC de tal manera que se espera que Contoso solo gaste aproximadamente un 20 % del coste que dedica cada año al servicio de Conferencia RTC actual.</p></td>
</tr>
</tbody>
</table>

_Tabla 1 Ejemplo de caso de uso de negocio_


Además de definir los casos de uso de negocio, a la hora de pasar al siguiente paso de la fase de Enfoque, va a ser de gran ayuda tener muy claro el ámbito organizativo y las escalas de tiempo del proyecto.

<a name="identify-key-stakeholders"></a>Identificar las partes interesadas clave
-------------------------

Los casos de uso de negocio que se definieron en el paso anterior incluirán el ámbito organizativo de la implementación de Audioconferencia y, en función de eso, se completará la matriz de participantes con la adición de las personas que tienen que estar involucradas en el proyecto.

<table>
<thead>
<tr class="header">
<th align="left">Rol</th>
<th align="left">Descripción</th>
<th align="left">Nombre, información de contacto, ubicación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Patrocinador ejecutivo del proyecto</strong></td>
<td align="left"><ul><li>La autoridad y responsable últimos del proyecto y de la consecución de los objetivos del proyecto.</li>
<li>Ayuda a resolver problemas que haya remitido el responsable de proyecto.</li>
<li>Promueve la comunicación sobre los objetivos del proyecto dentro de la empresa.</li>
<li>Responsable de tomar decisiones clave de estrategia.</li>
<li>Responsable de garantizar la disponibilidad de los recursos y el presupuesto necesarios.</p>
<li>Encargado de realizar revisiones empresariales trimestrales (QBR).</li>
<li>Obtiene el consenso y el respaldo del esfuerzo de la campaña de sensibilización.</li>
<li>Debe actuar como patrocinador de proyecto para el lanzamiento del programa.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left"><strong>Responsable de proyecto</strong></td>
<td align="left"><ul><li>Administración y liderazgo en el equipo de proyecto.</li>
<li>Se coordina con los socios y los equipos de trabajo que están involucrados en el proyecto.</li>
<li>Responsable de crear y administrar planes de proyecto para alcanzar los principales resultados para el trimestre.</li>
<li>Se encarga de solucionar problemas procedentes de diversas funciones.</li>
<li>Mantiene informado de forma regular a los patrocinadores del proyecto.</li>
<li>Se ocupa de la incorporación de aspectos de adopción en el plan de proyecto general.</li>
<li>Se encarga de realizar revisiones operativas y empresariales mensuales (MBR), como contribución a las revisiones empresariales trimestrales.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left"><strong>Arquitecto/responsable de colaboración</strong></td>
<td align="left"><ul><li>Responsable de que los ejecutivos de la empresa lleven a cabo la estrategia de colaboración.</li>
<li>Debe analizar y elegir los productos de colaboración para que la empresa cumpla los objetivos de negocio.</li>
<li>Es responsable de diseñar las operaciones para los productos de colaboración.</li>
<li>Define el modelo de operación y soporte.</li>
<li>Debe contribuir a las revisiones empresariales mensuales y trimestrales.</li><ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left"><strong>Consultor</strong></td>
<td align="left"><ul><li>Es responsable de los servicios de configuración.</li>
<li>Contribuye a la arquitectura general de soluciones.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left"><strong>Jefe de proyecto</strong></td>
<td align="left"><ul><li>Se encarga de desarrollar y mantener el plan de proyecto.</li>
<li>Se encarga de que las entregas de proyecto se realicen en línea con el plan y el presupuesto del proyecto.</li>
<li>Registra y administra los problemas que surgen en el proyecto, incluidas las remisiones a escalas superiores.</li>
<li>Lleva a cabo llamadas de control semanales.</li>
<li>Es el encargado de relacionarse y mantener informados a los patrocinadores ejecutivos del proyecto.</li>
<li>Trabaja con el arquitecto para definir el enfoque de administración de cambios y los planes de comunicación.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left"><strong>Especialista en adopción/administración de cambios</strong></td>
<td align="left"><ul><li>Aporta su punto de vista en la fase de descubrimiento sobre los procesos de adopción y formación.</li>
<li>Participa en los talleres de estrategia de adopción.</li>
<li>Se encarga de desarrollar la estrategia de adopción y es responsable de ella.</li>
<li>Se encarga de desarrollar y llevar a cabo el plan de comunicación.</li>
<li>Es responsable de proporcionar formación a los usuarios finales.</li>
<li>Recopila comentarios y realiza encuestas.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left"><strong>Responsable de redes</strong></td>
<td align="left"><ul><li>Aporta su punto de vista en la fase de descubrimiento sobre el diseño de redes.</li>
<li>Participa en la planificación durante el taller de Enfoque.</li>
<li>Coordina el trabajo del equipo de redes durante la ejecución del proyecto.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left"><strong>Responsable de seguridad</strong></td>
<td align="left"><ul><li>Aporta su punto de vista en la fase de descubrimiento sobre los procesos y el diseño de la seguridad.</li>
<li>Participa en la planificación durante el taller de Enfoque.</li>
<li>Coordina el trabajo del equipo de seguridad durante la ejecución del proyecto.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left"><strong>Responsable de telefonía</strong></td>
<td align="left"><ul><li>Aporta su punto de vista en la fase de descubrimiento sobre el diseño de la telefonía.</li>
<li>Participa en la planificación durante el taller de enfoque.</li>
<li>Coordina el trabajo del equipo de telefonía durante la ejecución del proyecto.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left"><strong>Responsable de escritorio</strong></td>
<td align="left"><ul><li>Aporta su punto de vista en la fase de descubrimiento sobre los clientes y el proceso de actualización.</li>
<li>Participa en la planificación durante el taller de enfoque.</li>
<li>Coordina el trabajo del equipo de escritorio durante la ejecución del proyecto.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left"><strong>Responsable del servicio de asistencia y soporte técnico</strong></td>
<td align="left"><ul><li>Aporta su punto de vista en la fase de descubrimiento sobre el modelo operativo y de soporte.</li>
<li>Participa en la planificación durante el taller de enfoque.</li>
<li>Participa en la planificación del modelo de soporte.</li>
<li>Coordina el trabajo de los recursos y los equipos de soporte técnico durante la ejecución del proyecto.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left"><strong>Representantes de la unidad de negocio</strong></td>
<td align="left"><ul><li>Contribuyen en la creación de los materiales y guías de adopción basados en el usuario final.</li>
<li>Contribuyen en la creación de casos de uso de negocio y los revisan.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left"><strong>Responsable de implementación</strong></td>
<td align="left"><ul><li>Garantiza que se cumplan los requisitos previos de implementación.</li>
<li>Involucra a los recursos del cliente para que se impliquen en la preparación y la implementación de las actividades de las primeras fases.</li>
<li>Participa en reuniones para revisar, preparar e implementar el estado.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left"><strong>Administradores de TI</strong></td>
<td align="left"><ul><li>Los profesionales de TI se encargan de ayudar en la planificación y ejecución de pruebas.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left"><strong>Propietario del servicio</strong></td>
<td align="left"><ul><li>Es responsable de que el servicio de Audioconferencia funcione de forma continua.</li>
<li>Propietario del servicio de Audioconferencia.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left"><strong>Experto en calidad</strong></td>
<td align="left"><ul><li>Genera calidad, fiabilidad y recopila opiniones de los usuarios.</li>
<li>Identifica las tendencias en la calidad y propicia la corrección de los problemas con los equipos correspondientes.</li>
<li>Mantiene informada a la directiva a través del comité directivo.</li>
<li>Informa sobre la calidad, la fiabilidad y las opiniones de los usuarios a través de Valorar mi llamada y Net Promoter Score.</li></ul></td>
<td align="left">Por añadir</td>
</tr>
</tbody>
</table>

_Tabla 2 Ejemplo de plantilla de matriz de participantes_


> [!NOTE]
> La tabla de ejemplos anterior y las tablas siguientes que se ofrecen en este documento se pueden usar como plantillas. La frase "Por añadir" indica que falta por completar con información como parte del proceso de planificación.



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Definir objetivos y resultados principales, indicadores de éxito principales y riesgos
--------------------------------------------------------------------

Con la participación de todas las partes involucradas en el proyecto, los casos de uso, el ámbito organizativo y las escalas de tiempo del proyecto se pueden traducir en objetivos y resultados principales (OKR, del inglés "objectives and key results"), y las medidas de éxito del proyecto se pueden definir en una lista de indicadores de éxito principales (KSI, del inglés "key success indicators").

Al contar con la plena participación de todos las partes involucradas en el proyecto a la hora de definir los OKR y los KSI, se garantiza el sentido de propiedad y su adecuación a los requisitos organizativos del negocio.

Los OKR contendrán una lista de los objetivos que se establecieron al inicio del proyecto, con los principales resultados que se pueden medir y que se definen trimestralmente. Los principales resultados se revisan mensualmente para hacer un seguimiento del estado del proyecto general y, en función de cómo avancen, se podrán ir ajustando los planes trimestrales.

<table>
<thead>
<tr class="header">
<th align="left"><p><strong>Visión:</strong> aumentar la productividad maximizando las inversiones de Office 365</p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Objetivos</strong></td>
<td align="left"><strong>Resultados principales</strong></td>
<td align="left"><strong>Pendiente</strong></td>
</tr>
<tr class="even">
<td align="left">Implementar Audioconferencia en Microsoft Teams al final del año fiscal 2018</td>
<td align="left">T1 2018: implementar Audioconferencia en Microsoft Teams globalmente</td>
<td align="left"><p>Enfoque</p>
<ul><li>Crear el plan de éxito</li>
<li>Crear un plan técnico de implementación muy detallado</li></ul>
<p>Incorporación</p>
<ul><li>Ejecutar el plan de éxito</li>
<li>Ejecutar el plan técnico de implementación</li></ul></td>
</tr>
<tr class="odd">
<td align="left">Retirar globalmente el servicio de Conferencia RTC antiguo a mediados del año fiscal 2018</td>
<td align="left">T2 2018: retirar globalmente el servicio de Conferencia RTC antiguo</td>
<td align="left"><p>Nuevos valores</p>
<ul><li>Potenciar la participación del usuario e impulsar la adopción</li>
<li>Administrar y prepararse para el cambio</li>
<li>Medir, compartir el éxito e iterar</li></ul></td>
</tr>
</tbody>
</table>

_Tabla 3 Ejemplo de OKR_


Los KSI miden la calidad y el éxito de los resultados principales, y complementan la naturaleza binaria de los OKR (conseguidos o no conseguidos) al detallar los buenos o los malos resultados. Para definir los KSI, recomendamos aplicar criterios SMART o criterios "específicos, medibles, atribuibles, realistas y temporales".

<table>
<thead>
<tr class="header">
<th align="left">Tipo</th>
<th align="left"><p>Cuestiones &amp;</p>
<p>criterios de KSI</p></th>
<th align="left">Cómo se miden</th>
<th align="left">Criterios de éxito</th>
<th align="left">Medidos</th>
<th align="left">Responsable</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Uso/adopción</strong></td>
<td align="left">La calidad de las llamadas es igual o mejor que en la solución anterior</td>
<td align="left">Encuesta</td>
<td align="left">El 80 % de los usuarios está de acuerdo o muy de acuerdo</td>
<td align="left">Tras la habilitación y trimestralmente</td>
<td align="left">Equipo de tecnología de la información</td>
</tr>
<tr class="even">
<td align="left"><strong>Uso/adopción</strong></td>
<td align="left">El proceso de comunicación es más sencillo con Microsoft Teams</td>
<td align="left">Encuesta</td>
<td align="left">El 80 % de los usuarios está de acuerdo o muy de acuerdo</td>
<td align="left">Tras la habilitación y trimestralmente</td>
<td align="left">Equipo de administración de cambios</td>
</tr>
<tr class="odd">
<td align="left"><strong>Uso/adopción</strong></td>
<td align="left">Los usuarios utilizan la solución activamente</td>
<td align="left">Informes de Office 365, panel de calidad de llamadas</td>
<td align="left">El 80 % de los usuarios son usuarios activos diarios</td>
<td align="left">A diario</td>
<td align="left">Equipo de administración de cambios</td>
</tr>
<tr class="even">
<td align="left"><strong>Uso/calidad</strong></td>
<td align="left">El porcentaje de llamadas/conferencias de mala calidad debe ser mínimo</td>
<td align="left">Panel de calidad de llamadas</td>
<td align="left">&lt; Un 5 % de llamadas de mala calidad al mes</td>
<td align="left">A diario</td>
<td align="left">Equipo de tecnología de la información</td>
</tr>
<tr class="odd">
<td align="left"><strong>Uso/soporte</strong></td>
<td align="left">Sé cómo conseguir soporte técnico</td>
<td align="left">Encuesta</td>
<td align="left">El 90% de los usuarios está de acuerdo o muy de acuerdo</td>
<td align="left">Tras la habilitación y trimestralmente</td>
<td align="left">Equipo de administración de cambios</td>
</tr>
<tr class="even">
<td align="left"><strong>Uso/soporte</strong></td>
<td align="left">Estoy satisfecho con la calidad del soporte técnico</td>
<td align="left">Encuesta</td>
<td align="left">El 80 % de los usuarios está de acuerdo o muy de acuerdo</td>
<td align="left">Tras cada incidente</td>
<td align="left">Equipo de tecnología de la información</td>
</tr>
<tr class="odd">
<td align="left"><strong>Financiero</strong></td>
<td align="left">Reducción de los minutos de conferencias antiguas</td>
<td align="left">Sistema financiero</td>
<td align="left">Cumplir el ROI definido</td>
<td align="left">Basado en ROI</td>
<td align="left">Equipo de administración de cambios</td>
</tr>
</tbody>
</table>

_Tabla 4 Ejemplo de KSI_


Como parte de este ejercicio, hay que identificar los riesgos del negocio y definir un plan de mitigación para cada uno de los riesgos que se identifiquen. Esta información se puede plasmar en un plan de riesgos.

<table>
<thead>
<tr class="header">
<th align="left">Riesgo</th>
<th align="left">Probabilidad</th>
<th align="left">Impacto</th>
<th align="left">General</th>
<th align="left">Plan de mitigación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Con la próxima fusión se sumarán hasta 1000 personas</td>
<td align="left">Alta</td>
<td align="left">Alta</td>
<td align="left">Alta</td>
<td align="left"><p>Para las empresas fusionadas, OKR independiente con proceso propio (Enfoque, Incorporación, Nuevos valores).</p>
<p>No se deben incluir en los OKR existentes.</p></td>
</tr>
<tr class="even">
<td align="left">La portabilidad de los números de teléfono retrasará la finalización del proyecto.</td>
<td align="left">Alta</td>
<td align="left">Alta</td>
<td align="left">Alta</td>
<td align="left"><p>Se debe preparar con antelación toda la información para la portabilidad de los números de teléfono (registro de servicios al cliente, detalles de facturación, carta de autorización).</p>
<p>La escala de tiempo del proyecto se debe ajustar para incluir el tiempo que se tarda en realizar la portabilidad de los números de teléfono.</p>
<p>Se debe comunicar el uso de los nuevos números de conferencia de acceso telefónico local a los participantes externos.</p></td>
</tr>
<tr class="odd">
<td align="left">Se ha planificado rediseñar las redes</td>
<td align="left">Alta</td>
<td align="left">Mediana</td>
<td align="left">Mediana</td>
<td align="left">Antes de implementar Microsoft Teams como plataforma de colaboración y comunicaciones moderna, evalúe la preparación de la red en los sitios que se incluyen en el ámbito del proyecto.</td>
</tr>
</tbody>
</table>

_Tabla 5 Ejemplo de plan de riesgos_


<a name="assess-environment-and-evaluate-adoption-readiness"></a>Evaluar el entorno y la preparación que se tiene para la adopción
--------------------------------------------------

Para conseguir los OKR que se pretenden, es posible que tenga que definir una arquitectura de alto nivel de la solución. De este modo, se evalúan todos los aspectos relacionados con la infraestructura de TI y telefonía, las redes y las operaciones a través del descubrimiento del entorno.

Todas las cuestiones relacionadas con la informática para usuarios finales, como la evaluación de la preparación de los ordenadores personales y los dispositivos móviles para admitir casos de uso de empresas para Audioconferencia, se incluirán como parte del proceso de descubrimiento del entorno.

Con el descubrimiento del entorno también se puede poner de manifiesto si hay algún requisito para [transferir números de teléfono a Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e). De este modo, la organización podrá ajustar el plan de proyecto y preparar toda la información que necesite para la portabilidad de los números. El descubrimiento del entorno se puede llevar a cabo mediante el siguiente [cuestionario](https://go.microsoft.com/fwlink/?linkid=858995).

En el descubrimiento del entorno se debe incluir la evaluación de preparación de la red para asegurarse de que esta pueda soportar la implementación del servicio de Audioconferencia.

También se puede determinar si la red está preparada para soportar el servicio de Audioconferencia evaluando la información que se recopila en el descubrimiento del entorno (como los detalles de la conectividad a Internet y la topología de WAN, los vínculos a sitios, el ancho de banda disponible) y los datos de los análisis de personas (que se pueden traducir en el uso que se espera de cada carga de trabajo) en la [herramienta My Advisor Network Planner](https://go.microsoft.com/fwlink/?linkid=858999). Para confirmar en mayor medida el estado de la red, se puede realizar una simulación del tráfico multimedia en tiempo real con soluciones que proporcione [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) o los [socios de las herramientas para la evaluación de la preparación de la red](https://go.microsoft.com/fwlink/?linkid=859003).

Con los resultados de esta evaluación se podrá tener una idea más clara de la corrección o la optimización que se necesita hacer en la red para que la implementación de Audioconferencia se pueda desarrollar correctamente.

Para evaluar la preparación para la adopción se puede ejecutar un análisis de personas que genere una lista de las personas de la organización en las que se podrá llevar a cabo la implementación del servicio de Audioconferencia. El análisis de personas incluye la identificación de otros periféricos y dispositivos que se necesitan para obtener los resultados de negocio que se desean.

Para realizar el análisis de personas, puede realizar un taller en el que se involucre a todas las partes relevantes del proyecto mediante la plataforma de talleres [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) y [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006). El resultado de este taller de análisis de personas se puede resumir en un informe que se elabora con la plantilla [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007).


> [!NOTE]
> Si bien el cuestionario de descubrimiento y los ejemplos de análisis de personas se crearon en un principio para Skype Empresarial Online, la mayoría del contenido es válido para Microsoft Teams. Modifique y quite los elementos que crea que no son relevantes de los objetivos del proyecto.


Los riesgos técnicos se pueden identificar como parte de una evaluación del entorno y la evaluación de la preparación para la adopción, y se puede desarrollar un plan de mitigación para cada uno de los riesgos que se identifiquen. Esta información se debe incorporar en el plan de riesgos.

<a name="map-operational-roles"></a>Asignar roles operativos
---------------------

Planificar las operaciones e identificar a los equipos que utilizarán el servicio de Audioconferencia es un paso muy importante, ya que las operaciones deben comenzar cuando se habiliten los primeros usuarios del piloto. Cada uno de los equipos que se identifiquen debe revisar y aceptar las tareas y las responsabilidades que se identifiquen y deben comenzar la preparación para utilizar el servicio de Audioconferencia. En la fase de preparación se podría incluir formación y capacitación, contratación de más personal o garantizar que los proveedores externos están listos para ofrecer el servicio.

<table>
<thead>
<tr class="header">
<th align="left">Rol operativo</th>
<th align="left">Descripción</th>
<th align="left">Equipo</th>
<th align="left">Datos de contacto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Propietario del servicio</td>
<td align="left">Propietario del servicio, interactuar con las divisiones de la empresa, estrategia</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left">Operaciones de Audioconferencia</td>
<td align="left">Operaciones diarias, transferencia/adición/cambio de cuenta de dispositivo y usuario, supervisión</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left">Administrador de inquilinos</td>
<td align="left">Cambiar la configuración de todos los inquilinos, habilitar nuevas características</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left">Servicio de asistencia</td>
<td align="left">Interactuar con usuarios finales que necesitan soporte</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left">Operaciones de red</td>
<td align="left">Cubre LAN, WAN, Wi-Fi y acceso a Internet</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left">Cliente y equipo de puntos de conexión</td>
<td align="left">Administrar implementaciones de escritorio</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left">Operaciones de identidad</td>
<td align="left">Administrar infraestructura de identidad (AD, ADFS, Azure AD)</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
</tr>
<tr class="even">
<td align="left">Adopción/administración de cambios</td>
<td align="left">Administrar el reconocimiento, la formación y la adopción de la solución</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
</tr>
<tr class="odd">
<td align="left">Operaciones de Exchange</td>
<td align="left">Administra el entorno de Exchange</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
</tr>
</tbody>
</table>

_Tabla 6 Ejemplo de la asignación de roles operativos_


Para que la asignación de roles operativos se pueda llevar a cabo de una forma más detallada, incluidas las tareas asociadas a cada rol operativo, el [libro de trabajo para la asignación de roles operativos](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) puede ser muy útil para capturar los detalles que determinarán con claridad cuáles son los roles y las responsabilidades que respaldarán el servicio de Audioconferencia.

<a name="document-success-plan"></a>Documentar el plan de éxito
---------------------

Un plan de éxito es la documentación que se crea en la fase de Enfoque y que consta del caso de negocio, la preparación del servicio, el plan de adopción y el plan operativo.

El plan de éxito proporcionará al equipo del proyecto (que puede incluir FastTrack o el asociado de implementación) la información que le permita alcanzar los objetivos de la organización con el servicio de Audioconferencia.

En general, un plan de éxito contendrá las siguientes secciones principales:

-   Caso de negocio

-   Preparación del servicio

-   Plan de adopción

-   Plan operativo

### <a name="business-case"></a>Caso de negocio

Los casos de uso de negocio, las partes interesadas, los OKR y los KSI, los riesgos y las escalas de tiempo del proyecto configuran normalmente la mayor parte de la información requerida para un caso de negocio. Es necesario documentarlos como parte del plan de éxito.

### <a name="service-readiness"></a>Preparación del servicio

Con la evaluación del entorno se obtiene la información inicial que se necesita para determinar la preparación técnica de la organización para implementar la Audioconferencia.

Aquí se incluye el plan para abordar las áreas que necesitan correcciones y que se han detectado durante la evolución del entorno. Como parte del plan de éxito, hay que incluir la evaluación de preparación del servicio y el plan de corrección.

### <a name="adoption-plan"></a>Plan de adopción

Tras evaluar la preparación de la adopción, es necesario completar otra planificación más detallada para que el equipo del proyecto pueda elaborar un conjunto completo de planes de comunicación, un plan de formación y actividades de adopción previas al lanzamiento, para el lanzamiento y posteriores al lanzamiento.

En este paso también se identifican los recursos que respaldan las actividades de adopción, como prospectos, correos electrónicos de bienvenida y materiales de formación, junto con las personalizaciones que hay que hacer para cumplir los requisitos de la organización.

Las plantillas para las actividades de adopción están disponibles [aquí](https://www.microsoft.com/download/details.aspx?id=54244).

### <a name="operational-plan"></a>Plan operativo

El ejercicio para la asignación de roles operativos establecerá los roles y las responsabilidades, así como los equipos asignados a cada rol operativo para respaldar la implementación de Audioconferencia.

Hay que completarlo e incluir el plan operativo como parte del plan de éxito para garantizar la preparación operativa de la solución.

Planificación de Audioconferencia en Microsoft Teams  <a name="Planning_AudioConferencing"> </a>
========================================

Para planificar la implementación de Audioconferencia en Microsoft Teams, hay que tomar una serie de decisiones con antelación para preparar mejor a la organización ante la implementación de una solución que cumpla los requisitos del negocio. Estas decisiones se documentarán en un plan de implementación técnico.

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a>Disponibilidad de Audioconferencia

Audioconferencia está disponible en estos [países y regiones](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).


> [!IMPORTANT]
> Por imperativo de carácter jurídico, para que Audioconferencia pueda estar disponible en organizaciones multinacionales, el contrato de suscripciones de Office 365 debe provenir de países y regiones que están cubiertos por el servicio de Audioconferencia.

Tras confirmar que su organización reúne los requisitos para poder usar el servicio de Audioconferencia, recopile la lista de ubicaciones de usuario u oficinas en las que se implementará el servicio de Audioconferencia según la lista de países y regiones disponibles.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Puntos de decisión</td>
<td align="left"><p>Decida qué oficinas o ubicaciones de usuario implementarán el servicio de Audioconferencia.</p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Siguientes pasos</td>
<td align="left"><p>Decida qué oficinas o ubicaciones de usuario se habilitarán para el servicio de Audioconferencia.</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Oficina</th>
<th align="left">Ubicación</th>
<th align="left">Servicio de conferencia RTC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">One Epping Road</td>
<td align="left">Australia</td>
<td align="left">Audioconferencia</td>
</tr>
<tr class="even">
<td align="left">100 Cyberport Road</td>
<td align="left">RAE de Hong Kong</td>
<td align="left">Conferencia RTC antigua</td>
</tr>
<tr class="odd">
<td align="left">One Marina Boulevard</td>
<td align="left">Singapur</td>
<td align="left">Audioconferencia</td>
</tr>
<tr class="even">
<td align="left">32 London Bridge Street</td>
<td align="left">Reino Unido</td>
<td align="left">Audioconferencia</td>
</tr>
<tr class="odd">
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Francia</td>
<td align="left">Audioconferencia</td>
</tr>
</tbody>
</table>

_Tabla 7 Ejemplo de una lista de habilitación del sitio de servicio de Audioconferencia_


## <a name="licensing-for-audio-conferencing"></a>Licencias para Audioconferencia

La [licencia de Audioconferencia](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), anteriormente conocida como licencia de Conferencia RTC para Skype Empresarial, está disponible como parte de los planes de suscripción de Office 365 E5 o como un complemento a los planes de suscripción de Office 365 E3 o E1.

> [!NOTE]
> Las conferencias de acceso telefónico local o RTC no admiten los proveedores de servicios de audioconferencia de terceros (ACP).<sup></sup> <br>Si está usando la Conferencia RTC para Skype Empresarial Online, puede beneficiarse al instante de Audioconferencia en Microsoft Teams.

Para proporcionar números de teléfono gratuitos para puentes de conferencia y admitir las conferencias por aceptación de llamada de números de teléfono internacionales, tendrá que configurar [Créditos de comunicaciones](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) para su organización.


> [!IMPORTANT]
> En algunos países solo se pueden usar números de teléfono gratuitos para puentes de conferencia y, en tal caso, hay que usar obligatoriamente Créditos de comunicaciones para poder admitir el acceso telefónico local para esos países.

La primera consideración que hay que tener en cuenta a la hora de implementar Créditos de comunicaciones es decidir la cantidad inicial de fondos que se deben adquirir. La cantidad de fondos que se recomienda se puede mencionar en la documentación de [Créditos de comunicaciones](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059).

Si su organización decide utilizar la recarga automática, también se incluye en la documentación de [Créditos de comunicaciones](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) una recomendación para el umbral (la cantidad más baja de fondos). El importe de recarga automática se determina por el uso real. El uso de Créditos de comunicación se debe supervisar con el paso del tiempo y hay que ajustar la cantidad de recarga según sea necesario.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Puntos de decisión</td>
<td align="left"><ul><li>Si su organización aún no ha adquirido las licencias de Audioconferencia que necesita, decida si las licencias de Audioconferencia se van a adquirir incrementando las suscripciones existentes de Office 365 o comprando complementos de Audioconferencia.</li>
<li>Decida si los Créditos de comunicaciones son necesarios para la implementación de Audioconferencia. En tal caso, decida la cantidad inicial de fondos que se va a comprar. Cuando sea necesario, decida la cantidad para el umbral y la cantidad de autorecarga.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Siguientes pasos</td>
<td align="left"><ul><li>Documente los usuarios a los que se les asignará la licencia de Audioconferencia.</li>
<li>Documente el plan de Créditos de comunicaciones (cantidad inicial, cantidad de umbral, cantidad de recarga automática).</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Usuario</th>
<th align="left">Oficina</th>
<th align="left">Licencia de Office 365</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E3, complemento de Audioconferencia</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">Office 365 E3, complemento de Audioconferencia</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E3, complemento de Audioconferencia</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E3, complemento de Audioconferencia</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E5</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Office 365 E3, complemento de Audioconferencia</td>
</tr>
</tbody>
</table>

_Tabla 8 Ejemplo de una lista de asignación de licencias para los organizadores de reuniones de Audioconferencia_

<table>
<thead>
<tr class="header">
<th align="left">Cantidad inicial</th>
<td align="left">1000 $</td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left">Cantidad de umbral</th>
<td align="left">400 $</td>
</tr>
<tr class="header">
<th align="left">Cantidad de recarga automática</th>
<td align="left">Por añadir</td>
</tr>
</tbody>
</table>

_Tabla 9 Ejemplo de números de planificación de Créditos de comunicaciones_


## <a name="conference-bridge-phone-numbers"></a>Números de teléfono para puentes de conferencia

El servicio de Audioconferencia en Office 365 incluye:

-   Varios tipos de números de teléfono para puentes de conferencia (gratuitos y de pago)

-   Varias categorías del número de teléfono (dedicado y compartido)

-   Soporte para varios idiomas del puente de conferencia (principal y secundario)

-   Un número de teléfono predeterminado para el inquilino.

La descripción completa de las funcionalidades que se incluyen se puede extraer de [Configurar conferencias de acceso telefónico local o RTC para Skype Empresarial](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) y [Números de teléfono para las conferencias de Audio](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**

> [!NOTE]
> Los números de teléfono dedicados para puentes de conferencia se tienen en cuenta como parte del límite de números de teléfono que se pueden adquirir por inquilino, según el número de licencias que corresponden, como se describe en [Obtener números de teléfono de servicio de Skype Empresarial](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734). Los números de teléfono gratuitos para puentes de conferencia necesitan los Créditos de comunicaciones.

Si ya hay números de teléfono para puentes de conferencia que hay que transferir al servicio de Audioconferencia, teniendo en cuenta que cumplen los requisitos para cada país o región, los números de teléfono para puentes de conferencia existentes se pueden transferir a Microsoft.


> [!NOTE]
> La complejidad que entraña la transferencia de los números de teléfono a Microsoft varía enormemente según cuáles sean los países y las regiones, los operadores, el número de circuitos involucrados y muchos otros factores. Para planificar la portabilidad de los números de teléfono, revise la [guía de portabilidad de números](https://go.microsoft.com/fwlink/?linkid=859011).

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

Encontrará más detalles sobre la transferencia de números de teléfono al servicio de Audioconferencia en [Transferir números de teléfono a Skype Empresarial Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Puntos de decisión</td>
<td align="left"><ul><li>Decida si la organización necesita números de teléfono dedicados para puentes de conferencia.</li>
<li>Decida cómo se obtendrán los números de teléfono dedicados para puentes de conferencia para las oficinas o ubicaciones de usuario que entran dentro de la implementación de Audioconferencia (obtenerlos de Microsoft o transferir números de teléfono existentes).</li>
<li>Si elige obtenerlos de Microsoft, decida el método para obtener los números de teléfono (envío de formulario o automatizado) para las oficinas o ubicaciones de usuario que entran dentro de la implementación de Audioconferencia.</li>
<li>Decida las preferencias de idioma que se deben configurar para cada número de teléfono dedicado para puentes de conferencia.</li>
<li>Decida el número de teléfono predeterminado para puentes de conferencia del inquilino.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Siguientes pasos</td>
<td align="left"><ul><li>Documente el plan maestro para la adquisición de números de teléfono y especifique cómo se obtendrán los números de teléfono para cada oficina o ubicación de usuario que entra dentro de la implementación de Audioconferencia.</li>
<li>Si corresponde, complete <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">un formulario de solicitud de número de teléfono nuevo</a> por cada oficina o ubicación.</li>
<li>Si elige transferir números de teléfono existentes, revise la <a href="https://go.microsoft.com/fwlink/?linkid=859011">guía de portabilidad de números</a> para planificar y ajustar el tiempo de implementación de Audioconferencia de forma acorde.</li>
<li>Documente las configuraciones de los números de teléfono para puentes de conferencia (números de teléfono compartidos y dedicados para puentes de conferencia, preferencias de idioma para cada número de teléfono dedicado para puente de conferencia, número de teléfono predeterminado para puente de conferencia del inquilino).</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Oficina</th>
<th align="left">Adquisición de número de puente y tipo de puente</th>
<th align="left">Número de puente</th>
<th align="left">Idioma de puente</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">One Epping Road</td>
<td align="left">Adquirir nuevo, dedicado</td>
<td align="left">Por añadir</td>
<td align="left">Inglés (Australia)</td>
</tr>
<tr class="even">
<td align="left">One Marina Boulevard</td>
<td align="left">Adquirir nuevo, compartido</td>
<td align="left">Por añadir</td>
<td align="left">Inglés (Estados Unidos), chino (simplificado, RPC)</td>
</tr>
<tr class="odd">
<td align="left">32 London Bridge Street</td>
<td align="left">Puerto existente, dedicado</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">Inglés (Reino Unido)</td>
</tr>
<tr class="even">
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Adquirir nuevo, dedicado</td>
<td align="left">Por añadir</td>
<td align="left">Francés (Francia), inglés (Reino Unido)</td>
</tr>
</tbody>
</table>

_Tabla 10 Ejemplo de detalles de puentes de conferencia_


> [!NOTE]
> La tabla de ejemplos anterior y las tablas siguientes que se ofrecen en este documento se pueden usar como plantillas. La frase "Por añadir" indica que falta por completar con información como parte del proceso de planificación.

## <a name="conference-bridge-settings"></a>Configuración de puentes de conferencia

Las opciones de configuración que se aplican a toda la organización en torno a la experiencia de unión a reuniones de Audioconferencia (notificación de entrada y salida de la reunión y grabación del nombre de la persona que llama), la longitud del PIN del organizador de la reunión, y la notificación de correo electrónico están disponibles para personalizar aún más la experiencia del usuario final.

-   Las notificaciones de entrada y salida de la reunión están disponibles en la forma de nombre grabado, número de teléfono y tonos.

-   La longitud del PIN se puede configurar de 4 a 12 dígitos, siendo el PIN de 5 dígitos el predeterminado.

-   Los correos electrónicos de notificación tras la habilitación de la licencia de Audioconferencia o cualquier otro cambio impulsado por el administrador se habilitan de forma predeterminada. Esta característica se puede deshabilitar, de manera que tomará el control de las comunicaciones de los usuarios finales de su organización.

Para los usuarios a los que se les asigne una licencia de Audioconferencia, los números gratuitos o de pago predeterminados (los cuales se muestra en las coordenadas de Audioconferencia) se pueden configurar para usar:

-   el predeterminado a nivel de inquilino,

-   los números de teléfono para puentes de conferencia que se asignan automáticamente o

-   los números de teléfono para puentes de conferencia que se definen manualmente para cada usuario.

Los números de teléfono para puentes de conferencia específicos para usuarios son útiles en organizaciones globales y nacionales en las que los usuarios están repartidos en distintas ubicaciones y deben proporcionar números locales como números de teléfono para puentes de conferencia en las invitaciones a reuniones.

Los participantes que se unan desde distintas ciudades o desde otros países pueden buscar otros números configurados a nivel de inquilino, pero estos números no aparecen directamente en las invitaciones para las reuniones. Las invitaciones para reuniones incluyen un vínculo con el que los participantes se dirigirán a la página de números de acceso telefónico a conferencias de Microsoft Teams donde pueden buscar los números de teléfono para puentes de conferencia más próximos que estén disponibles para su ubicación.

También puede configurar cómo gestiona cada organizador de una reunión los autores de llamada que no se han autenticado. Puede elegir que el organizador de la reunión tenga que iniciar la reunión antes de que se admitan los autores de llamada sin autenticar o bien permitir que los autores de llamada que no se han autenticado inicien una reunión.

Hay otras configuraciones que se pueden aplicar para cada usuario y poder controlar el uso de los números de teléfono gratuitos para puentes de conferencia y realizar llamadas desde una conferencia.

> [!NOTE]
> Estos controles relacionados con los costes solo están disponibles en este momento para clientes de la versión preliminar. Puede inscribir a su organización en el programa de versión preliminar en [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).

Con estos controles, puede decidir si los organizadores de las reuniones pueden proporcionar números de teléfono gratuitos para puentes de conferencia en las reuniones que organicen ellos y controlar si los participantes pueden llamar desde las reuniones que organicen ellos. El nivel de control de la aceptación de llamada abarca desde deshabilitar la aceptación de llamada, permitir solo llamar a números nacionales o permitir llamar a números nacionales e internacionales.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Puntos de decisión</td>
<td align="left"><ul><li>Decida si la organización necesita notificaciones de entrada y salida y, en caso afirmativo, el tipo de notificación que se implementará (tonos, número de teléfono o nombre grabado).</li>
<li>Decida la longitud del PIN de Audioconferencia que cumpla los requisitos de seguridad de la organización.</li>
<li>Decida si la organización quiere controlar las comunicaciones de los usuarios finales que estén relacionadas con el servicio de Audioconferencia.</li>
<li>Decida qué números de teléfono para puentes de conferencia se asignarán a cada organizador de reuniones.</li>
<li>Decida si algunos organizadores de reuniones necesitan la opción de usar números de teléfono gratuitos para puentes de conferencia para sus reuniones.</li>
<li>Decida si algunos organizadores de reuniones necesitan la opción de permitir que autores de llamada sin autenticar puedan iniciar una reunión.</li>
<li>Decida si algunos organizadores de reuniones necesitan que se controlen las llamadas desde la conferencia.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Siguientes pasos</td>
<td align="left"><ul><li>Documente la configuración de puentes de conferencia con todos los detalles (notificaciones de entrada y salida, longitud de PIN, notificación por correo electrónico de cambios en la configuración).</li>
<li>Documente qué números de teléfono para puentes de conferencia se asignan a cada organizador de reunión y la configuración correspondiente para controlar la directiva de autores de llamada sin autenticar y los controles de llamadas desde la reunión y gratuitas.</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><strong>Habilitar las notificaciones de entrada y salidas de las reuniones</strong></td>
<td align="left">Habilitado</td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><strong>Tipo de anuncio de entrada/salida</strong></td>
<td align="left">Tonos</td>
</tr>
<tr class="header">
<td align="left"><strong>Pedir a los autores de llamada que graben su nombre antes de unirse a la reunión</strong></td>
<td align="left">Deshabilitado</td>
</tr>
<tr class="header">
<td align="left"><strong>Longitud de PIN</strong></td>
<td align="left">5</td>
</tr>
<tr class="header">
<td align="left"><strong>Enviar correos automáticamente a los usuarios si cambia su configuración de acceso telefónico</strong></td>
<td align="left">Deshabilitado</td>
</tr>
</tbody>
</table>

_Tabla 11 Ejemplo de configuración de puentes de conferencia_


<table>
<thead>
<tr class="header">
<th align="left">Usuario</th>
<th align="left">Oficina</th>
<th align="left">Número de pago predeterminado</th>
<th align="left">Número gratuito predeterminado</th>
<th align="left">Permitir número gratuito</th>
<th align="left">Los autores de llamadas sin autenticar no pasan por la sala de espera</th>
<th align="left">Llamadas desde la conferencia</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
<td align="left">Sí</td>
<td align="left">Habilitado</td>
<td align="left">Internacionales y nacionales</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
<td align="left">No</td>
<td align="left">Deshabilitado</td>
<td align="left">No se permiten</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
<td align="left">No</td>
<td align="left">Deshabilitado</td>
<td align="left">No se permiten</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
<td align="left">Sí</td>
<td align="left">Deshabilitado</td>
<td align="left">Nacionales</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
<td align="left">Sí</td>
<td align="left">Habilitado</td>
<td align="left">Nacionales</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
<td align="left">Sí</td>
<td align="left">Habilitado</td>
<td align="left">Nacionales</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">Por añadir</td>
<td align="left">Sí</td>
<td align="left">Habilitado</td>
<td align="left">No se permiten</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">Por añadir</td>
<td align="left">Sí</td>
<td align="left">Deshabilitado</td>
<td align="left">No se permiten</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">+44 20 7946 0001</td>
<td align="left">Por añadir</td>
<td align="left">Sí</td>
<td align="left">Deshabilitado</td>
<td align="left">No se permiten</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
<td align="left">No</td>
<td align="left">Deshabilitado</td>
<td align="left">Nacionales</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
<td align="left">Sí</td>
<td align="left">Habilitado</td>
<td align="left">Internacionales y nacionales</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Por añadir</td>
<td align="left">Por añadir</td>
<td align="left">No</td>
<td align="left">Deshabilitado</td>
<td align="left">Nacionales</td>
</tr>
</tbody>
</table>

_Tabla 12 Ejemplo de asignaciones en la configuración de puentes de conferencia_


## <a name="dial-plans"></a>Planes de marcado

Un [plan de marcado](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), una característica de Sistema telefónico de Office 365, es un conjunto de reglas de normalización con las que los números de teléfono que se marcan se traducen en un formato alternativo (normalmente, el formato [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) para poder autorizar la llamada y enrutarla. El servicio de Audioconferencia utiliza las mismas funcionalidades de Sistema telefónico para traducir los números de teléfono marcados en escenarios de llamadas desde la conferencia.

Con un plan de marcado, los usuarios pueden marcar números de teléfono como suelen hacerlo, como, por ejemplo, omitiendo el código de área para las llamadas locales, omitiendo el código de país para las llamadas domésticas o incluso usando una marcación de dígitos breve cuando se realizan llamadas desde la conferencia.

Dentro de la característica de Sistema telefónico de Office 365, existen dos tipos de planes de marcado:

-   **Plan de marcado de servicio**. Es el plan de marcado predeterminado y se aplica a los usuarios en función de la ubicación de uso de Office 365. No se puede modificar.

<!-- -->

-   **Plan de marcado de inquilino**. Este plan de marcado se puede personalizar dentro de un inquilino y se puede volver a dividir en dos tipos:

    -   **Plan de marcado de inquilino global:** el plan de marcado se aplica a todos los usuarios dentro del inquilino.

    -   **Plan de marcado de usuario de inquilino:** el plan se aplica únicamente a determinados usuarios.


> [!NOTE]
> Revise la documentación sobre [planes de marcado del plan de llamadas de Office 365](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) si desea ver más detalles y ejemplos.

El plan de marcado efectivo que se asigna a los usuarios es la combinación del plan de marcado de servicio (basado en la ubicación de uso de Office 365 del usuario) y el plan de marcado de inquilino (ya sea el de inquilino global o el de usuario de inquilino).

![La tabla muestra tres combinaciones de planes de marcado de inquilino y servicio.](media/audio_conferencing_image8.png)

Hay un máximo de 25 reglas de normalización en cada plan de marcado de inquilino y, por lo tanto, hay que evitar duplicar las reglas de normalización que ya están disponibles como parte del plan de marcado de servicio.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Puntos de decisión</td>
<td align="left"><ul><li>Decida si su organización necesita planes de marcado personalizados (requisitos empresariales, requisitos de adopción, etc.).</li>
<li>En caso de necesitarlos, decida qué ámbito del plan de marcado de inquilino (inquilino global o usuario de inquilino) se ajusta a los requisitos de los planes de marcado personalizados.</li>
<li>En caso necesario, decida los planes de macado de inquilino que se van a crear como soporte a las oficinas o ubicaciones de los usuarios en las que se va a implementar Audioconferencia.</li>
<li>En caso necesario, decida qué usuario necesita un plan de marcado personalizado y qué plan de marcado de inquilino se va a asignar a cada usuario.</li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Siguientes pasos</td>
<td align="left"><ul><li>Documente qué planes de marcado personalizados y reglas de normalización asociadas se van a configurar como parte de la implementación de Audioconferencia.</li>
<li>Documente a qué usuarios se les va a asignar un plan de marcado personalizado y qué plan de marcado de inquilino se va a asignar a cada usuario.</li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left">Nombre/descripción del plan de marcado de inquilino</th>
<th align="left">Nombre/descripción de reglas de normalización</th>
<th align="left">Patrón</th>
<th align="left">Traducción</th>
<th align="left">IsInternalExtension</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AU-NSW-NorthRyde-OER</strong></p>
<p><em>Plan de marcado de One Epping Road North Ryde, NSW, AU</em></p></td>
<td align="left"><p><strong>AU-NSW-NorthRyde-OER-Internal</strong></p>
<p><em>Número interno (x7000 - x7999) para oficina de One Epping Road, North Ryde, NSW, Australia</em></p></td>
<td align="left">^(7\d{3})$</td>
<td align="left">+6125550$1</td>
<td align="left">True</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>AU-NSW-Local</strong></p>
<p><em>Normalización de número local para NSW, Australia</em></p></td>
<td align="left">^([2-9]\d{7})$</td>
<td align="left">+612$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>AU-TollFree</strong></p>
<p><em>Normalización de número gratuito para Australia</em></p></td>
<td align="left">^(1[38]\d{4,8})\d*$</td>
<td align="left">+61$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>AU-Service</strong></p>
<p><em>Normalización de número de servicio para Australia</em></p></td>
<td align="left">^(000|1[0125]\d{1,8})$</td>
<td align="left">1 $</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SG-Singapore-OMB</strong></p>
<p><em>Plan de marcado de OMB Singapore, SG</em></p></td>
<td align="left"><p><strong>SG-OMB-Internal</strong></p>
<p><em>Número interno (x8000 – x8999) para la oficina de +OMB, Singapur</em></p></td>
<td align="left">^(8\d{3})$</td>
<td align="left">+656888$1</td>
<td align="left">True</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>SG-TollFree</strong></p>
<p><em>Normalización de número gratuito para Singapur</em></p></td>
<td align="left">^(1?800\d{7})\d*$</td>
<td align="left">+65$1</td>
<td align="left">False</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>SG-Service</strong></p>
<p><em>Normalización de número de servicio para Singapur</em></p></td>
<td align="left">^(1\d{3,4}|9\d{2})$</td>
<td align="left">1 $</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"><p><strong>FR-Paris-Issy-39qdPR</strong></p>
<p><em>Plan de marcado de 39 quai du Président Roosevelt Issy-les-Moulineaux, Francia</em></p></td>
<td align="left"><p><strong>FR-39qdPR-Internal</strong></p>
<p><em>Número interno (x7000 – x7999) para 39 quai du Président Roosevelt office, Issy-les-Moulineaux, Francia</em></p></td>
<td align="left">^(7\d{3})$</td>
<td align="left">+3319999$1</td>
<td align="left">True</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><strong>FR-TollFree</strong></p>
<p><em>Normalización de número gratuito para Francia</em></p></td>
<td align="left">^0?(80\d{7})\d*$</td>
<td align="left">+33$1</td>
<td align="left">False</td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><strong>FR-Service</strong></p>
<p><em>Normalización de número de servicio para Francia</em></p></td>
<td align="left"><p>^(1\d{1,2}|11[68]\d{3}|</p>
<p>10\d{2}|3\d{3})$</p></td>
<td align="left">1 $</td>
<td align="left">False</td>
</tr>
</tbody>
</table>

_Tabla 13 Ejemplo de planes de marcado de inquilino_


<table>
<thead>
<tr class="header">
<th align="left">Usuario</th>
<th align="left">Oficina</th>
<th align="left">Tipo de plan de marcado</th>
<th align="left">Nombre de plan de marcado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Adele Vance</td>
<td align="left">One Epping Road</td>
<td align="left">Plan de marcado de inquilino</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="even">
<td align="left">Alex Wilber</td>
<td align="left">One Epping Road</td>
<td align="left">Plan de marcado de inquilino</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="odd">
<td align="left">Ben Walters</td>
<td align="left">One Epping Road</td>
<td align="left">Plan de marcado de inquilino</td>
<td align="left">AU-NSW-NorthRyde-OER</td>
</tr>
<tr class="even">
<td align="left">Christie Cline</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Plan de marcado de inquilino</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="odd">
<td align="left">Debra Berger</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Plan de marcado de inquilino</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="even">
<td align="left">Lee Gu</td>
<td align="left">One Marina Boulevard</td>
<td align="left">Plan de marcado de inquilino</td>
<td align="left">SG-Singapore-OMB</td>
</tr>
<tr class="odd">
<td align="left">Emily Braun</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Plan de marcado de servicio</td>
<td align="left">N/D</td>
</tr>
<tr class="even">
<td align="left">Lidia Holloway</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Plan de marcado de servicio</td>
<td align="left">N/D</td>
</tr>
<tr class="odd">
<td align="left">Pradeep Gupta</td>
<td align="left">32 London Bridge Street</td>
<td align="left">Plan de marcado de servicio</td>
<td align="left">N/D</td>
</tr>
<tr class="even">
<td align="left">Marcel Beauchamp</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Plan de marcado de inquilino</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
<tr class="odd">
<td align="left">Rachelle Cormier</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Plan de marcado de inquilino</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
<tr class="even">
<td align="left">Isabell Potvin</td>
<td align="left">39 quai du Président Roosevelt</td>
<td align="left">Plan de marcado de inquilino</td>
<td align="left">FR-Paris-Issy-39qdPR</td>
</tr>
</tbody>
</table>

_Tabla 14 Ejemplo de asignaciones de plan de marcado_


## <a name="microsoft-teams-configurations"></a>Configuraciones de Microsoft Teams

Como Audioconferencia solo está disponible para reuniones programadas, hay que habilitar las configuraciones a nivel de inquilino que rigen la programación de las reuniones (reuniones privadas y de canal).


> [!NOTE]
> Por el momento, si su organización tiene ciertas normativas por las que se tienen que poder detectar todas las discusiones de las reuniones, debe deshabilitar las reuniones privadas si el organizador tiene un buzón de correo local de Exchange.<br><br>
> En otros casos, si todas las reuniones de la organización solo pueden estar visibles <strong>para las partes invitadas</strong> y así evitar que se revele la información de reuniones a partes que no están invitadas, le recomendamos que deshabilite la capacidad de programar reuniones en <strong>canales</strong>.

Las configuraciones, disponibles como configuraciones a nivel de inquilino, se aplican a todos los usuarios de la organización y repercutirán en la programación de todas las reuniones de Microsoft Teams, no solo en las reuniones de Microsoft Teams **con** Audioconferencia.

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left">Punto de decisión</td>
<td align="left"><p>Decida si la organización tiene que habilitar o deshabilitar la programación de reuniones privadas.</p>
<p>Decida si la organización tiene que habilitar o deshabilitar la programación de reuniones de canal.</p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left">Siguientes pasos</td>
<td align="left"><p>Documente las configuraciones para la programación de reuniones de Microsoft Teams.</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><strong>Permitir la programación de reuniones privadas</strong></td>
<td align="left">Habilitado</td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><strong>Permitir la programación de reuniones de canal</strong></td>
<td align="left">Deshabilitado</td>
</tr>
</tbody>
</table>

_Tabla 15 Ejemplo de configuraciones de reuniones de Microsoft Teams_


## <a name="document-technical-implementation-plan"></a>Documentar el plan técnico de implementación

Utilice los puntos de decisión anteriores como referencia para documentar el plan de implementación técnico.

Este plan de implementación técnico proporcionará al equipo del proyecto (que puede incluir FastTrack o el asociado de implementación) la información que le permita ejecutar la incorporación de técnicos para la implementación de Audioconferencia.

En general, un plan de implementación técnico contendrá las siguientes secciones principales:

-   Lista de habilitación del sitio de servicio de Audioconferencia

-   Lista de asignación de licencias para los organizadores de reuniones de Audioconferencia

-   Números de planificación de Créditos de comunicaciones

-   Detalles de puentes de conferencia

-   Configuración de puentes de conferencia

-   Asignaciones de configuraciones de puentes de conferencia

-   Planes de marcado de inquilino

-   Asignaciones de planes de marcado

-   Configuraciones de reuniones de Microsoft Teams

Una vez que complete el plan de éxito y el plan de implementación técnico, podrá seguir con el recorrido de cliente de Office 365.

<a name="onboard"></a>Incorporación
=======

*Próximamente*

<a name="drive-value"></a>Nuevos valores
===========

*Próximamente*



### <a name="see-also"></a>Vea también
[Configurar conferencias de acceso telefónico local o RTC para Skype Empresarial](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)

---
title: "Guía práctica para implementar Audioconferencia en Microsoft Teams."
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/22/2017
ms.topic: article
ms.service: msteams
description: "Guía práctica para planificar, implementar y administrar Sistema telefónico con Planes de llamada en Microsoft Teams mediante el marco Enfoque (planificar), Incorporación (entregar), Nuevos valores (operar)."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 69162c3795bfab8ddc95eba0ce91a790b20f6332
ms.sourcegitcommit: 495ee65ffc85d223c965c8b31f0350c7e844ab96
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a>Guía práctica para implementar Audioconferencia en Microsoft Teams.
============================================================

Audioconferencia en Office 365 permite a los participantes unirse a las reuniones desde cualquier teléfono.

Esto es lo que conseguirá con [Audioconferencia](https://go.microsoft.com/fwlink/?linkid=858992) en Office 365.

En esta guía práctica se detallan el recorrido que sigue el cliente con FastTrack para Office 365 y las tres fases que lo conforman (Enfoque, Incorporación y Nuevos valores) para ayudarle a planificar, entregar y utilizar una implementación correcta de Audioconferencia.

> [!TIP]
> En esta guía práctica ofreceremos ejemplos de respuestas para todas las actividades y discusiones clave. Los ejemplos de este documento se muestran dentro de recuadros de CONSEJO y se pueden utilizar como plantillas. La frase "Por añadir" indica que falta por completar con información como parte del proceso de planificación.

Enfoque <a name="Envision_AudioConferencing"> </a>
=========

En la fase de Enfoque, se define el recorrido que tendrá que hacer el cliente de Office 365 y se aplicará a todo tipo de cargas de trabajo, como la de Audioconferencia.

En esta fase se definen los objetivos empresariales, con la participación de todas las partes interesadas del proyecto, para, por último, presentar:

-   Un plan de éxito de gran nivel que contenga casos de uso empresariales, las principales partes interesadas, los objetivos y resultados principales, los indicadores de éxito principales, los riesgos, la evaluación del entorno, la preparación para la adopción y el plan operativo.

-  Un plan detallado de implementación técnica de Audioconferencia para conseguir el estado final deseado.

<a name="define-business-use-cases-for-audio-conferencing"></a>Definir casos de uso empresariales para Audioconferencia
------------------------------------------------

Audioconferencia proporciona a las organizaciones unos puntos de entrada adicionales a reuniones (ad hoc y programadas). Para ello, los participantes se unen a través de RTC (red telefónica conmutada), llamando con teléfonos móviles, PBX o fijos tradicionales.

Resulta muy útil cuando el organizador o los participantes no tienen delante un ordenador o cuando no hay conexiones de datos o estas no soportan las comunicaciones por voz; por ejemplo, cuando el participante se encuentra en un área remota con una cobertura de datos móviles muy irregular o si se conecta a un servicio de red Wi-Fi público y gratuito con ancho de banda limitado, o bien cuando los participantes de la reunión prefieren acceder a ella por teléfono mediante puntos de conexión de telefonía de fácil acceso.

En este paso, los principales participantes del proyecto definirán casos de uso de empresas que admitan la implementación de Audioconferencia.

Los casos de uso de empresa se aportan con la intención de definir y documentar los resultados que se esperan y que se pueden medir. Incluyen lo siguiente:

-   Descripción del proceso de negocio actual
-   Retos que se deben conseguir con el proceso de negocio actual definido.
-   De qué manera la tecnología puede ayudar a alcanzar estos retos.
-   Los resultados empresariales que se esperan y que se pueden medir si se superan los retos.

> [!TIP]
> A continuación se muestra un ejemplo de caso de uso de negocio completado:
>|         |
>|---------|
>|**Descripción del proceso de negocio actual**<br>Contoso utiliza en estos momentos los servicios de Conferencia RTC que ofrece el proveedor de telefonía local que le corresponde y que se cobran por minutos de reunión en reuniones internas y reuniones en las que participan usuarios externos.|
>|**Retos que se deben conseguir con el proceso de negocio actual definido**<br>A Contoso, el servicio de Conferencia RTC actual le supone aproximadamente 1 millón de USD al año, de donde el 75 % del coste incurrido es para reuniones internas.<br>El uso de los puntos de conexión de telefonía tradicional para unirse a las reuniones que aloja el servicio de Conferencia RTC no está en línea con el plan que está desarrollando la empresa para adoptar Microsoft Teams como plataforma de colaboración y comunicaciones moderna.|
>|**De qué manera la tecnología puede ayudar a alcanzar estos retos**<br>Al adoptar Microsoft Teams como plataforma de colaboración y comunicaciones moderna, los usuarios internos podrán fundamentalmente unirse a las reuniones con sus PC, equipados con auriculares y dispositivos de salas de reuniones adecuados. Audioconferencia estará disponible para los usuarios externos o para situaciones en las que a los participantes internos no les vaya bien el audio del PC.|
>|**Propósitos y medición de los resultados de negocio**<br>El cambio a Microsoft Teams como plataforma de colaboración y comunicaciones moderna, junto con el servicio de Audioconferencia, reducirá enormemente el coste que tiene el servicio de Conferencia RTC de tal manera que se espera que Contoso solo gaste aproximadamente un 20 % del coste que dedica cada año al servicio de Conferencia RTC actual.|

Además de definir los casos de uso de su empresa, al avanzar al paso siguiente de la fase de Enfoque, deberá aclarar los temas siguientes:
- ámbito organizativo y
- escalas de tiempo del proyecto

<a name="identify-key-stakeholders"></a>Identificar las partes interesadas clave
-------------------------

Los casos de uso de negocio que se definieron en el paso anterior incluirán el ámbito organizativo de la implementación de Audioconferencia y, en función de eso, se completará la matriz de participantes con la adición de las personas que tienen que estar involucradas en el proyecto.

> [!TIP]
> A continuación se muestra un ejemplo de plantilla de matriz de participantes que puede usar para documentar los participantes del proyecto:
>|Rol  |Descripción  |Nombre, información de contacto, ubicación  |
>|---------|---------|---------|
>|Patrocinador ejecutivo de proyecto|<ul><li>La autoridad y responsable últimos del proyecto y de la consecución de los objetivos del proyecto.</li><li>Ayuda a resolver problemas que haya remitido el responsable de proyecto.</li><li>Promueve la comunicación sobre los objetivos del proyecto dentro de la empresa.</li><li>Responsable de tomar decisiones clave de estrategia.</li><li>Responsable de garantizar la disponibilidad de los recursos y el presupuesto necesarios.</li><li>Encargado de realizar revisiones empresariales trimestrales (QBR).</li><li>Obtiene el consenso y el respaldo del esfuerzo de la campaña de sensibilización.</li><li>Debe actuar como patrocinador de proyecto para el lanzamiento del programa.</li></ul>|Por añadir|
>|Responsable de proyecto|<ul><li>Administración y liderazgo en el equipo de proyecto.</li><li>Se coordina con los socios y los equipos de trabajo que están involucrados en el proyecto.</li><li>Responsable de crear y administrar planes de proyecto para alcanzar los principales resultados para el trimestre.</li><li>Se encarga de solucionar problemas procedentes de diversas funciones.</li><li>Mantiene informado de forma regular a los patrocinadores del proyecto.</li><li>Se ocupa de la incorporación de aspectos de adopción en el plan de proyecto general.</li><li>Se encarga de realizar revisiones operativas y empresariales mensuales (MBR), como contribución a las revisiones empresariales trimestrales.</li></ul>|Por añadir|
>|Arquitecto/responsable de colaboración|<ul><li>Responsable de que los ejecutivos de la empresa lleven a cabo la estrategia de colaboración.</li><li>Debe analizar y elegir los productos de colaboración para que la empresa cumpla los objetivos de negocio.</li><li>Es responsable de diseñar las operaciones para los productos de colaboración.</li><li>Define el modelo de operación y soporte.</li><li>Debe contribuir a las revisiones empresariales mensuales y trimestrales.</li><ul>|Por añadir|
>|Consultor|<ul><li>Es responsable de los servicios de configuración.</li><li>Contribuye a la arquitectura general de soluciones.</li></ul>|Por añadir|
>|Jefe de proyecto|<ul><li>Se encarga de desarrollar y mantener el plan de proyecto.</li><li>Se encarga de que las entregas de proyecto se realicen en línea con el plan y el presupuesto del proyecto.</li><li>Registra y administra los problemas que surgen en el proyecto, incluidas las remisiones a escalas superiores.</li><li>Lleva a cabo llamadas de control semanales.</li><li>Es el encargado de relacionarse y mantener informados a los patrocinadores ejecutivos del proyecto.</li><li>Trabaja con el arquitecto para definir el enfoque de administración de cambios y los planes de comunicación.</li></ul>|Por añadir|
>|Especialista en adopción/administración de cambios|<ul><li>Aporta su punto de vista en la fase de descubrimiento sobre los procesos de adopción y formación.</li><li>Participa en los talleres de estrategia de adopción.</li><li>Se encarga de desarrollar la estrategia de adopción y es responsable de ella.</li><li>Se encarga de desarrollar y llevar a cabo el plan de comunicación.</li><li>Es responsable de proporcionar formación a los usuarios finales.</li><li>Recopila comentarios y realiza encuestas.</li></ul>|Por añadir|
>|Responsable de redes|<ul><li>Aporta su punto de vista en la fase de descubrimiento sobre el diseño de redes.</li><li>Participa en la planificación durante el taller de Enfoque.</li><li>Coordina el trabajo del equipo de redes durante la ejecución del proyecto.</li></ul>|Por añadir|
>|Responsable de seguridad|<ul><li>Aporta su punto de vista en la fase de descubrimiento sobre los procesos y el diseño de la seguridad.</li><li>Participa en la planificación durante el taller de Enfoque.</li><li>Coordina el trabajo del equipo de seguridad durante la ejecución del proyecto.</li></ul>|Por añadir|
>|Responsable de telefonía|<ul><li>Aporta su punto de vista en la fase de descubrimiento sobre el diseño de la telefonía.</li><li>Participa en la planificación durante el taller de enfoque.</li><li>Coordina el trabajo del equipo de telefonía durante la ejecución del proyecto.</li></ul>|Por añadir|
>|Responsable de escritorio|<ul><li>Aporta su punto de vista en la fase de descubrimiento sobre los clientes y el proceso de actualización.</li><li>Participa en la planificación durante el taller de enfoque.</li><li>Coordina el trabajo del equipo de escritorio durante la ejecución del proyecto.</li></ul>|Por añadir|
>|Responsable del servicio de asistencia y soporte técnico|<ul><li>Aporta su punto de vista en la fase de descubrimiento sobre el modelo operativo y de soporte.</li><li>Participa en la planificación durante el taller de enfoque.</li><li>Participa en la planificación del modelo de soporte.</li><li>Coordina el trabajo de los recursos y los equipos de soporte técnico durante la ejecución del proyecto.</li></ul>|Por añadir|
>|Representantes de la unidad de negocio|<ul><li>Contribuyen en la creación de los materiales y guías de adopción basados en el usuario final.</li><li>Contribuyen en la creación de casos de uso de negocio y los revisan.</li></ul>|Por añadir|
>|Responsable de implementación|<ul><li>Garantiza que se cumplan los requisitos previos de implementación.</li><li>Involucra a los recursos del cliente para que se impliquen en la preparación y la implementación de las actividades de las primeras fases.</li><li>Participa en reuniones para revisar, preparar e implementar el estado.</li></ul>|Por añadir|
>|Administradores de TI|<ul><li>Los profesionales de TI se encargan de ayudar en la planificación y ejecución de pruebas.</li></ul>|Por añadir|
>|Propietario del servicio|<ul><li>Es responsable de que el servicio de Audioconferencia funcione de forma continua.</li><li>Propietario del servicio de Audioconferencia.</li></ul>|Por añadir|
>|Expertos en calidad|<ul><li>Genera calidad, fiabilidad y recopila opiniones de los usuarios.</li><li>Identifica las tendencias en la calidad y propicia la corrección de los problemas con los equipos correspondientes.</li><li>Mantiene informada a la directiva a través del comité directivo.</li><li>Informa sobre la calidad, la fiabilidad y las opiniones de los usuarios a través de Valorar mi llamada y Net Promoter Score.</li></ul>|Por añadir|

<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Definir objetivos y resultados principales, indicadores de éxito principales y riesgos
--------------------------------------------------------------------

Con la participación de todas las partes involucradas en el proyecto, los casos de uso, el ámbito organizativo y las escalas de tiempo del proyecto se pueden traducir en objetivos y resultados principales (OKR, del inglés "objectives and key results"), y las medidas de éxito del proyecto se pueden definir en una lista de indicadores de éxito principales (KSI, del inglés "key success indicators").

Al contar con la plena participación de todos las partes involucradas en el proyecto a la hora de definir los OKR y los KSI, se garantiza el sentido de propiedad y su adecuación a los requisitos organizativos del negocio.

Los OKR contendrán una lista de los objetivos que se establecieron al inicio del proyecto, con los principales resultados que se pueden medir y que se definen trimestralmente. Los principales resultados se revisan mensualmente para hacer un seguimiento del estado del proyecto general y, en función de cómo avancen, se podrán ir ajustando los planes trimestrales.

> [!TIP]
> A continuación puede consultar un ejemplo de OKR relevante para la implementación de Audioconferencia:
><br>
>
>**Visión: aumentar la productividad maximizando las inversiones de Office 365**
>|Objetivos  |Resultados principales  |Acciones que realizar  |
>|---------|---------|---------|
>|Implementar Audioconferencia en Microsoft Teams al final del año fiscal 2018|T1 2018: implementar Audioconferencia en Microsoft Teams globalmente|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
>|Retirar globalmente el servicio de Conferencia RTC antiguo a mediados del año fiscal 2018|T2 2018: retirar globalmente el servicio de Conferencia RTC antiguo|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|

Los KSI miden la calidad y el éxito de los resultados principales, y complementan la naturaleza binaria de los OKR (conseguidos o no conseguidos) al detallar los buenos o los malos resultados. Para definir los KSI, recomendamos aplicar criterios SMART o criterios "específicos, medibles, atribuibles, realistas y temporales".

> [!TIP]
> A continuación se muestra un ejemplo de KSI relevantes para este proyecto:
>|Tipo  |Cuestiones y criterios sobre el KSI  |Cómo se miden  |Criterios de éxito  |Medidos  |Responsable  |
>|---------|---------|---------|---------|---------|---------|
>|Uso/adopción|La calidad de las llamadas es igual o mejor que en la solución anterior|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de tecnología de la información|
>|Uso/adopción|El proceso de comunicación fue más sencillo gracias a Microsoft Teams|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de administración de cambios|
>|Uso/adopción|Los usuarios utilizan la solución activamente|Informes de Office 365, panel de calidad de llamadas|El 80 % de los usuarios son usuarios activos diarios|A diario|Equipo de administración de cambios|
>|Uso/calidad|El porcentaje de llamadas/conferencias de mala calidad debe ser mínimo|Panel de calidad de llamadas|Menos del 5 % de llamadas de mala calidad al mes|A diario|Equipo de tecnología de la información|
>|Uso/soporte|Sé cómo conseguir soporte técnico|Encuesta|El 90% de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de administración de cambios|
>|Uso/soporte|Estoy satisfecho con la calidad del soporte técnico|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras cada incidente|Equipo de tecnología de la información|
>|Financiero|Reducción de los minutos de conferencias antiguas|Sistema financiero|Cumplir el ROI definido|Basado en ROI|Equipo de administración de cambios|

Como parte de este ejercicio, hay que identificar los riesgos del negocio y definir un plan de mitigación para cada uno de los riesgos que se identifiquen. Esta información se puede plasmar en un plan de riesgos.

> [!TIP]
> El plan de riesgos puede documentarse del modo que se muestra en el siguiente ejemplo:
>|Riesgo  |Probabilidad  |Impacto  |General  |Plan de mitigación  |
>|---------|---------|---------|---------|---------|
>|Con la próxima fusión se sumarán hasta 1000 personas|Alta|Alta|Alta|<ul><li>Para las empresas fusionadas, OKR independiente con proceso propio (Enfoque, Incorporación, Nuevos valores).</li><li>No se deben incluir en los OKR existentes.</li></ul>|
>|La portabilidad de los números de teléfono retrasará la finalización del proyecto.|Alta|Alta|Alta|<ul><li>Se debe preparar con antelación toda la información para la portabilidad de los números de teléfono (registro de servicios al cliente, detalles de facturación, carta de autorización).</li><li>La escala de tiempo del proyecto se debe ajustar para incluir el tiempo que se tarda en realizar la portabilidad de los números de teléfono.</li><li>Se debe comunicar el uso de los nuevos números de conferencia de acceso telefónico local a los participantes externos.</li></ul>|
>|Se ha planificado rediseñar las redes|Alta|Mediana|Mediana|<ul><li>Antes de implementar Microsoft Teams como plataforma de colaboración y comunicaciones moderna, evalúe la preparación de la red en los sitios que se incluyen en el ámbito del proyecto.</li></ul>|

<a name="assess-environment-and-evaluate-adoption-readiness"></a>Evaluar el entorno y la preparación que se tiene para la adopción
--------------------------------------------------

Para conseguir los OKR que se pretenden, es posible que tenga que definir una arquitectura de alto nivel de la solución. De este modo, se evalúan todos los aspectos relacionados con la infraestructura de TI y telefonía, las redes y las operaciones a través del descubrimiento del entorno.

Todas las cuestiones relacionadas con la informática para usuarios finales, como la evaluación de la preparación de los ordenadores personales y los dispositivos móviles para admitir casos de uso de empresas para Audioconferencia, se incluirán como parte del proceso de descubrimiento del entorno.

Con el descubrimiento del entorno también se puede poner de manifiesto si hay algún requisito para [transferir números de teléfono a Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365). De este modo, la organización podrá ajustar el plan de proyecto y preparar toda la información que necesite para la portabilidad de los números. El descubrimiento del entorno se puede llevar a cabo mediante el siguiente [cuestionario](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_3).

En el descubrimiento del entorno se debe incluir la evaluación de preparación de la red para asegurarse de que esta pueda soportar la implementación del servicio de Audioconferencia.

También se puede determinar si la red está preparada para soportar el servicio de Audioconferencia evaluando la información que se recopila en el descubrimiento del entorno (como los detalles de la conectividad a Internet y la topología de WAN, los vínculos a sitios y el ancho de banda disponible) y los datos de los análisis de personas (que se pueden traducir en el uso que se espera de cada carga de trabajo) en la [herramienta de planificación de red de My Advisor](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). Para confirmar en mayor medida el estado de la red, se puede realizar una simulación del tráfico multimedia en tiempo real con soluciones que proporcione [Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) o los [socios de las herramientas para la evaluación de la preparación de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Partners?ToolPartners).

Con los resultados de esta evaluación se podrá tener una idea más clara de la corrección o la optimización que se necesita hacer en la red para que la implementación de Audioconferencia se pueda desarrollar correctamente.

Para evaluar la preparación para la adopción se puede ejecutar un análisis de personas que genere una lista de las personas de la organización en las que se podrá llevar a cabo la implementación del servicio de Audioconferencia. El análisis de personas incluye la identificación de otros periféricos y dispositivos que se necesitan para obtener los resultados de negocio que se desean.

Para realizar el análisis de personas, puede realizar un taller en el que se involucre a todas las partes relevantes del proyecto mediante la plataforma de talleres [Persona Alignment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_7) y [Persona Feature Matrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_8). El resultado de este taller de análisis de personas se puede resumir en un informe que se elabora con la plantilla [Persona Analysis Report](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_9).

> [!NOTE]
> Si bien el cuestionario de descubrimiento y los ejemplos de análisis de personas se crearon en un principio para Skype Empresarial Online, la mayoría del contenido es válido para Microsoft Teams. Modifique y quite los elementos que crea que no son relevantes de los objetivos del proyecto.

Los riesgos técnicos se pueden identificar como parte de una evaluación del entorno y la evaluación de la preparación para la adopción, y se puede desarrollar un plan de mitigación para cada uno de los riesgos que se identifiquen. Esta información se debe incorporar en el plan de riesgos.

<a name="map-operational-roles"></a>Asignar roles operativos
---------------------

Planificar las operaciones e identificar a los equipos que utilizarán el servicio de Audioconferencia es un paso muy importante, ya que las operaciones deben comenzar cuando se habiliten los primeros usuarios del piloto. Cada uno de los equipos que se identifiquen debe revisar y aceptar las tareas y las responsabilidades que se identifiquen y deben comenzar la preparación para utilizar el servicio de Audioconferencia. En la fase de preparación se podría incluir formación y capacitación, contratación de más personal o garantizar que los proveedores externos están listos para ofrecer el servicio.

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla para documentar el resultado del ejercicio de asignación de roles operativos que ha realizado como parte del proyecto:
>|Rol operativo  |Descripción  |Equipo  |Datos de contacto  |
>|---------|---------|---------|---------|
>|Propietario del servicio|Propietario del servicio, interactuar con las divisiones de la empresa, estrategia|Por añadir|Por añadir|
>|Operaciones de Audioconferencia|Operaciones diarias, transferencia/adición/cambio de cuenta de dispositivo y usuario, supervisión|Por añadir|Por añadir|
>|Administrador de inquilinos|Cambiar la configuración de todos los inquilinos, habilitar nuevas características|Por añadir|Por añadir|
>|Servicio de asistencia|Interactuar con usuarios finales que necesitan soporte|Por añadir|Por añadir|
>|Operaciones de red|Cubre LAN, WAN, Wi-Fi y acceso a Internet|Por añadir|Por añadir|
>|Equipo de cliente y puntos de conexión|Administrar implementaciones de escritorio|Por añadir|Por añadir|
>|Operaciones de identidad|Administrar infraestructura de identidad (AD, ADFS, Azure AD)|Por añadir|Por añadir|
>|Adopción/administración de cambios|Administrar el reconocimiento, la formación y la adopción de la solución|Por añadir|Por añadir|
>|Operaciones de Exchange|Administra el entorno de Exchange|Por añadir|Por añadir|

Para que la asignación de roles operativos se pueda llevar a cabo de una forma más detallada, incluidas las tareas asociadas a cada rol operativo, el [libro de trabajo para la asignación de roles operativos](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_16) puede ser muy útil para capturar los detalles que determinarán con claridad cuáles son los roles y las responsabilidades que respaldarán el servicio de Audioconferencia.

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

<br>
Planificación técnica de Audioconferencia
-----------------------------------------

Para planificar la implementación técnica de Audioconferencia en Microsoft Teams, hay que tomar una serie de decisiones con antelación para preparar mejor a la organización para la implementación de una solución que cumpla los requisitos del negocio. Estas decisiones se documentarán en un plan de implementación técnico.

## <a name="availability-of-audio-conferencing"></a>Disponibilidad de Audioconferencia

Audioconferencia está disponible en estos [países y regiones](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

> [!IMPORTANT]
> Por imperativo de carácter jurídico, para que Audioconferencia pueda estar disponible en organizaciones multinacionales, el contrato de suscripciones de Office 365 debe provenir de países y regiones que estén cubiertos por el servicio de Audioconferencia o en los que el servicio de Audioconferencia esté disponible comercialmente.

Tras confirmar que su organización reúne los requisitos para poder usar el servicio de Audioconferencia, recopile la lista de ubicaciones de usuario u oficinas en las que se implementará el servicio de Audioconferencia según la lista de países y regiones disponibles.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida qué oficinas o ubicaciones de usuario se implementarán el servicio de Audioconferencia.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Decida qué oficinas o ubicaciones de usuario se habilitarán para el servicio de Audioconferencia.</li></ul>|

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla de la lista de habilitación del sitio de Sistema telefónico con Planes de llamada:
>|Oficina   |Ubicación |Servicio de conferencia RTC  |
>|---------|---------|---------|
>|One Epping Road|Australia|Audioconferencia|
>|100 Cyberport Road|RAE de Hong Kong|Conferencia RTC antigua|
>|One Marina Boulevard|Singapur|Audioconferencia|
>|32 London Bridge Street|Reino Unido|Audioconferencia|
>|39 quai du Président Roosevelt|Francia|Audioconferencia|

## <a name="licensing-for-audio-conferencing"></a>Licencias para Audioconferencia

La [licencia de Audioconferencia](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) está disponible como parte de los planes de suscripción de Office 365 E5, o como complemento para los planes de suscripción de Office 365 E1 y E3.

> [!NOTE]
> Las conferencias de acceso telefónico local o RTC no admiten los proveedores de servicios de audioconferencia de terceros (ACP).<sup></sup> <br>Si está usando la Conferencia RTC para Skype Empresarial Online, puede beneficiarse al instante de Audioconferencia en Microsoft Teams.

Para proporcionar números de teléfono gratuitos para puentes de conferencia y admitir las conferencias por aceptación de llamada de números de teléfono internacionales, tendrá que configurar [Créditos de comunicaciones](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) para su organización.

> [!IMPORTANT]
> En algunos países solo se pueden usar números de teléfono gratuitos para puentes de conferencia y, en tal caso, hay que usar obligatoriamente Créditos de comunicaciones para poder admitir el acceso telefónico local para esos países.

La primera consideración que hay que tener en cuenta a la hora de implementar Créditos de comunicaciones es decidir la cantidad inicial de fondos que se deben adquirir. La cantidad de fondos que se recomienda se puede consultar en el artículo [Créditos de comunicaciones](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

En el artículo [Créditos de comunicaciones](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) también se incluye una recomendación para el umbral (la cantidad más baja de fondos), lo que le interesará especialmente si su organización decide utilizar la recarga automática. El importe de recarga automática se determina por el uso real. Con el paso del tiempo es recomendable supervisar el uso de Créditos de comunicaciones y ajustar la cantidad de recarga según sea necesario.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Si su organización aún no ha adquirido las licencias de Audioconferencia que necesita, decida si estas se van a adquirir incrementando las suscripciones existentes de Office 365 o comprando complementos de Audioconferencia.</li><li>Decida si los Créditos de comunicaciones son necesarios para la implementación de Audioconferencia. En tal caso, decida la cantidad inicial de fondos que se va a comprar. Cuando sea necesario, decida la cantidad para el umbral y la cantidad de autorecarga.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Documente los usuarios a los que se les asignará la licencia de Audioconferencia.</li><li>Documente el plan de Créditos de comunicaciones (cantidad inicial, cantidad de umbral y cantidad de recarga automática).</li></ul>|

> [!TIP]
> Puede documentar la lista de asignación de licencias de los usuarios de Audioconferencia usando el siguiente ejemplo.
>|Usuario  |Oficina  |Licencia de Office 365  |
>|---------|---------|---------|
>|Adele Vance|One Epping Road|Office 365 E5|
>|Alex Wilber|One Epping Road|Office 365 E3, complemento de Audioconferencia|
>|Ben Walters|One Epping Road|Office 365 E3, complemento de Audioconferencia|
>|Christie Cline|One Marina Boulevard|Office 365 E3, complemento de Audioconferencia|
>|Debra Berger|One Marina Boulevard|Office 365 E5|
>|Lee Gu|One Marina Boulevard|Office 365 E5|
>|Emily Braun|32 London Bridge Street|Office 365 E5|
>|Lidia Holloway|32 London Bridge Street|Office 365 E5|
>|Pradeep Gupta|32 London Bridge Street|Office 365 E5|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, complemento de Audioconferencia|
>|Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
>|Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, complemento de Audioconferencia|

<br>
> [!TIP]
> Los números de planificación de Créditos de comunicaciones se pueden documentar del modo siguiente:
>|         |         |
>|---------|---------|
>|Cantidad inicial|1000 $|
>|Cantidad de umbral|400 $|
>|Cantidad de recarga automática|Por añadir|

## <a name="conference-bridge-phone-numbers"></a>Números de teléfono para puentes de conferencia

El servicio de Audioconferencia en Office 365 incluye:

-   Varios tipos de números de teléfono para puentes de conferencia (gratuitos y de pago)
-   Varias categorías del número de teléfono (dedicado y compartido)
-   Soporte para varios idiomas del puente de conferencia (principal y secundario)
-   Un número de teléfono predeterminado para el inquilino.

La descripción completa de las funcionalidades que se incluyen se puede extraer de [Configurar Audioconferencia para Skype Empresarial y Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) y [Números de teléfono para Audioconferencia](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing).

> [!NOTE]
> Los números de teléfono dedicados para puentes de conferencia se tienen en cuenta como parte del límite de números de teléfono que se pueden adquirir por inquilino, según el número de licencias que corresponden, como se describe en [Obtener números de teléfono de servicio de Skype Empresarial y Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers). Los números de teléfono gratuitos para puentes de conferencia necesitan los Créditos de comunicaciones.

Si ya hay números de teléfono para puentes de conferencia que hay que transferir al servicio de Audioconferencia, teniendo en cuenta que cumplen los requisitos para cada país o región, los números de teléfono para puentes de conferencia existentes se pueden transferir a Microsoft.

> [!NOTE]
> La complejidad que entraña la transferencia de los números de teléfono a Microsoft varía enormemente según cuáles sean los países y las regiones, los operadores, el número de circuitos involucrados y muchos otros factores. Para planificar la portabilidad de los números de teléfono, revise la [guía de portabilidad de números](https://go.microsoft.com/fwlink/?linkid=859011).

Encontrará más detalles sobre la transferencia de números de teléfono al servicio de Audioconferencia en [Transferir números de teléfono a Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si la organización necesita números de teléfono dedicados para puentes de conferencia.</li><li>Decida cómo se obtendrán los números de teléfono dedicados para puentes de conferencia para las oficinas o ubicaciones de usuario que entran dentro de la implementación de Audioconferencia (obtenerlos de Microsoft o transferir números de teléfono existentes).</li><li>Si elige obtenerlos de Microsoft, decida el método para obtener los números de teléfono (envío de formulario o automatizado) para las oficinas o ubicaciones de usuario que entran dentro de la implementación de Audioconferencia.</li><li>Decida las preferencias de idioma que se deben configurar para cada número de teléfono dedicado para puentes de conferencia.</li><li>Decida el número de teléfono predeterminado para puentes de conferencia del inquilino.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Documente el plan maestro para la adquisición de números de teléfono y especifique cómo se obtendrán los números de teléfono para cada oficina o ubicación de usuario que entra dentro de la implementación de Audioconferencia.</li><li>Si corresponde, complete <a href="https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization">un formulario de solicitud de número de teléfono nuevo</a> por cada oficina o ubicación.</li><li>Si elige transferir números de teléfono existentes, revise la <a href="https://go.microsoft.com/fwlink/?linkid=859011">guía de portabilidad de números</a> para planificar el proceso y ajustar el tiempo de implementación de Audioconferencia de forma acorde.</li><li>Documente las configuraciones de los números de teléfono para puentes de conferencia (números de teléfono compartidos y dedicados para puentes de conferencia, preferencias de idioma para cada número de teléfono dedicado para puente de conferencia, número de teléfono predeterminado para puente de conferencia del inquilino).</li></ul>|

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla para capturar los detalles de los puentes de conferencia:
>|Oficina   |Adquisición de número de puente y tipo de puente |Número de puente  |Idioma de puente|
>|---------|---------|---------|---------|
>|One Epping Road|Adquirir nuevo, dedicado|Por añadir|Inglés (Australia)|
>|One Marina Boulevard|Adquirir nuevo, compartido|Por añadir|Inglés (Estados Unidos), chino (simplificado, RPC)|
>|32 London Bridge Street|Puerto existente, dedicado|+44 20 7946 0001|Inglés (Reino Unido)|
>|39 quai du Président Roosevelt|Adquirir nuevo, dedicado|Por añadir|Francés (Francia), inglés (Reino Unido)|

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

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si la organización necesita notificaciones de entrada y salida y, en caso afirmativo, el tipo de notificación que se implementará (tonos, número de teléfono o nombre grabado).</li><li>Decida la longitud del PIN de Audioconferencia que cumpla los requisitos de seguridad de la organización.</li><li>Decida si la organización quiere controlar las comunicaciones de los usuarios finales que estén relacionadas con el servicio de Audioconferencia.</li><li>Decida qué números de teléfono para puentes de conferencia se asignarán a cada organizador de reuniones.</li><li>Decida si algunos organizadores de reuniones necesitan la opción de usar números de teléfono gratuitos para puentes de conferencia para sus reuniones.</li><li>Decida si algunos organizadores de reuniones necesitan la opción de permitir que autores de llamada sin autenticar puedan iniciar una reunión.</li><li>Decida si algunos organizadores de reuniones necesitan que se controlen las llamadas desde la conferencia.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Documente la configuración de puentes de conferencia con todos los detalles (notificaciones de entrada y salida, longitud de PIN y notificación por correo electrónico de cambios en la configuración).</li><li>Documente qué números de teléfono para puentes de conferencia se asignan a cada organizador de reunión y la configuración correspondiente para controlar la directiva de autores de llamada sin autenticar y los controles de llamadas desde la reunión y gratuitas.</li></ul>|

> [!TIP]
> La configuración de puentes de conferencia se puede documentar del modo siguiente:
>|         |         |
>|---------|---------|
>|Habilitar las notificaciones de entrada y salidas de las reuniones|Habilitado|
>|Tipo de anuncio de entrada/salida|Tonos|
>|Pedir a los autores de llamada que graben su nombre antes de unirse a la reunión|Deshabilitado|
>|Longitud de PIN|5|
>|Enviar correos automáticamente a los usuarios si cambia su configuración de acceso telefónico|Deshabilitado|

<br>
> [!TIP]
> Puede documentar la lista de asignaciones de configuraciones de puentes de conferencia para usuarios de Audioconferencia usando el siguiente ejemplo:
>|Usuario  |Oficina  |Número de pago predeterminado  |Número gratuito predeterminado  |Permitir número gratuito  |Los autores de llamadas sin autenticar no pasan por la sala de espera  |Llamadas desde la conferencia  |
>|---------|---------|---------|---------|---------|---------|---------|
>|Adele Vance|One Epping Road|Por añadir|Por añadir|Sí|Habilitado|Internacionales y nacionales|
>|Alex Wilber|One Epping Road|Por añadir|Por añadir|No|Deshabilitado|No se permiten|
>|Ben Walters|One Epping Road|Por añadir|Por añadir|No|Deshabilitado|No se permiten|
>|Christie Cline|One Marina Boulevard|Por añadir|Por añadir|Sí|Deshabilitado|Nacionales|
>|Debra Berger|One Marina Boulevard|Por añadir|Por añadir|Sí|Habilitado|Nacionales|
>|Lee Gu|One Marina Boulevard|Por añadir|Por añadir|Sí|Habilitado|Nacionales|
>|Emily Braun|32 London Bridge Street|+44 20 7946 0001|Por añadir|Sí|Habilitado|No se permiten|
>|Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|Por añadir|Sí|Deshabilitado|No se permiten|
>|Pradeep Gupta|32 London Bridge Street|+44 20 7946 0001|Por añadir|Sí|Deshabilitado|No se permiten|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Por añadir|Por añadir|No|Deshabilitado|Nacionales|
>|Rachelle Cormier|39 quai du Président Roosevelt|Por añadir|Por añadir|Sí|Habilitado|Internacionales y nacionales|
>|Isabell Potvin|39 quai du Président Roosevelt|Por añadir|Por añadir|No|Deshabilitado|Nacionales|

## <a name="dial-plans"></a>Planes de marcado

Un [plan de marcado](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) en la característica de Sistema telefónico de Office 365 es un conjunto de reglas de normalización con las que los números de teléfono que se marcan se traducen a un formato alternativo (normalmente, el formato [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) para poder autorizar las llamadas y enrutarlas. El servicio de Audioconferencia utiliza las mismas funcionalidades de Sistema telefónico para traducir los números de teléfono marcados en escenarios de llamadas desde la conferencia.

Con un plan de marcado, los usuarios pueden marcar números de teléfono como suelen hacerlo, como, por ejemplo, omitiendo el código de área para las llamadas locales, omitiendo el código de país para las llamadas domésticas o incluso usando una marcación de dígitos breve cuando se realizan llamadas desde la conferencia.

Dentro de la característica de Sistema telefónico de Office 365, existen dos tipos de planes de marcado:

-   **Plan de marcado de servicio**. Es el plan de marcado predeterminado y se aplica a los usuarios en función de la ubicación de uso de Office 365. No se puede modificar.
-   **Plan de marcado de inquilino**. Este plan de marcado se puede personalizar dentro de un inquilino y se puede volver a dividir en dos tipos:
    -   **Plan de marcado de inquilino global:** el plan de marcado se aplica a todos los usuarios dentro del inquilino.
    -   **Plan de marcado de usuario de inquilino:** el plan se aplica únicamente a determinados usuarios.

> [!NOTE]
> Consulte la documentación [¿Qué son los planes de marcado?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) para obtener más información y ejemplos.

El plan de marcado efectivo que se asigna a los usuarios es la combinación del plan de marcado de servicio (basado en la ubicación de uso de Office 365 del usuario) y el plan de marcado de inquilino (ya sea el de inquilino global o el de usuario de inquilino).

![La tabla muestra tres combinaciones de planes de marcado de inquilino y servicio.](media/audio_conferencing_image8.png)

Hay un máximo de 25 reglas de normalización en cada plan de marcado de inquilino y, por lo tanto, hay que evitar duplicar las reglas de normalización que ya están disponibles como parte del plan de marcado de servicio.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si su organización necesita planes de marcado personalizados (requisitos empresariales, requisitos de adopción, etc.).</li><li>En caso de necesitarlos, decida qué ámbito del plan de marcado de inquilino (inquilino global o usuario de inquilino) se ajusta a los requisitos de los planes de marcado personalizados.</li><li>En caso necesario, decida los planes de macado de inquilino que se van a crear como soporte a las oficinas o ubicaciones de los usuarios en las que se va a implementar Audioconferencia.</li><li>En caso necesario, decida qué usuario necesita un plan de marcado personalizado y qué plan de marcado de inquilino se va a asignar a cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Documente qué planes de marcado personalizados y reglas de normalización asociadas se van a configurar como parte de la implementación de Audioconferencia.</li><li>Documente a qué usuarios se les va a asignar un plan de marcado personalizado y qué plan de marcado de inquilino se va a asignar a cada usuario.</li></ul>|

> [!TIP]
> Si es aplicable a su proyecto, puede usar la siguiente plantilla para documentar las configuraciones de planes de marcado de inquilino:
>|Nombre de plan de marcado de inquilino<br>_Descripción_  |Nombre de reglas de normalización<br>_Descripción_  |Patrón<br>Traducción<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_Plan de marcado de One Epping Road North Ryde, NSW, AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Número interno (x7000 - x7999) para oficina de One Epping Road, North Ryde, NSW, Australia_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_Normalización de número local para NSW, Australia_|^([2-9]\d{7})$<br>+612$1<br>False|
>||**AU-TollFree**<br>_Normalización de número gratuito para Australia_|^(1[38]\d{4,8})\d*$<br>+61$1<br>False|
>||**AU-Service**<br>_Normalización de número de servicio para Australia_|^(000\|1[0125]\d{1,8})$<br>1 $<br>False|
>|**SG-Singapore-OMB**<br>_Plan de marcado de OMB Singapore, SG_|**SG-OMB-Internal**<br>_Número interno (x8000 – x8999) para la oficina de +OMB, Singapur_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_Normalización de número gratuito para Singapur_|^(1?800\d{7})\d*$<br>+65$1<br>False|
>||**SG-Service**<br>_Normalización de número de servicio para Singapur_|^(1\d{3,4}\|9\d{2})$<br>1 $<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_Plan de marcado de 39 quai du Président Roosevelt Issy-les-Moulineaux, Francia_|**FR-39qdPR-Internal**<br>_Número interno (x7000 – x7999) para 39 quai du Président Roosevelt office, Issy-les-Moulineaux, Francia_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_Normalización de número gratuito para Francia_|^0?(80\d{7})\d*$<br>+33$1<br>False|
>||**FR-Service**<br>_Normalización de número de servicio para Francia_|^(1\d{1,2}\|11[68]\d{3}\|10\d{2}\|3\d{3})$<br>1 $<br>False|

<br>
> [!TIP]
> La plantilla de ejemplo siguiente se puede utilizar para documentar las asignaciones de planes de marcado de su proyecto:
>|Usuario  |Oficina  |Tipo de plan de marcado  |Nombre de plan de marcado  |
>|---------|---------|---------|---------|
>|Adele Vance|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
>|Alex Wilber|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
>|Ben Walters|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
>|Christie Cline|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
>|Debra Berger|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
>|Lee Gu|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
>|Emily Braun|32 London Bridge Street|Plan de marcado de servicio|N/D|
>|Lidia Holloway|32 London Bridge Street|Plan de marcado de servicio|N/D|
>|Pradeep Gupta|32 London Bridge Street|Plan de marcado de servicio|N/D|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|

## <a name="microsoft-teams-configurations"></a>Configuraciones de Microsoft Teams

La compatibilidad para Audioconferencia está disponible para reuniones ad hoc y programadas. Para las reuniones programadas, hay que habilitar las configuraciones a nivel de inquilino que rigen la programación de las reuniones (reuniones privadas y de canal).

> [!NOTE]
> Por el momento, si su organización tiene ciertas normativas por las que se tienen que poder detectar todas las discusiones de las reuniones, debe deshabilitar las reuniones privadas si el organizador tiene un buzón de correo local de Exchange.<br>
> En otros casos, si todas las reuniones de la organización solo pueden estar visibles **para las partes invitadas** y así evitar que se revele la información de reuniones a partes que no están invitadas, le recomendamos que deshabilite la capacidad de programar reuniones en **canales**.

Las configuraciones, disponibles como configuraciones a nivel de inquilino, se aplican a todos los usuarios de la organización y repercutirán en la programación de todas las reuniones de Microsoft Teams, no solo en las reuniones de Microsoft Teams **con** Audioconferencia.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si la organización tiene que habilitar o deshabilitar la programación de reuniones privadas.</li><li>Decida si la organización tiene que habilitar o deshabilitar la programación de reuniones de canal.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Documente las configuraciones para la programación de reuniones de Microsoft Teams.</li></ul>|

> [!TIP]
> Las configuraciones de reuniones de Microsoft Teams se pueden documentar del modo siguiente:
>|         |         |
>|---------|---------|
>|Permitir la programación de reuniones privadas|Habilitado|
>|Permitir la programación de reuniones de canal|Deshabilitado|

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

<br>
Una vez que complete el plan de éxito y el plan de implementación técnico, podrá seguir con el recorrido de cliente de Office 365.

<br>
Incorporación =======

*Próximamente*

<br>
Nuevos valores ===========

*Próximamente*

<br>
## <a name="see-also"></a>Vea también

[Configurar Audioconferencia para Skype Empresarial y Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
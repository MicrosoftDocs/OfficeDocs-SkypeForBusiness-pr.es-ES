---
title: "Guía práctica para Sistema telefónico con planes de llamada en Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: "Guía práctica para planificar, implementar y administrar Sistema telefónico con Planes de llamada en Microsoft Teams mediante el marco Enfoque (planificar), Incorporación (entregar), Nuevos valores (operar)."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5ed92ed1fd156279c32c2627b85eca170a457f0
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a>Guía práctica para Sistema telefónico con planes de llamada en Microsoft Teams
=========================================================================

Sistema telefónico es una funcionalidad de Office 365 que permite administrar el enrutamiento de llamadas, las directivas y el aprovisionamiento de usuarios. Aquí se incluye el sistema de administración de llamadas, el enrutamiento de llamadas y el control de llamadas.

Planes de llamada de Office 365 es un servicio complementario para la función Sistema telefónico que se proporciona a través de Microsoft Teams y Skype Empresarial Online. Planes de llamada proporciona a los usuarios de su empresa un número de teléfono principal y les permite realizar llamadas fuera de la organización y recibirlas a través de la red telefónica conmutada (RTC).

Para obtener más información, consulte [Esto es lo que conseguirá con Sistema telefónico en Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) y [¿Qué son los Planes de llamada en Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)

En esta guía práctica se detallan el recorrido que sigue el cliente con FastTrack para Office 365 y las tres fases que lo conforman (Enfoque, Incorporación y Nuevos valores) para ayudarle a planificar, entregar y utilizar una implementación correcta de Sistema telefónico con Planes de llamada.

> [!TIP]
> En esta guía práctica ofreceremos ejemplos de respuestas para todas las actividades y discusiones clave. Los ejemplos de este documento se muestran dentro de recuadros de CONSEJO y se pueden utilizar como plantillas. La frase "Por añadir" indica que falta por completar con información como parte del proceso de planificación.

Enfoque <a name="Envision_PhoneSystemWithCallingPlans"> </a>
========

La fase de Enfoque, en la que se define el recorrido que tendrá que hacer el cliente de Office 365, es aplicable a todo tipo de cargas de trabajo, incluidas las de Sistema telefónico con Planes de llamada.

En esta fase se definen los objetivos empresariales, con la participación de todas las partes interesadas del proyecto, para, por último, presentar:

-   Un plan de éxito de gran nivel que contenga casos de uso empresariales, las principales partes interesadas, los objetivos y resultados principales, los indicadores de éxito principales, los riesgos, la evaluación del entorno, la preparación para la adopción y el plan operativo.

-   Un plan detallado de implementación técnica de Sistema telefónico con Planes de llamada para conseguir el estado final deseado.

<a name="define-business-use-cases-for-phone-system-with-calling-plans"></a>Definir casos de uso empresariales para Sistema telefónico con Planes de llamada
-------------------------------------------------------------

Sistema telefónico con Planes de llamada permite a las organizaciones modernizar su área de trabajo al permitir a los usuarios realizar llamadas telefónicas de trabajo desde sus equipos y dispositivos móviles.

La modernización del área de trabajo puede realizarse como parte de una implementación de un modelo de trabajo basado en actividades, un cambio de oficinas, una actualización de la dotación de las oficinas, la retirada de soluciones de centrales de conmutación (PBX) antiguas, la finalización de un contrato con un proveedor de servicios RTC, etc.

En este paso, los principales participantes del proyecto definirán casos de uso empresariales relacionados con la implementación de Sistema telefónico con Planes de llamada.

Los casos de uso empresariales se aportan con la intención de documentar los resultados que se esperan y que se pueden medir. Incluyen lo siguiente:

-   Descripción del proceso de negocio actual
-   Retos que se deben conseguir con el proceso de negocio actual definido.
-   De qué manera la tecnología puede ayudar a alcanzar estos retos.
-   Los resultados empresariales que se esperan y que se pueden medir si se alcanzan los retos impuestos anteriormente.

> [!TIP]
> A continuación se muestra un ejemplo de caso de uso de negocio completado:
>|         |
>|---------|
>|**Descripción del proceso de negocio actual**<p>La configuración estándar de las áreas de trabajo de la oficina de Contoso incluye un teléfono de escritorio en cada mesa. A cada empleado se le proporcionará un número de teléfono de marcado entrante directo (DID). Los teléfonos de escritorio van conectados a un sistema PBX y a RTC mediante un tronco de protocolo de inicio de sesión (SIP). Los empleados solo pueden realizar y recibir llamadas telefónicas en sus teléfonos de escritorio asignados.|
>|**Retos que se deben conseguir con el proceso de negocio actual definido**<p>El análisis de uso de los teléfonos de escritorio muestra que solo el 10% de los teléfonos de escritorio se usan activamente, mientras que el resto están configurados para desviar llamadas a teléfonos móviles o están configurados para llamar simultáneamente a teléfonos móviles. El mantenimiento del sistema PBX existente y de los teléfonos de escritorio asociados contribuye al 20% del coste de servicio de telefonía.|
>|**De qué manera la tecnología puede ayudar a alcanzar estos retos**<p>El sistema telefónico con planes de llamada permitirá que el PC personal del usuario final pueda recibir y realizar llamadas telefónicas en la red de datos aprovechando la aplicación nativa de Microsoft Teams, eliminando así la necesidad de desplegar y mantener teléfonos de escritorio. Esto da la oportunidad de desmantelar el sistema PBX existente, ya que el servicio telefónico se puede ofrecer mediante la nube a través de la red sin tener que depender del sistema telefónico tradicional.|
>|**Propósitos y medición de los resultados de negocio**<p>Eliminar los requisitos para mantener y desmantelar el PBX heredado existente y los teléfonos de escritorio proporcionarán una reducción del 20% del gasto de servicios de telefonía mensual. El sistema telefónico con planes de llamada simplificará las áreas de trabajo de la oficina, de modo que Contoso podrá ampliar sus operaciones estableciendo nuevas oficinas con un mínimo coste de telefonía inicial.|

Durante la fase de Enfoque, además de definir los casos de uso de su empresa, deberá aclarar los siguientes elementos:
- Ámbito organizativo
- Escalas de tiempo del proyecto

<a name="identify-key-stakeholders"></a>Identificar las partes interesadas clave
-------------------------

Los casos de uso empresariales que se definieron en el paso anterior incluirán el ámbito organizativo de la implementación de Sistema telefónico con Planes de llamada. En función de eso, se completará la matriz de participantes con la adición de las personas que tienen que estar involucradas en el proyecto.

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
>|Propietario del servicio|<ul><li>Es responsable de que el servicio de Sistema telefónico con Planes de llamada funcione de forma continua.</li><li>Propietario del servicio de Sistema telefónico con Planes de llamada</li></ul>|Por añadir|
>|Expertos en calidad|<ul><li>Genera calidad, fiabilidad y recopila opiniones de los usuarios.</li><li>Identifica las tendencias en la calidad y propicia la corrección de los problemas con los equipos correspondientes.</li><li>Mantiene informada a la directiva a través del comité directivo.</li><li>Informa sobre la calidad, la fiabilidad y las opiniones de los usuarios a través de Valorar mi llamada y Net Promoter Score.</li></ul>|Por añadir|

<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Definir objetivos y resultados principales, indicadores de éxito principales y riesgos
--------------------------------------------------------------------

Con la participación de todas las partes involucradas en el proyecto, los casos de uso empresariales, el ámbito organizativo y las escalas de tiempo del proyecto se pueden traducir en objetivos y resultados principales (OKR, del inglés "Objectives and Key Results"), y las medidas de éxito del proyecto se pueden definir en una lista de indicadores de éxito principales (KSI, del inglés "Key Success Indicators").

Al contar con la plena participación de todos las partes involucradas en el proyecto a la hora de definir los OKR y los KSI, se garantiza el sentido de propiedad y su adecuación a los requisitos organizativos del negocio.

Los OKR contendrán una lista de los objetivos que se establecieron al inicio del proyecto, con los principales resultados que se pueden medir y que se definen trimestralmente. Los principales resultados se revisan mensualmente para hacer un seguimiento del estado del proyecto general y, en función de cómo avancen, se podrán ir ajustando los planes trimestrales.

> [!TIP]
> A continuación puede consultar un ejemplo de OKR relevantes para la implementación de Sistema telefónico con Planes de llamada:
><br>
>
>**Visión: aumentar la productividad maximizando las inversiones de Office 365**
>|Objetivos  |Resultados principales  |Acciones que realizar  |
>|---------|---------|---------|
>|Implementar Sistema telefónico con Planes de llamada en las sucursales europeas a finales del año fiscal 2018|T3 2018: implementar Sistema telefónico con Planes de llamada en la oficina de Londres|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
>|Retirar el sistema PBX antiguo de la oficina de Londres a finales del año fiscal 2018|T4 2018: retirar el sistema PBX antiguo de la oficina de Londres|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|

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
>|Financiero|Reducción del gasto mensual en servicios de telefonía|Sistema financiero|Cumplir el ROI definido|Basado en ROI|Equipo de administración de cambios|

Como parte de este ejercicio, hay que identificar los riesgos del negocio y definir un plan de mitigación para cada uno de los riesgos que se identifiquen. Registre esta información en un plan de riesgos.

> [!TIP]
> El plan de riesgos puede documentarse del modo que se muestra en el siguiente ejemplo:
>|Riesgo  |Probabilidad  |Impacto  |General  |Plan de mitigación  |
>|---------|---------|---------|---------|---------|
>|Con la próxima fusión se sumarán hasta 1000 personas|Alta|Alta|Alta|<ul><li>Para las empresas fusionadas, OKR independiente con proceso propio (Enfoque, Incorporación, Nuevos valores).</li><li>No se deben incluir en los OKR existentes.</li></ul>|
>|La portabilidad de los números de teléfono retrasará la finalización del proyecto.|Alta|Alta|Alta|<ul><li>Se debe preparar con antelación toda la información para la portabilidad de los números de teléfono (registro de servicios al cliente, detalles de facturación, carta de autorización).</li><li>La escala de tiempo del proyecto se debe ajustar para incluir el tiempo que se tarda en realizar la portabilidad de los números de teléfono.</li><li>Se deben usar números de teléfono temporales con manipulación del identificador de llamada.</li></ul>|
>|Se ha planificado rediseñar las redes|Alta|Mediana|Mediana|<ul><li>Antes de implementar Microsoft Teams como plataforma de colaboración y comunicaciones moderna, evalúe la preparación de la red en los sitios que se incluyen en el ámbito del proyecto.</li></ul>|

<a name="assess-environment-and-evaluate-adoption-readiness"></a>Evaluar el entorno y la preparación que se tiene para la adopción
--------------------------------------------------

Para conseguir los OKR que se pretenden, es posible que tenga que definir una arquitectura de alto nivel de la solución. De este modo, se evalúan todos los aspectos relacionados con la infraestructura de TI y telefonía, las redes y las operaciones a través del descubrimiento del entorno.

Todas las cuestiones relacionadas con la informática para usuarios finales, como la evaluación de la preparación de los ordenadores personales y los dispositivos móviles para admitir casos de uso empresariales para Sistema telefónico con Planes de llamada, desde los requisitos de hardware hasta los de software, se incluirán como parte del proceso de descubrimiento del entorno.

Con el descubrimiento del entorno también se puede poner de manifiesto si existe la necesidad de [transferir números de teléfono a Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Office-365-47b3af8e-4171-4dec-8333-c956f108664e). De este modo, la organización podrá ajustar el plan de proyecto y preparar toda la información que necesite para la portabilidad de los números. Para realizar un descubrimiento del entorno, use el [cuestionario de descubrimiento](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_3).

En el descubrimiento del entorno se debe incluir la evaluación de preparación de la red para asegurarse de que esta puede soportar la implementación de Sistema telefónico con Planes de llamada.

También se puede determinar si la red está preparada para soportar Sistema telefónico con Planes de llamada evaluando la información recopilada con el descubrimiento del entorno (como los detalles de la conectividad a Internet y la topología de WAN, los vínculos a sitios o el ancho de banda disponible) y los datos de los análisis de personas (que se pueden traducir en el uso que se espera de cada carga de trabajo) en la [herramienta My Advisor Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). Para confirmar en mayor medida el estado de la red, se puede realizar una simulación del tráfico multimedia en tiempo real con estas soluciones:
- Desde Microsoft: [herramienta de evaluación de red de Skype Empresarial](https://www.microsoft.com/download/details.aspx?id=53885)
- Desde un socio: [socios de herramientas para la evaluación de la preparación de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Partners?ToolPartners)

Con los resultados de esta evaluación se podrá tener una idea más clara de la corrección o la optimización que se necesita hacer en la red para que la implementación de Sistema telefónico con Planes de llamada se pueda desarrollar correctamente.

Para evaluar la preparación para la adopción se puede ejecutar un análisis de personas que genere una lista de las personas de la organización para las que se podrá llevar a cabo la implementación de Sistema telefónico con Planes de llamada. El análisis de personas incluye la identificación de otros periféricos y dispositivos que se necesitan para obtener los resultados de negocio que se desean.

Para realizar el análisis de personas, puede realizar un taller en el que se involucre a todas las partes relevantes del proyecto mediante la plataforma de talleres [Persona Alignment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_7) y [Persona Feature Matrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_8). El resultado de este taller de análisis de personas se puede resumir en un informe que se elabora con la plantilla [Persona Analysis Report](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_9).

> [!NOTE]
> Si bien el cuestionario de descubrimiento y los ejemplos de análisis de personas se crearon en un principio para Skype Empresarial Online, la mayoría del contenido es válido para Microsoft Teams. Modifique y quite los elementos que crea que no son relevantes de los objetivos del proyecto.

Los riesgos técnicos se pueden identificar como parte de una evaluación del entorno y la evaluación de la preparación para la adopción, y se puede desarrollar un plan de mitigación para cada uno de los riesgos que se identifiquen. Esta información se debe incorporar en el plan de riesgos.

<a name="map-operational-roles"></a>Asignar roles operativos
---------------------

Planificar las operaciones e identificar a los equipos que utilizarán el servicio de Sistema telefónico con Planes de llamada es un paso muy importante, ya que las operaciones deben comenzar cuando se habiliten los primeros usuarios del grupo piloto. Cada uno de los equipos que se identifiquen debe revisar y aceptar las tareas y las responsabilidades que se señalen, y deben comenzar la preparación para utilizar el servicio de Sistema telefónico con Planes de llamada. En la fase de preparación se podría incluir formación y capacitación, contratación de más personal o garantizar que los proveedores externos están listos para ofrecer el servicio.

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla para documentar el resultado del ejercicio de asignación de roles operativos que ha realizado como parte del proyecto:
>|Rol operativo  |Descripción  |Equipo  |Datos de contacto  |
>|---------|---------|---------|---------|
>|Propietario del servicio|Propietario del servicio, interactuar con las divisiones de la empresa, estrategia|Por añadir|Por añadir|
>|Operaciones de Sistema telefónico con Planes de llamada|Operaciones diarias, transferencia/adición/cambio de cuentas de dispositivos y usuarios, supervisión|Por añadir|Por añadir|
>|Administrador de inquilinos|Cambiar la configuración de todos los inquilinos, habilitar nuevas características|Por añadir|Por añadir|
>|Servicio de asistencia|Interactuar con usuarios finales que necesitan soporte|Por añadir|Por añadir|
>|Operaciones de red|Cubre LAN, WAN, Wi-Fi y acceso a Internet|Por añadir|Por añadir|
>|Equipo de cliente y puntos de conexión|Administrar implementaciones de escritorio|Por añadir|Por añadir|
>|Operaciones de identidad|Administrar infraestructura de identidad (AD, ADFS, Azure AD)|Por añadir|Por añadir|
>|Adopción/administración de cambios|Administrar el reconocimiento, la formación y la adopción de la solución|Por añadir|Por añadir|
>|Operaciones de Exchange|Administra el entorno de Exchange|Por añadir|Por añadir|

Para que se pueda llevar a cabo de una forma más detallada la asignación de roles operativos, incluidas las tareas asociadas a cada rol operativo, el [libro de trabajo para la asignación de roles operativos](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_16) puede ser muy útil para capturar los detalles que determinarán con claridad cuáles son los roles y las responsabilidades que se aplicarán en el servicio de Sistema telefónico con Planes de llamada.

<a name="document-success-plan"></a>Documentar el plan de éxito
---------------------

Un plan de éxito es la documentación que se crea en la fase de Enfoque y que consta del caso de negocio, la preparación del servicio, el plan de adopción y el plan operativo.

El plan de éxito proporcionará al equipo del proyecto (que puede incluir FastTrack o el socio de implementación) la información que le permita alcanzar los objetivos de la organización con el servicio de Sistema telefónico con Planes de llamada.

En general, un plan de éxito contendrá las siguientes secciones principales:

-   Caso de negocio
-   Preparación del servicio
-   Plan de adopción
-   Plan operativo

### <a name="business-case"></a>Caso de negocio

Los casos de uso de negocio, las partes interesadas, los OKR y los KSI, los riesgos y las escalas de tiempo del proyecto configuran normalmente la mayor parte de la información requerida para un caso de negocio. Es necesario documentarlos como parte del plan de éxito.

### <a name="service-readiness"></a>Preparación del servicio

Con la evaluación del entorno se obtiene la información inicial que se necesita para determinar la preparación técnica de la organización para implementar el servicio de Sistema telefónico con Planes de llamada.

Aquí se incluye el plan para abordar las áreas que necesitan correcciones y que se han detectado durante la evolución del entorno. Como parte del plan de éxito, hay que incluir la evaluación de preparación del servicio y el plan de corrección.

### <a name="adoption-plan"></a>Plan de adopción

Tras evaluar la preparación de la adopción, es necesario completar otra planificación más detallada para que el equipo del proyecto pueda elaborar un conjunto completo de planes de comunicación, un plan de formación y actividades de adopción previas al lanzamiento, para el lanzamiento y posteriores al lanzamiento.

En este paso también se identifican los recursos que respaldan las actividades de adopción, como prospectos, correos electrónicos de bienvenida y materiales de formación, junto con las personalizaciones que hay que hacer para cumplir los requisitos de la organización.

Las plantillas para las actividades de adopción están disponibles [aquí](https://www.microsoft.com/download/details.aspx?id=54244).

### <a name="operational-plan"></a>Plan operativo

El ejercicio para la asignación de roles operativos establecerá los roles y las responsabilidades, así como los equipos asignados a cada rol operativo para realizar la implementación del servicio de Sistema telefónico con Planes de llamada.

Hay que completarlo e incluir el plan operativo como parte del plan de éxito para garantizar la preparación operativa de la solución.

<br>
Planificación técnica para Sistema telefónico con Planes de llamada
------------------------------------------------------

Para planificar la implementación técnica de Sistema telefónico con Planes de llamada, hay que tomar una serie de decisiones con antelación para preparar mejor a la organización y lograr una implementación de una solución que cumpla los requisitos del negocio. Estas decisiones se documentarán en un plan de implementación técnico.

## <a name="availability-of-calling-plans"></a>Disponibilidad de Planes de llamada

Para averiguar dónde está disponible el servicio de Planes de llamada, consulte [Países y regiones en los que están disponibles Audioconferencias y Planes de llamada](https://support.office.com/article/Countries-regions-that-are-supported-for-Audio-Conferencing-and-Calling-Plans-6ba72f37-d303-4795-aa8f-7e1845078ed7).

> [!IMPORTANT]
> Por imperativo de carácter jurídico, para que Planes de llamada pueda estar disponible en organizaciones multinacionales, el contrato de suscripciones de Office 365 debe provenir de países y regiones que estén cubiertos por el servicio de Planes de llamada o en los que el servicio de Planes de llamada esté disponible comercialmente.

Tras confirmar que su organización reúne los requisitos para poder usar el complemento Planes de llamada, recopile la lista de ubicaciones de usuario u oficinas en las que se implementará el servicio de Planes de llamada según la lista de países y regiones disponibles.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida en qué oficinas o ubicaciones de usuario se implementará el servicio de Planes de llamada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Documente qué oficinas o ubicaciones de usuario se habilitarán para el servicio de Planes de llamada.</li></ul>|

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla de la lista de habilitación del sitio de Sistema telefónico con Planes de llamada:
>|Oficina   |Ubicación |Servicio de Sistema telefónico  |
>|---------|---------|---------|
>|One Epping Road|Australia|Servicio de RTC antiguo|
>|100 Cyberport Road|RAE de Hong Kong|Servicio de RTC antiguo|
>|One Marina Boulevard|Singapur|Servicio de RTC antiguo|
>|32 London Bridge Street|Reino Unido|Sistema telefónico con Planes de llamada|
>|39 quai du Président Roosevelt|Francia|Sistema telefónico con Planes de llamada|

## <a name="licensing-for-calling-plans"></a>Licencias de Planes de llamada

Planes de llamada es un componente de la función Sistema telefónico en Office 365, por lo que debe tener habilitada una licencia de Sistema telefónico para usar Planes de llamada.

La [licencia de Sistema telefónico](https://support.office.com/article/Skype-for-Business-and-Microsoft-Teams-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7) está disponible como parte de los planes de suscripción de Office 365 E5, o como complemento para los planes de suscripción de Office 365 E1 y E3.
Hay dos tipos de [licencia de Planes de llamada](https://support.office.com/article/Calling-Plans-for-Office-365-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918):

-   Plan de llamada nacional
-   Plan de llamada nacional e internacional

> [!NOTE]
> La definición de "nacional" para un usuario específico está determinada por la ubicación de uso de Office 365 asignada al usuario.

Cada tipo de Plan de llamada proporciona una asignación de minutos de llamada que los usuarios pueden usar al mes, ya sea para realizar llamadas nacionales o internacionales. Los Planes de llamada nacionales tienen un coste menor que los Planes de llamada nacionales e internacionales. Para averiguar cuántos minutos están disponibles para cada país/región, consulte la sección "Planes de llamada" de [Países y regiones en los que están disponibles Audioconferencias y Planes de llamada](https://support.office.com/article/Countries-regions-that-are-supported-for-Audio-Conferencing-and-Calling-Plans-6ba72f37-d303-4795-aa8f-7e1845078ed7).

Normalmente no es necesario que todos los usuarios de una organización puedan realizar llamadas internacionales. La flexibilidad de poder suscribir y asignar el tipo de Plan de llamada más adecuado en función de los requisitos empresariales de cada usuario le permite a su organización controlar los costes de la implementación de Planes de llamada.

Para cada inquilino de Office 365, la cantidad combinada de minutos de llamada se agrupa por país o región, y por tipo de Plan de llamada. Cuando un inquilino llega al límite de minutos de llamada mensual, el servicio de Planes de llamada se suspende hasta finalizar el mes (a excepción de las llamadas de emergencia). Los servicios de Planes de llamada se reanudarán automáticamente el primer día del siguiente mes natural.

Para que los usuarios puedan realizar llamadas salientes después de agotar los minutos de llamada sin que tengan que esperar al ciclo de facturación del mes siguiente, puede configurar Créditos de comunicaciones para su organización. Los [Créditos de comunicaciones](https://support.office.com/article/What-are-Communications-Credits-524dbea7-117f-493d-8005-6461f7f10059) también permiten a los usuarios que tienen asignado un Plan de llamada nacional realizar llamadas internacionales que se facturarán por minuto.

La primera consideración que hay que tener en cuenta a la hora de implementar Créditos de comunicaciones es decidir la cantidad inicial de fondos que se deben adquirir. La cantidad de fondos que se recomienda se puede consultar en el artículo [Créditos de comunicaciones](https://support.office.com/article/What-are-Communications-Credits-524dbea7-117f-493d-8005-6461f7f10059).

En el artículo [Créditos de comunicaciones](https://support.office.com/article/What-are-Communications-Credits-524dbea7-117f-493d-8005-6461f7f10059) también se incluye una recomendación para el umbral (la cantidad más baja de fondos), lo que le interesará especialmente si su organización decide utilizar la recarga automática. El importe de recarga automática se determina por el uso real. Con el paso del tiempo es recomendable supervisar el uso de Créditos de comunicaciones y ajustar la cantidad de recarga según sea necesario.

El uso de Créditos de comunicaciones se puede controlar por usuario, lo que le permite asegurarse de que se ha asignado la funcionalidad a personas de la organización que tienen necesidades empresariales legítimas para usarla.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Si su organización aún no ha adquirido las licencias de Sistema telefónico que necesita, decida si estas licencias se van a adquirir incrementando las suscripciones existentes de Office 365 o comprando complementos de Sistema telefónico.</li><li>Decida qué usuarios necesitan un Plan de llamada nacional y cuáles necesitan un Plan de llamada nacional e internacional.</li><li>Decida si los Créditos de comunicaciones son necesarios para la implementación de Planes de llamada. En tal caso, decida la cantidad inicial de fondos que se va a comprar. Cuando sea necesario, decida la cantidad para el umbral y la cantidad de autorecarga.</li><li>Decida qué usuarios necesitan usar una licencia de Créditos de comunicaciones.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Documente a qué usuarios se asignará una licencia de Sistema telefónico junto con una licencia de Plan de llamada nacional y a qué usuarios se asignará una licencia de Sistema telefónico con una licencia de Plan de llamada nacional e internacional.</li><li>Documente el plan de Créditos de comunicaciones (cantidad inicial, cantidad de umbral y cantidad de recarga automática).</li><li>Documente qué usuarios se habilitarán para el uso de una licencia de Créditos de comunicaciones.</li></ul>|

> [!TIP]
> Puede documentar la lista de asignación de licencias a usuarios de Sistema telefónico con Planes de llamada con el ejemplo siguiente:
>|Usuario  |Oficina  |Licencia de Office 365  |Créditos de comunicaciones  |
>|---------|---------|---------|---------|
>|Emily Braun|32 London Bridge Street|Office 365 E5, Plan de llamada nacional e internacional|Habilitado|
>|Lidia Holloway|32 London Bridge Street|Office 365 E5, Plan de llamada nacional|Deshabilitado|
>|Pradeep Gupta|32 London Bridge Street|Office 365 E5, Plan de llamada nacional|Habilitado|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, complemento Sistema telefónico, Plan de llamada nacional|Deshabilitado|
>|Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5, Plan de llamada nacional e internacional|Habilitado|
>|Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, complemento Sistema telefónico, Plan de llamada nacional|Deshabilitado|

<br>
> [!TIP]
> Los números de planificación de Créditos de comunicaciones se pueden documentar del modo siguiente:
>|         |         |
>|---------|---------|
>|Cantidad inicial|1000 $|
>|Cantidad de umbral|400 $|
>|Cantidad de recarga automática|Por añadir|

## <a name="phone-numbers-and-emergency-locations"></a>Números de teléfono y ubicaciones de emergencia

Con Planes de llamada en Office 365, cada usuario de su organización debe tener un número de teléfono de marcado entrante directo (DID, del inglés "Direct Inward Dialing") único y su correspondiente [dirección de emergencia validada](https://support.office.com/article/What-are-emergency-locations-addresses-and-call-routing-589bf5f5-490a-4215-8588-99bab7d33e31).

Los números de teléfono se pueden conseguir [directamente a través de Microsoft](https://support.office.com/article/Manage-phone-numbers-for-your-organization-6b61cb3c-361c-48a8-a9ef-d81bddde27bb), pero también es posible [transferir (portar) a Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Office-365-47b3af8e-4171-4dec-8333-c956f108664e) los números que ya tenga.

> [!NOTE]
> La complejidad que entraña la transferencia de los números de teléfono a Microsoft varía enormemente según cuáles sean los países y las regiones, los operadores, el número de circuitos involucrados y muchos otros factores. Para planificar la portabilidad de los números de teléfono, consulte los detalles recogidos en la [guía de portabilidad de números](https://go.microsoft.com/fwlink/?linkid=859011).

Para obtener números de teléfono de Microsoft directamente, use una de estas opciones:

- [Centro de administración de Skype Empresarial](https://support.office.com/article/Getting-phone-numbers-for-your-users-aa2ec464-3481-4bbb-8c14-e13e18093df5)
- [Cmdlets a través de una sesión remota de Windows PowerShell](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
- [Enviar un formulario de solicitud de números de teléfono nuevos](https://support.office.com/article/Manage-phone-numbers-for-your-organization-6b61cb3c-361c-48a8-a9ef-d81bddde27bb).

El formulario de solicitud de números de teléfono nuevos es la mejor opción para la adquisición planificada de números de teléfono, porque le permite solicitar un bloque de números de teléfono consecutivos. La obtención de números de teléfono mediante el centro de administración de Skype Empresarial o una sesión remota de Windows PowerShell no está disponible en todos los países o regiones.

Los dos primeros métodos (usar el centro de administración de Skype Empresarial o una sesión remota de Windows PowerShell) se pueden utilizar para una adquisición de números de teléfono instantánea y puntual, y cuando no se requieren bloques de números de teléfono consecutivos.

> [!NOTE]
> Existe un límite en la [cantidad de números de teléfono](https://support.office.com/article/How-many-phone-numbers-can-you-get-61dfb27c-5bfa-4481-a930-9c026e73ff3a) que se pueden adquirir a través de Microsoft, que se basa en el número de licencias de Plan de llamada suscritas en su organización. Para calcular los números de teléfono de usuario (suscriptor), la fórmula es (número de Plan de llamada nacional + licencias de Plan de llamada nacional e internacional) x 1,1 + 10. Por ejemplo, si tiene 50 usuarios con licencias de Plan de llamada, puede adquirir 65 números de teléfono ((50 x 1,1) + 10).

Cuando configura números para Planes de llamada, es necesario asignar una dirección de emergencia a cada número de teléfono antes de realizar la asignación al usuario. Este paso es necesario para poder realizar llamadas de emergencia. La dirección de emergencia se debe validar para garantizar que se reconoce, que tiene el formato correcto y que la pueden usar los servicios de respuesta ante emergencias.

> [!IMPORTANT]
> Con el servicio de Planes de llamada, la función de Llamada a servicios de emergencia funciona de modo diferente que con los servicios de telefonía tradicionales. Es importante que comprenda estas diferencias e informe de ellas a todos los usuarios. Consulte [Términos y condiciones de las llamadas de emergencia](https://support.office.com/article/Emergency-calling-terms-and-conditions-ca2c751b-53ab-42c7-aed9-cfe27e662940) para obtener más información.

Además de las direcciones de emergencia validadas, se pueden definir ubicaciones de emergencia y asociarlas con direcciones de emergencia validadas para proporcionar una ubicación más precisa en una dirección. Una ubicación de emergencia es, normalmente, el número de edificio, la planta, la sección del edificio o el número de oficina donde se encuentra el usuario.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida cómo se obtendrán los números de teléfono para las oficinas o ubicaciones de usuario que entran dentro de la implementación de Planes de llamada (obtenerlos de Microsoft o transferir números de teléfono existentes).</li><li>Si elige obtenerlos de Microsoft, decida el método para obtener los números de teléfono (envío de formulario o automatizado) para las oficinas o ubicaciones de usuario que entran dentro de la implementación de Planes de llamada.</li><li>Decida el nivel de detalle de la información sobre ubicación de emergencia que se recopilará para definir las oficinas o ubicaciones de usuario dentro de la implementación de Planes de llamada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Documente el plan maestro para la adquisición de números de teléfono y especifique cómo se obtendrán los números de teléfono para cada oficina o ubicación de usuario que entre dentro de la implementación de Planes de llamada.</li><li>Si corresponde, complete <a href="https://support.office.com/article/Manage-phone-numbers-for-your-organization-6b61cb3c-361c-48a8-a9ef-d81bddde27bb">un formulario de solicitud de número de teléfono nuevo</a> por cada oficina o ubicación.</li><li>Si elige transferir números de teléfono existentes, revise la <a href="https://go.microsoft.com/fwlink/?linkid=859011">guía de portabilidad de números</a> para planificar y ajustar el tiempo de implementación de Planes de llamada de forma acorde.</li><li>Documente las ubicaciones y las direcciones emergencia detalladas para cada oficina o ubicación de usuario dentro de la implementación de Planes de llamada.</li></ul>|

> [!TIP]
> Los detalles sobre la adquisición de números de teléfono, los números de teléfono y los datos de las ubicaciones de emergencia se pueden documentar con la plantilla siguiente:
>|Usuario  |Ubicación y dirección de emergencia  |Adquisición de número de teléfono  |Número de teléfono  |
>|---------|---------|---------|---------|
>|Emily Braun|1034/32 London Bridge Street, Londres, SE1, Reino Unido|Puerto existente|+44 20 7946 0034|
>|Lidia Holloway|1023/32 London Bridge Street, Londres, SE1, Reino Unido|Puerto existente|+44 20 7946 0065|
>|Pradeep Gupta|1023/32 London Bridge Street, Londres, SE1, Reino Unido|Puerto existente|+44 20 7946 0023|
>|Marcel Beauchamp|07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia|Adquirir nuevo|Por añadir|
>|Rachelle Cormier|07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia|Adquirir nuevo|Por añadir|
>|Isabell Potvin|07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Francia|Adquirir nuevo|Por añadir|

## <a name="voicemail"></a>Correo de voz

El correo de voz de Sistema telefónico, con tecnología de los servicios de correo de voz de Azure, solo admite entradas de correo de voz en buzones de Exchange y no es compatible con sistemas de correo electrónico de terceros.

El correo de voz de Sistema telefónico funciona de forma predefinida con Exchange Online, aunque tiene un [modelo de implementación y versión de Exchange local con compatibilidad](https://support.microsoft.com/help/3195158/customer-issues-between-exum-and-azure-voicemail) mínima para permitir la entrega de mensajes de correo de voz a buzones de usuario en la implementación local de Exchange.

El correo de voz de Sistema telefónico cuenta con transcripción del correo de voz y esta opción está activada de forma predeterminada para todos los usuarios de la organización. En algunos casos, es posible que su empresa tenga que desactivar la transcripción del correo de voz para usuarios específicos o en toda la organización.

> [!NOTE]
> Se ha implementado un mecanismo de reserva para que el correo de Sistema telefónico pueda reenviar mensajes mediante SMTP, lo que implica que los usuarios con un buzón de un sistema de correo electrónico de terceros podrán recibir sus mensajes de correo de voz. Sin embargo, no se ofrecen garantías sobre la actividad del servicio ni la disponibilidad de otras funciones del correo de voz, como el cambio del saludo y otros ajustes de configuración.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si habilitará el correo de voz de Sistema telefónico para la implementación de Planes de llamada.</li><li>Si se usa Exchange local y la implementación existente no cumple los requisitos de compatibilidad del correo de voz de Sistema telefónico, elija una de las opciones disponibles (actualizar y realizar la configuración para lograr la compatibilidad con el correo de voz de Sistema telefónico, migrar a Exchange Online o utilizar el mecanismo de reserva).</li><li>Decida si la transcripción del correo de voz estará activada o desactivada en toda la organización, o para usuarios específicos.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Si corresponde, documente los puntos de decisión sobre Exchange relativos al correo de voz de Sistema telefónico.</li><li>Si no va a habilitar para todos los usuarios el correo de voz o la transcripción del correo de voz, documente los usuarios que tendrán habilitadas estas funciones.</li></ul>|

> [!TIP]
> Los detalles sobre el correo de voz de Sistema telefónico para la implementación de Sistema telefónico con Planes de llamada se pueden documentar del siguiente modo:
>|Usuario  |Buzón de Exchange  |Habilitar el correo de voz  |Transcripción de correo de voz  |
>|---------|---------|---------|---------|
>|Emily Braun|En línea|Sí|Habilitado|
>|Lidia Holloway|En línea|Sí|Habilitado|
>|Pradeep Gupta|Local|Sí|Habilitado|
>|Marcel Beauchamp|Local|Sí|Deshabilitado|
>|Rachelle Cormier|En línea|Sí|Deshabilitado|
>|Isabell Potvin|Local|Sí|Deshabilitado|

## <a name="calling-identity"></a>Identidad de llamada

De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificador de llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada. En algunos casos, existen requisitos empresariales legítimos para ocultar el identificador de llamada con el fin de proteger la identidad de la persona que llama usando en su lugar el número de la línea principal de la oficina (normalmente se trata de un número de servicio configurado para ser atendido con un [operador automático](https://support.office.com/article/What-are-Phone-System-auto-attendants-ab9f05a2-22cb-4692-a585-27f82d1b37c7)) o bloqueando la presentación del identificador de llamada.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si la manipulación del identificador de llamada es necesaria para la implementación de Planes de llamada.</li><li>Si corresponde, decida qué tipos de manipulación del identificador de llamada se implementarán (enmascaramiento con un número de servicio o anonimia).</li><li>Si corresponde, decida qué usuarios requieren la manipulación del identificador de llamada y el tipo de manipulación que se asignará a cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Documente los usuarios a los que se asignará la manipulación del identificador de llamada y el tipo de manipulación aplicable a cada usuario.</li></ul>|

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla de documentación de los detalles sobre el enmascaramiento del identificador de llamada:
>|Usuario  |Habilitar el enmascaramiento del identificador de llamada en llamadas salientes  |Tipo de enmascaramiento del identificador de llamada  |Permitir la invalidación por parte del usuario  | Habilitar el enmascaramiento del identificador de llamada en llamadas entrantes  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|No|N/D|Sí|No|
>|Lidia Holloway|Sí|Número de servicio (OrgAA, +44 20 7946 0000)|No|Sí|
>|Pradeep Gupta|No|N/D|Sí|No|
>|Marcel Beauchamp|Sí|Número de servicio (OrgAA, TBA)|No|Sí|
>|Rachelle Cormier|Sí|Anonimizar|Sí|No|
>|Isabell Potvin|Sí|Número de servicio (OrgAA, TBA)|No|Sí|

## <a name="dial-plans"></a>Planes de marcado

Un [plan de marcado](https://support.office.com/article/What-are-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) en la característica de Sistema telefónico de Office 365 es un conjunto de reglas de normalización con las que los números de teléfono que se marcan se traducen a un formato alternativo (normalmente, el formato [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) para poder autorizar las llamadas y enrutarlas. 

Con un plan de marcado, los usuarios pueden marcar números de teléfono de la forma habitual, como, por ejemplo, omitiendo el código de área para las llamadas locales, omitiendo el prefijo internacional para las llamadas nacionales o incluso usando una marcación de dígitos breve cuando se realizan llamadas telefónicas.

Dentro de la característica de Sistema telefónico de Office 365, existen dos tipos de planes de marcado:

-   **Plan de marcado de servicio**. Es el plan de marcado predeterminado y se aplica a los usuarios en función de la ubicación de uso de Office 365. No se puede modificar.
-   **Plan de marcado de inquilino**. Este plan de marcado se puede personalizar dentro de un inquilino y se puede volver a dividir en dos tipos:
    -   **Plan de marcado de inquilino global:** el plan de marcado se aplica a todos los usuarios dentro del inquilino.
    -   **Plan de marcado de usuario de inquilino:** el plan se aplica únicamente a determinados usuarios.

> [!NOTE]
> Consulte [¿Qué son los planes de marcado?](https://support.office.com/article/What-are-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) para obtener más información y ejemplos.

El plan de marcado efectivo que se asigna a los usuarios es la combinación del plan de marcado de servicio (basado en la ubicación de uso de Office 365 del usuario) y el plan de marcado de inquilino (ya sea el de inquilino global o el de usuario de inquilino).

![La tabla muestra tres combinaciones de planes de marcado de inquilino y servicio.](media/audio_conferencing_image8.png)

Hay un máximo de 25 reglas de normalización en cada plan de marcado de inquilino y, por lo tanto, hay que evitar duplicar las reglas de normalización que ya están disponibles como parte del plan de marcado de servicio.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si su organización necesita planes de marcado personalizados (requisitos empresariales, requisitos de adopción, etc.).</li><li>En caso de necesitarlos, decida qué ámbito del plan de marcado de inquilino (inquilino global o usuario de inquilino) se ajusta a los requisitos de los planes de marcado personalizados.</li><li>En caso necesario, decida los planes de marcado de inquilino que se van a crear como soporte para las oficinas o ubicaciones de usuario en las que se va a implementar Planes de llamada.</li><li>En caso necesario, decida qué usuario necesita un plan de marcado personalizado y qué plan de marcado de inquilino se va a asignar a cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Siguientes pasos|<ul><li>Documente qué planes de marcado personalizados y reglas de normalización asociadas se van a configurar como parte de la implementación de Planes de llamada.</li><li>Documente a qué usuarios se les va a asignar un plan de marcado personalizado y qué plan de marcado de inquilino se va a asignar a cada usuario.</li></ul>|

> [!TIP]
> Si es aplicable a su proyecto, puede usar la siguiente plantilla para documentar las configuraciones de planes de marcado de inquilino:
>|Nombre de plan de marcado de inquilino<br>Descripción  |Nombre de reglas de normalización<br>_Descripción_  |Patrón<br>Traducción<br>IsInternalExtension  |
>|---------|---------|---------|
>|**FR-Paris-Issy-39qdPR**<br>_Plan de marcado de 39 quai du Président Roosevelt Issy-les-Moulineaux, Francia_|**FR-39qdPR-Internal**<br>_Número interno (x7000 – x7999) para 39 quai du Président Roosevelt office, Issy-les-Moulineaux, Francia_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_Normalización de número gratuito para Francia_|^0?(80\d{7})\d*$<br>+33$1<br>False|
>||**FR-Service**<br>_Normalización de número de servicio para Francia_|^(1\d{1,2}\|11[68]\d{3}\|10\d{2}\|3\d{3})$<br>1 $<br>False|

<br>
> [!TIP]
> La plantilla de ejemplo siguiente se puede utilizar para documentar las asignaciones de planes de marcado de su proyecto:
>|Usuario  |Oficina  |Tipo de plan de marcado  |Nombre de plan de marcado  |
>|---------|---------|---------|---------|
>|Emily Braun|32 London Bridge Street|Plan de marcado de servicio|N/D|
>|Lidia Holloway|32 London Bridge Street|Plan de marcado de servicio|N/D|
>|Pradeep Gupta|32 London Bridge Street|Plan de marcado de servicio|N/D|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-39qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-39qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-39qdPR|

## <a name="document-technical-implementation-plan"></a>Documentar el plan técnico de implementación

Utilice los puntos de decisión anteriores como referencia para documentar el plan de implementación técnico.
Este plan de implementación técnica proporcionará al equipo del proyecto (que puede incluir FastTrack o un socio de implementación) la información que le permitirá ejecutar la incorporación de los recursos técnicos necesarios para la implementación de Sistema telefónico con Planes de llamada.

En general, un plan de implementación técnico contendrá las siguientes secciones principales:

-   Lista de habilitación del sitio de Sistema telefónico con Planes de llamada

-   Asignación de licencias a usuarios de Sistema telefónico con Planes de llamada

-   Números de planificación de Créditos de comunicaciones

-   Adquisición de números de teléfono, número de teléfono y detalles de las ubicaciones de emergencia

-   Detalles de la configuración del correo de voz

-   Detalles de la configuración del enmascaramiento del identificador de llamada

-   Planes de marcado de inquilino

-   Asignaciones de planes de marcado

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

[Configurar Planes de llamada](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[Guía de inicio rápido: Configurar Planes de llamada en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/configuring-teams-calling-quickstartguide)

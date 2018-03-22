---
title: Empresa plan de pruebas para el sistema de teléfono con planes de llamada en Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Validar que se cumplen las expectativas de su organización a través de sistema de teléfono de prueba en equipos características, funcionalidad y facilidad de uso.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b07aa459f5512c30967efe65d011d6911b6f4967
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
<a name="define-and-document-your-phone-system-with-calling-plans-in-teams-test-plan-for-enterprises"></a>Defina y documente su sistema telefónico con planes de llamada en el plan de pruebas de equipos para empresas 
============================================================================================

Una vez definido y documentado su sistema telefónico con planes de llamada en el éxito del negocio de los equipos y los planes de implementación técnica como parte de la fase de previsión, el paso siguiente es validar que se cumplan las expectativas y requisitos de su organización a través de características, funcionalidad y facilidad de uso. Debe realizar este paso de validación antes de implementar una implementación piloto o final en el entorno de producción.

Puede aprovechar el plan de éxito del negocio definidos durante la fase de previsión para servir como base para determinar las actividades, las expectativas, casos de prueba de características y funcionalidades y alcance general a evaluar durante la fase de pruebas.

<a name="identify-testing-support-stakeholders"></a>Identificar a participantes pruebas de compatibilidad
-------------------------------------

Cuando se prepare para evaluar el sistema de teléfono con planes de llamar a funciones, cree una matriz de los participantes de soporte pruebas para identificar las funciones necesarias para admitir la fase de pruebas.

> [!TIP]
> Como rellenar los equipos de pruebas de la matriz de soporte de los participantes, podría ver que algunas funciones son las mismas que se identifican durante la fase de previsión, pero con las descripciones de rol inclinadas hacia pruebas. Debe identificar las funciones adicionales, dependiendo de las necesidades exclusivas de los escenarios de pruebas.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Equipos de pruebas de la matriz de soporte de los participantes

> [!TIP]

> A continuación es un ejemplo de una plantilla de los participantes soporte pruebas que puede utilizar para documentar qué participantes que se requiere para soportar la fase de pruebas.

| Rol                          | Descripción de la función                                                                                                                                                                          | Recurso asignado, información de contacto y ubicación |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Pruebas de patrocinadores ejecutivos  | <ul><li>Asegúrese de características de los equipos cumplen las necesidades de negocio; los patrocinadores ejecutivos están habituados en los resultados clave del negocio y casos de uso con prioridad.</li><li>Servir como última autoridad y asumir la responsabilidad de característica equipos pruebas de objetivos.</li><li>Ayudar a resolver problemas comunicados por el jefe de pruebas.</li><li>Patrocinador de comunicación dentro de la empresa sobre las pruebas de objetivos.</li><li>Ser responsable de la toma de decisiones estratégicas clave.</li><li>Ser responsable de garantizar la disponibilidad de los recursos necesarios y presupuesto para apoyar los esfuerzos de pruebas.</li><li>Unidad de conciencia y comprar para la campaña de pruebas con otras partes interesadas.</li><li>Servir como el patrocinador de pruebas durante la fase de evaluación de prueba.</li></ul>                                                 | TBD                                                  |
| Miembros del Comité directivo    | <ul><li>Mantener el interés en y proporcionar una guía para la dirección general del sistema de teléfono con planes de llamar a la implementación del servicio.<li>Ayudar a promocionando perspectiva estratégica mediante el impulso de comprar en toda la organización.</li></ul>                                                                        | TBD                                                  |
| Responsable de proyecto                  |<ul><li> Gestionar y liderar el equipo de proyecto.</li><li>Coordinar los socios y los equipos de trabajo en el proyecto.</li><li>Ser responsable de crear y planes de administración del proyecto para cumplir los resultados trimestrales de clave.</li><li>Resolver problemas de funciones cruzadas.</li><li>Proporcionan actualizaciones regulares para los patrocinadores del proyecto.</li><li>Incorporar aprendizajes de experiencia de usuario clave identificados en los resultados de las pruebas en el plan de adopción global del usuario.</li><li>Conducir el negocio mensual y las revisiones operativas, contribuyen a revisiones de negocios trimestral.</li></ul>                                                                                                                                                         | TBD                                                  |
| Arquitecto/responsable de colaboración  | <ul><li>Ser responsable de la ejecución de la estrategia de colaboración definida por los ejecutivos de la empresa.</li><li>Analizar y elegir los productos de colaboración de la empresa que satisfagan los objetivos de negocio.</li><li>Ser responsable del diseño de las operaciones de los productos de colaboración.</li><li>Definir los modelos de operación y soporte técnico.</li><li>Contribuir a revisiones de negocios mensuales y trimestrales.</li></ul>                                                                                                 | TBD                                                  |
| Jefe de proyecto               | <ul><li>Desarrollar y mantener el plan del proyecto.</li><li>Administrar entregas en consonancia con el plan del proyecto y el presupuesto del proyecto.</li><li>Registrar y administrar los problemas del proyecto, incluidas las extensiones.</li><li>Realizar llamadas diaria semanales.</li><li>Póngase en contacto con y proporcionar actualizaciones a los patrocinadores ejecutivos del proyecto.</li><li>Trabajar con equipos de comunicación y administración de cambios internos para actualizar el cambio de enfoque y comunicación planes de gestión según sea necesario.</li></ul>                                                                                                                                                   | TBD                                                  |
| Responsable de redes                  | <ul><li>Proporcionar la entrada en el diseño de la red durante la fase de descubrimiento.</li><li>Participar en el diseño durante los talleres de la fase de previsión.</li><li>Coordinar el trabajo del equipo de la red durante la ejecución del proyecto.</li></ul>                                                                                                                               | TBD                                                  |
| Responsable de seguridad                 | <ul><li>Proporcionar la entrada en el diseño de seguridad y procesos durante la fase de descubrimiento.</li><li>Participar en el diseño durante los talleres de la fase de previsión.</li><li>Coordinar el trabajo del equipo de seguridad durante la ejecución del proyecto.</li></ul>                                                                                                                | TBD                                                  |
| Responsable de telefonía                | <ul><li>Proporcionar la entrada en el diseño de telefonía durante la fase de descubrimiento.</li><li>Participar en el diseño durante los talleres de la fase de previsión.</li><li>Coordinar el trabajo del equipo de telefonía durante la ejecución del proyecto.</li></ul>                                                                                                                           | TBD                                                  |
| Responsable de escritorio                  | <ul><li>Proporcionar la entrada de los clientes y el proceso de actualización durante la fase de descubrimiento.</li><li>Participar en el diseño durante los talleres de la fase de previsión.</li><li>Coordinar el trabajo del equipo de escritorio durante la ejecución del proyecto.</li></ul>                                                                                                              | TBD                                                  |
| Representantes de la unidad de negocio | <ul><li>Contribuir a guías de adopción basadas en usuarios y materiales.</li><li>Contribuyen a y revisar los casos de uso de negocio.</li></ul>                                                                                                                                   | TBD                                                  |
| Administradores de TI                     | <ul><li>Ayudar con la planeación de pruebas y ejecución (esta función es para los profesionales de TI).                                                                                                                       | TBD                                                  |
| Propietario del servicio                 | <ul><li>Ser responsable de la operación del sistema de teléfono con el servicio llamando a los planes, todo.</li><li>Servir como propietario del sistema de teléfono con el servicio llamando a los planes.</li></ul>                                                                                                               | TBD                                                  |
| Director de prueba             | <ul><li>Definir el plan de pruebas, incluidas las actividades, las dependencias, entorno, objetivos, estrategia, recursos (ambientales y humanos) y la escala de tiempo requerido para la compatibilidad con la fase de pruebas.</li><li>Coordinar la preparación para las dependencias del plan de prueba y entrega.</li><li>Alinear con la prioridad de derecho para la resolución del defecto.</li><li>Servir como el path de escalamiento para los problemas de pruebas que se presentan.</li><li>Comunicar y notificar el estado del plan de pruebas con equipos internos y los participantes designados.</li><li>Documentar y presentar los resultados de la prueba final.</li></ul> | TBD                                                  |
| Sistema telefónico con Tester planes de llamada     | <ul><li>Revisar el plan de pruebas para comprender pruebas requisitos, objetivos, línea de tiempo, resolución de problemas y casos de prueba para ejecutarse.</li><li>Revisar y desarrollar casos de prueba compatible con sistema de teléfono con los requisitos de aceptación y funcionalidad llamando a los planes.</li><li>Ejecutar casos de prueba y resultados de la prueba.</li><li>Documentar los defectos que puedan surgir y ellos convertirse en el jefe de pruebas para la asignación de prioridades y resolución.</li><li>Prueba de regresiones para cerrar defectos una vez confirmado el defecto de resolución.</li></ul>                                                                | TBD                                                  |
| Herramienta de comprobación de red                | <ul><li>Revisar el plan de pruebas para comprender pruebas requisitos, objetivos, línea de tiempo, resolución de problemas y casos de prueba para ejecutarse.</li><li>Revise los casos de prueba compatible con requerimientos de performance y aceptación de la preparación de red.</li><li>Ejecutar pruebas relacionadas con la preparación de la red, incluida la conectividad de red y validación de rendimiento, validación de QoS y validación de la configuración de túnel dividido.</li><li>Completó la validación de ancho de banda para sitios de ámbito utilizando planificador de red a través de MyAdvisor.</li><li>Documentar los resultados de las pruebas de preparación de red.</li><li>Documentar los defectos que puedan surgir y ellos convertirse en el jefe de pruebas para la asignación de prioridades y resolución.</li><li>Prueba de regresiones para cerrar defectos una vez confirmado el defecto de resolución.</li></ul>                                                                | TBD                                                  |
| Herramienta de comprobación de seguridad               | <ul><li>Revisar el plan de pruebas para comprender pruebas requisitos, objetivos, línea de tiempo, resolución de problemas y casos de prueba para ejecutarse.</li><li>Revisar y desarrollar casos de prueba de compatibilidad con los requisitos de aceptación de seguridad.</li><li>Ejecutar pruebas relacionadas a la aceptación de seguridad para casos de prueba.</li><li>Aceptación de seguridad documento resultados de las pruebas.</li><li>Documentar los defectos que puedan surgir y ellos convertirse en el jefe de pruebas para la asignación de prioridades y resolución.</li><li>Prueba de regresiones para cerrar defectos una vez confirmado el defecto de resolución.</li></ul>                                                                | TBD                                                  |
| Herramienta de comprobación de telefonía              | <ul><li>Revisar el plan de pruebas para comprender pruebas requisitos, objetivos, línea de tiempo, resolución de problemas y casos de prueba para ejecutarse.</li><li>Revise los casos de prueba auxiliares número trasladar funcionalidad y aceptación requerimientos de servicio.</li><li>Ejecutar pruebas relacionadas con el servicio número trasladar, incluido el puerto de servicio del número a Office 365.</li><li>Ejecutar casos de prueba y documentar los resultados de caso de prueba.</li><li>Documentar los defectos que puedan surgir y ellos convertirse en el jefe de pruebas para la asignación de prioridades y resolución.</li><li>Prueba de regresiones para cerrar defectos una vez confirmado el defecto de resolución.</li></ul>                                                                | TBD                                                  |
| Prueba de administración de planes de sistema de teléfono con llamada | <ul><li>Revisar el plan de pruebas para comprender pruebas requisitos, objetivos, línea de tiempo, resolución de problemas y casos de prueba para ejecutarse.</li><li>Revisar y desarrollar admiten sistema telefónico con una llamada a los planes de aceptación y funcionalidad requisitos de administración de casos de prueba.</li> <li>Ejecutar casos de prueba y documentar los resultados de caso de prueba.</li><li>Documentar los defectos que puedan surgir y ellos convertirse en el jefe de pruebas para la asignación de prioridades y resolución.</li><li>Prueba de regresiones para cerrar defectos una vez confirmado el defecto de resolución.</li></ul>                                                                | TBD                                                  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir qué funciones de apoyo y los participantes pruebas necesita para probar el sistema de teléfono con planes de llamar a funciones en su entorno.</li><li>Decidir los recursos que se asignará para las funciones de soporte y los participantes pruebas que ha identificado.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar las funciones de soporte y los participantes pruebas necesarias en la matriz de los participantes de admitir pruebas.</li><li>Documentar la información de contacto y detalles de ubicación para cada recurso que se indican en la matriz de los participantes de soporte de pruebas.
</table>


<a name="define-phone-system-with-calling-plans-feature-requirements"></a>Definir el sistema telefónico con requisitos de planes de llamada 
------------------------------------------------------------

Como parte de la definición de sistema de teléfono con planes de llamar a los requisitos de características para los usuarios en el ámbito, uno de los primeros pasos que debe haber completado durante la fase de previsión fue el [Análisis del rol](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#assess-environment-and-evaluate-adoption-readiness), donde se define el sistema de teléfono con planes de llamada roles y escenarios.
Con esta referencia identificada, el siguiente paso es evaluar el plan público de equipos más reciente para determinar:

-   Qué sistema de teléfono con planes de llamada a funciones podrá implementar para los usuarios en el ámbito.

-   Sistema telefónico de usuario esperados con planes de llamar a los requisitos de funcionalidad, dado su actual Skype para el entorno de implementación de negocios, Exchange y SharePoint.

-   Si puede confirmar que sistema telefónico con planes de llamada a funciones se describe en la última guía pública cumplen su usuario, funcionalidad y requisitos de ámbito en la escala de tiempo de la implementación

> [!TIP]
> La guía básica de los equipos más reciente para identificar sistema telefónico con planes de llamar a funciones en el ámbito de la implementación puede encontrarse en <https://aka.ms/skype2teamsroadmap>.

Ahora que se ha definido el sistema de teléfono con las características y planes de llamar a la persona, los siguientes criterios para la evaluación será la experiencia de interoperabilidad con los equipos. Para obtener información adicional acerca de la experiencia de interoperabilidad junto con opciones de configuración disponibles, consulte [equipos de Microsoft y Skype para la interoperabilidad de negocio](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).

#### <a name="phone-system-with-calling-plans-feature-definition"></a>Sistema telefónico con planes de llamar a la definición de función

> [!TIP]
> A continuación es un ejemplo de un sistema de teléfono con la plantilla de definición de planes de llamada puede utilizar para documentar el sistema de teléfono con las características de grupo de administración y usuario llamando a planes a evaluarse.


| Nivel empresarial   | Reuniones de colaboración    | Plataforma y dispositivos   | Profesionales de TI  | Grupo de negocio adicionales, específicos del sitio  | Mediante la guía básica de los equipos más reciente que se cumplen los requisitos |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Características del sistema de llamada de teléfono:<ul><li>Transferencia ciega</li><li>Bloqueo de llamadas</li><li>Desvío de llamada</li><li>Identificador de Masking</li><li>Soporte de E911</li><li>Marcado de extensión</li><li>Contención de llamada</li><li>Control de llamada múltiple</li><li>Llamadas simultáneas</li><li>Correo de voz de Azure</li></ul></li><li>Compatibilidad de planes de llamada</li></ul> |<ul><li>Skype para empresas-a-equipos de llamada</li></ul> |<ul><li> Windows, reuniones con los clientes los equipos Mac cuentan con soporte</li><li>Característica de las reuniones del explorador equipos cliente soporte para:<ul><li>Cromo</li><li>Microsoft Edge</li></ul></li><li>iOS y Android equipos cliente de compatibilidad de la característica de reuniones</li><li>Soporte de TTY</li></ul> | <ul><li>Portal diagnóstico de calidad de llamada</li><li>Plan de marcado de inquilinos</li><li>Directivas de identificador de inquilinos</li><li>Habilitar análisis de calidad de llamada (CQD)</li></ul> | <ul><li>Validar equipos de características basadas en imagen corporativa portátil de reunión</li><li>Compatibilidad con idiomas específicos</li><li>Configuración de GPO que se aplican para un escenario de usuario determinado o sitio específico</li></ul> | Sí  |




#### <a name="phone-system-with-calling-plans-user-functionality-definition"></a>Sistema telefónico con planes de llamar a la definición de funcionalidad de usuario

> [!TIP]
> A continuación se basa un ejemplo de una plantilla de funciones de usuario que puede utilizar para documentar la experiencia de usuario en el sistema de teléfono con planes de llamar a funciones en evaluarse.


| Experiencia de Exchange                          | Experiencia de SharePoint                            | Experiencia de directiva de interoperabilidad de los equipos |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Crear equipos (creación de grupo de Office habilitado)</li><li>Unirse a equipos</li><li>Crear canales</li><li>Crear y ver reuniones</li><li>Modificar la imagen de perfil de usuario</li><li>Agregar y configurar conectores</li><li>Agregar y configurar fichas</li><li>Agregar y configurar bots</li></ul> | <ul><li>Almacenar y compartir archivos dentro de las conversaciones de los equipos</li><li>Almacenar y compartir y archivos dentro de las charlas privadas (basados en OneDrive)</li></ul> | <ul><li>ChatDefaultClient: valor predeterminado</li><li>CallingDefaultClient: valor predeterminado</li></ul>      |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li> Decidir qué sistema de teléfono con planes de llamar a funciones de categoría podrá implementar en su entorno.</li><li>Identificar el sistema de teléfono del usuario con planes de llamar a los requisitos de funcionalidad dados su actual Skype para el entorno de implementación de negocios, Exchange y SharePoint.</li><li>Decidir qué experiencia de interoperabilidad de los equipos usted la implementará.</li><li>Revisar el plan público de equipos más reciente y decidir si las capacidades actuales de carga de trabajo cumplen la escala de tiempo de implementación.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documento el sistema telefónico con planes de llamar a funciones de categoría deben para admitir el sistema de teléfono con una llamada a los planes de implementación.</li><li>Documento sistema de teléfono del usuario con planes de llamar a funciones y requisitos de interoperabilidad dado su actual Skype para el entorno de implementación de negocios, Exchange y SharePoint.</li><li>Si el plan público de equipos más reciente que representa el sistema de teléfono con capacidades de planes de llamada satisface las necesidades de negocio y los requisitos de sincronización de la implementación del documento.</li></ul></td></tr>
</table>

<a name="define-and-document-your-phone-system-with-calling-plans-test-plan"></a>Defina y documente el sistema de teléfono llamando a planes plan de prueba
------------------------------------------------------------------

Una vez definidos el sistema telefónico con planes de llamar a funciones en el ámbito, el siguiente paso es crear el plan de pruebas. En un nivel alto, el plan de pruebas abarca la estrategia de pruebas y la metodología que se utilizará para apoyar la validación de la característica en el proceso de pruebas.

En un nivel alto, el plan de pruebas debe incluir:

-   **Pruebas de ámbito:** Resume las áreas de enfoque (objetivos, escenarios y objetivos) se evalúen como parte de la fase de pruebas

-   **Casos de prueba:** El conjunto de casos de prueba para validar para el sistema de teléfono con una llamada a los planes de características en el ámbito

-   **Recursos de pruebas:** Una matriz de recursos necesarios para apoyar el esfuerzo de pruebas desde un punto de vista ambiental, técnica y personal

-   **El plan de pruebas (timeline):** Representa al probar comenzará, cuánto tiempo es probable que la última y, cuando se espera que finalice la fase de pruebas

-   **Defecto, corrección y reporting:** Instrucciones de cómo deben notificarse problemas con las pruebas, realiza el seguimiento y evaluar

-   **Defecto triage y escalamiento:** Esquema de cómo y cuándo se debe iniciar un escalamiento de defecto

-   **Criterios de salida y la suspensión de pruebas:** Criterios de esquematización de orientación para ambos lograr cerrar la sesión para salir de la fase de pruebas o pruebas de pausa hasta que se resuelvan los defectos con prioridad

-   **Probar productos (deliverables):** Resumen de que los resultados se ser desarrollados y ofrecidos para admitir la aceptación que cierre la sesión y salir del proceso de prueba

> [!TIP]
>   Metodología de pruebas puede que ya exista en la organización, pero las instrucciones a continuación reflejan las mejores prácticas que pueden incluirse o aprovechadas por separado para las características de los equipos de pruebas en su entorno.

En las secciones que siguen se encontrará orientación adicional prescrito ayudará a decisiones específicas, plantillas y temas para tener en cuenta a medida que complete el plan de prueba.

### <a name="define-and-document-testing-scope"></a>Definir y documentar el ámbito de las pruebas

Mientras trabaja para desarrollar su plan de pruebas, debe definir por adelantado, el ámbito de las pruebas resaltando la carga de trabajo y lista de características que se va a evaluar.

El ámbito para evaluar correctamente el sistema telefónico con planes de llamada a funciones normalmente incluye:

-   Sistema de teléfono con una llamada a los planes de preparación del sitio

-   Sistema telefónico con planes de llamar a la experiencia del usuario

-   Sistema de teléfono con una llamada a los planes de administración

#### <a name="phone-system-with-calling-plans-testing-scope"></a>Sistema de teléfono con una llamada a planes de pruebas de ámbito

> [!TIP]
>   A continuación es un ejemplo de plantilla de ámbito de prueba que puede utilizar para documentar el sistema de teléfono con las características de grupo de administración y usuario llamando a planes a evaluarse.

| Sistema de teléfono con una llamada a los planes de preparación del sitio                                                                                                                                                                                    | Sistema telefónico con planes de llamar a la experiencia del usuario                                                                                                                                                                                         | Sistema telefónico con experiencia en planes de llamar a la administración                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>Red de ancho de banda de planificador planificación (vía MyAdvisor)<li></li>Validación de conectividad y performance de la red (a través de Skype para la herramienta de evaluación de red empresarial)<li></li>Calidad de validación del servicio (QoS)<li></li>Validación de división túnel de acceso remoto</li></ul>|<ul><li>Características de PBX<li></li>PSTN llamada (nacionales e internacionales)<li></li> Efectuar y recibir llamadas PSTN<li></li>Correo de voz de Azure<li></li>E911<li></li>Plan de marcado de inquilinos<li></li>Enmascaramiento de identificador de inquilinos <li></li>Características de control de llamada avanzada (por ejemplo, llamadas, reenvío de llamadas simultáneas)</li></ul> |<ul><li>Asignación de licencias</li><li>Número de suscriptor trasladar a Office 365</li><li>Sistema de teléfono con los planes de llamar a informes</li><li>Calidad de las llamadas reporting (CQD)</li></ul> |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir el sistema telefónico con llamar a planes de pruebas ámbito mediante la identificación de características para ser evaluados por área de enfoque.</li><li>Decidir los objetivos adicionales y los objetivos de la evaluación.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documente el sistema de teléfono con planes de llamar a funciones que evalúa el área de foco.</li><li>Documentar objetivos adicionales y los objetivos para la evaluación.</li></ul></td></tr>
</table>

### <a name="define-and-document-phone-system-with-calling-plans-test-cases"></a>Defina y documente el sistema telefónico con planes de llamar a casos de prueba

Una vez definidos el sistema de teléfono con planes de llamar a funciones, la implementación del cliente y escenarios en paralelo con Skype para empresa (si procede), el siguiente paso es formular los casos de prueba necesarios para evaluar el sistema de teléfono con planes de llamar a funciones de ámbito de aplicación. A un alto nivel, casos de prueba normalmente están agrupados por área de enfoque e incluyen:

-   **Título del caso de prueba:** Área de enfoque de la función de la prueba está evaluando (por ejemplo, el sistema telefónico con planes de llamada)

-   **Descripción del caso de prueba:** Resumen de los objetivos de las funciones de prueba que se está evaluadas la esquematización

-   **Instrucciones de caso de prueba:** Pasos a seguir para ejecutar correctamente el caso de prueba se realiza

-   **Entorno necesarios (requisitos previos):** Instrucciones de instalación necesarias para ejecutar correctamente la prueba

-   **Recurso requerido:** Recursos de personal necesitan para una evaluación adecuada y la ejecución de la prueba

-   **Resultados esperados:** El resultado que esperaba después de la prueba se ha completado correctamente

> [!NOTE]
>   Dado que el enfoque y el nivel de detalle necesario para la creación de casos de prueba pueden variar dentro de su organización, es recomendable seguir un método que permite un nivel de detalle adecuado pero que equilibre minuciosidad con practicidad, para admitir la prueba general facilidad de uso.

> [!TIP]
>   Para ayudar con la creación de casos de prueba como punto de partida, consulte la lista de instrucciones del usuario de sistema de teléfono disponible en [las reuniones de los equipos y llamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

#### <a name="phone-system-with-calling-plans-test-case"></a>Sistema de teléfono con una llamada a los planes de caso de prueba

> [!TIP]
>   A continuación es un ejemplo de plantilla de caso de prueba que puede utilizar para documentar el sistema de teléfono con las características de grupo de administración y usuario llamando a planes a evaluarse.

Sistema telefónico con validación de planes de llamada

| Identificador del caso de prueba | Título del caso de prueba               | Descripción del caso de prueba                                                  | Entorno necesario para la ejecución del caso de prueba                                               | Pasos necesarios para la ejecución del caso de prueba                                                                                                                                                          | Probar el recurso necesario              |
|--------------|-------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| 1            | Colocar una llamada saliente de PSTN | Compruebe que puede realizar una llamada de voz externo a un número de 10 dígitos. |<ul><li>Instalado el cliente de los equipos.</li><li>Usuario habilitado con las siguientes licencias de Office 365 asignadas:<ul><li>Office Enterprise E5 con sistema de teléfonos, equipos de Microsoft y planes de llamada nacionales e internacionales</li><li>Office Enterprise E3 con sistema de teléfonos, equipos de Microsoft y planes de llamada nacionales e internacionales</li></ul></li></ul> | <ol><li>Iniciar sesión en el cliente de los equipos.</li><li>Seleccione el teclado de marcado y especifique un número de 10 dígitos a marcar.</li><li>Compruebe que el número marcado está normalizado correctamente y se establece la llamada PSTN externa.</li></ol>    | Sistema telefónico con Tester planes de llamada |


> [!TIP]
>   Para obtener orientación adicional en la facilitación de caso de prueba individual y creación de plan global para evaluar el sistema de teléfono con planes de llamar a funciones de la organización, revise el [Plan de pruebas de sistema de teléfono](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) proporcionado por [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir qué sistema de teléfono con una llamada a los planes de administración y funciones de usuario evaluará.</li><li>Decidir qué entorno de prueba es necesario para admitir la ejecución del caso de prueba.</li><li>Decidir los pasos necesarios para la evaluación del caso de prueba.</li><li>Decidir los recursos necesarios para la correcta ejecución de la prueba.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar los casos de prueba para evaluar, basado en la plantilla de caso de prueba proporcionada.</li><li>Incluir la plantilla completa como parte de su plan global de pruebas.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>Defina y documente los recursos de prueba

Para admitir la fase de pruebas, es importante que desarrolle un plan de recursos que se detallan los recursos de personal, el soporte y la tecnología que requerirá. Un componente importante del plan global de pruebas, puede ser que necesite el recurso plan le ayudará a que determinar cualquier dependencia que exista y proporciona una sensación de alto nivel del recurso de soporte.

A un alto nivel, estos recursos normalmente consisten en:

-   **Personas**: los participantes

-   **Tecnología**: inquilinos, licencias, dispositivos

-   **Compatible con**: formación (tarjetas, vídeos), soporte de administración de path de escalamiento definido

#### <a name="testing-resource-requirements"></a>Pruebas de requisitos de recursos

> [!TIP]
>   A continuación es un ejemplo de plantilla de requisito de recurso pruebas que puede utilizar para documentar los distintos tipos de recursos necesarios para la fase de pruebas.


| Tipo de recurso | Recursos necesarios                                           | Descripción del recurso |
|---------------|--------------------------------------------------------------|----------------------|
| Personas        | Los participantes probar probadores de cable                               | TBD                  |
| Tecnología    | Acceso a Office 365 con habilitados los siguientes servicios:<ul><li>Office 365 E5 licencias asignadas</li><li>Plan de llamadas nacionales e internacionales asignada</li></ul>    | TBD                  |
| Asistencia técnica       | Respons administrador prueba soporte técnico de prueba | TBD                  |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir los tipos de recursos (personas, tecnología y soporte) que necesitará para admitir la fase de pruebas.</li><li>Decidir los recursos específicos necesarios para los tipos de recursos que se identificó.</li><li>Decidir si se debe proporcionar más detalle para describir los tipos de recursos que necesita.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar los tipos de recursos (personas, tecnología y soporte) que necesitará para admitir la fase de pruebas.</li><li>Documentar los recursos específicos necesarios para los tipos de recursos que se identificó.</li><li>Si decide que es necesario, documente los detalles adicionales sobre los tipos de recursos que necesita para soportar la fase de pruebas.</li></ul></td></tr>
</table>


### <a name="define-and-document-a-testing-timeline"></a>Definir y documentar una escala de tiempo de prueba

Como parte de la definición del plan de pruebas, crear una escala de tiempo que describe la programación en que espera a completar las actividades de prueba y alcanzar hitos de alto nivel.

En un nivel alto, esto normalmente consta de:

-   **Tarea:** Actividad de alto nivel para completar

-   **Hito:** Objetivo de alto nivel o el progreso que se ha completado

-   **Recurso requerido:** Pruebas de recursos requeridos para soportar la entrega del hito o tarea identificada

-   **Fecha de inicio:** La fecha en que se inició la actividad, hito o tarea

-   **La fecha de finalización:** La fecha en que espera la actividad, hito o tarea se complete por

-   **Propietario:** Recurso asignado que es responsable de garantizar que la actividad, hito o tarea se ha completado en el tiempo, según la fecha de finalización

-   **Estimación:** Número de horas que los recursos asignados prevé tendrá para asegurarse de que la actividad, hito o tarea se ha completado en el tiempo

#### <a name="testing-scheduling-and-timeline-requirements"></a>Requisitos de programación y línea de tiempo de prueba

> [!TIP]
>   A continuación es un ejemplo de una plantilla de requisito pruebas de escala de tiempo que puede utilizar para documentar las fechas previstas para cuando se completará las actividades de pruebas específicas o hitos enviados por.

| Tarea                                                 | Hito       | Fecha de inicio                                                             | Fecha de finalización | Owner | Recursos asignados | Estimación |
|------------------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Informe de prueba                                          | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Horas de TBD  |
| Ejecución del caso de prueba: Sistema de teléfono con planes de llamada | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Horas de TBD  |
| Ejecución del caso de prueba: Preparación de la red               | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Horas de TBD  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir la actividad de la línea de tiempo, hito y las tareas que necesita realizar el seguimiento.</li><li>Decidir qué recursos debe asignar.</li><li>Decida la fecha en que espera realizar.</li><li>Identifique al propietario de la entrega.</li><li>Decidir cuánto tiempo se tardará en completar la actividad, hito o tarea.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar la escala de tiempo de prueba mediante la plantilla proporcionada e incluyen:<ul><li>Actividad de la línea de tiempo, hito y las tareas que debe realizar el seguimiento.</li><li>Recursos que deben asignarse.</li><li>Fecha de finalización anticipada.</li><li>Propietario de la entrega.</li><li>Tiempo necesario para completar la actividad, hito o tarea.</li></ul></li><li>Incluir la plantilla completa como parte de su plan global de pruebas.</li></ul></td></tr>
</table>


### <a name="define-and-document-test-defect-report-criteria"></a>Defina y documente los criterios de informe de defectos de prueba

A medida que ejecutan los casos de prueba dentro de una fase determinada o una secuencia, pueden surgir problemas donde el resultado del caso de prueba que se está ejecutando no es lo que esperaba.

Cuando se producen estos tipos de resultados, deben capturar en un plan de informe y corrección de defectos que se remite el cliente potencial de prueba designado para su revisión, informes y resolución de defectos.

Normalmente, un plan de informe y la corrección de defectos incluye lo siguiente:

-   **Defecto ID:** El número asignado al problema

-   **Identificador del caso de prueba afectado**: el número asignado al caso de prueba que se está evaluando en el momento en que se identificó el defecto

-   **Defecto Descripción:** Resumen del problema

-   **Entorno y pasos para reproducirlo:** Resumen de la configuración de entorno pruebas, junto con los pasos exactos necesarios para reproducir el problema

-   **Gravedad del defecto**: el impacto del problema, que van desde impide que el caso de prueba que apruebe aceptada con un riesgo mínimo. Algunos ejemplos podrían incluir:

-   **Bajo:** El problema tiene poco impacto y no impedirá que el caso de prueba lograr aceptación si se puede resolver el problema más adelante.

-   **Medio:** El problema tiene un impacto sustancial, pero no impedirá que el caso de prueba logro si se puede resolver el problema antes de que finalice la fase de pruebas de aceptación.

-   **Alto:** -el problema tiene impacto crítico en el caso de prueba. El problema se debe resolver antes de que se puede aceptar el caso de prueba.

-   **Estado:** Tiene el problema que se ha resuelto, es abierto, o siendo investigado

-   **Enviado por:** El evaluador que ha presentado el problema

-   **Propietario asignado:** El recurso asignado desde el equipo de pruebas que es responsable de resolver el problema

-   **Los detalles:** Esto puede incluir, pero no se limita a, los registros de cliente, imágenes o vídeo del problema.

Como evaluadores ejecutan los casos de prueba descritos en su plan de pruebas, deben completar un plan de informe y corrección de defecto para cualquier problema que surja.
Esto resaltará el impacto potencial que podría obstaculizar o incluso por detener el proceso de evaluación de prueba.

#### <a name="testing-defect-report-and-remediation-plan"></a>Plan de pruebas informe de defectos y corrección

> [!TIP]
>   A continuación es un ejemplo de plantilla de informe de defectos y el Plan de corrección que puede utilizar para documentar los problemas descubiertos durante la fase de pruebas.

| Id. de defecto                                | Identificador del caso de prueba afectado | Descripción del defecto                                                                                 | Entorno /steps para reproducir                                                                                                | Gravedad | Estado | Enviado por | Propietario asignado | Los detalles (logs, capturas de pantalla etc.) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Cuando el usuario entra en una extensión de cuatro dígitos, intenta realizar una llamada saliente, la llamada producirá errores. | En el cliente de los equipos, seleccione el teclado de marcado, escriba una extensión de cuatro dígitos y seleccione el icono del teléfono para intentar realizar la llamada. | Medio   | Cerrado | Louis Lahr   | Lisa gris      | Registro de equipos cliente<br/> Captura de pantalla de equipos cliente     |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir qué niveles de gravedad de criterios defecto asignará para apoyar el esfuerzo de pruebas.</li><li>Decidir qué pruebas defecto reporting criterios que podrá documentar si surgen problemas durante las pruebas.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documente el defecto de pruebas informes criterios requeridos en la plantilla que se proporciona.</li><li>Incluir la plantilla completa como parte de su plan global de pruebas.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Defina y documente los criterios de salida y suspensión

Como parte del proceso de ejecución de plan de prueba general, debe definir los criterios para indicar el punto en el que debe suspender los esfuerzos de pruebas y los requisitos que deben cumplirse para obtener aprobación y salir de la fase de pruebas.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Criterios de suspensión y salir de plan de prueba

> [!TIP]
>   A continuación es un ejemplo de plantilla de criterios de salida y suspensión que puede utilizar en su plan de pruebas para los criterios de documento necesaria para lograr el cierre, salir de la fase de pruebas o suspender las actividades de prueba.

| Prueba de criterios de salida                            | Criterios de suspensión de pruebas                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>Todos los casos de prueba debe lograr una velocidad de paso de TBD %</li><li>Todos los casos de prueba debe haber ejecutado completamente</li><li>En todos los casos de prueba se evalúa, deben cerrarse todos los defectos de gravedad alta</li></ul> | <ul><li>Todos los casos de prueba debe lograr una tasa de error de % TBD</li><li>Deben resolverse todos los defectos identificados como gravedad alta pruebas pueden continuar.</li></ul> |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir suspensión criterios que deben cumplirse si se identifican problemas con las pruebas.</li><li>Decida los criterios de salida que deben cumplirse para obtener aprobación de pruebas aceptación y apoyo de salir de la fase de pruebas pruebas después de todo las actividades están completas.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documente los criterios de salida y suspensión prueba necesarios en las plantillas de prueba y salida proporcionadas.</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>Definir y documentar el proceso de escalamiento de defecto

Largo de la ejecución del plan de pruebas, puede descubrir un problema o identificar un defecto que requiere elevación al recurso derecho de conducción y determinar la resolución necesaria para realizar las pruebas continuar.

Como defectos se identifican con la gravedad adecuado y la prioridad asignada, se crea una matriz de escalamiento y evaluación revisar el proceso de asignación de salida cuando se desencadena una escalada y cómo, cuándo y quién se asignará el defecto a para más revisión y resolución.

Normalmente, un plan de informe y la corrección de defectos incluye lo siguiente:

-   **Defecto ID:** El número asignado al problema

-   **Defecto Descripción:** Resumen del problema

-   **Defecto evaluación de prioridad:** El nivel de prioridad asignado a un defecto de resolución basado en impacto empresarial y defecto de gravedad. Algunos ejemplos:

-   **Bajo:** El problema tiene poco impacto en la prevención de la fase de pruebas de lograr cierre si se puede resolver el problema más adelante.

-   **Medio:** El problema tiene un impacto sustancial en la prevención de la fase de pruebas de lograr sign-off si no se resuelve el problema.

-   **Alta:** El problema tiene un impacto crítico en la prevención de la fase de pruebas de lograr sign-off si no se resuelve el problema.

-   **Propietario del defecto asignado:** El recurso asignado desde el equipo de pruebas que es responsable de resolver el problema

-   **Asigna el punto de extensión de defecto:** El recurso asignado que está en el punto para solucionar el problema de la organización (si es necesario) para la conducción de resolución; basándose en la gravedad del defecto

-   **Estado de defecto:** Tiene el problema que se ha resuelto, es abierto, o siendo investigado

-   **Requiere resolución fecha:** La fecha que se debe resolver el problema por

-   **La fecha de estado:** Se actualizó la fecha que refleja el último estado de tiempo como resultado de una revisión de la clasificación de defectos

#### <a name="test-plan-defect-escalation"></a>Escalamiento de defecto del plan de prueba

> [!TIP]
>   A continuación es un ejemplo de una plantilla de escalamiento de defecto que puede utilizar en parte de su plan de pruebas para documentar el proceso de escalamiento necesario para establecer prioridades y resolver los defectos de pruebas.

| Id. de defecto                                | Descripción del defecto                                                                                 | Evaluación de prioridad de defecto                                           | Propietario de defecto asignado | Punto de extensión defecto asignado | Método de extensión de defecto                                          | Estado de defecto | Resolución necesaria por fecha | Fecha de estado |
|------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1                                        | Cuando el usuario entra en una extensión de cuatro dígitos, intenta realizar una llamada saliente, la llamada producirá errores. | Medio                                                               | Lisa gris             | Louis Lahr                       | Correo electrónico semanal de revisión de evaluación de errores de alta prioridad a los implicados afectados | Abrir          | ASAP                        | 12/1/2018   |



<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir y acordar las prioridades de defecto para apoyar su plan de pruebas.</li><li>Decidir el punto de extensión para cada área de defecto.</li><li>Decidir el escalamiento de defecto y el plan de evaluación de errores para seguir, basándose en su prioridad.</li><li>Decidir los informes de defectos y clasificación del plan de comunicación para el escalamiento.</li><li>Decidir la cadencia de reunión de revisión de evaluación de errores de defecto.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar las prioridades acordado en defecto.</li><li>Documentar el punto de extensión para cada área de foco potencial.</li><li>Documentar el plan de evaluación de errores y de escalamiento de defecto según criterios acordados previamente.</li><li>Documente el defecto de las directrices de informe.</li><li>Programar la serie de reuniones de evaluación de defectos.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-deliverables"></a>Defina y documente los resultados de pruebas

El componente final y la último en la creación de un plan de pruebas consiste en identificar los resultados en términos de entregas específicas que ofrece el plan global de pruebas.

A un alto nivel, estos incluyen normalmente, pero no están limitados a:

-   Plan de pruebas

-   Casos de prueba

-   Informes de defectos

-   Resumen de resultados de la prueba

-   Pruebas de aceptación y aprobación.

#### <a name="test-plan-deliverables"></a>Resultados del plan de pruebas

> [!TIP]
>   A continuación es un ejemplo de una matriz entrega de plan de pruebas que puede utilizar para documentar las entregas que se creará, junto con los recursos necesarios para su revisión, aprobación y cierre.

| Entrega de plan de pruebas                    | Formato de entrega de plan de pruebas | Propietario de la entrega de Test plan                                                                                                      | Revisor de entrega de plan de pruebas | Aprobador de entrega de plan de pruebas | Plan entrega cierre fecha de prueba |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Plan de pruebas                                | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Informes de administración de defecto                | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Pruebas de informes de estado                   | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Resumen de resultados de la prueba                     | Word PPTX                    | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir qué productos deben ser creados y capturados como resultado de cada fase de pruebas. Para cada entrega, decidir sobre su:<ul><li>Formato</li><li>Owner</li><li>Revisor</li><li>Aprobador</li></ul></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar un plan entrega la creación y la entrega matriz de pruebas.</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>Evaluar la preparación de la red
----------------------------

Como elemento crítico de apoyo a la implementación de equipos, preparación de la red es una parte crucial de las pruebas para asegurarse de que la red correctamente está optimizada para la compatibilidad con las comunicaciones de los equipos. Para asegurarse de que está lista para los sitios en el ámbito de la red, son las áreas de focalización listadas en la estrategia de prueba global:

-   Estimación del ancho de banda y la planificación con el planificador de la red (a través de MyAdvisor)

-   Calidad de la validación de la configuración de servicio (QoS)

-   Verificación de conectividad y performance a través de la simulación de tráfico de red

-   Validación de túnel dividido

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Ejecutar planes de red (mediante MyAdvisor) para los sitios y personas en el ámbito

Antes de introducir los servicios de comunicación en tiempo real como los equipos de su entorno, es importante asegurarse de que la red se ha optimizado y correctamente tamaño desde un ExpressRoute de Azure (si procede), internet y ancho de banda WAN perspectiva.

Para ayudar a determinar la cantidad de ancho de banda y nivel de optimización de red necesaria para sitios de admitir su implementación de ámbito, completar la herramienta de [Planificación de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) (mediante MyAdvisor) para validar la preparación de la red de su organización necesita. Para obtener orientación adicional sobre cómo determinar los requisitos de red para equipos a través de los planes de red, consulte MyAdvisor: planificador de la red.

> [!TIP]
>   Para obtener información adicional acerca de la ficha de **recomendaciones** , ejemplos de cómo configurar e interpretar los resultados, consulte el [Resumen de recomendaciones](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp)de planificador de la red.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decidir qué sitios de red en el ámbito de implementación de equipos de servicios.</li><li>Decidir los roles necesarios para las modalidades de equipos en el ámbito.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Complete el planificador de la red (mediante MyAdvisor) de la lista de sitios que están en el ámbito.</li><li>Resultados de validación de red planificador de documento en la plantilla de resultados del plan de prueba proporcionada.</li><li>Validar que ExpressRoute (si procede), internet y ancho de banda WAN que se calculó para sitios de ámbito se alinea con los valores de ancho de banda que están asignados actualmente.</li><li>Para los sitios que no tienen un ancho de banda adecuado, ejecutar planes de escalamiento y corrección para resolver los problemas de ancho de banda.</li><li>Establecer una red de supervisión de la solución para sitios de ámbito para supervisar el uso de ancho de banda y QoS para segmentos WAN, internet y ExpressRoute (si procede).</li><li>Programar una reunión del Comité directivo para revisar los resultados del planificador de la red.</li><li>Presentar resultados al Comité directivo para identificar las áreas que requieren corrección de planificación de ancho de banda.</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>Evaluar la configuración de QoS para sitios de ámbito
---------------------------------------------

Como parte de la validación de preparación para admitir comunicaciones en tiempo real de los equipos de la red, es igualmente importante garantizar que la red haya sido configurada correctamente y se optimizado desde una perspectiva de QoS.

Para obtener orientación adicional acerca de cómo configurar, implementar y validar la preparación de la red QoS para equipos mediante Directiva de grupo, consulte [Habilitación de QoS para equipos](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decida la configuración de QoS a implementarse.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Configurar QoS.</li><li>Ejecutar la validación de QoS tal como se describe en pasos que se indican mediante el "validar a través de GPO" y "Validar mediante analizador de mensaje" secciones anteriores.</li></ul></td></tr>
</table>


### <a name="document-qos-configuration-validation-test-results"></a>Documentar resultados de pruebas de validación de configuración de QoS

Una vez haya realizado pruebas utilizando Directiva de grupo para sitios en el ámbito de la validación de QoS, crear un informe que resume los resultados de las pruebas para presentar durante la revisión final Comité directivo.

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>Sitio A: validación de la configuración de QoS informe resumen de la prueba

> [!TIP]
>   A continuación es un ejemplo que prueba de plantilla de informe de resumen que puede revisar durante la próxima reunión del Comité directivo cuando decida a incorporado sistema telefónico con planes de llamar a los servicios en la fase de prueba piloto.


**Validación de la configuración de QoS a través de GPO y analizador de mensaje**

**Resumen de los resultados**:&nbsp;&nbsp;&nbsp;& #9744; Pasar&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Un error

<table>
<tr><th colspan="2">Aspectos destacados de pruebas </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Pruebas de relieve  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Corrección:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores de elementos identificados </td></tr>
<tr><td>**Bloqueador**: TBD</td><td>**Corrección**: TBD</td></tr>
</table>


> [!TIP]
> Para facilitar la discusión adicional durante la revisión final Comité directivo, puede utilizar la actualizada [matriz de resultados de la prueba](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para documentar y resaltar áreas adicionales que requieren corrección.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar los resultados de la prueba de QoS para garantizar que el tráfico multimedia en tiempo real se está correctamente los equipos marcados y prioridad.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documento QoS los resultados de pruebas en la plantilla de resultado de plan de prueba proporcionada.</li><li>Ejecutar planes de corrección y escalamiento para resolver problemas donde QoS no esté configurado correctamente o no funcionar como se espera para permitir el tráfico de los medios de comunicación de equipos.</li></ul></td></tr><li>Programar una reunión del Comité directivo para revisar el resumen de resultados de prueba.</li><li>Presente prueba resumen de los resultados al Comité directivo para identificar las áreas que requieren corrección.</li>
</table>


<a name="execute-split-tunnel-enablement-validation"></a>Ejecutar la validación de la habilitación de túnel dividido
------------------------------------------

Es común que las empresas hoy en día tiene una o más soluciones para proporcionar acceso remoto, como una red privada virtual o VPN. Estas soluciones permiten conectividad a los activos internos de línea de negocio y aplicaciones de forma segura y fiable.

Aunque las soluciones de acceso remoto pueden funcionar muy bien para dar acceso a algunas aplicaciones, cuando se trata de túnel el tráfico multimedia en tiempo real de los equipos, estas soluciones con frecuencia como resultado una experiencia de usuario menos óptimo para todos los participantes de un audio de equipos escenario de llamada o conferencia.

Para asegurarse de que el tráfico de los equipos multimedia no *recorrer los soluciones de acceso remoto en su entorno* , se requerirá una configuración de túnel dividido.

Para obtener orientación adicional acerca de cómo configurar y validar la preparación de la red de configuración de túnel de división para los equipos, vea Preparación de la [red](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!NOTE]
>   Debido al enorme volumen de las soluciones de acceso remoto disponibles en el mercado, este documento no puede proporcionar detalles específicos del proveedor, directrices generales para qué deben configurarse en soluciones de acceso remoto.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decidir la configuración de túnel dividido para implementar.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Implementar la configuración de túnel dividido.</li><li>Probar y validar la configuración de túnel dividido.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>Resultados de la prueba de validación de documento configuración de túnel dividido

Una vez completada la configuración de túnel dividido pruebas para sitios de ámbito, crear un informe que resume los resultados de las pruebas y presentarlo durante la próxima revisión del Comité de dirección.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>Sitio A: validación de la configuración de túnel dividido informe resumen de la prueba

> [!TIP]
>   A continuación es un ejemplo que prueba de plantilla de informe de resumen que puede revisar durante la próxima reunión del Comité directivo cuando decida a incorporado sistema telefónico con planes de llamar a los servicios en la fase de prueba piloto.

**Validación de la configuración de túnel dividido**

**Resumen de los resultados**:&nbsp;&nbsp;&nbsp;& #9744; Pasar&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Un error

<table>
<tr><th colspan="2">Aspectos destacados de pruebas </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Pruebas de relieve  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Corrección:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores de elementos identificados </td></tr>
<tr><td>**Bloqueador**: TBD</td><td>**Corrección**: TBD</td></tr>
</table>


> [!TIP]
> Para facilitar la discusión adicional durante la revisión final Comité directivo, puede utilizar la actualizada [matriz de resultados de la prueba](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para documentar y resaltar áreas adicionales que requieren corrección.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar los resultados de pruebas de túnel de división para asegurarse de que el tráfico en tiempo real de equipos se excluye de la solución de acceso remoto.</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar los resultados de las pruebas en la plantilla de resultado de plan de pruebas proporcionada conectividad de túnel dividido.</li><li>Ejecutar planes de corrección y escalamiento para resolver problemas donde enrutamiento correcto no exista para la compatibilidad con medios de equipos dentro de una configuración de túnel dividido.</li><li>Programar una reunión del Comité directivo para revisar el resumen de resultados de prueba.</li><li>Presente prueba resumen de los resultados al Comité directivo para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>Ejecutar la validación de conectividad y performance de la red mediante la herramienta de evaluación de la red de Microsoft
-----------------------------------------------------------------------------------------------------------

La herramienta de evaluación de la red de Microsoft realiza pruebas de conectividad y simulación de tráfico por streaming paquetes simulados de audio, para un período predefinido y el número de iteraciones en el sitio más cercano del borde que proporciona conectividad con el servicio de los equipos. Un objetivo de este ensayo es evaluar las métricas de rendimiento de red para la pérdida de paquetes, jitter, latencia de ida y vuelta y porcentaje de pedido de paquetes de cada llamada simulada. Además, la prueba valida que se permite una conectividad adecuada entre interno y elementos a todos los puntos de entrada de borde que soportan conectividad a los servicios de los equipos de la red de borde.

Para obtener instrucciones adicionales sobre cómo confirmar y evaluar la preparación de la red de los equipos de los sitios designados en el ámbito, vea Preparación de la [red](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!TIP]
>   Para completar el análisis de preparación de la red y preparación para sitios de ámbito, designar un cliente potencial para cada sitio que puedan ayudar con los esfuerzos de evaluación de disponibilidad de red.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decidir la evaluación de la red y el perfil de pruebas de conectividad para sitios de ámbito.</li><li>Decidir los requisitos del archivo de configuración de red evaluación para sitios en ámbito.</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Configurar requisitos del archivo de configuración de red evaluación para sitios de ámbito.</li><li>Ejecutar la validación de rendimiento y conectividad de red para los sitios en el ámbito.</li></ul></td></tr>
</table>



### <a name="document-network-connectivity-and-performance-validation-test-results"></a>Documentar resultados de pruebas de validación de rendimiento y conectividad de red

Después de completar todas las pruebas de rendimiento para los sitios en el ámbito y conectividad de red, crear un informe que resume los resultados de las pruebas y presentarlo durante la próxima revisión del Comité de dirección.

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>Sitio A: informe de resumen de performance y conectividad de la red

> [!TIP]
> A continuación es un ejemplo red conectividad y rendimiento resumen de plantilla que puede utilizar durante la próxima revisión del Comité de dirección al determinar la preparación de la red para sitios de ámbito global.

**Ubicación: Seattle [interior wired] cliente Office 365 resultados**

**Resumen de los resultados**:&nbsp;&nbsp;&nbsp;& #9744; Pasar&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Un error 



| Métrica                                                        | Target                                                                                                            | Día de la semana: horario de oficina 9:30 A.M. a 11:00 A.M.                                                                                                                                                                                                                                                                                                 | Día de la semana: horario de oficina 2:30 P.M. a 4:30 P.M. | Día de la semana: después de horas 10:30 P.M. a 12:30 A.M. | Fin de semana: horario 9:30 A.M. a 11:30 AM | Fin de semana: horario 2:30 P.M. a 4:30 P.M. |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| Latencia (unidireccional)                                             | \<50 ms                                                                                                           | 40 ms                                                                                                                                                                                                                                                                                                                                     | 38 ms                                    | 41 ms                                     | 35 ms                                    | 36 ms                                   |
| Latencia (tiempo de ida y vuelta o RTT)                             | \<100 ms                                                                                                          | 81 ms                                                                                                                                                                                                                                                                                                                                     | 77 ms                                    | 80 ms                                     | 72 ms                                    | 70 ms                                   |
| Pérdida de paquetes ráfaga                                             | \<10% durante cualquier intervalo de 200 ms                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | 2%                                       | 2%                                        | 0,2%                                     | 0,1%                                    |
| Pérdida de paquetes                                                   | \<1% durante cualquier intervalo de 15 seg                                                                                   | 0,4%                                                                                                                                                                                                                                                                                                                                      | 0,3%                                     | 0,3%                                      | 0,1%                                     | 0 %                                      |
| Vibración de llegada entre paquetes                                   | \<30 ms durante cualquier intervalo de 15 seg                                                                                | 12 ms                                                                                                                                                                                                                                                                                                                                     | 11 ms                                    | 13 ms                                     | 5 ms                                     | 5 ms                                    |
| Reaprovisionamiento de paquete                                                | \<paquetes de salida de la orden de 0,05%                                                                                      | 0 %                                                                                                                                                                                                                                                                                                                                        | 0 %                                       | 0 %                                        | 0 %                                       | 0 %                                      |



<table>
<tr><th colspan="2">Aspectos destacados de pruebas </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Pruebas de relieve  </th></tr> 
<tr><td>**Problema**: alta latencia</td><td>**Corrección:** Investigue el enrutamiento de paquetes e implementar la ruta ideal.</td></tr>
<tr><td>**Problema**: doble la latencia no es el tiempo de ida y vuelta</td><td>**Corrección:** Investigue un posible problema de configuración de firewall o enrutador. Investigar las rutas de tráfico.</td></tr>
<tr><td>**Problema**: alta pérdida de paquetes </td><td>**Corrección:** A través de los planes de la red, compruebe que se ha asignado suficiente ancho de banda. </td></tr>
<tr><td>**Problema**: elevada vibración </td><td> **Corrección:** Investigue si se utilizan los valores de (DSCP) punto de código de servicios diferenciados correcto. </td></tr>
<tr><td>**Problema**: alta pérdida de paquetes </td><td>**Corrección:** Investigue la pérdida de paquetes. </td></tr>
<tr><td>**Problema**: punto de pedido de paquetes alta </td><td>**Corrección:** Investigue el ancho de banda y la cola de enrutador. </td></tr>
<tr><th colspan="2">Bloqueadores de elementos identificados </td></tr>
<tr><td>**Bloqueador**: TBD</td><td>**Corrección**: TBD</td></tr>
</table>

 


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar la evaluación de la red y los resultados para asegurarse de que cumple los requisitos descritos en el [rendimiento de conectividad de red y calidad Media](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) para el segmento del borde y segmentos de cliente de pruebas de conectividad.</li><li>¿Ha evaluado las capacidades de red para admitir los medios de comunicación en tiempo real para todos los sitios en el ámbito?</li><li> ¿Si la red no ha evaluado correctamente o si se sabe no admite medios de comunicación en tiempo real, deshabilitará vídeo y capacidades de uso compartido de pantalla para reducir la red impactan y mejoran la experiencia de los equipos de los usuarios?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Rendimiento de la red y los resultados de la prueba de conectividad.</li><li>Ejecutar planes de corrección y escalamiento para resolver problemas con sitios donde no hay suficiente ancho de banda, o no se cumplen los requisitos de rendimiento y conectividad de red.</li><li>Programar una reunión del Comité directivo para revisar el resumen de resultados de prueba.</li><li>Presente prueba resumen de los resultados al Comité directivo para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


<a name="execute-subscriber-number-port-validation"></a>Ejecutar la validación puerto del suscriptor
-----------------------------------------

Si necesita transferir números de proporcionar capacidades llamadas entrante y saliente en los sistemas telefónicos con planes de llamar a servicios admitidos por los equipos, debe realizar un puerto parcial para un número de servicio. Esto le ayudará a validar las expectativas, requisitos y escala de tiempo razonable que termine de preparar la implementación del sistema de teléfono con una llamada a los planes de servicios en su entorno de producción.

Para completar un puerto parcial de un número de suscriptor de su actual proveedor de servicios PSTN a equipos, recorra los pasos que se describen a continuación.

#### <a name="step-1"></a>Paso 1

Identificar el número de pruebas que desea trasladar a Office 365 como un usuario puede asignar número (suscriptor) sea atendido a través del sistema de teléfono con una llamada a los planes de servicio en equipos.

> [!IMPORTANT]
>Mientras planea la prueba número de traslado, asegúrese de revisar las pautas más recientes para las solicitudes de traslado número de [Preguntas comunes de número de puerto](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions).

#### <a name="step-2"></a>Paso 2

Identifique y documente toda la información de cuenta (incluido el nombre de la cuenta específica) para el operador actual del número de pruebas que se va trasladar.
Normalmente, encontrará la información que necesitará en la factura o la factura más reciente de su proveedor de servicio actual.

> [!TIP]
>   Puede trasladar o números de teléfono de transferencia dentro de todos los países y regiones; compatible Sin embargo, la manera de enviar una solicitud de pedido de puerto podría diferir según el país o la región donde se proceden de los números de teléfono. Para obtener la lista más reciente de países o regiones admitidas actualmente, consulte [países y la disponibilidad de la región para conferencias de Audio y llamar a los planes](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

>   Para obtener información adicional sobre la transferencia de números de teléfono a teléfono sistema con planes de llamada, junto con posibles restricciones, consulte [transferir números de teléfono para Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) y [gratuito marcando las restricciones dentro de Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Paso 3

Descargue y cree una carta de autorización (LOA) para su país o región que se basa en el "número de servicio" como tipo de traslado número.

>[!NOTE]
>   Porque LOA formatos pueden variar por país, región o tipo de número (que es geográfica versus no geográficos o el número de usuario frente a servicio o número de teléfono gratuito), compruebe que está utilizando la plantilla LOA correcta para su tipo de situación específica. Vea [Descargar carta de autorización (LOA)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) para obtener más información acerca de cómo elegir el LOA o ir directamente a la [página de descarga](https://www.microsoft.com/download/details.aspx?id=49167).

>[!NOTE]
> **Sólo en Estados Unidos**<br/>
>   Porque sólo nos estamos trasladar un número de servicio para esta prueba, asegúrese de seleccionar los campos adecuados en la LOA como se muestra a continuación:

¿ ![Cómo muchos números de teléfono transferirá? Respuesta: yo soy sólo transferencia de algunas de Mis números de mi proveedor actual.] ¿ (media/onboarding-test-plan-image1.png "Cómo muchos números de teléfono transferirá? Respuesta: yo soy sólo transferencia de algunas de Mis números de mi proveedor actual.")

![¿Qué tipo de números de teléfono va a transferir? Respuesta: yo estoy transfiriendo números de teléfono de servicio de voz como para operadores automáticos o puentes de conferencia.] (media/onboarding-test-plan-image2.png "¿Qué tipo de números de teléfono va a transferir? Respuesta: yo estoy transfiriendo números de teléfono de servicio de voz como para operadores automáticos o puentes de conferencia.")

>[!IMPORTANT]
>   Al importar manualmente los números de teléfono utilizando un LOA, asegúrese de que seleccionar el tipo de número de teléfono correcto. Debe enviar pedidos de puerto diferente para cada tipo de número de teléfono que desea transferir.<br/><br/>
>   Porque queremos probar el número de trasladar el proceso utilizando un número de teléfono asociado con el mismo número de facturación telefónica (BTN), debe asegurarse de que el número de teléfono de facturación *no* se incluye con el número de teléfono específico se están trasladando.

#### <a name="step-4"></a>Paso 4

En el portal de administración de inquilinos, vaya a la ficha de **soporte** y crear y enviar una solicitud de servicio. Adjunte el archivo LOA completado para programar el número de teléfono asociado con su actual proveedor de servicios para la migración. Para elegir el método de solicitud de servicio más apropiado para el tamaño de los inquilinos, consulte [enviar manualmente una solicitud de servicio personalizado](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Después de recibe la solicitud de soporte, Microsoft Support seguirá basándose en el método de comunicación que ha elegido y avisarle de estado y los próximos pasos para completar el proceso de traslado de número.

#### <a name="step-5"></a>Paso 5

Cuando se haya confirmado el número como haber sido portado sobre como un nuevo número de suscriptor en Office 365, asignar el número al sistema telefónico con el servicio de llamada a planes visitando el portal de administración de inquilinos \> **Skype para Business Admin Center** \> ** Voz**. En la ficha **Números de teléfono** , asigne al nuevo número de servicio al sistema de teléfono con una llamada a los planes de servicio.

> [!TIP]
>   Aunque esta tarea asigna a un nuevo número de servicio al sistema de teléfono con los planes de llamada, en el momento de escribir este artículo, la administración de esta tarea se completa utilizando el Skype para el centro de administración de negocios.

#### <a name="step-6"></a>Paso 6

Ahora que ha asignado al número de puertos del suscriptor, iniciar sesión en un cliente de equipos como el usuario y marcar un número de 10 dígitos externo a través de la red PSTN. Después de realizar la llamada, confirme que la llamada se ha conectado y que el identificador de llamadas mostrada coincide con el número de suscriptor que transportar.

#### <a name="step-7"></a>Paso 7

Desde un número externo de PSTN, realizar una llamada al número de suscriptor que migrar a Office 365 y compruebe que se recibió la llamada entrante y conectados a través del cliente de los equipos.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decidir qué números de suscriptor nacional necesitará puerto, por país o región.</li><li>Decidir qué plantilla LOA que va a utilizar.</li><li>Determinar si su actual portador (carrier perdedora) permite la fragmentación de número de teléfono (es decir, permite pedidos parciales puerto).</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Recopilar la información necesaria y preparar el LOAs.</li><li>Descargar y completar las plantillas LOA que necesita.</li><li>Enviar una solicitud de traslado número de suscriptor.</li><li>Ejecutar pruebas de validación para los números de puertos asignando el sistema de teléfono con una llamada a los planes de servicio para acceso telefónico y confirmar que funcionan, tal como se describe en los pasos 6 y 7 anteriormente en esta sección.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Número de servicio trasladar los resultados de la prueba del documento

Después de completar todas las pruebas de número de suscriptor, crear un informe que resume los resultados de las pruebas para presentar durante la próxima revisión del Comité de dirección.

#### <a name="site-a-number-porting-test-summary-report"></a>Número de sitio A: trasladar el informe resumen de la prueba

> [!TIP]
>   A continuación es un ejemplo de plantilla de informe resumen de pruebas que puede utilizar para la revisión durante la próxima reunión del Comité directivo cuando decida a incorporado sistema telefónico con planes de llamar a los servicios en la fase de prueba piloto.

**Número de servicio al trasladar**

**Resumen de los resultados**:&nbsp;&nbsp;&nbsp;& #9744; Pasar&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Un error 

<table>
<tr><th colspan="2">Aspectos destacados de pruebas </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Pruebas de relieve  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Corrección:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores de elementos identificados </td></tr>
<tr><td>**Bloqueador**: TBD</td><td>**Corrección**: TBD</td></tr>
</table>


> [!TIP]
>   Para facilitar la discusión adicional durante la revisión final Comité directivo, puede utilizar la actualizada [la matriz de resultados de pruebas](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) proporcionado por [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para documentar y resaltar áreas de prueba adicionales que requieren corrección.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar si los números de suscriptor enviados para migración trasladados correctamente al sistema de teléfono con el servicio de llamada a planes..</li><li>Evalúe si podía asignar al número de puertos de servicio para el sistema de teléfono con el servicio llamando a los planes.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documente el número trasladar los resultados de la prueba.</li><li>Ejecutar planes de corrección y escalamiento para resolver problemas que ha experimentado con el proceso de conversión numérico, si existe.</li><li>Programar una reunión del Comité directivo para revisar el resumen de resultados de prueba.</li><li>Presentar los resultados de resumen de la prueba al Comité directivo para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


<a name="execute-your-test-plan-for-phone-system-with-calling-plans"></a>Ejecutar su plan de pruebas para el sistema de teléfono con planes de llamada
----------------------------------------------------------

Ahora que ha definido su plan de pruebas, el siguiente paso es describir los casos de prueba, centrarse en evaluar el sistema de teléfono con una llamada a los planes de administración y usuario disfrutar de características en el ámbito. Antes de la prueba comienza realmente, compruebe que existen los pruebas siguientes requisitos previos.

### <a name="phone-system-with-calling-plans-testing-prerequisites"></a>Sistema de teléfono con una llamada a planes de comprobación de requisitos previos

-   Casos de uso de negocios se han definido para el sistema de teléfono con el servicio llamando a los planes.

-   Se han identificado los participantes clave.

-   La licencia requerida para el sistema de teléfono con una llamada a los planes de servicios está disponible y se ha asignado al grupo de usuarios en el ámbito.

-   Se han identificado la lista de sitios organizativos y grupos de usuarios en el ámbito.

-   [Créditos de comunicaciones](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (si es necesario) se han configurado para su organización.

-   Sistema de teléfono con la configuración de planes de llamada han identificado y configurado.

-   Plan de configuración que admiten el sistema de teléfono con una llamada a los planes de se han identificado, configurado y aplicado para el grupo de usuarios en el ámbito de marcado de inquilinos.

-   Sistema de teléfono con llamada planes identificadas y configuradas para el grupo de usuarios en el ámbito de las directivas.

-   Sistema de teléfono con los requerimientos de cumplimiento de planes de llamada han identificado y configurada para el grupo de usuarios en el ámbito.

### <a name="document-phone-system-with-calling-plans-test-case-passfail-status"></a>Sistema telefónico de documento con el estado de correcto o incorrecto de casos de prueba de planes de llamada

Casos de prueba se evalúan para los equipos administrativos y características del sistema de teléfono de usuario en el ámbito, realizar el seguimiento de los resultados de cada caso de prueba para reflejar el estado parcial o superar, junto con el identificador asignado del defecto en caso de surgen problemas imprevistos.

#### <a name="phone-system-with-calling-plans-test-case-status"></a>Sistema telefónico con planes de llamada de estado de casos de prueba

> [!TIP]
>   A continuación es un ejemplo de plantilla de estado de caso de prueba que puede utilizar para los resultados de la prueba para su revisión durante la próxima reunión del Comité directivo cuando decida a incorporado sistema telefónico con planes de llamar a los servicios en la fase de prueba piloto.

| Sistema telefónico con Planes de llamada          |                              |                                                                                            |                           |                                                                            |
|------------------------------------------|------------------------------|--------------------------------------------------------------------------------------------|---------------------------|----------------------------------------------------------------------------|
| Identificador del caso de prueba                             | Título del caso de prueba              | Descripción del caso de prueba                                                                      | Resumen de resultados de caso de prueba | Id. de defecto asignado (si procede)                                         |
| 1                                        | Colocación de llamadas salientes de RTC. | Realizar una llamada saliente marcando un número de 10 dígitos nacional.                              |    & #9744; Pasar<br/>& #9744; Parcial<br/> & #9744; Un error                   | Cuando un usuario escribe un número de cuatro dígitos, se produce un error en la llamada que se coloca a la RTC. |



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar el estado de correcto o incorrecto de casos de prueba de alto nivel por el sitio para el sistema de teléfono con planes de llamar a funciones en el ámbito.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar los resultados de estado de caso de prueba para todos los casos de prueba completados en ámbito.</li><li>Programar una reunión del Comité directivo para revisar el resumen de resultados de prueba.</li><li>Estado de casos de prueba presente resultados al Comité directivo para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


### <a name="document-phone-system-with-calling-plans-testing-result-summary"></a>Documento de sistema de teléfono con una llamada a planes de resumen de resultados de las pruebas

Después de todos los casos de prueba que admiten el sistema de teléfono con planes de llamar a funciones en el ámbito, se han completado por sitio, documentar los resultados para revisar durante una reunión del Comité directivo cuando decida cuándo habilitar sistema de teléfono con planes de llamar a los servicios en la prueba piloto fase.

#### <a name="site-a-phone-system-with-calling-plans-test-case-summary-report"></a>Sitio A: teléfono sistema con planes de llamada informe de resumen de caso de prueba:

> [!TIP]
>   A continuación es un ejemplo de plantilla de informe resumen de prueba que puede revisar durante la próxima reunión del Comité directivo cuando decida a incorporado sistema telefónico con planes de llamar a los servicios en la fase de prueba piloto.


**Sistema de teléfono de equipos con planes de llamada**

**Resumen de los resultados**:&nbsp;&nbsp;&nbsp;& #9744; Pasar&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Un error 

<table>
<tr><th colspan="2">Aspectos destacados de pruebas </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Pruebas de relieve  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Corrección:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores de elementos identificados </td></tr>
<tr><td>**Bloqueador**: TBD</td><td>**Corrección**: TBD</td></tr>
</table>


> [!TIP]
>   Para facilitar la discusión adicional durante la revisión final Comité directivo, puede utilizar la actualizada [matriz de resultados de la prueba](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) proporcionada por [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para documentar y resaltar áreas adicionales que requieren corrección.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar los resultados de prueba de alto nivel resumen por sitio para el sistema de teléfono con planes de llamar a funciones en el ámbito.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>El informe de resumen de casos de prueba del documento después de que se han completado todos los resultados del caso de prueba.</li><li>Programar una reunión del Comité directivo para revisar el resumen de resultados de prueba.</li><li>Presente prueba resumen de los resultados al Comité directivo para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>



<a name="present-and-report-phone-system-with-calling-plans-test-findings"></a>Presentar e informar el sistema telefónico con planes de llamar a los resultados de prueba
----------------------------------------------------------------

Después de todo se han completado actividades de prueba y los defectos con un impacto de baja se han resueltos, programar una reunión de liquidación final con los participantes de pruebas designados. En la reunión, dirección:

-   Resumen de estado

-   Resaltar o relieve

-   Lecciones aprendidas

-   ¿Recomendación general: continuar con la fase piloto o evaluar los resultados de las pruebas?

-   Resultados de la matriz (éstas deberían documentarse completamente en un apéndice)

#### <a name="test-plan-deliverables"></a>Resultados del plan de pruebas:

> [!TIP]
>   A continuación es un ejemplo de un plan de pruebas que entrega plantilla que puede utilizar para documentar los criterios necesarios para lograr el cierre la sesión y salir de la fase de pruebas o suspender pruebas hasta que estén completamente resueltos todos los problemas identificados.

| Resumen de estado               | Sombras/iluminaciones | Lecciones aprendidas | Recomendación de cierre |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Tasa de pass de caso de prueba de % de TBD</li><li>Todas las pruebas superadas</li></ul> | TBD                  | TBD             | Efectuar la prueba piloto       |

-   Todas las pruebas superadas


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decidir el resumen de estado de pruebas.</li><li>Identificar pruebas de iluminaciones y sombras.</li><li>Identificar las lecciones aprendidas.</li><li>Decidir qué actualizaciones siguen siendo acciones, si existe.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Resultados de resumen de la prueba de documento para incluir:<ul><li>Resumen de estado</li><li>Sombras/iluminaciones</li><li>Lecciones aprendidas</li></ul></li><li>Programar una reunión del Comité directivo final para revisar los resultados de las pruebas.</li><li>Revisión resultados de resumen de prueba presente durante un Comité directivo obtener Cierre final para salir de la fase de pruebas.</li></ul></td></tr>
</table>
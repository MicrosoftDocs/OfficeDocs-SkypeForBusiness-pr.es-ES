---
title: Enterprise plan de pruebas para el sistema telefónico con planes de llamada en Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Validar que se cumplen las expectativas de su organización a través de las pruebas del sistema de teléfono en las características de los equipos, las funciones y facilidad de uso.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fffb52988da639f21246b0c5d27f2c8554b459ac
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855428"
---
<a name="define-and-document-your-phone-system-with-calling-plans-in-teams-test-plan-for-enterprises"></a>Defina y documente el sistema de teléfono con planes de llamada en el plan de pruebas de los equipos para empresas 
============================================================================================

Una vez que haya definido y documenta el sistema telefónico con planes de llamada en el éxito del negocio los equipos y los planes de implementación técnica como parte de la fase de previsión, el siguiente paso es validar que se cumplen los requisitos y las expectativas de su organización a través de característica, las funciones y facilidad de uso. Debe realizar este paso de validación antes de implementar una implementación piloto o de final en el entorno de producción.

Puede aprovechar el plan de éxito empresarial que haya definido durante la fase de previsión para que sirva como base para determinar las actividades, las expectativas, casos de prueba de características y funcionalidades y ámbito global que se deben evaluar durante la fase de pruebas.

<a name="identify-testing-support-stakeholders"></a>Identificar a las partes interesadas pruebas de compatibilidad
-------------------------------------

Mientras se prepara para evaluar el sistema telefónico con una llamada a los planes de características, cree una matriz de los participantes de soporte pruebas para identificar los roles necesarios para admitir la fase de pruebas.

> [!TIP]
> Como rellenar los equipos de prueba de la matriz de compatibilidad de los participantes, es posible que vea que algunos roles son los mismos que los identificado durante la fase de previsión, pero con las descripciones de rol inclinadas hacia las pruebas. Es posible que necesite identificar funciones adicionales, dependiendo de los requisitos únicos de los escenarios de pruebas.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Equipos de prueba de la matriz de compatibilidad de los participantes

> [!TIP]

> A continuación se incluye un ejemplo de una plantilla de pruebas compatibilidad con los participantes que puede usar en qué necesita para admitir la fase de pruebas de las partes interesadas del documento.

| Rol                          | Descripción de la función                                                                                                                                                                          | Recurso asignado, información de contacto y ubicación |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Las pruebas patrocinadores ejecutivos  | <ul><li>Asegúrese de que las características de los equipos satisfacen las necesidades de negocio; los patrocinadores ejecutivos están habituados en los resultados de negocio clave y escenarios de uso prioridades de mayúsculas y minúsculas.</li><li>Actuar como autoridad ultimate y asumir la responsabilidad, para probar los objetivos de característica de los equipos.</li><li>Ayudar a resolver problemas comunicados por el jefe de pruebas.</li><li>Patrocinador comunicación dentro de la empresa acerca de las pruebas de objetivos.</li><li>Ser responsable de la toma de decisiones clave estratégica.</li><li>Ser responsable de garantizar la disponibilidad de recursos necesarios y el presupuesto para admitir los esfuerzos de pruebas.</li><li>Unidad conocimiento del producto y comprar en para la campaña de prueba con otras partes interesadas claves.</li><li>Actuar como el patrocinador prueba durante la fase de evaluación de prueba.</li></ul>                                                 | TBD                                                  |
| Miembros del Comité de gobierno    | <ul><li>Mantener el interés en y se ofrece orientación para la dirección general del sistema de teléfono con una llamada a los planes de implementación del servicio.<li>Ayudar a dedicado a promocionar perspectiva estratégica a través de tiende a comprar en toda la organización.</li></ul>                                                                        | TBD                                                  |
| Responsable de proyecto                  |<ul><li> Administrar y conducir el equipo del proyecto.</li><li>Coordinar los socios y los equipos de trabajo ocupados en el proyecto.</li><li>Ser responsable de crear y planes de proyecto de administración para satisfacer los resultados de la claves trimestrales.</li><li>Resolver problemas de funciones cruzadas.</li><li>Proporcionan actualizaciones regulares patrocinadores del proyecto.</li><li>Incorporar los conocimientos de la experiencia de usuario clave identificados en los resultados de pruebas en el plan de adopción global del usuario.</li><li>Potenciales mensual empresarial y las revisiones operativas, contribuir a trimestral revisiones de negocios.</li></ul>                                                                                                                                                         | TBD                                                  |
| Arquitecto/responsable de colaboración  | <ul><li>Ser responsable de la ejecución de la estrategia de colaboración definida por los ejecutivos de la empresa.</li><li>Analizar y elija productos de colaboración para la empresa que cumplan los objetivos del negocio.</li><li>Ser responsable del diseño de las operaciones para productos de colaboración.</li><li>Definir los modelos de operación y soporte técnico.</li><li>Contribuir a revisiones de negocios mensual y trimestral.</li></ul>                                                                                                 | TBD                                                  |
| Jefe de proyecto               | <ul><li>Desarrollar y mantener el plan del proyecto.</li><li>Administración de entregas del proyecto en línea con el plan del proyecto y el presupuesto.</li><li>Registrar y administrar los problemas del proyecto, incluidas las extensiones.</li><li>Realizar llamadas de diaria semanales.</li><li>Póngase en contacto con y proporcionan actualizaciones para patrocinadores ejecutivos del proyecto.</li><li>Trabajar con los equipos de administración y la comunicación de cambio interno para actualizar el cambio de enfoque y comunicación de planes de administración según sea necesario.</li></ul>                                                                                                                                                   | TBD                                                  |
| Responsable de redes                  | <ul><li>Proporcionar información sobre el diseño de red durante la fase de detección.</li><li>Participar en el diseño durante talleres de fase de previsión.</li><li>Coordinar el trabajo del equipo de red durante la ejecución del proyecto.</li></ul>                                                                                                                               | TBD                                                  |
| Responsable de seguridad                 | <ul><li>Proporcionar información de diseño de seguridad y los procesos durante la fase de detección.</li><li>Participar en el diseño durante talleres de fase de previsión.</li><li>Coordinar el trabajo del equipo de seguridad durante la ejecución del proyecto.</li></ul>                                                                                                                | TBD                                                  |
| Responsable de telefonía                | <ul><li>Proporcionar información sobre el diseño de telefonía durante la fase de detección.</li><li>Participar en el diseño durante talleres de fase de previsión.</li><li>Coordinar el trabajo del equipo de telefonía durante la ejecución del proyecto.</li></ul>                                                                                                                           | TBD                                                  |
| Responsable de escritorio                  | <ul><li>Proporcionar información sobre los clientes y el proceso de actualización durante la fase de detección.</li><li>Participar en el diseño durante talleres de fase de previsión.</li><li>Coordinar el trabajo del equipo de escritorio durante la ejecución del proyecto.</li></ul>                                                                                                              | TBD                                                  |
| Representantes de la unidad de negocio | <ul><li>Contribuir a guías de adopción basadas en usuarios y materiales.</li><li>Contribuir a y revisar, casos de uso de negocio.</li></ul>                                                                                                                                   | TBD                                                  |
| Administradores de TI                     | <ul><li>Ayudar con la planeación de pruebas y ejecución (esta función es para los profesionales de TI).                                                                                                                       | TBD                                                  |
| Propietario del servicio                 | <ul><li>Ser responsable de la operación del sistema de teléfono con una llamada a los planes de servicio, Subir todo.</li><li>Actuar como propietario del sistema de teléfono con una llamada a los planes de servicio.</li></ul>                                                                                                               | TBD                                                  |
| Director de prueba             | <ul><li>Definir el plan de pruebas, incluidas las actividades, las dependencias, entorno, objetivos, estrategia, recursos (medioambientales y humana) y la escala de tiempo necesario para la compatibilidad con la fase de pruebas.</li><li>Coordinar la entrega y preparación para dependencias del plan de pruebas.</li><li>Alinear con la prioridad para la resolución de defecto de derecho.</li><li>Actuar como la ruta de acceso de escalación de pruebas problemas que surgen.</li><li>Comunicarse y notificar el estado del plan de pruebas con equipos internos y los participantes designados.</li><li>Documentar y presentar los resultados de la prueba final.</li></ul> | TBD                                                  |
| Sistema telefónico al llamar a los planes de evaluador     | <ul><li>Revise el plan de pruebas para comprender pruebas requisitos, objetivos, escala de tiempo, resolución de problemas y casos de prueba que se va a ejecutar.</li><li>Revise y desarrollar casos de prueba de compatibilidad con el sistema telefónico con los requisitos de aceptación y funcionalidad de planes de llamar a.</li><li>Ejecutar casos de prueba y los resultados de pruebas de documento.</li><li>Defectos de documentos que puedan surgir y pasar de la líder de prueba para priorización y resolución.</li><li>Reducciones de cierre defectos después de que se haya confirmado defecto de resolución de prueba.</li></ul>                                                                | TBD                                                  |
| Ingeniero de pruebas de red                | <ul><li>Revise el plan de pruebas para comprender pruebas requisitos, objetivos, escala de tiempo, resolución de problemas y casos de prueba que se va a ejecutar.</li><li>Revise los casos de prueba de compatibilidad con los requisitos de aceptación y el rendimiento de la preparación de red.</li><li>Ejecutar las pruebas relacionadas con la preparación de la red, como la conectividad de red y validación de rendimiento, validación de QoS y validar la configuración de túnel de división.</li><li>Complete la validación de ancho de banda para los sitios en el ámbito mediante el uso de organizador de red a través de MyAdvisor.</li><li>Preparación de la red documento resultados de las pruebas.</li><li>Defectos de documentos que puedan surgir y pasar de la líder de prueba para priorización y resolución.</li><li>Reducciones de cierre defectos después de que se haya confirmado defecto de resolución de prueba.</li></ul>                                                                | TBD                                                  |
| Ingeniero de pruebas de seguridad               | <ul><li>Revise el plan de pruebas para comprender pruebas requisitos, objetivos, escala de tiempo, resolución de problemas y casos de prueba que se va a ejecutar.</li><li>Revise y desarrollar casos de prueba de compatibilidad con los requisitos de aceptación de seguridad.</li><li>Ejecutar las pruebas relacionadas con aceptación de seguridad para casos de prueba.</li><li>Aceptación de seguridad de documento resultados de las pruebas.</li><li>Defectos de documentos que puedan surgir y pasar de la líder de prueba para priorización y resolución.</li><li>Reducciones de cierre defectos después de que se haya confirmado defecto de resolución de prueba.</li></ul>                                                                | TBD                                                  |
| Herramienta de comprobación de telefonía              | <ul><li>Revise el plan de pruebas para comprender pruebas requisitos, objetivos, escala de tiempo, resolución de problemas y casos de prueba que se va a ejecutar.</li><li>Revisión de compatibilidad con servicio traslado aceptación y funcionalidad de los requisitos del número de casos de prueba.</li><li>Ejecutar las pruebas relacionadas con el servicio trasladar número, incluido el servicio de puerto número a Office 365.</li><li>Ejecutar casos de prueba y los resultados de caso de prueba del documento.</li><li>Defectos de documentos que puedan surgir y pasar de la líder de prueba para priorización y resolución.</li><li>Reducciones de cierre defectos después de que se haya confirmado defecto de resolución de prueba.</li></ul>                                                                | TBD                                                  |
| Prueba de administración de planes de sistema telefónico con llamadas | <ul><li>Revise el plan de pruebas para comprender pruebas requisitos, objetivos, escala de tiempo, resolución de problemas y casos de prueba que se va a ejecutar.</li><li>Revise y desarrollar casos de prueba de compatibilidad con el sistema telefónico con una llamada a los planes de aceptación y funcionalidad de requisitos de administración.</li> <li>Ejecutar casos de prueba y los resultados de caso de prueba del documento.</li><li>Defectos de documentos que puedan surgir y pasar de la líder de prueba para priorización y resolución.</li><li>Reducciones de cierre defectos después de que se haya confirmado defecto de resolución de prueba.</li></ul>                                                                | TBD                                                  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir qué funciones de los participantes y soporte técnico de pruebas requieren para probar el sistema telefónico con una llamada a los planes de características en el entorno.</li><li>Decidir qué recursos asignará para las funciones de los participantes y soporte técnico de pruebas que ha identificado.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Las funciones de los participantes y soporte técnico de pruebas requeridas en la matriz de los participantes de admitir las pruebas de documentos.</li><li>Información de contacto del documento y detalles de ubicación para cada recurso de lista en la matriz de los participantes de compatibilidad con las pruebas.
</table>


<a name="define-phone-system-with-calling-plans-feature-requirements"></a>Definir el sistema telefónico con una llamada a los planes de requisitos de característica 
------------------------------------------------------------

Como parte de la definición de sistema telefónico con planes de llamar a los requisitos de características para los usuarios en el ámbito, uno de los primeros pasos que debe haber completado durante la fase de previsión era el [Análisis de rol](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#assess-environment-and-evaluate-adoption-readiness), donde se define el sistema telefónico con planes de llamada rol y escenarios.
Con esta línea de base identificado, el siguiente paso es evaluar la guía pública más reciente de los equipos para determinar:

-   Qué sistema de teléfono con una llamada a los planes de características va a implementar para los usuarios en el ámbito.

-   Se esperaba user sistema telefónico con planes de llamar a los requisitos de funcionalidad, dado su Skype actual para el entorno de implementación empresarial, Exchange y SharePoint.

-   Si puede confirmar que sistema telefónico con planes de llamar a las características que se describen en la guía pública más reciente que cumple con el usuario, las funciones y requisitos de ámbito en la escala de tiempo de la implementación

> [!TIP]
> La guía básica de los equipos más reciente para la identificación de sistema telefónico con una llamada a los planes de características en el ámbito para la implementación se puede encontrar en <https://aka.ms/skype2teamsroadmap>.

Ahora que se han definido el sistema telefónico con las características y planes de llamar a la persona, los criterios para la evaluación siguiente será la experiencia de interoperabilidad con los equipos. Para obtener información adicional acerca de la experiencia de interoperabilidad junto con opciones de configuración disponibles, vea [los equipos de Microsoft y Skype para la interoperabilidad de negocio](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability).

#### <a name="phone-system-with-calling-plans-feature-definition"></a>Sistema telefónico con planes de llamar a la definición de característica

> [!TIP]
> A continuación se incluye un ejemplo de un sistema telefónico con la plantilla de definición de planes de llamada que puede usar para documentar el sistema telefónico con características de grupo de administración y usuario planes de llamada que se va a evaluar.


| Calificación de la empresa   | Reuniones de colaboración    | Plataforma y dispositivos   | Para profesionales de TI  | Grupo de negocio adicionales, específicos del sitio  | Por último guía básica de los equipos se cumplen los requisitos |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Características del sistema de llamada de teléfono:<ul><li>Transferencia de copia oculta</li><li>Bloqueo de llamadas</li><li>Desvío de llamadas</li><li>Identificador de autor de la llamada de transparencias</li><li>Compatibilidad con E911</li><li>Marcado de extensión</li><li>Contención de llamada</li><li>Control de llamadas múltiples</li><li>Llamada simultánea</li><li>Correo de voz de Azure</li></ul></li><li>Soporte técnico del plan de llamada</li></ul> |<ul><li>Skype para la empresa-a-de los equipos de llamada</li></ul> |<ul><li> Soporte técnico de características de Windows, las reuniones de cliente de los equipos de Mac</li><li>Admitir la característica de las reuniones de explorador los equipos cliente para:<ul><li>Cromo</li><li>Microsoft Edge</li></ul></li><li>iOS y Android de los equipos cliente de compatibilidad de la característica de las reuniones</li><li>Soporte técnico de TTY</li></ul> | <ul><li>Portal de diagnóstico de calidad de llamada</li><li>Plan de marcado de inquilinos</li><li>Directivas de identificador de autor de la llamada del inquilino</li><li>Habilitar el análisis de calidad de llamada (CQD)</li></ul> | <ul><li>Validar los equipos de las características basadas en imagen portátil corporativo de reunión</li><li>Compatibilidad con idiomas específicos</li><li>Opciones de GPO que se aplican para un escenario de usuario determinado o sitio específico</li></ul> | Sí  |




#### <a name="phone-system-with-calling-plans-user-functionality-definition"></a>Sistema telefónico con planes de llamar a definición de funciones de usuario

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla de funcionalidad de usuario que puede utilizar para documentar la experiencia de usuario necesaria según el sistema telefónico con planes de llamar a las características que se deben evaluar.


| Experiencia de Exchange                          | Experiencia de SharePoint                            | Experiencia de directiva de interoperabilidad de los equipos |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Crear equipos (habilitado para la creación de grupo de Office)</li><li>Unirse a equipos</li><li>Crear canales</li><li>Crear y ver reuniones</li><li>Modificar la imagen de perfil de usuario</li><li>Agregar y configurar conectores</li><li>Agregar y configurar fichas</li><li>Agregar y configurar bots</li></ul> | <ul><li>Almacenar y compartir archivos dentro de las conversaciones de los equipos</li><li>Almacenar y compartir y los archivos dentro de chats privadas (basados en OneDrive)</li></ul> | <ul><li>ChatDefaultClient: valor predeterminado</li><li>CallingDefaultClient: valor predeterminado</li></ul>      |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li> Decidir qué sistema de teléfono con planes de llamar a las características de categoría va a implementar en su entorno.</li><li>Identificar su sistema de teléfono del usuario con planes de llamar a los requisitos de funcionalidad dados su Skype actual para el entorno de implementación empresarial, Exchange y SharePoint.</li><li>Decidir qué experiencia de interoperabilidad de los equipos que va a implementar.</li><li>Revise la guía pública más reciente de los equipos y decida si las capacidades de carga de trabajo actual cumplen la escala de tiempo de implementación.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>El sistema telefónico con planes de llamar a las características de categorías necesarios para admitir el sistema telefónico con una llamada a los planes de implementación de documento.</li><li>Documento del sistema de teléfono del usuario con planes de llamar a funciones y requisitos de interoperabilidad dados su Skype actual para el entorno de implementación empresarial, Exchange y SharePoint.</li><li>Si la guía pública más reciente de los equipos que representa el sistema telefónico con planes de llamar a funciones cumple los requisitos de control de tiempo de la implementación y las necesidades empresariales de documentos.</li></ul></td></tr>
</table>

<a name="define-and-document-your-phone-system-with-calling-plans-test-plan"></a>Defina y documente el sistema telefónico con planes de llamar al plan de pruebas
------------------------------------------------------------------

Una vez que haya definido el sistema telefónico con una llamada a los planes de características en el ámbito, el siguiente paso es crear el plan de pruebas. En un nivel alto, el plan de pruebas abarca la estrategia de pruebas general y la metodología que se usará para admitir la validación de la característica en el proceso de pruebas.

En un nivel alto, debe incluir el plan de pruebas:

-   **Pruebas ámbito:** Se resumen las áreas de foco (los objetivos, escenarios y objetivos) que se deben evaluar como parte de la fase de pruebas

-   **Casos de prueba:** El conjunto de casos de prueba para validar de las características de sistema de teléfono con planes de llamada en el ámbito

-   **Pruebas de recursos:** Una matriz de los recursos necesarios para admitir el trabajo de las pruebas desde un punto de vista medioambiental, técnicos y personal

-   **El plan de pruebas (escala de tiempo):** Representa al probar comenzará, ¿durante cuánto tiempo es probable que la última y, cuando se espera para finalizar la fase de pruebas

-   **Dar de baja el reporting y corrección:** Instrucciones de cómo se deben informar problemas con las pruebas, realiza un seguimiento y clasificado

-   **Dar de baja de escalación y evaluación de errores:** Esquema para cómo y cuándo debe iniciarse una escalación defecto

-   **Pruebas de suspensión y la salida de criterios:** Inicio de sesión desactivado criterios esquematización de instrucciones para cualquier lograr para salir de la fase de pruebas o las pruebas pausar hasta que se resuelvan defectos con prioridad

-   **Probar entregas:** Resumen de los cuales los resultados que se desarrollado y entregar para admitir la aceptación de cierre de sesión y salir del proceso de prueba

> [!TIP]
>   Una metodología de prueba es posible que ya existen en la organización, pero las instrucciones que aparece a continuación refleja los procedimientos recomendados que pueden incluirse o aprovecharse por separado para las características de los equipos de pruebas en el entorno.

En las secciones siguientes se encontrará instrucciones prescritos adicionales que le ayudarán a en decisiones específicas y las plantillas y temas para tener en cuenta al realizar el plan de prueba.

### <a name="define-and-document-testing-scope"></a>Definir y documentar el ámbito de las pruebas

Mientras se trabaja para desarrollar el plan de pruebas, debe definir por adelantado, el ámbito de las pruebas para resaltar la carga de trabajo y la lista de características que se va a evaluar.

El ámbito para evaluar correctamente el sistema telefónico con una llamada a los planes de características normalmente incluye:

-   Sistema de teléfono con una llamada a los planes de preparación del sitio

-   Sistema telefónico con una llamada a los planes de experiencia del usuario

-   Sistema de teléfono con una llamada a los planes de administración

#### <a name="phone-system-with-calling-plans-testing-scope"></a>Sistema de teléfono con una llamada a planes de pruebas de ámbito

> [!TIP]
>   A continuación se incluye un ejemplo de plantilla de ámbito de prueba que puede utilizar para documentar el sistema telefónico con características de grupo de administración y usuario planes de llamada que se va a evaluar.

| Sistema de teléfono con una llamada a los planes de preparación del sitio                                                                                                                                                                                    | Sistema telefónico con una llamada a los planes de experiencia del usuario                                                                                                                                                                                         | Sistema telefónico con planes de llamar a la experiencia de administración                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>Ancho de banda de organizador de planeación (a través de MyAdvisor) de la red<li></li>Validación de conectividad y rendimiento de la red (a través de Skype para la herramienta de evaluación de red empresarial)<li></li>Calidad de la validación de servicio (QoS)<li></li>Validación de división túnel de acceso remoto</li></ul>|<ul><li>Características de PBX<li></li>RTC de llamada (nacional e internacional)<li></li> Realizar y recibir llamadas de RTC<li></li>Correo de voz de Azure<li></li>E911<li></li>Plan de marcado de inquilinos<li></li>Enmascaramiento de identificador de autor de la llamada de inquilinos <li></li>Características de control de llamada avanzadas (por ejemplo, de transferencia de llamadas simultáneas)</li></ul> |<ul><li>Asignación de licencias</li><li>Número de suscriptor trasladar a Office 365</li><li>Sistema de teléfono con una llamada a los planes de informes</li><li>Calidad de llamada de creación de informes (CQD)</li></ul> |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir el sistema telefónico con una llamada a planes de pruebas de ámbito mediante la identificación de las características que se deben evaluar por área de foco.</li><li>Decidir adicionales metas y objetivos para la evaluación.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documente el sistema de teléfono con una llamada a los planes de características que se deben evaluar por área de foco.</li><li>Documentar objetivos adicionales y los objetivos para la evaluación.</li></ul></td></tr>
</table>

### <a name="define-and-document-phone-system-with-calling-plans-test-cases"></a>Defina y documente el sistema telefónico con planes de llamar a casos de prueba

Una vez que haya definido el sistema telefónico con una llamada a los planes de características, implementación del cliente y escenarios en paralelo con Skype para la empresa (si procede), el siguiente paso es formulen necesarios para evaluar el sistema telefónico con una llamada a los planes de características en los casos de prueba ámbito. En un nivel alto, casos de prueba normalmente se agrupan por área de foco e incluyen:

-   **Título del caso de prueba:** Área de foco de la característica de la prueba está evaluando (por ejemplo, el sistema telefónico con planes de llamada)

-   **Descripción del caso de prueba:** Resumen de los objetivos de las características de prueba que se está evaluadas la esquematización

-   **Instrucciones de caso de prueba:** Pasos a seguir para ejecutar correctamente el caso de prueba se lleva a cabo

-   **Entorno necesarios (los requisitos previos):** Instrucciones de instalación necesarias para ejecutar correctamente la prueba

-   **Recurso requerido:** Recursos de personal necesitan para la evaluación sea correcta y la ejecución de la prueba

-   **Resultados esperados:** El resultado que espera una vez completada correctamente la prueba

> [!NOTE]
>   Debido a que el enfoque y el nivel de detalle necesario para la creación de caso de prueba pueden variar dentro de la organización, es una buena idea que se deben seguir un enfoque que permite un nivel de detalle adecuado aún equilibra minuciosidad con viabilidad, para admitir la prueba general capacidad de administración.

> [!TIP]
>   Para ayudar con la creación de caso de prueba como punto de partida, vea la lista de la Guía de usuario de teléfono del sistema disponible en [las reuniones de los equipos y las llamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

#### <a name="phone-system-with-calling-plans-test-case"></a>Sistema de teléfono con una llamada a los planes de caso de prueba

> [!TIP]
>   A continuación se incluye un ejemplo de plantilla de caso de prueba que puede utilizar para documentar el sistema telefónico con características de grupo de administración y usuario planes de llamada que se va a evaluar.

Sistema telefónico al llamar a los planes de validación

| Identificador de caso de prueba | Título del caso de prueba               | Descripción del caso de prueba                                                  | Entorno necesario para la ejecución del caso de prueba                                               | Pasos necesarios para la ejecución del caso de prueba                                                                                                                                                          | Las pruebas de los recursos necesarios              |
|--------------|-------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| 1            | Realizar una llamada saliente de RTC | Compruebe que puede realizar una llamada de voz externo a un número de 10 dígitos. |<ul><li>Instalado el cliente de los equipos.</li><li>Usuario habilitado con las siguientes licencias de Office 365 asignadas:<ul><li>Office Enterprise E5 con el sistema telefónico, los equipos de Microsoft y planes de llamada nacional e internacional</li><li>Office Enterprise E3 con el sistema telefónico, los equipos de Microsoft y planes de llamada nacional e internacional</li></ul></li></ul> | <ol><li>Inicie sesión en el cliente de los equipos.</li><li>Seleccione el teclado de marcado y escriba un número de 10 dígitos que se va a marcar.</li><li>Compruebe que el número marcado correctamente se normaliza y se establece la llamada de RTC externa.</li></ol>    | Sistema telefónico al llamar a los planes de evaluador |


> [!TIP]
>   Para obtener instrucciones adicionales en facilitar individual caso de prueba y creación de plan general para evaluar el sistema telefónico con planes de llamar a las características de la organización, revise el [Plan de pruebas de sistema de teléfono](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) proporcionados por [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir qué sistema de teléfono con la administración de los planes de llamada y se evaluará las características de usuario.</li><li>Decidir qué entorno de prueba es necesario para admitir la ejecución del caso de prueba.</li><li>Decidir los pasos necesarios para la evaluación del caso de prueba.</li><li>Decidir los recursos necesarios para la correcta ejecución de la prueba.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar los casos de prueba que se deben evaluar, basado en la plantilla de caso de prueba proporcionada.</li><li>Incluir la plantilla completa como parte del plan de pruebas global.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>Definir y documentar los recursos de prueba

Para admitir la fase de pruebas, es importante que desarrolle un plan de recursos que se detallan los recursos de personas, soporte técnico y la tecnología que necesita aquí. Un componente importante del plan de prueba general, es posible que necesita el recurso plan le ayudará a que determinar las dependencias que pueden existir y proporciona una sensación de alto nivel del recurso admiten.

En un nivel alto, estos recursos normalmente constan de:

-   **Personas**: las partes interesadas

-   **Tecnología**: inquilino, administración de licencias, dispositivos

-   **Admitir**: formación (tarjetas, vídeos), soporte técnico de administración con la ruta de acceso de escalación definido

#### <a name="testing-resource-requirements"></a>Las pruebas de los requisitos de recursos

> [!TIP]
>   A continuación es un ejemplo de pruebas plantilla de requisito de recursos que puede usar para los diferentes tipos de recursos necesarios para admitir la fase de prueba de documentos.


| Tipo de recurso | Recursos necesarios                                           | Descripción del recurso |
|---------------|--------------------------------------------------------------|----------------------|
| Personas        | Los evaluadores tienen resultados de prueba de las partes interesadas                               | TBD                  |
| Tecnología    | Acceso a Office 365 con habilitados los siguientes servicios:<ul><li>Office 365 E5 licencias asignadas</li><li>Plan nacional e internacional llamada asignado</li></ul>    | TBD                  |
| Asistencia técnica       | Jefe de soporte técnico de prueba de administrador técnico de prueba de pruebas | TBD                  |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir los tipos de recursos (personas, tecnología y soporte técnico) que necesitará para admitir la fase de pruebas.</li><li>Decidir los recursos específicos necesarios para los tipos de recursos que ha identificado.</li><li>Decidir si debe proporcionar aún más detalles para describir los tipos de recursos que necesita.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documente los tipos de recursos (personas, tecnología y soporte técnico) que necesitará para admitir la fase de pruebas.</li><li>Los recursos específicos necesarios para los tipos de recurso que ha identificado del documento.</li><li>Si decide que es necesario, documente cualquier más detalles sobre los tipos de recursos que necesita para admitir la fase de pruebas.</li></ul></td></tr>
</table>


### <a name="define-and-document-a-testing-timeline"></a>Definir y documentar una escala de tiempo de prueba

Como parte de la definición del plan de prueba, cree una escala de tiempo que se describe la programación para cuando espera a completar las actividades de pruebas y lograr hitos de alto nivel.

En un nivel alto, normalmente se compone de:

-   **Tarea:** Actividad de alto nivel para completarse

-   **Hito:** Objetivo de alto nivel o el progreso de la que se ha completado

-   **Recurso requerido:** Las pruebas de recursos necesarios para admitir la entrega del hito o tarea identificada

-   **Fecha de inicio:** La fecha en que se inició la actividad, hito o tarea en

-   **Fecha de finalización:** La fecha en que espera la actividad, hito o que se complete por tarea

-   **Propietario:** Recurso asignado quién es responsable de garantizar que la actividad, hito o tarea se ha completado en el tiempo, de acuerdo con la fecha de finalización

-   **Estimación:** Número de horas que los recursos asignados prevé tardará para asegurarse de que la actividad, hito o tarea se ha completado en el tiempo

#### <a name="testing-scheduling-and-timeline-requirements"></a>Requisitos de escala de tiempo y programación de prueba

> [!TIP]
>   A continuación es un ejemplo de una plantilla de requisito pruebas de escala de tiempo que puede utilizar para documentar las fechas anticipadas para cuando se completará las actividades de pruebas específicas o hitos enviados por.

| Tarea                                                 | Hito       | Fecha de inicio                                                             | Fecha de finalización | Owner | Recursos asignados | Estimación |
|------------------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Informe de pruebas                                          | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Horas de TBD  |
| La ejecución del caso de prueba: Sistema de teléfono con planes de llamada | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Horas de TBD  |
| La ejecución del caso de prueba: Preparación de la red               | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Horas de TBD  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir la actividad de escala de tiempo, hito y las tareas que necesita para realizar un seguimiento.</li><li>Decidir qué recursos que necesitará para asignar.</li><li>Decidir la fecha en que espera realizarse.</li><li>Identificar el propietario de la entrega.</li><li>Decidir cuánto tiempo se tardará en completar la actividad, un hito o una tarea.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>La escala de tiempo prueba de documentos mediante el uso de la plantilla que se proporciona e incluyen:<ul><li>Actividad de escala de tiempo, hito y las tareas que debe realizar un seguimiento.</li><li>Recursos que se deben asignar.</li><li>Fecha de finalización prevista.</li><li>Propietario de la entrega.</li><li>Tiempo necesario para completar la actividad, un hito o una tarea.</li></ul></li><li>Incluir la plantilla completa como parte del plan de pruebas global.</li></ul></td></tr>
</table>


### <a name="define-and-document-test-defect-report-criteria"></a>Definir y documentar los criterios de informe de prueba defecto

A medida que ejecutan los casos de prueba dentro de una fase determinada o secuencia, pueden surgir problemas donde el resultado del caso de prueba que se está ejecutando no es lo que esperaba.

Cuando se producen estos tipos de resultados, deben capturar en un plan de informe y corrección de defecto que se remite el jefe de pruebas designados para su revisión, informes y resolución de defecto.

Normalmente, un plan de informe y corrección de defecto incluye lo siguiente:

-   **Dar de baja el identificador:** El número asignado al problema

-   **Identificador de caso de prueba afectado**: el número asignado al caso de prueba que se está evaluando en el momento en que se identificó el defecto

-   **Dar de baja el Descripción:** Resumen del problema

-   **Entorno y pasos para reproducir:** Resumen de la configuración del entorno pruebas, junto con los pasos exactos necesarios para reproducir el problema

-   **Gravedad defecto**: el impacto del problema, que van desde impide que el caso de prueba que haya aprobado acepten con un riesgo mínimo. Es posible que algunos ejemplos:

-   **Baja:** El problema tiene poco efecto y no impedir que el caso de prueba de lograr la aceptación si se puede resolver el problema más adelante.

-   **Medio:** El problema tiene impacto importante, pero no impide que el caso de prueba lograr la aceptación si se puede resolver el problema antes de que se complete la fase de pruebas.

-   **Alta:** -el problema tiene impacto crítico en el caso de prueba. Se debe resolver el problema antes de que se puede aceptar el caso de prueba.

-   **Estado:** Tiene el problema que se ha resuelto, está abierto, o aún bajo investigación

-   **Enviado por:** El evaluador que notificó el problema

-   **Propietario asignado:** El recurso asignado desde el equipo de pruebas que es responsable de resolver el problema

-   **Los detalles:** Esto puede incluir, pero no se limita a: los registros del lado cliente, capturas de pantalla o vídeo del problema.

Como los evaluadores ejecutan los casos de prueba que se describen en su plan de pruebas, debe estar seguro para llevar a cabo un plan de informe y corrección de defecto para cualquier problema que surja.
Esto resaltará impacto potencial que podría obstaculizar o incluso por detener el proceso de evaluación de prueba.

#### <a name="testing-defect-report-and-remediation-plan"></a>Planeación de pruebas de informe de defectos y corrección

> [!TIP]
>   A continuación es un ejemplo de plantilla de informe de defectos y planeación de corrección que puede usar para documentar los problemas detectados durante la fase de pruebas.

| Identificador de defecto                                | Identificador de caso de prueba afectado | Descripción del defecto                                                                                 | Entorno /steps reproducir                                                                                                | Gravedad | Estado | Presentado por | Propietario asignado | Compatibilidad con detalles (registros, capturas de pantalla etc.) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Cuando el usuario escribe una extensión de cuatro dígitos, si se intenta realizar una llamada saliente, la llamada se produce un error. | En el cliente de los equipos, seleccione el teclado de marcado, escriba una extensión de cuatro dígitos y seleccione el icono de teléfono para intentar realizar la llamada. | Medio   | Cerrado | Louis Lahr   | Lisa gris      | Registro de los equipos cliente<br/> Captura de pantalla de los equipos cliente     |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir qué niveles de gravedad de criterios defecto asignará para admitir el trabajo de las pruebas.</li><li>Decidir qué prueba defecto informes criterios que aquí documentos si surgen problemas durante las pruebas.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar el defecto prueba informes criterios necesarios en la plantilla que se proporciona.</li><li>Incluir la plantilla completa como parte del plan de pruebas global.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Definir y documentar los criterios de salida y de suspensión

Como parte del proceso de ejecución de plan de prueba general, debe definir los criterios para indicar el punto en el que debe suspender los esfuerzos de pruebas frente a los requisitos que se deben cumplir para obtener cierre la sesión y salir de la fase de pruebas.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Criterios de suspensión y la salida del plan de prueba

> [!TIP]
>   A continuación es un ejemplo de suspensión y la salida de plantilla de criterios que puede usar en su plan de pruebas para criterios de documento necesario para lograr el cierre de sesión, salga de la fase de pruebas o suspender las actividades de pruebas.

| Prueba de criterios de salida                            | Comprobación de criterios de suspensión                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>Todos los casos de prueba debe alcanzar una velocidad de acceso de TBD %</li><li>Todos los casos de prueba debe haber ejecutado completamente</li><li>Desde evaluados todos los casos de prueba, se deben cerrar todos los defectos de gravedad alta</li></ul> | <ul><li>Todos los casos de prueba debe lograr un porcentaje de errores de % TBD</li><li>Antes de continúen con las pruebas, se deben resolver todos los defectos que se identificó como una gravedad alta.</li></ul> |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decida los criterios de suspensión que deben cumplirse si se identifican problemas con las pruebas.</li><li>Decidir en criterios de salida que se deben cumplir para obtener pruebas aceptación cierre la sesión y admitir la salida de la fase de pruebas después de todo pruebas actividades están completas.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documente los criterios de suspensión y la salida de prueba necesarios en las plantillas de prueba y de salida proporcionadas.</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>Definir y documentar el proceso de escalación defecto

Durante el transcurso de la ejecución de planes de prueba, es posible que descubra un problema o identificar un defecto que requiere escalación al recurso derecho para impulsar y determinar la resolución necesaria para permitir que las pruebas continuar.

Como defectos se identifican con la gravedad adecuada y la prioridad asignada, se crea una matriz de escalación y proceso de asignación de salida de la revisión de evaluación de errores cuando se desencadena una escalación y cómo, cuándo y quién se va a asignar el defecto para profundizar revisión y resolución.

Normalmente, un plan de informe y corrección de defecto incluye lo siguiente:

-   **Dar de baja el identificador:** El número asignado al problema

-   **Dar de baja el Descripción:** Resumen del problema

-   **Dar de baja el evaluación de prioridad:** El nivel de prioridad asignado a un defecto para la resolución de en función del impacto empresarial y defecto gravedad. Se incluyen algunos ejemplos:

-   **Baja:** El problema tiene poco impacto en la prevención de la fase de pruebas de lograr desactivar inicio de sesión si se puede resolver el problema más adelante.

-   **Medio:** El problema tiene un impacto importante en la prevención de la fase de pruebas de lograr desactivar inicio de sesión si no se puede resolver el problema.

-   **Alta:** El problema tiene un impacto crítico en la prevención de la fase de pruebas de lograr desactivar inicio de sesión si no se puede resolver el problema.

-   **Asignado defecto propietario:** El recurso asignado desde el equipo de pruebas que es responsable de resolver el problema

-   **Asigna el punto de escalación defecto:** El recurso asignado que está en el punto para trasladar el problema en la organización (si es necesario) para conducir resolución; basándose en la gravedad de defecto

-   **Dar de baja el estado:** Tiene el problema que se ha resuelto, está abierto, o aún bajo investigación

-   **Requeridos resolución por fecha:** La fecha que se debe resolver el problema por

-   **Fecha de estado:** Se actualizó la fecha que refleja el estado de última hora como un resultado de una revisión de evaluación de errores de defecto

#### <a name="test-plan-defect-escalation"></a>Escalado de defecto del plan de pruebas

> [!TIP]
>   A continuación es un ejemplo de una plantilla de escalación defecto que puede usar en parte de su plan de pruebas en el proceso de escalación requerido para asignar prioridades a los y resolución de pruebas defectos del documento.

| Identificador de defecto                                | Descripción del defecto                                                                                 | Evaluación de prioridad de defecto                                           | Propietario de defecto asignados | Punto de escalación defecto asignados | Método de extensión de defecto                                          | Estado de defecto | Resolución necesaria por fecha | Fecha de estado |
|------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1                                        | Cuando el usuario escribe una extensión de cuatro dígitos, si se intenta realizar una llamada saliente, la llamada se produce un error. | Medio                                                               | Lisa gris             | Louis Lahr                       | Correo electrónico semanal de revisión de evaluación de errores de alta prioridad a los participantes afectados | Abra el           | ASAP                        | 1/12/2018   |



<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir y está de acuerdo en las prioridades de defecto para admitir su plan de pruebas.</li><li>Decidir el punto de escalación para cada área de defecto.</li><li>Decidir el defecto escalación y el plan de evaluación de errores que se deben seguir, en función de prioridad.</li><li>Decidir el defecto de informes y clasificación del plan de comunicación para escalación.</li><li>Decidir la cadencia de reunión de revisión de evaluación de errores de defecto.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Las prioridades acordadas en defecto de documentos.</li><li>El punto de escalación para cada área de foco posibles del documento.</li><li>Documentar el plan de escalación y evaluación de errores de defecto según criterios acordado en.</li><li>Documente su defecto las directrices de informe.</li><li>Programar la serie de reuniones de evaluación de errores de defecto.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-deliverables"></a>Definir y documentar los resultados de pruebas

El componente final y la último en la creación de un plan de pruebas consiste en identificar los resultados en términos de entregas específicas que proporcionará el plan de prueba general.

En un nivel alto, estos incluyen normalmente, pero no están limitados a:

-   Plan de pruebas

-   Casos de prueba

-   Informes de defecto

-   Resumen de los resultados de prueba

-   Prueba de aceptación y aprobación.

#### <a name="test-plan-deliverables"></a>Entregas del plan de pruebas

> [!TIP]
>   A continuación se incluye un ejemplo de una matriz de entrega de plan de prueba que puede utilizar para documentar las entregas que se creará, junto con los recursos necesarios para la revisión, aprobación y cierre la sesión.

| Plan de pruebas de entrega                    | Formato de entrega de plan de pruebas | Entrega propietario del plan de pruebas                                                                                                      | Revisor de entrega de plan de pruebas | Aprobador de entrega de plan de pruebas | Plan entrega cierre fecha de la prueba |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Plan de pruebas                                | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Informes de administración de defecto                | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Pruebas de informes de estado                   | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Resumen de los resultados de prueba                     | Word PPTX                    | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir qué entregas deben crearse y capturan como resultado de cada fase de pruebas. Para cada entrega, decide cuál será su:<ul><li>Formato</li><li>Owner</li><li>Revisor</li><li>Aprobador</li></ul></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Un plan entrega creación y la entrega matriz de pruebas del documento.</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>Evaluación de la preparación de la red
----------------------------

Como un elemento crítico para admitir la implementación de los equipos, preparación de la red es una parte fundamental de las pruebas para asegurarse de que la red correctamente está optimizada para admitir comunicaciones de los equipos. Para asegurarse de que su red esté preparada para los sitios en el ámbito, incluir las áreas de foco enumeradas a continuación en su estrategia de prueba:

-   Estimación del ancho de banda y la planificación con el organizador de la red (a través de MyAdvisor)

-   Calidad de la validación de la configuración de servicio (QoS)

-   Comprobación el rendimiento y la conectividad de red a través de simulación de tráfico

-   Validación de túnel dividido

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Ejecutar el organizador de la red (a través de MyAdvisor) para sitios y roles en el ámbito

Antes de la presentación de servicios de comunicación en tiempo real, al igual que los equipos en su entorno, es importante para asegurarse de que la red se ha correctamente optimizada y tamaño de una ExpressRoute de Azure (si procede), internet y perspectiva de ancho de banda WAN.

Para ayudar a determinar la cantidad de ancho de banda y el nivel de optimización de la red necesaria para sitios de ámbito que admite la implementación, completar la herramienta de [Planeación de red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) (a través de MyAdvisor) para validar la preparación de la red de su organización necesita. Para obtener instrucciones adicionales sobre cómo determinar los requisitos de red para los equipos a través del organizador de la red, consulte MyAdvisor: organizador de red.

> [!TIP]
>   Para obtener información adicional acerca de la ficha de **recomendaciones** , con ejemplos de cómo configurar e interpretar los resultados, vea el organizador de la red [Información general de las recomendaciones](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp).



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decidir qué sitios de red están en el ámbito para la implementación de los equipos de servicios.</li><li>Decidir los roles necesarios para modalidades de los equipos en el ámbito.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Complete el organizador de la red (a través de MyAdvisor) para la lista de sitios que están en el ámbito.</li><li>Validación del organizador de la red de documentos da como resultado la plantilla de resultados de plan de prueba proporcionada.</li><li>Validar que el ExpressRoute (si procede), internet y ancho de banda de WAN que se ha calculado para sitios de ámbito se alinea a los valores de ancho de banda que están asignados actualmente.</li><li>Para los sitios que no tengan el ancho de banda adecuado, ejecutar planes de escalación y corrección para resolver los problemas de ancho de banda.</li><li>Establecer una red de supervisión de soluciones para sitios de ámbito para supervisar el uso de ancho de banda y QoS para segmentos WAN, internet y ExpressRoute (si procede).</li><li>Programar una reunión del Comité de dirección para revisar los resultados del organizador de la red.</li><li>Presentar los resultados en el Comité de dirección para identificar las áreas que requieren la corrección de planeación de ancho de banda.</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>Evaluación de la configuración de QoS para sitios de ámbito
---------------------------------------------

Como parte de validación de preparación de la red para admitir comunicaciones en tiempo real de los equipos, es igualmente importante para asegurarse de que la red haya sido configurada correctamente y se optimizado desde una perspectiva de QoS.

Para obtener instrucciones adicionales sobre cómo configurar, implementar y validar la preparación de la red QoS para los equipos mediante la directiva de grupo, vea [Habilitación de QoS para equipos](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decida en la configuración de QoS que se va a implementar.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Configuración de QoS.</li><li>Ejecutar QoS validación tal como se describe en los pasos que se indican a través de la "validar a través de GPO" y "validar a través del analizador de mensajes" en las secciones anteriores.</li></ul></td></tr>
</table>


### <a name="document-qos-configuration-validation-test-results"></a>Resultados de pruebas de validación de configuración de QoS de documentos

Una vez completada pruebas mediante el uso de directiva de grupo para los sitios en el ámbito de la validación de QoS, cree un informe que resuma los resultados de las pruebas para presentar durante la revisión final Comité de dirección.

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>Sitio r: validar la configuración de QoS pruebas de informe de resumen

> [!TIP]
>   A continuación es un ejemplo prueba la plantilla de informe de resumen que puede revisar durante la próxima reunión del Comité de dirección cuando decida a incorporado sistema telefónico con planes de llamar a servicios en la fase de prueba piloto.


**Validar la configuración de QoS a través de GPO y del analizador de mensaje**

**Resumen de los resultados**:&nbsp;&nbsp;&nbsp;& #9744; Pasar&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Conmutación por error

<table>
<tr><th colspan="2">Aspectos destacados de pruebas </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Prueba de relieve  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Corrección:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores de elementos identificados </td></tr>
<tr><td>**Bloqueador de elementos**: TBD</td><td>**Corrección**: TBD</td></tr>
</table>


> [!TIP]
> Para facilitar la discusión más durante la revisión final Comité de dirección, se puede usar la actualizada [matriz de resultados de las pruebas](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para documentar y resaltar áreas adicionales que requieren corrección.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar los resultados de prueba de QoS para asegurarse de que los equipos que el tráfico de medios en tiempo real se está correctamente marcado y prioriza.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Resultados de pruebas de QoS de documento en la plantilla de resultados de plan de prueba proporcionada.</li><li>Ejecutar planes de escalación y corrección para resolver los problemas que QoS no estar correctamente configurado o no laborable como se espera para admitir el tráfico de medios de los equipos.</li></ul></td></tr><li>Programar una reunión del Comité de dirección para revisar el resumen de resultados de prueba.</li><li>Presente resumen resultados de las pruebas para el Comité de dirección para identificar las áreas que requieren corrección.</li>
</table>


<a name="execute-split-tunnel-enablement-validation"></a>Ejecutar la validación de la habilitación de túnel dividido
------------------------------------------

Es habitual para empresas hoy en día tener una o varias soluciones para proporcionar acceso remoto, como una red privada virtual o VPN. Estas soluciones habilitar la conectividad con los activos internos de línea de negocio y las aplicaciones de forma segura y fiable.

Aunque las soluciones de acceso remoto pueden funcionar muy bien para dar acceso a algunas aplicaciones, cuando se trata de túnel el tráfico de medios en tiempo real de los equipos, estas soluciones con frecuencia como resultado una experiencia de usuario menos óptimo para todos los participantes de un audio de los equipos escenario llamada o conferencia.

Para asegurarse de que el tráfico de medios de los equipos no *no* recorrido soluciones de acceso remoto en su entorno, se necesitarán una configuración de túnel de división.

Para obtener instrucciones adicionales sobre cómo configurar y validar la preparación de la red de configuración de túnel de división para los equipos, vea Preparación de la [red](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!NOTE]
>   Debido al gran volumen de las soluciones de acceso remoto disponibles en el mercado, este documento no proporciona detalles específicos de proveedor, instrucciones generales acaba por qué deben configurarse en soluciones de acceso remoto.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decidir la configuración de túnel de división para implementar.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Implementar la configuración de túnel de división.</li><li>Probar y validar la configuración de túnel de división.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>Resultados de pruebas de validación de documento configuración de túnel dividido

Una vez completada la configuración de túnel de división prueba para sitios de ámbito, crear un informe que resuma los resultados de pruebas y presentar durante la siguiente revisión del Comité de dirección.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>Sitio r: validar la configuración dividido túnel pruebas de informe de resumen

> [!TIP]
>   A continuación es un ejemplo prueba la plantilla de informe de resumen que puede revisar durante la próxima reunión del Comité de dirección cuando decida a incorporado sistema telefónico con planes de llamar a servicios en la fase de prueba piloto.

**Validar la configuración de túnel dividido**

**Resumen de los resultados**:&nbsp;&nbsp;&nbsp;& #9744; Pasar&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Conmutación por error

<table>
<tr><th colspan="2">Aspectos destacados de pruebas </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Prueba de relieve  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Corrección:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores de elementos identificados </td></tr>
<tr><td>**Bloqueador de elementos**: TBD</td><td>**Corrección**: TBD</td></tr>
</table>


> [!TIP]
> Para facilitar la discusión más durante la revisión final Comité de dirección, se puede usar la actualizada [matriz de resultados de las pruebas](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para documentar y resaltar áreas adicionales que requieren corrección.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar los resultados de las pruebas de división túnel para asegurarse de que el tráfico en tiempo real de los equipos se excluye de la solución de acceso remoto.</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar los resultados de pruebas de conectividad de túnel de división en la plantilla de resultados de plan de prueba proporcionado.</li><li>Ejecutar planes de escalación y corrección para resolver los problemas donde enrutamiento correcto es posible que no existe para admitir la media de los equipos dentro de una configuración de túnel de división.</li><li>Programar una reunión del Comité de dirección para revisar el resumen de resultados de prueba.</li><li>Presente resumen resultados de las pruebas para el Comité de dirección para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>Ejecutar la validación de conectividad y rendimiento de red mediante el uso de la herramienta de evaluación de la red de Microsoft
-----------------------------------------------------------------------------------------------------------

La herramienta de evaluación de la red de Microsoft realiza pruebas del tráfico de simulación y la conectividad de transmisión por secuencias simulado los paquetes de audio, para un período predefinido y el número de iteraciones, en el sitio de borde más cercano que proporciona conectividad con el servicio de los equipos. Un objetivo de esta prueba es evaluar las métricas de rendimiento de red para la pérdida de paquetes, vibración, latencia de ida y vuelta y porcentaje de reaprovisionamiento de paquete de cada llamada simulado. Además, la prueba valida que se permite una conectividad adecuada entre interna y perimetral elementos de red a todos los puntos de entrada de borde que admiten la conectividad a los servicios de los equipos.

Para obtener instrucciones adicionales sobre cómo confirmar y evaluación de la preparación de la red de los equipos para sitios designados en el ámbito, vea Preparación de la [red](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!TIP]
>   Para completar el análisis de preparación de red y preparación para sitios de ámbito, designar un cliente potencial para cada sitio Web que puede ayudarle con los esfuerzos de evaluación de preparación de red.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decidir la evaluación de la red y el perfil de pruebas de conectividad para sitios de ámbito.</li><li>Decidir los requisitos de archivo de configuración de evaluación de red para los sitios en el ámbito.</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Configurar requisitos de archivos de configuración de evaluación de red para los sitios en el ámbito.</li><li>Ejecutar la validación de rendimiento y la conectividad de la red para los sitios en el ámbito.</li></ul></td></tr>
</table>



### <a name="document-network-connectivity-and-performance-validation-test-results"></a>Resultados de pruebas de validación de rendimiento y la conectividad de red de documentos

Una vez haya completado todas las pruebas de rendimiento para los sitios en el ámbito y conectividad de red, crear un informe que resuma los resultados de pruebas y presentar durante la siguiente revisión del Comité de dirección.

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>Sitio A: informe de resumen de conectividad y rendimiento de la red

> [!TIP]
> A continuación es un ejemplo red conectividad y rendimiento de resumen de plantilla que puede usar durante la siguiente revisión del Comité de dirección al determinar la preparación de la red general para los sitios en el ámbito.

**Ubicación: Seattle [inside cableada] cliente a los resultados de Office 365**

**Resumen de los resultados**:&nbsp;&nbsp;&nbsp;& #9744; Pasar&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Conmutación por error 



| Métrica                                                        | Target                                                                                                            | Weekday: horario de oficina 9:30 A.M. a 11:00 A.M.                                                                                                                                                                                                                                                                                                 | Weekday: las horas de oficina 2:30 P.M. a 4:30 P.M. | Día de la semana: después del horario laboral 10:30 P.M. a 12:30 A.M. | Fin de semana: después del horario laboral 9:30 A.M. a 11:30 AM | Fin de semana: después del horario laboral 2:30 P.M. a 4:30 P.M. |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| Latencia (unidireccional)                                             | \<50 ms                                                                                                           | 40 ms                                                                                                                                                                                                                                                                                                                                     | 38 ms                                    | 41 ms                                     | 35 ms                                    | 36 ms                                   |
| Latencia (tiempo de ida y vuelta o RTT)                             | \<100 ms                                                                                                          | 81 ms                                                                                                                                                                                                                                                                                                                                     | 77 ms                                    | 80 ms                                     | 72 ms                                    | 70 ms                                   |
| Pérdida de paquetes de ráfaga                                             | \<10% durante un intervalo de 200 ms                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | % 2                                       | % 2                                        | 0,2%                                     | 0,1%                                    |
| Pérdida de paquetes                                                   | \<% 1 durante cualquier intervalo de 15 segundos                                                                                   | 0,4%                                                                                                                                                                                                                                                                                                                                      | 0,3%                                     | 0,3%                                      | 0,1%                                     | 0 %                                      |
| Vibración de llegada entre granjas de paquetes                                   | \<30 ms durante un intervalo de 15 segundos                                                                                | 12 ms                                                                                                                                                                                                                                                                                                                                     | 11 ms                                    | 13 ms                                     | 5 ms                                     | 5 ms                                    |
| Reordenamiento de paquetes                                                | \<paquetes de salida de orden 0,05%                                                                                      | 0 %                                                                                                                                                                                                                                                                                                                                        | 0 %                                       | 0 %                                        | 0 %                                       | 0 %                                      |



<table>
<tr><th colspan="2">Aspectos destacados de pruebas </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Prueba de relieve  </th></tr> 
<tr><td>**Problema**: latencia alta</td><td>**Corrección:** Investigar el enrutamiento de paquetes e implementar la ruta ideal.</td></tr>
<tr><td>**Problema**: double la latencia no es el tiempo de ida y vuelta</td><td>**Corrección:** Investigue un posible problema de configuración del firewall o enrutador. Investigar las rutas de tráfico.</td></tr>
<tr><td>**Problema**: alta pérdida de paquetes </td><td>**Corrección:** A través del organizador de la red, compruebe que se ha asignado suficiente ancho de banda. </td></tr>
<tr><td>**Problema**: vibración alta </td><td> **Corrección:** Investigue si se usan los valores de punto (DSCP) de código de servicios diferenciados correcta. </td></tr>
<tr><td>**Problema**: alta pérdida de paquetes </td><td>**Corrección:** Investigue la pérdida de paquetes. </td></tr>
<tr><td>**Problema**: reaprovisionamiento de paquetes alta </td><td>**Corrección:** Investigar el ancho de banda y la cola de enrutador. </td></tr>
<tr><th colspan="2">Bloqueadores de elementos identificados </td></tr>
<tr><td>**Bloqueador de elementos**: TBD</td><td>**Corrección**: TBD</td></tr>
</table>

 


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluación de la evaluación de la red y los resultados para asegurarse de que cumple con los requisitos descritos en el [rendimiento de conectividad de red y calidad Media](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) para el segmento de borde y segmentos de cliente de pruebas de conectividad.</li><li>¿Se evalúa las capacidades de red para la compatibilidad con multimedia en tiempo real para todos los sitios en el ámbito?</li><li> ¿Si no ha evaluado correctamente la red o sabe que no se admite la multimedia en tiempo real, se deshabilitará vídeo y capacidades de uso compartido de pantalla para reducir la red un impacto y mejoran la experiencia de los equipos de los usuarios?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Rendimiento de la red y los resultados de pruebas de conectividad de documentos.</li><li>Ejecutar planes de escalación y corrección para resolver los problemas con los sitios donde no hay suficiente ancho de banda, o no se cumplen los requisitos de rendimiento y la conectividad de red.</li><li>Programar una reunión del Comité de dirección para revisar el resumen de resultados de prueba.</li><li>Presente resumen resultados de las pruebas para el Comité de dirección para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


<a name="execute-subscriber-number-port-validation"></a>Ejecutar la validación del puerto número de suscriptor
-----------------------------------------

Si necesita transferir números como parte de proporcionar las funciones de entrada y salida de llamadas en el sistema telefónico con planes de llamar a servicios compatibles con los equipos, debe realizar un puerto parcial para un número de servicio. Esto le ayudará a validar las expectativas, los requisitos y escala de tiempo razonable, tal y como se haya terminado de preparar la implementación del sistema de teléfono con planes de llamar a servicios en el entorno de producción.

Para completar un puerto parcial de un número de suscriptor de su proveedor de servicios de RTC actual en los equipos, recorra los pasos que se describen a continuación.

#### <a name="step-1"></a>Paso 1

Identificar el número de prueba que le gustaría usar para el puerto a Office 365 como un número (número de suscriptor) de usuario puede asignarse a se pasarán a través del sistema de teléfono con una llamada a los planes de servicio en los equipos.

> [!IMPORTANT]
>Al planear la prueba de traslado número, asegúrese de revisar las pautas más recientes para las solicitudes de traslado números en [Número de puerto de las preguntas más frecuentes](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions).

#### <a name="step-2"></a>Paso 2

Identificar y documentar toda la información de cuenta (incluido el nombre que se usa para la cuenta específica) para el operador actual del número de prueba que se va trasladar.
Normalmente, puede encontrar la información que necesitará en la lista más reciente o la factura de su proveedor de servicio actual.

> [!TIP]
>   Puede trasladar o números de teléfono de transferencia dentro de todos los países o regiones; admiten actualmente Sin embargo, la forma de enviar una solicitud de orden de puerto podría variar según el país o región donde se proceden de los números de teléfono. Para obtener la lista más reciente de países o regiones admitidas actualmente, vea [países y la disponibilidad de la región para las conferencias de Audio y planes de llamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

>   Para obtener información adicional acerca de cómo transferir los números de teléfono al sistema de teléfono con planes de llamada — junto con las restricciones de posibles — vea [transferir los números de teléfono a Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) y [Marcar gratuito restricciones dentro de Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Paso 3

Descargue y cree una carta de autorización (LOA) para su país o región que se basa en "servicio de número" como el tipo de traslado número.

>[!NOTE]
>   Debido a que pueden diferir LOA formatos por país, la región o el tipo de número (que es geográfica frente a no geográficos o el número de usuario frente a servicio o número de teléfono gratuito), compruebe que está utilizando la plantilla LOA correcta correspondiente a su tipo de escenario específico. Consulte [descargar una carta de autorización (LOA)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) para obtener más información acerca de cómo elegir la LOA o vaya directamente a la [página de descarga](https://www.microsoft.com/download/details.aspx?id=49167).

>[!NOTE]
> **Sólo en los Estados Unidos**<br/>
>   Debido a que sólo nos estamos trasladar un número de servicio para esta prueba, asegúrese de seleccionar los campos adecuados en la LOA tal y como se muestra a continuación:

¿ ![Cómo muchos números de teléfono transferirá? Respuesta: Estoy sólo transferencia de algunas de Mis números de mi compañía actual.] ¿ (media/onboarding-test-plan-image1.png "Cómo muchos números de teléfono transferirá? Respuesta: Estoy sólo transferencia de algunas de Mis números de mi compañía actual.")

![¿Qué tipo de números de teléfono va a transferir? Respuesta: estoy transfiriendo los números de teléfono del servicio de voz como para operadores automáticos o puentes de conferencia.] (media/onboarding-test-plan-image2.png "¿Qué tipo de números de teléfono va a transferir? Respuesta: estoy transfiriendo los números de teléfono del servicio de voz como para operadores automáticos o puentes de conferencia.")

>[!IMPORTANT]
>   Cuando los números de teléfono puertos manualmente mediante el uso de un LOA, asegúrese de que seleccionar el tipo de número de teléfono correcto. Debe enviar una solicitud de portabilidad independiente para cada tipo de número de teléfono que desee transferir.<br/><br/>
>   Porque queremos probar el número trasladar el proceso mediante el uso de un número de teléfono asociado con el mismo número de facturación teléfono (BTN), debe asegurarse de que el número de teléfono de facturación *no* se incluye con el número de teléfono específico que se va a migrar.

#### <a name="step-4"></a>Paso 4

En el portal de administración de inquilinos, vaya a la ficha de **soporte técnico** y crear y enviar una solicitud de servicio. Adjunte el archivo LOA completado para programar el número de teléfono asociado con su proveedor de servicios actual para la migración. Para elegir el método de solicitud de servicio más adecuado para el tamaño de su inquilino, consulte [manualmente puede enviar una solicitud de servicio personalizado](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Una vez que se recibe la solicitud de soporte técnico, Microsoft Support realizará un seguimiento según el método de comunicación que ha elegido y avisarle de estado y los pasos siguientes para completar el proceso de traslado de números.

#### <a name="step-5"></a>Paso 5

Cuando se haya confirmado el número como tener se ha trasladado a través de como un nuevo número de suscriptor en Office 365, asignar el número para el sistema telefónico con planes de llamar al servicio desde el portal de administración de inquilinos \> **Skype para el centro de administración de negocio** \> ** Voz**. En la ficha **Números de teléfono** , asigne al nuevo número de servicio para el sistema telefónico con una llamada a los planes de servicio.

> [!TIP]
>   Aunque esta tarea asigna a un nuevo número de servicio al sistema de teléfono con planes de llamada, en el momento de escribir este artículo, la administración de esta tarea se completa mediante la Skype para el centro de administración de negocio.

#### <a name="step-6"></a>Paso 6

Ahora que ha asignado al número de puertos de suscriptor, inicie sesión en un cliente de los equipos como el usuario y un número de 10 dígitos externo a través de la RTC de marcado. Después de realizar la llamada, confirme que la llamada se ha conectado y que el identificador de autor de la llamada que se muestra coincide con el número de suscriptor que puertos.

#### <a name="step-7"></a>Paso 7

En un número externo de RTC, realice una llamada al número de suscriptor trasladado a Office 365 y compruebe que se recibió la llamada entrante y conectados a través del cliente de los equipos.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decidir qué números de suscriptor nacionales que necesitará para el puerto, por país o región.</li><li>Decidir qué plantilla LOA que va a utilizar.</li><li>Determinar si su operador de telefonía actual (perder portadora) permite la fragmentación de número de teléfono (es decir, permite parcial puerto pedidos).</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Recopilar la información necesaria y preparar la LOAs.</li><li>Descargar y completar las plantillas LOA que necesita.</li><li>Enviar una solicitud de traslado número de suscriptor.</li><li>Ejecutar pruebas de validación para los números de puertos asignando el sistema telefónico con planes de llamar al servicio de acceso telefónico y confirme que funcionan, tal como se describe en los pasos 6 y 7 anteriormente en esta sección.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Número de servicio trasladar los resultados de la prueba del documento

Una vez que haya completado todas las pruebas de número de suscriptor, cree un informe que resuma los resultados de las pruebas para presentar durante la siguiente revisión del Comité de dirección.

#### <a name="site-a-number-porting-test-summary-report"></a>Número de sitios r: trasladar el informe de resumen de prueba

> [!TIP]
>   A continuación es un ejemplo de plantilla de informe de resumen de prueba que puede usar para su revisión durante la próxima reunión del Comité de dirección cuando decida a incorporado sistema telefónico con planes de llamar a servicios en la fase de prueba piloto.

**Número de servicio al trasladar**

**Resumen de los resultados**:&nbsp;&nbsp;&nbsp;& #9744; Pasar&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Conmutación por error 

<table>
<tr><th colspan="2">Aspectos destacados de pruebas </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Prueba de relieve  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Corrección:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores de elementos identificados </td></tr>
<tr><td>**Bloqueador de elementos**: TBD</td><td>**Corrección**: TBD</td></tr>
</table>


> [!TIP]
>   Para facilitar la discusión más durante la revisión final Comité de dirección, puede usar la actualizada [matriz de resultados de pruebas](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) proporcionado por [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para documentar y resaltar áreas de prueba adicionales que requieren corrección.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar si los números de suscriptor enviados para la migración trasladados correctamente para el sistema telefónico con planes de llamar al servicio..</li><li>Evalúe si podían asignar al número de puertos de servicio para el sistema telefónico con una llamada a los planes de servicio.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Su número de trasladar los resultados de pruebas de documentos.</li><li>Ejecutar planes de escalación y corrección para resolver los problemas que ha experimentado con el proceso de traslado número, si hay alguno.</li><li>Programar una reunión del Comité de dirección para revisar el resumen de resultados de prueba.</li><li>Presentar los resultados de resumen de pruebas para el Comité de dirección para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


<a name="execute-your-test-plan-for-phone-system-with-calling-plans"></a>Ejecutar su plan de pruebas para el sistema telefónico con planes de llamada
----------------------------------------------------------

Ahora que ha definido su plan de pruebas, el siguiente paso es recorrer los casos de prueba, centrándose en la evaluación del sistema de teléfono con una llamada a los planes de administración y usuario Descubra las características en el ámbito. Antes de la prueba comienza realmente, compruebe que los requisitos previos de pruebas enumerados a continuación están en su lugar.

### <a name="phone-system-with-calling-plans-testing-prerequisites"></a>Sistema de teléfono con una llamada a planes de pruebas de los requisitos previos

-   Casos de uso de negocio se han definido para el sistema de teléfono con una llamada a los planes de servicio.

-   Se han identificado las partes interesadas clave.

-   La licencia se necesita para el sistema telefónico con planes de llamar a servicios está disponible y se ha asignado al grupo de usuarios en el ámbito.

-   Se han identificado la lista de sitios organizativos y grupos de usuarios en el ámbito.

-   [Créditos de comunicaciones](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (si es necesario) se han configurado para su organización.

-   Sistema telefónico con la configuración de planes de llamada se han identificado y configurado.

-   Plan de configuración que admiten el sistema telefónico con planes de llamada se han identificado, configurado y aplicado para el grupo de usuarios en el ámbito de marcado de inquilinos.

-   Teléfono del sistema con una llamada a planes de directivas se han identificado y configurados para el grupo de usuarios en el ámbito.

-   Se han identificado y configurados para el grupo de usuarios en el ámbito del sistema telefónico con los requisitos de cumplimiento de planes de llamada.

### <a name="document-phone-system-with-calling-plans-test-case-passfail-status"></a>Sistema de teléfono de documentos con el estado de aprobación o error de casos de prueba de planes de llamar a

Tal y como se evalúan casos de prueba para los equipos administrativos y características del sistema de teléfono de usuario en el ámbito, realizar un seguimiento de los resultados de cada caso de prueba para reflejar el estado de aprobación o parcial o error, junto con el identificador asignado de la defecto en caso de producen problemas imprevistos.

#### <a name="phone-system-with-calling-plans-test-case-status"></a>Sistema de teléfono con el estado de caso de prueba de planes de llamada

> [!TIP]
>   A continuación es un ejemplo de plantilla de estado de caso de prueba que puede utilizar para los resultados de pruebas de documento para su revisión durante la próxima reunión del Comité de dirección cuando decida a incorporado sistema telefónico con planes de llamar a servicios en la fase de prueba piloto.

| Sistema telefónico con Planes de llamada          |                              |                                                                                            |                           |                                                                            |
|------------------------------------------|------------------------------|--------------------------------------------------------------------------------------------|---------------------------|----------------------------------------------------------------------------|
| Identificador de caso de prueba                             | Título del caso de prueba              | Descripción del caso de prueba                                                                      | Resumen de resultados de caso de prueba | Identificador de defecto asignado (si procede)                                         |
| 1                                        | Realizar llamadas salientes de RTC. | Realizar una llamada saliente marcando un número de 10 dígitos nacional.                              |    & #9744; Pase<br/>& #9744; Parcial<br/> & #9744; Conmutación por error                   | Cuando un usuario escribe un número de cuatro dígitos, se produce un error en la llamada realizada a la RTC. |



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar el estado de aprobación o error de casos de prueba de alto nivel por sitio para el sistema telefónico con una llamada a los planes de características en el ámbito.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documente los resultados de estado de caso de prueba para todos los casos de prueba completados en el ámbito.</li><li>Programar una reunión del Comité de dirección para revisar el resumen de resultados de prueba.</li><li>Presentar los resultados de estado de caso de prueba para el Comité de dirección para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


### <a name="document-phone-system-with-calling-plans-testing-result-summary"></a>Sistema de teléfono de documentos con una llamada a planes de resumen de resultados de las pruebas

Después de todos los casos de prueba de compatibilidad con el sistema telefónico con planes de llamar a las características de ámbito de sitio se hayan completado, documentar los resultados para revisar durante una reunión del Comité de dirección al decidir cuándo se debe habilitar sistema telefónico con planes de llamar a servicios en la prueba piloto fase.

#### <a name="site-a-phone-system-with-calling-plans-test-case-summary-report"></a>Sitio r: de teléfono del sistema con una llamada a los planes de informe de resumen de caso de prueba:

> [!TIP]
>   A continuación es un ejemplo de plantilla de informe de resumen de prueba que puede revisar durante la próxima reunión del Comité de dirección cuando decida a incorporado sistema telefónico con planes de llamar a servicios en la fase de prueba piloto.


**Sistema de teléfono de los equipos con planes de llamada**

**Resumen de los resultados**:&nbsp;&nbsp;&nbsp;& #9744; Pasar&nbsp; &nbsp; &nbsp; & #9744; Parcial&nbsp; &nbsp; &nbsp; & #9744; Conmutación por error 

<table>
<tr><th colspan="2">Aspectos destacados de pruebas </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Prueba de relieve  </th></tr>  
<tr><td>**Problema**: TBD</td><td>**Corrección:** TBD</td></tr>
<tr><th colspan="2">Bloqueadores de elementos identificados </td></tr>
<tr><td>**Bloqueador de elementos**: TBD</td><td>**Corrección**: TBD</td></tr>
</table>


> [!TIP]
>   Para facilitar la discusión más durante la revisión final Comité de dirección, puede usar la actualizada [matriz de resultados de pruebas](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) proporcionado por [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para documentar y resaltar áreas adicionales que requieren corrección.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Evaluar los resultados de prueba de alto nivel resumen por sitio para el sistema telefónico con una llamada a los planes de características en el ámbito.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>El informe de resumen de caso de prueba del documento después de que se hayan completado todos los resultados de caso de prueba.</li><li>Programar una reunión del Comité de dirección para revisar el resumen de resultados de prueba.</li><li>Presente resumen resultados de las pruebas para el Comité de dirección para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>



<a name="present-and-report-phone-system-with-calling-plans-test-findings"></a>Resultados de las pruebas presente e informe del sistema de teléfono con planes de llamada
----------------------------------------------------------------

Después de todo se hayan completado las actividades de pruebas y los defectos con un impacto de baja se han resueltos, programar una reunión de cierre final con las partes interesadas de pruebas designadas. En la reunión, dirección:

-   Resumen de estado

-   Resaltado y relieve

-   Lecciones aprendidas

-   ¿Recomendación general, continúe con la fase de prueba piloto o volver a evaluar los resultados de pruebas?

-   Probar los resultados de la matriz (estos deberían estar plenamente documentados en el apéndice)

#### <a name="test-plan-deliverables"></a>Entregas del plan de pruebas:

> [!TIP]
>   A continuación es un ejemplo de un plan de pruebas de plantilla de entrega que pueden usar para documentar los criterios necesarios para lograr el cierre de sesión y salir de la fase de pruebas o suspender las pruebas hasta que estén completamente resueltos todos los problemas identificados.

| Resumen de estado               | Información destacada/relieve | Lecciones aprendidas | Recomendación de cierre |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Tasa de pass de caso de prueba de TBD %</li><li>Todas las pruebas se pasan</li></ul> | TBD                  | TBD             | Continúe con la prueba piloto       |

-   Todas las pruebas se pasan


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Puntos de decisión</td><td><ul><li>Decidir el resumen de estado de prueba.</li><li>Identificar relieve y temas destacados de pruebas.</li><li>Identificar lecciones aprendidas.</li><li>Decidir qué corrección permanecen acciones, si hay alguno.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Resultados de resumen de la prueba de documento para incluir:<ul><li>Resumen de estado</li><li>Información destacada/relieve</li><li>Lecciones aprendidas</li></ul></li><li>Programar una reunión final Comité de dirección para revisar los resultados de pruebas.</li><li>Presente resultados de resumen de prueba durante un Comité de dirección de revisión para obtener la último inicio de sesión para salir de la fase de pruebas.</li></ul></td></tr>
</table>
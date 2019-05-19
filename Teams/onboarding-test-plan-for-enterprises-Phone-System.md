---
title: Plan de pruebas de empresa para Sistema telefónico con planes de llamada en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Valide que las expectativas de la organización se cumplan probando el sistema telefónico en las características, la funcionalidad y la utilidad de Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1534c1b327e7fda146894430ca750f01c53e8fa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898757"
---
<a name="define-and-document-your-phone-system-with-calling-plans-in-teams-test-plan-for-enterprises"></a>Definir y documentar el sistema telefónico con planes de llamadas en el plan de pruebas de Teams para empresas 
============================================================================================

Después de definir y documentar el sistema telefónico con planes de llamadas en Teams Business planes de éxito y de implementación técnica como parte de la fase de previsión, el siguiente paso consiste en validar que se cumplen las expectativas y los requisitos de la organización mediante características, funcionalidad y facilidad de uso. Debe realizar este paso de validación antes de implementar una implementación piloto o final en su entorno de producción.

Puede aprovechar el plan de éxito empresarial que definió durante la fase de enVision para servir como base para determinar las actividades, expectativas, casos de pruebas de características/funcionalidades y ámbito general que se evaluará durante la fase de pruebas.

<a name="identify-testing-support-stakeholders"></a>Identificar a los participantes de soporte técnico de pruebas
-------------------------------------

A medida que se prepara para evaluar el sistema telefónico con características de planes de llamadas, cree una matriz de la parte interesada de soporte técnico para identificar los roles necesarios para admitir la fase de pruebas.

> [!TIP]
> A medida que rellene la matriz de partes más interesadas de Teams, es posible que vea que algunos roles son iguales a los identificados durante la fase de previsión, pero con descripciones de roles inclinadas para las pruebas. Es posible que necesite identificar roles adicionales, en función de los requisitos únicos de los escenarios de pruebas.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Teams probando compatibilidad matriz matriz

> [!TIP]
> 
> A continuación se muestra un ejemplo de una plantilla de partes de la ayuda de pruebas que puede usar para documentar qué partes interesadas necesita para admitir la fase de pruebas.

| Rol                          | Descripción de la función                                                                                                                                                                          | Recurso asignado, información de contacto y ubicación |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Prueba de los patrocinadores ejecutivos  | <ul><li>Garantizar que las características de Team cumplen las necesidades empresariales; los patrocinadores ejecutivos están habituados a los principales resultados empresariales y los escenarios de casos de uso con prioridad.</li><li>Actúe como la máxima autoridad y asuma la responsabilidad de los equipos de pruebas de las características de Teams.</li><li>Ayudar a resolver problemas escalados por el responsable de pruebas.</li><li>Patrocinar la comunicación dentro de la empresa sobre los objetivos de la prueba.</li><li>Responsabilizarse de tomar decisiones clave.</li><li>Responsabilizarse de asegurar la disponibilidad de los recursos necesarios y el presupuesto para admitir los esfuerzos de pruebas.</li><li>Impulsa la conciencia y la compra de la campaña de pruebas con otras partes clave.</li><li>Actúe como patrocinador de pruebas durante la fase de evaluación de prueba.</li></ul>                                                 | DETERMINADO                                                  |
| Miembros del Comité de dirección    | <ul><li>Mantener el interés en y proporcionar instrucciones para la dirección general del sistema telefónico con la implementación del servicio de planes de llamadas.<li>Ayudar a promocionar los conocimientos estratégicos a través del impulso de la compra en toda la organización.</li></ul>                                                                        | DETERMINADO                                                  |
| Responsable de proyecto                  |<ul><li> Administrar y dirigir al equipo del proyecto.</li><li>Coordine socios y los equipos de trabajo que participan en el proyecto.</li><li>Sea responsable de crear y administrar planes de proyecto para cumplir con los resultados de los meses.</li><li>Resolver problemas de funciones cruzadas.</li><li>Proporcionar actualizaciones periódicas a los patrocinadores del proyecto.</li><li>Incorporar los conocimientos clave de la experiencia del usuario identificados en los resultados de la prueba en el plan de adopción de usuarios general.</li><li>Lidera las revisiones empresariales y operativas mensuales, contribuye a las revisiones trimestrales de la empresa.</li></ul>                                                                                                                                                         | DETERMINADO                                                  |
| Arquitecto/responsable de colaboración  | <ul><li>Responsabilizarse de la ejecución de la estrategia de colaboración definida por los ejecutivos de la empresa.</li><li>Analizar y elegir los productos de colaboración para la empresa que cumplan con los objetivos empresariales.</li><li>Responsabilizarse del diseño de las operaciones de los productos de colaboración.</li><li>Definir los modelos de funcionamiento y soporte técnico.</li><li>Contribuye a las revisiones mensuales y trimestrales de la empresa.</li></ul>                                                                                                 | DETERMINADO                                                  |
| Jefe de proyecto               | <ul><li>Desarrollar y mantener el plan del proyecto.</li><li>Administrar las entregas del proyecto en línea con el plan y el presupuesto del proyecto.</li><li>Grabe y administre problemas del proyecto, incluidas las escalaciones.</li><li>Realiza llamadas standup semanales.</li><li>Establecer un dedo y proporcionar actualizaciones a los patrocinadores ejecutivos de Project.</li><li>Trabaje con equipos internos de administración y comunicación de cambios para actualizar el enfoque de la administración de cambios y los planes de comunicación según sea necesario.</li></ul>                                                                                                                                                   | DETERMINADO                                                  |
| Responsable de redes                  | <ul><li>Proporciona información sobre el diseño de red durante la fase de detección.</li><li>Participar en la planificación durante los talleres de fase de previsión.</li><li>Coordine el trabajo del equipo de redes durante la ejecución del proyecto.</li></ul>                                                                                                                               | DETERMINADO                                                  |
| Responsable de seguridad                 | <ul><li>Proporcionar información sobre el diseño y los procesos de seguridad durante la fase de detección.</li><li>Participar en la planificación durante los talleres de fase de previsión.</li><li>Coordine el trabajo del equipo de seguridad durante la ejecución del proyecto.</li></ul>                                                                                                                | DETERMINADO                                                  |
| Responsable de telefonía                | <ul><li>Proporciona información sobre el diseño de telefonía durante la fase de detección.</li><li>Participar en la planificación durante los talleres de fase de previsión.</li><li>Coordine el trabajo del equipo de telefonía durante la ejecución del proyecto.</li></ul>                                                                                                                           | DETERMINADO                                                  |
| Responsable de escritorio                  | <ul><li>Proporciona información sobre los clientes y el proceso de actualización durante la fase de detección.</li><li>Participar en la planificación durante los talleres de fase de previsión.</li><li>Coordine el trabajo del equipo de escritorio durante la ejecución del proyecto.</li></ul>                                                                                                              | DETERMINADO                                                  |
| Representantes de la unidad de negocio | <ul><li>Participe en materiales y guías de adopción de usuarios.</li><li>Contribuya a y revise los casos de uso empresarial.</li></ul>                                                                                                                                   | DETERMINADO                                                  |
| Administradores de TI                     | <ul><li>Ayuda con la planificación y ejecución de pruebas (esta función es para los profesionales de TI).                                                                                                                       | DETERMINADO                                                  |
| Propietario del servicio                 | <ul><li>Será responsable del funcionamiento del sistema telefónico con el servicio de planes de llamadas, todo listo.</li><li>Actuar como propietario del sistema telefónico con el servicio de planes de llamadas.</li></ul>                                                                                                               | DETERMINADO                                                  |
| Probar Jefe/Administrador             | <ul><li>Defina el plan de pruebas, incluidas actividades, dependencias, entorno, objetivos, estrategia, reaprovisionamiento (entorno y humano) y la escala de tiempo necesaria para apoyar la fase de pruebas.</li><li>Coordinar la entrega y la preparación de las dependencias del plan de prueba.</li><li>Alinee con la prioridad correcta para la resolución de defectos.</li><li>Actuar como la ruta de remisión a cualquier problema de prueba que surja.</li><li>Comunique e informe el estado del plan de prueba con equipos internos y participantes designados.</li><li>Documente y presente resultados de pruebas finales.</li></ul> | DETERMINADO                                                  |
| Sistema telefónico con prueba de planes de llamadas     | <ul><li>Revise el plan de pruebas para comprender los requisitos de prueba, las metas, la escala de tiempo, la resolución de problemas y los casos de prueba que se van a ejecutar.</li><li>Revise y desarrolle casos de prueba que admiten sistemas telefónicos con los planes de llamadas aceptación y requisitos de funcionalidad.</li><li>Ejecutar casos de prueba y documentar resultados de pruebas.</li><li>Documentar defectos a medida que se producen y enviarlos al responsable de pruebas para la priorización y la resolución.</li><li>Pruebe los regresiones para cerrar los defectos después de confirmar la resolución del defecto.</li></ul>                                                                | DETERMINADO                                                  |
| Comprobador de red                | <ul><li>Revise el plan de pruebas para comprender los requisitos de prueba, las metas, la escala de tiempo, la resolución de problemas y los casos de prueba que se van a ejecutar.</li><li>Revise los casos de prueba compatibles con los requisitos de rendimiento y aceptación de red.</li><li>Ejecutar pruebas relacionadas con la disponibilidad de la red, incluidas la validación de rendimiento y conectividad de red, la validación de QoS y la configuración de túnel dividido.</li><li>Complete la validación del ancho de banda para los sitios en el ámbito con Planner de red mediante el programa de asesoría.</li><li>Documentar los resultados de la prueba de disponibilidad de red.</li><li>Documentar defectos a medida que se producen y enviarlos al responsable de pruebas para la priorización y la resolución.</li><li>Pruebe los regresiones para cerrar los defectos después de confirmar la resolución del defecto.</li></ul>                                                                | DETERMINADO                                                  |
| Evaluador de seguridad               | <ul><li>Revise el plan de pruebas para comprender los requisitos de prueba, las metas, la escala de tiempo, la resolución de problemas y los casos de prueba que se van a ejecutar.</li><li>Revise y desarrolle los casos de prueba que admiten requisitos de aceptación de seguridad.</li><li>Ejecute las pruebas relacionadas con la aceptación de seguridad para casos de prueba.</li><li>Documentar resultados de prueba de aceptación de seguridad.</li><li>Documentar defectos a medida que se producen y enviarlos al responsable de pruebas para la priorización y la resolución.</li><li>Pruebe los regresiones para cerrar los defectos después de confirmar la resolución del defecto.</li></ul>                                                                | DETERMINADO                                                  |
| Evaluador de telefonía              | <ul><li>Revise el plan de pruebas para comprender los requisitos de prueba, las metas, la escala de tiempo, la resolución de problemas y los casos de prueba que se van a ejecutar.</li><li>Revise los casos de prueba que admiten el traslado de número de servicio requisitos de aceptación y funcionalidad.</li><li>Ejecutar pruebas relacionadas con el traslado de números de servicio, incluido el puerto de números de servicio a Office 365.</li><li>Ejecutar casos de pruebas y documentar resultados de casos de pruebas.</li><li>Documentar defectos a medida que se producen y enviarlos al responsable de pruebas para la priorización y la resolución.</li><li>Pruebe los regresiones para cerrar los defectos después de confirmar la resolución del defecto.</li></ul>                                                                | DETERMINADO                                                  |
| Sistema telefónico con prueba de administración planes de llamadas | <ul><li>Revise el plan de pruebas para comprender los requisitos de prueba, las metas, la escala de tiempo, la resolución de problemas y los casos de prueba que se van a ejecutar.</li><li>Revise y desarrolle casos de prueba que admiten sistemas telefónicos con planes de llamadas requisitos de aceptación y funcionalidad.</li> <li>Ejecutar casos de pruebas y documentar resultados de casos de pruebas.</li><li>Documentar defectos a medida que se producen y enviarlos al responsable de pruebas para la priorización y la resolución.</li><li>Pruebe los regresiones para cerrar los defectos después de confirmar la resolución del defecto.</li></ul>                                                                | DETERMINADO                                                  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decida qué pruebas y roles de partes interesadas necesita para probar el sistema telefónico con las características de planes de llamadas de su entorno.</li><li>Decida qué recursos asignará para las funciones de soporte técnico de pruebas y de partes interesadas que identificó.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente las funciones de soporte técnico de pruebas y de partes interesadas en la matriz de participantes de la prueba de soporte.</li><li>Documente la información de contacto y los detalles de ubicación para cada recurso que enumere en la matriz de las partes más interesadas de la prueba.
</table>


<a name="define-phone-system-with-calling-plans-feature-requirements"></a>Definir un sistema telefónico con los requisitos de características de planes de llamadas 
------------------------------------------------------------

Como parte de la definición de un sistema telefónico con planes de llamadas características de los usuarios en el ámbito, vea [sistema telefónico con planes de llamadas](calling-plan-landing-page.md).
A continuación, evalúe el plan público más reciente de Teams para determinar:

-   El sistema telefónico con características de planes de llamadas que implementará para los usuarios en el ámbito.

-   Sistema telefónico de usuario esperado con los requisitos de la función planes de llamadas, dados su entorno actual de implementación de Skype empresarial, Exchange y SharePoint.

-   Si puede confirmar que el sistema telefónico con las características de planes de llamadas descritas en el plan público más reciente cumple con los requisitos de usuario, funcionalidad y ámbito en la escala de tiempo de su implementación

> [!TIP]
> La última guía básica de Microsoft para identificar el sistema telefónico con las características de los planes de llamadas en el <https://aka.ms/O365Roadmap>ámbito de la implementación puede encontrarse en.

Ahora que se ha definido el sistema telefónico con roles y características de planes de llamadas, los siguientes criterios de evaluación serán la experiencia de interoperabilidad con Teams. Para obtener más información sobre la experiencia de interoperabilidad junto con las opciones de configuración disponibles, consulte [Microsoft Teams y Skype for Business Interoperability](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability).

#### <a name="phone-system-with-calling-plans-feature-definition"></a>Sistema telefónico con definición de características de planes de llamadas

> [!TIP]
> A continuación se muestra un ejemplo de un sistema telefónico con una plantilla de definición de planes de llamada que puede usar para documentar el sistema telefónico con las características de administración de planes de llamadas y grupos de usuarios que se van a evaluar.


| Nivel empresarial   | Reuniones de colaboración    | Plataforma y dispositivos   | Profesional de ti  | Grupo de negocio adicional, específico del sitio  | Requisitos cumplidos por la última guía básica de Microsoft Teams |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Características de las llamadas del sistema telefónico:<ul><li>Transferencia ciega</li><li>Bloqueo de llamadas</li><li>Desvío de llamadas</li><li>Máscara de identificación de llamadas</li><li>Soporte técnico de E911</li><li>Marcado de extensión</li><li>Llamada en espera</li><li>Administración de llamadas múltiples</li><li>Llamadas simultáneas</li><li>Buzón de voz de Azure</li></ul></li><li>Soporte de plan de llamadas</li></ul> |<ul><li>Llamadas entre usuarios de Skype empresarial</li></ul> |<ul><li> Compatibilidad de características de reuniones de cliente de Windows, Mac Teams</li><li>Explorador de la característica reuniones de cliente de Teams para:<ul><li>Ventanas</li><li>Microsoft Edge</li></ul></li><li>compatibilidad con características de las reuniones cliente de iOS y Android Teams</li><li>Compatibilidad con TTY</li></ul> | <ul><li>Portal de diagnóstico de calidad de llamadas</li><li>Plan de marcado de inquilino</li><li>Directivas de identificación de llamadas de inquilino</li><li>Habilitar análisis de calidad de llamadas (CQD)</li></ul> | <ul><li>Validar las características de reunión de Teams basadas en la imagen de un equipo portátil corporativo</li><li>Compatibilidad con idiomas específicos</li><li>Configuración de GPO aplicada a un escenario de usuario determinado o un sitio específico</li></ul> | Sí  |




#### <a name="phone-system-with-calling-plans-user-functionality-definition"></a>Sistema telefónico con definición de funcionalidad de usuario planes de llamadas

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla de funcionalidad de usuario que puede usar para documentar la experiencia del usuario requerida en función del sistema telefónico con las características de planes de llamadas que se van a evaluar.


| Experiencia de Exchange                          | Experiencia de SharePoint                            | Experiencia de la Directiva de interoperabilidad de Teams |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Crear equipos (la creación de grupos de Office está habilitada)</li><li>Unirse a equipos</li><li>Crear canales</li><li>Crear y ver reuniones</li><li>Modificar la imagen de perfil de usuario</li><li>Agregar y configurar conectores</li><li>Agregar y configurar fichas</li><li>Agregar y configurar bots</li></ul> | <ul><li>Almacenar y compartir archivos en conversaciones de Teams</li><li>Almacenar y compartir y archivos en chats privados (basados en OneDrive)</li></ul> | <ul><li>ChatDefaultClient: valor predeterminado</li><li>CallingDefaultClient: valor predeterminado</li></ul>      |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li> Decida qué sistema telefónico con las características de la categoría planes de llamadas que implementará en su entorno.</li><li>Identifique su sistema telefónico de usuario con los requisitos de la función planes de llamadas de Skype empresarial, Exchange y SharePoint actuales.</li><li>Decidir qué experiencia de interoperabilidad entre equipos se implementará.</li><li>Revise los planes públicos más recientes de Teams y decida si las capacidades actuales de carga de trabajo cumplen su escala de tiempo de implementación.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente el sistema telefónico con las características de la categoría planes de llamadas necesarias para admitir su sistema telefónico con la implementación de planes de llamadas.</li><li>Documente el sistema telefónico de los usuarios con la función planes de llamadas y los requisitos de interoperabilidad dados su entorno actual de implementación de Skype empresarial, Exchange y SharePoint.</li><li>Documente si el plan público más reciente de los equipos del sistema telefónico con capacidades de planes de llamadas cumple con las necesidades empresariales y los requisitos de tiempo de la implementación.</li></ul></td></tr>
</table>

<a name="define-and-document-your-phone-system-with-calling-plans-test-plan"></a>Definir y documentar el sistema telefónico con el plan de pruebas de planes de llamadas
------------------------------------------------------------------

Una vez que haya definido el sistema telefónico con las características de los planes de llamadas en el ámbito, el siguiente paso es crear el plan de pruebas. En un nivel alto, el plan de pruebas abarca la estrategia general de pruebas y la metodología que usará para admitir la validación de características en el proceso de prueba.

En un nivel alto, el plan de pruebas debe incluir:

-   **Probando el ámbito:** Resume las áreas de foco (objetivos, escenarios y objetivos) que se evaluarán como parte de la fase de pruebas.

-   **Casos de prueba:** El conjunto de casos de prueba que se validarán para el sistema telefónico con características de planes de llamadas en el ámbito

-   **Probando recursos:** Matriz de recursos necesarios para apoyar el trabajo de pruebas de un punto de vista medioambiental, técnico y de personal

-   **Programación de pruebas (escala de tiempo):** Representa Cuándo comenzarán las pruebas, cuánto tiempo puede durar y cuándo se espera que finalice la fase de pruebas.

-   **Informes y corrección de defectos:** Pautas sobre cómo deberían comunicarse, controlarse y clasificar los problemas con las pruebas

-   **Evaluación y escalamiento de defectos:** Esquema sobre cómo y cuándo se debe iniciar la elevación de un defecto

-   **Criterios de salida y suspensión de prueba:** Orientación que describe los criterios para lograr la desconexión para salir de la fase de pruebas o pausar las pruebas hasta que se resuelvan los defectos prioritarios

-   **Entregas de prueba:** Resumen de los resultados que se desarrollarán y entregarán para admitir la aceptación y el cierre del proceso de pruebas.

> [!TIP]
>   Es posible que ya exista una metodología de prueba en la organización, pero las instrucciones a continuación reflejan los procedimientos recomendados que se pueden incluir o aprovechar por separado para probar las características de Teams en su entorno.

En las secciones siguientes encontrará instrucciones recomendadas adicionales que le ayudarán a tomar decisiones específicas, así como plantillas y temas que debe tener en cuenta a medida que completa el plan de pruebas.

### <a name="define-and-document-testing-scope"></a>Definir y documentar el ámbito de las pruebas

A medida que trabaja para desarrollar el plan de pruebas, debe definir el ámbito de la prueba en primer plano, resaltando la carga de trabajo y la lista de características que está evaluando.

El ámbito para evaluar correctamente el sistema telefónico con las características de planes de llamadas normalmente incluye:

-   Sistema telefónico con planes de llamadas preparación del sitio

-   Sistema telefónico con experiencia de usuario de planes de llamadas

-   Sistema telefónico con administración de planes de llamadas

#### <a name="phone-system-with-calling-plans-testing-scope"></a>Sistema telefónico con planes de llamadas con ámbito de prueba

> [!TIP]
>   A continuación se muestra un ejemplo de una plantilla de ámbito de prueba que puede usar para documentar el sistema telefónico con planes de llamadas y características de grupos de usuarios que se van a evaluar.

| Sistema telefónico con planes de llamadas preparación del sitio                                                                                                                                                                                    | Sistema telefónico con experiencia de usuario de planes de llamadas                                                                                                                                                                                         | Sistema telefónico con experiencia de administración de planes de llamadas                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>Planificación de ancho de banda de Network Planner (por medio de mi Asesor)<li></li>Validación de rendimiento y conectividad de red (a través de la herramienta de evaluación de redes de Skype empresarial)<li></li>Validación de calidad de servicio (QoS)<li></li>Acceso remoto-validación de túnel dividido</li></ul>|<ul><li>Características de PBX<li></li>Llamadas RTC (nacionales e internacionales)<li></li> Realizar y recibir llamadas RTC<li></li>Buzón de voz de Azure<li></li>E911<li></li>Plan de marcado de inquilino<li></li>Máscara de identificación de llamadas de inquilino <li></li>Características avanzadas de control de llamadas (por ejemplo, desvío de llamadas, llamadas simultáneas)</li></ul> |<ul><li>Asignación de licencias</li><li>Portabilidad de números de suscriptores a Office 365</li><li>Sistema telefónico con informes de llamadas a planes</li><li>Informes de calidad de llamadas (CQD)</li></ul> |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decida el sistema telefónico con el ámbito de las llamadas de planes mediante la identificación de las características que se evaluarán según el área de enfoque.</li><li>Decidir objetivos adicionales y objetivos para la evaluación.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente el sistema telefónico con las características de planes de llamadas para evaluarlas por área de enfoque.</li><li>Documentar objetivos y objetivos adicionales para la evaluación.</li></ul></td></tr>
</table>

### <a name="define-and-document-phone-system-with-calling-plans-test-cases"></a>Definir y documentar el sistema telefónico con los casos de prueba de planes de llamadas

Una vez que haya definido el sistema telefónico con las características de planes de llamadas, la implementación de clientes y los escenarios en paralelo con Skype empresarial (si procede), el siguiente paso es formular los casos de prueba necesarios para evaluar el sistema telefónico con las características de planes de llamadas de ID. En un nivel alto, los casos de prueba generalmente se agrupan por área de foco e incluyen:

-   **Título de caso de prueba:** Área de enfoque de la característica que la prueba está evaluando (por ejemplo, sistema telefónico con planes de llamadas)

-   **Descripción del caso de prueba:** Resumen de los objetivos de las características de prueba que se están evaluando

-   **Instrucciones de casos de prueba:** Pasos que debe seguir para ejecutar correctamente el caso de prueba que se está realizando

-   **Environment Required (requisitos previos):** Instrucciones de instalación necesarias para ejecutar la prueba correctamente

-   **Recurso requerido:** Recursos de personal necesarios para una evaluación y ejecución adecuada de la prueba

-   **Resultados esperados:** El resultado que esperas una vez completada la prueba correctamente

> [!NOTE]
>   Dado que el enfoque y el nivel de detalle necesarios para la creación de casos de prueba pueden variar dentro de la organización, es una buena idea seguir un enfoque que permita un nivel de detalle adecuado, pero que equilibre la rigurosidad con la práctica, para admitir las pruebas generales. capacidad.

> [!TIP]
>   Para obtener ayuda con la creación de casos de prueba como punto de partida, consulte la lista de instrucciones para el usuario del sistema telefónico disponible en las [reuniones y las llamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)de Teams.

#### <a name="phone-system-with-calling-plans-test-case"></a>Sistema telefónico con caso de prueba de planes de llamadas

> [!TIP]
>   A continuación se muestra un ejemplo de plantilla de caso de prueba que puede usar para documentar el sistema telefónico con planes de llamadas las características de grupos de usuarios que se van a evaluar.

Sistema telefónico con validación de planes de llamadas

| IDENTIFICADOR del caso de prueba | Título de caso de prueba               | Descripción del caso de prueba                                                  | Entorno necesario para la ejecución de casos de prueba                                               | Pasos necesarios para la ejecución de casos de prueba                                                                                                                                                          | Se necesita un recurso de prueba              |
|--------------|-------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| 1            | Realizar una llamada RTC saliente | Compruebe que puede realizar una llamada externa a un número de 10 dígitos. |<ul><li>Cliente de Teams instalado.</li><li>Usuario habilitado con las siguientes licencias de Office 365 asignadas:<ul><li>Office Enterprise E5 con sistema telefónico, Microsoft Teams y planes de llamadas nacionales e internacionales</li><li>Office Enterprise E3 con sistema telefónico, Microsoft Teams y planes de llamadas nacionales e internacionales</li></ul></li></ul> | <ol><li>Inicie sesión en el cliente de Teams.</li><li>Seleccione el teclado de marcado y escriba un número de 10 dígitos para marcar.</li><li>Compruebe que el dial de número esté correctamente normalizado y que se haya establecido la llamada RTC externa.</li></ol>    | Sistema telefónico con prueba de planes de llamadas |


> [!TIP]
>   Para obtener más información sobre cómo facilitar la creación individual de casos de prueba y el plan general para evaluar el sistema telefónico con las características de planes de llamadas de su organización, revise el [plan de pruebas del sistema telefónico](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) proporcionado por el [Asistente](https://myadvisor.fasttrack.microsoft.com/).


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decidir qué sistema telefónico con las características de usuario y administración de planes de llamadas se evaluarán.</li><li>Decidir qué entorno de prueba es necesario para admitir la ejecución de casos de prueba.</li><li>Decida los pasos necesarios para la evaluación de casos de prueba.</li><li>Decidir los recursos necesarios para la correcta ejecución de la prueba.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente los casos de prueba que se van a evaluar, en función de la plantilla de caso de prueba proporcionada.</li><li>Incluya la plantilla completada como parte de su plan de pruebas general.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>Definir y documentar recursos de prueba

Para apoyar la fase de pruebas, es importante que desarrolle un plan de recursos en el que se detallan las personas, el soporte y los recursos tecnológicos que necesitará. Un componente importante del plan general de pruebas, el plan de recursos le ayuda a determinar las dependencias que pueden existir y le da un sentido de alto nivel del soporte técnico de recursos que puede necesitar.

En un nivel alto, estos recursos suelen constar de:

-   **Personas**: partes interesadas

-   **Tecnología**: espacio empresarial, licencias, dispositivos

-   **Soporte técnico**: aprendizaje (tarjetas, vídeos), compatibilidad de administración con la ruta de escalamiento definida

#### <a name="testing-resource-requirements"></a>Comprobar los requisitos de recursos

> [!TIP]
>   A continuación se muestra un ejemplo de prueba de la plantilla de requisitos de recursos que puede usar para documentar los distintos tipos de recursos necesarios para admitir su fase de pruebas.


| Tipo de recurso | Recursos necesarios                                           | Descripción del recurso |
|---------------|--------------------------------------------------------------|----------------------|
| Personas        | Personas interesadas probar evaluadores de plomo                               | DETERMINADO                  |
| Tecnología    | Acceso a Office 365 con los siguientes servicios habilitados:<ul><li>Licencias de Office 365 E5 asignadas</li><li>Plan de llamadas nacionales e internacionales asignado</li></ul>    | DETERMINADO                  |
| Soporte técnico       | Técnico de prueba de administrador de prueba de soporte técnico de prueba | DETERMINADO                  |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decida los tipos de recursos (personas, tecnología y soporte técnico) que necesitará para admitir la fase de pruebas.</li><li>Decida los recursos específicos necesarios para los tipos de recursos que identificó.</li><li>Decida si debe proporcionar más información para describir los tipos de recursos que necesita.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente los tipos de recursos (personas, tecnología y soporte técnico) que necesitará para admitir la fase de pruebas.</li><li>Documente los recursos específicos necesarios para los tipos de recursos que identificó.</li><li>Si decide que es necesario, documente más información sobre los tipos de recursos que necesita para admitir la fase de pruebas.</li></ul></td></tr>
</table>


### <a name="define-and-document-a-testing-timeline"></a>Definir y documentar una escala de tiempo de prueba

Como parte de la definición del plan de pruebas, cree una escala de tiempo que deslinee la programación para cuando desee completar actividades de pruebas y lograr hitos de alto nivel.

En un nivel alto, generalmente se compone de:

-   **Tarea:** Se completará la actividad de alto nivel

-   **Hito:** Objetivo de alto nivel o progreso que se completó

-   **Recurso requerido:** Probar los recursos necesarios para admitir la entrega del hito o de la tarea identificados

-   **Fecha de Inicio:** La fecha en la que se inició la actividad, el hito o la tarea

-   **Fecha de finalización:** La fecha en la que espera que se complete la actividad, el hito o la tarea

-   **Propietario:** Recurso asignado al responsable de garantizar que la actividad, el hito o la tarea se completa a tiempo, de acuerdo con la fecha de finalización

-   **Estimación:** Número de horas que anticipan los recursos asignados para asegurarse de que la actividad, el hito o la tarea se completan a tiempo

#### <a name="testing-scheduling-and-timeline-requirements"></a>Comprobar los requisitos de programación y escala de tiempo

> [!TIP]
>   A continuación se muestra un ejemplo de una plantilla de requisito de pruebas de escala de tiempo que puede usar para documentar las fechas anticipadas cuando se completarán las actividades de pruebas específicas o se entreguen los hitos.

| Tarea                                                 | Económico       | Fecha de inicio                                                             | Fecha de finalización | Propietario | Recursos asignados | Cálculos |
|------------------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Informe de prueba                                          | DETERMINADO             | DETERMINADO                                                                    | DETERMINADO             | DETERMINADO   | DETERMINADO                | Horas TBD  |
| Ejecución de casos de prueba: sistema telefónico con planes de llamadas | DETERMINADO             | DETERMINADO                                                                    | DETERMINADO             | DETERMINADO   | DETERMINADO                | Horas TBD  |
| Ejecución de casos de prueba: disponibilidad de red               | DETERMINADO             | DETERMINADO                                                                    | DETERMINADO             | DETERMINADO   | DETERMINADO                | Horas TBD  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decida la actividad de escala de tiempo, el hito y las tareas de las que necesita realizar un seguimiento.</li><li>Decida qué recursos tendrá que asignar.</li><li>Decida la fecha que espera que se haya hecho.</li><li>Identifique el propietario de la entrega.</li><li>Decida cuánto tiempo tardará en completarse la actividad, el hito o la tarea.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente la escala de tiempo de la prueba con la plantilla proporcionada e incluya:<ul><li>Actividad de escala de tiempo, hito y tareas en las que es necesario realizar un seguimiento.</li><li>Recursos que deben asignarse.</li><li>Fecha de finalización anticipada.</li><li>Propietario de la entrega.</li><li>Tiempo necesario para completar la actividad, el hito o la tarea.</li></ul></li><li>Incluya la plantilla completada como parte de su plan de pruebas general.</li></ul></td></tr>
</table>


### <a name="define-and-document-test-defect-report-criteria"></a>Definir y documentar criterios de informe de defectos de prueba

A medida que se ejecutan casos de prueba dentro de una fase o una secuencia determinada, pueden surgir problemas cuando el resultado del caso de prueba que se está ejecutando no es lo que se espera.

Cuando se producen estos tipos de resultados, deben registrarse en un informe de defectos y un plan de corrección que se transfiere al jefe de pruebas designado para su revisión, creación de informes y resolución de defectos.

Normalmente, un informe de defectos y un plan de correcciones incluye lo siguiente:

-   **Identificador de defecto:** Número asignado al problema

-   **Identificador de caso de prueba afectado**: el número asignado al caso de prueba que se estaba evaluando en el momento en que se identificó el defecto

-   **Descripción del defecto:** Resumen del problema

-   **Entorno/pasos para reproducir:** Resumen de la configuración del entorno de pruebas, junto con los pasos exactos necesarios para reproducir el problema

-   **Gravedad del defecto**: el impacto del problema, que va desde impedir que el caso de prueba se apruebe hasta su aceptación con un riesgo mínimo. Algunos ejemplos pueden incluir:

-   **Bajo:** El problema tiene poco impacto y no evitará que el caso de prueba logre la aceptación si el problema se puede resolver más tarde.

-   **Medio:** El problema tiene una repercusión considerable, pero no evitará que el caso de prueba logre la aceptación si el problema se puede resolver antes de que se complete la fase de pruebas.

-   **Alto:** -el problema es importante en el caso de prueba. El problema debe resolverse antes de que se acepte el caso de prueba.

-   **Estado:** ¿Se ha solucionado el problema, está abierto o aún está en investigación?

-   **Enviado por:** El evaluador que notificó el problema

-   **Propietario asignado:** El recurso asignado del equipo de pruebas responsable de resolver el problema

-   **Detalles de soporte:** Esto puede incluir, entre otros, registros del cliente, capturas de pantalla o vídeo del problema.

A medida que los evaluadores ejecutan los casos de prueba indicados en su plan de pruebas, deben asegurarse de completar un informe de defectos y un plan de corrección de los problemas que surjan.
Esto resaltará el posible impacto que podría impedir o incluso detener el proceso de evaluación de las pruebas.

#### <a name="testing-defect-report-and-remediation-plan"></a>Probar el informe de defectos y el plan de corrección

> [!TIP]
>   A continuación se muestra un ejemplo de informe de defectos y plantilla de plan de correcciones que puede usar para documentar los problemas descubiertos durante la fase de pruebas.

| IDENTIFICADOR de defecto                                | IDENTIFICADOR de caso de prueba afectado | Descripción de defectos                                                                                 | /Steps de entorno para reproducir                                                                                                | Gravedad | Statu | Enviado por | Propietario asignado | Detalles complementarios (registros, capturas de pantallas, etc.) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Cuando el usuario escribe una extensión de cuatro dígitos, intenta realizar una llamada saliente, la llamada falla. | En el cliente de Teams, seleccione el teclado de marcado, escriba una extensión de cuatro dígitos y seleccione el icono del teléfono para intentar realizar la llamada. | Medio   | Liquida | Louis Lahr   | Lisa gris      | Registro del cliente de Teams<br/> Captura de pantalla del cliente de Teams     |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decidir qué niveles de gravedad de los criterios de defectos asignaremos para admitir el trabajo de pruebas.</li><li>Decida qué criterios de evaluación de los informes de defectos va a documentar si surgen problemas durante las pruebas.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente los criterios de informes de defectos de pruebas necesarios en la plantilla proporcionada.</li><li>Incluya la plantilla completada como parte de su plan de pruebas general.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Definir y documentar los criterios de salida y suspensión

Como parte del proceso general de ejecución del plan de pruebas, debe definir criterios para indicar el punto en el que debe suspender las pruebas y los requisitos que deben cumplirse para obtener la aprobación y salir de la fase de pruebas.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Criterios de salida y suspensión del plan de prueba

> [!TIP]
>   A continuación se muestra un ejemplo de la plantilla de criterios de salida y suspensión que puede usar en su plan de pruebas para documentar los criterios necesarios para obtener la aprobación, salir de la fase de pruebas o suspender actividades de prueba.

| Criterios de salida de prueba                            | Criterios de suspensión de pruebas                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>Todos los casos de prueba deben alcanzar una tasa de paso de% TBD</li><li>Todos los casos de prueba deben haberse ejecutado por completo</li><li>En todos los casos de prueba evaluados, deben cerrarse todos los defectos de gravedad alta</li></ul> | <ul><li>Todos los casos de prueba deben lograr una tasa de errores por un porcentaje por ciento</li><li>Todos los defectos identificados como gravedad alta deben resolverse antes de que puedan continuar las pruebas.</li></ul> |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decidir los criterios de suspensión que deben cumplirse si se identifican problemas con las pruebas.</li><li>Decidir cuáles son los criterios de salida que deben cumplirse para obtener la aprobación de las pruebas y el soporte para salir de la fase de pruebas después de completar todas las actividades de prueba.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente los criterios de salida y suspensión de pruebas necesarios en las plantillas de prueba y de salida proporcionadas.</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>Definir y documentar el proceso de escalamiento de defectos

Durante el transcurso de la ejecución del plan de prueba, es posible que se detecte un problema o se identifique un defecto que requiera escalamiento al recurso adecuado para procesar y determinar la resolución necesaria para permitir la realización de las pruebas.

A medida que se identifican defectos con la gravedad y prioridad asignadas, se crea una matriz de escala y se evalúa el proceso de revisión para la asignación cuando se desencadena un aumento de nivel y cómo, Cuándo y a quién se asignará el defecto para su posterior revisión y Solution.

Normalmente, un informe de defectos y un plan de correcciones incluye lo siguiente:

-   **Identificador de defecto:** El número que ha asignado al problema

-   **Descripción del defecto:** Resumen del problema

-   **Evaluación de la prioridad de defectos:** El nivel de prioridad asignado a un defecto para la resolución según el impacto empresarial y la gravedad del defecto. Algunos ejemplos podrían incluir:

-   **Bajo:** El problema tiene poco impacto en evitar que la fase de pruebas logre la aprobación si el problema se puede resolver más tarde.

-   **Medio:** El problema tiene un impacto sustancial en evitar que la fase de pruebas logre la aprobación si el problema no se puede resolver.

-   **Alto:** El problema tiene una repercusión crítica en evitar que la fase de pruebas logre la aprobación si el problema no se puede resolver.

-   **Propietario asignado al defecto:** El recurso asignado del equipo de pruebas que es responsable de resolver el problema

-   **Punto de escalado de defecto asignado:** El recurso asignado que es el punto de escalar el problema en la organización (si es necesario) para la resolución de conducción; basado en la gravedad del defecto

-   **Estado del defecto:** ¿Se ha solucionado el problema, está abierto o aún está en investigación?

-   **Resolución requerida por fecha:** La fecha en la que debe resolverse el problema

-   **Fecha de estado:** La fecha en la que se refleja la última vez que se actualizó el estado como resultado de una revisión de la clasificación de defectos

#### <a name="test-plan-defect-escalation"></a>Escala de defectos de plan de prueba

> [!TIP]
>   A continuación se muestra un ejemplo de una plantilla de escalado de defecto que puede usar en parte de su plan de pruebas para documentar el proceso de escalado necesario para establecer prioridades y resolver defectos de prueba.

| IDENTIFICADOR de defecto                                | Descripción de defectos                                                                                 | Evaluación de la prioridad de defectos                                           | Propietario del defecto asignado | Punto de escalado de defecto asignado | Método de elevación de defectos                                          | Estado de defectos | Resolución requerida por fecha | Fecha de estado |
|------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1                                        | Cuando el usuario escribe una extensión de cuatro dígitos, intenta realizar una llamada saliente, la llamada falla. | Medio                                                               | Lisa gris             | Louis Lahr                       | La clasificación semanal revisa el correo electrónico de alta prioridad para participantes afectados | Volver          | PRONTO                        | 1/12/2018   |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decidir y acordar las prioridades de defectos para admitir su plan de pruebas.</li><li>Decida el punto de extensión para cada área de defectos.</li><li>Decidir el nivel de elevación de defectos y el plan de evaluación, según la prioridad.</li><li>Decidir la creación de informes de defectos y el plan de comunicación de evaluación para escalar.</li><li>Decidir el defecto de la evaluación de la evaluación de la reunión.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente las prioridades de defectos acordadas.</li><li>Documente el punto de extensión de cada área de foco potencial.</li><li>Documente la elevación de defectos y el plan de evaluación de problemas según los criterios acordados.</li><li>Documentar las pautas de informes de defectos.</li><li>Programe la serie de reuniones de evaluación de defectos.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-deliverables"></a>Definir y documentar las entregas de prueba

El último componente final de la creación de un plan de pruebas es identificar los resultados en términos de entregas específicas que proporcionará el plan de pruebas general.

En un nivel alto, generalmente se incluyen, entre otras, las siguientes:

-   Plan de pruebas

-   Casos de prueba

-   Informes de defectos

-   Resumen de resultados de pruebas

-   Aceptación y aprobación de prueba

#### <a name="test-plan-deliverables"></a>Resultados del plan de pruebas

> [!TIP]
>   A continuación se muestra un ejemplo de una matriz de resultados del plan de pruebas que puede usar para documentar las entregas que se van a crear, junto con los recursos necesarios para la revisión, aprobación y cierre.

| Resultado del plan de prueba                    | Formato de resultados del plan de prueba | Propietario de la entrega del plan de pruebas                                                                                                      | Revisor de resultados del plan de pruebas | Aprobador de resultados del plan de pruebas | Fecha de inicio de la entrega del plan de prueba |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Plan de pruebas                                | Word                         | DETERMINADO                                                                                                                              | DETERMINADO                            | DETERMINADO                            | DETERMINADO                                 |
| Informes de administración de defectos                | Word                         | DETERMINADO                                                                                                                              | DETERMINADO                            | DETERMINADO                            | DETERMINADO                                 |
| Probar los informes de estado                   | Word                         | DETERMINADO                                                                                                                              | DETERMINADO                            | DETERMINADO                            | DETERMINADO                                 |
| Resumen de resultados de pruebas                     | PPTX de Word                    | DETERMINADO                                                                                                                              | DETERMINADO                            | DETERMINADO                            | DETERMINADO                                 |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decidir qué entregas se crearán y se capturarán como salida de cada fase de prueba. Para cada resultado, decida su:<ul><li>Formatea</li><li>Propietario</li><li>Revisor</li><li>Aprobador</li></ul></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente una matriz de creación y entrega de la entrega del plan de pruebas.</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>Evaluar la disponibilidad de red
----------------------------

Como elemento crítico para la implementación de equipos, la preparación de red es una parte crucial de las pruebas para garantizar que la red esté optimizada correctamente para admitir las comunicaciones de Teams. Para asegurarse de que su red está lista para los sitios dentro del ámbito, incluya las áreas de enfoque que se indican a continuación en su estrategia general de pruebas:

-   Estimación del ancho de banda y planificación con el organizador de la red (por medio de mi Asesor)

-   Validación de la configuración de calidad de servicio (QoS)

-   Comprobación de rendimiento y conectividad de red mediante la simulación de tráfico

-   Validación de túnel dividido

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Ejecutar Planner de red (por medio de mi Asesor) para sitios y personas en el ámbito

Antes de introducir servicios de comunicación en tiempo real como, por ejemplo, los equipos de su entorno, es importante que se asegure de que la red se ha optimizado y ajustado correctamente desde una perspectiva de ancho de banda de Azure ExpressRoute (si procede), Internet y WAN.

Para ayudarle a determinar la cantidad de ancho de banda y el nivel de optimización de red necesarios para los sitios en el [](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) ámbito de la implementación, complete la herramienta de planeación de la red (por medio de mis asesores) para validar las necesidades de disponibilidad de red de su organización. Para obtener más información sobre cómo determinar los requisitos de red para Teams mediante el planificador de redes, consulte mi Asesor: Network Planner.

> [!TIP]
>   Para obtener más información sobre la ficha **recomendaciones** , con ejemplos de cómo configurar e interpretar los resultados, consulte la [información general de recomendaciones](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp)de Network Planner.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Decidir qué sitios de red están en el ámbito para la implementación de los servicios de Teams.</li><li>Decidir las personas necesarias para las modalidades de Teams en el ámbito.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Complete el planificador de la red (por medio de mi Asesor) para obtener la lista de sitios que están en el ámbito.</li><li>Document Network Planner Validation resultados en la plantilla de resultados del plan de pruebas.</li><li>Valide que el ancho de banda de ExpressRoute (si procede), Internet y WAN que se calculó para los sitios en el ámbito se alinee con los valores de ancho de banda asignados actualmente.</li><li>Para los sitios que no tienen el ancho de banda adecuado, ejecuten planes de escalado y corrección para resolver problemas de ancho de banda.</li><li>Establezca una solución de supervisión de red para los sitios en el ámbito con el fin de controlar el uso del ancho de banda y QoS para los segmentos de ExpressRoute (si corresponde), Internet y WAN.</li><li>Programe una reunión de Comité Director para revisar los resultados del planificador de red.</li><li>Presentar los resultados de la planificación del ancho de banda al Comité de dirección para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>Evaluar la configuración de QoS para los sitios en el ámbito
---------------------------------------------

Como parte de la validación de la preparación de la red para dar soporte a las comunicaciones en tiempo real, es igualmente importante asegurarse de que la red se ha configurado y optimizado correctamente desde una perspectiva de QoS.

Para obtener más información sobre cómo configurar, implementar y validar la preparación de la red de QoS para los equipos mediante la Directiva de grupo, vea [Habilitar QoS para Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Decidir la configuración de QoS que se va a implementar.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Configurar QoS.</li><li>Ejecute la validación QoS como se describe en los pasos que se indican a través de las secciones "validar a través de GPO" y "validar a través del analizador de mensajes" anteriores.</li></ul></td></tr>
</table>


### <a name="document-qos-configuration-validation-test-results"></a>Resultados de la prueba de validación de QoS de documento

Después de completar las pruebas de validación de QoS con la Directiva de grupo para los sitios en el ámbito, cree un informe que resuma los resultados de las pruebas que deben presentarse durante la revisión final del Comité de gobierno.

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>Sitio A: informe de Resumen de pruebas de validación de configuración de QoS

> [!TIP]
>   A continuación se muestra un ejemplo de una plantilla de informe de Resumen de prueba que puede revisar durante la siguiente reunión del Comité Directivo cuando decide cuándo se encuentra en el sistema telefónico con servicios de planes de llamadas en la fase piloto.


**Validación de la configuración de QoS mediante GPO y analizador de mensajes**

**Resumen**de resultados&nbsp;&nbsp;&nbsp;: & # 9744; &nbsp; &nbsp; Pasa&nbsp; & # 9744; _AMP_&nbsp; &nbsp; &nbsp; parcial # 9744; Recuperación

<table>
<tr><th colspan="2">Resaltado de pruebas </th></tr>
<tr><td>DETERMINADO</td><td>DETERMINADO</td></tr>
<tr><th colspan="2">Pruebas lowlights  </th></tr><br/><tr><td><strong>Problema</strong>: TBD</td><td><strong>Corrección:</strong> DETERMINADO</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td><strong>Bloqueador</strong>: TBD</td><td><strong>Corrección</strong>: TBD</td></tr>
</table>


> [!TIP]
> Para facilitar el debate en la revisión final del Comité de gobierno, puede usar la [matriz de resultados de pruebas](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) actualizada de mi [asesor](https://myadvisor.fasttrack.microsoft.com/) para documentar y resaltar otras áreas que requieran corrección.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Evalúe los resultados de la prueba QoS para asegurarse de que el tráfico de los medios en tiempo real se marca y se prioriza correctamente.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Los resultados de la prueba QoS de documento se proporcionan en la plantilla de resultado del plan de pruebas.</li><li>Ejecutar planes de escalamiento y corrección para resolver problemas en los que QoS podría no estar configurado correctamente o no funcione de la manera esperada para admitir el tráfico de los medios de los equipos.</li></ul></td></tr><li>Programe una reunión de Comité Director para revisar los resultados del Resumen de pruebas.</li><li>Presentar los resultados del Resumen de la prueba al Comité Directivo para identificar las áreas que requieren corrección.</li>
</table>


<a name="execute-split-tunnel-enablement-validation"></a>Ejecutar validación de habilitación de túnel dividido
------------------------------------------

Hoy en día, las empresas tienen una o varias soluciones para proporcionar acceso remoto, como una red privada virtual o una VPN. Estas soluciones permiten la conectividad a las aplicaciones y los activos internos de la línea de negocios de manera segura y confiable.

Aunque las soluciones de acceso remoto pueden funcionar muy bien para dar acceso a algunas aplicaciones, cuando se trata de canalizar el tráfico de medios en tiempo real, estas soluciones suelen dar lugar a una experiencia de usuario menos que óptima para todos los participantes de un audio de Teams escenario de conferencias o llamadas.

Para asegurarse de que el tráfico multimedia de Teams *no* atraviese las soluciones de acceso remoto de su entorno, se necesitará una configuración de túnel dividido.

Para obtener más información sobre cómo configurar y validar la preparación de redes de configuración de túnel dividido para equipos, consulte disponibilidad de [red](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!NOTE]
>   Debido al gran volumen de soluciones de acceso remoto disponibles en el mercado, este documento no puede proporcionar detalles específicos de proveedores, solo se incluyen directrices generales para lo que se debe configurar en las soluciones de acceso remoto.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Decida la configuración de túnel dividido que se va a implementar.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Implementar una configuración de túnel dividido.</li><li>Pruebe y valide la configuración de túnel dividido.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>División de documentos-resultados de prueba de validación de configuración de túnel

Una vez completada la prueba de la configuración de túnel dividido de los sitios en el ámbito, cree un informe que resuma los resultados de la prueba y preséntela durante la siguiente revisión del Comité de dirección.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>Sitio A: informe de Resumen de pruebas de validación de configuración de túnel dividido

> [!TIP]
>   A continuación se muestra un ejemplo de una plantilla de informe de Resumen de prueba que puede revisar durante la siguiente reunión del Comité Directivo cuando decide cuándo se encuentra en el sistema telefónico con servicios de planes de llamadas en la fase piloto.

**Validación de configuración de túnel dividido**

**Resumen**de resultados&nbsp;&nbsp;&nbsp;: & # 9744; &nbsp; &nbsp; Pasa&nbsp; & # 9744; _AMP_&nbsp; &nbsp; &nbsp; parcial # 9744; Recuperación

<table>
<tr><th colspan="2">Resaltado de pruebas </th></tr>
<tr><td>DETERMINADO</td><td>DETERMINADO</td></tr>
<tr><th colspan="2">Pruebas lowlights  </th></tr><br/><tr><td><strong>Problema</strong>: TBD</td><td><strong>Corrección:</strong> DETERMINADO</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td><strong>Bloqueador</strong>: TBD</td><td><strong>Corrección</strong>: TBD</td></tr>
</table>


> [!TIP]
> Para facilitar el debate en la revisión final del Comité de gobierno, puede usar la [matriz de resultados de pruebas](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) actualizada de mi [asesor](https://myadvisor.fasttrack.microsoft.com/) para documentar y resaltar otras áreas que requieran corrección.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Evalúe los resultados de las pruebas de túnel dividido para asegurarse de que el tráfico en tiempo real de Teams se excluya de la solución de acceso remoto.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documento: los resultados de la prueba de conectividad de túnel se muestran en la plantilla de resultado del plan de pruebas.</li><li>Ejecutar planes de escalamiento y corrección para resolver problemas en los que es posible que no exista un enrutamiento adecuado para admitir los medios de los equipos dentro de una configuración de túnel dividido.</li><li>Programe una reunión de Comité Director para revisar los resultados del Resumen de pruebas.</li><li>Presentar los resultados del Resumen de la prueba al Comité Directivo para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>Ejecutar la validación de rendimiento y conectividad de red con la herramienta de evaluación de redes de Microsoft
-----------------------------------------------------------------------------------------------------------

La herramienta de evaluación de redes de Microsoft realiza pruebas de simulación y conectividad de tráfico al transmitir paquetes de audio simulados, para un período predefinido y un número de iteraciones, al sitio perimetral más cercano que proporciona conectividad con el servicio de Teams. Un objetivo de esta prueba es evaluar las métricas de rendimiento de la red para la pérdida de paquetes, la vibración, la latencia de recorrido de ida y vuelta y el porcentaje de reaprovisionamiento de paquetes de cada llamada simulada. Además, la prueba valida que se permiten las conexiones adecuadas entre los elementos de la red interna y perimetral a todos los puntos de entrada de borde que admiten conectividad con los servicios de Teams.

Para obtener más información sobre cómo confirmar y evaluar la preparación de red de Teams para los sitios designados en el ámbito, consulte disponibilidad de [red](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!TIP]
>   Para completar el análisis de la disponibilidad de red y la preparación de los sitios en el ámbito, designe un cliente potencial para cada sitio que pueda ayudarle con los esfuerzos de evaluación de la disponibilidad de red.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Decidir el perfil de prueba de evaluación de red y de conectividad para los sitios en el ámbito.</li><li>Decida los requisitos del archivo de configuración de evaluación de red para los sitios en el ámbito.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Configure los requisitos del archivo de configuración de evaluación de red para los sitios en el ámbito.</li><li>Ejecute la validación de rendimiento y conectividad de red para los sitios en el ámbito.</li></ul></td></tr>
</table>



### <a name="document-network-connectivity-and-performance-validation-test-results"></a>Documentar resultados de pruebas de conectividad de red y validación de rendimiento

Después de completar todas las pruebas de rendimiento y conectividad de red de los sitios del ámbito, cree un informe que resuma los resultados de pruebas y preséntela durante la siguiente revisión del Comité de dirección.

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>Sitio A: informe Resumen de rendimiento y conectividad de red

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla de conectividad de red y Resumen de rendimiento que puede usar durante la siguiente revisión del Comité Directivo cuando está determinando la disponibilidad general de la red para los sitios en el ámbito.

**Ubicación: Seattle [Inside Wired] cliente para Office 365 resultados**

**Resumen**de resultados&nbsp;&nbsp;&nbsp;: & # 9744; &nbsp; &nbsp; Pasa&nbsp; & # 9744; _AMP_&nbsp; &nbsp; &nbsp; parcial # 9744; Recuperación 



| Métrica                                                        | Target                                                                                                            | Día de la semana: oficina horas 9:30 AM a 11:00 AM                                                                                                                                                                                                                                                                                                 | Día de la semana: Office hours 2:30 PM a 4:30 PM | Día de la semana: después de las horas 10:30 PM a 12:30 AM | Fin de semana: después de las horas 9:30 A.M. a 11:30 AM | Fin de semana: después de las horas 2:30 PM a 4:30 PM |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| Latencia (unidireccional)                                             | \<50 ms                                                                                                           | 40 ms                                                                                                                                                                                                                                                                                                                                     | 38 MS                                    | 41 MS                                     | 35 MS                                    | 36 MS                                   |
| Latencia (tiempo de ida y vuelta o RTT)                             | \<100 ms                                                                                                          | 81 MS                                                                                                                                                                                                                                                                                                                                     | 77 MS                                    | 80 MS                                     | 72 MS                                    | 70 MS                                   |
| Pérdida de paquetes en ráfagas                                             | \<10% durante cualquier intervalo de 200-ms                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | 1                                       | 1                                        | 0,2%                                     | 0,1%                                    |
| Pérdida de paquetes                                                   | \<1% durante cualquier intervalo de 15-sec                                                                                   | 0,4%                                                                                                                                                                                                                                                                                                                                      | 0,3%                                     | 0,3%                                      | 0,1%                                     | 0%                                      |
| Vibración de llegada entre paquetes                                   | \<30 ms durante cualquier intervalo de 15-sec                                                                                | 12 ms                                                                                                                                                                                                                                                                                                                                     | 11 ms                                    | 13 MS                                     | 5 ms                                     | 5 ms                                    |
| Reordenación de paquetes                                                | \<0,05% de paquetes desordenados                                                                                      | 0 %                                                                                                                                                                                                                                                                                                                                        | 0 %                                       | 0 %                                        | 0 %                                       | 0 %                                      |



<table>
<tr><th colspan="2">Resaltado de pruebas </th></tr>
<tr><td>DETERMINADO</td><td>DETERMINADO</td></tr>
<tr><th colspan="2">Pruebas lowlights  </th></tr> 
<tr><td><strong>Problema</strong>: alta latencia</td><td><strong>Corrección:</strong> Investigue el enrutamiento de paquetes e implemente la ruta ideal.</td></tr>
<tr><td><strong>Problema</strong>: el tiempo de ida y vuelta isn& # 39; t duplicar la latencia</td><td><strong>Corrección:</strong> Investigue un posible problema de configuración de firewall o router. Investigue las rutas de tráfico.</td></tr>
<tr><td><strong>Problema</strong>: pérdida de paquetes elevada </td><td><strong>Corrección:</strong> Compruebe mediante el planificador de la red que se ha asignado suficiente ancho de banda. </td></tr>
<tr><td><strong>Problema</strong>: alta vibración </td><td> <strong>Corrección:</strong> Investigue si se están usando los valores correctos de punto de código de servicios diferenciados (DSCP). </td></tr>
<tr><td><strong>Problema</strong>: pérdida de paquetes elevada </td><td><strong>Corrección:</strong> Investigue la pérdida de paquetes. </td></tr>
<tr><td><strong>Problema</strong>: reordenación de paquetes altos </td><td><strong>Corrección:</strong> Investigue la cola y el ancho de banda del router. </td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td><strong>Bloqueador</strong>: TBD</td><td><strong>Corrección</strong>: TBD</td></tr>
</table>




<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Evalúe los resultados de la evaluación de la red y de las pruebas de conectividad para asegurarse de que cumple con los requisitos descritos en <a href="https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance" data-raw-source="[Media quality and network connectivity performance](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)">calidad de medios y rendimiento de conectividad de red</a> tanto para el segmento perimetral como para los segmentos de cliente.</li><li>¿Ha evaluado capacidades de red para admitir medios en tiempo real para todos los sitios del ámbito?</li><li> Si su red no se ha evaluado correctamente, o si sabe que no admite medios en tiempo real, deshabilitará las capacidades de vídeo y uso compartido de pantalla para reducir el impacto de la red y mejorar la experiencia de los equipos de los usuarios.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documentar resultados de pruebas de rendimiento y conectividad de red.</li><li>Ejecutar planes de escalamiento y corrección para resolver problemas con sitios en los que no hay suficiente ancho de banda, o no se cumplen los requisitos de rendimiento y conectividad de la red.</li><li>Programe una reunión de Comité Director para revisar los resultados del Resumen de pruebas.</li><li>Presentar los resultados del Resumen de la prueba al Comité Directivo para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


<a name="execute-subscriber-number-port-validation"></a>Ejecutar validación de puerto de número de suscriptor
-----------------------------------------

Si necesita transferir números como parte de la oferta de capacidades de llamadas entrantes y salientes en el sistema telefónico con los servicios de planes de llamadas admitidos por Teams, debe realizar un puerto parcial para un número de servicio. Esto le ayudará a validar las expectativas, los requisitos y la escala de tiempo razonable a medida que finaliza la preparación de la implementación del sistema telefónico con servicios de planes de llamadas en su entorno de producción.

Para completar un puerto parcial de un número de suscriptor de su proveedor de servicios RTC actual a Teams, siga los pasos que se describen a continuación.

#### <a name="step-1"></a>Paso 1

Identifique el número de prueba que desea trasladar a Office 365 como un número de usuario asignable (número de suscriptor) que se va a enviar a través del sistema telefónico con el servicio de planes de llamadas de Teams.

> [!IMPORTANT]
>Mientras planea la prueba de portabilidad de números, asegúrese de revisar las directrices más recientes para las solicitudes de portabilidad de número en [preguntas frecuentes sobre](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)el número de puertos.

#### <a name="step-2"></a>Paso 2

Identifique y documente toda la información de las cuentas (incluido el nombre usado para la cuenta específica) para el operador actual del número de prueba que va a migrar.
Normalmente, puede encontrar la información que necesitará en la factura más reciente de su proveedor de servicios actual.

> [!TIP]
>   Puede trasladar o transferir números de teléfono en todos los países o regiones admitidos actualmente; sin embargo, la manera de enviar una solicitud de portabilidad puede diferir según el país o la región desde donde se han origen los números de teléfono. Para obtener la lista más reciente de países o regiones admitidos actualmente, consulta [disponibilidad de países y regiones para las conferencias de audio y los planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).
> 
>   Para obtener más información sobre la transferencia de números de teléfono al sistema telefónico con planes de llamadas, junto con posibles restricciones, consulte [transferir números de teléfono a office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) y [restricciones de marcado gratuito de Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Paso 3

Descargue y cree una carta de autorización (LOA) para su país o región según el "número de servicio" como el tipo de portabilidad de número.

>[!NOTE]
>   Dado que los formatos de LOA pueden diferir según el país, la región o el tipo de número (es decir, que es geográfico o no geográfico o número de usuario frente al servicio o número gratuito), compruebe que está usando la plantilla de LOA correcta para su tipo de escenario específico. Consulte [descargar una carta de autorización (Loa)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) para obtener más información sobre cómo elegir la loa o vaya directamente a la [Página de descarga](https://www.microsoft.com/download/details.aspx?id=49167).

>[!NOTE]
> **Solo Estados Unidos**<br/>
>   Puesto que solo se está migrando un número de servicio para esta prueba, asegúrese de seleccionar los campos apropiados en la LOA como se muestra a continuación:

¿Cuántos números de teléfono va a ![transferir? Respuesta: estoy transfiriendo solo algunos de mis números de mi operador actual.] ¿Cuántos números de teléfono va a (media/onboarding-test-plan-image1.png "transferir? Respuesta: estoy transfiriendo solo algunos de mis números de mi operador actual.")

![¿Qué tipo de números de teléfono va a transferir? Respuesta: estoy transfiriendo números de teléfono de servicio de voz, como para los operadores automáticos o los puentes de conferencia.] (media/onboarding-test-plan-image2.png "¿Qué tipo de números de teléfono va a transferir? Respuesta: estoy transfiriendo números de teléfono de servicio de voz, como para los operadores automáticos o los puentes de conferencia.")

>[!IMPORTANT]
>   Cuando porte números de teléfono manualmente con una LOA, asegúrese de seleccionar el tipo correcto de número de teléfono. Debe enviar una solicitud de portabilidad independiente para cada tipo de número de teléfono que desee transferir.<br/><br/>
>   Como queremos probar el proceso de migración de números con un número de teléfono asociado al mismo número de teléfono de facturación (BTN), debe asegurarse de que el número de teléfono de facturación *no* esté incluido en el número de teléfono específico que se está transportando.

#### <a name="step-4"></a>Paso 4

En el portal de administración de inquilinos, vaya a la pestaña **soporte** y cree y envíe una solicitud de servicio. Adjunte el archivo de LOA completado para programar el número de teléfono asociado a su proveedor de servicios actual para la migración. Para elegir el método de solicitud de servicio más adecuado para el tamaño de su espacio empresarial, consulte [enviar manualmente una solicitud de servicio personalizada](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Una vez recibida la solicitud de asistencia, el soporte técnico de Microsoft seguirá el seguimiento según el método de comunicación que haya elegido y le informará de su estado y de los siguientes pasos para completar el proceso de migración de números.

#### <a name="step-5"></a>Paso 5

Después de confirmar que el número ha sido transcurrido como un nuevo número de suscriptor en Office 365, asigne el número al sistema telefónico con el servicio de planes de llamadas desde el portal \> de administración de inquilinos **Centro** \> **de administración de Skype empresarial Voz**. En la ficha **números de teléfono** , asigne el nuevo número de servicio al sistema telefónico con el servicio de planes de llamadas.

> [!TIP]
>   Aunque esta tarea asigna un nuevo número de servicio a un sistema telefónico con planes de llamadas, en el momento de escribir este artículo, la administración de esta tarea se completa con el centro de administración de Skype empresarial.

#### <a name="step-6"></a>Paso 6

Ahora que ha asignado el número de suscriptor que ha migrado, inicie sesión en un cliente de Teams como usuario y marque un número de 10 dígitos externo a través de la RTC. Una vez que haya realizado la llamada, confirme que la llamada se ha conectado y que la identificación de llamadas mostrada coincide con el número de suscriptor que ha migrado.

#### <a name="step-7"></a>Paso 7

Desde un número de RTC externo, realice una llamada al número de suscriptor que haya trasladado a Office 365 y compruebe que la llamada se recibe de entrada y se conecta a través del cliente de Teams.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Decide qué números de suscriptor nacionales tendrás que portar, por país o región.</li><li>Decidir qué plantilla de LOA va a usar.</li><li>Determine si su operador actual (que pierde el operador) permite la fragmentación de números de teléfono (es decir, permite el uso de pedidos de Puerto parcial).</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Recopilar la información necesaria y preparar la LOAs.</li><li>Descargue y complete las plantillas de LOA que necesita.</li><li>Enviar una solicitud de portabilidad de número de suscriptor.</li><li>Ejecute la validación de prueba para números ported asignándoles el sistema telefónico con el servicio de planes de llamadas para el acceso telefónico y confirmar que funcionan, como se describe en los pasos 6 y 7 descritos anteriormente en esta sección.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Resultados de la prueba de migración de números de servicios de documentos

Una vez que haya completado todas las pruebas de número de suscriptor, cree un informe que resuma los resultados de pruebas para que se presenten durante la revisión siguiente del Comité de dirección.

#### <a name="site-a-number-porting-test-summary-report"></a>Sitio A: informe de Resumen de la migración de números

> [!TIP]
>   A continuación se muestra un ejemplo de plantilla de informe de Resumen de pruebas que puede usar para su revisión durante la siguiente reunión del Comité Director cuando decide cuándo se encuentra en el sistema telefónico con servicios de planes de llamadas en la fase piloto.

**Portabilidad de números de servicio**

**Resumen**de resultados&nbsp;&nbsp;&nbsp;: & # 9744; &nbsp; &nbsp; Pasa&nbsp; & # 9744; _AMP_&nbsp; &nbsp; &nbsp; parcial # 9744; Recuperación 

<table>
<tr><th colspan="2">Resaltado de pruebas </th></tr>
<tr><td>DETERMINADO</td><td>DETERMINADO</td></tr>
<tr><th colspan="2">Pruebas lowlights  </th></tr><br/><tr><td><strong>Problema</strong>: TBD</td><td><strong>Corrección:</strong> DETERMINADO</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td><strong>Bloqueador</strong>: TBD</td><td><strong>Corrección</strong>: TBD</td></tr>
</table>


> [!TIP]
>   Para facilitar el debate en la revisión final del Comité de gobierno, puede usar la [matriz de resultados](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) de pruebas [](https://myadvisor.fasttrack.microsoft.com/) actualizada proporcionada por él para documentar y resaltar otras áreas de prueba que requieran corrección.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Evaluar si los números de suscriptor enviados para la migración se han trasladado correctamente al sistema telefónico con el servicio de planes de llamadas..</li><li>Evalúe si ha podido asignar el número de servicio trasladado al sistema telefónico con el servicio de planes de llamadas.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente el número de resultados de la prueba de portabilidad.</li><li>Ejecute planes de escalamiento y corrección para resolver los problemas que se hayan producido con el proceso de migración de números, si corresponde.</li><li>Programe una reunión de Comité Director para revisar los resultados del Resumen de pruebas.</li><li>Presentar los resultados del Resumen de prueba en el Comité Directivo para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


<a name="execute-your-test-plan-for-phone-system-with-calling-plans"></a>Ejecutar el plan de prueba para el sistema telefónico con planes de llamadas
----------------------------------------------------------

Ahora que ha definido su plan de pruebas, el siguiente paso es recorrer los casos de prueba, centrándose en la evaluación del sistema telefónico con las características de experiencia de usuario y administración de planes de llamadas en el ámbito. Antes de comenzar con las pruebas, verifique que los requisitos previos de prueba que se indican a continuación estén en su sitio.

### <a name="phone-system-with-calling-plans-testing-prerequisites"></a>Sistema telefónico con planes de llamadas que prueban los requisitos previos

-   Se han definido casos de uso empresarial para el sistema telefónico con el servicio de planes de llamadas.

-   Se han identificado los participantes clave.

-   La licencia necesaria para el sistema telefónico con los servicios de planes de llamadas está disponible y se ha asignado al grupo de usuarios en el ámbito.

-   Se identificó la lista de sitios y grupos de usuarios organizativos en el ámbito.

-   [Créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) se ha configurado para su organización.

-   El sistema telefónico con la configuración de planes de llamadas ha sido identificado y configurado.

-   La configuración del plan de marcado inquilino que admite el sistema telefónico con planes de llamadas ha sido identificada, configurada y aplicada para el grupo de usuarios en el ámbito.

-   El sistema telefónico con las directivas de planes de llamadas se ha identificado y configurado para el grupo de usuarios en el ámbito.

-   El sistema telefónico con los planes de llamadas los requisitos de cumplimiento se han identificado y configurado para el grupo de usuarios en el ámbito.

### <a name="document-phone-system-with-calling-plans-test-case-passfail-status"></a>Documentar el sistema telefónico con el estado de prueba de casos de prueba de plan de llamadas

A medida que se evalúan los casos de prueba para las características de sistema de teléfono administrativo y de usuario de los equipos de ámbito, realice un seguimiento de los resultados de cada caso de prueba para reflejar el estado Pass/Partial/FAIL, junto con el identificador asignado del defecto en caso de que surjan problemas imprevistos.

#### <a name="phone-system-with-calling-plans-test-case-status"></a>Sistema telefónico con el estado caso de prueba de planes de llamadas

> [!TIP]
>   A continuación se muestra un ejemplo de plantilla de estado de caso de prueba que puede usar para documentar los resultados de pruebas para su revisión durante la siguiente reunión del Comité Director cuando decida cuándo se encuentra en el sistema telefónico integrado con los servicios de planes de llamadas en la fase piloto.

| Sistema telefónico con planes de llamadas          |                              |                                                                                            |                           |                                                                            |
|------------------------------------------|------------------------------|--------------------------------------------------------------------------------------------|---------------------------|----------------------------------------------------------------------------|
| IDENTIFICADOR del caso de prueba                             | Título de caso de prueba              | Descripción del caso de prueba                                                                      | Resumen de resultados de casos de prueba | IDENTIFICADOR de defecto asignado (si corresponde)                                         |
| 1                                        | Realizar llamadas RTC salientes. | Realiza una llamada saliente marcando un número nacional de 10 dígitos.                              |    &#9744; Transcurr<br/>&#9744; Caudal<br/> &#9744; Recuperación                   | Cuando un usuario escribe un número de cuatro dígitos, se produce un error en la llamada que se aplica a la RTC. |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Evaluar el estado de aprobado o error de casos de prueba de alto nivel por sitio para el sistema telefónico con características de planes de llamadas en el ámbito.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente los resultados de estado de casos de prueba de todos los casos de prueba completados en el ámbito.</li><li>Programe una reunión de Comité Director para revisar los resultados del Resumen de pruebas.</li><li>Presentar el estado del caso de prueba en el Comité Directivo para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>


### <a name="document-phone-system-with-calling-plans-testing-result-summary"></a>Documentar un sistema telefónico con el Resumen de las pruebas de llamadas

Después de que todos los casos de prueba que admiten el sistema telefónico con características de planes de llamadas en el ámbito se hayan completado por sitio, documente los resultados que se van a revisar durante la reunión de un Comité Directivo cuando decida cuándo habilitar el sistema telefónico con servicios de planes de llamadas en el piloto. elimina.

#### <a name="site-a-phone-system-with-calling-plans-test-case-summary-report"></a>Sitio A: sistema telefónico con el informe de Resumen de casos de prueba de planes de llamadas:

> [!TIP]
>   A continuación se muestra un ejemplo de plantilla de informe de Resumen de pruebas que puede revisar durante la próxima reunión del Comité Director cuando decide cuándo se encuentra en el sistema telefónico con servicios de planes de llamadas en la fase piloto.


**Sistema telefónico de equipos con planes de llamadas**

**Resumen**de resultados&nbsp;&nbsp;&nbsp;: & # 9744; &nbsp; &nbsp; Pasa&nbsp; & # 9744; _AMP_&nbsp; &nbsp; &nbsp; parcial # 9744; Recuperación 

<table>
<tr><th colspan="2">Resaltado de pruebas </th></tr>
<tr><td>DETERMINADO</td><td>DETERMINADO</td></tr>
<tr><th colspan="2">Pruebas lowlights  </th></tr><br/><tr><td><strong>Problema</strong>: TBD</td><td><strong>Corrección:</strong> DETERMINADO</td></tr>
<tr><th colspan="2">Bloqueadores identificados </td></tr>
<tr><td><strong>Bloqueador</strong>: TBD</td><td><strong>Corrección</strong>: TBD</td></tr>
</table>


> [!TIP]
>   Para facilitar el debate en la revisión final del Comité de gobierno, puede usar la [matriz de resultados](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) de pruebas [](https://myadvisor.fasttrack.microsoft.com/) actualizada proporcionada por él para documentar y resaltar otras áreas que requieran corrección.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Evaluar resultados de Resumen de prueba de alto nivel por sitio para el sistema telefónico con características de planes de llamadas en el ámbito.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documente el informe de Resumen de caso de prueba después de que se hayan completado todos los resultados de casos de pruebas.</li><li>Programe una reunión de Comité Director para revisar los resultados del Resumen de pruebas.</li><li>Presentar los resultados del Resumen de la prueba al Comité Directivo para identificar las áreas que requieren corrección.</li></ul></td></tr>
</table>



<a name="present-and-report-phone-system-with-calling-plans-test-findings"></a>Presentar y denunciar un sistema telefónico con los resultados de la prueba de planes de llamadas
----------------------------------------------------------------

Una vez completadas todas las actividades de prueba y se hayan resuelto los defectos con un impacto de bajo, programe una reunión final con participantes para las pruebas. En la reunión, dirección:

-   Resumen de estado

-   Resaltar o lowlights

-   Lecciones aprendidas

-   Recomendación general: ¿vaya a la fase piloto o vuelva a evaluar los resultados de pruebas?

-   Resultados de la matriz de prueba (se deben documentar completamente en un apéndice)

#### <a name="test-plan-deliverables"></a>Resultados del plan de pruebas:

> [!TIP]
>   A continuación se muestra un ejemplo de una plantilla de la entrega del plan de pruebas que puede usar para documentar los criterios necesarios para lograr la aprobación y salir de la fase de pruebas o suspender la prueba hasta que todos los problemas identificados se hayan resuelto por completo.

| Resumen de estado               | Características destacadas/lowlights | Lecciones aprendidas | Recomendación de cierre |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Tasa de cambio de caso de prueba de% TBD</li><li>Todas las pruebas superadas</li></ul> | DETERMINADO                  | DETERMINADO             | Continuar con el piloto       |

-   Todas las pruebas superadas


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Puntos de decisión</td><td><ul><li>Decida el resumen del estado de las pruebas.</li><li>Identifique resaltados de pruebas y lowlights.</li><li>Identificar lecciones aprendidas.</li><li>Decidir qué acciones de corrección permanecen, si las hay.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documentar los resultados del Resumen de prueba para incluir:<ul><li>Resumen de estado</li><li>Características destacadas/lowlights</li><li>Lecciones aprendidas</li></ul></li><li>Programe una reunión del Comité del gobierno final para revisar los resultados de la prueba.</li><li>Presente los resultados del Resumen de la prueba durante el repaso del Comité Directivo para obtener la aprobación final para salir de la fase de pruebas.</li></ul></td></tr>
</table>

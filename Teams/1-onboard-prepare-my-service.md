---
title: Preparar la implementación de servicios de voz de nube de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Usar listas de comprobación de incorporación a preparar Office 365 para los equipos y configurar la funcionalidad básica de los equipos, redes y en la nube cargas de trabajo de voz.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 203a819eb3732d37aa65f92372eb21ffd59aea08
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462071"
---
# <a name="prepare-my-service"></a>Preparar mi servicio

En este artículo se ofrece una visión general de los requisitos de preparación en la nube de servicios de voz para su organización. Preparando correctamente, puede estar seguro de que está listo para proporcionar capacidades de voz a la organización de la nube.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de comprobación de incorporación de cargas de trabajo de voz de Microsoft Teams

Las listas de comprobación siguientes le guiarán a través de los pasos para la implementación de conferencias de Audio, el sistema telefónico con capacidades de teléfono del sistema enrutamiento directo ("enrutamiento directo") y llamar a planes ("llamar a planes de") en Microsoft Teams.

*  [Preparación de Office 365 para los equipos](onboarding-checklist-enable-office-365.md)

*  [Configurar la funcionalidad básica de los equipos](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Configuración de redes](onboarding-checklist-configure-networking.md)

*  [Configurar las cargas de trabajo de voz de la nube en los equipos](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurar el enrutamiento directo en los equipos](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Las tareas y actividades en estas listas de comprobación son los elementos de "tareas pendientes" principales que se aplican a todas las implementaciones de las capacidades de voz en la nube con los equipos. Puede personalizar las listas de comprobación para incluir las actividades y tareas que son específicas de su propio viaje de los equipos.

>[!NOTE]
>Esta guía se centra únicamente en los planes de llamada, conferencias de Audio y el enrutamiento directo. Si está familiarizado con los equipos, revise la [Información general de los equipos de Microsoft](teams-overview.md). Para obtener instrucciones generales para planear la implementación de los equipos, empiece con [chat Deploy, los equipos, los canales y aplicaciones en los equipos de Microsoft](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Use las listas de comprobación proporcionadas para realizar un seguimiento del estado de cada actividad individual y tareas, y estar seguro de que no ha omitido los pasos más importantes. Cada actividad incluye una descripción detallada de las acciones necesarias y las referencias a información adicional que puede usar para llevar a cabo dicha actividad.

Aunque se recomienda que siga las listas de comprobación en orden, la secuencia exacta dependerá del ámbito de la implementación y la configuración y la complejidad de su entorno. Para admitir puede ser un "en entorno virgen" en que están organizados los equipos de implementación (uno con ningún Skype anterior de presencia en línea de negocio) o migrar de Skype para profesionales en línea a los equipos. Si está migrando desde Skype para profesionales en línea, es posible que algunas de estas actividades ya ha completado y puede omitir ahora.

Cuando se haya de incorporación a los usuarios en una base por sitio, se recomienda que use la [Guía de habilitación de sitio para voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como una guía adicional a estas listas de comprobación.

>[!NOTE]
>La mayoría de las opciones de configuración es comunes entre los equipos y Skype para profesionales en línea. Use el centro de administración del centro de administración de Office 365 y Microsoft Teams para configurar esas opciones de configuración.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>¿Quién será responsable de supervisar la finalización de las listas de comprobación de incorporación?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Descargar las listas de comprobación de incorporación.</li><li>Funciona a través de los elementos de lista de comprobación de incorporación paso a paso de acuerdo con el plan de implementación de la organización.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar la incorporación de redes

Después de completar estas listas de comprobación, se habrán agregado correctamente las capacidades de voz a su implementación de los equipos.

Como el siguiente paso, use la [Guía de habilitación de sitio para voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) que le ayudarán a incorporación los usuarios en cada sitio y ayudar a garantizar que planear y ejecutar importantes actividades específica del sitio.

-   Plan de implantación de sitio por sitio listo

-   Establecer el proceso de administración de servicio

-   Ejecutar la prueba y corrección

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Cargas de trabajo de prueba en la nube voz en los equipos

Después de ha definido y documentado el éxito del negocio de voz de los equipos en la nube y planes de implementación técnica como parte de la fase de previsión y realizada la configuración que desee en el centro de administración, el siguiente paso es validar que la organización se cumplen las expectativas y requisitos a través de la característica, la funcionalidad y facilidad de uso. Debe realizar este paso de validación antes de implementar una implementación piloto o de final en el entorno de producción.

Puede aprovechar el plan de éxito empresarial que haya definido durante la fase de previsión para que sirva como base para determinar las actividades, las expectativas, casos de prueba de características y funcionalidades y ámbito global que se deben evaluar durante la fase de pruebas.

## <a name="define-your-testing-approach"></a>Definir su enfoque de pruebas

En su forma más sencilla, su enfoque de pruebas se basa en la revisión de las capacidades de la característica de las conferencias de Audio, planes de llamada, o tiene previsto de servicio de enrutamiento directo y desarrollar una prueba comprobar que se cumplen los requisitos de funcionalidad para los usuarios en el ámbito. El siguiente es un plan de pruebas de ejemplo para la fase de una implementación de conferencias de audio integrado.


| Característica de conferencia de audio para probar | Resumen de resultados | Notas adicionales |
|------------|-----------------|------------------|
| Programar una reunión de los equipos de ad-hoc que contiene información de marcado de conferencias de audio | Superar   | TBD |
| Usar un teléfono para el audio de la reunión marcando el número en una reunión desde la RTC con la información de acceso telefónico proporcionada | Superar | TBD |
| Unirse a otras personas a una reunión existente mediante marcación a través de la RTC | Superar | TBD |



| Para probar la característica enrutamiento directa o planes de llamada | Resumen de resultados | Notas adicionales |
|----------------------------------------------------|-----------------|------------------|
| Realizar una llamada de RTC marcando un número RTC       | Superar       | TBD |
| Recibir una llamada de RTC marcando el número de RTC desde una línea externa (móvil, teléfono fijo) | Superar | TBD|
| Transferir una llamada de RTC de un usuario de los equipos a otra | Superar | TBD |


>[!TIP]
>Para ayudar con la creación de caso de prueba como punto de partida, vea la lista de instrucciones de usuario disponibles en [las reuniones de los equipos y las llamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configuración de cargas de trabajo de voz en la nube para los equipos

Ahora que ha definido su enfoque de pruebas, el siguiente paso es la configuración de su entorno de servicio y los usuarios en el ámbito de las características de voz de los equipos en la nube.

Para obtener información adicional, vea:

- [Planificación técnica de Audioconferencia](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

- [Técnica de planeación para el sistema telefónico con planes de llamada](calling-plan-landing-page.md)

- [Configurar planes de llamada de Skype para empresas y Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planear el enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Configurar el enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Ejecutar el plan de pruebas

[//]: # (¿Editar bien? "Usuario" parece un poco ambiguo a mí.)
Después de que se han configurado el entorno del usuario y el servicio, el último paso de prueba incluye la ejecución de planes de prueba con el foco en la validación de características y funcionalidades. 

**Las pruebas de los requisitos previos y supuestos para los usuarios y sitios en el ámbito de conferencia de audio:**

-   Empresa utilizar definición de mayúsculas y minúsculas para las conferencias de Audio se ha completado el servicio.

-   Licencias necesarias para conferencias de Audio está disponible y se ha asignado.

-   La lista de sitios organizativos y grupos de usuarios se han identificado.

-   Se han identificado y configurado la lista de conferencias de audio dedicada y compartida marcado en los números con la preferencia de idioma.

-   [Créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) se han configurado para su organización.

-   Configuración de puente de conferencia de audio conferencia ha sido identificados y configurado (longitud PIN, las notificaciones de entrada o salida, preferencia de notificación de activación).

-   Las directivas de conferencia de inquilinos y que admitan conferencias de Audio de salida de los escenarios se han identificado, configurados y aplica la configuración del plan de marcado.

-   Requisitos de cumplimiento de conferencia de audio se han identificado y configurado.

**Llamar a los planes de pruebas de los requisitos previos y supuestos para los usuarios y sitios en el ámbito:**

-   Empresa utilizar definición de mayúsculas y minúsculas para la llamada planes de servicio se ha completado.

-   Necesario para llamar a los planes de licencias está disponible y se ha asignado.

-   La lista de sitios organizativos y grupos de usuarios se han identificado.

-   Los números de teléfono que se asignará a los usuarios se han adquirido o trasladado a Microsoft y están disponibles en el portal de inquilinos.

-   [Créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) se han configurado para su organización.

-   Las directivas de usuario de inquilinos y que admiten una llamada a planes de escenarios se han identificado, configurados y aplica la configuración del plan de marcado.

-   Llamar a los planes que se han identificado los requisitos de cumplimiento y se ha configurado.

**Las pruebas de los requisitos previos y supuestos para los usuarios y sitios en el ámbito de enrutamiento directa:**

-   Empresa utilizar definición de mayúsculas y minúsculas para el enrutamiento directo de servicio se ha completado.

-   Licencias necesarias para el enrutamiento directo está disponible y se ha asignado.

-   La lista de sitios organizativos y grupos de usuarios se han identificado.

-   Un [certificado de controlador de borde de sesión (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) se ha implementado, configurado y emparejada con el sistema telefónico.

-   Se ha habilitado la telefonía IP empresarial, y se han asignado los números de teléfono.

-   Se han identificado, configuradas y asigna las directivas de enrutamiento de voz.

-   Microsoft Teams se estableció como el cliente llamado preferido para los usuarios en el ámbito.
 
-   Requisitos de cumplimiento de normas de enrutamiento directos se han identificado y configurado.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decidir qué capacidades de la característica de conferencia de Audio que se van a implementar (Decisión del servicio).</li><li>Identificar los requisitos de la funcionalidad de usuario para conferencias de Audio.</li><li>Identificar los requisitos de configuración de servicios para conferencias de Audio.</li><br><li>Decidir si el enrutamiento directo o planes de llamada se implementarán y configurados.<li>Decidir qué capacidades de las funciones del sistema de teléfono que se va a implementar (Decisión del servicio).</li><li>Identificar los requisitos de la funcionalidad de usuario para enrutamiento directa o planes de llamada.</li><li>Identificar requisitos de configuración de servicio para enrutamiento directa o planes de llamada.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Desarrollar y documentar el enfoque del plan de pruebas.</li><li>Preparar el entorno de servicio y los usuarios en el ámbito de las características de conferencia de Audio.</li><li>Preparar su entorno de servicio y los usuarios en el ámbito de las características de enrutamiento directa o planes de llamada.</li><li>Ejecutar pruebas de validación para las características de conferencia de Audio que desea habilitar.</li><li>Ejecutar pruebas de validación para las características de enrutamiento directa o planes de llamada que se va a habilitar.</li><li>Para cualquier probar errores, confirme que la configuración es correcta, revise los artículos de la Comunidad, y, si es necesario: elevar un caso de soporte técnico.</li></ul></td></tr>
</table>


Para obtener instrucciones detalladas adicionales acerca de cómo realizar las pruebas para conferencias de Audio en los equipos, vea la [detallada de las pruebas de guía para conferencias de Audio](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).

Para obtener instrucciones detalladas adicionales acerca de cómo realizar las pruebas para llamar a los planes de en los equipos, vea la [detallada de las pruebas de guía para el sistema telefónico](onboarding-test-plan-for-enterprises-Phone-System.md).

<!--ENDOFSECTION-->

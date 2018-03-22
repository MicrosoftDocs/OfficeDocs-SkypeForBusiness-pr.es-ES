---
title: Prepararse para implementar el servicio de voz de nube de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Utilizar listas de comprobación de incorporación preparar Office 365 para equipos y configurar las principales funciones de los equipos, redes y las cargas de trabajo de la voz de la nube.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2b3d68d63661c988116f3b6729656eb3f34cf37
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="prepare-my-service"></a>Preparar mi servicio

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de comprobación de incorporación para cargas de trabajo de voz de Microsoft Teams

Las listas de comprobación siguientes le guiarán por los pasos para implementar el sistema de teléfono y conferencias de Audio con planes de llamar a las capacidades de Microsoft Teams.

*  [Preparar equipos de Office 365](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365)

*  [Configurar las funciones principales de los equipos](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities)

*  [Configurar la red](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)

*  [Configurar las cargas de trabajo de voz de nube en equipos](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams)

Las tareas y actividades en estas listas de comprobación son los principales elementos "pendientes que se aplican a todas las implementaciones de las capacidades de voz de nube con los equipos". Puede personalizar las listas de comprobación para incluir las actividades y tareas que son específicas de su propio viaje de equipos.

>[!NOTE]
>Esta guía se centra exclusivamente en el sistema de teléfono con planes de llamada y conferencia de Audio. Si eres nuevo a equipos, revise el [Resumen de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/teams-overview). Para obtener instrucciones generales para planear la implementación de equipos, consulte la [Guía de planificación de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/quick-start-enable-teams).

Utilizar listas de comprobación proporcionadas para realizar el seguimiento del estado de cada actividad individual y tareas, y para asegurarse no pasó por alto los pasos más importantes. Cada actividad incluye una descripción detallada de las acciones necesarias y las referencias a información adicional que puede utilizar para completar dicha actividad.

Aunque le recomendamos que siga las listas de comprobación en orden, la secuencia exacta dependerá del ámbito de la implementación y la configuración y la complejidad de su entorno. Para admitir un "greenfield" en que están organizados los equipos de implementación (uno con ningún Skype anterior presencia en línea de negocios) o migrar de Skype para los negocios en línea a los equipos. Si está migrando desde Skype para los negocios en línea, podría haber completado ya algunas de estas actividades y puede omitir ahora.

Cuando haya duda basándose en cada sitio, recomendamos que utilice el [Sitio de habilitación de guía de voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como una guía complementaria a estas listas de comprobación.

>[!NOTE]
>La mayoría de las opciones de configuración es comunes entre los equipos y Skype para los negocios en línea. Utilice Office 365 Skype para el centro de administración de negocios para configurar esas opciones.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>¿Quién será responsable de supervisar la finalización de las listas de comprobación de incorporación?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Descargar las listas de comprobación de incorporación.</li><li>Funciona a través de los elementos de la lista de comprobación de incorporación paso a paso, con arreglo al plan de implementación de la organización.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar la incorporación

Después de completar esta lista de comprobación, se habrán agregado correctamente las capacidades de voz a su implementación de equipos.

El siguiente paso, usar el [Sitio de habilitación de guía de voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ayudarle a bordo los usuarios en cada sitio y ayudan a garantizar que planear y ejecutar las actividades importantes de sitio específico.

-   Plan de implementación de sitio por sitio listo

-   Establecer el proceso de administración de servicio

-   Ejecutar pruebas y corrección

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Prueba cargas de trabajo de voz de la nube en equipos

Una vez definido y documentado el éxito del negocio de voz de nube de equipos y planes de implementación técnica como parte de la fase de previsión y emprendido la configuración que desee en el centro de administración, el paso siguiente es validar que su organización se cumplen las expectativas y requisitos a través de características, funcionalidad y facilidad de uso. Debe realizar este paso de validación antes de implementar una implementación piloto o final en el entorno de producción.

Puede aprovechar el plan de éxito del negocio definidos durante la fase de previsión para servir como base para determinar las actividades, las expectativas, casos de prueba de características y funcionalidades y alcance general a evaluar durante la fase de pruebas.

## <a name="define-your-testing-approach"></a>Definir el enfoque de pruebas

En su forma más simple, su enfoque de pruebas se basa en la revisión se cumplen las capacidades de la característica del sistema telefónico o conferencias de Audio con una llamada a los planes de servicio y desarrollar un plan de pruebas para comprobar que los requisitos de funcionalidad para los usuarios en el ámbito. El siguiente es un plan de prueba de ejemplo para la fase de una implementación de conferencias de audio incorporado.

| Característica de conferencia de audio para probar | Resumen de resultados | Notas adicionales |
|------------|-----------------|------------------|
| Programar una reunión de equipos ad hoc que contiene información de acceso telefónico de conferencia de audio | Correcto/incorrecto   | TBD |
| Utilice el teléfono para las reuniones audio llamando a una reunión desde la RTC con la información de acceso telefónico proporcionada | Correcto/incorrecto | TBD |
| Unirse a otras personas a una reunión existente por la realización de llamadas a través de la red PSTN | Correcto/incorrecto | TBD |


| Sistema de teléfono con planes de una llamada a función para probar | Resumen de resultados | Notas adicionales |
|----------------------------------------------------|-----------------|------------------|
| Realizar una llamada PSTN a marcando un número PSTN       | Correcto/incorrecto       | TBD |
| Recibe una llamada PSTN marcando el número PSTN desde una línea externa (móvil, teléfono fijo) | Correcto/incorrecto | TBD|
|Transferir una llamada PSTN de un usuario de equipos a otro | Correcto/incorrecto | TBD |


>[!TIP]
>Para ayudar con la creación de casos de prueba como punto de partida, consulte la lista de instrucciones del usuario de conferencia de audio disponibles en [las reuniones de los equipos y llamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8?ui=en-US&rs=en-US&ad=US#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar las cargas de trabajo de voz de nube para equipos

Ahora que ha definido su enfoque de pruebas, el paso siguiente es configurar su entorno de servicio y los usuarios en el ámbito de las funciones de voz de nube de equipos. Para obtener información adicional, consulte [Planes técnicos para conferencias de Audio](https://docs.microsoft.com/microsoftteams/audio-conferencing#technical-planning-for-audio-conferencing) y [Configurar conferencias de Audio de Skype para empresas y equipos de Microsoft](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) además de [Planes técnicos para el sistema de teléfono con planes de llamada](https://docs.microsoft.com/microsoftteams/phone-system-with-calling-plans#technical-planning-for-phone-system-with-calling-plans) y [conjunto Planes de llamada de Skype para empresas y equipos de Microsoft](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

<!--ENDOFSECTION-->

### <a name="execute-the-test-plan"></a>Ejecutar el plan de pruebas

Después de configurar los entornos de servicio Conferencia de audio y el usuario, el último paso de pruebas incluye la ejecución de planes de prueba con el enfoque de validación de características y funcionalidades. 

**Probar los requisitos previos y suposiciones acerca de los usuarios y los sitios en el ámbito de conferencia de audio:**

-   Empresa utilizar definición de caso para las conferencias de Audio se ha completado el servicio.

-   Licencias necesarias para conferencias de Audio está disponible y se ha asignado.

-   La lista de sitios organizativos y grupos de usuarios se han identificado.

-   Se han identificado y configura la lista de conferencias de audio dedicados y compartidos marcado en números con la preferencia de idioma.

-   [Créditos de comunicaciones](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (si es necesario) se han configurado para su organización.

-   Configuración de puente de conferencia de audio conferencia ha sido identificadas y configurado (longitud PIN, notificaciones de entrada y salida, preferencias de notificación de activación).

-   Las directivas de la conferencia de inquilinos y que admiten Audio conferencia escenarios de acceso telefónico de salida se han identificado, configura y aplica la configuración del plan de marcado.

-   Requisitos de cumplimiento de normas de audio conferencia se han identificado y configurado.

**Sistema de teléfono con una llamada a planes de pruebas de los requisitos previos y suposiciones acerca de los sitios y los usuarios en el ámbito:**

-   Definición de caso de uso de negocio para el sistema de teléfono con el servicio de llamada a planes se ha completado.

-   Licencias necesarios para el sistema de teléfono con planes de llamada está disponible y se ha asignado.

-   La lista de sitios organizativos y grupos de usuarios se han identificado.

-   Números de teléfono que se asignará a los usuarios se han adquirido o trasladado a Microsoft y están disponibles en el portal de inquilinos.

-   [Créditos de comunicaciones](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (si es necesario) se han configurado para su organización.

-   Inquilinos de las directivas de usuario y configuración del plan de marcado que admitan el sistema de teléfono con una llamada a los planes de escenarios identificada, configurada y aplicada.

-   Sistema de teléfono con los requerimientos de cumplimiento de planes de llamada han identificado y configurado.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir qué capacidades de la característica de conferencia de Audio que se van a implementar (Decisión de servicio).</li><li>Identificar los requisitos de funcionalidad de usuario para conferencias de Audio.</li><li>Identificar requisitos de configuración del servicio de conferencia de Audio.</li><li>Decidir qué sistema de teléfono con capacidades de planes de llamar a las funciones será implementado (Decisión del servicio).</li><li>Identificar requisitos de funciones de usuario para el sistema de teléfono con planes de llamada.</li><li>Identificar los requisitos de configuración de servicio para el sistema de teléfono con planes de llamada.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Desarrollar y documentar el enfoque del plan de pruebas.</li><li>Preparar el entorno del servicio y los usuarios en el ámbito de las características de conferencia de Audio.</li><li>Preparar el entorno del servicio y los usuarios en el ámbito de sistema telefónico con planes de llamada a funciones.</li><li>Ejecutar pruebas de validación para las características de conferencia de Audio que desee habilitar.</li><li>Ejecutar pruebas de validación para el sistema de teléfono con planes de llamar a funciones que desea habilitar.</li><li>Para cualquier prueba errores, confirme que la configuración es correcta, revise los artículos de la Comunidad, y, si es necesario, provocar un caso de soporte.</li></ul></td></tr>
</table>


Para obtener orientación adicional detallada acerca de cómo realizar pruebas para conferencias de Audio en los equipos, consulte el [detallada pruebas guía para conferencias de Audio] (https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Audio-Conferencing).

Para obtener orientación adicional detallada acerca de cómo realizar las pruebas para el sistema de teléfono con llamar a los planes en los equipos, consulte la [detallada guía de sistema de teléfono de pruebas](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Phone-System).

<!--ENDOFSECTION-->
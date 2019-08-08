---
title: Preparar la implementación de servicios de voz de nube de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use listas de comprobación de incorporación para preparar Office 365 para equipos y configurar las capacidades básicas de Teams, las redes y las cargas de trabajo de voz de nube.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63b507237cbc9a1d32dc891b99eaf6425528b559
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236201"
---
# <a name="prepare-my-service"></a>Preparar mis servicios

Este artículo proporciona una descripción general de los requisitos para preparar los servicios de voz en la nube para su organización. Si se prepara correctamente, puede estar seguro de que está listo para proporcionar funcionalidades de voz en la nube a su organización.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de comprobación de incorporación para las cargas de trabajo de voz de Microsoft Teams

La siguiente lista de comprobación le guiará a través de los pasos para implementar audioconferencias, sistemas telefónicos con planes de llamadas ("planes de llamadas") y capacidades de enrutamiento directo del sistema telefónico ("enrutamiento directo") en Microsoft Teams.

*  [Preparar Office 365 para equipos](onboarding-checklist-enable-office-365.md)

*  [Configurar capacidades básicas de Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Configurar redes](onboarding-checklist-configure-networking.md)

*  [Configurar cargas de trabajo de voz de nube en Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurar el enrutamiento directo en Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Las tareas y actividades de estas listas de comprobación son los elementos básicos de "tareas pendientes" que se aplican a cada implementación de las capacidades de voz en la nube con Teams. Puede personalizar las listas de comprobación para incluir las actividades y las tareas específicas de su propio viaje de equipos.

>[!NOTE]
>Esta guía se centra únicamente en los planes de llamadas, las conferencias de audio y el enrutamiento directo. Si es nuevo en Teams, revise la [información general de Microsoft Teams](teams-overview.md). Para obtener instrucciones generales sobre el planeamiento de la implementación de Teams, comience con la [implementación de chat, equipos, canales y aplicaciones en Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Use las listas de comprobación proporcionadas para realizar un seguimiento del estado de cada una de las actividades y tareas, y para asegurarse de que no ha omitido ningún paso importante. Cada actividad incluye una descripción detallada de las acciones y referencias necesarias para la información adicional que puede usar para completar esa actividad.

Aunque le recomendamos que siga las listas de comprobación en orden, la secuencia exacta dependerá del alcance de la implementación, así como de la configuración y la complejidad de su entorno. Están organizados para admitir una implementación de equipos de "Greenfield" (uno sin presencia anterior de Skype empresarial online) o de Skype empresarial online a teams. Si va a migrar desde Skype empresarial online, es posible que ya haya completado algunas de estas actividades y las pueda ignorar ahora.

Cuando incorpora usuarios en función de cada sitio, le recomendamos encarecidamente que use la guía [de habilitación de sitios para voz (guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como una guía complementaria a estas listas de comprobación.

>[!NOTE]
>La mayoría de las opciones de configuración son comunes entre equipos y Skype empresarial online. Use el centro de administración de Microsoft 365 y el centro de administración de Microsoft Teams para configurar estas opciones.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Quién será el responsable de supervisar la finalización de las listas de comprobación de incorporación?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Descargue las listas de comprobación de incorporación.</li><li>Trabaje paso a paso en la lista de comprobación de complementos de acuerdo con el plan de implementación de su organización.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar con la incorporación

Después de completar estas listas de comprobación, habrá agregado correctamente capacidades de voz a la implementación de Teams.

Como paso siguiente, use la [Guía de habilitación de sitios para voz (Guía de servicio)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para que le resulte más fácil incorporar a los usuarios de cada sitio y asegurarse de que planea y ejecuta actividades importantes específicas del sitio.

-   Plan de lanzamiento de sitio preparado por sitio

-   Establecer el proceso de administración de servicios

-   Ejecutar pruebas y correcciones

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Probar las cargas de trabajo de voz en la nube en Teams

Una vez que haya definido y documentado los planes de implementación técnica y de éxito de su equipo de voz en la nube como parte de la fase de previsión y haya realizado la configuración que desea en el centro de administración, el siguiente paso es validar que la organización las expectativas y los requisitos se cumplen mediante características, funcionalidad y facilidad de uso. Debe realizar este paso de validación antes de implementar una implementación piloto o final en su entorno de producción.

Puede aprovechar el plan de éxito empresarial que definió durante la fase de enVision para servir como base para determinar las actividades, expectativas, casos de pruebas de características/funcionalidades y ámbito general que se evaluará durante la fase de pruebas.

## <a name="define-your-testing-approach"></a>Definir el método de prueba

En su forma más simple, el método de pruebas se basa en la revisión de las capacidades de las características de la audioconferencia, los planes de llamadas o el servicio de enrutamiento directo y el desarrollo de un plan de pruebas para comprobar que se cumplen los requisitos de funcionalidad para los usuarios en el ámbito. A continuación se encuentra un plan de prueba de ejemplo para la fase integrada de una implementación de audioconferencia.


| Característica de audioconferencia para probar | Resumen de resultados | Notas adicionales |
|------------|-----------------|------------------|
| Programar una reunión de equipos ad-hoc que contenga información de acceso telefónico de las conferencias de audio | Superado/suspenso   | DETERMINADO |
| Usar un teléfono para el audio de la reunión mediante el marcado a una reunión desde la RTC con la información de acceso telefónico proporcionada | Superado/suspenso | DETERMINADO |
| Unirse a otras personas a una reunión existente mediante la llamada a través de la RTC | Superado/suspenso | DETERMINADO |



| Planes de llamadas o característica de enrutamiento directo para probar | Resumen de resultados | Notas adicionales |
|----------------------------------------------------|-----------------|------------------|
| Hacer una llamada RTC marcando un número de RTC       | Superado/suspenso       | DETERMINADO |
| Recibir una llamada RTC marcando su número de RTC desde una línea externa (móvil, teléfono fijo) | Superado/suspenso | DETERMINADO|
| Transferir una llamada RTC de un usuario de un equipo a otro | Superado/suspenso | DETERMINADO |


>[!TIP]
>Para obtener ayuda con la creación de casos de prueba como punto de partida, consulte la lista de instrucciones para el usuario disponible en las [reuniones y las llamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)de Teams.

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar cargas de trabajo de voz en la nube para equipos

Ahora que ha definido el método de prueba, el siguiente paso es configurar su entorno de servicio y los usuarios en ámbito para las características de voz en la nube de Teams.

Para obtener más información, consulte:

- [Planificación técnica de Audioconferencia](cloud-voice-deployment.md)

- [Configurar audioconferencias en Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planificación técnica para el sistema telefónico con planes de llamadas](calling-plan-landing-page.md)

- [Configurar planes de llamadas para Skype empresarial y Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planear el enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Configurar el enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Ejecutar el plan de pruebas

[//]: # (¿Modificar? "El usuario" parecía algo ambiguo para mí.)
Después de configurar el entorno de usuario y el servicio, el último paso de las pruebas incluye la ejecución del plan de pruebas con el foco en la validación de características y funciones. 

**Pruebas de las conferencias de audio y requisitos previos para usuarios y sitios en el ámbito:**

-   Se ha completado la definición del caso de uso empresarial para el servicio audioconferencia.

-   Las licencias necesarias para las conferencias de audio están disponibles y se han asignado.

-   Se ha identificado la lista de sitios y grupos de usuarios de la organización.

-   Se ha identificado y configurado la lista de números de marcado de audioconferencias dedicados y compartidos con preferencias de idioma.

-   [Créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) se ha configurado para su organización.

-   La configuración del puente de conferencia de conferencia de audio ha sido identificada y configurada (longitud del PIN, notificaciones de entrada/salida, preferencia de notificación de habilitación).

-   Las directivas de conferencia de inquilino y la configuración del plan de marcado que admiten escenarios de llamada de conferencias de audio se han identificado, configurado y aplicado.

-   Se han identificado y configurado los requisitos de cumplimiento de las conferencias de audio.

**Planes de llamadas que prueban los requisitos previos y los supuestos de los usuarios y los sitios en el ámbito:**

-   Se ha completado la definición del caso de uso empresarial para el servicio de planes de llamada.

-   La licencia necesaria para los planes de llamadas está disponible y se ha asignado.

-   Se ha identificado la lista de sitios y grupos de usuarios de la organización.

-   Los números de teléfono que se asignarán a los usuarios se han adquirido o trasladado a Microsoft y están disponibles en el portal del inquilino.

-   [Créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) se ha configurado para su organización.

-   Las directivas de usuario de inquilino y la configuración del plan de marcado que admiten escenarios de llamadas se han identificado, configurado y aplicado.

-   Se han identificado y configurado los requisitos de cumplimiento de planes de llamadas.

**Enrutamiento directo pruebe las suposiciones y los requisitos previos de los usuarios y los sitios en el ámbito:**

-   Se ha completado la definición del caso de uso empresarial para el servicio de enrutamiento directo.

-   La licencia necesaria para el enrutamiento directo está disponible y se ha asignado.

-   Se ha identificado la lista de sitios y grupos de usuarios de la organización.

-   Un [controlador de borde de sesión (SBC) certificado](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) se ha implementado, configurado y emparejado con el sistema telefónico.

-   Se ha habilitado la telefonía IP empresarial y se han asignado los números de teléfono.

-   Se han identificado, configurado y asignado las directivas de enrutamiento de voz.

-   Microsoft Teams se ha configurado como el cliente de llamadas preferido para los usuarios en el ámbito.
 
-   Los requisitos de cumplimiento de enrutamiento directo se han identificado y configurado.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decidir qué capacidades de características de audioconferencia se implementarán (decisión de servicio).</li><li>Identifique los requisitos de funcionalidad de usuario para audioconferencia.</li><li>Identifique los requisitos de configuración del servicio para audioconferencia.</li><br><li>Decidir si los planes de llamadas o enrutamiento directos se implementarán y configurarán.<li>Decidir qué funcionalidades de características del sistema telefónico se implementarán (decisión de servicio).</li><li>Identifique los requisitos de funcionalidad de usuario para los planes de llamadas o el enrutamiento directo.</li><li>Identifique los requisitos de configuración del servicio para los planes de llamadas o el enrutamiento directo.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Desarrolle y documente el método de su plan de pruebas.</li><li>Preparar el entorno de servicio y los usuarios en el ámbito de las características de audioconferencia.</li><li>Preparar el entorno de servicio y los usuarios en el ámbito de los planes de llamadas o de las características de enrutamiento directo.</li><li>Ejecute la validación de prueba para las características de audioconferencia que desea habilitar.</li><li>Ejecute la validación de prueba para los planes de llamadas o las características de enrutamiento directo que desee habilitar.</li><li>Para cualquier error de prueba, confirme que la configuración es correcta, revise los artículos de la comunidad y, si es necesario, aumente un caso de soporte técnico.</li></ul></td></tr>
</table>


Para obtener instrucciones detalladas adicionales sobre cómo realizar pruebas de conferencias de audio en Teams, consulte la [Guía de pruebas detallada de audioconferencia](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).

Para obtener instrucciones detalladas adicionales sobre cómo realizar pruebas de planes de llamadas en Teams, consulte la [Guía de pruebas detallada para el sistema telefónico](onboarding-test-plan-for-enterprises-Phone-System.md).

<!--ENDOFSECTION-->

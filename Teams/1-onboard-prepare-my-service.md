---
title: Prepararse para implementar el servicio de voz en la nube
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use listas de comprobación de incorporación para preparar Microsoft 365 o Office 365 para Teams y configurar Teams capacidades principales, redes y cargas de trabajo de voz en la nube.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a91a57a077db38675a62238289ad2c204040a9cd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675442"
---
# <a name="prepare-my-service"></a>Preparar mis servicios

En este artículo se ofrece información general sobre los requisitos para preparar los servicios de voz en la nube para su organización. Al prepararse correctamente, puede asegurarse de que está listo para proporcionar capacidades de voz en la nube a su organización.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de comprobación de incorporación para Microsoft Teams cargas de trabajo de voz

Las siguientes listas de comprobación le guiarán por los pasos para implementar Audioconferencia, Sistema telefónico con planes de llamadas ("Planes de llamadas") y Sistema telefónico funciones de enrutamiento directo ("enrutamiento directo") en Microsoft Teams.

*  [Preparar Microsoft 365 o Office 365 para Teams](onboarding-checklist-enable-office-365.md)

*  [Configurar las capacidades principales de Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Preparar la red](prepare-network.md)

*  [Configurar cargas de trabajo de voz en la nube en Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurar enrutamiento directo en Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Las tareas y actividades de estas listas de comprobación son los elementos principales "pendientes" que se aplican a todas las implementaciones de capacidades de voz en la nube con Teams. Puede personalizar las listas de comprobación para incluir las actividades y tareas específicas de su propio recorrido Teams.

>[!NOTE]
>Esta guía se centra únicamente en planes de llamadas, Audioconferencia y enrutamiento directo. Si no está familiarizado con Teams, revise [Información general de Microsoft Teams](teams-overview.md). Para obtener instrucciones generales para planear la implementación de Teams, empiece con [Implementar chat, equipos, canales y aplicaciones en Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Use las listas de comprobación proporcionadas para realizar un seguimiento del estado de cada tarea y actividad individuales, y para asegurarse de que no ha omitido ningún paso crítico. Cada actividad incluye una descripción detallada de las acciones necesarias y referencias a información adicional que puede usar para completar esa actividad.

Aunque le recomendamos que siga las listas de comprobación en orden, la secuencia exacta dependerá del ámbito de la implementación y de la configuración y complejidad del entorno. Están organizados para admitir una implementación de "campo verde" Teams (una sin presencia previa Skype Empresarial en línea) o migrar de Skype Empresarial Online a Teams. Si va a migrar desde Skype Empresarial Online, es posible que ya haya completado algunas de estas actividades y pueda ignorarlas ahora.

Cuando incorpora usuarios por sitio, le recomendamos encarecidamente que use la Guía de [habilitación del sitio para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como guía complementaria para estas listas de comprobación.

>[!NOTE]
>La mayoría de las opciones de configuración son comunes entre Teams y Skype Empresarial Online. Use el Centro de Administración de Microsoft 365 y Microsoft Teams centro de administración para configurar dichas opciones.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Quién será responsable de supervisar la finalización de las listas de comprobación de incorporación?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Siguientes pasos</td><td><ul><li>Descargue las listas de comprobación de incorporación.</li><li>Trabaje paso a paso con los elementos de lista de comprobación de incorporación según el plan de implementación de su organización.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar la incorporación

Después de completar estas listas de comprobación, habrá agregado correctamente funcionalidades de voz a la implementación de Teams.

Como paso siguiente, use el Libro de reproducción de [habilitación del sitio para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ayudarle a incorporar a los usuarios en cada sitio y garantizar que planea y ejecuta actividades importantes específicas del sitio.

-   Plan de implementación listo para el sitio por sitio

-   Establecer el proceso de administración de servicios

-   Ejecutar pruebas y corrección

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Probar las cargas de trabajo de voz en la nube en Teams

Una vez que haya definido y documentado sus Teams planes de implementación técnica y éxito empresarial de voz en la nube como parte de la fase de visualización y de llevar a cabo la configuración que desee en el centro de administración, el siguiente paso es validar que las expectativas y los requisitos de su organización se cumplen mediante características, funciones y facilidad de uso. Debe realizar este paso de validación antes de implementar una implementación piloto o final en el entorno de producción.

Puede aprovechar el plan de éxito empresarial que definió durante la fase de visualización para servir como base para determinar las actividades, expectativas, casos de prueba de características y funcionalidades y el ámbito general que se evaluará durante la fase de pruebas.

## <a name="define-your-testing-approach"></a>Definir el enfoque de pruebas

En su forma más sencilla, el enfoque de pruebas se basa en la revisión de las funciones de la Audioconferencia, planes de llamadas o servicio de enrutamiento directo y el desarrollo de un plan de prueba para comprobar que los requisitos de funcionalidad se cumplen para los usuarios en el ámbito. El siguiente es un plan de prueba de ejemplo para la fase incorporada de una implementación de audioconferencia.


| Audioconferencia característica para probar | Resumen de resultados | Notas adicionales |
|------------|-----------------|------------------|
| Programar una reunión ad hoc Teams que contenga información de acceso telefónico de audioconferencia | Pass/Fail   | TBD |
| Use un teléfono para el audio de la reunión marcando para entrar en una reunión desde la RTC con la información de acceso telefónico local proporcionada | Pass/Fail | TBD |
| Unirse a otras personas a una reunión existente mediante llamadas a través de RTC | Pass/Fail | TBD |



| Planes de llamadas o característica de enrutamiento directo para probar | Resumen de resultados | Notas adicionales |
|----------------------------------------------------|-----------------|------------------|
| Realizar una llamada RTC marcando un número de RTC       | Pass/Fail       | TBD |
| Recibir una llamada RTC marcando su número de RTC desde una línea externa (móvil, fijo) | Pass/Fail | TBD|
| Transferir una llamada RTC de un usuario de Teams a otro | Pass/Fail | TBD |


>[!TIP]
>Para ayudar con la creación de casos de prueba como punto de partida, consulte la lista de instrucciones del usuario disponibles en [Teams Reuniones y llamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar cargas de trabajo de voz en la nube para Teams

Ahora que ha definido el enfoque de pruebas, el siguiente paso es configurar el entorno de servicio y los usuarios en el ámbito de Teams las características de voz en la nube.

Para obtener más información, consulte:

- [Planificación técnica de Audioconferencia](./cloud-voice-landing-page.md)

- [Configurar audioconferencias en Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planificación técnica de Sistema telefónico con planes de llamadas](calling-plan-landing-page.md)

- [Configurar planes de llamadas para Skype Empresarial y Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planear el enrutamiento directo](./direct-routing-plan.md)

- [Configurar el enrutamiento directo](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>Ejecutar el plan de pruebas

[//]: # (¿Editar bien? "Usuario" me parecía un poco ambiguo.)
Después de configurar el entorno del usuario y el servicio, el último paso de las pruebas incluye la ejecución del plan de pruebas con el foco en la validación de características y funcionalidades. 

**Audioconferencia pruebas de requisitos previos e suposiciones para usuarios y sitios en el ámbito:**

-   Se ha completado la definición de caso de uso empresarial para el servicio de Audioconferencia.

-   La licencia necesaria para Audioconferencia está disponible y se ha asignado.

-   Se ha identificado la lista de sitios de la organización y grupos de usuarios.

-   Se ha identificado y configurado la lista de números de audioconferencia dedicados y compartidos con preferencias de idioma.

-   Se han configurado [créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) para su organización.

-   Audioconferencia configuración del puente de conferencia se han identificado y configurado (longitud del PIN, notificaciones de entrada y salida, preferencia de notificación de habilitación).

-   Las directivas de conferencia de inquilinos y la configuración del plan de marcado que admiten Audioconferencia escenarios de llamada de salida se han identificado, configurado y aplicado.

-   Audioconferencia se han identificado y configurado los requisitos de cumplimiento normativo.

**Planes de llamadas probando requisitos previos e hipótesis para usuarios y sitios en el ámbito:**

-   Se ha completado la definición de caso de uso empresarial para el servicio planes de llamadas.

-   La licencia necesaria para los planes de llamadas está disponible y se ha asignado.

-   Se ha identificado la lista de sitios de la organización y grupos de usuarios.

-   Teléfono números que se van a asignar a los usuarios se han adquirido o portado a Microsoft y están disponibles en el portal de inquilinos.

-   Se han configurado [créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) para su organización.

-   Se han identificado, configurado y aplicado las directivas de usuario de inquilino y la configuración del plan de marcado que admite escenarios de planes de llamada.

-   Se han identificado y configurado los requisitos de cumplimiento de los planes de llamadas.

**Requisitos previos y supuestos de pruebas de enrutamiento directo para usuarios y sitios en el ámbito:**

-   Se ha completado la definición de caso de uso empresarial para el servicio de enrutamiento directo.

-   La licencia necesaria para enrutamiento directo está disponible y se ha asignado.

-   Se ha identificado la lista de sitios de la organización y grupos de usuarios.

-   Se ha implementado, configurado y emparejado un [controlador de borde de sesión certificado (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) con Sistema telefónico.

-   Enterprise voz se ha habilitado y se han asignado los números de teléfono.

-   Las directivas de enrutamiento de voz se han identificado, configurado y asignado.

-   Microsoft Teams se ha establecido como cliente de llamada preferido para los usuarios en el ámbito.
 
-   Se han identificado y configurado los requisitos de cumplimiento de enrutamiento directo.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decida qué funciones de Audioconferencia características se implementarán (decisión del servicio).</li><li>Identificar los requisitos de funcionalidad del usuario para Audioconferencia.</li><li>Identifique los requisitos de configuración del servicio para Audioconferencia.</li><br><li>Decida si el enrutamiento directo o los planes de llamada se implementarán y configurarán.<li>Decida qué funciones de Sistema telefónico características se implementarán (decisión de servicio).</li><li>Identifique los requisitos de funcionalidad de usuario para planes de llamadas o enrutamiento directo.</li><li>Identifique los requisitos de configuración del servicio para planes de llamada o enrutamiento directo.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Siguientes pasos</td><td><ul><li>Desarrolle y documente el enfoque del plan de pruebas.</li><li>Prepare el entorno de servicio y los usuarios en el ámbito de las características de Audioconferencia.</li><li>Prepare el entorno de servicio y los usuarios en el ámbito de las características Planes de llamadas o Enrutamiento directo.</li><li>Ejecute la validación de prueba para las características de Audioconferencia que desee habilitar.</li><li>Ejecute la validación de prueba para las características planes de llamadas o enrutamiento directo que desea habilitar.</li><li>En caso de errores de prueba, confirme que la configuración es correcta, revise los artículos de la comunidad y, si es necesario, plantee un caso de soporte técnico.</li></ul></td></tr>
</table>


Para obtener instrucciones detalladas adicionales sobre cómo realizar pruebas para Audioconferencia en Teams, consulte la [guía de pruebas detallada para Audioconferencia](./deploy-audio-conferencing-teams-landing-page.md).

Para obtener instrucciones detalladas adicionales sobre cómo realizar pruebas para planes de llamadas en Teams, consulte la [guía de pruebas detallada para Sistema telefónico](./cloud-voice-landing-page.md).

<!--ENDOFSECTION-->
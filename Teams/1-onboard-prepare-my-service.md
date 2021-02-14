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
description: Use listas de comprobación de incorporación para preparar Microsoft 365 u Office 365 para Teams y configurar las capacidades principales de Teams, las redes y las cargas de trabajo de voz en la nube.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3c805e8ff14ddb1c46f83db819c5dd8a2c305914
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610072"
---
# <a name="prepare-my-service"></a>Preparar mis servicios

En este artículo se proporciona información general sobre los requisitos para preparar los servicios de voz en la nube para su organización. Al prepararse correctamente, puede estar seguro de que está listo para proporcionar funcionalidades de voz en la nube a su organización.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de comprobación de incorporación para cargas de trabajo de voz de Microsoft Teams

Las siguientes listas de comprobación le guían en los pasos para implementar Audioconferencia, Sistema telefónico con planes de llamada ("Planes de llamadas") y Enrutamiento directo de sistema telefónico en Microsoft Teams.

*  [Preparar Microsoft 365 u Office 365 para Teams](onboarding-checklist-enable-office-365.md)

*  [Configurar las capacidades principales de Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Preparar la red](prepare-network.md)

*  [Configurar cargas de trabajo de voz en la nube en Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurar el enrutamiento directo en Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Las tareas y actividades de estas listas de comprobación son los elementos "pendientes" principales que se aplican a todas las implementaciones de capacidades de voz en la nube con Teams. Puede personalizar las listas de comprobación para incluir las actividades y tareas específicas para su propio viaje de Teams.

>[!NOTE]
>Esta guía se centra únicamente en los planes de llamadas, audioconferencia y enrutamiento directo. Si es la primera vez que usa Teams, consulte [Información general de Microsoft Teams.](teams-overview.md) Para obtener instrucciones generales sobre cómo planear la implementación de Teams, empiece con [Implementar chat, equipos, canales y aplicaciones en Microsoft Teams.](deploy-chat-teams-channels-microsoft-teams-landing-page.md)

Use las listas de comprobación proporcionadas para realizar un seguimiento del estado de cada tarea y actividad individual, y para asegurarse de que no ha omitido ningún paso crítico. Cada actividad incluye una descripción detallada de las acciones necesarias y referencias a información adicional que puede usar para completar esa actividad.

Aunque le recomendamos que siga las listas de comprobación en orden, la secuencia exacta dependerá del ámbito de la implementación y de la configuración y la complejidad del entorno. Están organizados para admitir una implementación de Teams de "campo verde" (una sin presencia previa de Skype Empresarial Online) o migrar de Skype Empresarial Online a Teams. Si está migrando desde Skype Empresarial Online, es posible que ya haya completado algunas de estas actividades y pueda pasarlas por alto ahora.

Al incorporar usuarios por sitios, recomendamos encarecidamente que use el Libro de reproducción para voz [(Guía de reproducción)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para habilitar el sitio como guía complementaria para estas listas de comprobación.

>[!NOTE]
>La mayoría de las opciones de configuración son comunes entre Teams y Skype Empresarial Online. Para configurar estas opciones, debe usar el Centro de administración de Microsoft 365 y el Centro de administración de Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Quién será responsable de supervisar la finalización de las listas de comprobación de incorporación?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Descargue las listas de comprobación de incorporación.</li><li>Trabaje en los elementos de lista de comprobación de incorporación paso a paso de acuerdo con el plan de implementación de su organización.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar la incorporación

Después de completar estas listas de comprobación, habrá agregado correctamente funcionalidades de voz a la implementación de Teams.

Como paso siguiente, use el Libro de reproducción para voz [(Guía de reproducción)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ayudarle a incorporar a los usuarios en cada sitio y garantizar que planee y ejecute actividades importantes específicas del sitio.

-   Plano de implementación de Sitio preparado por sitio

-   Establecer proceso de administración de servicios

-   Ejecutar pruebas y corrección

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Probar cargas de trabajo de voz en la nube en Teams

Una vez que haya definido y documentado los planes de éxito empresarial de voz en la nube e implementación técnica de Teams como parte de la fase de visión y haya realizado la configuración que desee en el centro de administración, el siguiente paso es validar que las expectativas y requisitos de su organización se cumplen a través de la característica, la funcionalidad y la facilidad de uso. Debe realizar este paso de validación antes de implementar una implementación piloto o final en su entorno de producción.

Puede aprovechar el plan de éxito empresarial que definió durante la fase de visión para servir como base para determinar las actividades, las expectativas, los casos de prueba de características y funcionalidades, y el ámbito general que se evaluará durante la fase de prueba.

## <a name="define-your-testing-approach"></a>Definir el enfoque de pruebas

En su forma más sencilla, el enfoque de pruebas se basa en la revisión de las funciones de audioconferencia, planes de llamadas o servicio de enrutamiento directo y en desarrollar un plan de pruebas para comprobar que los requisitos de funcionalidad se cumplen para los usuarios en el ámbito. El siguiente es un plan de pruebas de ejemplo para la fase de incorporación de una implementación de audioconferencias.


| Característica de Audioconferencia para probar | Resumen de resultados | Notas adicionales |
|------------|-----------------|------------------|
| Programar una reunión ad-hoc de Teams que contenga información de acceso telefónico para audioconferencias | Pase o error   | TBD |
| Usar un teléfono para el audio de una reunión mediante acceso telefónico a una reunión desde RTC con la información de acceso telefónico proporcionada | Pase o error | TBD |
| Unirse a otras personas a una reunión existente mediante una llamada a través de RTC | Pase o error | TBD |



| Característica planes de llamadas o enrutamiento directo para probar | Resumen de resultados | Notas adicionales |
|----------------------------------------------------|-----------------|------------------|
| Realizar una llamada RTC marcando un número DE RTC       | Pase o error       | TBD |
| Recibir una llamada RTC marcando su número de RTC desde una línea externa (móvil, fijo) | Pase o error | TBD|
| Transferir una llamada RTC de un usuario de Teams a otro | Pase o error | TBD |


>[!TIP]
>Para ayudarle con la creación de casos de prueba como punto de partida, vea la lista de instrucciones de usuario disponibles en Reuniones [y llamadas de Teams.](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar cargas de trabajo de voz en la nube para Teams

Ahora que ha definido el enfoque de pruebas, el siguiente paso es configurar el entorno de servicio y los usuarios en el ámbito de las características de voz en la nube de Teams.

Para obtener información adicional, vea:

- [Planificación técnica de Audioconferencia](cloud-voice-deployment.md)

- [Configurar audioconferencias en Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planificación técnica del sistema telefónico con planes de llamadas](calling-plan-landing-page.md)

- [Configurar planes de llamadas para Skype Empresarial y Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planear el enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Configurar el enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Ejecutar el plan de pruebas

[//]: # (¿Editar bien? El "usuario" parecía un poco ambiguo para mí.)
Después de configurar el entorno del usuario y el servicio, el último paso de las pruebas incluye la ejecución del plan de pruebas con el foco en la validación de características y funcionalidades. 

**Pruebas de Audioconferencia requisitos previos y supuestos para usuarios y sitios dentro del ámbito:**

-   Se ha completado la definición de casos de uso empresarial para el servicio de Audioconferencia.

-   Las licencias necesarias para Audioconferencia están disponibles y se han asignado.

-   Se ha identificado la lista de sitios de la organización y grupos de usuarios.

-   Se ha identificado y configurado la lista de números de acceso telefónico de audioconferencia compartidos y dedicados con preferencia de idioma.

-   [Se han configurado](what-are-communications-credits.md) créditos de comunicaciones (si es necesario) para tu organización.

-   Se han identificado y configurado las opciones del puente de conferencia de Audioconferencia (longitud del PIN, notificaciones de entrada y salida, preferencia de notificación de habilitación).

-   Las directivas de conferencia de inquilino y las opciones del plan de marcado que admiten escenarios de llamada de audioconferencia se han identificado, configurado y aplicado.

-   Se han identificado y configurado los requisitos de cumplimiento de Audioconferencia.

**Requisitos previos y supuestos de prueba de planes de llamadas para usuarios y sitios dentro del ámbito:**

-   Se ha completado la definición de casos de uso empresarial para el servicio Planes de llamadas.

-   Las licencias necesarias para planes de llamadas están disponibles y se han asignado.

-   Se ha identificado la lista de sitios de la organización y grupos de usuarios.

-   Los números de teléfono que se asignarán a los usuarios se han adquirido o se han portado a Microsoft y están disponibles en el portal inquilino.

-   [Se han configurado](what-are-communications-credits.md) créditos de comunicaciones (si es necesario) para tu organización.

-   Las directivas de usuario de inquilino y la configuración del plan de marcado que admiten escenarios de planes de llamadas se han identificado, configurado y aplicado.

-   Se han identificado y configurado los requisitos de cumplimiento de los planes de llamadas.

**Requisitos previos y supuestos de pruebas de enrutamiento directo para usuarios y sitios dentro del ámbito:**

-   Se ha completado la definición de casos de uso empresarial para el servicio de enrutamiento directo.

-   La licencia necesaria para enrutamiento directo está disponible y se ha asignado.

-   Se ha identificado la lista de sitios de la organización y grupos de usuarios.

-   Se ha implementado, configurado y emparejado un controlador de borde de sesión [(SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) certificado con Sistema telefónico.

-   Se ha habilitado la voz empresarial y se han asignado los números de teléfono.

-   Las directivas de enrutamiento de voz se han identificado, configurado y asignado.

-   Microsoft Teams se ha configurado como el cliente de llamadas preferido para los usuarios en el ámbito.
 
-   Se han identificado y configurado los requisitos de cumplimiento de enrutamiento directo.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decidir qué funcionalidades de Audioconferencia se implementarán (decisión del servicio).</li><li>Identifique los requisitos de funcionalidad de usuario para Audioconferencia.</li><li>Identifique los requisitos de configuración del servicio para Audioconferencia.</li><br><li>Decida si se implementará y configurará el enrutamiento directo o los planes de llamadas.<li>Decidir qué funcionalidades de sistema telefónico se implementarán (decisión del servicio).</li><li>Identifique los requisitos de funcionalidad de usuario para planes de llamadas o enrutamiento directo.</li><li>Identifique los requisitos de configuración del servicio para planes de llamadas o enrutamiento directo.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Desarrolle y documente el enfoque del plan de pruebas.</li><li>Prepare el entorno de servicio y los usuarios en el ámbito de las características de Audioconferencia.</li><li>Prepare el entorno de servicio y los usuarios en el ámbito de los planes de llamadas o las características de enrutamiento directo.</li><li>Ejecute la validación de prueba para las características de Audioconferencia que desee habilitar.</li><li>Ejecute la validación de prueba para las características de planes de llamadas o enrutamiento directo que desee habilitar.</li><li>Para los errores de las pruebas, confirme que la configuración es correcta, revise los artículos de la comunidad y, si es necesario, resalte un caso de soporte técnico.</li></ul></td></tr>
</table>


Para obtener instrucciones detalladas sobre cómo realizar pruebas para Audioconferencia en Teams, consulte la guía de pruebas detallada [para Audioconferencia.](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)

Para obtener instrucciones detalladas sobre cómo realizar pruebas para planes de llamadas en Teams, consulte la guía de pruebas [detalladas para Sistema telefónico.](onboarding-test-plan-for-enterprises-Phone-System.md)

<!--ENDOFSECTION-->

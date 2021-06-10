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
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 42ded974ba5f4400bdcb5796410a8277fbed4488
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103976"
---
# <a name="prepare-my-service"></a>Preparar mis servicios

En este artículo se proporciona información general sobre los requisitos para preparar los servicios de voz en la nube para su organización. Al prepararse correctamente, puede asegurarse de que está listo para proporcionar capacidades de voz en la nube a su organización.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de comprobación de incorporación para Microsoft Teams de voz

Las siguientes listas de comprobación le guían por los pasos para implementar las audioconferencias, Sistema telefónico con planes de llamadas ("Planes de llamadas") y las capacidades de enrutamiento directo ("enrutamiento directo") de Sistema telefónico en Microsoft Teams.

*  [Preparar Microsoft 365 o Office 365 para Teams](onboarding-checklist-enable-office-365.md)

*  [Configurar Teams principales](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Preparar la red](prepare-network.md)

*  [Configurar cargas de trabajo de voz en la nube en Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurar enrutamiento directo en Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Las tareas y actividades de estas listas de comprobación son los elementos principales "pendientes" que se aplican a todas las implementaciones de capacidades de voz en la nube con Teams. Puede personalizar las listas de comprobación para incluir las actividades y tareas que son específicas de su propio Teams viaje.

>[!NOTE]
>Esta guía se centra únicamente en planes de llamadas, audioconferencias y enrutamiento directo. Si no es nuevo en Teams, revise [Información general de Microsoft Teams](teams-overview.md). Para obtener instrucciones generales para planear Teams implementación, empiece con Implementar [chat, equipos,](deploy-chat-teams-channels-microsoft-teams-landing-page.md)canales y aplicaciones en Microsoft Teams .

Use las listas de comprobación proporcionadas para realizar un seguimiento del estado de cada actividad y tarea individuales, y para asegurarse de que no ha omitido ningún paso crítico. Cada actividad incluye una descripción detallada de las acciones necesarias y referencias a información adicional que puede usar para completar esa actividad.

Aunque le recomendamos que siga las listas de comprobación en orden, la secuencia exacta dependerá del ámbito de la implementación y de la configuración y complejidad de su entorno. Están organizados para admitir una implementación Teams "greenfield" (una sin presencia Skype Empresarial online anterior) o migrar de Skype Empresarial Online a Teams. Si va a migrar desde Skype Empresarial Online, es posible que ya haya completado algunas de estas actividades y pueda ignorarlas ahora.

Cuando está incorporando usuarios en cada sitio, le recomendamos encarecidamente que use el Playbook de habilitación del sitio para voz [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como guía complementaria de estas listas de comprobación.

>[!NOTE]
>La mayoría de las opciones de configuración son comunes entre Teams y Skype Empresarial online. Use el Centro Microsoft 365 administración y Microsoft Teams de administración para configurar dichas opciones.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Quién será responsable de supervisar la finalización de las listas de comprobación de incorporación?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Descargue las listas de comprobación de incorporación.</li><li>Trabaje paso a paso con los elementos de la lista de comprobación de incorporación de acuerdo con el plan de implementación de su organización.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar la incorporación

Después de completar estas listas de comprobación, habrá agregado correctamente capacidades de voz a su Teams implementación.

Como paso siguiente, use el Playbook de habilitación del sitio para [voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ayudarle a incorporar a los usuarios en cada sitio y asegurarse de que planee y ejecute actividades importantes específicas del sitio.

-   Plan de implementación de Sitio por sitio listo

-   Establecer el proceso de administración de servicios

-   Ejecutar pruebas y corrección

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Probar cargas de trabajo de voz en la nube en Teams

Después de definir y documentar los planes de éxito empresarial y de implementación técnica de voz en la nube de Teams como parte de la fase de Envision y haber realizado la configuración que desea en el centro de administración, el siguiente paso es validar que las expectativas y los requisitos de su organización se cumplen mediante características, funcionalidad y usabilidad. Debe realizar este paso de validación antes de implementar una implementación piloto o final en su entorno de producción.

Puede aprovechar el plan de éxito empresarial que definió durante la fase Devisión para que sirva de base para determinar las actividades, las expectativas, los casos de prueba de características y funcionalidades y el ámbito general que se evaluará durante la fase de prueba.

## <a name="define-your-testing-approach"></a>Definir el enfoque de pruebas

En su forma más sencilla, el enfoque de prueba se basa en revisar las funcionalidades de características del servicio de audioconferencia, planes de llamadas o enrutamiento directo y desarrollar un plan de prueba para comprobar que los requisitos de funcionalidad se cumplen para los usuarios en el ámbito. A continuación se muestra un plan de prueba de ejemplo para la fase integrada de una implementación de audioconferencia.


| Característica de audioconferencia para probar | Resumen de resultados | Notas adicionales |
|------------|-----------------|------------------|
| Programar una reunión de acceso telefónico Teams ad hoc que contenga información de acceso telefónico local de audioconferencia | Pasar o fallar   | TBD |
| Usar un teléfono para el audio de la reunión marcando en una reunión desde la RTC con la información de acceso telefónico local proporcionada | Pasar o fallar | TBD |
| Unirse a otras personas a una reunión existente marcando a través de la RTC | Pasar o fallar | TBD |



| Planes de llamadas o característica de enrutamiento directo para probar | Resumen de resultados | Notas adicionales |
|----------------------------------------------------|-----------------|------------------|
| Realizar una llamada RTC marcando un número RTC       | Pasar o fallar       | TBD |
| Para recibir una llamada RTC, marque su número RTC desde una línea externa (móvil, fijo) | Pasar o fallar | TBD|
| Transferir una llamada RTC de un usuario Teams a otro | Pasar o fallar | TBD |


>[!TIP]
>Para ayudar con la creación de casos de prueba como punto de partida, vea la lista de instrucciones del usuario disponibles en [Teams reuniones y llamadas.](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar cargas de trabajo de voz en la nube para Teams

Ahora que ha definido el enfoque de pruebas, el siguiente paso es configurar el entorno de servicio y los usuarios en el ámbito de Teams de voz en la nube.

Para obtener información adicional, vea:

- [Planificación técnica de Audioconferencia](./cloud-voice-landing-page.md)

- [Configurar audioconferencias en Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planificación técnica para Sistema telefónico con planes de llamadas](calling-plan-landing-page.md)

- [Configurar planes de llamadas para Skype Empresarial y Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planear el enrutamiento directo](./direct-routing-plan.md)

- [Configurar el enrutamiento directo](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>Ejecutar el plan de prueba

[//]: # (¿Edita bien? "Usuario" me parecía un poco ambiguo.)
Una vez configurado el entorno de usuario y el servicio, el último paso de las pruebas incluye la ejecución del plan de pruebas con el foco en la validación de características y funcionalidades. 

**Requisitos previos y supuestos de pruebas de audioconferencia para usuarios y sitios en el ámbito:**

-   Se ha completado la definición de casos de uso empresarial para el servicio de audioconferencia.

-   Las licencias necesarias para las audioconferencias están disponibles y se han asignado.

-   Se ha identificado la lista de sitios organizativos y grupos de usuarios.

-   Se ha identificado y configurado la lista de números de marcado de audioconferencia dedicados y compartidos con preferencias de idioma.

-   [Los créditos](what-are-communications-credits.md) de comunicaciones (si es necesario) se han configurado para su organización.

-   Se han identificado y configurado las opciones de puente de conferencia de audioconferencia (longitud del PIN, notificaciones de entrada y salida, preferencia de notificación de habilitación).

-   Se han identificado, configurado y aplicado las directivas de conferencia de inquilino y la configuración del plan de marcado que admiten escenarios de acceso telefónico local de audioconferencia.

-   Los requisitos de cumplimiento de audioconferencia se han identificado y configurado.

**Planes de llamadas que prueban requisitos previos y supuestos para usuarios y sitios en el ámbito:**

-   Se ha completado la definición de casos de uso empresarial para el servicio Planes de llamadas.

-   Las licencias necesarias para los planes de llamadas están disponibles y se han asignado.

-   Se ha identificado la lista de sitios organizativos y grupos de usuarios.

-   Teléfono los números que se asignarán a los usuarios se han adquirido o portado a Microsoft y están disponibles en el portal de inquilinos.

-   [Los créditos](what-are-communications-credits.md) de comunicaciones (si es necesario) se han configurado para su organización.

-   Se han identificado, configurado y aplicado las directivas de usuario inquilino y la configuración del plan de marcado que admiten escenarios de planes de llamadas.

-   Se han identificado y configurado los requisitos de cumplimiento de planes de llamadas.

**Requisitos previos y supuestos de pruebas de enrutamiento directo para usuarios y sitios en el ámbito:**

-   Se ha completado la definición de casos de uso profesional para el servicio de enrutamiento directo.

-   Las licencias necesarias para enrutamiento directo están disponibles y se han asignado.

-   Se ha identificado la lista de sitios organizativos y grupos de usuarios.

-   Se ha implementado, configurado y emparejado un controlador de borde de sesión [certificado (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) con Sistema telefónico.

-   Enterprise se ha habilitado la voz y se han asignado los números de teléfono.

-   Las directivas de enrutamiento de voz se han identificado, configurado y asignado.

-   Microsoft Teams se ha establecido como el cliente de llamadas preferido para los usuarios del ámbito.
 
-   Se han identificado y configurado los requisitos de cumplimiento de enrutamiento directo.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decida qué funcionalidades de características de audioconferencia se implementarán (decisión de servicio).</li><li>Identifique los requisitos de funcionalidad de usuario para las audioconferencias.</li><li>Identificar los requisitos de configuración del servicio para audioconferencias.</li><br><li>Decida si los planes de enrutamiento directo o de llamadas se implementarán y configurarán.<li>Decida qué Sistema telefónico de características se implementarán (decisión de servicio).</li><li>Identifique los requisitos de funcionalidad de usuario para planes de llamadas o enrutamiento directo.</li><li>Identifique los requisitos de configuración de servicio para planes de llamadas o enrutamiento directo.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Desarrolle y documente el enfoque del plan de prueba.</li><li>Prepare el entorno de servicio y los usuarios en el ámbito de las características de audioconferencia.</li><li>Prepare el entorno de servicio y los usuarios en el ámbito de las características planes de llamadas o enrutamiento directo.</li><li>Ejecute la validación de prueba para las características de audioconferencia que desea habilitar.</li><li>Ejecute la validación de prueba de las características Planes de llamadas o Enrutamiento directo que desee habilitar.</li><li>Para cualquier error de prueba, confirme que su configuración es correcta, revise los artículos de la comunidad y, si es necesario, levante un caso de soporte técnico.</li></ul></td></tr>
</table>


Para obtener instrucciones detalladas adicionales sobre cómo realizar pruebas para audioconferencias en Teams, vea la guía de pruebas detallada para [audioconferencias.](./deploy-audio-conferencing-teams-landing-page.md)

Para obtener instrucciones detalladas adicionales sobre cómo realizar pruebas para planes de llamadas en Teams, consulte la guía de pruebas detallada [para Sistema telefónico](./cloud-voice-landing-page.md).

<!--ENDOFSECTION-->
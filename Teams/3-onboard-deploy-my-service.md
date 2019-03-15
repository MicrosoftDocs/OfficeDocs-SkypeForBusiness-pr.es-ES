---
title: Implementación de servicios de voz de nube de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Descargue la Guía de habilitación de sitio para planear la implantación de los equipos y acelerar y optimizar la adopción de usuario, los requisitos de calidad y satisfacción.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ea80d3ba87a6499cba3bf52b5f70d45d0619c8a
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568467"
---
# <a name="deploy-my-service"></a>Implementar mis servicios

Este artículo proporciona una visión general de los requisitos para implementar correctamente los servicios de voz en la nube. Siguiendo las instrucciones de implementación de servicios de voz de la nube, puede asegurarse de que correctamente para todos los requisitos de cuenta y ofrecer resultados repetibles.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Guía de habilitación de sitio para las cargas de trabajo de voz de Microsoft Teams

Use esta guía para ayudar a su organización a planear y ejecutar la implantación de las características de voz de Microsoft Teams en el sitio por sitio.

Incluidas las actividades de todos los necesarias, recomendada escalas de tiempo y vínculos a la Ayuda correspondiente para cada actividad, esta guía trata instrucciones de end-to-end para ayudar a garantizar una correcta implementación de voz de los equipos de un sitio determinado, centrándose en los factores que son importantes para el usuario.

Al completar las actividades en esta guía, su organización puede:

-   Planear y programar la implantación de los equipos de manera eficaz.

-   Acelerar y optimizar la adopción de usuario.

-   Reducir las necesidades de soporte técnico y aumentar la satisfacción de los usuarios.

> [!NOTE]
> En este artículo y la Guía de asociados no están pensadas para describir cada paso de configuración técnica requeridas para la habilitación de servicio o proporcionar el tono de marcado a un sitio específico. En su lugar, puedan centran en las actividades y tareas que se recomienda a los usuarios incorporados fácilmente y pídales que comienzan a consumir cargas de trabajo de voz a los equipos a través de una transición rápida y sin problemas con una tasa de adopción alta, y que minimicen los requisitos de soporte técnico. Para obtener orientación técnica acerca de cómo configurar mejor el entorno de voz de los equipos, consulte las listas de comprobación de la incorporación de redes para la [configuración de las cargas de trabajo de voz de los equipos](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [Configurar el enrutamiento directo en los equipos](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [capacidades básicas de los equipos](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), las redes [ para los equipos](onboarding-checklist-configure-networking.md)y la [habilitación de Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Áreas de enfoque de guía

El foco de la guía es tratar los factores que influyen en la percepción del usuario de una implementación de voz de los equipos. Las actividades y tareas se agrupan en las siguientes áreas de enfoque:

-   Validación de la preparación del servicio
    - Audioconferencia
    - Planes de llamadas
    - Enrutamiento directo

-   Habilitación de usuario

-   Puntos de conexión

-   Uso y calidad

-   Adopción

La [Guía de habilitación de sitio para voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) es un libro de Microsoft Excel. Cada una de estas áreas de cinco foco es una hoja independiente del libro, y cada tarea de implementación y la actividad se agrupan en una de estas hojas.

![Captura de pantalla de la guía] (media/deploy-my-service-image1.png "Captura de pantalla de la guía")

> [!NOTE]
> Creará una instancia independiente de la guía para cada sitio en el ámbito de la implantación de los equipos.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Cómo usar la Guía

Independientemente del tamaño y complejidad de la ubicación, habilitar cada sitio, es preciso que planee las tareas y actividades lo bastante pronto — y ejecutarlos en orden óptimo: antes, durante y después de la implantación real del servicio. Se recomienda que siga estos pasos como planear y ejecutar su propio viaje a voz de Microsoft Teams.

1. Descargue la [Guía de habilitación de sitio para voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para los equipos de Microsoft Voice.

2. Crear una copia independiente de la guía para cada sitio.

3. En la ficha de la hoja denominada **Guía para {SiteName código}**, reemplace **{SiteName-código}** con el nombre del sitio relevante o el código de sitio.

4. Escriba **el nombre del sitio, código de sitio**e la **fecha de inicio planeada**, tal y como se muestra a continuación. Éste es un paso crítico, debido a que se ajusta a las fechas límite recomendadas para todas las actividades en la guía.

   ![Ejemplo con nombre del sitio de Nueva York, el código del sitio NY01 y la fecha de inicio planeada de 20-Mar-18] (media/deploy-my-service-image2.png "Ejemplo con nombre del sitio de Nueva York, el código del sitio NY01 y la fecha de inicio planeada de 20-Mar-18")

5. Revise cada actividad, realice las acciones necesarias y actualizar el estado a medida que vaya a través de la escala de tiempo. Estado está representado gráficamente, tal como se describe a continuación:
   <ul>
   <li>![Marca de verificación verde](media/deploy-my-service-image3.png) <strong>Sí o no es aplicable (verde):</strong> se ha completado la actividad, o no es aplicable para este sitio, y no es necesaria ninguna otra acción.</li>
   <li>![Signo de exclamación amarillo](media/deploy-my-service-image4.png) <strong>la actividad no se completó aún (amarillo):</strong> la actividad no ha finalizado todavía y debe actualizarse a sí o No en su programación.</li>
   <li>![X roja](media/deploy-my-service-image5.png) <strong>sin (rojo):</strong> la actividad no se puede completar debido a un problema y debe llevarse a la reunión de estado del proyecto.</li></ul>

6. El estado es resumido dentro de cada sección, y el encabezado de sección tiene el formato con uno de estos indicadores de estado. **Estado semanal** también se actualiza automáticamente.

![Captura de pantalla de la semanal estado resúmenes en la guía] (media/deploy-my-service-image6.png "Captura de pantalla de la semanal estado resúmenes en la guía")

> [!TIP]
> Repita los pasos anteriores para todas las ubicaciones que tiene.

> [!IMPORTANT]
> Algunos pasos podrían no ser aplicables a todos los sitios y las ubicaciones. Si una actividad específica no es relevante para un sitio, debe seleccionar **no es aplicable** para esta actividad. **No elimine** cualquiera filas en la Guía; Si lo hace, no funcionarán las fórmulas de resumen de estado.<br/><br/>
Preste atención a las actividades que pueden tardar más tiempo del planeado para, como número de trasladar y las actividades de compras. Estas actividades pueden afectar negativamente a la escala de tiempo de implementación del sitio. Asegúrese de revisar y actualizar la lista de actividades y la escala de tiempo asociado semanalmente y presentarlos en [las reuniones del Comité de dirección](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) para asegurarse de que tener en cuenta el estado de cada sitio y cualquier desviación del plan de implementación de las partes interesadas.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decidir si es necesaria para la implementación de la Guía de habilitación de sitio.</li><li>Decidir quién será responsable de la personalización de la Guía de habilitación de sitio para Microsoft Teams para cada sitio que se va a implementar.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Descargar la Guía de habilitación de sitio</a>.</li><li>Personalizar la Guía de habilitación de sitio para el primer sitio.</li><li>Repita según sea necesario para los sitios adicionales.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
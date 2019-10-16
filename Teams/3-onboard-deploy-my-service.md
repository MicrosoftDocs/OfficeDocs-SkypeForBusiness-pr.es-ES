---
title: Implementación de servicios de voz de nube de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience: admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Descargue la guía de habilitación de sitios para planificar los lanzamientos de equipos y acelerar y optimizar la adopción de los usuarios, la percepción de su calidad y la satisfacción.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 760beb6b5f786367c76ce9ac2b66d808fa10c6de
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516003"
---
# <a name="deploy-my-service"></a>Implementar mis servicios

Este artículo proporciona una descripción general de los requisitos para implementar correctamente los servicios de voz en la nube. Si sigue una guía prescriptiva para implementar los servicios de voz en la nube, puede asegurarse de que tiene éxito todos los requisitos y de ofrecer resultados repetibles.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Guía de habilitación de sitios para cargas de trabajo de voz de Microsoft Teams

Use esta guía para ayudar a su organización a planear y ejecutar correctamente la implementación de las características de voz de Microsoft Teams en cada sitio.

Incluye todas las actividades necesarias, las escalas de tiempo recomendadas y los vínculos a la orientación correspondiente para cada actividad, en esta guía se tratan las instrucciones completas para ayudar a garantizar una implementación de voz de Teams correcta para un sitio determinado, centrándose en los factores que son importantes para el usuario.

Al completar las actividades de esta guía, su organización puede:

-   Planear y programar de forma eficaz el lanzamiento de Teams.

-   Acelerar y optimizar la adopción por el usuario.

-   Reduzca las necesidades de soporte técnico y aumente la satisfacción del usuario.

> [!NOTE]
> Este artículo y la guía relacionada no se destinan a describir todos los pasos de configuración técnica necesarios para la habilitación del servicio o el suministro de tono de marcado a un sitio específico. En su lugar, se concentran en actividades y tareas recomendadas para los usuarios que se incorporan fácilmente y que les permiten comenzar a consumir cargas de trabajo de voz a través de una transición rápida y fluida con una tasa de adopción elevada, a la vez que minimizan los requisitos de soporte técnico. Para obtener instrucciones técnicas sobre cómo configurar mejor su entorno para la voz de Teams, consulte las listas de comprobación de incorporación para [configurar las cargas de trabajo de voz de Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), configurar el [enrutamiento directo en Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [capacidades básicas de Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [redes para Teams](onboarding-checklist-configure-networking.md)y [habilitar Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Áreas de concentración de la guía

El foco de la guía consiste en tratar los factores que influyen en la percepción del usuario de una implementación de voz de Teams. Las actividades y las tareas se agrupan en las siguientes áreas de concentración:

-   Validación de la preparación del servicio
    - Audioconferencia
    - Planes de llamadas
    - Enrutamiento directo

-   Habilitación del usuario

-   Puntos de conexión

-   Uso y calidad

-   Aprobación

La [Guía de habilitación de sitios para voz](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) es un libro de Microsoft Excel. Cada una de estas cinco áreas de enfoque es una hoja independiente en el libro, y cada tarea y actividad de implementación se agrupan en una de estas hojas.

![Captura de pantalla de la guía de activación de sitios](media/deploy-my-service-image1.png "de la guía")

> [!NOTE]
> Creará una instancia independiente de la guía para cada sitio en el ámbito de la implementación de Teams.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Cómo usar la guía

Independientemente del tamaño y la complejidad de la ubicación, habilitar cada sitio requiere que planee las tareas y las actividades lo antes posible (y las ejecute en orden óptimo) antes, durante y después de la implementación del servicio real. Le recomendamos que siga estos pasos mientras planea y ejecuta su propio viaje a Microsoft Teams Voice.

1. Descargue la [Guía de habilitación de sitios para voz (Guía de voz)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para Microsoft Teams Voice.

2. Cree una copia independiente de la guía para cada sitio.

3. En la pestaña de la hoja denominada **Guía para {siteName-Code}**, reemplaza **{siteName-Code}** por el nombre de sitio correspondiente o el código de sitio.

4. Escriba el **nombre del sitio, el código de sitio**y la **fecha de lanzamiento planificada**, como se muestra a continuación. Este es un paso crítico, ya que ajusta las fechas límite recomendadas para cada actividad de la guía.

   Ejemplo ![con nombre de sitio, código de sitio y ejemplo de fecha de lanzamiento planeada](media/deploy-my-service-image2.png "con el nombre de sitio de Nueva York, código de sitio NY01 y fecha de lanzamiento planificada de 20 de marzo de 18")

5. Revise cada actividad, lleve a cabo las acciones necesarias y actualice el estado a medida que recorra la escala de tiempo. El estado se representa de forma gráfica, como se describe a continuación:
  
   - ![Ilustración de una marca](media/deploy-my-service-image3.png) de verificación verde **sí o no aplicable (verde):** la actividad se ha completado, o no es aplicable para este sitio, y no se necesita ninguna otra acción.</li>
   - ![Ilustración de un signo de exclamación](media/deploy-my-service-image4.png) amarillo <strong>la actividad no se ha completado aún (amarillo):</strong> la actividad aún no se ha completado y debe actualizarse a sí o no en su programación.</li>
   - ![Ilustración de una X roja que indica](media/deploy-my-service-image5.png) no no <strong>(rojo):</strong> la actividad no se puede completar debido a un problema y debe llevarse a la reunión de estado del proyecto.</li></ul>

6. El estado se resume dentro de cada sección y el título de la sección tiene el formato de uno de estos indicadores de estado. El **Estado semanal** también se actualiza automáticamente.

![Captura de pantalla de los resúmenes de estado semanales en la guía](media/deploy-my-service-image6.png "de la guía de los resúmenes de estado semanales en la guía")

> [!TIP]
> Repita los pasos anteriores para todas las ubicaciones que tiene.

> [!IMPORTANT]
> Es posible que algunos pasos no se apliquen a todas las ubicaciones y sitios. Si una actividad específica no es relevante para un sitio, debe seleccionar **no aplicable** para esta actividad. **No elimine** ninguna fila de la guía; Si lo hace, las fórmulas de la imagen de estado no funcionarán.<br/><br/>
Preste atención a las actividades que pueden tardar más tiempo del que planeó, como la portabilidad de números y las actividades de compra. Estas actividades pueden afectar negativamente a la escala de tiempo de la implementación del sitio. Asegúrese de revisar y actualizar la lista de actividades y la escala de tiempo asociada semanalmente y preséntelas en las [reuniones del Comité de dirección](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) para asegurarse de que las partes interesadas conozcan el estado de cada sitio y las posibles desviaciones de la programación de implementación.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decida si la guía de habilitación de sitios es necesaria para su implementación.</li><li>Decida quién será el responsable de personalizar la guía de habilitación del sitio de Microsoft Teams para cada sitio que vaya a implementar.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Descargue la guía de habilitación de sitios</a>.</li><li>Personalizar la guía de habilitación del sitio para su primer sitio.</li><li>Repita los pasos necesarios para los sitios adicionales.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
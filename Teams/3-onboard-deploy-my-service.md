---
title: Implementación de servicios de voz de nube de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Descargue la Guía de habilitación de sitios para planear la implementación de Teams y acelerar y optimizar la adopción del usuario, la satisfacción y la calidad.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae9a1e6abf7dbf97e625be4eb69a0ef95b1910da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532577"
---
# <a name="deploy-my-service"></a>Implementar mis servicios

En este artículo se ofrece información general sobre los requisitos para implementar correctamente los servicios de voz en la nube. Si sigue instrucciones prescriptivas para implementar servicios de voz en la nube, puede asegurarse de que cumple correctamente todos los requisitos y ofrece resultados que se pueden repetir.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Guía de reproducción de habilitación de sitios para cargas de trabajo de voz de Microsoft Teams

Use esta guía para ayudar a su organización a planear y ejecutar correctamente la implementación de las características de voz de Microsoft Teams en cada sitio.

Con todas las actividades necesarias, las escalas de tiempo recomendadas y los vínculos a las instrucciones correspondientes de cada actividad, en esta guía se delegue una guía de un extremo a otro para garantizar una implementación de voz de Teams correcta para un sitio específico, centrándose en los factores importantes para el usuario.

Al completar las actividades de esta guía, la organización puede:

-   Planee y programe su implementación de Teams de forma eficaz.

-   Acelere y optimice la adopción de usuarios.

-   Reduzca las necesidades de soporte técnico y aumente la satisfacción del usuario.

> [!NOTE]
> Este artículo y la guía asociada no están pensados para describir todos los pasos de configuración técnica necesarios para habilitar el servicio o proporcionar un tono de marcado a un sitio específico. En su lugar, se centran en las actividades y tareas recomendadas para incorporar a los usuarios fácilmente y que empiecen a consumir cargas de trabajo de voz de Teams a través de una transición rápida y fluida con un alto índice de adopción, a la vez que minimizan los requisitos de soporte técnico. Para obtener instrucciones técnicas sobre cómo configurar mejor el entorno para teams de voz, consulte las listas de comprobación de incorporación para configurar las cargas de trabajo de voz de [Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)configurar el enrutamiento directo en [Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)las funcionalidades principales de [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)las redes para [Teams](prepare-network.md)y habilitar [Microsoft 365 u Office 365.](onboarding-checklist-enable-office-365.md)

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Áreas en las que centrarse en playbook

El foco del libro de reproducción es tratar los factores que influyen en la idea del usuario de implementar una implementación de voz de Teams. Las actividades y las tareas se agrupan en las siguientes áreas de foco:

-   Validación de disponibilidad del servicio
    - Audioconferencia
    - Planes de llamadas
    - Enrutamiento directo

-   Habilitación del usuario

-   Puntos de conexión

-   Uso y calidad

-   Adopción

El [Libro de reproducción de habilitación de sitios para voz (Guía de reproducción)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) es un libro de Microsoft Excel. Cada una de estas cinco áreas de foco es una hoja separada en el libro y cada tarea y actividad de implementación se agrupan en una de estas hojas.

![Captura de pantalla del libro de reproducción de habilitación del sitio](media/deploy-my-service-image1.png "Captura de pantalla del libro de reproducción")

> [!NOTE]
> Creará una instancia independiente del libro de reproducción para cada sitio en el ámbito de su implementación de Teams.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Cómo usar la guía

Independientemente del tamaño y la complejidad de la ubicación, habilitar cada sitio requiere que planee las tareas y actividades lo suficientemente pronto y las ejecute en orden óptimo antes, durante y después de la implementación del servicio real. Le recomendamos que siga estos pasos mientras planea y ejecuta su propio camino a la voz de Microsoft Teams.

1. Descargue el Libro de reproducción para voz [(Guía de reproducción)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para Microsoft Teams Voice.

2. Cree una copia independiente del libro de reproducción para cada sitio.

3. En la pestaña de la hoja denominada Playbook para **{SiteName-Code},** reemplace **{SiteName-Code}** por el nombre del sitio correspondiente o el código de sitio.

4. Escriba el **nombre del sitio, el código de** sitio y la fecha de lanzamiento **planeada,** como se muestra a continuación. Este es un paso crítico, ya que ajusta las fechas límite recomendadas para cada actividad de la guía.

   ![Ejemplo con el nombre del sitio, el código de sitio y la fecha de lanzamiento planeada](media/deploy-my-service-image2.png "Ejemplo con el nombre del sitio de Nueva York, el código de sitio NY01 y la fecha de lanzamiento planeada del 20-mar.-18")

5. Revise cada actividad, tome las medidas necesarias y actualice el estado a medida que pase por la escala de tiempo. El estado se representa gráficamente, como se describe a continuación:
  
   - ![Ilustración de una marca de verificación verde Sí o no aplicable ](media/deploy-my-service-image3.png) **(verde):** La actividad se ha completado o no es aplicable a este sitio y no es necesario realizar ninguna acción.</li>
   - ![Ilustración de un signo de exclamación amarillo: La actividad aún no ha finalizado (amarillo): La actividad no se ha completado todavía y debe actualizarse a Sí o No en ](media/deploy-my-service-image4.png) <strong></strong> su programación.</li>
   - ![Ilustración de una X roja que indica ](media/deploy-my-service-image5.png) <strong>que no hay (rojo):</strong> la actividad no se puede completar debido a un problema y debe llevar a la reunión de estado del proyecto.</li></ul>

6. El estado se muestra dentro de cada sección y el encabezado de la sección tiene formato con uno de estos indicadores de estado. **El estado semanal** también se actualiza automáticamente.

![Captura de pantalla de los informes de estado semanales en el libro de reproducción](media/deploy-my-service-image6.png "Captura de pantalla de los informes de estado semanales en el libro de reproducción")

> [!TIP]
> Repita los pasos anteriores para todas las ubicaciones que tenga.

> [!IMPORTANT]
> Es posible que algunos pasos no sean aplicables a todas las ubicaciones y sitios. Si una actividad específica no es relevante para un sitio, debe seleccionar **No aplicable** a esta actividad. **NO ELIMINE ninguna** fila de la guía; si lo hace, las fórmulas de la lista de estado no funcionarán.<br/><br/>
Preste atención a las actividades que podrían llevar más tiempo del planeado, como porciones de números y actividades de compra. Estas actividades pueden afectar negativamente a la escala de tiempo de implementación del sitio. Asegúrese de revisar y actualizar la lista de actividades y [](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) la escala de tiempo asociada semanalmente, y de presentarlos en reuniones del comité de dirección para asegurarse de que las partes interesadas son conscientes del estado de cada sitio y las posibles desviaciones de la programación de implementación.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decida si la Guía de habilitación del sitio es necesaria para la implementación.</li><li>Decida quién será el responsable de personalizar el libro de reproducción de habilitación del sitio para Microsoft Teams en cada sitio que implemente.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Descargue el Libro de reproducción de habilitación del sitio.</a></li><li>Personalice el Libro de reproducción de habilitación del sitio para su primer sitio.</li><li>Repita el proceso según sea necesario para sitios adicionales.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
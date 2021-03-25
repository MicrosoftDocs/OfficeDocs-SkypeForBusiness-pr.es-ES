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
description: Descargue el Libro de reproducción de habilitación del sitio para planear la implementación de Teams y acelerar y optimizar la adopción del usuario, la percepción de calidad y la satisfacción.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112636"
---
# <a name="deploy-my-service"></a>Implementar mis servicios

En este artículo se proporciona información general sobre los requisitos para implementar correctamente los servicios de voz en la nube. Siguiendo instrucciones prescriptivas para implementar servicios de voz en la nube, puede asegurarse de que cumple correctamente todos los requisitos y ofrece resultados repetibles.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Libro de reproducción de habilitación del sitio para cargas de trabajo de voz de Microsoft Teams

Use este libro de juegos para ayudar a su organización a planear y ejecutar correctamente la implementación de las características de voz de Microsoft Teams de forma individual.

Incluyendo todas las actividades necesarias, las escalas de tiempo recomendadas y los vínculos a las instrucciones correspondientes para cada actividad, este libro de reproducción trata las instrucciones de extremo a extremo para ayudar a garantizar una implementación de voz de Teams correcta para un sitio determinado, centrándose en los factores que son importantes para el usuario.

Al completar las actividades de este libro de juegos, su organización puede:

-   Planee y programe su implementación de Teams de forma eficaz.

-   Acelere y optimice la adopción de usuarios.

-   Reduzca las necesidades de soporte técnico y aumente la satisfacción del usuario.

> [!NOTE]
> Este artículo y el libro de juegos asociados no están diseñados para describir todos los pasos de configuración técnica necesarios para la habilitación del servicio o proporcionar tono de marcado a un sitio específico. En su lugar, se centran en las actividades y tareas recomendadas para incorporar a los usuarios fácilmente y hacer que empiecen a consumir cargas de trabajo de voz de Teams mediante una transición rápida y fluida con una alta tasa de adopción, al tiempo que minimizan los requisitos de soporte técnico. Para obtener instrucciones técnicas sobre cómo configurar mejor su entorno para la voz de Teams, vea las listas de comprobación de incorporación para configurar las cargas de trabajo de voz de [Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)configurar el enrutamiento directo en [Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)las capacidades principales de [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)las redes para [Teams](prepare-network.md)y habilitar [Microsoft 365 u Office 365.](onboarding-checklist-enable-office-365.md)

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Áreas de foco de Playbook

El foco del libro de reproducción es abordar los factores que influyen en la percepción del usuario de una implementación de voz de Teams. Las actividades y tareas se agrupan en las siguientes áreas de enfoque:

-   Validación de la preparación del servicio
    - Audioconferencia
    - Planes de llamadas
    - Enrutamiento directo

-   Habilitación de usuario

-   Puntos de conexión

-   Uso y calidad

-   Adopción

El [Libro de reproducción de habilitación del sitio para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) es un libro de Microsoft Excel. Cada una de estas cinco áreas de enfoque es una hoja independiente en el libro y cada tarea y actividad de implementación se agrupa en una de estas hojas.

![Captura de pantalla del libro de reproducción de habilitación del sitio](media/deploy-my-service-image1.png "Captura de pantalla del libro de reproducción")

> [!NOTE]
> Creará una instancia independiente del libro de juegos para cada sitio en el ámbito de la implementación de Teams.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Cómo usar el libro de reproducción

Independientemente del tamaño y la complejidad de la ubicación, la habilitación de cada sitio requiere que planee sus tareas y actividades lo suficientemente pronto como para ejecutarlas en orden óptimo, antes, durante y después de la implementación real del servicio. Le recomendamos que siga estos pasos a medida que planee y ejecute su propio viaje a La voz de Microsoft Teams.

1. Descargue el Libro de reproducción de habilitación [del sitio para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para Microsoft Teams Voice.

2. Cree una copia independiente del libro de reproducción para cada sitio.

3. En la pestaña de la hoja denominada **Playbook para {SiteName-Code},** reemplace **{SiteName-Code}** por el nombre del sitio o el código de sitio correspondiente.

4. Escriba el **nombre del sitio, el código del** sitio y la fecha de inicio **planificada,** como se muestra a continuación. Este es un paso crítico, ya que ajusta las fechas límite recomendadas para cada actividad del libro de reproducción.

   ![Ejemplo con nombre de sitio, código de sitio y fecha de inicio planeada](media/deploy-my-service-image2.png "Ejemplo con el nombre del sitio de Nueva York, el código de sitio NY01 y la fecha de lanzamiento planeada del 20 de marzo al 18")

5. Revise cada actividad, haga las acciones necesarias y actualice el estado a medida que pase por la escala de tiempo. El estado se representa gráficamente, como se describe a continuación:
  
   - ![Ilustración de una marca de verificación verde Sí o no aplicable ](media/deploy-my-service-image3.png) **(verde):** la actividad se ha completado o no es aplicable para este sitio y no se necesita ninguna acción adicional.</li>
   - ![Ilustración de un signo de exclamación amarillo La actividad aún no se ha completado (amarillo): la actividad aún no se ha completado y debe actualizarse a Sí o No en ](media/deploy-my-service-image4.png) <strong></strong> su programación.</li>
   - ![Ilustración de una X roja que indica que no ](media/deploy-my-service-image5.png) <strong>(rojo):</strong> la actividad no se puede completar debido a un problema y debe llevarse a la reunión de estado del proyecto.</li></ul>

6. El estado se incluye en cada sección y el encabezado de sección tiene formato con uno de estos indicadores de estado. **El estado semanal** también se actualiza automáticamente.

![Captura de pantalla de las actualizaciones semanales de estado en el libro de reproducción](media/deploy-my-service-image6.png "Captura de pantalla de las actualizaciones semanales de estado en el libro de reproducción")

> [!TIP]
> Repita los pasos anteriores para todas las ubicaciones que tiene.

> [!IMPORTANT]
> Es posible que algunos pasos no sean aplicables a todas las ubicaciones y sitios. Si una actividad específica no es relevante para un sitio, debe seleccionar **No aplicable** a esta actividad. **DO NOT DELETE** any rows in the playbook; si lo hace, las fórmulas de succión de estado no funcionarán.<br/><br/>
Preste atención a las actividades que pueden llevar más tiempo de lo planeado, como porción de números y actividades de compras. Estas actividades pueden afectar negativamente a la escala de tiempo de implementación del sitio. Asegúrese de revisar y actualizar la lista de actividades y [](./envision-steering-committee-complete-guide.md) la escala de tiempo asociada semanalmente y presentarlas en reuniones del comité de dirección para asegurarse de que las partes interesadas son conscientes del estado de cada sitio y de las posibles desviaciones de la programación de implementación.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decida si el Playbook de habilitación del sitio es necesario para su implementación.</li><li>Decida quién será el responsable de personalizar el Playbook de habilitación del sitio para Microsoft Teams para cada sitio que implemente.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Descargue el Libro de reproducción de habilitación del sitio.</a></li><li>Personalice el Libro de reproducción de habilitación del sitio para el primer sitio.</li><li>Repita el procedimiento según sea necesario para sitios adicionales.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
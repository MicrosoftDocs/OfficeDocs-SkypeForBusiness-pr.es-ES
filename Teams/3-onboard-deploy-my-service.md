---
title: Implementar el servicio de voz de nube de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Descargue la Guía de activación de sitio para planear la implementación de equipos y acelerar y optimizar la adopción de usuario, la percepción de la calidad y la satisfacción.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f59b7568f5ec0d3d9b6ef3b04f4094b222d0702b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="deploy-my-service"></a>Implementar mi servicio

Este artículo ofrece una visión general de los requisitos para implementar correctamente Servicios de nube de voz. Siguiendo la orientación prescriptiva para implementar servicios de voz de la nube, puede asegurarse de que correctamente cuenta para todos los requerimientos y ofrecer resultados repetibles.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Guía de habilitación del sitio para cargas de trabajo de voz de Microsoft Teams

Utilice esta guía para ayudar a su organización a planear y ejecutar la distribución de las características de voz de Microsoft Teams en el sitio por sitio.

Incluye actividades necesarios, recomendada escalas de tiempo y vínculos a las instrucciones correspondientes para cada actividad, esta guía cubre Guía de end-to-end para ayudar a garantizar una implementación satisfactoria de voz de equipos para un sitio determinado, centrándose en factores que son importantes para el usuario.

Al terminar las actividades de esta guía, su organización puede:

-   Efectivamente, planear y programar la implementación de equipos.

-   Acelerar y optimizar la adopción de usuario.

-   Reducir las necesidades de soporte y aumentar la satisfacción del usuario.

> [!NOTE]
> En este artículo y la guía asociada no se pretenden describir cada paso de configuración técnica necesaria para la activación del servicio o proporcionar el tono de marcado a un sitio específico. En su lugar, se concentran en las actividades y tareas que se recomienda a los usuarios a bordo fácilmente y pedirles que comienzan a consumir cargas de trabajo de equipos voz a través de una transición suave y rápida con una velocidad alta de adopción, mientras minimiza los requerimientos de soporte. Para obtener orientación técnica sobre cómo mejorar la configuración de su entorno para la voz de los equipos, vea Resumir listas de comprobación para [configurar las cargas de trabajo de equipos voz](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams), [capacidades de equipos](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities), [redes de equipos](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)y [Habilitar Office 365 ](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Áreas de enfoque de la Guía

El enfoque de la guía es tratar los factores que influyen en la percepción del usuario de una implementación de voz de los equipos. Las actividades y tareas se agrupan en las siguientes áreas de focalización:

-   Validación de la preparación del servicio

-   Habilitación de usuario

-   Puntos de conexión

-   Calidad y uso

-   Adopción

El [Sitio de habilitación de guía de voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) es un libro de Microsoft Excel. Cada una de estas áreas de cinco focalización es una hoja independiente del libro y cada actividad y la tarea de despliegue se agrupan en una de estas hojas.

![Captura de pantalla de la guía] (media/deploy-my-service-image1.png "Captura de pantalla de la guía")

> [!NOTE]
> Creará una instancia independiente de la guía para cada sitio en el ámbito de la implementación de equipos.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Cómo utilizar la Guía

Independientemente del tamaño y complejidad de la ubicación, la habilitación de cada sitio requiere planear las tareas y actividades lo bastante pronto y ejecutarlas en el orden óptimo: antes, durante y después de la implantación real del servicio. Recomendamos que siga estos pasos como planear y ejecutar su propio viaje a voz de Microsoft Teams.

1.  Descargue la [Guía de activación de sitio para voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para equipos de Microsoft Voice.

2.  Crear una copia independiente de la guía para cada sitio.

3.  En la ficha de la hoja denominada **Guía para {SiteName código}**, reemplace **{SiteName código}** con el nombre de sitio correspondiente o el código de sitio.

4.  Escriba **el nombre del sitio, código del sitio**y la **fecha de inicio planeada**, tal como se ilustra a continuación. Éste es un paso crítico, porque se ajusta los plazos recomendados para todas las actividades en la guía.

    ![Ejemplo con nombre del sitio de Nueva York, NY01, el código de sitio y fecha de inicio planeada de 20-Mar-18] (media/deploy-my-service-image2.png "Ejemplo con nombre del sitio de Nueva York, NY01, el código de sitio y fecha de inicio planeada de 20-Mar-18")

5.  Revise cada actividad, tome las acciones necesarias y actualizar el estado a medida que vaya a través de la línea de tiempo. Estado se representa gráficamente, tal como se describe a continuación:
    <ul>
    <li>![Marca de verificación verde](media/deploy-my-service-image3.png) **Sí o no aplicable (verde):** se ha completado la actividad, o no es aplicable para este sitio y no es necesario realizar ninguna otra acción.</li>
    <li>![Signo de exclamación amarillo](media/deploy-my-service-image4.png) **la actividad no se completa aún (amarillo):** la actividad no ha finalizado todavía y debe actualizarse a sí o No en su programación.</li>
    <li>![X roja](media/deploy-my-service-image5.png) **sin (rojo):** no se puede completar debido a un problema de la actividad y se llevarán a la reunión de estado del proyecto.</li></ul>

6.  Dentro de cada sección se resume el estado y el título de sección tenga con uno de estos indicadores de estado. **Estado semanal** también se actualiza automáticamente.

![Captura de pantalla de la semanal estado resúmenes de la guía] (media/deploy-my-service-image6.png "Captura de pantalla de la semanal estado resúmenes de la guía")

> [!TIP]
> Repita los pasos anteriores para todas las ubicaciones que usted tiene.


> [!IMPORTANT]
> Algunos pasos no sería aplicables a todos los sitios y ubicaciones. Si una actividad específica no es relevante para un sitio, debe seleccionar **no es aplicable** para esta actividad. **No elimine** cualquiera de las filas en la Guía; Si lo hace, no funcionarán las fórmulas de resumen de estado.<br/><br/>
Preste atención a las actividades que podrían tardar más tiempo del planeado, como número de traslado y las actividades de compras. Estas actividades pueden afectar negativamente a la escala de tiempo de implementación del sitio. Asegúrese de revisar y actualizar la lista de actividades y la escala de tiempo asociado semanalmente y presentarlos en las [reuniones del Comité de dirección](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) para asegurarse de que los interesados conozcan el estado de cada sitio y cualquier desviación del plan de implementación de.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir si es necesaria para la implementación de la Guía de habilitación del sitio.</li><li>Decidir quién será responsable de la personalización de la Guía de habilitación del sitio para Microsoft Teams para cada sitio que va a implementar.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Descargue la Guía de habilitación del sitio.</li><li>Personalizar la Guía de habilitación del sitio para su primer sitio.</li><li>Repita según sea necesario para otros sitios.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
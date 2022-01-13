---
title: Usar el Asistente para la incorporación de trabajadores en primera línea para que su fuerza de trabajo de primera línea esté en funcionamiento
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar el Asistente para la incorporación de trabajadores en primera línea para implementar rápidamente una experiencia en Teams adaptada a los trabajadores y administradores de primera línea de su organización.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97f8994ecc5c7aef610e040f30b43803f03c6844
ms.sourcegitcommit: efea3b3b9dceb1a1d82eb7a09a5104dcd6df8abf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61993196"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Usar el Asistente para la incorporación de trabajadores en primera línea para que su fuerza de trabajo de primera línea esté en funcionamiento

## <a name="overview"></a>Información general

El Asistente para la incorporación de trabajadores en primera línea de la Centro de administración de Microsoft 365 simplifica la incorporación de trabajadores de primera línea a su organización. El asistente le permite implementar rápidamente una experiencia en Microsoft Teams que está adaptada a su personal de primera línea. Con el asistente, puede iniciar fácilmente la implementación piloto de Teams para los trabajadores de primera línea de su organización.

El asistente configura un equipo para los trabajadores [](manage-policy-packages.md) de primera línea y asigna licencias y paquetes de directivas a cada miembro del equipo. Puede crear su equipo desde cero o desde una plantilla [de equipo](get-started-with-teams-templates-in-the-admin-console.md)y, a continuación, agregar usuarios y asignar roles. El rol determina el paquete de directivas que el asistente asigna a cada usuario.

Actualmente, el asistente admite la adición de 100 usuarios cada vez que lo ejecute. Estamos trabajando en aumentar el número de usuarios por ejecución pronto. Vuelva aquí para ver las actualizaciones más recientes.

El asistente está disponible para todas las organizaciones que tengan al menos una [licencia F.](https://www.microsoft.com/microsoft-365/enterprise/frontline) Puede ejecutar el asistente tantas veces como necesite para Teams personal de primera línea en diferentes ubicaciones o sitios de su organización.

Consulte este breve vídeo para obtener información general sobre cómo ejecutar el asistente para incorporar a su personal de primera línea.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> Este asistente le permite incorporar rápidamente a su personal de primera línea para Teams a través del Centro de administración de Microsoft 365. Para obtener información sobre cómo implementar Teams personal de primera línea con scripts, vea Cómo aprovisionar Teams a escala para los trabajadores [de frontline](flw-scripted-deployment.md).

> [!NOTE]
> El asistente aún no admite etiquetas [de confidencialidad.](sensitivity-labels.md) Si su organización requiere etiquetas de confidencialidad para crear un equipo, no verá el asistente en el Centro de administración de Microsoft 365.

## <a name="run-the-wizard"></a>Ejecutar el asistente

1. En el panel de navegación izquierdo del [Centro de administración de Microsoft 365](https://admin.microsoft.com/), elija **Configurar.** Vaya a la **sección Aplicaciones y correo** electrónico y, a continuación, en Activar y ejecutar la plantilla de primera línea, seleccione **Ver.**  Aquí puede obtener más información sobre las capacidades que ofrece Microsoft 365 para los trabajadores de primera línea.

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Captura de pantalla de la página de detalles de la experiencia de incorporación de trabajadores de frontline en el Centro de administración de Microsoft 365" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. Cuando esté listo, seleccione **Empezar a** ejecutar el asistente.

3. Escriba un nombre para el equipo, agregue uno o varios propietarios del equipo y seleccione una configuración de privacidad. A continuación, elija si desea crear el equipo desde cero o desde una plantilla de equipo. Las plantillas de equipo vienen con canales y pestañas predefinidos, que optimizan el equipo para una necesidad o proyecto empresarial en particular.

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="Captura de pantalla de la página Configurar un equipo del asistente" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. Agregue usuarios al equipo. También puede agregar grupos. Si agrega grupos, tenga en cuenta que las licencias y los paquetes de directivas se asignan directamente a cada usuario del grupo, no al propio grupo.

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="Captura de pantalla de la página Agregar usuarios del asistente donde agrega usuarios y grupos a su equipo" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. Asigne uno de los siguientes roles a cada miembro del equipo: Trabajador de frontline, Administrador de línea frontal, Ninguno. 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="Captura de pantalla de la página Asignar roles de trabajo del asistente donde asigna roles, ubicaciones y licencias a los miembros del equipo" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    Al asignar un rol de trabajador de frontline o administrador de frontline, ese usuario recibirá un paquete de directiva. El paquete de directivas creará una experiencia en Teams que se adapte a su rol. Esta experiencia incluye aplicaciones y directivas ancladas previamente para la comunicación y colaboración de los trabajadores en primera línea y los administradores en buen estado.

    A continuación, seleccione una ubicación y asigne una Microsoft 365 F a cada miembro del equipo. Si no tiene suficientes licencias, puede seleccionar Comprar **más** licencias para comprar más licencias.  

6. Elija quién recibe el correo electrónico de estado después de completar el asistente. El correo electrónico contiene información de éxito y errores sobre las acciones realizadas por el asistente para crear el equipo, agregar miembros del equipo y asignar un paquete de licencia y directiva a cada miembro &mdash; del equipo. Use esta información para solucionar los errores que se puedan producir.

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="Captura de pantalla de la página Agregar destinatarios de correo electrónico de estado del asistente" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. Revise las selecciones y, a continuación, **seleccione Confirmar**.

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="Captura de pantalla de la página Revisar equipo del asistente donde revisa la configuración del equipo" lightbox="media/flw-onboarding-wizard-review-team.png":::

    El asistente crea el equipo y asigna licencias y paquetes de directivas a los miembros del equipo. Puede tardar unos minutos en completarse, después de lo cual los destinatarios elegidos recibirán un correo electrónico de estado.

8. Estás en camino, pero aún no has terminado. A continuación, consulte la [sección Qué hacer después de ejecutar el](#what-to-do-after-running-the-wizard) asistente de este artículo.

## <a name="what-to-do-after-running-the-wizard"></a>Qué hacer después de ejecutar el asistente

Después de ejecutar el asistente, es importante:

- Haga saber a los trabajadores y administradores de primera línea que están asignados Teams licencias.
- Si usa dispositivos compartidos, asegúrese de que Teams está instalado en esos dispositivos. Si su organización usa un modelo de "traer su propio dispositivo", haga saber a los trabajadores y administradores de primera línea que tienen que descargar e instalar Teams en sus dispositivos.

Cuando el empleado de primera línea abra Teams por primera vez, recibirá una experiencia personalizada de primera ejecución, que incluye chats y canales, llamadas y administración de tareas, todo dentro de Teams.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar los paquetes de directivas para Teams](manage-policy-packages.md)
- [Usar plantillas de equipo en el centro Teams administración](get-started-with-teams-templates-in-the-admin-console.md)

---
title: Usar el asistente de incorporación de personal de primera línea para que su fuerza de trabajo esté en funcionamiento
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar el asistente para la incorporación de trabajadores de primera línea para implementar rápidamente una experiencia de Teams adaptada a los trabajadores de primera línea y los administradores de su organización.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ac4db418927c34920614c65d6f94a400ff116a91
ms.sourcegitcommit: 1e8cff687b12348d4ecc538084ab57bbba23b523
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2022
ms.locfileid: "64703686"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Usar el asistente de incorporación de personal de primera línea para que su fuerza de trabajo esté en funcionamiento

## <a name="overview"></a>Información general

El Asistente para la incorporación de trabajadores de primera línea en el Centro de administración de Microsoft 365 simplifica la incorporación de trabajadores de primera línea a su organización. El asistente le permite implementar rápidamente una experiencia de Microsoft Teams adaptada a su personal de primera línea. Con el asistente, puede iniciar fácilmente la implementación piloto de Teams para los trabajadores de primera línea de su organización.

El asistente configura un equipo para los trabajadores de primera línea y asigna licencias y [paquetes de directivas](manage-policy-packages.md) a cada miembro del equipo. Puede crear su equipo desde cero o a partir de una [plantilla de equipo](get-started-with-teams-templates-in-the-admin-console.md) y, a continuación, agregar usuarios y asignar roles. El rol determina el paquete de directivas que el asistente asigna a cada usuario.

Actualmente, el asistente admite la adición de 100 usuarios cada vez que se ejecute. Estamos trabajando para aumentar pronto el número de usuarios por ejecución. Vuelve aquí para ver las últimas actualizaciones.

El asistente está disponible para todas las organizaciones que tengan al menos una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline). Puede ejecutar el asistente tantas veces como sea necesario para implementar Teams para los empleados de primera línea en diferentes ubicaciones o sitios de la organización.

Consulte este breve vídeo para obtener información general sobre cómo ejecutar el asistente para incorporar a su personal de primera línea.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> Este asistente le permite incorporar rápidamente a sus empleados de primera línea para Teams a través de la Centro de administración de Microsoft 365. Para obtener información sobre cómo implementar Teams a los empleados de primera línea con scripts, vea [Cómo aprovisionar Teams a escala para los trabajadores de frontline](flw-scripted-deployment.md).

> [!NOTE]
> El asistente aún no admite [etiquetas de confidencialidad](sensitivity-labels.md) . Si su organización requiere etiquetas de confidencialidad para crear un equipo, no verá el asistente en el Centro de administración de Microsoft 365.

## <a name="run-the-wizard"></a>Ejecutar el asistente

1. En el panel de navegación izquierdo de la [Centro de administración de Microsoft 365](https://admin.microsoft.com/), elija **Configuración**. Vaya a la sección **Aplicaciones y correo electrónico** y, a continuación, en **Poner en marcha su personal de primera línea**, seleccione **Ver**. Aquí puede obtener más información sobre las capacidades que Microsoft 365 para los trabajadores de primera línea.

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Captura de pantalla de la página de detalles de la experiencia de incorporación de trabajadores de primera línea en el Centro de administración de Microsoft 365" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. Cuando esté listo, seleccione **Comenzar** para ejecutar el asistente.

3. Escriba un nombre para su equipo, agregue uno o más propietarios del equipo y seleccione una configuración de privacidad. Después, elija si desea crear su equipo desde cero o a partir de una plantilla de equipo. Las plantillas de equipo incluyen fichas y canales predefinidos, que optimizan el equipo para una necesidad o proyecto empresarial en particular.

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="Captura de pantalla de la página Configurar un equipo del asistente" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. Agregue usuarios al equipo. También puede agregar grupos. Si agrega grupos, tenga en cuenta que las licencias y los paquetes de directivas se asignan directamente a cada usuario del grupo, no al propio grupo.

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="Captura de pantalla de la página Agregar usuarios del asistente donde agregar usuarios y grupos a su equipo" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. Asigne uno de los siguientes roles a cada miembro del equipo: Frontline Worker, Frontline Manager, None. 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="Captura de pantalla de la página Asignar roles de trabajo del asistente donde se asignan roles, ubicaciones y licencias a los miembros del equipo" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    Al asignar un rol de frontline worker o frontline manager, ese usuario recibirá un paquete de directiva. El paquete de directivas creará una experiencia en Teams adaptada a su rol. Esta experiencia incluye aplicaciones y directivas ancladas previamente para una comunicación y colaboración con los trabajadores de primera línea y los administradores sanos.

    A continuación, seleccione una ubicación y asigne una licencia de Microsoft 365 F a cada miembro del equipo. Si no tiene suficientes licencias, puede seleccionar **Comprar más licencias** para comprar más licencias.  

6. Elija quién recibe el correo electrónico de estado una vez completado el asistente. El correo electrónico contiene información sobre el éxito y el error sobre las acciones realizadas por el asistentecrear&mdash; el equipo, agregar miembros al equipo y asignar una licencia y un paquete de directiva a cada miembro del equipo. Use esta información para solucionar los errores que puedan producirse.

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="Captura de pantalla de la página Agregar destinatarios de correo electrónico de estado del asistente" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. Revise las selecciones y, a continuación, seleccione **Confirmar**.

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="Captura de pantalla de la página Revisar equipo del asistente donde revisar la configuración del equipo" lightbox="media/flw-onboarding-wizard-review-team.png":::

    El asistente crea su equipo y asigna licencias y paquetes de directivas a los miembros del equipo. Puede tardar unos minutos en completarse, tras lo cual los destinatarios que eligió recibirán un correo electrónico de estado.

8. ¡Estás en camino, pero aún no has terminado! Después, consulte la sección [Qué hacer después de ejecutar el asistente](#what-to-do-after-running-the-wizard) de este artículo.

## <a name="what-to-do-after-running-the-wizard"></a>Qué hacer después de ejecutar el asistente

Después de ejecutar el asistente, es importante lo siguiente:

- Informe a los trabajadores de primera línea y a los administradores de que se les han asignado licencias de Teams.
- Si su organización usa dispositivos compartidos, asegúrese de que Teams esté instalado en esos dispositivos. Los usuarios que haya agregado al equipo recibirán un correo electrónico de bienvenida en el que se les pedirá que abran Teams.
- Si su organización usa un modelo "traer su propio dispositivo" (BYOD), informe a cada usuario que haya agregado al equipo de que tiene que descargar e instalar Teams en sus dispositivos. También recibirán un correo electrónico de bienvenida en el que se les pedirá que descarguen Teams.

    > [!NOTE]
    > Tenga en cuenta que los usuarios con licencias F1 no recibirán un correo electrónico de bienvenida porque la licencia F1 no incluye acceso al correo electrónico.  

Cuando el empleado de la primera línea abre Teams por primera vez, recibirá una experiencia de primera ejecución personalizada, que incluye chats y canales, llamadas y administración de tareas dentro de Teams.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar los paquetes de directivas para Teams](manage-policy-packages.md)
- [Usar plantillas de equipo en el centro de administración de Teams](get-started-with-teams-templates-in-the-admin-console.md)

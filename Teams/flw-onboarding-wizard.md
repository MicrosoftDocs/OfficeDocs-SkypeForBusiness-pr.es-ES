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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 461e73a4c4008d028e564c25b5842c7b59e2a57b
ms.sourcegitcommit: b17e5acadcca0261eaccc64e1b4ee457348f975c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2021
ms.locfileid: "58365926"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Usar el Asistente para la incorporación de trabajadores en primera línea para que su fuerza de trabajo de primera línea esté en funcionamiento

> [!NOTE]
> En este artículo se describe una característica que aún no se ha publicado. Estará próximamente. Si es administrador, puede averiguar cuándo se liberará esta característica en el Centro de mensajes (en la [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home)). Para mantenerse al tanto de las próximas Teams, consulte el [mapa de ruta Microsoft 365 ruta.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)

## <a name="overview"></a>Información general

El Asistente para la incorporación de trabajadores en primera línea de la Centro de administración de Microsoft 365 simplifica la incorporación de trabajadores de primera línea a su organización. El asistente le permite implementar rápidamente una experiencia en Microsoft Teams que está adaptada a su personal de primera línea. Con el asistente, puede iniciar fácilmente la implementación piloto de Teams para los trabajadores de primera línea de su organización.

El asistente configura un equipo para los trabajadores [](manage-policy-packages.md) de primera línea y asigna licencias y paquetes de directivas a cada miembro del equipo. Puede crear su equipo desde cero o desde una plantilla [de equipo](get-started-with-teams-templates-in-the-admin-console.md)y, a continuación, agregar usuarios y asignar roles. El rol determina el paquete de directivas que el asistente asigna a cada usuario.

El asistente está disponible para todas las organizaciones que tienen al menos una licencia Microsoft 365 F. Puede ejecutar el asistente tantas veces como necesite para Teams personal de primera línea en diferentes ubicaciones o sitios de su organización.

> [!NOTE]
> Este asistente le permite incorporar rápidamente a sus trabajadores de primera línea para Teams a través del Centro de administración de Microsoft 365. Para obtener más información sobre cómo implementar Teams a los trabajadores de primera línea con scripts, vea Cómo aprovisionar Teams a escala para los trabajadores [de frontline](flw-scripted-deployment.md).

## <a name="run-the-wizard"></a>Ejecutar el asistente

1. En el panel de navegación izquierdo del [Centro de administración de Microsoft 365](https://admin.microsoft.com/), seleccione **Configurar.** Vaya a la **sección Aplicaciones y correo** electrónico y, a continuación, en Activar y ejecutar la plantilla de primera línea, seleccione **Ver.**  Aquí puede obtener más información sobre las capacidades que ofrece Microsoft 365 para los trabajadores de primera línea.

2. Cuando esté listo, seleccione **Empezar a** ejecutar el asistente.

3. Escriba un nombre para su equipo, seleccione una configuración de privacidad y agregue uno o varios propietarios del equipo. A continuación, elija si desea crear el equipo desde cero o desde una plantilla de equipo. Las plantillas de equipo vienen con canales y pestañas predefinidos, que optimizan el equipo para una necesidad o proyecto empresarial en particular.

4. Agregue usuarios al equipo. También puede agregar grupos. Si agrega grupos, tenga en cuenta que las licencias y los paquetes de directivas se asignan directamente a cada usuario del grupo, no al propio grupo.

5. Asigne uno de los siguientes roles a cada miembro del equipo.

    - Trabajador en primera línea
    - Administrador de primera línea
    - Ninguna

    Al asignar un rol de trabajador de frontline o de administrador de frontline, ese usuario recibirá una experiencia en Teams que se adapte a su rol. Esto incluye aplicaciones y directivas ancladas previamente para la comunicación y colaboración de los trabajadores en primera línea y los administradores en buen estado.

    A continuación, asigne una Microsoft 365 F a cada miembro del equipo. Si no tiene suficientes licencias, puede seleccionar Comprar **más** licencias para comprar más licencias.  

6. Elija quién recibe el correo electrónico de estado después de completar el asistente. El correo electrónico contiene información de éxito y errores sobre las acciones realizadas por el asistente para crear el equipo, agregar miembros del equipo y asignar un paquete de licencia y directiva a cada miembro &mdash; del equipo. Use esta información para solucionar los errores que se puedan producir.

7. Revise las selecciones y, a continuación, **seleccione Confirmar**.

    El asistente crea el equipo y asigna licencias y paquetes de directivas a los miembros del equipo. Esto puede tardar unos minutos en completarse, después de lo cual los destinatarios elegidos recibirán un correo electrónico de estado.

8. Estás en camino, pero aún no has terminado. A continuación, consulte la [sección Qué hacer después de ejecutar el](#what-to-do-after-running-the-wizard) asistente de este artículo.

## <a name="what-to-do-after-running-the-wizard"></a>Qué hacer después de ejecutar el asistente

Después de ejecutar el asistente, es importante:

- Haga saber a los trabajadores y administradores de primera línea que están asignados Teams licencias.
- Si usa dispositivos compartidos, asegúrese de que Teams está instalado en esos dispositivos. Si su organización usa un modelo de "traer su propio dispositivo", haga saber a los trabajadores y administradores de primera línea que tienen que descargar e instalar Teams en sus dispositivos.

Cuando el empleado de primera línea abra Teams por primera vez, recibirá una experiencia personalizada de primera ejecución, que incluye chats y canales, llamadas y administración de tareas, todo dentro de Teams.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar los paquetes de directivas para Teams](manage-policy-packages.md)
- [Usar plantillas de equipo en el centro Teams administración](get-started-with-teams-templates-in-the-admin-console.md)
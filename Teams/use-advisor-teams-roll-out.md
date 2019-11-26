---
title: Usar el Asesor de Teams (versión preliminar) para ayudar a implementar Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: Use el Asesor de Teams (versión preliminar) para ayudar a planear y completar la implementación de Microsoft Teams.
ms.openlocfilehash: f7de348c6f8ca60cc1d062fce79725b4b18d0350
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "39209196"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Usar el Asesor de Teams para ayudar a implementar Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

El Asesor de Teams (versión preliminar) le guiará a través de la implementación de Microsoft Teams. Evalúa el entorno del inquilino de Office 365 e identifica las configuraciones más comunes que puede necesitar actualizar o modificar antes de poder implementar correctamente Teams. Después, el Asesor de Teams crea un Equipo de implementación (en Teams), con canales para cada una de las cargas de trabajo que desea implementar. Cada carga de trabajo en el Equipo de implementación viene con un plan de Planner completo que incluye todas las tareas de implementación para cada carga de trabajo.  Con este plan de Planner, podrá asignar las tareas a las personas responsables de cada fase del lanzamiento, (incluyendo el jefe de proyecto, administradores de Teams y Office 365, personal de soporte técnico, y su equipo de adopción y preparación del usuario). Cada tarea de implementación contiene todos los recursos e instrucciones que necesita para completar la tarea con éxito.

El Asesor de Teams forma parte del [centro de administración de Teams](https://admin.teams.microsoft.com). Para usar el Asesor de Teams la primera vez, haga clic en el botón **Iniciar** en el widget **Implementando la carga de trabajo de Teams** en el Panel. O vaya a **Planificación** > **Asesor**.

> [!IMPORTANT]
> El Asesor de Teams no está disponible para las implementaciones de Microsoft 365 Administración Pública - GCC High o DoD.

## <a name="using-advisor-for-teams-preview"></a>Usando el Asesor de Teams (versión preliminar)

No es necesario ser un administrador de Teams para usar el Asesor de Teams: cualquiera de los usuarios de su organización puede usarlo. Hemos establecido permisos especiales para que los usuarios que no sean administradores puedan ir al Asesor de Teams, aunque esté en el centro de administración de Teams. Debe ser un administrador de Teams, un administrador de servicios de Teams o un Administrador Global para abrir las evaluaciones de preparación de inquilinos.

La primera vez que use el Asesor de Teams, se creará un Equipo de implementación para usted en Teams. Se agregan canales para cada carga de trabajo que desea implementar. 


## <a name="available-advisor-for-teams-plans"></a>Planes disponibles para el Asesor de Teams

Aunque el Asesor de Teams se encuentra en versión preliminar, estamos proporcionando estos dos planes:

1. Chat, equipos, canales y aplicaciones
    - Evaluación de los inquilinos
    - Plan de Planner, incluidas las tareas de adopción
    - Encuesta de usuario de Forms
1. Reuniones y conferencias
    - Evaluación de los inquilinos
    - Plan de Planner, incluidas las tareas de adopción
    - Encuesta de usuario de Forms

Le recomendamos que empiece con el chat, equipos, canales y plan de aplicaciones. Cuando haya terminado la implementación de la carga de trabajo, vuelva al Asesor y haga clic en **Agregar canal** para iniciar la siguiente carga de trabajo. 

## <a name="tenant-assessment"></a>Evaluación de los inquilinos
Cada plan incluye una evaluación de preparación para inquilinos que puede usar para identificar y solucionar cualquier deficiencia en su entorno antes de implementar Teams. Esto es lo que cada evaluación comprueba:

### <a name="chat-teams-channels-and-apps"></a>Chat, equipos, canales y aplicaciones


|Evaluación  |Qué le indica  |
|---------|---------|
|Licencias de Teams     |Si tiene una suscripción activa con licencias de Teams disponibles |
|Licencias de Exchange     |Si tiene una suscripción activa con licencias de Exchange Online disponibles. Aunque Exchange no es necesario para las funciones básicas de Teams, la integración con Exchange ofrece una experiencia de Teams óptima.         |
|Licencias de SharePoint Online     | Si tiene una suscripción activa con licencias de SharePoint Online disponibles. Necesita una licencia de SharePoint Online por usuario para almacenar archivos, colaborar en canales y chatear. 
|Acceso de invitado habilitado     |Si el acceso de invitado está activado en Teams. La configuración de Azure Active Directory para el acceso de invitados no se revisa.   |
|Dominio personalizado configurado     |Si hay un dominio que no sea @onmicrosoft.com configurado para su inquilino  |
|Grupo estándar de nomenclatura configurado en Office 365     | Si se han configurado estándares de nomenclatura para los Grupos de Office 365        |
|Expiración de Grupo de Office 365 configurada     |  Si se ha definido una directiva de expiración de Grupo para los Grupos de Office 365. Si no es así, el valor se establece en nunca.        |
|Acceso externo configurado     |Si está activado el acceso externo, de modo que pueda comunicarse con organizaciones externas en Teams.          |

### <a name="meetings-and-conferencing"></a>Reuniones y conferencias


|Evaluación  |Qué le indica  |
|---------|---------|
|Licencias de Teams     |Si tiene una suscripción activa con licencias de Teams disponibles |
|Licencias de Exchange     |Si tiene una suscripción activa con licencias de Exchange Online disponibles. Aunque Exchange no es necesario para las funciones básicas de Teams, la integración con Exchange ofrece una experiencia de Teams óptima. |
|Licencias de audioconferencia    |Si tiene una suscripción activa con licencias de audioconferencia |
|Licencias de transmisión     |Si tiene una suscripción activa con licencias de transmisión, que puede usarse si se desea la Grabación de Reuniones. |
|Acceso de invitado     |Si el acceso de invitado está activado en Teams. La configuración de Azure Active Directory para el acceso de invitados no se revisa.|
|Dominio personalizado     |Si hay un dominio que no sea @onmicrosoft.com configurado para su inquilino.  |
|Acceso externo     |Si está activado el acceso externo, de modo que pueda comunicarse con organizaciones externas en Teams. |


### <a name="advisor-bot"></a>Bot del Asesor
Una vez que el Asesor cree el Equipo de implementación, el bot del Asesor entregará el siguiente mensaje.

>**¡Le damos la bienvenida al Equipo de implementación de Microsoft Teams!**
>  
>El propósito de este equipo es guiarlo a través de la implementación de Teams en su organización, proporcionándole todos los recursos necesarios y brindando un espacio de colaboración para el equipo del proyecto. Cada canal creado con el Asesor de Teams incluye un plan de Planner paso a paso y otros recursos, como una encuesta de usuarios de Forms que puede usarse durante toda la implementación. En cualquier momento, puede volver atrás y revisar la evaluación de preparación de inquilino o agregar otros planes de carga de trabajo con el centro de administración de Teams. 
> 
>**Llamada a la acción** 
>- Si no está familiarizado con Teams o Planner, consulte nuestra [Guía sobre Teams](https://teamsdemo.office.com/) y vea los [Vídeos de inicio rápido de Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 
>- Vaya al Equipo de implementación en Teams. Seleccione su canal de carga de trabajo (por ejemplo, chat, equipos, canales y aplicaciones) y seleccione la pestaña **Planner** para empezar.
> 
>Para más información sobre el Asesor de Teams, lea [Use el Asesor de Teams para implementar Microsoft Teams](use-advisor-teams-roll-out.md).
>
> [!IMPORTANT]
> El bot del Asesor de Teams solo se usa para enviar un mensaje de bienvenida al equipo de implementación. No se recopilan datos adicionales.

> [!IMPORTANT]
> De forma predeterminada, el bot del Asesor de Teams está habilitado. No lo deshabilite si usa o planea usar el Asesor de Teams.


## <a name="frequently-asked-questions"></a>Preguntas más frecuentes
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>¿Cuáles son los requisitos de licencia para el Asesor de Teams?
No hay otros requisitos de licencia adicionales más allá de tener licencia para Teams.

### <a name="can-i-delete-the-deployment-team"></a>¿Puedo eliminar el equipo de implementación?
Cuando el Asesor de Teams haya creado el Equipo de implementación, administrará el equipo como cualquier otro, con la posibilidad de eliminarlo. Tenga en cuenta que, si no elimina el equipo con el centro de administración de Teams, se le indicará que el equipo existe.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>¿Puedo agregar o quitar canales en el Equipo de implementación?
Sí, una vez que se haya creado el Equipo de implementación, podrá administrar los canales de la misma forma que lo haría con cualquier otro equipo.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>¿Puedo agregar o quitar miembros del equipo del proyecto en el Equipo de implementación?
Sí, una vez que se haya creado el Equipo de implementación, podrá administrarlo de la misma forma que lo haría con cualquier otro equipo.

### <a name="can-i-modify-the-planner-plans"></a>¿Puedo modificar los planes de Planner?
Sí, cuando el Asesor de Teams haya creado el Equipo de implementación, debe actualizar el plan de Planner para mejorar la compatibilidad con la implementación de Teams. Puede modificar cualquier cosa (los depósitos, las tareas, los detalles de las tareas), al igual que cualquier otro plan de Planner.


### <a name="can-i-modify-the-forms-survey"></a>¿Puedo modificar la encuesta de Forms?
Sí, una vez que el Asesor de Teams haya creado el Equipo de implementación, puede modificar la encuesta de Forms según sea necesario.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>¿Qué información recopila el Asesor de Teams sobre mi organización?
El Asesor de Teams solicita su acuerdo con la recopilación de información que no sea EUII (información de identificación de usuario final). La información que se recopila se encuentra en forma de telemetría, que proporciona retroalimentación a Microsoft sobre qué tan bien el Asesor de Teams impulsa los resultados correctos y dónde es posible que deba mejorarse. Estos mismos datos se usan para identificar oportunidades para que Microsoft pueda participar de forma proactiva en su organización con el fin de ayudarle con la implementación.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>¿Puedo usar el Asesor de Teams con FastTrack?
Sí, FastTrack aprovecha el Asesor de Teams para todos los clientes que buscan implementar Teams. Pueden ayudarle con la configuración inicial de su Equipo de implementación utilizando el Asesor de Teams (si lo requiere) y también ofrecer soporte necesario sobre temas específicos durante la implementación de Teams.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>¿Puedo usar el Asesor de Teams con un asociado?
Sí, puede usar el Asesor de Teams mientras usa también un asociado de implementación para la implementación de Teams. Si su asociado es un CSP y administra el inquilino en su nombre, puede usar el asesor de Teams para crear el Equipo de implementación y ayudarle a ejecutar el proyecto global. Además, puede trabajar con cualquier asociado si agrega a estos usuarios como invitados en el Equipo de implementación, para que puedan participar como miembros del equipo del proyecto global.

### <a name="how-do-i-use-planner"></a>¿Cómo puedo usar Planner?
Consulte [Ayuda de Microsoft Planner](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) y los [Vídeos de inicio rápido de Planner](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 

### <a name="how-do-i-use-forms"></a>¿Cómo puedo usar Forms?
Vaya al [Centro de ayuda de Forms](https://support.office.com/forms).

## <a name="related-topics"></a>Temas relacionados

[Cómo implementar Teams](How-to-roll-out-teams.md)

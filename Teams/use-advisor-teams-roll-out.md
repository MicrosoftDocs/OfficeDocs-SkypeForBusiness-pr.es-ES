---
title: Usar el Asesor de Teams (versión preliminar pública) para ayudar a implementar Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ''
description: Use el Asesor de Teams (versión preliminar pública) para ayudar a planear y completar la implementación de Microsoft Teams.
ms.openlocfilehash: ef9b22d7e4a3a3c3670acc766ee27cdc2c3de67c
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868157"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Usar el Asesor de Teams para ayudar a implementar Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

El Asesor de Teams (versión preliminar pública) le guiará a través de la implementación de Microsoft Teams. Evalúa el entorno de la organización de Microsoft 365 u Office 365 e identifica las configuraciones más comunes que puede necesitar actualizar o modificar antes de poder implementar correctamente Teams. Después, el Asesor de Teams crea un Equipo de implementación (en Teams), con canales para cada una de las cargas de trabajo que desea implementar. Cada carga de trabajo en el Equipo de implementación viene con un plan de Planner completo que incluye todas las tareas de implementación para cada carga de trabajo.  Con este plan de Planner, podrá asignar las tareas a las personas responsables de cada fase del lanzamiento, (incluyendo el jefe de proyecto, administradores de Teams y Microsoft 365 u Office 365, personal de soporte técnico, y su equipo de adopción y preparación del usuario). Cada tarea de implementación contiene todos los recursos e instrucciones que necesita para completar la tarea con éxito.

El Asesor de Teams forma parte del [centro de administración de Teams](https://admin.teams.microsoft.com). Como mínimo, necesitará una licencia de Microsoft 365 Empresa Básico para poder aprovechar la integración del Asesor de Teams con Forms y Planner. Para empezar a utilizar el asesor para Teams, haga clic en el botón **Inicio** en el widget **implementar Teams de carga** de trabajo en el panel. O vaya a **Planificar** > **Asesor para Teams**.

> [!IMPORTANT]
> El Asesor de Teams no está disponible para las implementaciones de Microsoft 365 Administración Pública - GCC High o DoD.

Para obtener una visión general guiada de la experiencia del asesor de Teams, consulte el vídeo [Implementar y configurar Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50)de Microsoft Mechanics.

## <a name="using-advisor-for-teams-public-preview"></a>Usando el Asesor de Teams (versión preliminar pública)

**Se necesitan licencias de Teams, de Forms y de Planner para usar el Asesor para Teams.** Sin embargo, no es necesario ser un administrador de Teams para usar el Asesor de Teams: cualquier usuario de su organización puede hacerlo. Hemos establecido permisos especiales para que los usuarios que no sean administradores puedan ir al Asesor de Teams, aunque esté en el centro de administración de Teams. Usted tiene que ser un administrador de Teams, un administrador de servicio de Teams o un administrador global para abrir las evaluaciones de preparación del inquilino (esto se debe a que los roles especiales no administrativos no tienen acceso a las APIs de Microsoft Graph subyacentes a las evaluaciones).

> [!IMPORTANT]
> Si no se muestra el **Asesor para Teams** en **Planificar** en el centro de administración de Teams, esto significa que el usuario no tiene licencia para Teams. Este comportamiento cambiará en el futuro.

La primera vez que utilice el asesor para Teams, creará un equipo de implementación para usted en Teams. Se agrega un canal para cada carga de trabajo que seleccione.

> [!IMPORTANT]
> Si ya se ha creado un equipo de implementación y otro usuario intenta crearlo, obtendrá un error que le indicará que se ponga en contacto con el equipo de soporte. Esto evita que Teams revele involuntariamente información sobre el equipo existente y sus miembros. Pídale al propietario del equipo de implementación que lo añada o póngase en contacto con su persona de soporte para obtener ayuda.

## <a name="available-advisor-for-teams-plans"></a>Asesor disponible para los planes de Teams

Aunque asesor para equipos se encuentra en la versión preliminar pública, ofreceremos los dos siguientes planes:

1. Chat, equipos, canales y aplicaciones
    - Evaluación de los inquilinos
    - Plan de Planner, incluidas las tareas de adopción
    - Encuesta de usuario de Forms
    - Asesor de los Teams bot
1. Reuniones y conferencias
    - Evaluación de los inquilinos
    - Plan de Planner, incluidas las tareas de adopción
    - Encuesta de usuario de Forms
    - Asesor de los Teams bot
1. Actualización de Skype Empresarial
    - Evaluación de los inquilinos
    - Plan de Planner, incluidas las tareas de adopción
    - Encuesta de usuario de Forms
    - Asesor de los Teams bot
    - Diseñado para clientes que actualmente usan Skype Empresarial Online o entornos locales de Skype Empresarial, el plan de actualización de Skype Empresarial le ayudará a evitar las conjeturas en el proceso de la actualización. Aprovechando un marco de éxito comprobado para implementar el cambio, el plan le guiará a través del proceso paso a paso, tanto si acaba de empezar a usar Teams como si ya usa Teams junto a Skype Empresarial o si está listo para actualizar. El plan también le conectará con [instrucciones en línea y procedimientos recomendados](https://aka.ms/SkypeToTeams), [activos descargables](https://aka.ms/UpgradeSuccessKit), [en directo 1: muchos talleres de planificación](https://aka.ms/UpgradeWorkshops) y recursos adicionales para dar soporte a su éxito.

Te recomendamos que empieces con el plan de chat, equipos, canales y aplicaciones. Cuando haya terminado de implementar esa carga de trabajo, vuelva a asesor para Teams y haga clic en **Agregar canal** para iniciar la siguiente carga de trabajo.

## <a name="tenant-assessment"></a>Evaluación del inquilino
Cada plan incluye una evaluación de la preparación de los inquilinos que usted puede utilizar para identificar rápidamente los aspectos de su entorno que pueden necesitar corrección antes de desplegar los equipos. Las evaluaciones incluyen requisitos previos y mejores prácticas. Cada prueba de evaluación tendrá una marca de verificación verde o un triángulo de advertencia naranja. 

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>Una marca de verificación verde significa que su inquilino pasó la prueba específica. 
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>Un triángulo de advertencia naranja significa que le sugerimos que haga un seguimiento para determinar si es necesario realizar alguna acción (por ejemplo, se recomienda, pero no es necesario, una política de caducidad del Grupo Microsoft 365).

> [!IMPORTANT]
> Una vez que un usuario con un rol administrativo inicia el asesor para Teams, todas las evaluaciones se ejecutan en segundo plano. Si actualiza o repara algo, es posible que no se refleje en sus evaluaciones durante un máximo de 24 horas. Este es un caso provisional: tan pronto como asesor para Teams deja la versión preliminar pública y está disponible en general, las evaluaciones se actualizarán casi en tiempo real.

Las siguientes secciones describen cada evaluación, incluyendo si algo es un requisito previo o mejores prácticas, qué es lo que cada evaluación está haciendo y por qué, y orientación para remediarlo según sea necesario.

### <a name="assessment-tests-for-all-workloads"></a>Pruebas de evaluación para todas las cargas de trabajo

|Prueba de evaluación  |Qué le indica  |
|---------|---------|
|Dominio de vanidad configurado     |Si existe un dominio non-@onmicrosoft.com configurado para el inquilino (por ejemplo, @contoso.onmicrosoft.com). Puede utilizar el dominio @onmicrosoft.com, por supuesto, o puede configurar un dominio de vanidad: su elección. Para más información, lea [Agregar un dominio a Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). |
|Licencias de Teams     |Este es un requisito previo: usted**debe tener **licencias de Teams para poder desplegar Teams. Consulta Microsoft Graph para ver si tiene licencias de Equipos (con al menos una licencia disponible para asignar). Para obtener más información, lea la [Descripción del servicio de Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).    |
|Licencias en línea de Exchange     |Si tiene una suscripción activa con licencias de Exchange Online disponibles. Aunque Exchange no es necesario para las funciones básicas de Teams, la integración con Exchange ofrece una experiencia de Teams óptima. Consulta Microsoft Graph para analizar las suscripciones asociadas con su arrendatario y validar si tiene suscripciones con una licencia de Exchange Online elegible (con al menos una licencia disponible para asignar). Para más información, lea [Cómo interactúan Teams y Exchange](exchange-teams-interact.md).    |
|Licencias de SharePoint Online     |Si tiene una suscripción activa con licencias de SharePoint Online disponibles. Recomendamos una licencia de SharePoint Online por usuario para proporcionar OneDrive para la Empresa para el almacenamiento de archivos en chats Consulta Microsoft Graph para ver si tiene licencias de SharePoint Online (con al menos una licencia disponible para asignar). Para obtener más información, lea [Cómo SharePoint Online y OneDrive para la Empresa interactúan con Teams](https://docs.microsoft.com/microsoftteams/sharepoint-onedrive-interact).    |
|Acceso de invitado habilitado     |Si el [acceso de invitados](guest-access.md) está activado. El acceso de invitados le permite invitar a usuarios externos a unirse a sus equipos. Utilice la [lista de control de acceso de invitados de Teams](guest-access-checklist.md) para ver cómo activar el acceso de invitados en Teams; la lista de control incluye las configuraciones necesarias de Azure AD. |
|Acceso externo configurado     |Ya sea[ acceso externo](manage-external-access.md) está activado. Por defecto, está activado, con federación abierta. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>Evaluaciones para chat, equipos, canales y aplicaciones

Además de las [pruebas de evaluación para todas las cargas de trabajo](#assessment-tests-for-all-workloads), se realizan las siguientes evaluaciones adicionales para la carga de trabajo de chat, equipos, canales y aplicaciones:

|Prueba de evaluación  |Qué le indica  |
|---------|---------|
|Directiva de nomenclatura de grupos de Microsoft 365 configurada     |Si se han configurado estándares de nomenclatura para Grupos de Microsoft 365. La Directiva de nomenclatura de Grupos de Microsoft 365 permite a su organización aplicar una estrategia de asignación de nombres coherente a los equipos creados por los usuarios y también se aplica a otras cargas de trabajo de grupos (incluidos Outlook, SharePoint, Planner y Yammer). Esta prueba consulta Azure AD a través de Microsoft Graph para comprobar la existencia de directivas de nomenclatura que se aplican a los Grupos de Microsoft 365. Para obtener más información, lea la [Directiva de Nomenclatura de grupos](https://docs.microsoft.com/microsoft-365/admin/create-groups/groups-naming-policy).    |
|Directiva de expiración de grupos de Microsoft 365 configurada     |Si se ha definido una Directiva de caducidad de grupo para los Grupos de Microsoft 365. Esto permite a su organización eliminar automáticamente los equipos inactivos. Está desactivado por defecto. Esta prueba consulta Azure AD a través de Microsoft Graph e informa si el valor ha sido modificado desde el valor predeterminado. Para más información, lea la [Política de Expiración de grupo de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy).    |

### <a name="assessments-for-meetings-and-conferencing"></a>Evaluaciones para reuniones y conferencias

Además de las [pruebas de evaluación para todas las cargas de trabajo](#assessment-tests-for-all-workloads), se realizan las siguientes evaluaciones adicionales para la carga de trabajo de reuniones y conferencias:

|Prueba de evaluación  |Qué le indica  |
|---------|---------|
|Licencias de audio conferencia    |Si tiene una suscripción activa con licencias de audio conferencia. Este es un requisito previo si está implementando puentes de audio conferencia. Consulta el Microsoft Graph para ver si tiene licencias de audio conferencia (con al menos una licencia disponible para asignar). Para obtener más información, lea[Licencias adicionales para Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).    |
|Licencias de transmisión     |Si tiene una suscripción activa con licencias de Microsoft Stream. Este es un requisito previo si desea activar la grabación de reuniones. Consulta el Microsoft Graph para ver si tiene licencias de Microsoft Stream (con al menos una licencia disponible para asignar). Para obtener más información sobre Stream y cómo activarlo, lea [Grabación de reuniones en la nube de Teams](cloud-recording.md).

### <a name="assessments-for-skype-for-business-upgrade"></a>Evaluaciones para actualizaciones de Skype Empresarial
Además de las [Pruebas de evaluación para todas las cargas de trabajo](#assessment-tests-for-all-workloads), la actualización de Skype Empresarial también incluye evaluaciones utilizadas en el plan de reuniones y conferencias.

### <a name="advisor-for-teams-bot"></a>Asesor de los Teams bot

Una vez que asesor para Teams crea su equipo de implementación, el bot asesor entrega el siguiente mensaje en el canal general:

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
> El bot asesor de Teams está activado de forma predeterminada. No lo apague si utiliza o planea utilizar el servicio de asesor para Teams.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>¿Cuáles son los requisitos de licencia para el Asesor de Teams?
Como mínimo, necesitará Microsoft 365 Empresa Básico para poder aprovechar la integración del Asesor de Teams con Forms y Planner.

### <a name="can-i-delete-the-deployment-team"></a>¿Puedo eliminar el equipo de implementación?
Cuando el Asesor de Teams haya creado el Equipo de implementación, administrará el equipo como cualquier otro, con la posibilidad de eliminarlo. Tenga en cuenta que, si no elimina el equipo utilizando el centro de administración de equipos, el centro de administración de equipos mostrará que el equipo sigue existiendo. Este es un caso provisional: se corregirá cuando asesor para Teams abandone el período de versión preliminar pública y esté disponible para el público general.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>¿Puedo agregar o quitar canales en el Equipo de implementación?
Sí, una vez que se haya creado el Equipo de implementación, podrá administrar los canales de la misma forma que lo haría con cualquier otro equipo.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>¿Puedo agregar o quitar miembros del equipo del proyecto en el Equipo de implementación?
Sí, una vez que se haya creado el Equipo de implementación, podrá administrarlo de la misma forma que lo haría con cualquier otro equipo.

### <a name="can-i-modify-the-planner-plans"></a>¿Puedo modificar los planes de Planner?
Sí, cuando el Asesor de Teams haya creado el Equipo de implementación, debe actualizar el plan de Planner para mejorar la compatibilidad con la implementación de Teams. Puede modificar cualquier cosa (los depósitos, las tareas, los detalles de las tareas), al igual que cualquier otro plan de Planner.

### <a name="can-i-modify-the-forms-survey"></a>¿Puedo modificar la encuesta de Forms?
Sí, una vez que el Asesor de Teams haya creado el Equipo de implementación, puede modificar la encuesta de Forms según sea necesario.

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>¿Hay alguna diferencia entre Asesor de Teams en GCC?
Sí, los formularios de encuesta de usuario se crean, pero no se anclan en canales de plan, ya que la aplicación de formularios de Teams no está disponible en GCC en este momento.

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

[Procedimientos recomendados para organizar los equipos en Teams](best-practices-organizing.md)

[Nombres de productos e identificadores de planes de servicio para licencias](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference
)

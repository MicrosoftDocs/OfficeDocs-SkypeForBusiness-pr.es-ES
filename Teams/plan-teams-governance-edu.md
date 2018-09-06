---
title: Gobierno de Microsoft Education preguntas más frecuentes para profesionales de TI - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Respuestas a las preguntas más frecuentes de los administradores de grupos de Microsoft Education que usan los equipos.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4991990143b0292f83b5c71b8b2bf01a5d612184
ms.sourcegitcommit: 5943c41bac520558733d08f4a9ecc4425c422ff9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "22599457"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Gobierno de Microsoft Education preguntas más frecuentes para los administradores

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>¿Cómo controlar la creación del equipo? Le preocupa a los alumnos va a crear equipos inapropiados.

Para evitar inapropiados o engañoso son nombres, o simplemente para proporcionar más estructura de cómo se denominan los equipos, puede usar los grupos de 365 Office directiva (actualmente en la vista previa) de nomenclatura:

-   **Directiva de nomenclatura de prefijo sufijo** Puede usar prefijos o sufijos para definir la convención de nomenclatura de equipos (grupos), por ejemplo, **GRP_US_My Group_Engineering**. Los prefijos y sufijos se pueden corregir las cadenas o atributos de usuario (por ejemplo, **[departamento]**) que se agregan al nombre en función del usuario que está creando el equipo.
-   **Custom bloqueados palabras** Puede cargar un conjunto de palabras que los usuarios de una organización específica no se pueden utilizar en los nombres de los equipos que crean. Por ejemplo, puede bloquear los términos **consejero Delegado**, **nóminas**y **recursos humanos** se usen en los nombres de equipo para que no se aplican a los grupos.
-   **Clasificación** Puede crear clasificaciones de que los usuarios de su organización pueden establecer al crear un grupo de Office 365. 

> [!IMPORTANT]
> Uso de la directiva de nomenclatura de grupos de Office 365 requiere licencias de Azure Active Directory Premium P1 o licencias de Azure AD básica EDU para cada usuario único que es un miembro de uno o varios grupos de Office 365.

Para obtener instrucciones detalladas, vea [Directiva de nomenclatura de grupos de Office](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Si los equipos se crean automáticamente mediante el uso de la entrada de otro sistema (por ejemplo, sincronización de datos de escuela), compruebe que los datos de entrada cumplen con la directiva de nomenclatura que ha configurado; Si no, equipo se producirá un error en la creación.

## <a name="can-i-see-who-created-a-team"></a>¿Puedo ver quién creó un equipo?

Para saber quién creó un equipo específico, consulte [el registro de auditoría para eventos en los equipos de Microsoft la búsqueda](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>¿Puedo controlar quién puede crear equipos?

En general, no le recomendamos impidiendo que cualquier persona de la creación de los equipos. Si todos los usuarios pueden crear equipos, los equipos es más probable adopción generalizada. Profesores, profesores o alumnos pueden usar los equipos para crear grupos de estudio o grupos de interés especial. Esto le ayudará a los equipos se acepten dentro y fuera del aula.

En nuestra experiencia, la capacitación del usuario se asegura uso responsable de los equipos. Tan pronto como los usuarios comprendan que los equipos de creación no es anónimo, puedan comprender las consecuencias de su creación sin tener cuidado y tienden a evitan el uso incorrecto de la herramienta.

Si está seguro de que desea controlar quién puede crear equipos, vea [administrar quién puede crear grupos de Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>¿Cómo crea automáticamente un equipo para cada curso al principio de cada semestre o trimestre?

Al principio de cada semestre o trimestre, necesitará un número de equipos de nuevo. Podría ser útil para tomar un enfoque automatizado para crear automáticamente estos equipos, rellenará con los usuarios derecho y establecer los permisos adecuados:

-   Sincronización de datos de escuela puede crear grupos de Office 365 para Exchange Online y SharePoint Online, los equipos de clase para blocs de notas de Microsoft Teams y clase de OneNote, grupos de escuela para Intune para educación y rostering y único integración sign-on (SSO) para muchos otros aplicaciones de otros fabricantes. Encontrará más información en [Información general de la sincronización de datos School](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).
-   Con PowerShell, puede crear equipos y canales y establecer la configuración automáticamente. Para obtener más información, vea [Microsoft PowerShell de los equipos](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
-   Puede usar la API de Microsoft Graph (actualmente en beta) para crear, configurar, clonar y archivar los equipos. Para obtener más información, vea [usar la API de Microsoft Graph para que funcione con los equipos de Microsoft](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) .

> [!TIP]
> Sincronización de datos de School crea un grupo de Office 365 para cada clase sincronizado y [permite la pertenencia al grupo oculta](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) para que únicamente los profesores y los alumnos dentro de la clase pueden ver a los miembros de la clase. Si usa un proceso diferente para crear grupos de clase, usa el parámetro HiddenGroupMembershipEnabled del cmdlet New-UnifiedGroup para cumplir los mismos requisitos de privacidad.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>¿Cómo se trabaja con los equipos cuando finaliza el semestre o trimestre?

Se recomienda que primero piense cómo desea controlar los datos de los equipos cuando un semestre escuela o trimestre sea a través de: si desea eliminarlo o tenerla disponible para los alumnos incluso después de que hayan finalizado el curso. Desea mantener el calendario escolar en cuenta para que las directivas que establezca no entre en conflicto con los días festivos. Puede usar las siguientes herramientas para implementar su estrategia de:

-   **La directiva de retención:** Se usa para eliminar todos los datos anteriores a una edad que especificar para asegurarse de que los datos antiguos se eliminan de chats (para algunos o todos los usuarios) y canales. También puede configurar los equipos para conservar el contenido por lo que no se puede eliminar. Para obtener más información, vea [directivas de retención para los equipos de Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Directiva de expiración:** Configurar los equipos para que caduquen después de un determinado número de días. Treinta días antes de la expiración, reciben una notificación a todos los propietarios de un equipo que tiene que renovar su equipo, en caso contrario, se eliminará (aunque un administrador puede recuperar equipos eliminados para otros 30 días). Esta configuración es muy útil para asegurarse de que los equipos no usados son sunsetted. Encontrará más información en la [Directiva de expiración de grupo de Office 365](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Equipo de archivo:** Esta opción coloca los equipos en modo de sólo lectura. Aún pueden examinar y buscar, pero nadie puede agregar cualquier publicaciones nuevas. [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describe cómo los propietarios de equipo pueden archivar un equipo; Los propietarios de equipo también pueden utilizar la [API de gráfico (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para archivar o restaurar un equipo.
 
> [!IMPORTANT]
> Uso de la directiva de caducidad de grupos de Office 365 requiere licencias de Azure Active Directory Premium P1 para cada usuario único que es un miembro de uno o varios grupos de Office 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>¿Hay plantillas de equipo para Mis los profesores a usar al crear un equipo?

Sí. Los usuarios pueden seleccionar **Crear equipo desde la plantilla existente** al crear un nuevo equipo, y los propietarios de los equipos también pueden usar la [API de gráfico (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para crear un nuevo equipo de las plantillas disponibles.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>¿Qué tareas puedo automatizar a través de PowerShell o gráfico?

La [API de Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) puede hacer lo siguiente:

-   Crear un equipo.
-   Agregar miembros y propietarios.
-   Agregar canales.
-   Agregar aplicaciones.
-   Acceso directo de esos pasos clonando una existente del equipo y obtener sus fichas demasiado.
-   Proporcione al usuario un vínculo para el equipo que acaba de crear.
-   Quitar miembros, los propietarios, canales y aplicaciones cuando ya no necesite.
-   Archivar el equipo cuando ya no está activo. 
-   Eliminar el equipo.
-   Crear un subproceso de canal

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) puede hacer lo siguiente:

-   Crear un equipo.
-   Agregar miembros y propietarios.
-   Agregar canales.
-   Quitar miembros, los propietarios y los canales cuando ya no necesite.
-   Eliminar el equipo.

> [!TIP]
> Los cmdlets de PowerShell y API de gráfico constantemente va a agregar funcionalidad. Asegúrese de comprobar los artículos de [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) y [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) a menudo para mejoras de la característica.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>¿Puedo controlar qué características de los equipos Mis profesores y los alumnos tienen acceso a?

Sí. Puede utilizar directivas para controlar la mensajería específico, reunión, llamada y live funciones de eventos de a que los usuarios tienen acceso. Puede usar la configuración de todo el inquilino para aplicar la misma configuración a todos o aplicar directivas de nivel de usuario, si es necesario. 

Para obtener más información acerca de las directivas de los equipos, vea [las características de administración de equipos de Microsoft en su organización de Office 365](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>¿Puedo controlar qué partes externas Mis profesores y estudiantes colaboran con?

Puede usar el acceso de invitado para invitar a los usuarios de fuera de su inquilino, que puede ser útil para la colaboración en la investigación o conferencias de invitado:

-   Use la lista blanca de dominio para permitir o bloquear a los invitados en función de su dominio.
-   Activar el acceso de invitado encendido y apagado para Office 365 grupos y equipos, concreto controlar lo que los equipos pueden (y no se pueden) invitar a los invitados.
-   Usar el registro de auditoría para ver qué alertas se envían a los usuarios invitados.

Para obtener más información, vea [acceso como invitado en grupos de Office 365](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>¿Qué información puedo revisar acerca de los equipos existentes?

Puede comprobar los registros de auditoría para ver:

-   Quién Invitado como invitado a qué equipo.
-   Quién creó qué equipo.

Para obtener más información, vea [el registro de auditoría para eventos en los equipos de Microsoft Search](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Los equipos evoluciona tan rápidamente. ¿Cómo puedo Manténgase al día?

Recomendamos los siguientes recursos para obtener las actualizaciones más recientes en los equipos:

-   [Novedades en Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)

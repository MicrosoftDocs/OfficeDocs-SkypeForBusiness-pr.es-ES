---
title: Preguntas frecuentes de la administración de Microsoft Education para administradores
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Respuestas a las preguntas más frecuentes de los administradores de grupos de Microsoft Education que usan Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fe9c0b19e5ba586ac8bfe430295de459c3d836d2
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790185"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Preguntas frecuentes de la administración de Microsoft Education para administradores

> [!Tip]
> Vea la siguiente sesión para obtener más información sobre la administración en Microsoft Teams: [Gobierno, administración y ciclo de vida en Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Cómo controlar la creación de equipos? Me preocupa que los estudiantes creen equipos inadecuados.

Para evitar nombres inadecuados o engañosos, o simplemente para proporcionar más estructura para el nombre de los equipos, puede usar la directiva de nomenclatura de Grupos de Microsoft 365 (actualmente en versión preliminar):

-   **Directiva de nomenclatura de prefijos y sufijos** Puede usar prefijos o sufijos para definir la convención de nomenclatura de los equipos (grupos), por ejemplo, **GRP_US_My Group_Engineering**. Los prefijos y sufijos pueden ser cadenas fijas o atributos de usuario (como **[Departamento]**) que se agregan al nombre en función del usuario que está creando el equipo.
-   **Palabras bloqueadas personalizadas** Puede cargar un conjunto de palabras que los usuarios de una organización específica no pueden usar en los nombres de los equipos que crean. Por ejemplo, puede bloquear el uso de los términos **CEO**, **Nóminas** y **RR. HH** . en los nombres de equipo de los grupos a los que no se aplican.
-   **Clasificación** Puede crear clasificaciones que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365. 

> [!IMPORTANT]
> El uso de la directiva de nomenclatura de Grupos de Microsoft 365 requiere licencias de Azure Active Directory Premium P1 o licencias de Azure AD Basic EDU para cada usuario único que sea miembro de uno o más grupos de Microsoft 365.

Para obtener instrucciones detalladas, consulte [Directiva de nomenclatura de grupos de Office](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Si los equipos se crean automáticamente mediante la entrada de otro sistema (por ejemplo, School Data Sync), compruebe que los datos de entrada cumplan con la directiva de nomenclatura que ha configurado; si no es así, se producirá un error en la creación de equipos.

## <a name="can-i-see-who-created-a-team"></a>¿Puedo ver quién creó un equipo?

Para averiguar quién creó un equipo específico, consulte [Buscar eventos en Microsoft Teams en el registro de auditoría](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>¿Puedo controlar quién puede crear equipos?

En general, le recomendamos que no impida que nadie cree equipos. Si todos los usuarios pueden crear equipos, es más probable que Teams se adopte ampliamente. Los profesores, profesores o estudiantes pueden usar Teams para crear grupos de estudio o grupos de interés especial. Esto ayudará a que Teams se acepte dentro y fuera de la clase.

En nuestra experiencia, el aprendizaje del usuario ayuda a garantizar el uso responsable de Teams. Tan pronto como los usuarios comprendan que la creación de equipos no es anónima, entienden las implicaciones de crearlos de forma descuidada y tienden a dejar de usar incorrectamente la herramienta.

Si está seguro de que quiere controlar quién puede crear equipos, consulte [Administrar quién puede crear Grupos de Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Cómo crear automáticamente un equipo para cada curso al principio del semestre o trimestre?

Al comienzo de cada semestre o trimestre, necesitará varios equipos nuevos. Puede que tenga sentido adoptar un enfoque automatizado para crear estos equipos automáticamente, rellenarlos con los usuarios adecuados y establecer los permisos adecuados:

-   School Data Sync puede crear Grupos de Microsoft 365 para Exchange Online y SharePoint Online, equipos de clase para Microsoft Teams y blocs de notas de clase de OneNote, grupos educativos para Intune para Educación y listas e integración de inicio de sesión único (SSO) para muchas otras aplicaciones de terceros. Obtenga más información en [Información general de School Data Sync](/schooldatasync/overview-of-school-data-sync).
-   Con PowerShell, puede crear equipos y canales y configurar las opciones automáticamente. Consulte [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.
-   Puede usar microsoft Graph API (actualmente en versión beta) para crear, configurar, clonar y archivar equipos. Consulte [Usar microsoft Graph API para trabajar con Microsoft Teams](/graph/api/resources/teams-api-overview) para obtener más información.

> [!TIP]
> School Data Sync crea un grupo de Microsoft 365 para cada clase sincronizada y [habilita la pertenencia a grupos ocultas](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) para que solo los profesores y alumnos de la clase puedan ver a los miembros de esa clase. Si usa un proceso diferente para crear grupos de clases, use el parámetro HiddenGroupMembershipEnabled del cmdlet de New-UnifiedGroup para cumplir los mismos requisitos de privacidad.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Cómo tratar con los equipos cuando finalice el semestre o trimestre?

Le recomendamos que primero piense en cómo desea administrar los datos de Teams cuando finalice el semestre o trimestre escolar: si desea eliminarlos o mantenerlos disponibles para los alumnos incluso después de que hayan completado el curso. Querrá tener en cuenta el calendario escolar para que las directivas que establezca no entren en conflicto con los días festivos. Puede usar las siguientes herramientas para implementar la estrategia:

-   **Directiva de retención:** Use esta opción para eliminar todos los datos anteriores a una edad especificada para asegurarse de que los datos antiguos se quitan de los chats (para todos o algunos usuarios) y los canales. También puede configurar Teams para que conserve el contenido para que no se pueda eliminar. Para obtener más información, consulte [Directivas de retención para Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Directiva de expiración:** Configure equipos para que expiren después de un número determinado de días. Treinta días antes de la expiración, se notifica a todos los propietarios de un equipo que su equipo debe renovarse, de lo contrario se eliminará (aunque un administrador puede recuperar equipos eliminados durante 30 días adicionales). Esta configuración es muy útil para asegurarse de que se pone el sol en los equipos sin usar. Obtenga más información en Directiva de [expiración de Microsoft 365 Group](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Equipo de archivo:** Esta configuración pone a los equipos en modo de solo lectura. Aún se pueden examinar y buscar, pero nadie puede agregar nuevas publicaciones. [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describe cómo los propietarios del equipo pueden archivar un equipo; Los propietarios de equipos también pueden usar la [Graph API (beta)](/graph/api/resources/teams-api-overview) para archivar o restaurar un equipo.
 
> [!IMPORTANT]
> El uso de la directiva de expiración de Grupos de Microsoft 365 requiere licencias de Azure Active Directory Premium P1 para cada usuario único que sea miembro de uno o más grupos de Microsoft 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>¿Hay plantillas de equipo para que los profesores las usen al crear un equipo?

Sí. Los usuarios pueden seleccionar **Crear equipo a partir de una plantilla existente** al crear un equipo nuevo, y los propietarios de Teams también pueden usar la [Graph API (beta)](/graph/api/resources/teams-api-overview) para crear un nuevo equipo a partir de las plantillas disponibles.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>¿Qué tareas puedo automatizar a través de PowerShell o Graph?

[Microsoft Graph API (beta)](/graph/api/resources/teams-api-overview) puede hacer lo siguiente:

-   Crear un equipo.
-   Agregue miembros y propietarios.
-   Agregar canales.
-   Agregar aplicaciones.
-   Acceso directo a esos pasos mediante la clonación de un equipo existente y obtener sus pestañas también.
-   Proporcione al usuario un vínculo al equipo que acaba de crear.
-   Quite miembros, propietarios, canales y aplicaciones cuando ya no los necesite.
-   Archive el equipo cuando ya no esté activo. 
-   Eliminar el equipo.
-   Crear una conversación de canal

[PowerShell](/powershell/module/teams/?view=teams-ps) puede hacer lo siguiente:

-   Crear un equipo.
-   Agregue miembros y propietarios.
-   Agregar canales.
-   Quite miembros, propietarios y canales cuando ya no los necesite.
-   Eliminar el equipo.

> [!TIP]
> Los cmdlets de Graph API y PowerShell están agregando funcionalidad constantemente. Asegúrate de consultar a menudo los artículos [de Microsoft Graph API (beta)](/graph/api/resources/teams-api-overview) y [PowerShell](/powershell/module/teams/?view=teams-ps) para obtener mejoras de características.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>¿Puedo controlar las características de Teams a las que mi facultad y los estudiantes tienen acceso?

Sí. Puede usar directivas para controlar las características específicas de mensajería, reuniones, llamadas y eventos en directo a las que los usuarios tienen acceso. Puede usar la configuración de todo el espacio empresarial para aplicar la misma configuración a todos o aplicar directivas de nivel de usuario si es necesario. 

Para obtener más información sobre las directivas de Teams, consulte [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>¿Puedo controlar con qué partes externas colaboran mi facultad y los estudiantes?

Puede usar el acceso de invitado para invitar a usuarios de fuera de su inquilino, lo que puede resultar útil para la colaboración de investigación o conferencias de invitado:

-   Use una lista de permitidos de dominio para permitir o bloquear invitados en función de su dominio.
-   Active y desactive el acceso de invitado para determinados Grupos de Microsoft 365 y equipos, para controlar qué equipos pueden o no invitar a invitados.
-   Use el registro de auditoría para ver qué alertas se enviaron a los invitados invitados.

Para obtener más información, vea [Acceso de invitado en Grupos de Microsoft 365](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>¿Qué información puedo revisar sobre los equipos existentes?

Puede comprobar los registros de auditoría para ver:

-   A quién se le invitó como invitado a cada equipo.
-   Quién creó cada equipo.

Para obtener más información, consulte [Buscar eventos en Microsoft Teams en el registro de auditoría](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams evoluciona tan rápidamente. ¿Cómo puedo mantenerme al día?

Le recomendamos los siguientes recursos para obtener las últimas actualizaciones en Teams:

-   [Novedades de Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
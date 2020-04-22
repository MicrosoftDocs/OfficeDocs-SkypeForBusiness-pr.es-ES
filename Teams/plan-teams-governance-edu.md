---
title: Preguntas frecuentes de la administración de Microsoft Education para administradores
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Respuestas a las preguntas más frecuentes de los administradores de Microsoft Education Groups que usan Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 79b6e33c6434a1242b7d30322aff77b62f1b42fd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780219"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Preguntas frecuentes de la administración de Microsoft Education para administradores

> [!Tip]
> Vea la siguiente sesión para obtener más información sobre la administración en Microsoft Teams: [gobernanza, administración y ciclo de vida en Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>¿Cómo puedo controlar la creación de un equipo? Me preocupa que los estudiantes vayan a crear equipos incorrectos.

Para evitar nombres inapropiados o incorrectos, o simplemente para proporcionar más estructura para el nombre de Teams, puede usar la política de nomenclatura de grupos de 365 de Microsoft (actualmente en versión preliminar):

-   **Directiva de nomenclatura de prefijos** Puede usar prefijos o sufijos para definir la Convención de nomenclatura de Teams (grupos), por ejemplo, **GRP_US_My Group_Engineering**. Los prefijos y los sufijos pueden ser cadenas fijas o atributos de usuario (como **[Departamento]**) que se agregan al nombre basándose en el usuario que está creando el equipo.
-   **Palabras bloqueadas personalizadas** Puede cargar un conjunto de palabras que los usuarios de una organización específica tienen bloqueados para usar en los nombres de los equipos que creen. Por ejemplo, puede bloquear los términos **CEO**, **nómina**y **HR** para que no se usen en los nombres de equipo de los grupos a los que no se aplican.
-   **Clasificación** Puede crear clasificaciones que los usuarios de su organización puedan establecer al crear un grupo de Office 365. 

> [!IMPORTANT]
> El uso de la Directiva de nomenclatura de grupos de 365 de Microsoft requiere licencias de Azure Active Directory Premium P1 o licencias de Azure AD Basic EDU para cada usuario único que sea miembro de uno o más grupos de Microsoft 365.

Para obtener instrucciones detalladas, consulte [política de nomenclatura de grupos de Office](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Si se crean equipos automáticamente mediante la entrada de otro sistema (por ejemplo, School Data Sync), compruebe que los datos de entrada cumplan con la política de nomenclatura que ha configurado; de lo contrario, se producirá un error en la creación del equipo.

## <a name="can-i-see-who-created-a-team"></a>¿Puedo ver quién ha creado un equipo?

Para averiguar quién creó un equipo específico, consulte [buscar eventos en Microsoft Teams en el registro de auditoría](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>¿Puedo controlar quién puede crear Teams?

En general, le recomendamos evitar que alguien cree equipos. Si todos los usuarios pueden crear equipos, es más probable que Teams se haya adoptado ampliamente. Los profesores, profesores o alumnos pueden usar Teams para crear grupos de estudio o grupos de interés especial. Esto ayudará a que los equipos sean aceptados dentro y fuera del aula.

En nuestra experiencia, la educación de los usuarios ayuda a garantizar el uso de equipos responsables. Tan pronto como los usuarios entienden que la creación de equipos no es anónima, entienden las implicaciones de crearlos sin precuidado y tiende a fingir la baja de la herramienta.

Si está seguro de que desea controlar quién puede crear equipos, consulte [administrar quién puede crear grupos de Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>¿Cómo creo automáticamente un equipo para cada curso al principio del semestre o el trimestre?

Al comienzo de cada semestre o trimestre, necesitará un número de nuevos equipos. Puede tener sentido tomar un enfoque automatizado para crear estos equipos automáticamente, rellenarlos con los usuarios adecuados y establecer los permisos adecuados:

-   School Data Sync puede crear grupos de Microsoft 365 para Exchange Online y SharePoint Online, clase Teams para Microsoft Teams y blocs de notas de clase de OneNote, grupos escolares para Intune para educación, y la integración de inicio de sesión único (SSO) para muchas otras aplicaciones de terceros. Para obtener más información, vea [información general de School Data Sync](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).
-   Con PowerShell, puede crear equipos y canales, y configurar las opciones automáticamente. Para obtener más información, vea [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
-   Puede usar la API de Microsoft Graph (actualmente está en versión beta) para crear, configurar, clonar y archivar equipos. Para obtener más información, vea [usar la API de Microsoft Graph para trabajar con Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) .

> [!TIP]
> School Data Sync crea un grupo de Office 365 para cada clase sincronizada y [habilita la pertenencia a grupos ocultas](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) para que solo los profesores y alumnos de la clase puedan ver los miembros de la clase. Si usa un proceso diferente para crear grupos de clases, use el parámetro HiddenGroupMembershipEnabled del cmdlet New-Unifiedgrouphttps para cumplir los mismos requisitos de privacidad.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>¿Cómo puedo enfrentarse con Teams cuando el semestre o el trimestre termina?

Le recomendamos que piense primero cómo desea controlar los datos de los equipos cuando el semestre de la escuela o el trimestre está por encima: Si desea eliminarlos o mantenerlos disponibles para los alumnos incluso después de haber completado el curso. Querrá tener en cuenta el calendario de la escuela para que las directivas que establezca no entren en conflicto con los días no laborables. Puede usar las siguientes herramientas para implementar su estrategia:

-   **Directiva de retención:** Use esta para eliminar todos los datos anteriores a una antigüedad que especifique para asegurarse de que los datos antiguos se quitan de los chats (para todos o algunos usuarios) y canales. También puede configurar Teams para que retenga el contenido, de modo que no se pueda eliminar. Para obtener más información, consulte [directivas de retención para Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Directiva de expiración:** Configurar Teams para que venza después de un número determinado de días. Treinta días antes de la expiración, se notifica a todos los propietarios de un equipo que es necesario renovar el equipo; de lo contrario, se eliminará (aunque un administrador puede recuperar los equipos eliminados durante 30 días adicionales). Esta configuración es muy útil para asegurarse de que los equipos que no se usan estén sunsetted. Para obtener más información, vea la [Directiva de expiración del grupo de Office 365](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Equipo de archivo:** Esta opción pone equipos en el modo de solo lectura. Aún puede examinarlos y buscarlos, pero nadie puede agregar mensajes nuevos. [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describe cómo los propietarios del equipo pueden archivar un equipo; Los propietarios del equipo también pueden usar la [API de Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para archivar o restaurar un equipo.
 
> [!IMPORTANT]
> El uso de la Directiva de expiración de grupos de Microsoft 365 requiere licencias de Azure Active Directory Premium P1 para cada usuario único que sea miembro de uno o más grupos de Microsoft 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>¿Hay plantillas de equipo para que los miembros de mi docente usen al crear un equipo?

Sí. Los usuarios pueden seleccionar **crear equipo a partir de una plantilla existente** al crear un equipo nuevo y los propietarios de los equipos también pueden usar la [API de Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para crear un equipo nuevo a partir de las plantillas disponibles.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>¿Qué tareas puedo automatizar mediante PowerShell o Graph?

La [API de Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) puede hacer lo siguiente:

-   Crear un equipo.
-   Agregue miembros y propietarios.
-   Agregar canales.
-   Agregar aplicaciones.
-   Para obtener acceso directo a esos pasos, clonar un equipo existente y obtener también sus pestañas.
-   Asigne al usuario un vínculo al equipo que acaba de crear.
-   Quite miembros, propietarios, canales y aplicaciones cuando ya no los necesite.
-   Archivar el equipo cuando ya no esté activo. 
-   Elimine el equipo.
-   Crear un hilo de canales

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) puede hacer lo siguiente:

-   Crear un equipo.
-   Agregue miembros y propietarios.
-   Agregar canales.
-   Quite miembros, propietarios y canales cuando ya no los necesite.
-   Elimine el equipo.

> [!TIP]
> La API Graph y los cmdlets de PowerShell están constantemente agregando funcionalidades. Asegúrese de comprobar la [API de Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) y los artículos de [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) con frecuencia para obtener mejoras de las características.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>¿Puedo controlar a qué equipos se incluye el acceso a mi profesora y a los alumnos?

Sí. Puede usar directivas para controlar mensajes específicos, reuniones, llamadas y características de eventos en vivo a los que tienen acceso los usuarios. Puede usar la configuración de todos los inquilinos para aplicar la misma configuración a todos o aplicar directivas de nivel de usuario si es necesario. 

Para obtener más información sobre las directivas de Teams, vea [administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>¿Puedo controlar con qué partes externas mi facultad y sus alumnos pueden colaborar?

Puede usar el acceso de invitado para invitar a usuarios externos a su inquilino, que pueden ser útiles para la colaboración de investigación o las conferencias de invitados:

-   Use listas blancas de dominio para permitir o bloquear a los invitados en función de su dominio.
-   Active y desactive el acceso de invitados en determinados grupos y equipos de Microsoft 365 para controlar qué equipos pueden invitar a invitados o no.
-   Use el registro de auditoría para ver qué alertas se enviaron a los invitados.

Para obtener más información, vea [acceso de invitado en grupos de 365 de Microsoft](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>¿Qué información puedo revisar acerca de los equipos existentes?

Puede consultar los registros de auditoría para ver:

-   A quién fue invitado como invitado del equipo.
-   Quién creó el equipo.

Para obtener más información, vea [buscar eventos en Microsoft Teams en el registro de auditoría](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams evoluciona tan rápidamente. ¿Cómo puedo mantenerme al día?

Recomendamos los siguientes recursos para obtener las actualizaciones más recientes de Teams:

-   [Novedades de Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)

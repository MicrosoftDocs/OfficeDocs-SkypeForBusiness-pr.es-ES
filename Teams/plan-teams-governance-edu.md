---
title: Preguntas frecuentes de la administración de Microsoft Education para administradores
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Respuestas a las preguntas más frecuentes de administradores de grupos de Microsoft Education que usan Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f8f8593d598901c71590cc395eb45b0bac7cf4f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812910"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Preguntas frecuentes de la administración de Microsoft Education para administradores

> [!Tip]
> Vea la siguiente sesión para obtener más información sobre la administración en Microsoft Teams: [Gobierno, administración y ciclo de vida en Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>¿Cómo controlo la creación de equipos? Me preocupa que los alumnos creen equipos inadecuados.

Para evitar nombres inapropiados o engañosos, o simplemente para proporcionar una mayor estructura de cómo se denomina a los equipos, puede usar la directiva de nomenclatura de Microsoft 365 Groups (actualmente en versión preliminar):

-   **Directiva de nomenclatura de prefijos y sufijos** Puede usar prefijos o sufijos para definir la convención de nomenclatura de los equipos (grupos), por ejemplo, **GRP_US_My Group_Engineering.** Los prefijos y sufijos pueden ser cadenas fijas o atributos de usuario (como **[Department])** que se agregan al nombre en función del usuario que está creando el equipo.
-   **Palabras bloqueadas personalizadas** Puede cargar un conjunto de palabras que los usuarios de una organización específica no pueden usar en los nombres de los equipos que creen. Por ejemplo, puede bloquear los términos  **director** **general,** nóminas y RR. UU. para que no se usen en los nombres de equipo para los grupos a los que no se apliquen.
-   **Clasificación** Puede crear clasificaciones que los usuarios de su organización pueden establecer al crear un grupo de Microsoft 365. 

> [!IMPORTANT]
> Para usar la directiva de nomenclatura de Microsoft 365 Groups, es necesario disponer de licencias P1 de Azure Active Directory Premium o licencias EDU de Azure AD Basic para cada usuario único que sea miembro de uno o varios grupos de Microsoft 365.

Para obtener instrucciones detalladas, consulte [la directiva de nomenclatura de grupos de Office.](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

> [!Note]
> Si los equipos se crean automáticamente usando la entrada de otro sistema (por ejemplo, School Data Sync), compruebe que los datos de entrada cumplan con la directiva de nomenclatura que ha configurado; si no es así, se producirá un error en la creación de equipos.

## <a name="can-i-see-who-created-a-team"></a>¿Puedo ver quién ha creado un equipo?

Para averiguar quién ha creado un equipo específico, consulte Buscar eventos en el registro de auditoría [de Microsoft Teams.](audit-log-events.md)

## <a name="can-i-control-who-can-create-teams"></a>¿Puedo controlar quién puede crear equipos?

En general, le recomendamos que no evite que nadie cree equipos. Si todos los usuarios pueden crear equipos, es más probable que Teams se adopte ampliamente. Los profesores, los profesores o los alumnos pueden usar Teams para crear grupos de estudio o grupos de interés especial. Esto ayudará a que Se acepte Teams dentro y fuera de la clase.

En nuestra experiencia, el aprendizaje de los usuarios ayuda a garantizar un uso responsable de Teams. Tan pronto como los usuarios entienden que la creación de equipos no es anónima, entienden las implicaciones de crearlos de forma descuada y suelen evitar usar la herramienta.

Si está seguro de que quiere controlar quién puede crear equipos, consulte Administrar quién [puede crear grupos de Microsoft 365.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>¿Cómo creo automáticamente un equipo para cada curso al principio del semestre o trimestre?

Al principio de cada semestre o trimestre, necesitará varios equipos nuevos. Sería lógico usar un enfoque automatizado para crear estos equipos automáticamente, rellenarlos con los usuarios adecuados y establecer los permisos adecuados:

-   School Data Sync puede crear grupos de Microsoft 365 para Exchange Online y SharePoint Online, equipos de clase para Microsoft Teams y blocs de notas de clase de OneNote, grupos escolares para Intune for Education y la integración de listas e inicio de sesión único (SSO) para muchas otras aplicaciones de terceros. Obtenga más información en [Información general sobre School Data Sync.](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)
-   Con PowerShell, puede crear equipos y canales y configurar las opciones automáticamente. Vea [PowerShell de Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
-   Puede usar la API de Microsoft Graph (actualmente en versión beta) para crear, configurar, clonar y archivar equipos. Vea [Usar la API de Microsoft Graph para trabajar con Microsoft Teams para](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) obtener más información.

> [!TIP]
> School Data Sync crea un grupo de Microsoft 365 para cada clase sincronizado y habilita la pertenencia a grupos ocultos para que solo los profesores y alumnos de la clase puedan ver los miembros de esa clase. [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) Si usa un proceso diferente para crear grupos de clase, use el parámetro HiddenGroupMembershipEnabled del cmdlet New-UnifiedGroup para cumplir los mismos requisitos de privacidad.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>¿Cómo trabajo con los equipos cuando termina el semestre o trimestre?

Le recomendamos que, cuando se complete el semestre o el trimestre de la escuela, piense primero en cómo tratar los datos de Teams: si quiere eliminarlos o mantenerlos disponibles para los alumnos incluso después de que hayan finalizado el curso. Querrá tener en cuenta el calendario escolar para que las directivas que establezca no entren en conflicto con los días festivos. Puede usar las siguientes herramientas para implementar su estrategia:

-   **Directiva de retención:** Use esta opción para eliminar todos los datos de más de una edad que especifique para asegurarse de que los datos antiguos se quitan de los chats (para todos los usuarios o para algunos) y los canales. También puede configurar Teams para que retenga contenido y no se pueda eliminar. Para obtener más información, vea [Directivas de retención para Microsoft Teams.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)
-   **Directiva de expiración:** Configure los equipos para que expiren después de un número determinado de días. Treinta días antes de la expiración, se notifica a todos los propietarios de un equipo que es necesario renovar su equipo, de otro modo se elimina (aunque un administrador puede recuperar equipos eliminados durante 30 días adicionales). Esta configuración es muy útil para asegurarse de que los equipos sin utilizar se pone en marcha. Más información en Directiva de expiración de grupos [de Microsoft 365.](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **Equipo de archivado:** Esta configuración pone a los equipos en modo de solo lectura. Aún se pueden examinar y buscar, pero nadie puede agregar nuevas publicaciones. [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describe cómo los propietarios de equipos pueden archivar un equipo; Los propietarios de equipos también [pueden usar la API de Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para archivar o restaurar un equipo.
 
> [!IMPORTANT]
> El uso de la directiva de expiración de grupos de Microsoft 365 requiere licencias P1 de Azure Active Directory Premium para cada usuario único que sea miembro de uno o varios grupos de Microsoft 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>¿Hay plantillas de equipo que los miembros de mi facultad pueden usar al crear un equipo?

Sí. Los usuarios pueden seleccionar **Crear** equipo a partir de una plantilla existente al crear un equipo, mientras que los propietarios de equipos también pueden usar la API de [Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) para crear un equipo a partir de las plantillas disponibles.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>¿Qué tareas puedo automatizar a través de PowerShell o Graph?

La [API de Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) puede hacer lo siguiente:

-   Cree un equipo.
-   Agregar miembros y propietarios.
-   Agregar canales.
-   Agregar aplicaciones.
-   Haga acceso directo a esos pasos mediante la clonación de un equipo existente y obtenga sus pestañas también.
-   Dé un vínculo al usuario al equipo que acaba de crear.
-   Quite miembros, propietarios, canales y aplicaciones cuando ya no los necesite.
-   Archive el equipo cuando ya no esté activo. 
-   Elimine el equipo.
-   Crear una conversación de canal

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) puede hacer lo siguiente:

-   Cree un equipo.
-   Agregar miembros y propietarios.
-   Agregar canales.
-   Quite miembros, propietarios y canales cuando ya no los necesite.
-   Elimine el equipo.

> [!TIP]
> Los cmdlets de La API de Graph y PowerShell agregan continuamente funciones. Asegúrese de comprobar los artículos de [API de Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) y [PowerShell a](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) menudo para ver si hay mejoras en las características.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>¿Puedo controlar las características de Teams a las que tienen acceso mi profesor y los estudiantes?

Sí. Puede usar directivas para controlar características específicas de mensajería, reuniones, llamadas y eventos en directo a los que los usuarios tienen acceso. Puede usar la configuración de todos los inquilinos para aplicar la misma configuración a todos o aplicar directivas a nivel de usuario si es necesario. 

Para obtener más información sobre las directivas de Teams, consulte [Administrar la configuración de Microsoft Teams para su organización.](enable-features-office-365.md)
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>¿Puedo controlar con qué partes externas colaboran mi facultad y los estudiantes?

Puede usar el acceso de invitado para invitar a usuarios externos a su inquilino, lo que puede ser útil para la colaboración en investigación o para conferencias de invitado:

-   Use la lista de dominios para permitir o bloquear invitados en función de su dominio.
-   Active y desactive el acceso de invitados para grupos y equipos particulares de Microsoft 365 para controlar qué equipos pueden (o no) invitar a invitados.
-   Use el registro de auditoría para ver qué alertas se han enviado a los invitados invitados.

Para obtener más información, vea [Acceso de invitado en Grupos de Microsoft 365.](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)

## <a name="what-information-can-i-review-about-existing-teams"></a>¿Qué información puedo revisar sobre los equipos existentes?

Puede comprobar los registros de auditoría para ver:

-   ¿A quién se invitó como invitado a cada equipo?
-   Quién ha creado cada equipo.

Para obtener más información, consulte Buscar eventos en el [registro de auditoría de Microsoft Teams.](audit-log-events.md)

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams evoluciona tan rápidamente. ¿Cómo puedo mantenerme al día?

Le recomendamos los siguientes recursos para obtener las actualizaciones más recientes en Teams:

-   [Novedades de Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)

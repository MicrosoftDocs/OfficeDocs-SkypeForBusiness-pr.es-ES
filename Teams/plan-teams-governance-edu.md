---
title: Preguntas frecuentes de la administración de Microsoft Education para administradores
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Respuestas a preguntas más frecuentes de administradores de grupos de Microsoft Education que usan Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ada92509adc0f066bf957ddaa8f5de8dd0c47653
ms.sourcegitcommit: 8906fc384cd13255972df53d2a07d12589154d42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "52085852"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Preguntas frecuentes de la administración de Microsoft Education para administradores

> [!Tip]
> Vea la siguiente sesión para obtener más información sobre la administración en Microsoft Teams: [Gobierno, administración y](https://aka.ms/teams-governance) ciclo de vida en Microsoft Teams

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>¿Cómo controlo la creación de equipos? Me preocupa que los alumnos creen equipos inadecuados.

Para evitar nombres inapropiados o engañosos, o simplemente para proporcionar más estructura para cómo se denominan los equipos, puede usar la directiva de nomenclatura Microsoft 365 Grupos (actualmente en versión preliminar):

-   **Directiva de nomenclatura prefijo-sufijo** Puede usar prefijos o sufijos para definir la convención de nomenclatura de los equipos (grupos), por ejemplo, **GRP_US_My Group_Engineering**. Los prefijos y sufijos pueden ser cadenas fijas o atributos de usuario (como **[Departamento]**) que se agregan al nombre en función del usuario que está creando el equipo.
-   **Palabras bloqueadas personalizadas** Puede cargar un conjunto de palabras que los usuarios de una organización específica no pueden usar en los nombres de los equipos que creen. Por ejemplo, puede bloquear los términos  **Director** **general,** Nómina y RRHH para que no se usen en los nombres de equipo de los grupos a los que no se aplican.
-   **Clasificación** Puede crear clasificaciones que los usuarios de su organización pueden establecer al crear un Microsoft 365 grupo. 

> [!IMPORTANT]
> El uso de la directiva de nomenclatura Microsoft 365 grupos de Azure Active Directory Premium requiere licencias P1 o licencias educaciones básicas de Azure AD para cada usuario único que sea miembro de uno o más Microsoft 365 grupos.

Para obtener instrucciones detalladas, [vea Office directiva de nomenclatura de grupos.](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

> [!Note]
> Si los equipos se crean automáticamente mediante la entrada de otro sistema (por ejemplo, School Data Sync), compruebe que los datos de entrada cumplen con la directiva de nomenclatura que ha configurado; si no es así, se producirá un error en la creación de equipos.

## <a name="can-i-see-who-created-a-team"></a>¿Puedo ver quién creó un equipo?

Para averiguar quién creó un equipo específico, vea Buscar eventos en el registro de auditoría en [Microsoft Teams](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>¿Puedo controlar quién puede crear equipos?

En general, se recomienda evitar que nadie cree equipos. Si todos los usuarios pueden crear equipos, Teams es más probable que se adopten ampliamente. Los profesores, profesores o alumnos pueden usar Teams crear grupos de estudio o grupos de interés especial. Esto le ayudará a Teams dentro y fuera del aula.

En nuestra experiencia, la educación de los usuarios ayuda a garantizar un uso Teams responsable. Tan pronto como los usuarios comprendan que la creación de equipos no es anónima, comprenden las implicaciones de crearlos descuidos y tienden a evitar usar la herramienta de forma errónea.

Si está seguro de que desea controlar quién puede crear equipos, vea Administrar quién puede crear Microsoft 365 [grupos.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>¿Cómo puedo crear automáticamente un equipo para cada curso al principio del semestre o trimestre?

Al principio de cada semestre o trimestre, necesitará varios equipos nuevos. Es posible que tenga sentido tomar un enfoque automatizado para crear estos equipos automáticamente, rellenarlos con los usuarios adecuados y establecer los permisos adecuados:

-   School Data Sync puede crear grupos de Microsoft 365 para Exchange Online y SharePoint Online, equipos de clase para blocs de notas de clase de Microsoft Teams y OneNote, grupos escolares para Intune para educación e integración de listas e inicio de sesión único (SSO) para muchas otras aplicaciones de terceros. Obtenga más información en [Información general sobre School Data Sync](/schooldatasync/overview-of-school-data-sync).
-   Con PowerShell, puede crear equipos y canales y configurar la configuración automáticamente. Vea [Microsoft Teams PowerShell para](/powershell/module/teams/?view=teams-ps) obtener más información.
-   Puede usar la API Graph Microsoft (actualmente en beta) para crear, configurar, clonar y archivar equipos. Vea [Usar la API Graph Microsoft para trabajar con Microsoft Teams](/graph/api/resources/teams-api-overview) para obtener más información.

> [!TIP]
> School Data Sync crea un grupo de Microsoft 365 para cada clase [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) sincronizado y habilita la pertenencia a grupos ocultos para que solo los profesores y alumnos de la clase puedan ver los miembros de esa clase. Si usa un proceso diferente para crear grupos de clase, use el parámetro HiddenGroupMembershipEnabled del cmdlet New-UnifiedGroup para cumplir los mismos requisitos de privacidad.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>¿Cómo puedo tratar con los equipos cuando termina el semestre o trimestre?

Le recomendamos que primero piense en la manera en que desea administrar los datos Teams cuando el semestre o trimestre escolar haya terminado: si desea eliminarlos o mantenerlos disponibles para los alumnos incluso después de que hayan completado el curso. Querrá tener en cuenta el calendario escolar para que las directivas que establezca no entren en conflicto con los días festivos. Puede usar las siguientes herramientas para implementar la estrategia:

-   **Directiva de retención:** Úselo para eliminar todos los datos anteriores a una edad que especifique para asegurarse de que los datos antiguos se quitan de los chats (para todos o algunos usuarios) y los canales. También puede configurar Teams conservar el contenido para que no se pueda eliminar. Para obtener más información, vea [Directivas de retención para Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Directiva de expiración:** Configure los equipos para que expiren después de un número determinado de días. Treinta días antes de la expiración, se notifica a todos los propietarios de un equipo que su equipo debe renovarse, de lo contrario se eliminará (aunque un administrador puede recuperar equipos eliminados durante 30 días adicionales). Esta configuración es muy útil para asegurarse de que los equipos sin usar se extinten. Obtenga más información en [Microsoft 365 directiva de expiración del grupo.](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **Equipo de archivo:** Esta configuración pone a los equipos en modo de solo lectura. Aún se pueden examinar y buscar, pero nadie puede agregar nuevas publicaciones. [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describe cómo los propietarios de los equipos pueden archivar un equipo; Los propietarios de equipos también [pueden usar Graph API (beta) para](/graph/api/resources/teams-api-overview) archivar o restaurar un equipo.
 
> [!IMPORTANT]
> Usar la Microsoft 365 de expiración de grupos Azure Active Directory Premium licencias P1 para cada usuario único que sea miembro de uno o más Microsoft 365 grupos.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>¿Hay plantillas de equipo para los miembros de mis profesores que usar al crear un equipo?

Sí. Los usuarios  pueden seleccionar Crear equipo a partir de una plantilla existente al crear un equipo nuevo y los propietarios de Teams también pueden usar la [API de Graph (beta)](/graph/api/resources/teams-api-overview) para crear un nuevo equipo a partir de las plantillas disponibles.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>¿Qué tareas puedo automatizar a través de PowerShell o Graph?

La [API Graph microsoft (beta)](/graph/api/resources/teams-api-overview) puede hacer lo siguiente:

-   Crear un equipo.
-   Agregar miembros y propietarios.
-   Agregar canales.
-   Agregar aplicaciones.
-   Para obtener acceso directo a esos pasos, clonar un equipo existente y obtener sus pestañas también.
-   Dé al usuario un vínculo al equipo que acaba de crear.
-   Quite miembros, propietarios, canales y aplicaciones cuando ya no los necesite.
-   Archive el equipo cuando ya no esté activo. 
-   Elimine el equipo.
-   Crear una conversación de canal

[PowerShell](/powershell/module/teams/?view=teams-ps) puede hacer lo siguiente:

-   Crear un equipo.
-   Agregar miembros y propietarios.
-   Agregar canales.
-   Quite miembros, propietarios y canales cuando ya no los necesite.
-   Elimine el equipo.

> [!TIP]
> Los Graph API y cmdlets de PowerShell están agregando funcionalidad constantemente. Asegúrese de comprobar los artículos Graph [API de Microsoft (beta)](/graph/api/resources/teams-api-overview) y [PowerShell a](/powershell/module/teams/?view=teams-ps) menudo para obtener mejoras de características.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>¿Puedo controlar a qué Teams tienen acceso mis profesores y alumnos?

Sí. Puede usar directivas para controlar determinadas características de mensajería, reunión, llamadas y eventos en directo a las que tienen acceso los usuarios. Puede usar la configuración de todo el espacio empresarial para aplicar la misma configuración a todos o aplicar directivas de nivel de usuario si es necesario. 

Para obtener más información sobre Teams directivas, vea [Administrar Microsoft Teams configuración de su organización.](enable-features-office-365.md)
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>¿Puedo controlar con qué partes externas colaboran mis profesores y alumnos?

Puede usar el acceso de invitado para invitar a usuarios de fuera de su inquilino, lo que puede ser útil para la colaboración de investigación o conferencias de invitado:

-   Use una lista de permitidos de dominio para permitir o bloquear invitados en función de su dominio.
-   Active y desactive el acceso de invitado para grupos de Microsoft 365 y equipos específicos, para controlar qué equipos pueden (y no pueden) invitar invitados.
-   Use el registro de auditoría para ver qué alertas se enviaron a invitados invitados.

Para obtener más información, vea [Acceso de invitado en Microsoft 365 grupos.](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)

## <a name="what-information-can-i-review-about-existing-teams"></a>¿Qué información puedo revisar sobre los equipos existentes?

Puede comprobar los registros de auditoría para ver:

-   Quién invitado a qué equipo.
-   Quién el equipo.

Para obtener más información, vea [Buscar eventos en](audit-log-events.md)el registro de auditoría en Microsoft Teams .

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams evoluciona tan rápidamente. ¿Cómo puedo mantenerme al día?

Se recomiendan los siguientes recursos para obtener las últimas actualizaciones en Teams:

-   [Novedades de Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
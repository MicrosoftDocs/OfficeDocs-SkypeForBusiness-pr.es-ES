---
title: Plan para la administración en Teams - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: En este artículo, aprenderá a planear la implementación de capacidades de gobierno en Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2180c819491b3067225ada993aec60ec052bc69f
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416910"
---
# <a name="plan-for-governance-in-teams"></a>Planificar el gobierno en Teams

Teams proporciona un conjunto completo de herramientas para implementar cualquier funcionalidad de gobierno que su organización pueda necesitar. Este artículo guía a los profesionales de TI a hacer las preguntas correctas para determinar sus requisitos para el gobierno y cómo cumplirlas. 

> [!Tip] 
> Vea la siguiente sesión para obtener más información sobre el gobierno en Microsoft Teams: [gobierno, administración y ciclo de vida en Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Creación de grupos y equipos, nomenclatura, clasificación y acceso de invitado

Es posible que su organización requiera que implemente controles estrictos sobre cómo se denominan y clasifican los equipos, si se pueden agregar invitados como miembros del equipo y quién puede crear equipos. Puede configurar estas áreas mediante Azure Active Directory (Azure AD) y etiquetas de confidencialidad. 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Puntos de decisión|<ul><li>¿Su organización requiere una convención de nomenclatura específica para los equipos?</li><li>¿Los creadores de equipos necesitan poder asignar clasificaciones específicas de la organización a los equipos?</li><li>¿Necesita restringir la capacidad de agregar invitados a los equipos en cada equipo?</li><li>¿Su organización requiere limitar quién puede crear equipos?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente los requisitos de su organización para la creación de equipos, los nombres, la clasificación y el acceso de invitados.</li><li>Planifique para implementar estos requisitos como parte de la implementación de Teams.</li><li>Comunique y publique las directivas para informar a los usuarios de Teams del comportamiento que pueden esperar.</li></ul>|

> [!TIP]
> Use la tabla siguiente para capturar los requisitos de su organización.

|Funcionalidad |Detalles |Azure AD Premium <br> licencia requerida |Decisión |
|---------|---------|---------|---------|
|Directiva de nomenclatura de equipo | Use palabras bloqueadas personalizadas basadas en prefijos. |P1 |TBD |
|Clasificación del equipo |Asigne clasificaciones a los equipos. |P1 |TBD |
|Acceso de invitado de equipo |Permitir o impedir que los invitados se agregó a los equipos. |No |TBD |
|Creación de equipos |Limite la creación de equipos a los administradores. |No |TBD|
|Creación de equipos |Limite la creación de equipos a los miembros del grupo de seguridad. |P1 |TBD|
|Etiquetas de confidencialidad|Configurar la privacidad y el uso compartido de invitados|No|TBD|

> [!NOTE]
> Para ayudarle a planear con antelación, [obtenga más información sobre cómo configurar estas directivas y qué licencias requieren.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)
> 
> [!NOTE]
> Limitar la creación de grupos y equipos puede ralentizar la productividad de los usuarios, ya que muchos de los servicios de Microsoft 365 y Office 365 requieren que se cree un grupo para que funcione el servicio. Para obtener información adicional, vaya a y expanda [¿Por qué controlar quién crea grupos de Microsoft 365?](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)


#### <a name="additional-information"></a>Información adicional

Una vez determinados los requisitos, puede implementarlos mediante controles de Azure AD. Para obtener instrucciones técnicas sobre cómo implementar esta configuración, vea:

- [Cmdlets de Azure Active Directory para configurar las opciones de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Exigir una directiva de nomenclatura para grupos de Microsoft 365 en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Directiva de nomenclatura de Microsoft 365 Groups](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Opciones de fin de ciclo de vida de grupos, equipos y Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Expiración, retención y archivado de grupos y equipos

Es posible que su organización tenga requisitos adicionales para establecer directivas de expiración, retención y archivado de datos de equipos y equipos (mensajes de canal y archivos de canal). Puede configurar directivas de expiración de grupo para administrar automáticamente el ciclo de vida del grupo y las directivas de retención con el fin de conservar o eliminar la información según sea necesario, y puede archivar equipos (establecerlos en modo de solo lectura) para conservar una vista en un momento dado de un equipo que ya no está activo. Tenga en cuenta que los equipos archivados siguen teniendo aplicada la directiva de expiración y pueden eliminarse a menos que se excluyan o renueve.

|           |            |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Su organización requiere especificar una fecha de expiración para los equipos?</li><li>¿Su organización requiere que se apliquen directivas de retención de datos específicas a los equipos?</li><li>¿Espera su organización requerir la capacidad de archivar equipos inactivos para conservar el contenido en un estado de solo lectura?</li></ul>|
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Documente los requisitos de su organización para la expiración del equipo, la retención de datos y el archivado.</li><li>Planee implementar estos requisitos como parte de la implementación de Teams.</li><li>Comunique y publique las directivas para informar a los usuarios de Teams del comportamiento que pueden esperar.</li></ul>|

> [!TIP]
> Use la tabla siguiente para capturar los requisitos de su organización.

|Funcionalidad |Detalles |Se requiere licencia de Azure AD Premium |Decisión |
|---------|---------|---------|---------|
|Directiva de expiración |Administre el ciclo de vida de los grupos de Microsoft 365 configurando una directiva de expiración. |P1 |TBD|
|Directiva de retención |Conserve o elimine datos durante un período de tiempo específico estableciendo directivas de retención para Teams en el Centro de & seguridad y cumplimiento. **Nota:** El uso de esta característica requiere licencias de Microsoft 365 u Office 365 Enterprise E3 o superior. |No |TBD |
|Archivar y restaurar |Archive un equipo cuando ya no esté activo, pero quiera mantenerlo como referencia o para reactivar en el futuro. |No |TBD |

> [!Note]
> La expiración del grupo es una característica de Azure AD Premium. Para que esta característica esté disponible, el inquilino debe tener una suscripción a Azure AD Premium y licencias para el administrador que configura la configuración y los miembros de los grupos afectados.

#### <a name="additional-information"></a>Información adicional

Para obtener instrucciones técnicas sobre cómo implementar esta configuración, vea:

- [Configure la expiración de los grupos de Microsoft 365.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

- [Configurar directivas de retención de Teams.](retention-policies.md)

- [Archivar o restaurar un equipo.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>Administración de pertenencia a grupos y equipos

La administración coherente de miembros de grupos restringidos o basados en proyectos es necesaria para los equipos que requieren incorporación y gestión rápida de documentos, o usuarios e invitados. Es posible que su organización también tenga que asegurarse de que todos los miembros actuales tengan la justificación comercial para estar en un equipo. Administrar miembros puede ser difícil porque los propietarios del equipo pueden abandonar y los usuarios no suelen dejar los grupos por su propio acuerdo cuando termina un proyecto o cuando cambian de rol. La mejor forma de administrar la pertenencia a grupos que permite a los usuarios obtener acceso cuando sea necesario, pero asegurarse de que el grupo no tiene un riesgo de acceso inadecuado es a través de dos procesos de distrito: la administración de derechos y las revisiones de acceso.

[La administración de](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) derechos le permite delegar en alguien, como un jefe de proyecto, para recopilar todos los recursos necesarios, incluidas las pertenencias a equipos, en un único paquete. También pueden definir quién puede realizar solicitudes: los usuarios de su inquilino o de otras organizaciones conectadas. El jefe de proyecto recibirá solicitudes de acceso en su correo electrónico y aprobar o denegar las solicitudes en el portal MyAccess. Los administradores pueden configurar las condiciones de acceso para incluir una fecha o período de expiración antes del momento en que el usuario o el invitado se quitarán del equipo a menos que se renueve el acceso. Los administradores también pueden configurar los grupos asociados con los equipos para participar en las revisiones de acceso. Para [las revisiones de](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)acceso, los propietarios del grupo recibirán avisos regulares para revisar los miembros de un equipo. Las revisiones de Access incluyen recomendaciones, que facilitan a los propietarios del grupo pasar por su proceso de atesado normal.

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Puntos de decisión | ¿Su organización requiere un proceso coherente para administrar la pertenencia a uno o más equipos? <br> ¿Su organización requiere que los propietarios o los propios miembros justifiquen que siguen formando parte de uno o más equipos de forma regular? <br> ¿Su organización requiere la aprobación para que los usuarios e invitados soliciten acceso a recursos, incluidos equipos, grupos, sitios de SharePoint y aplicaciones? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| ¿Pasos siguientes? | Documente los requisitos de las organizaciones para cada equipo o equipos específicos para la expiración de la suscripción.<br>Planee cómo su organización puede agrupar equipos, grupos, sitios de SharePoint y aplicaciones en paquetes de Access.<br>Planee qué personas, como el administrador del solicitante, un jefe de proyecto, un patrocinador de una organización conectada o un responsable de seguridad de su organización tendrán que aprobar o denegar las solicitudes de acceso. |

> [!TIP]
> Use la tabla siguiente para capturar los requisitos de su organización.

| Funcionalidad | Detalles | Se requiere licencia de Azure AD Premium | Decisión |
|:-|:-|:-|:-|
| Revisiones de Access | Configurar revisiones de acceso para volver a certificar la pertenencia a equipos específicos a intervalos regulares | P2 | TBD |
| Administración de derechos | Configurar el paquete de acceso para permitir que los usuarios e invitados soliciten acceso a los equipos | P2 | TBD |

> [!NOTE]
> Para ayudarle a planear con antelación, [obtenga más información sobre las licencias que necesitan.](https://azure.microsoft.com/pricing/details/active-directory/)

### <a name="additional-information"></a>Información adicional

Para obtener instrucciones técnicas sobre cómo implementar esta configuración, vea:

- [Administración de derechos](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Revisiones de Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Administración de características de Teams

Otro aspecto importante del gobierno y la administración del ciclo de vida de Teams es la capacidad de controlar las características a las que tendrán acceso los usuarios. Puede administrar las características de mensajería, reuniones y llamadas, ya sea en el nivel de Microsoft 365 u Office 365 de la organización o por usuario.


|         |         |
|---------|---------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Su organización requiere que se limiten las características de Teams para todo su inquilino?</li><li>¿Su organización requiere que se limiten las características de Teams para usuarios específicos?</li></ul>|
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Documente los requisitos de su organización para limitar las características de Teams en el nivel de inquilino y de usuario.</li><li>Planee implementar sus requisitos específicos como parte de la implementación de Teams.</li><li>Comunique y publique las directivas para informar a los usuarios de Teams del comportamiento que pueden esperar.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Áreas en las que centrarse en la administración de características de Teams

Teams proporciona funcionalidades granulares para controlar la mensajería, las reuniones, las llamadas y las características de eventos en directo, entre otras, mediante directivas. Se pueden aplicar distintas directivas a todos los usuarios de forma predeterminada o por usuario según lo requiera su organización. 

Para obtener listas detalladas de todas las configuraciones, incluida orientación técnica sobre cómo implementarlas para su organización, vea los artículos siguientes:

- [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md)
- [Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Canales privados en Microsoft Teams](private-channels.md)
- [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md)
- [Administrar directivas de mensajería de Teams](messaging-policies-in-teams.md)
- [Administrar las aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)

Además, puede configurar la moderación de un canal y dar funcionalidades de moderador a determinados usuarios para que puedan controlar quién puede crear publicaciones del canal y responder a ellos. Vea [Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md) para obtener más información.

## <a name="security-and-compliance"></a>Seguridad y cumplimiento

Teams se basa en las capacidades avanzadas de seguridad y cumplimiento de Microsoft 365 y Office 365 y admite la auditoría y los informes, la búsqueda de contenido de cumplimiento, la detección electrónica, la retención legal y las directivas de retención.

> [!Important]
> Si su organización tiene requisitos de cumplimiento y seguridad, revise el contenido detallado que se proporciona sobre este tema en el artículo Información general sobre seguridad y cumplimiento [en Microsoft Teams.](security-compliance-overview.md)

## <a name="related-topics"></a>Temas relacionados

[Inicio rápido de gobierno para Teams](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->

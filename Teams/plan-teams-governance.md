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
ms.openlocfilehash: 38e51b85e7ecf8efc61c6ca78ca16e4366372885
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756236"
---
# <a name="plan-for-governance-in-teams"></a>Planificar el gobierno en Teams

Teams proporciona un amplio conjunto de herramientas para implementar las capacidades de gobierno que su organización pueda necesitar. En este artículo, los profesionales de TI pueden hacer las preguntas correctas para determinar sus requisitos de gobernanza y cómo cumplirlos. 

> [!Tip] 
> Vea la siguiente sesión para obtener más información sobre gobernanza en Microsoft Teams: [gobernanza, administración y](https://aka.ms/teams-governance) ciclo de vida en Microsoft Teams

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Creación de grupos y equipos, nomenclatura, clasificación y acceso de invitado

Es posible que su organización requiera implementar controles estrictos sobre cómo se denominan y clasifican los equipos, si los invitados se pueden agregar como miembros del equipo y quién puede crear equipos. Puede configurar estas áreas mediante Azure Active Directory (Azure AD) y etiquetas de confidencialidad. 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Puntos de decisión|<ul><li>¿Su organización requiere una convención de nomenclatura específica para los equipos?</li><li>¿Necesitan los creadores de equipos la capacidad de asignar clasificaciones específicas de la organización a los equipos?</li><li>¿Necesita restringir la capacidad de agregar invitados a los equipos por equipo?</li><li>¿Su organización requiere limitar quién puede crear equipos?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente los requisitos de su organización para la creación de equipos, los nombres, la clasificación y el acceso de invitados.</li><li>Planee implementar estos requisitos como parte de la implementación de Teams.</li><li>Comunique y publique sus directivas para informar a los usuarios de Teams del comportamiento que pueden esperar.</li></ul>|

> [!NOTE]
> Para ayudarle a planear con antelación, obtenga más información sobre cómo configurar [estas directivas y qué licencias requieren.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)
> 
> [!NOTE]
> Limitar la creación de grupos y equipos puede ralentizar la productividad de los usuarios, ya que muchos servicios de Microsoft 365 y Office 365 requieren que se cree un grupo para que el servicio funcione. Para obtener más información, vaya a y expanda [¿Por qué controlar quién crea grupos de Microsoft 365?](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)


#### <a name="additional-information"></a>Información adicional

Después de determinar los requisitos, puede implementarlos mediante controles de Azure AD. Para obtener instrucciones técnicas sobre cómo implementar esta configuración, vea:

- [Cmdlets de Azure Active Directory para configurar la configuración del grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Exigir una directiva de nomenclatura para grupos de Microsoft 365 en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Directiva de nomenclatura de grupos de Microsoft 365](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Opciones de fin de ciclo de vida para grupos, equipos y Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Expiración, retención y archivado de grupos y equipos

Es posible que su organización tenga requisitos adicionales para configurar directivas de expiración, retención y archivado de datos de equipos y equipos (mensajes de canal y archivos de canal). Puede configurar directivas de expiración de grupo para administrar automáticamente el ciclo de vida del grupo y las directivas de retención para conservar o eliminar información según sea necesario, y puede archivar equipos (configúrelos en modo de solo lectura) para conservar una vista a tiempo de un equipo que ya no está activo. Tenga en cuenta que los equipos archivados siguen aplicando la directiva de expiración y pueden eliminarse a menos que se excluyan o se renueve.

|-          |-           |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Su organización requiere especificar una fecha de expiración para los equipos?</li><li>¿Su organización requiere que se apliquen directivas de retención de datos específicas a los equipos?</li><li>¿Su organización espera requerir la capacidad de archivar equipos inactivos para conservar el contenido en un estado de solo lectura?</li></ul>|
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Documente los requisitos de su organización para la expiración del equipo, la retención de datos y el archivado.</li><li>Planee implementar estos requisitos como parte de la implementación de Teams.</li><li>Comunique y publique sus directivas para informar a los usuarios de Teams del comportamiento que pueden esperar.</li></ul>|

> [!TIP]
> Use la tabla siguiente para capturar los requisitos de su organización.

|Funcionalidad |Detalles |Se requiere una licencia de Azure AD Premium |Decisión |
|---------|---------|---------|---------|
|Directiva de expiración |Administre el ciclo de vida de los grupos de Microsoft 365 estableciendo una directiva de expiración. |P1 |TBD|
|Directiva de retención |Retenga o elimine datos durante un período de tiempo específico estableciendo directivas de retención para Teams en el Centro de cumplimiento de & seguridad. **Nota:** Usar esta característica requiere licencias de Microsoft 365 u Office 365 Enterprise E3 o superiores. |No |TBD |
|Archivar y restaurar |Archive un equipo cuando ya no esté activo, pero desea mantenerlo como referencia o reactivar en el futuro. |No |TBD |

> [!Note]
> La expiración del grupo es una característica de Azure AD Premium. Para que esta característica esté disponible, el inquilino debe tener una suscripción a Azure AD Premium y licencias para el administrador que configura la configuración y los miembros de los grupos afectados.

#### <a name="additional-information"></a>Información adicional

Para obtener instrucciones técnicas sobre cómo implementar esta configuración, vea:

- [Configurar la expiración de grupos de Microsoft 365](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

- [Configurar directivas de retención de Teams](retention-policies.md).

- [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).

## <a name="group-and-team-membership-management"></a>Administración de pertenencia a grupos y equipos

La administración coherente de miembros de grupos restringidos o basados en proyectos es necesaria para los equipos que requieren la incorporación rápida y el offboarding, o usuarios e invitados. Es posible que su organización también tenga que asegurarse de que todos los miembros actuales tengan la justificación empresarial para estar en un equipo. La administración de miembros puede ser difícil porque los propietarios de los equipos pueden salir y los usuarios no suelen abandonar los grupos por su cuenta cuando termina un proyecto o cuando cambian de roles. La mejor manera de administrar la pertenencia a grupos que permite a los usuarios obtener acceso cuando sea necesario pero asegurarse de que el grupo no tiene un riesgo de acceso inadecuado es a través de dos procesos de distrito: administración de derechos y revisiones de acceso.

[La administración](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) de derechos le permite delegar a alguien, como un jefe de proyecto, para recopilar todos los recursos necesarios, incluidas las pertenencias a equipos, en un único paquete. También pueden definir quién puede realizar solicitudes: ya sea usuarios de su inquilino o de otras organizaciones conectadas. El jefe de proyecto recibirá solicitudes de acceso en su correo electrónico y aprobará o denegará solicitudes en el portal de MyAccess. Los administradores pueden configurar las condiciones de acceso para incluir una fecha de expiración o un período para cuando el usuario o el invitado se quiten del equipo a menos que se renueve el acceso. Los administradores también pueden configurar los grupos asociados a los equipos para que puedan participar en las revisiones de acceso. Para [las revisiones de](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)acceso, los propietarios del grupo recibirán avisos regulares para revisar a los miembros de un equipo. Las revisiones de Access incluyen recomendaciones, lo que facilita que los propietarios del grupo puedan pasar por su proceso regular de atestación.

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Puntos de decisión | ¿Su organización requiere un proceso coherente para administrar la pertenencia a uno o varios equipos? <br> ¿Su organización requiere que los propietarios o los propios miembros justifiquen su pertenencia a uno o varios equipos de forma periódica? <br> ¿Necesita su organización la aprobación de usuarios e invitados para solicitar acceso a recursos, incluidos equipos, grupos, sitios de SharePoint y aplicaciones? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| ¿Pasos siguientes? | Documente los requisitos de las organizaciones para cada equipo o equipos específicos para la expiración de la pertenencia.<br>Planee cómo su organización puede agrupar equipos, grupos, sitios de SharePoint y aplicaciones en paquetes de acceso.<br>Planee qué personas, como el administrador del solicitante, un jefe de proyecto, un patrocinador de una organización conectada o un responsable de seguridad de su organización tendrán que aprobar o denegar las solicitudes de acceso. |

> [!TIP]
> Use la tabla siguiente para capturar los requisitos de su organización.

| Funcionalidad | Detalles | Se requiere una licencia de Azure AD Premium | Decisión |
|:-|:-|:-|:-|
| Opiniones de Access | Configurar revisiones de acceso para volver a certificar la pertenencia de equipos específicos a intervalos regulares | P2 | TBD |
| Administración de derechos | Paquete de acceso de configuración para permitir que usuarios e invitados soliciten acceso a los equipos | P2 | TBD |

> [!NOTE]
> Para ayudarle a planear con antelación, [obtenga más información sobre las licencias que requieren.](https://azure.microsoft.com/pricing/details/active-directory/)

### <a name="additional-information"></a>Información adicional

Para obtener instrucciones técnicas sobre cómo implementar esta configuración, vea:

- [Administración de derechos](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Opiniones de Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Administración de características de Teams

Otro aspecto importante del gobierno y la administración del ciclo de vida de Teams es la capacidad de controlar las características a las que tendrán acceso los usuarios. Puede administrar las características de mensajería, reunión y llamadas, ya sea en el nivel de organización de Microsoft 365 u Office 365 o por usuario.


|-        |-        |
|---------|---------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Su organización requiere limitar las características de Teams para todo el espacio empresarial?</li><li>¿Su organización requiere limitar las características de Teams para usuarios específicos?</li></ul>|
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Documente los requisitos de su organización para limitar las características de Teams en el nivel de inquilino y usuario.</li><li>Planee implementar sus requisitos específicos como parte de la implementación de Teams.</li><li>Comunique y publique sus directivas para informar a los usuarios de Teams del comportamiento que pueden esperar.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Áreas de foco de administración de características de Teams

Teams ofrece capacidades granulares para controlar las características de mensajería, reunión, llamadas y eventos en directo, entre otras, a través de directivas. Se pueden aplicar directivas diferentes a todos los usuarios de forma predeterminada o por usuario según lo requiera su organización. 

Para obtener listas detalladas de todas las configuraciones, incluidas las instrucciones técnicas sobre cómo implementarlas para su organización, vea los siguientes artículos:

- [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md)
- [Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Canales privados en Microsoft Teams](private-channels.md)
- [Administración de directivas de reunión en Teams](meeting-policies-in-teams.md)
- [Administrar las directivas de mensajería en Teams](messaging-policies-in-teams.md)
- [Administrar las aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)

Además, puede configurar la moderación de un canal y proporcionar capacidades de moderador a determinados usuarios para que puedan controlar quién puede crear publicaciones de canal y responder a ellas. Vea [Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md) para obtener más información.

## <a name="security-and-compliance"></a>Seguridad y cumplimiento

Teams se basa en las capacidades avanzadas de seguridad y cumplimiento de Microsoft 365 y Office 365 y admite auditorías e informes, búsqueda de contenido de cumplimiento, detección electrónica, retención legal y directivas de retención.

> [!Important]
> Si su organización tiene requisitos de cumplimiento y seguridad, revise el contenido detallado que se proporciona sobre este tema en el artículo Información general sobre seguridad y cumplimiento [en Microsoft Teams.](security-compliance-overview.md)

## <a name="related-topics"></a>Temas relacionados

[Inicio rápido de gobierno para Teams](teams-adoption-governance-quick-start.md)

[Instrucciones de licencias de Microsoft 365 para el cumplimiento & seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->

---
title: Plan para la administración en Teams - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: En este artículo, obtendrá información sobre cómo planear la implementación de las capacidades de gobierno en Teams.
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

Teams proporciona un amplio conjunto de herramientas para implementar cualquier funcionalidad de gobierno que su organización pueda necesitar. En este artículo, se guía a los profesionales de TI para que hagan las preguntas correctas para determinar sus requisitos de gobierno y cómo cumplirlos. 

> [!Tip] 
> Vea la siguiente sesión para obtener más información sobre la gobernanza en Microsoft Teams: [gobernanza, administración y ciclo de vida en Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Creación, nomenclatura, clasificación y acceso de invitados a grupos y equipos

Es posible que su organización requiera que implemente controles estrictos sobre el nombre y la clasificación de los equipos, si los invitados pueden agregarse como miembros del equipo y quién puede crear equipos. Puede configurar estas áreas con Azure Active Directory (Azure AD) y etiquetas de confidencialidad. 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Puntos de decisión|<ul><li>¿Su organización requiere una Convención de nomenclatura específica para Teams?</li><li>¿Los creadores de equipos necesitan la capacidad de asignar clasificaciones específicas de la organización a teams?</li><li>¿Necesita restringir la posibilidad de agregar invitados a los equipos de acuerdo con cada equipo?</li><li>¿Requiere su organización limitar quién puede crear equipos?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Siguientes pasos|<ul><li>Documente los requisitos de la organización para la creación, denominación, clasificación y acceso de invitados de su organización.</li><li>Planee la implementación de estos requisitos como parte de la implementación de Teams.</li><li>Comunique y publique sus directivas para informar a los usuarios del comportamiento que pueden esperar.</li></ul>|

> [!TIP]
> Use la tabla siguiente para capturar los requisitos de la organización.

|Función |Detalles |Azure AD Premium <br> licencia requerida |Tomar |
|---------|---------|---------|---------|
|Directiva de nomenclatura de grupo | Usar palabras bloqueadas personalizadas basadas en prefijos y prefijos. |Min |DETERMINADO |
|Clasificación de equipo |Asignar clasificaciones a los equipos. |Min |DETERMINADO |
|Acceso de invitado de equipo |Permitir o impedir que los invitados se agreguen a teams. |No |DETERMINADO |
|Creación de equipos |Limitar la creación de equipos a los administradores. |No |DETERMINADO|
|Creación de equipos |Limitar la creación del equipo a miembros del grupo de seguridad. |Min |DETERMINADO|
|Etiquetas de confidencialidad|Configurar la privacidad y el uso compartido de invitados|No|DETERMINADO|

> [!NOTE]
> Para ayudarle a planificar con antelación, [Obtenga más información sobre cómo establecer estas directivas y qué licencias necesitan](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).
> 
> [!NOTE]
> La limitación de la creación de grupos y equipos puede ralentizar la productividad de los usuarios, porque muchos de los servicios de Microsoft 365 y Office 365 requieren la creación de grupos para que el servicio funcione. Para obtener información adicional, vaya a y expanda el [motivo por el que el control crea grupos de Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Información adicional

Una vez que haya determinado sus requisitos, puede implementarlos con los controles de Azure AD. Para obtener instrucciones técnicas sobre cómo implementar esta configuración, consulte:

- [Cmdlets de Azure Active Directory para configurar las opciones de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Exigir una directiva de nomenclatura para los grupos de Microsoft 365 en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Directiva de nomenclatura de Microsoft 365 Groups](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Opciones de fin del ciclo de vida para grupos, equipos y Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Caducidad, retención y archivado de grupo y equipo

Es posible que su organización tenga requisitos adicionales para establecer directivas para el vencimiento, la retención y los datos de Teams y de almacenamiento (mensajes de canal y archivos de canal). Puede configurar directivas de expiración de grupo para administrar automáticamente el ciclo de vida del grupo y las directivas de retención para conservar o eliminar información según sea necesario y puede archivar los equipos (establecerlos en el modo de solo lectura) para conservar una vista puntual de un equipo que ya no esté activo. Tenga en cuenta que los equipos que están archivados continúan teniendo la Directiva de expiración aplicada y se pueden eliminar a menos que se excluyan o renueven.

|           |            |
|-----------|------------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Necesita su organización especificar una fecha de expiración para Teams?</li><li>¿Su organización requiere directivas específicas de retención de datos que se aplicarán a teams?</li><li>¿Se espera que su organización necesite la capacidad de archivar equipos inactivos para conservar el contenido en un estado de solo lectura?</li></ul>|
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Documente los requisitos de la organización para la caducidad del equipo, la retención de datos y el archivado.</li><li>Planee la implementación de estos requisitos como parte de la implementación de Teams.</li><li>Comunique y publique sus directivas para informar a los usuarios del comportamiento que pueden esperar.</li></ul>|

> [!TIP]
> Use la tabla siguiente para capturar los requisitos de la organización.

|Función |Detalles |Se necesita una licencia de Azure AD Premium |Tomar |
|---------|---------|---------|---------|
|Directiva de expiración |Administre el ciclo de vida de los grupos de Microsoft 365 mediante la configuración de una directiva de expiración. |Min |DETERMINADO|
|Directiva de retención |CONSERVE o elimine datos durante un período de tiempo específico configurando directivas de retención para equipos en el centro de cumplimiento de & de seguridad. **Nota**: para usar esta característica, es necesario disponer de licencias de Microsoft 365 u Office 365 Enterprise E3 o una versión posterior. |No |DETERMINADO |
|Archivar y restaurar |Archivar un equipo cuando ya no está activo pero desea mantenerlo por referencia o reactivarlo en el futuro. |No |DETERMINADO |

> [!Note]
> La expiración del grupo es una característica de Azure AD Premium. Para que esta característica esté disponible, su inquilino debe tener una suscripción a Azure AD Premium y licencias para el administrador que configure la configuración y los miembros de los grupos afectados.

#### <a name="additional-information"></a>Información adicional

Para obtener instrucciones técnicas sobre cómo implementar esta configuración, consulte:

- [Configurar la expiración de grupos de 365 de Microsoft](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

- [Configure las directivas de retención de Teams](retention-policies.md).

- [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).

## <a name="group-and-team-membership-management"></a>Administración de la pertenencia a grupos y equipos

Administrar de forma coherente miembros de proyectos basados en proyectos o grupos restringidos son necesarios para los equipos que requieren la incorporación y descarga rápida o los usuarios y los invitados. Es posible que su organización también tenga que asegurarse de que todos los miembros actuales tengan la justificación empresarial en un equipo. La administración de miembros puede ser difícil porque los propietarios del equipo pueden abandonar y los usuarios no suelen dejar grupos por sí mismos cuando el proyecto finaliza o cuando cambian los roles. La mejor manera de administrar la pertenencia a grupos que permite a los usuarios obtener acceso cuando es necesario pero asegurarse de que el grupo no tiene ningún riesgo de acceso inapropiado es mediante dos procesos de distrito: la administración de derechos y las revisiones de Access.

La [Administración de derechos](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) le permite delegar a alguien, como un jefe de proyecto, recopilar todos los recursos necesarios, incluidas las pertenencias a equipos, en un único paquete. También pueden definir quién puede hacer solicitudes: usuarios de su inquilino o de otras organizaciones conectadas. El jefe de proyecto recibirá solicitudes de acceso en su correo electrónico y aprobará o denegará solicitudes en el portal de acceso. Los administradores pueden configurar las condiciones de acceso para incluir una fecha o período de expiración cuando el usuario o el invitado se van a quitar del equipo, a menos que se renueve el acceso. Los administradores también pueden configurar los grupos asociados a los equipos para participar en las revisiones de Access. Para las [revisiones de Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview), los propietarios del grupo recibirán avisos periódicos para revisar los miembros de un equipo. Las revisiones de Access incluyen recomendaciones que hacen que sea más fácil para los propietarios del grupo pasar por el proceso de atestación habitual.

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Puntos de decisión | ¿Requiere su organización un proceso coherente para administrar la pertenencia de uno o varios equipos? <br> ¿Requiere su organización propietarios, o los miembros mismos, para justificar la pertenencia continua de uno o varios equipos de forma periódica? <br> ¿Requiere su organización aprobación para que los usuarios y los invitados soliciten el acceso a los recursos, incluidos equipos, grupos, sitios de SharePoint y aplicaciones? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Pasos siguientes | Documente los requisitos de la organización para cada equipo o para equipos específicos para la caducidad de la suscripción.<br>Planee la forma en que su organización puede empaquetar equipos, grupos, sitios de SharePoint y aplicaciones conjuntamente en paquetes de Access.<br>Planee qué personas, como el administrador del solicitante, un jefe de proyecto, un patrocinador de una organización conectada o un funcionario de seguridad de su organización deberán aprobar o denegar solicitudes de acceso. |

> [!TIP]
> Use la tabla siguiente para capturar los requisitos de la organización.

| Función | Detalles | Se necesita una licencia de Azure AD Premium | Tomar |
|:-|:-|:-|:-|
| Revisiones de Access | Configurar las revisiones de Access para recertificar la pertenencia de determinados equipos a intervalos regulares | P2 | DETERMINADO |
| Administración de derechos | Configurar el paquete de Access para permitir a los usuarios e invitados solicitar acceso a teams | P2 | DETERMINADO |

> [!NOTE]
> Para ayudarle a planificar con antelación, [Obtenga más información sobre las licencias que requieren](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="additional-information"></a>Información adicional

Para obtener instrucciones técnicas sobre cómo implementar esta configuración, consulte:

- [Administración de derechos](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Revisiones de Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Administración de características de Teams

Otro aspecto importante de la administración del ciclo de vida y del gobierno de los equipos es la capacidad de controlar las características a las que los usuarios tendrán acceso. Puede administrar las características de mensajería, reunión y llamada, ya sea en el nivel de organización de Microsoft 365 u Office 365 o por usuario.


|         |         |
|---------|---------|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Su organización requiere la limitación de las características de Teams para todo el inquilino?</li><li>¿Su organización requiere la limitación de las características de Teams para usuarios específicos?</li></ul>|
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Documente los requisitos de la organización para limitar las características de Teams en el nivel de inquilino y de usuario.</li><li>Planee la implementación de sus requisitos específicos como parte de la implementación de Teams.</li><li>Comunique y publique sus directivas para informar a los usuarios del comportamiento que pueden esperar.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Áreas de administración de características de Teams

Teams proporciona capacidades granulares para controlar la mensajería, la reunión, las llamadas y las características de eventos en vivo, así como más, mediante directivas. Se pueden aplicar diferentes directivas a todos los usuarios de forma predeterminada o por usuario, según lo requiera su organización. 

Para obtener listas detalladas de todas las opciones de configuración, incluyendo instrucciones técnicas sobre cómo implementarlas para su organización, vea los artículos siguientes:

- [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md)
- [Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Canales privados en Microsoft Teams](private-channels.md)
- [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md)
- [Administrar directivas de mensajería de Teams](messaging-policies-in-teams.md)
- [Administrar las aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)

Además, puede configurar la moderación de un canal y proporcionar capacidades de moderador a determinados usuarios para que puedan controlar quién puede crear publicaciones de canal y responder a ellas. Para obtener más información [, vea Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md) .

## <a name="security-and-compliance"></a>Seguridad y cumplimiento

Teams está basado en las capacidades avanzadas de seguridad y cumplimiento de Microsoft 365 y Office 365, y admite auditorías e informes, búsqueda de contenido de cumplimiento, e-Discovery, retención legal y directivas de retención.

> [!Important]
> Si su organización tiene requisitos de cumplimiento y seguridad, revise el contenido detallado de este tema en el artículo [información general sobre seguridad y cumplimiento en Microsoft Teams](security-compliance-overview.md).

## <a name="related-topics"></a>Temas relacionados

[Inicio rápido de gobierno para Teams](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->

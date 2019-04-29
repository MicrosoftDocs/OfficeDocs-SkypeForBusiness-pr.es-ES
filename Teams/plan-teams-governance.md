---
title: Plan para la administración en Teams - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
description: Obtenga información acerca de cómo planear la implementación de las capacidades de gobierno en los equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b4e6d7c647c619baf5a890b74b2e807dbc111ca0
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401716"
---
# <a name="plan-for-governance-in-teams"></a>Planificar el gobierno en Teams

Los equipos proporciona un amplio conjunto de herramientas para implementar cualquier capacidades de gobierno, es posible que requiere su organización. En este artículo es una guía para profesionales de TI para las preguntas adecuadas para determinar los requisitos para el gobierno y cómo cumplirlos. 

> [!Tip] 
> Vea la sesión siguiente para obtener más información acerca de más información acerca del gobierno en Microsoft Teams: [gobierno, administración y ciclo de vida en los equipos de Microsoft](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Creación de grupo y de equipo, nomenclatura, clasificación y acceso de invitado

Es posible que requieren la implementación de controles estrictos en cómo se denominado y clasifica los equipos, si se pueden agregar invitados como miembros del equipo y quién puede crear los equipos de la organización. Puede configurar cada una de estas áreas con Azure Active Directory (AD Azure). 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>¿La organización requiere una convención de nomenclatura específica para los equipos?</li><li>¿Los creadores de equipo necesitan la capacidad para asignar clasificaciones específicos de la organización a los equipos?</li><li>¿Necesita restringir la capacidad de agregar invitados a los equipos en una base por equipo?</li><li>¿La organización requiere limitar quién puede crear equipos?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documentar los requisitos de su organización para la creación del equipo, nomenclatura, clasificación y acceso de invitado.</li><li>Plan para implementar estos requisitos como parte de la implantación de los equipos.</li><li>Comunicarse y publicar las directivas para informar a los usuarios de los equipos del comportamiento que pueden esperar.</li></ul>|

> [!TIP]
> Use la tabla siguiente para capturar los requisitos de su organización.

|Capacidad |Detalles |Premium de Azure AD <br> se requiere una licencia |Toma de decisiones |
|---------|---------|---------|---------|
|Directiva de nomenclatura de grupo | Use personalizado, prefijo y sufijo – basado en palabras bloqueado. |P1 |TBD |
|Clasificación de equipo |Asignar clasificaciones a los equipos. |P1 |TBD |
|Acceso de invitado de equipo |Permitir o evitar que se agreguen a los equipos de los invitados. |No |TBD |
|Creación de equipos |Limitar la creación del equipo a los administradores. |No |TBD|
|Creación de equipos |Limitar la creación del equipo a los miembros del grupo de seguridad. |P1 |TBD|

> [!NOTE]
> Para ayudarle a planear de antemano, [aprender más acerca de cómo establecer estas directivas y qué licencias que requieren](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).
> 
> [!NOTE]
> Limitación de creación de grupo y del equipo puede disminuir la productividad de los usuarios, debido a que muchos servicios de Office 365 requieren que se cree grupos para que funcione el servicio. Para obtener información adicional, vaya a y expanda [¿por qué controlar quién crea los grupos de Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Información adicional

Una vez que haya determinado los requisitos, se puede implementar mediante el uso de controles de Azure AD. Para obtener orientación técnica acerca de cómo implementar estas opciones, vea:

-   [Cmdlets de azure Active Directory para configurar las opciones de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

-   [Exigir una directiva de nomenclatura para los grupos de Office 365 en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).

-   [Directiva de nomenclatura de grupos de office 365](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).


## <a name="group-and-team-expiration-retention-and-archiving"></a>Expiración de grupo y de equipo, retención y archivado

Su organización puede tener requisitos adicionales para la configuración de directivas de caducidad, retención, y los equipos de archivado y de los equipos de datos (archivos de canal y los mensajes del canal). Puede configurar las directivas de expiración de grupo para administrar automáticamente el ciclo de vida de las directivas de grupo y de retención para conservar o eliminar la información según sea necesario, y puede archivar los equipos (establecerlas al modo de sólo lectura) para conservar una vista de punto en el tiempo de un equipo que ya no está activo.

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿Su organización requiere que especifica una fecha de caducidad para los equipos?</li><li>¿La organización requiere datos específicos las directivas de retención se aplica a los equipos?</li><li>¿Espera su organización requieren la capacidad para archivar los equipos inactivos para conservar el contenido en un estado de sólo lectura?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Requisitos de su organización de expiración del equipo, la retención de datos y archivado de documentos.</li><li>Plan para implementar estos requisitos como parte de la implantación de los equipos.</li><li>Comunicarse y publicar las directivas para informar a los usuarios de los equipos del comportamiento que pueden esperar.</li></ul>|

> [!TIP]
> Use la tabla siguiente para capturar los requisitos de su organización.

|Capacidad |Detalles |Se requiere una licencia AD Premium Azure |Toma de decisiones |
|---------|---------|---------|---------|
|Directiva de caducidad |Administrar el ciclo de vida de los grupos de Office 365 mediante la configuración de una directiva de caducidad. |P1 |TBD|
|Directiva de retención |Conservar o eliminar los datos para un período de tiempo específico mediante la configuración de las directivas de retención para los equipos en el centro de cumplimiento de seguridad &. **Nota**: el uso de esta característica requiere licencias de Office 365 Enterprise E3 o superior. |No |TBD |
|Archivo y restauración |Archivar un equipo cuando ya no está activo pero desea conservarla para referencia o volver a activar en el futuro. |No |TBD |

> [!Note]
> Expiración de grupo es una característica de Azure AD Premium. Para que esta característica esté disponible, el inquilino debe tener una suscripción a Azure AD Premium y licencias para el administrador que configura la configuración y los miembros de los grupos afectados.

#### <a name="additional-information"></a>Información adicional

Para obtener orientación técnica acerca de cómo implementar estas opciones, vea:

-   [Configurar la caducidad de los grupos de Office 365](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

-   [Configurar las directivas de retención de los equipos](retention-policies.md).

-   [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).


## <a name="teams-feature-management"></a>Administración de la característica de los equipos

Otro aspecto importante de gobierno y administración del ciclo de vida de los equipos es la capacidad para controlar qué características de los usuarios tendrán acceso a. Puede administrar mensajería, de la reunión y llamar a funciones, ya sea en el nivel de inquilino de Office 365 o por usuario. 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>¿La organización requiere limitar las características de los equipos para el inquilino todo?</li><li>¿La organización requiere limitar las características de los equipos para usuarios específicos?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>Pasos siguientes|<ul><li>Documentar los requisitos de la organización de la limitación de las características de los equipos en el nivel de usuario y del inquilino.</li><li>Plan para implementar los requisitos específicos como parte de la implantación de los equipos.</li><li>Comunicarse y publicar las directivas para informar a los usuarios de los equipos del comportamiento que pueden esperar.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Áreas de enfoque de administración de características de los equipos

Los equipos proporciona capacidades granulares para controlar mensajería, convocatorias de reunión, llamada y live características de eventos y otras tareas, a través de las directivas. Pueden aplicar distintas directivas a todos los usuarios de forma predeterminada o por usuario según sea necesario por la organización. 

Para obtener listas detalladas de todas las configuraciones, incluido orientación técnica acerca de cómo implementarlos para su organización, consulte los siguientes artículos:

-   [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md)
-   [Administrar Teams durante la transición al nuevo Centro de administración de Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
-   [Administrar las directivas de reunión en los equipos](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a>Seguridad y cumplimiento de normas

Los equipos se basa en la seguridad avanzada y funciones de cumplimiento de Office 365 y es compatible con auditoría y creación de informes, búsqueda de contenido de cumplimiento, exhibición de documentos electrónicos, suspensión Legal y las políticas de retención. 

> [!Important]
> Si su organización tiene requisitos de seguridad y cumplimiento de normas, revise el contenido exhaustivos proporcionado acerca de este tema en el artículo de [información general de seguridad y cumplimiento de normas en los equipos de Microsoft](security-compliance-overview.md).

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->

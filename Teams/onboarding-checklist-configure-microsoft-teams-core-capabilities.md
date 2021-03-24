---
title: 'Lista de comprobación de incorporación: configurar las capacidades principales: Microsoft Teams'
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Siga las tareas principales y las actividades pendientes de esta lista de comprobación al configurar Teams para su organización.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c28f33cb8d3c3823f74deb8f6540a39482f68b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098036"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurar las capacidades principales de Microsoft Teams

| No | Actividad o tarea | Descripción | ¿Completado? | Información adicional |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Validar que el entorno incluye todos los requisitos previos de Teams | Teams depende de otras plataformas para crear una solución de colaboración de un extremo a otro. Trabaje con sus equipos de TI para asegurarse de que ha implementado y configurado correctamente Exchange, SharePoint Online y OneDrive para la Empresa. | | [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md) |
| 2  | Validar que Teams está habilitado para el inquilino | Teams está activado de forma predeterminada para todas las organizaciones. Compruebe la **página Servicios & complementos** en el Centro de administración de Microsoft 365 para comprobar que Teams está habilitado para su organización y habilitarlo si es necesario. | | [Configurar Microsoft Teams en Microsoft 365 u Office 365](office-365-set-up.md) |
| 3  | Configurar roles y permisos | Teams admite dos tipos de roles: Miembro y Propietario. <br/><br/>Después de agregar un miembro a un equipo, un propietario también puede promover un miembro al rol propietario. Como práctica recomendada, le recomendamos que tenga al menos dos propietarios asignados a cada equipo. <br/><br/>De forma predeterminada, todos los usuarios de la organización que tienen un buzón hospedado en Exchange Online pueden crear un equipo. A un usuario que crea un equipo nuevo se le concede automáticamente el rol propietario de ese equipo. <br/><br/>Si es necesario, puede configurar la configuración de grupo de Microsoft 365 para que solo permita a usuarios específicos crear nuevos equipos. | | [Asignar roles y permisos en Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Grupos de Microsoft 365 y Microsoft Teams](office-365-groups.md) <br/><br/>[Administrar quién puede crear grupos de Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurar la configuración de Teams para todo el espacio empresarial | Puede configurar algunas configuraciones de Teams en el nivel de inquilino. Los usuarios habilitados para Teams heredan esta configuración de la configuración del espacio empresarial:<ul><li>General</li><li>Integración de correo electrónico</li><li>Aplicaciones</li><li>Almacenamiento en nube personalizado</li><li>Llamadas y reuniones</li><li>Mensajería </li></ul>| | [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md) |
| 5  | OPCIONAL: Configurar el acceso de invitado | Puede usar el acceso de invitado en Teams para colaborar con personas ajenas a su organización concedéndoles acceso a equipos y canales. El acceso de invitado es una configuración de nivel de inquilino en Teams. Está desactivado por defecto. <br/>Habilite el acceso de invitado y configure la configuración de invitado de todo el espacio empresarial, si su organización tiene previsto usar esa característica. | | [Acceso de invitado en Microsoft Teams](guest-access.md) |
| 6  | OPCIONAL: Configurar la directiva de nomenclatura de Teams | Teams aprovecha las directivas de nomenclatura para grupos de Microsoft 365 cuando los usuarios crean o editan nombres de equipo. <br/><br/>De forma predeterminada, no se aplican restricciones de nomenclatura cuando un usuario crea un equipo. <br/><br/>Si necesita exigir reglas para los nombres de los equipos, configure las directivas de nomenclatura de grupos de Microsoft 365 que se apliquen a su organización. Puede establecer prefijos y sufijos obligatorios y especificar palabras bloqueadas. | | [Planear grupos de Microsoft 365 al crear equipos en Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Directiva de nomenclatura de grupos de Microsoft 365](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurar Exchange para el dominio SMTP de Teams | Teams usa Exchange Online para enviar notificaciones a los miembros del equipo mediante el dominio SMTP (email.teams.microsoft.com) cuando se han agregado o quitado. <br/><br/>Asegúrese de agregar este dominio SMTP a la lista de dominios aceptados en su infraestructura de Exchange. | | [Crear listas de remitentes seguros en Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Configurar y administrar el acceso de usuario a Teams | Aunque le recomendamos encarecidamente que habilite todos los usuarios para Teams, puede permitir o no permitir el acceso a Teams por usuario asignando o quitando la licencia de producto de Teams. | | [Administrar el acceso de los usuarios a Microsoft Teams](user-access.md) |
| 9  | Asignar licencias a usuarios | Asignar licencias a los usuarios para características como conferencias de audio, sistema telefónico y planes de llamadas | | [Asignar licencias de complementos de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Opcional: Usar PowerShell para administrar Teams | Puede usar cmdlets de PowerShell en lugar del Centro de administración de Microsoft 365 para administrar y administrar la configuración de Teams. | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |
---
title: 'Lista de comprobación de la incorporación: configurar las funciones principales-Microsoft Teams'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Siga las actividades básicas y tareas pendientes de esta lista de comprobación cuando configure Teams para su organización.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1881afc4897ca6321cd56609e491aef144e10da
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456094"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurar las capacidades principales de Microsoft Teams

| No | Actividad o tarea | Descripción | ¿Completado? | Información adicional |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Validar que su entorno incluye todos los requisitos previos de Teams | Teams depende de otras plataformas para construir una solución de colaboración de extremo a extremo. Trabaje con sus equipos de TI para asegurarse de que ha implementado y configurado correctamente Exchange, SharePoint Online y OneDrive para la empresa. | | [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md) |
| 2  | Validar que Teams está habilitado para el inquilino | Teams está activado de forma predeterminada para todas las organizaciones. Compruebe la página **servicios & complementos** en el centro de administración de Microsoft 365 para comprobar que Teams está habilitado para su organización y habilítelo si es necesario. | | [Configurar Microsoft Teams en Microsoft 365 u Office 365](office-365-set-up.md) |
| 3  | Configurar roles y permisos | Teams admite dos tipos de roles: miembro y propietario. <br/><br/>Después de agregar un miembro a un equipo, un propietario también puede promocionar un miembro al rol de propietario. Como práctica recomendada, le recomendamos que tenga al menos dos propietarios asignados a cada equipo. <br/><br/>De forma predeterminada, todos los usuarios de la organización que tienen un buzón de correo hospedado en Exchange online pueden crear un equipo. A un usuario que crea un equipo nuevo se le concede automáticamente el rol de propietario de ese equipo. <br/><br/>Si es necesario, puede configurar las opciones del grupo de Microsoft 365 para permitir que usuarios específicos creen nuevos equipos. | | [Asignar roles y permisos en Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Microsoft 365 Groups y Microsoft Teams](office-365-groups.md) <br/><br/>[Administrar quién puede crear grupos de Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurar las opciones de Teams para todo el inquilino | Puede configurar algunas opciones de Teams en el nivel de inquilino. Los usuarios que están habilitados para los equipos heredan esta configuración de la configuración de inquilinos:<ul><li>General</li><li>Integración de correo electrónico</li><li>Aplicaciones</li><li>Almacenamiento en nube personalizado</li><li>Llamadas y reuniones</li><li>Mensajería </li></ul>| | [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md) |
| 5  | OPCIONAL: configurar el acceso de invitado | Use el acceso de invitado en Teams para colaborar con personas de fuera de su organización al otorgarles acceso a los equipos y canales. El acceso de invitados es una configuración de nivel de inquilino de Teams. Está desactivado por defecto. <br/>Habilite el acceso de invitado y configure la configuración de invitado en el inquilino, si su organización tiene previsto usar esa característica. | | [Acceso de invitado en Microsoft Teams](guest-access.md) |
| 6  | OPCIONAL: configurar la política de nomenclatura de Teams | Teams aprovecha las políticas de nomenclatura para los grupos de Microsoft 365 cuando los usuarios crean o editan nombres de equipos. <br/><br/>De forma predeterminada, no se aplican restricciones de nomenclatura cuando un usuario crea un equipo. <br/><br/>Si necesita aplicar reglas para los nombres de Teams, configure las directivas de nomenclatura de Microsoft 365 Groups que se aplican a su organización. Puede establecer prefijos y sufijos obligatorios y especificar palabras bloqueadas. | | [Planear los grupos de Microsoft 365 al crear equipos en Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Directiva de nomenclatura de Microsoft 365 Groups](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurar Exchange para el dominio SMTP de Teams | Teams usa Exchange Online para enviar notificaciones a los miembros del equipo mediante el dominio SMTP (email.teams.microsoft.com) cuando se han agregado o quitado. <br/><br/>Asegúrese de agregar este dominio SMTP a la lista de dominios aceptados de su infraestructura de Exchange. | | [Crear listas de remitentes seguros en Exchange](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 4,8  | Configurar y administrar el acceso de los usuarios a los equipos | Aunque le recomendamos encarecidamente que habilite todos los usuarios para Teams, puede permitir o denegar el acceso a Teams para cada usuario asignando o quitando la licencia de producto de Teams. | | [Administrar el acceso de los usuarios a Microsoft Teams](user-access.md) |
| 99,999  | Asignar licencias a usuarios | Asignar licencias a los usuarios para características como audioconferencia, teléfonos y planes de llamadas | | [Asignar licencias de complemento de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| base10 | Opcional: usar PowerShell para administrar equipos | Puede usar cmdlets de PowerShell en lugar del centro de administración de Microsoft 365 para administrar y administrar la configuración de Teams. | | [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |

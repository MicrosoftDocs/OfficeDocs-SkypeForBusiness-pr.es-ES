---
title: Lista de comprobación de incorporación - Configurar las capacidades principales - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Siga las tareas y actividades principales y pendientes de esta lista de comprobación al configurar Teams para su organización.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 200edfcbe8c93c2f629f176a17959e60f70cb902
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564248"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurar las funcionalidades principales de Microsoft Teams

| No | Actividad o tarea | Descripción | ¿Completado? | Información adicional |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Validar que su entorno incluye todos los requisitos previos de Teams | Teams depende de otras plataformas para construir una solución de colaboración de un extremo a otro. Trabaje con sus equipos de TI para asegurarse de que ha implementado y configurado correctamente Exchange, SharePoint Online y OneDrive para la Empresa. | | [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md) |
| 2  | Validar que Teams está habilitado para el inquilino | Teams está activado de forma predeterminada para todas las organizaciones. Consulte la página **Servicios & complementos en** la Centro de administración de Microsoft 365 para comprobar que Teams está habilitado para su organización y habilitarlo si es necesario. | | [Configurar Microsoft Teams en Microsoft 365 o Office 365](office-365-set-up.md) |
| 3  | Configurar roles y permisos | Teams admite dos tipos de roles: miembro y propietario. <br/><br/>Después de agregar un miembro a un equipo, un propietario también puede promover a un miembro al rol Propietario. Como procedimiento recomendado, le recomendamos que tenga al menos dos propietarios asignados a cada equipo. <br/><br/>De forma predeterminada, todos los usuarios de la organización que tengan un buzón hospedado en Exchange Online pueden crear un equipo. A un usuario que crea un equipo se le concede automáticamente el rol propietario de ese equipo. <br/><br/>Si lo necesita, puede configurar las opciones de grupo de Microsoft 365 para permitir que determinados usuarios creen nuevos equipos. | | [Asignar roles y permisos en Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Grupos de Microsoft 365 y Microsoft Teams](office-365-groups.md) <br/><br/>[Administrar quién puede crear Grupos de Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurar las opciones de Teams para todos los inquilinos | Puede configurar algunas opciones de Teams en el nivel de inquilino. Los usuarios habilitados para Teams heredan esta configuración de la configuración del inquilino:<ul><li>General</li><li>Integración de correo electrónico</li><li>Aplicaciones</li><li>Almacenamiento en nube personalizado</li><li>Llamadas y reuniones</li><li>Mensajería </li></ul>| | [Administrar la configuración de Microsoft Teams para su organización](enable-features-office-365.md) |
| 5  | OPCIONAL: Configurar el acceso de invitado | Puede usar el acceso de invitado en Teams para colaborar con personas de fuera de su organización al concederles acceso a equipos y canales. El acceso de invitado es una configuración de nivel de inquilino en Teams. Está desactivado por defecto. <br/>Habilite el acceso de invitado y configure la configuración de invitado para todos los inquilinos, si su organización planea usar esa característica. | | [Acceso de invitado en Microsoft Teams](guest-access.md) |
| 6  | OPCIONAL: Configurar la directiva de nomenclatura de Teams | Teams aprovecha las directivas de nomenclatura para Grupos de Microsoft 365 cuando los usuarios crean o editan nombres de equipos. <br/><br/>De forma predeterminada, no se aplican restricciones de nomenclatura cuando un usuario crea un equipo. <br/><br/>Si necesita aplicar reglas para los nombres de equipos, configure directivas de nomenclatura de Grupos de Microsoft 365 que se apliquen a su organización. Puede establecer prefijos y sufijos obligatorios y especificar palabras bloqueadas. | | [Planear grupos de Microsoft 365 al crear equipos en Microsoft Teams](plan-office-365-groups.md) <br/><br/>[directiva de nomenclatura de Grupos de Microsoft 365](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurar Exchange para el dominio SMTP de Teams | Teams usa Exchange Online para enviar notificaciones a los miembros del equipo mediante el dominio SMTP (email.teams.microsoft.com) cuando se agregan o quitan. <br/><br/>Asegúrese de agregar este dominio SMTP a la lista de dominios aceptados en la infraestructura de Exchange. | | [Crear listas de remitentes seguras en Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Configurar y administrar el acceso de usuarios a Teams | Aunque le recomendamos encarecidamente que habilite a todos los usuarios para Teams, puede permitir o no permitir el acceso a Teams por usuario asignando o quitando la licencia del producto de Teams. | | [Administrar el acceso de los usuarios a Microsoft Teams](user-access.md) |
| 9  | Asignar licencias a usuarios | Asignar licencias a los usuarios para características como Audioconferencia, Sistema telefónico y Planes de llamadas | | [Asignar licencias de complementos de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Opcional: Usar PowerShell para administrar Teams | Puede usar cmdlets de PowerShell en lugar de la Centro de administración de Microsoft 365 para administrar y administrar la configuración de Teams. | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |
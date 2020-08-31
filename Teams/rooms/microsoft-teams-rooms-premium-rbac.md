---
title: Control de acceso basado en roles con el servicio de Microsoft Teams Room Premium
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga más información sobre el control de acceso basado en roles con el servicio administrado salones de Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: 2f3886d7f7f59521028b87f05ffedfaa1fae9ac2
ms.sourcegitcommit: 206e01b72218f57e68823dc23b7ca28bce7cb3bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300294"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Control de acceso basado en roles con el servicio administrado de salas de Microsoft Teams

El control de acceso basado en roles (RBAC) en el servicio administrado salones de Microsoft Teams le ayuda a administrar el acceso de usuarios a los datos de recursos de la sala de su organización. Al asignar roles a los usuarios de su portal de servicios, puede limitar lo que pueden ver y cambiar. Cada rol tiene un conjunto de permisos que determinan los usuarios con los que el rol puede tener acceso y cambiar dentro de la organización.

Para crear, editar o asignar roles, su cuenta debe tener uno de los siguientes permisos:

- Administrador global a través de Azure Active Directory (Azure AD)
- Administrador de servicios administrados a través del portal de servicios administrados de salas de Microsoft Teams

## <a name="what-is-a-role"></a>¿Qué es un rol?

Un rol define el conjunto de permisos que se concede a los usuarios asignados a ese rol. Por el momento, el servicio administrado de salas de Microsoft Teams tiene tres roles integrados: **Administrador de servicios administrados**, **responsable de sitio**y técnico de **sitios**. Cubren algunos escenarios comunes de los usuarios de su organización que pueden implicarse en la administración de sus salas.

Para ver los roles, en el panel de navegación izquierdo del portal de servicios administrados de Microsoft Team salas, vaya a **roles**y, después, seleccione cualquiera de los roles para ver las propiedades, los permisos y las asignaciones del rol.  

- **Propiedades**: el nombre, el tipo de rol y la descripción
- **Permisos**: enumera las características y los permisos a los que tiene acceso el rol.
- **Tareas: una**lista de asignaciones de roles que definen los usuarios que tienen los permisos configurados en el ámbito de las cuentas de recursos de la sala. Un rol puede tener varias asignaciones y un usuario puede estar en varias tareas.

## <a name="built-in-roles"></a>Roles integrados

Puede asignar roles integrados a grupos o usuarios sin más configuración. Tenga en cuenta que no puede eliminar ni modificar el nombre, la descripción, el tipo o los permisos de un rol integrado.

- **Administrador de servicios administrados**: tiene acceso completo al portal de servicio de Microsoft Teams Room Premium.
- **Responsable de sitio**: organiza salas, tiene acceso a informes y puede administrar vales. No se puede restablecer la clave de inscripción ni realizar cambios en la configuración del servicio.  
- **Tecnología del sitio**: administra vales para salas específicas. No tiene permisos para modificar el servicio u organizar salas en el servicio.

En la tabla siguiente se resume lo que puede hacer cada rol.

|Funciones |Permiso |Administrador de servicios administrados  |Responsable de sitio  |Tech del sitio  |
|---------|---------|---------|---------|---------|
|Descanso     |Ver        |&#10004;           |&#10004;           |&#10004;  |
|    |Cambiar         |&#10004;           |&#10004;           |&#10004; |
|    |Restablecer clave         |&#10004;           |         ||
|    |Descargar clave         |&#10004;           |&#10004;          |&#10004; |
|    |Anular inscripción         |&#10004;           |&#10004;           |&#10004; |
|Administración de grupos   |Crear         |&#10004;           |           ||
|    |Ver       |&#10004;          |&#10004;           ||
|    |Cambiar         |&#10004;           |           ||
|Actualizar la administración de timbre    |Crear         |&#10004;           |           ||
|    |Ver         |&#10004;           |           ||
|    |Cambiar         |&#10004;           |           ||
|Informar   |Ver        |&#10004;           |&#10004;           ||
|Administración de vales   |Crear incidente del cliente         |&#10004;           |&#10004;           |&#10004;  |
|    |Ver         |&#10004;           |&#10004;           |&#10004;  |
|    |Actualización         |&#10004;           |&#10004;           |&#10004;  |
|Configuración del servicio administrado de salas de Microsoft Teams    |Ver         |&#10004;           |         ||
|    |Cambiar        |&#10004;           |         ||
|Administración de roles    |Ver         |&#10004;           |         ||
|    |Cambiar         |&#10004;           |         ||

## <a name="assign-a-role"></a>Asignar un rol

Para asignar roles, debe ser administrador global o administrador de servicios administrados.

1. En el sitio de navegación izquierdo del portal de servicios administrados de Microsoft Team salas, vaya a roles de **configuración**  >  **Roles**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Captura de pantalla de la página de control de acceso que muestra roles":::

2. Seleccione el rol que desea asignar.
3. En el panel de roles, **Assignments**seleccione  >  **Agregar**tareas.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Captura de pantalla de la opción Agregar para agregar un rol.":::

4. En la página **Configuración general** , en **propiedades de asignación**, escriba un nombre para la tarea. La descripción es opcional. Elija **siguiente.**
5. En la página **miembros** , en el cuadro **Buscar un usuario o grupo de seguridad** , escriba el nombre de un usuario o grupo de seguridad de su inquilino al que desee conceder permisos y, a continuación, complete la selección. Elija **siguiente**. 
6. En la página **ámbito** , en el cuadro **Buscar sala o grupo de salas** , escriba el nombre de una sala o un grupo de sala que el usuario podrá administrar. Elija **siguiente**.
7. En la página **Finalizar** , revise los detalles de la asignación. Si está satisfecho con la configuración, elija **Agregar asignación**. Si desea modificar una sección, use el botón **anterior** o seleccione el paso del icono de navegación izquierdo.  

## <a name="related-topics"></a>Temas relacionados

- [Servicio administrado de salas de Microsoft Teams](microsoft-teams-rooms-premium.md)

---
title: Control de acceso basado en roles con el servicio Microsoft Teams Room Premium
author: dstrome
ms.author: dstrome
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
description: Obtenga información sobre el control de acceso basado en roles con el servicio administrado salas de Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: d673a20b122af876d95bac9d11a1db0433a396e4
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662605"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Control de acceso basado en roles con el servicio administrado salas de Microsoft Teams

El control de acceso basado en roles (RBAC) del servicio administrado Salas de Microsoft Teams le ayuda a administrar el acceso de los usuarios a los datos de recursos de salas de su organización. Al asignar roles a los usuarios del portal de servicios, puede limitar lo que pueden ver y cambiar. Cada rol tiene un conjunto de permisos que determinan a qué usuarios con ese rol pueden acceder y cambiar dentro de su organización.

Para crear, editar o asignar roles, su cuenta debe tener uno de los siguientes permisos:

- Administrador global a través de Azure Active Directory (Azure AD)
- Administrador de servicios administrados a través del portal de servicios administrados de Salas de Microsoft Teams

## <a name="what-is-a-role"></a>¿Qué es un rol?

Un rol define el conjunto de permisos concedidos a los usuarios asignados a ese rol. Por ahora, el servicio administrado por salas de Microsoft Teams tiene tres roles integrados: Administrador de servicios administrados, Cliente potencial del sitio y Técnico del **sitio.** Abarcan algunos escenarios comunes para los usuarios de su organización que pueden estar implicados en la administración de sus salas.

Para ver los roles, en el panel de navegación izquierdo del portal de servicios administrados de Salas de Microsoft Teams, vaya a **Roles** y, después, seleccione cualquiera de los roles para ver las propiedades, los permisos y las asignaciones del rol.  

- **Propiedades:** nombre, tipo de rol y descripción
- **Permisos:** enumera las características y el nivel de permisos a los que tiene acceso el rol.
- **Asignaciones:** una lista de asignaciones de roles que definen qué usuarios tienen los permisos configurados en el ámbito de las cuentas de recursos de sala. Un rol puede tener varias tareas y un usuario puede estar en varias tareas.

## <a name="built-in-roles"></a>Roles integrados

Puede asignar roles integrados a grupos o usuarios sin realizar más configuraciones. Tenga en cuenta que no puede eliminar o editar el nombre, la descripción, el tipo o los permisos de un rol integrado.

- **Administrador de servicios administrados:** tiene acceso total al portal de servicios de Microsoft Teams Room Premium.
- **Cliente potencial del** sitio: organiza salas, tiene acceso a informes y puede administrar vales. No se puede restablecer la clave de inscripción ni realizar cambios en la configuración del servicio.  
- **Tecnología del sitio:** administra vales para salas específicas. No tiene permisos para modificar el servicio o organizar salas en el servicio.

En la tabla siguiente se resume lo que puede hacer cada rol.

|Funciones |Permiso |Administrador de servicios administrados  |Cliente potencial del sitio  |Site Tech  |
|---------|---------|---------|---------|---------|
|Salas     |Ver        |&#10004;           |&#10004;           |&#10004;  |
|    |Modificar         |&#10004;           |&#10004;           |&#10004; |
|    |Tecla Restablecer         |&#10004;           |         ||
|    |Clave de descarga         |&#10004;           |&#10004;          |&#10004; |
|    |Desenrollar         |&#10004;           |&#10004;           |&#10004; |
|Administración de grupos   |Crear         |&#10004;           |           ||
|    |Ver       |&#10004;          |&#10004;           ||
|    |Modificar         |&#10004;           |           ||
|Actualizar la administración de anillos    |Crear         |&#10004;           |           ||
|    |Ver         |&#10004;           |           ||
|    |Modificar         |&#10004;           |           ||
|Informes   |Ver        |&#10004;           |&#10004;           ||
|Administración de vales   |Crear incidente del cliente         |&#10004;           |&#10004;           |&#10004;  |
|    |Ver         |&#10004;           |&#10004;           |&#10004;  |
|    |Actualización         |&#10004;           |&#10004;           |&#10004;  |
|Configuración del servicio administrado por salas de Microsoft Teams    |Ver         |&#10004;           |         ||
|    |Modificar        |&#10004;           |         ||
|Administración de roles    |Ver         |&#10004;           |         ||
|    |Modificar         |&#10004;           |         ||

## <a name="assign-a-role"></a>Asignar un rol

Para asignar roles, debe ser administrador global o administrador de servicios administrados.

1. En el panel de navegación izquierdo del portal de servicios administrados de Salas de Microsoft Teams, vaya a Roles **de**  >  **configuración.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Captura de pantalla de la página de control de Access que muestra los roles":::

2. Seleccione el rol que desea asignar.
3. En el panel de roles, seleccione **Tareas**  >  **agregar.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Captura de pantalla de la opción Agregar para agregar un rol.":::

4. En la **página Configuración general,** en **Propiedades de la tarea,** escriba un nombre para esta tarea. La descripción es opcional. Elija **Siguiente.**
5. En **la** página Miembros, en el cuadro Buscar usuario o grupo de seguridad, escriba el nombre de un usuario o grupo de seguridad en el espacio empresarial al que desea conceder permisos y, a continuación, complete la selección.  Elija **Siguiente.** 
6. En la **página** Ámbito, en el cuadro Buscar salón o grupo de salón, escriba el nombre de un salón o un grupo de salón que el usuario podrá administrar.  Elija **Siguiente.**
7. En la **página** Finalizar, revise los detalles de la tarea. Si está satisfecho con la configuración, elija **Agregar tarea.** Si desea editar una sección, use el **botón** Anterior o seleccione el paso en el panel de navegación izquierdo.  

## <a name="related-topics"></a>Temas relacionados

- [Servicio administrado por salas de Microsoft Teams](microsoft-teams-rooms-premium.md)

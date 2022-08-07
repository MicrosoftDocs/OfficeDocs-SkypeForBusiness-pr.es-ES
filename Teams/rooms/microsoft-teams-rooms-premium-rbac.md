---
title: Control de acceso basado en roles con el servicio Room Premium de Microsoft Teams
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
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre el control de acceso basado en roles con el servicio administrado de Salas de Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: 0edce289a23116ed76bf984bfc72724295fc5a5a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268365"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Control de acceso basado en roles con el servicio administrado Salas de Microsoft Teams

El control de acceso basado en roles (RBAC) en el servicio administrado de Salas de Microsoft Teams le ayuda a administrar el acceso de los usuarios a los datos de recursos de sala de su organización. Al asignar roles a los usuarios del portal de servicios, puede limitar lo que pueden ver y cambiar. Cada rol tiene un conjunto de permisos que determinan a qué usuarios con ese rol pueden acceder y cambiar dentro de su organización.

Para crear, editar o asignar roles, su cuenta debe tener uno de los siguientes permisos:

- Administrador global a través de Azure Active Directory (Azure AD)
- Administrador de servicios administrados a través del portal de servicios administrados de Salas de Microsoft Teams

## <a name="what-is-a-role"></a>¿Qué es un rol?

Un rol define el conjunto de permisos concedidos a los usuarios asignados a ese rol. Por ahora, el servicio administrado de Salas de Microsoft Teams tiene tres roles integrados: **administrador de servicios administrados**, **jefe de sitio** y **técnico del sitio**. Abarcan algunos escenarios comunes para los usuarios de su organización que pueden estar implicados en la administración de las salas.

Para ver los roles, en el panel de navegación izquierdo del Salas de Microsoft Teams portal de servicios administrados, vaya a **Roles** y, a continuación, seleccione cualquiera de los roles para ver las propiedades, los permisos y las asignaciones del rol.  

- **Propiedades**: nombre, tipo de rol y descripción
- **Permisos**: muestra las características y el nivel de permisos a los que tiene acceso el rol.
- **Asignaciones**: una lista de asignaciones de roles que definen qué usuarios tienen los permisos configurados sobre el ámbito de las cuentas de recursos de sala. Un rol puede tener varias asignaciones y un usuario puede estar en varias asignaciones.

## <a name="built-in-roles"></a>Roles integrados

Puede asignar roles integrados a grupos o usuarios sin más configuración. Tenga en cuenta que no puede eliminar ni editar el nombre, la descripción, el tipo o los permisos de un rol integrado.

- **Administrador de servicios administrados**: tiene acceso completo al portal de servicio de Salas Premium de Microsoft Teams.
- **Cliente potencial del sitio**: organiza salas, tiene acceso a informes y puede administrar entradas. No se puede restablecer la clave de inscripción ni realizar cambios en la configuración del servicio.  
- **Site Tech**: Administra las entradas para salas específicas. No tiene permisos para modificar el servicio ni para organizar salas en el servicio.

En la tabla siguiente se resume lo que puede hacer cada rol.

|Funciones |Permiso |Administrador de servicios administrados  |Cliente potencial del sitio  |Site Tech  |
|---------|---------|---------|---------|---------|
|Habitaciones     |Ver        |&#10004;           |&#10004;           |&#10004;  |
|    |Modificar         |&#10004;           |&#10004;           |&#10004; |
|    |Tecla Restablecer         |&#10004;           |         ||
|    |Clave de descarga         |&#10004;           |&#10004;          |&#10004; |
|    |Anular la inscripción         |&#10004;           |&#10004;           |&#10004; |
|Administración de grupos   |Crear         |&#10004;           |           ||
|    |Ver       |&#10004;          |&#10004;           ||
|    |Modificar         |&#10004;           |           ||
|Administración de anillos de actualización    |Crear         |&#10004;           |           ||
|    |Ver         |&#10004;           |           ||
|    |Modificar         |&#10004;           |           ||
|Informes   |Ver        |&#10004;           |&#10004;           ||
|Administración de vales   |Crear incidente de cliente         |&#10004;           |&#10004;           |&#10004;  |
|    |Ver         |&#10004;           |&#10004;           |&#10004;  |
|    |Actualización         |&#10004;           |&#10004;           |&#10004;  |
|configuración del servicio administrado Salas de Microsoft Teams    |Ver         |&#10004;           |         ||
|    |Modificar        |&#10004;           |         ||
|Administración de roles    |Ver         |&#10004;           |         ||
|    |Modificar         |&#10004;           |         ||

## <a name="create-a-custom-role"></a>Crear un rol personalizado

Si los roles integrados no se ajustan a sus necesidades de la organización, puede crear un rol y configurar sus permisos como desee. Para crear un rol, debe ser administrador global o administrador de servicios administrados. 

1. En el panel de navegación izquierdo del Salas de Microsoft Teams portal de servicios administrados, vaya a **Roles** **de configuración** > .
2. Seleccione **Crear rol**.
3. En la página **Configuración general** , en **Propiedades de rol**, escriba un nombre para este rol. En **Descripción**, escriba los detalles sobre este rol. Elija **Siguiente**.
4. En la página **Permisos** , en **Permisos de rol**, seleccione las casillas correspondientes para elegir los permisos para este rol. Elija **Siguiente** para crear la primera asignación para este rol.
5. En la página **Tareas** , en **Propiedades de la tarea**, escriba un nombre para esta tarea. La descripción es opcional. En **Configuración de notificaciones** , active la casilla **Notificaciones por correo electrónico** si los usuarios de este rol deben recibir notificaciones por correo electrónico del servicio en salas del **ámbito** de esta tarea. Elija **Siguiente**.
6. En la página **Miembros** , en el cuadro **Buscar usuario o grupo de seguridad** , escriba el nombre de un usuario o grupo de seguridad de su inquilino al que desea conceder permisos y, después, complete la selección. Elija **Siguiente**. 
7. En la página **Ámbito** , en el cuadro **de grupo Buscar salones o salones** , escriba el nombre de un salón o grupo de salones que el usuario podrá administrar. Elija **Siguiente**.
8. En la página **Finalizar** , revise los detalles del rol y la asignación. Si está satisfecho con la configuración, elija **Agregar nuevo rol**. Si desea editar una sección, use el botón **Anterior** o seleccione el paso en el panel de navegación izquierdo.  

## <a name="assign-a-role"></a>Asignar un rol

Para asignar roles, debe ser administrador global o administrador de servicios administrados o tener un rol con permisos de administración de roles.

1. En el panel de navegación izquierdo del Salas de Microsoft Teams portal de servicios administrados, vaya a **Roles** **de configuración** > .

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Captura de pantalla de la página de control de Access que muestra los roles.":::

2. Seleccione el rol que desea asignar.
3. En el panel de roles, seleccione **Agregar asignaciones** > .

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Captura de pantalla de la opción Agregar para agregar un rol.":::

4. En la página **Configuración general** , en **Propiedades de la tarea**, escriba un nombre para esta tarea. La descripción es opcional. En **Configuración de notificaciones**, active la casilla **Notificaciones por correo electrónico** si los usuarios de este rol deben recibir notificaciones por correo electrónico del servicio en salas del **ámbito** de esta asignación. Elija **Siguiente**. 
5. En la página **Miembros** , en el cuadro **Buscar usuario o grupo de seguridad** , escriba el nombre de un usuario o grupo de seguridad de su inquilino al que desea conceder permisos y, después, complete la selección. Elija **Siguiente**. 
6. En la página **Ámbito** , en el cuadro **de grupo Buscar salones o salones** , escriba el nombre de un salón o grupo de salones que el usuario podrá administrar. Elija **Siguiente**.
7. En la página **Finalizar** , revise los detalles de la tarea. Si está satisfecho con la configuración, elija **Agregar asignación**. Si desea editar una sección, use el botón **Anterior** o seleccione el paso en el panel de navegación izquierdo.  

## <a name="related-topics"></a>Temas relacionados

- [Salas de Microsoft Teams servicio administrado](microsoft-teams-rooms-premium.md)

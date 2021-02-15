---
title: Delegar el control administrativo de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: eb78fc7e0f831bae1c5dd6e207791e27aa4c68d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832800"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegar el control administrativo de Skype Empresarial Server 

En Skype Empresarial Server, las tareas administrativas se delegan a los usuarios mediante la característica de control de acceso basado en roles (RBAC). Al instalar Skype Empresarial Server, se crean varios roles RBAC automáticamente. Estos roles corresponden a grupos de seguridad universales en los Servicios de dominio de Active Directory. Por ejemplo, el rol RBAC CsHelpDesk corresponde al grupo CsHelpDesk que se encuentra en el contenedor Usuarios de los Servicios de dominio de Active Directory. Además, cada rol RBAC está asociado a un conjunto de cmdlets de Skype Empresarial Server Windows PowerShell específicos. Estos cmdlets representan las tareas que pueden llevar a cabo los usuarios que tienen asignado el rol RBAC determinado. Por ejemplo, el rol CsHelpDesk se ha asignado a los cmdlets Lock-CsClientPin y UnlockCsClientPin. Esto significa que los usuarios a los que se ha asignado el rol CsHelpDesk pueden bloquear y desbloquear números de PIN de usuario. Sin embargo, el rol CsHelpDesk no se ha asignado al New-CsVoicePolicy cmdlet. Esto significa que los usuarios a los que se ha asignado el rol CsHelpDesk no pueden crear nuevas directivas de voz.

## <a name="viewing-information-about-rbac-roles"></a>Ver información sobre los roles RBAC

Puede recuperar información básica sobre sus roles RBAC ejecutando el siguiente comando desde el Shell de administración de Skype Empresarial Server:

`Get-CsAdminRole`

Tenga en cuenta que la identidad del rol RBAC (por ejemplo, CsVoiceAdministrator) tiene una asignación directa a un grupo de seguridad que se encuentra en el contenedor Usuarios de los Servicios de dominio de Active Directory.

Para ver una lista de los cmdlets que se han asignado a un rol, use un comando similar al siguiente:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Asignación de un rol RBAC a un usuario

Para asignar un rol RBAC a un usuario, debe agregarlo al grupo de seguridad de Active Directory adecuado. Por ejemplo, para asignar el rol CsLocationAdministrator a un usuario, es necesario agregar a dicho usuario al grupo CsLocationAdministrator. Eso puede hacerse siguiendo el procedimiento siguiente:

1. Usar una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, iniciar sesión en un equipo en el que se haya instalado el complemento Usuarios y equipos de Active Directory.
2. Haga clic en **Inicio**, en **Todos los programas**, en **Herramientas administrativas** y después en **Usuarios y equipos de Active Directory**.
3. En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor **Usuarios**.
4. Haga clic con el botón secundario en el grupo de seguridad **CsLocationAdministrator** y, a continuación, seleccione **Propiedades**.
5. En el cuadro de diálogo **Propiedades**, en la pestaña **Miembros**, haga clic en **Agregar**.
6. En el cuadro de diálogo Seleccionar **usuarios, equipos,** contactos o grupos, escriba el nombre de usuario o el nombre  para mostrar del usuario que se agregará al grupo (por ejemplo, Ken Myer) en el cuadro Escribir los nombres de objeto que desea seleccionar y, a continuación, haga clic en **Aceptar**.
7. En el cuadro de diálogo **Propiedades**, haga clic en **Aceptar**.

Para verificar que el rol RBAC se ha asignado, use el cmdlet Get-CsAdminRoleAssignment y envíe al cmdlet el SamAccountName (nombre de inicio de sesión de Active Directory) del usuario. Por ejemplo, ejecute este comando desde el Shell de administración de Skype Empresarial Server:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`

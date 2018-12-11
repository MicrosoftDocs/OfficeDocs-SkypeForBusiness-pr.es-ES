---
title: Delegar el control administrativo de Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 6dbd254a96e4ffe961edc1a7d601870eb38b35db
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222901"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegar el control administrativo de Skype para Business Server 

En Skype para Business Server, se delegan las tareas administrativas a los usuarios mediante el uso de la característica de acceso basado en roles (RBAC) del control. Al instalar Skype para Business Server, se crea un número de funciones de RBAC para usted. Estos roles corresponden a los grupos de seguridad universal de los Servicios de dominio de Active Directory. Por ejemplo, el rol RBAC CsHelpDesk corresponde al grupo CsHelpDesk que se encuentran en el contenedor de usuarios en servicios de dominio de Active Directory. Además, cada rol RBAC está asociado con un conjunto de Skype para cmdlets de Windows PowerShell de Business Server. Estos cmdlets representan las tareas que pueden llevarse a cabo por los usuarios que se ha asignado el rol RBAC determinado. Por ejemplo, le ha asignado el rol CsHelpDesk los cmdlets de UnlockCsClientPin y Lock-CsClientPin. Esto significa que los usuarios que tengan asignados al rol CsHelpDesk pueden bloquear y desbloquear los números PIN de usuario. Sin embargo, la función CsHelpDesk no se ha asignado el cmdlet New-CsVoicePolicy. Esto significa que los usuarios que tengan asignados al rol CsHelpDesk no pueden crear nuevas directivas de voz.

## <a name="viewing-information-about-rbac-roles"></a>Visualización de la información acerca de las funciones RBAC

Puede recuperar información básica sobre sus roles RBAC si ejecuta el siguiente comando desde dentro de la Skype para Shell de administración de servidor empresarial:

`Get-CsAdminRole`

Tenga en cuenta que la identidad de un rol RBAC (por ejemplo, CsVoiceAdministrator) tiene una asignación directa a un grupo de seguridad que se encuentran en el contenedor de usuarios en servicios de dominio de Active Directory.

Para ver una lista de los cmdlets que se han asignado a un rol, use un comando similar al siguiente:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Asignar un rol RBAC a un usuario

Para asignar un rol RBAC a un usuario, debe agregar ese usuario al grupo de seguridad de Active Directory adecuado. Por ejemplo, para asignar el rol CsLocationAdministrator a un usuario, debe agregar ese usuario al grupo CsLocationAdministrator. Que pueden hacerse por llevar a cabo el procedimiento siguiente:

1. Con una cuenta que tiene permiso para modificar la pertenencia de un grupo de Active Directory, inicie sesión en un equipo donde se ha instalado equipos y usuarios de Active Directory.
2. Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Herramientas administrativas**y, a continuación, haga clic en **usuarios y equipos de usuarios de Active Directory**.
3. En usuarios de Active Directory y los equipos, expanda el nombre de su dominio y haga clic en el contenedor **usuarios** .
4. Haga clic en el grupo de seguridad **CsLocationAdministrator**y, a continuación, haga clic en **Propiedades**.
5. En el cuadro de diálogo **Propiedades** , en la ficha **miembros** , haga clic en **Agregar**.
6. En el cuadro de diálogo **Seleccionar usuarios, equipos, contactos o grupos** , escriba el nombre de usuario o nombre para mostrar del usuario que se agregará al grupo (por ejemplo, Ken Myer) en el cuadro **Escriba los nombres de objeto para seleccionar** y, a continuación, haga clic en **Aceptar**.
7. En el cuadro de diálogo **Propiedades** , haga clic en **Aceptar**.

Para comprobar que se ha asignado el rol RBAC, use el cmdlet Get-CsAdminRoleAssignment, pasando el cmdlet SamAccountName (nombre de inicio de sesión de Active Directory) del usuario. Por ejemplo, ejecute este comando desde dentro de la Skype para Shell de administración de servidor empresarial:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
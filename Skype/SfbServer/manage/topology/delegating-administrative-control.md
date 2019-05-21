---
title: Delegar el control administrativo de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 1775fc4f02b7efa9ec26b962154f0aa90b59b296
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279210"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegar el control administrativo de Skype empresarial Server 

En Skype empresarial Server, las tareas administrativas se delegan a los usuarios mediante la característica de control de acceso basado en roles (RBAC). Al instalar Skype empresarial Server, se crea una serie de roles RBAC. Estos roles corresponden a los grupos de seguridad universal de los Servicios de dominio de Active Directory. Por ejemplo, el rol de RBAC CsHelpDesk se corresponde con el grupo CsHelpDesk que se encuentra en el contenedor usuarios de los servicios de dominio de Active Directory. Además, cada rol de RBAC está asociado a un conjunto de cmdlets de Windows PowerShell de Skype empresarial Server. Estos cmdlets representan las tareas que pueden realizar los usuarios a los que se les haya asignado el rol de RBAC determinado. Por ejemplo, a la función CsHelpDesk se le ha asignado el cmdlet Lock-CsClientPin y UnlockCsClientPin. Eso significa que los usuarios a los que se les ha asignado el rol de CsHelpDesk pueden bloquear y desbloquear números de PIN de usuario. Sin embargo, el rol CsHelpDesk no se ha asignado al cmdlet New-CsVoicePolicy. Eso significa que los usuarios a los que se les ha asignado el rol de CsHelpDesk no pueden crear directivas de voz nuevas.

## <a name="viewing-information-about-rbac-roles"></a>Ver información sobre los roles de RBAC

Puede recuperar información básica sobre los roles de RBAC ejecutando el siguiente comando desde el shell de administración de Skype empresarial Server:

`Get-CsAdminRole`

Tenga en cuenta que la identidad del rol RBAC (por ejemplo, CsVoiceAdministrator) tiene una asignación directa a un grupo de seguridad que se encuentra en el contenedor usuarios de servicios de dominio de Active Directory.

Para ver una lista de los cmdlets que se han asignado a un rol, use un comando similar a este:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Asignación de un rol de RBAC a un usuario

Para asignar un rol de RBAC a un usuario, debe agregar ese usuario al grupo de seguridad de Active Directory correspondiente. Por ejemplo, para asignar el rol CsLocationAdministrator a un usuario, debe agregar ese usuario al grupo CsLocationAdministrator. Esto se puede llevar a cabo mediante el siguiente procedimiento:

1. Con una cuenta que tenga permiso para modificar la pertenencia de un grupo de Active Directory, inicie sesión en un equipo en el que se hayan instalado usuarios y equipos de Active Directory.
2. Haga clic en **Inicio**, seleccione **todos los programas**, **herramientas administrativas**y, a continuación, haga clic en **usuarios y equipos de Active**Directory.
3. En usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor **usuarios** .
4. Haga clic con el botón secundario en el grupo de seguridad **CsLocationAdministrator**y haga clic en **propiedades**.
5. En el cuadro de diálogo **propiedades** , en la pestaña **miembros** , haga clic en **Agregar**.
6. En el cuadro de diálogo **Seleccionar usuarios, equipos, contactos o grupos** , escriba el nombre de usuario o el nombre para mostrar del usuario que se va a agregar al grupo (por ejemplo, Ken Myer) en el cuadro **Escriba los nombres de objeto que desea seleccionar** y, a continuación, haga clic en **Aceptar**.
7. En el cuadro de diálogo **propiedades** , haga clic en **Aceptar**.

Para comprobar que se ha asignado el rol RBAC, use el cmdlet Get-CsAdminRoleAssignment y pase el cmdlet como SamAccountName (nombre de inicio de sesión de Active Directory) del usuario. Por ejemplo, ejecute este comando desde el shell de administración de Skype empresarial Server:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`

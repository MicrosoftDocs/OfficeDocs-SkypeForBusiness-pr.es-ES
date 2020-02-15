---
title: 'Lync Server 2013: Delegación del control administrativo de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 028921122b0198e85e7cc95df97355908f517894
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>Delegación del control administrativo de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

En Lync Server 2013, las tareas administrativas se delegan a los usuarios con la nueva característica de control de acceso basado en roles (RBAC). Al instalar Lync Server, se crea una serie de roles RBAC. Estos roles corresponden a los grupos de seguridad universal de servicios de dominio de Active Directory. Por ejemplo, el rol de RBAC CsHelpDesk corresponde al grupo CsHelpDesk que se encuentra en el contenedor usuarios de los servicios de dominio de Active Directory. Además, cada rol RBAC está asociado a un conjunto de cmdlets de Windows PowerShell de Lync Server. Estos cmdlets representan las tareas que pueden realizar los usuarios a los que se les ha asignado el rol RBAC especificado. Por ejemplo, al rol CsHelpDesk se le han asignado los cmdlets Lock-CsClientPin y UnlockCsClientPin. Esto significa que los usuarios a los que se les asignó el rol CsHelpDesk pueden bloquear y desbloquear los números de PIN de los usuarios. Sin embargo, el rol CsHelpDesk no se ha asignado al cmdlet New-CsVoicePolicy. Esto significa que los usuarios a los que se les ha asignado el rol CsHelpDesk no pueden crear nuevas directivas de voz.

<div>

## <a name="viewing-information-about-rbac-roles"></a>Visualización de información sobre los roles RBAC

Puede recuperar la información básica de los roles RBAC ejecutando el siguiente comando desde el shell de administración de Lync Server:

    Get-CsAdminRole

Tenga en cuenta que la identidad del rol RBAC (por ejemplo, CsVoiceAdministrator) tiene una asignación directa a un grupo de seguridad que se encuentra en el contenedor usuarios de servicios de dominio de Active Directory.

Para ver una lista de los cmdlets que se han asignado a un rol, use un comando similar al siguiente:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>Asignación de un rol RBAC a un usuario

Para asignar un rol RBAC a un usuario, debe agregar ese usuario al grupo de seguridad de Active Directory correspondiente. Por ejemplo, para asignar el rol CsLocationAdministrator a un usuario, es necesario agregar a dicho usuario al grupo CsLocationAdministrator. Eso puede hacerse siguiendo el procedimiento siguiente:

**Asignar un usuario a un grupo de seguridad**

1.  Usar una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, iniciar sesión en un equipo en el que se haya instalado el complemento Usuarios y equipos de Active Directory.

2.  Haga clic en **Inicio**, en **Todos los programas**, en **Herramientas administrativas** y después en **Usuarios y equipos de Active Directory**.

3.  En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor **Usuarios**.

4.  Haga clic con el botón secundario en el grupo de seguridad **CsLocationAdministrator** y, a continuación, seleccione **Propiedades**.

5.  En el cuadro de diálogo **Propiedades**, en la pestaña **Miembros**, haga clic en **Agregar**.

6.  En el cuadro de diálogo **Seleccionar usuarios, equipos, contactos o grupos**, escriba el nombre del usuario o el nombre para mostrar del usuario que se desea agregar al grupo (por ejemplo, **Ken Myer**) en el cuadro **Escribir los nombres de objeto para seleccionar** y después haga clic en **Aceptar**.

7.  En el cuadro de diálogo **Propiedades**, haga clic en **Aceptar**.

Para verificar que el rol RBAC se ha asignado, use el cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) y envíe al cmdlet el SamAccountName (nombre de inicio de sesión de Active Directory) del usuario. Por ejemplo, ejecute este comando desde el shell de administración de Lync Server:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>


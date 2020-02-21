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
ms.openlocfilehash: e93985818c62b195227323f4c0f6d5030db1f16f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="4953a-102">Delegación del control administrativo de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4953a-102">Delegating administrative control of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4953a-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4953a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4953a-104">En Lync Server 2013, las tareas administrativas se delegan a los usuarios con la nueva característica de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="4953a-104">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="4953a-105">Al instalar Lync Server, se crea una serie de roles RBAC.</span><span class="sxs-lookup"><span data-stu-id="4953a-105">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="4953a-106">Estos roles corresponden a los grupos de seguridad universal de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4953a-106">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="4953a-107">Por ejemplo, el rol de RBAC CsHelpDesk corresponde al grupo CsHelpDesk que se encuentra en el contenedor usuarios de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4953a-107">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="4953a-108">Además, cada rol RBAC está asociado a un conjunto de cmdlets de Windows PowerShell de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4953a-108">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4953a-109">Estos cmdlets representan las tareas que pueden realizar los usuarios a los que se les ha asignado el rol RBAC especificado.</span><span class="sxs-lookup"><span data-stu-id="4953a-109">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="4953a-110">Por ejemplo, al rol CsHelpDesk se le han asignado los cmdlets Lock-CsClientPin y UnlockCsClientPin.</span><span class="sxs-lookup"><span data-stu-id="4953a-110">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="4953a-111">Esto significa que los usuarios a los que se les asignó el rol CsHelpDesk pueden bloquear y desbloquear los números de PIN de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4953a-111">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="4953a-112">Sin embargo, el rol CsHelpDesk no se ha asignado al cmdlet New-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="4953a-112">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="4953a-113">Esto significa que los usuarios a los que se les ha asignado el rol CsHelpDesk no pueden crear nuevas directivas de voz.</span><span class="sxs-lookup"><span data-stu-id="4953a-113">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="4953a-114">Visualización de información sobre los roles RBAC</span><span class="sxs-lookup"><span data-stu-id="4953a-114">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="4953a-115">Puede recuperar la información básica de los roles RBAC ejecutando el siguiente comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4953a-115">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="4953a-116">Tenga en cuenta que la identidad del rol RBAC (por ejemplo, CsVoiceAdministrator) tiene una asignación directa a un grupo de seguridad que se encuentra en el contenedor usuarios de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4953a-116">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="4953a-117">Para ver una lista de los cmdlets que se han asignado a un rol, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4953a-117">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="4953a-118">Asignación de un rol RBAC a un usuario</span><span class="sxs-lookup"><span data-stu-id="4953a-118">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="4953a-119">Para asignar un rol RBAC a un usuario, debe agregar ese usuario al grupo de seguridad de Active Directory correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4953a-119">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="4953a-120">Por ejemplo, para asignar el rol CsLocationAdministrator a un usuario, es necesario agregar a dicho usuario al grupo CsLocationAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4953a-120">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="4953a-121">Eso puede hacerse siguiendo el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="4953a-121">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="4953a-122">**Asignar un usuario a un grupo de seguridad**</span><span class="sxs-lookup"><span data-stu-id="4953a-122">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="4953a-123">Usar una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, iniciar sesión en un equipo en el que se haya instalado el complemento Usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4953a-123">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="4953a-124">Haga clic en **Inicio**, en **Todos los programas**, en **Herramientas administrativas** y después en **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4953a-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="4953a-125">En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4953a-125">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="4953a-126">Haga clic con el botón secundario en el grupo de seguridad **CsLocationAdministrator** y, a continuación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4953a-126">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="4953a-127">En el cuadro de diálogo **Propiedades**, en la pestaña **Miembros**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4953a-127">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="4953a-128">En el cuadro de diálogo **Seleccionar usuarios, equipos, contactos o grupos**, escriba el nombre del usuario o el nombre para mostrar del usuario que se desea agregar al grupo (por ejemplo, **Ken Myer**) en el cuadro **Escribir los nombres de objeto para seleccionar** y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4953a-128">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="4953a-129">En el cuadro de diálogo **Propiedades**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4953a-129">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="4953a-130">Para verificar que el rol RBAC se ha asignado, use el cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) y envíe al cmdlet el SamAccountName (nombre de inicio de sesión de Active Directory) del usuario.</span><span class="sxs-lookup"><span data-stu-id="4953a-130">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="4953a-131">Por ejemplo, ejecute este comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="4953a-131">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Delegación del control administrativo de Lync Server'
description: 'Lync Server 2013: Delegación del control administrativo de Lync Server.'
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
ms.openlocfilehash: a8d3710af2d194a5aa4ebdd7291be2ee58176507
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567496"
---
# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="51813-103">Delegación del control administrativo de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51813-103">Delegating administrative control of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51813-104">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="51813-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="51813-105">En Lync Server 2013, las tareas administrativas se delegan a los usuarios con la nueva característica de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="51813-105">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="51813-106">Al instalar Lync Server, se crea una serie de roles RBAC.</span><span class="sxs-lookup"><span data-stu-id="51813-106">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="51813-107">Estos roles corresponden a los grupos de seguridad universal de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51813-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="51813-108">Por ejemplo, el rol de RBAC CsHelpDesk corresponde al grupo CsHelpDesk que se encuentra en el contenedor usuarios de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51813-108">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="51813-109">Además, cada rol RBAC está asociado a un conjunto de cmdlets de Windows PowerShell de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="51813-109">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="51813-110">Estos cmdlets representan las tareas que pueden realizar los usuarios a los que se les ha asignado el rol RBAC especificado.</span><span class="sxs-lookup"><span data-stu-id="51813-110">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="51813-111">Por ejemplo, a la función CsHelpDesk se le han asignado los cmdlets Lock-CsClientPin y UnlockCsClientPin.</span><span class="sxs-lookup"><span data-stu-id="51813-111">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="51813-112">Esto significa que los usuarios a los que se les asignó el rol CsHelpDesk pueden bloquear y desbloquear los números de PIN de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="51813-112">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="51813-113">Sin embargo, el rol CsHelpDesk no tiene asignado el cmdlet New-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="51813-113">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="51813-114">Esto significa que los usuarios a los que se les ha asignado el rol CsHelpDesk no pueden crear nuevas directivas de voz.</span><span class="sxs-lookup"><span data-stu-id="51813-114">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="51813-115">Visualización de información sobre los roles RBAC</span><span class="sxs-lookup"><span data-stu-id="51813-115">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="51813-116">Puede recuperar la información básica de los roles RBAC ejecutando el siguiente comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="51813-116">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="51813-117">Tenga en cuenta que la identidad del rol RBAC (por ejemplo, CsVoiceAdministrator) tiene una asignación directa a un grupo de seguridad que se encuentra en el contenedor usuarios de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51813-117">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="51813-118">Para ver una lista de los cmdlets que se han asignado a un rol, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="51813-118">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="51813-119">Asignación de un rol RBAC a un usuario</span><span class="sxs-lookup"><span data-stu-id="51813-119">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="51813-120">Para asignar un rol RBAC a un usuario, debe agregar ese usuario al grupo de seguridad de Active Directory correspondiente.</span><span class="sxs-lookup"><span data-stu-id="51813-120">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="51813-121">Por ejemplo, para asignar el rol CsLocationAdministrator a un usuario, es necesario agregar a dicho usuario al grupo CsLocationAdministrator.</span><span class="sxs-lookup"><span data-stu-id="51813-121">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="51813-122">Eso puede hacerse siguiendo el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="51813-122">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="51813-123">**Asignar un usuario a un grupo de seguridad**</span><span class="sxs-lookup"><span data-stu-id="51813-123">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="51813-124">Usar una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, iniciar sesión en un equipo en el que se haya instalado el complemento Usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51813-124">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="51813-125">Haga clic en **Inicio**, en **Todos los programas**, en **Herramientas administrativas** y después en **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="51813-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="51813-126">En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="51813-126">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="51813-127">Haga clic con el botón secundario en el grupo de seguridad **CsLocationAdministrator** y, a continuación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="51813-127">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="51813-128">En el cuadro de diálogo **Propiedades**, en la pestaña **Miembros**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="51813-128">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="51813-129">En el cuadro de diálogo **Seleccionar usuarios, equipos, contactos o grupos**, escriba el nombre del usuario o el nombre para mostrar del usuario que se desea agregar al grupo (por ejemplo, **Ken Myer**) en el cuadro **Escribir los nombres de objeto para seleccionar** y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="51813-129">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="51813-130">En el cuadro de diálogo **Propiedades**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="51813-130">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="51813-131">Para verificar que el rol RBAC se ha asignado, use el cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) y envíe al cmdlet el SamAccountName (nombre de inicio de sesión de Active Directory) del usuario.</span><span class="sxs-lookup"><span data-stu-id="51813-131">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="51813-132">Por ejemplo, ejecute este comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="51813-132">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>


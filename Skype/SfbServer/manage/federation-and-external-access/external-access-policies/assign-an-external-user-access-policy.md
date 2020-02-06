---
title: Asignar una directiva de acceso de usuario externo
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si se ha habilitado un usuario en Skype empresarial Server, puede configurar la Federación SIP, el acceso de usuarios remotos y la conectividad de mensajería instantánea (mi) pública en el panel de control de Skype empresarial Server aplicando las directivas apropiadas a usuarios específicos.
ms.openlocfilehash: b87eb377b23063dbcdfd9562a99533da230a8f30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818331"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="b3eac-103">Asignar una directiva de acceso de usuarios externos a un usuario habilitado para Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="b3eac-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="b3eac-104">Si se ha habilitado un usuario en Skype empresarial Server, puede configurar la Federación SIP, el acceso de usuarios remotos y la conectividad de mensajería instantánea (mi) pública en el panel de control de Skype empresarial Server aplicando las directivas apropiadas a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="b3eac-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="b3eac-105">Por ejemplo, si creó una directiva para admitir el acceso de usuarios remotos, debe aplicarla al usuario antes de que el usuario pueda conectarse a Skype empresarial Server desde una ubicación remota y colaborar con usuarios internos desde la ubicación remota.</span><span class="sxs-lookup"><span data-stu-id="b3eac-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="b3eac-106">Para admitir el acceso de usuarios externos, debe habilitar la compatibilidad para cada tipo de acceso de usuario externo que desee admitir, así como configurar las directivas apropiadas y otras opciones para controlar su uso.</span><span class="sxs-lookup"><span data-stu-id="b3eac-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="b3eac-107">Para obtener más información, consulte [administrar la Federación y el acceso externo a Skype empresarial Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="b3eac-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="b3eac-108">Use el procedimiento de este tema para aplicar una directiva de acceso de usuarios externos creada previamente a una o más cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="b3eac-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="b3eac-109">Para aplicar una directiva de usuario externo a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="b3eac-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="b3eac-110">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b3eac-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b3eac-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b3eac-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b3eac-112">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="b3eac-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="b3eac-113">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="b3eac-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b3eac-114">En **Editar usuario de Skype empresarial Server** , en **Directiva de acceso externo**, seleccione la Directiva de usuario que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="b3eac-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="b3eac-115">La configuración de \*\* \<>automático\*\* aplica el servidor predeterminado o la configuración de la directiva global.</span><span class="sxs-lookup"><span data-stu-id="b3eac-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b3eac-116">Asignar directivas de acceso externo por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3eac-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b3eac-117">Las directivas de acceso externo por usuario se pueden asignar mediante Windows PowerShell y el cmdlet Grant-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="b3eac-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="b3eac-118">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3eac-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="b3eac-119">Para asignar una directiva de acceso externo por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="b3eac-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="b3eac-120">Este comando asigna el RedmondExternalAccessPolicy de directiva de acceso externo por usuario al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b3eac-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="b3eac-121">Para asignar una directiva de acceso externo por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="b3eac-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="b3eac-122">Este comando asigna el USAExternalAccessPolicy de directiva de acceso externo por usuario a todos los usuarios que tienen cuentas en la OU de Estados Unidos en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b3eac-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="b3eac-123">Para obtener más información sobre el parámetro de Uo que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="b3eac-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="b3eac-124">Para cancelar la asignación de una directiva de acceso externo por usuario</span><span class="sxs-lookup"><span data-stu-id="b3eac-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="b3eac-125">Este comando elimina la asignación de una directiva de acceso externo por usuario asignada previamente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b3eac-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="b3eac-126">Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b3eac-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="b3eac-127">La directiva de sitio tiene prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="b3eac-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="b3eac-128">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="b3eac-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>



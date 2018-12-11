---
title: Asignar una directiva de acceso de usuarios externos
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un usuario tiene habilitado para Skype para Business Server, puede configurar la federación SIP, acceso de usuarios remotos e instantánea pública conectividad de mensajería (IM en el Skype) para el Panel de Control de servidor empresarial mediante la aplicación de las directivas apropiadas a usuarios específicos.
ms.openlocfilehash: 3498b7aabaddc80053efca70b89198c224147c0e
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222845"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="bd212-103">Asignar una directiva de acceso de usuarios externos a un Skype para usuarios de empresa habilitado</span><span class="sxs-lookup"><span data-stu-id="bd212-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="bd212-104">Si un usuario tiene habilitado para Skype para Business Server, puede configurar la federación SIP, acceso de usuarios remotos e instantánea pública conectividad de mensajería (IM en el Skype) para el Panel de Control de servidor empresarial mediante la aplicación de las directivas apropiadas a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="bd212-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="bd212-105">Por ejemplo, si ha creado una directiva para permitir el acceso de usuarios remotos, se debe aplicar al usuario antes de que el usuario puede conectarse a Skype para Business Server desde una ubicación remota y colaborar con los usuarios internos de la ubicación remota.</span><span class="sxs-lookup"><span data-stu-id="bd212-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="bd212-106">Para permitir el acceso de usuarios externos, debe habilitar la compatibilidad con cada tipo de acceso de usuarios externos que desea admitir y configurar las directivas apropiadas y otras opciones para controlar su uso.</span><span class="sxs-lookup"><span data-stu-id="bd212-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="bd212-107">Para obtener información detallada, vea [Managing federación y el acceso externo a Skype para Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="bd212-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="bd212-108">Use el procedimiento de este tema para aplicar una directiva de acceso de usuarios externos creada previamente a una o más cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="bd212-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="bd212-109">Para aplicar una directiva de usuario externo a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="bd212-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="bd212-110">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="bd212-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bd212-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="bd212-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="bd212-112">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="bd212-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="bd212-113">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, finalmente, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="bd212-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="bd212-114">En **Editar Skype para usuarios de empresa Server** en **Directiva de acceso externo**, seleccione la directiva de usuario que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="bd212-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="bd212-115">La \*\* \<automática >\*\* configuración aplica el servidor predeterminado o la configuración de la directiva global.</span><span class="sxs-lookup"><span data-stu-id="bd212-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bd212-116">Asignación de directivas de acceso externo por usuario mediante el uso de Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd212-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bd212-117">Directivas de acceso externo por usuario pueden asignarse mediante el uso de Windows PowerShell y el cmdlet Grant-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="bd212-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="bd212-118">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd212-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="bd212-119">Para asignar una directiva de acceso externo por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="bd212-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="bd212-120">Este comando asigna la directiva de acceso externo por usuario RedmondExternalAccessPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="bd212-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="bd212-121">Para asignar una directiva de acceso externo por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="bd212-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="bd212-122">Este comando asigna la directiva de acceso externo por usuario USAExternalAccessPolicy a todos los usuarios que tienen cuentas en la unidad organizativa de Estados Unidos en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bd212-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="bd212-123">Para obtener más información sobre el parámetro de unidad organizativa que se usa en este comando, consulte la documentación para el cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="bd212-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="bd212-124">Para cancelar la asignación de una directiva de acceso externo por usuario</span><span class="sxs-lookup"><span data-stu-id="bd212-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="bd212-125">Este comando anula la asignación de cualquier directiva de acceso externo por usuario previamente asignada a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="bd212-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="bd212-126">Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="bd212-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="bd212-127">La directiva de sitio tiene prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="bd212-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="bd212-128">Para obtener más información, vea el tema de ayuda para el cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="bd212-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>



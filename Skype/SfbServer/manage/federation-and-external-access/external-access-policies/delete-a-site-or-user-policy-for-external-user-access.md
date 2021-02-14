---
title: Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede eliminar cualquier directiva de sitio o usuario que aparezca en el Panel de control de Skype Empresarial Server en la página Directiva de acceso externo.
ms.openlocfilehash: 0fbde98868bfe7f8dbe9f97db2350e02dba44560
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817280"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="0102d-103">Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="0102d-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="0102d-104">Si ha creado o configurado directivas de acceso de usuarios externos que ya no desea usar, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0102d-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="0102d-105">Elimine cualquier directiva de usuario o sitio que haya creado.</span><span class="sxs-lookup"><span data-stu-id="0102d-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="0102d-p101">Restablezca la configuración predeterminada de la directiva global. La configuración global predeterminada deniega cualquier tipo de acceso de usuarios externos. La directiva global no puede eliminarse.</span><span class="sxs-lookup"><span data-stu-id="0102d-p101">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>


<span data-ttu-id="0102d-109">Puede eliminar cualquier directiva de sitio o usuario que aparezca en el Panel de control de Skype Empresarial Server en la **página Directiva de acceso** externo.</span><span class="sxs-lookup"><span data-stu-id="0102d-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="0102d-110">La eliminación de la directiva global no la elimina realmente, sino que solo la restablece según la configuración predeterminada, que no incluye compatibilidad con opciones de acceso para usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="0102d-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="0102d-111">Para obtener más información acerca del restablecimiento de la directiva global, vea Restablecer la directiva [global para el acceso de usuarios externos.](reset-the-global-policy-for-external-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="0102d-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="0102d-112">Para eliminar una directiva de sitio o usuario para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="0102d-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="0102d-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0102d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0102d-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0102d-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0102d-115">Haga clic en **Acceso de usuarios externos** y seleccione **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="0102d-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="0102d-116">En la ficha **Directiva de acceso externo**, haga clic en la directiva de sitio o usuario que desea eliminar, seleccione **Editar** y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0102d-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="0102d-117">Cuando se le solicite que confirme la eliminación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0102d-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0102d-118">Quitar directivas de PIN mediante cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0102d-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0102d-119">Las directivas de acceso externo se pueden eliminar mediante Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy externo.</span><span class="sxs-lookup"><span data-stu-id="0102d-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="0102d-120">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0102d-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="0102d-121">Para quitar una directiva de acceso externo específica</span><span class="sxs-lookup"><span data-stu-id="0102d-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="0102d-122">Con este comando se quita la directiva de acceso externo aplicada al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="0102d-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="0102d-123">Para quitar todas las directivas de acceso externo aplicadas al ámbito por usuario</span><span class="sxs-lookup"><span data-stu-id="0102d-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="0102d-124">Con este comando se quitan todas las directivas de acceso externo configuradas en el ámbito por usuario:</span><span class="sxs-lookup"><span data-stu-id="0102d-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="0102d-125">Para quitar todas las directivas de acceso externo en las que el acceso de usuarios externos está deshabilitado</span><span class="sxs-lookup"><span data-stu-id="0102d-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="0102d-126">Con este comando se quitan todas las directivas de acceso externo cuando el acceso de usuarios externos se ha deshabilitado:</span><span class="sxs-lookup"><span data-stu-id="0102d-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="0102d-127">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsExternalAccessPolicy.](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="0102d-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

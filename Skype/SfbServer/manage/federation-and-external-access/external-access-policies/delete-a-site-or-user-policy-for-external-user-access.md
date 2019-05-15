---
title: Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede eliminar cualquier directiva de sitio o de usuario que aparece en el Skype para el Panel de Control de Business Server en la página Directiva de acceso externo.
ms.openlocfilehash: 517c5b015d4e2fe5de584a8079af1bb4f5ed248a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920420"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="1df91-103">Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="1df91-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="1df91-104">Si ha creado o configurado las directivas de acceso de usuarios externos que ya no desea usar, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1df91-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="1df91-105">Elimine cualquier directiva de sitio o de usuario que ha creado.</span><span class="sxs-lookup"><span data-stu-id="1df91-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="1df91-106">Restablecer la directiva global para la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1df91-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="1df91-107">La configuración de la directiva global predeterminada denegar el acceso de los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="1df91-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="1df91-108">No se puede eliminar la directiva global.</span><span class="sxs-lookup"><span data-stu-id="1df91-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="1df91-109">Puede eliminar cualquier directiva de sitio o de usuario que aparece en el Skype para el Panel de Control de Business Server en la página **Directiva de acceso externo** .</span><span class="sxs-lookup"><span data-stu-id="1df91-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="1df91-110">Eliminación de la directiva global, no elimina realmente, pero sólo restablece la configuración predeterminada, que no incluye compatibilidad con las opciones de acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="1df91-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="1df91-111">Para obtener más información acerca del restablecimiento de la directiva global, consulte [Restablecer la directiva global para el acceso de usuarios externos](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1df91-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="1df91-112">Para eliminar una directiva de sitio o usuario para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="1df91-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="1df91-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1df91-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1df91-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="1df91-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1df91-115">Haga clic en **Acceso de usuarios externos**, haga clic en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="1df91-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="1df91-116">En la ficha **Directiva de acceso externo** , haga clic en la directiva de sitio o usuario que desea eliminar, haga clic en **Editar**y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="1df91-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="1df91-117">Cuando se le pida que confirme la eliminación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1df91-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1df91-118">Eliminación de directivas de PIN mediante el uso de Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1df91-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1df91-119">Directivas de acceso externo se pueden eliminar mediante el uso de Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="1df91-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="1df91-120">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1df91-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="1df91-121">Para quitar una directiva de acceso externo determinada</span><span class="sxs-lookup"><span data-stu-id="1df91-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="1df91-122">Este comando quita la directiva de acceso externo aplicada al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="1df91-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="1df91-123">Para quitar todas las externos obtener acceso a las directivas que se aplican al ámbito por usuario</span><span class="sxs-lookup"><span data-stu-id="1df91-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="1df91-124">Este comando quita todas las directivas de acceso externo configuradas en el ámbito por usuario:</span><span class="sxs-lookup"><span data-stu-id="1df91-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="1df91-125">Para quitar todas las directivas de acceso externo donde se deshabilita el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="1df91-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="1df91-126">Este comando elimina todas las directivas de acceso externo donde usuarios externos acceso se ha deshabilitado:</span><span class="sxs-lookup"><span data-stu-id="1df91-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="1df91-127">Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="1df91-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

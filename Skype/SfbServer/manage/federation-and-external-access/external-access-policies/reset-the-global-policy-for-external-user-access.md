---
title: Restablecer la directiva global para el acceso de usuarios externos
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Completamente, no se puede eliminar una directiva global. Con la opción **Eliminar** en la directiva global, sólo restablece la directiva global para la configuración predeterminada, que no incluye compatibilidad con las opciones de acceso de usuarios externos.
ms.openlocfilehash: 048d1f1aabd2e188cefa25358068ea6ec150b8f3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877877"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="ae8a3-104">Restablecer la directiva global para el acceso de usuarios externos en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="ae8a3-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="ae8a3-105">Si ha creado o configurado las directivas de acceso de usuarios externos que ya no desea usar, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae8a3-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="ae8a3-106">Elimine cualquier directiva de sitio o de usuario que ha creado.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="ae8a3-107">Restablecer la directiva global para la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="ae8a3-108">La configuración de la directiva global predeterminada denegar el acceso de los usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="ae8a3-109">No se puede eliminar la directiva global.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="ae8a3-110">Completamente, no se puede eliminar una directiva global.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="ae8a3-111">Con la opción **Eliminar** en la directiva global, sólo restablece la directiva global para la configuración predeterminada, que no incluye compatibilidad con las opciones de acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="ae8a3-112">Para restablecer la directiva global para la configuración predeterminada</span><span class="sxs-lookup"><span data-stu-id="ae8a3-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="ae8a3-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ae8a3-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="ae8a3-115">En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**, haga clic en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="ae8a3-116">En la ficha **Directiva de acceso externo** , haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="ae8a3-117">Cuando se le pida que confirme la eliminación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="ae8a3-118">Aparece un mensaje en la parte superior de la página que le informa de que se ha restablecido la directiva global.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ae8a3-119">Restablecer la directiva de acceso externo Global mediante el uso de Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae8a3-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ae8a3-120">La directiva de acceso externo global se puede restablecer mediante el uso de Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="ae8a3-121">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae8a3-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="ae8a3-122">Para restablecer la directiva de acceso externo global</span><span class="sxs-lookup"><span data-stu-id="ae8a3-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="ae8a3-123">Este comando restablece la directiva de acceso externo global:</span><span class="sxs-lookup"><span data-stu-id="ae8a3-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="ae8a3-124">Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="ae8a3-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>



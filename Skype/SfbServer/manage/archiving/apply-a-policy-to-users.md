---
title: Aplicar una directiva de archivado a los usuarios en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumen: Aprenda a asignar una directiva de archivado a los usuarios en Skype empresarial Server.'
ms.openlocfilehash: 5dbd1624813b187e8c0981aa1a84b6096b79e86a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992787"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="e9f1e-103">Aplicar una directiva de archivado a los usuarios en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e9f1e-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="e9f1e-104">**Resumen:** Obtenga información sobre cómo asignar una directiva de archivado a los usuarios en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="e9f1e-105">Si ha creado una o más directivas de usuario para archivar para usuarios alojados en Skype empresarial Server, puede implementar la compatibilidad de archivado para usuarios específicos aplicando las directivas apropiadas a esos usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="e9f1e-106">Por ejemplo, si crea una directiva para admitir el archivado de comunicaciones internas, puede aplicarla a al menos un usuario o grupo de usuarios para admitir el archivado de las comunicaciones de Skype empresarial Server del usuario.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9f1e-107">Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange y si sus buzones se colocan en la retención local.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e9f1e-108">Para obtener más información, consulte [planear el archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md) y [configurar la integración con el almacenamiento de Exchange para Skype empresarial Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="e9f1e-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="e9f1e-109">Aplicar una directiva de usuario con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="e9f1e-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="e9f1e-110">Para aplicar una directiva de usuario con el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="e9f1e-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="e9f1e-111">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="e9f1e-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e9f1e-113">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="e9f1e-114">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e9f1e-115">En **Editar usuario de Lync Server** , en **Directiva de archivado**, seleccione la Directiva de usuario de archivado que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e9f1e-116">La \*\* \<configuración\> automática\*\* aplica la configuración predeterminada de la instalación del servidor.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="e9f1e-117">El servidor aplica automáticamente esta configuración.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="e9f1e-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="e9f1e-119">Aplicar una directiva de usuario mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9f1e-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="e9f1e-120">También puede aplicar una directiva de usuario mediante el cmdlet **Grant-CsArchivingPolicy de** Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e9f1e-121">El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="e9f1e-122">Con este comando se asigna la directiva de archivado por usuario RedmondArchivingPolicy a todos los usuarios que tengan cuentas hospedadas en el grupo de registradores atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="e9f1e-123">Para obtener más información sobre el parámetro de filtro usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e9f1e-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="e9f1e-p105">El siguiente comando quita cualquier directiva de archivado por usuario previamente asignada a Ken Myer. Una vez quitada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado con la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre las directivas globales.</span><span class="sxs-lookup"><span data-stu-id="e9f1e-p105">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="e9f1e-127">Para obtener más información, consulte la documentación del cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e9f1e-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  


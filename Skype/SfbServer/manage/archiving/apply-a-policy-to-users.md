---
title: Aplicar una directiva de archivado a los usuarios de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumen: obtenga información sobre cómo asignar una directiva de archivado a los usuarios de Skype Empresarial Server.'
ms.openlocfilehash: 1fce0dbd0cc7b0595dcf3cd91baeba9ed364e28a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095494"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="3b5ed-103">Aplicar una directiva de archivado a los usuarios de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3b5ed-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="3b5ed-104">**Resumen:** Obtenga información sobre cómo asignar una directiva de archivado a los usuarios de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="3b5ed-105">Si ha creado una o varias directivas de usuario para el archivado para usuarios que se aloban en Skype Empresarial Server, puede implementar la compatibilidad de archivado para usuarios específicos aplicando las directivas adecuadas a esos usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="3b5ed-106">Por ejemplo, si crea una directiva para admitir el archivado de comunicaciones internas, puede aplicarla al menos a un usuario o grupo de usuarios para admitir el archivado de las comunicaciones de Skype Empresarial Server del usuario.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b5ed-107">Si ha habilitado la integración de Microsoft Exchange para la implementación, las directivas de retención de Exchange In-Place controlan si el archivado está habilitado para los usuarios que se encuentran en Exchange y tienen sus buzones en espera In-Place espera.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="3b5ed-108">Para obtener más información, vea [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) y Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="3b5ed-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="3b5ed-109">Aplicar una directiva de usuario mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="3b5ed-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="3b5ed-110">Para aplicar una directiva de usuario mediante el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="3b5ed-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="3b5ed-111">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="3b5ed-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3b5ed-113">En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque la cuenta de usuario que quiera configurar.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="3b5ed-114">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="3b5ed-115">En **Editar usuario de Lync Server en** Directiva de **archivado,** seleccione la directiva de usuario de archivado que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3b5ed-116">La **\<Automatic\>** configuración aplica la configuración predeterminada de instalación del servidor.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="3b5ed-117">Esta configuración se aplica automáticamente por el servidor.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="3b5ed-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="3b5ed-119">Aplicar una directiva de usuario mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b5ed-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="3b5ed-120">También puede aplicar una directiva de usuario mediante el Windows PowerShell **cmdlet Grant-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="3b5ed-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="3b5ed-121">El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="3b5ed-122">Este comando asigna la directiva de archivado por usuario RedmondArchivingPolicy a todos los usuarios que tienen cuentas en el grupo de registradores atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="3b5ed-123">Para obtener más información sobre el parámetro Filter usado en este comando, consulte la documentación del cmdlet [Get-CsUser.](/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3b5ed-123">For details about the Filter parameter used in this command, see the [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="3b5ed-124">El siguiente comando quita cualquier directiva de archivado por usuario asignada anteriormente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="3b5ed-125">Después de quitar la directiva por usuario, Ken Myer se administrará automáticamente mediante la directiva global o, si existe, su directiva de sitio local.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="3b5ed-126">Las directivas de sitio tienen prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="3b5ed-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="3b5ed-127">Para obtener más información, consulte la documentación del cmdlet [Grant-CsArchivingPolicy.](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3b5ed-127">For details, see the [Grant-CsArchivingPolicy](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>

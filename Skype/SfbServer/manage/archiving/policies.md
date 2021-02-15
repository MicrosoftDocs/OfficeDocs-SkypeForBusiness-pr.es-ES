---
title: Administrar directivas de archivado en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumen: obtenga información sobre cómo administrar directivas de usuario para el archivado de Skype Empresarial Server.'
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828556"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="039ea-103">Administrar directivas de archivado en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="039ea-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="039ea-104">**Resumen:** Obtenga información sobre cómo administrar directivas de usuario para el archivado de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="039ea-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="039ea-105">Las directivas de archivado se establecen inicialmente al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="039ea-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="039ea-106">Las directivas de archivado determinan si se va a archivar:</span><span class="sxs-lookup"><span data-stu-id="039ea-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="039ea-107">Comunicaciones internas</span><span class="sxs-lookup"><span data-stu-id="039ea-107">Internal communications</span></span>
    
- <span data-ttu-id="039ea-108">Comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="039ea-108">External communications</span></span>
    
<span data-ttu-id="039ea-109">Las directivas de archivado se pueden establecer en el nivel global, de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="039ea-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="039ea-110">Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios que están en Exchange y tienen sus buzones en retención In-Place local.</span><span class="sxs-lookup"><span data-stu-id="039ea-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="039ea-111">Para obtener más información, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="039ea-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="039ea-112">Administrar directivas de archivado mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="039ea-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="039ea-113">Puede administrar las directivas de archivado mediante el Panel de control de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="039ea-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="039ea-114">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="039ea-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="039ea-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="039ea-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="039ea-116">En la barra de navegación izquierda, haga clic en **Directiva de archivado**</span><span class="sxs-lookup"><span data-stu-id="039ea-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="039ea-117">Administrar directivas de archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="039ea-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="039ea-118">También puede configurar directivas de archivado con los cmdlets Windows PowerShell que se enumeran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="039ea-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="039ea-119">Para obtener más información sobre la sintaxis, incluidos todos los parámetros disponibles, consulte Shell de administración [de Skype Empresarial Server.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="039ea-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="039ea-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="039ea-120">**Cmdlet**</span></span>|<span data-ttu-id="039ea-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="039ea-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="039ea-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="039ea-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="039ea-123">Devuelve información sobre las directivas de archivado de sesiones de mensajería instantánea (MI) de su organización.</span><span class="sxs-lookup"><span data-stu-id="039ea-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="039ea-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="039ea-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="039ea-125">Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="039ea-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="039ea-126">Estas directivas permiten archivar todas las sesiones de MI entre usuarios internos o archivar todas las sesiones de MI entre usuarios internos y socios externos.</span><span class="sxs-lookup"><span data-stu-id="039ea-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="039ea-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="039ea-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="039ea-128">Crea directivas de archivado de sesiones de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="039ea-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="039ea-129">Estas directivas permiten archivar todas las sesiones de mensajería instantánea entre usuarios internos o con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="039ea-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="039ea-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="039ea-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="039ea-131">Quita la directiva de archivado de mensajería instantánea (MI) especificada que determina si Skype Empresarial Server guardará automáticamente todas las sesiones de mensajería instantánea que tienen lugar entre usuarios internos o todas las sesiones de mensajería instantánea entre usuarios internos y socios federados.</span><span class="sxs-lookup"><span data-stu-id="039ea-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="039ea-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="039ea-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="039ea-133">Modifica una directiva de archivado de mensajería instantánea (MI) existente.</span><span class="sxs-lookup"><span data-stu-id="039ea-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="039ea-134">Una directiva de archivado le ofrece la capacidad de archivar todas las sesiones de mensajería instantánea y conferencias que tienen lugar entre usuarios internos; también puede archivar sesiones que tienen lugar entre usuarios internos y socios federados.</span><span class="sxs-lookup"><span data-stu-id="039ea-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   


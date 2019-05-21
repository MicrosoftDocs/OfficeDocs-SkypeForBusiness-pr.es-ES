---
title: Administrar directivas de archivado en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumen: Aprenda a administrar directivas de usuario para archivar en Skype empresarial Server.'
ms.openlocfilehash: f6918907f73ffe1b098ed96e1997d8ab8ffe4f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278429"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="d4c02-103">Administrar directivas de archivado en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d4c02-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="d4c02-104">**Resumen:** Aprenda a administrar directivas de usuario para archivar en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d4c02-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="d4c02-105">Inicialmente, debe configurar las directivas de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="d4c02-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="d4c02-106">Las directivas de archivado determinan si se debe archivar:</span><span class="sxs-lookup"><span data-stu-id="d4c02-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="d4c02-107">Comunicaciones internas</span><span class="sxs-lookup"><span data-stu-id="d4c02-107">Internal communications</span></span>
    
- <span data-ttu-id="d4c02-108">Comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="d4c02-108">External communications</span></span>
    
<span data-ttu-id="d4c02-109">Las directivas de archivado se pueden establecer en el nivel global, de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="d4c02-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4c02-110">Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange y si sus buzones se colocan en la retención local.</span><span class="sxs-lookup"><span data-stu-id="d4c02-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="d4c02-111">Para obtener más información, consulte [planear el archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md) y [configurar la integración con el almacenamiento de Exchange para Skype empresarial Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="d4c02-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="d4c02-112">Administrar directivas de archivado con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="d4c02-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="d4c02-113">Puede administrar las directivas de archivado con el Panel de control de esta manera:</span><span class="sxs-lookup"><span data-stu-id="d4c02-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="d4c02-114">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d4c02-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="d4c02-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d4c02-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d4c02-116">En la barra de navegación izquierda, haga clic en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="d4c02-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="d4c02-117">Administrar las directivas de archivado con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4c02-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="d4c02-118">También puede configurar las directivas de archivado con los cmdlets de Windows PowerShell que se enumeran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d4c02-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="d4c02-119">Para más información sobre la sintaxis, incluidos todos los parámetros disponibles, consulte [Shell de administración de Skype empresarial Server](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="d4c02-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="d4c02-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="d4c02-120">**Cmdlet**</span></span>|<span data-ttu-id="d4c02-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d4c02-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4c02-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d4c02-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d4c02-123">Devuelve información sobre las directivas de archivado de las sesiones de mensajería instantánea (MI) de la organización.</span><span class="sxs-lookup"><span data-stu-id="d4c02-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="d4c02-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d4c02-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d4c02-125">Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d4c02-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="d4c02-126">Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.</span><span class="sxs-lookup"><span data-stu-id="d4c02-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="d4c02-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d4c02-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d4c02-128">Crea directivas de archivado de sesiones de mensajería instantánea (MI).</span><span class="sxs-lookup"><span data-stu-id="d4c02-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="d4c02-129">Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.</span><span class="sxs-lookup"><span data-stu-id="d4c02-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="d4c02-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d4c02-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d4c02-131">Quita la Directiva de archivado de mensajería instantánea (mi) especificada que determina si Skype empresarial Server guardará automáticamente todas las sesiones de mensajería instantánea que se realicen entre usuarios internos o todas las sesiones de mensajería instantánea entre usuarios internos y socios federados.</span><span class="sxs-lookup"><span data-stu-id="d4c02-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="d4c02-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d4c02-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d4c02-133">Modifica una directiva de archivado de mensajería instantánea (mi) existente.</span><span class="sxs-lookup"><span data-stu-id="d4c02-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="d4c02-134">Una directiva de archivado le ofrece la posibilidad de archivar todas las sesiones y conferencias de mensajería instantánea que se producen entre usuarios internos; también puede archivar las sesiones que tienen lugar entre usuarios internos y socios federados.</span><span class="sxs-lookup"><span data-stu-id="d4c02-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   


---
title: Administración de directivas de archivado en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumen: Obtenga información sobre cómo administrar las directivas de usuario para el archivado de Skype para Business Server.'
ms.openlocfilehash: 289902ded6f1530c74f9c945517a3c853c99d364
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211058"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="49e0e-103">Administración de directivas de archivado en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="49e0e-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="49e0e-104">**Resumen:** Obtenga información sobre cómo administrar las directivas de usuario para el archivado de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="49e0e-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="49e0e-105">Inicialmente, configurar directivas de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar las configuraciones de después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="49e0e-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="49e0e-106">Las directivas de archivado determinan si desea archivar:</span><span class="sxs-lookup"><span data-stu-id="49e0e-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="49e0e-107">Comunicaciones internas</span><span class="sxs-lookup"><span data-stu-id="49e0e-107">Internal communications</span></span>
    
- <span data-ttu-id="49e0e-108">Comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="49e0e-108">External communications</span></span>
    
<span data-ttu-id="49e0e-109">Directivas de archivado pueden ser conjunto a nivel global, de sitio o de nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="49e0e-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="49e0e-110">Si se habilita la integración de Microsoft Exchange para la implementación, el control de las directivas de Exchange si el archivado está habilitado para los usuarios que están ubicados en Exchange y disponer sus buzones en suspensión en contexto.</span><span class="sxs-lookup"><span data-stu-id="49e0e-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="49e0e-111">Para obtener información detallada, vea [Planear el archivado en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md) y [Configure la integración con el almacenamiento de Exchange de Skype para Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="49e0e-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="49e0e-112">Administrar directivas de archivado con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="49e0e-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="49e0e-113">Puede administrar las directivas de archivado con el Panel de control de esta manera:</span><span class="sxs-lookup"><span data-stu-id="49e0e-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="49e0e-114">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="49e0e-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="49e0e-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="49e0e-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="49e0e-116">En la barra de navegación izquierda, haga clic en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="49e0e-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="49e0e-117">Administrar las directivas de archivado con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49e0e-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="49e0e-118">También puede configurar las directivas de archivado con los cmdlets de Windows PowerShell que se enumeran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="49e0e-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="49e0e-119">Para obtener información detallada sobre la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para Shell de administración de servidor empresarial](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="49e0e-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="49e0e-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="49e0e-120">**Cmdlet**</span></span>|<span data-ttu-id="49e0e-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="49e0e-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="49e0e-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="49e0e-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="49e0e-123">Devuelve información sobre las directivas de archivado de las sesiones de mensajería instantánea (MI) de la organización.</span><span class="sxs-lookup"><span data-stu-id="49e0e-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="49e0e-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="49e0e-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="49e0e-125">Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="49e0e-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="49e0e-126">Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.</span><span class="sxs-lookup"><span data-stu-id="49e0e-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="49e0e-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="49e0e-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="49e0e-128">Crea directivas de archivado de sesiones de mensajería instantánea (MI).</span><span class="sxs-lookup"><span data-stu-id="49e0e-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="49e0e-129">Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.</span><span class="sxs-lookup"><span data-stu-id="49e0e-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="49e0e-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="49e0e-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="49e0e-131">Quita el especificado mensajería instantánea (mi) directiva que determina si Skype para Business Server guardará automáticamente todas las sesiones de mensajería instantánea que tienen lugar entre los usuarios internos, o todas las sesiones de mensajería instantánea entre usuarios internos y los socios federados de archivado.</span><span class="sxs-lookup"><span data-stu-id="49e0e-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="49e0e-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="49e0e-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="49e0e-133">Modifica una existente mensajería instantánea (mi) Directiva de archivado.</span><span class="sxs-lookup"><span data-stu-id="49e0e-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="49e0e-134">Una directiva de archivado le ofrece la posibilidad de archivar todas las sesiones de mensajería instantánea y las conferencias que tienen lugar entre los usuarios internos; También puede archivar sesiones que tienen lugar entre los usuarios internos y los socios federados.</span><span class="sxs-lookup"><span data-stu-id="49e0e-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   


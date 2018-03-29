---
title: Administrar las directivas de archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumen: Conozca cómo administrar directivas de usuario para archiving de Skype para Business Server 2015.'
ms.openlocfilehash: 584849862e106098bc4bbad92ed4e0b87be410e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="9cb24-103">Administrar las directivas de archivado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9cb24-103">Manage archiving policies in Skype for Business Server 2015</span></span>

<span data-ttu-id="9cb24-104">**Resumen:** Obtenga información sobre cómo administrar las directivas de usuario para archiving de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9cb24-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9cb24-105">Inicialmente configurar políticas de archiving al implementar archiving, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="9cb24-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="9cb24-106">Políticas de archiving de determinan si se debe archivar:</span><span class="sxs-lookup"><span data-stu-id="9cb24-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="9cb24-107">Comunicaciones internas</span><span class="sxs-lookup"><span data-stu-id="9cb24-107">Internal communications</span></span>
    
- <span data-ttu-id="9cb24-108">Comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="9cb24-108">External communications</span></span>
    
<span data-ttu-id="9cb24-109">Políticas de archiving pueden ser a nivel de usuario, sitio o conjunto a nivel global.</span><span class="sxs-lookup"><span data-stu-id="9cb24-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9cb24-110">Si habilita la integración de Microsoft Exchange para la implementación, el control de directivas de Exchange si el archivado está habilitado para los usuarios que están alojados en Exchange y han puesto a sus buzones en mantenga In situ.</span><span class="sxs-lookup"><span data-stu-id="9cb24-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="9cb24-111">Para obtener más información, vea [planear para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md) y [Configurar la integración con almacenamiento de información de Exchange para Skype para Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="9cb24-111">For details, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="9cb24-112">Administrar directivas de archivado con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="9cb24-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="9cb24-113">Puede administrar las directivas de archivado con el Panel de control de esta manera:</span><span class="sxs-lookup"><span data-stu-id="9cb24-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="9cb24-114">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9cb24-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9cb24-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="9cb24-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9cb24-116">En la barra de navegación izquierda, haga clic en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="9cb24-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="9cb24-117">Administrar las directivas de archivado con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cb24-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="9cb24-118">También puede configurar las directivas de archivado con los cmdlets de Windows PowerShell que se enumeran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9cb24-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="9cb24-119">Para obtener más información acerca de la sintaxis, incluidos todos los parámetros disponibles, vea [Skype para el Shell de administración de negocio servidor 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="9cb24-119">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="9cb24-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="9cb24-120">**Cmdlet**</span></span>|<span data-ttu-id="9cb24-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9cb24-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9cb24-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="9cb24-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="9cb24-123">Devuelve información sobre las directivas de archivado de las sesiones de mensajería instantánea (MI) de la organización.</span><span class="sxs-lookup"><span data-stu-id="9cb24-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="9cb24-124">Concesión CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="9cb24-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="9cb24-125">Asigna directivas de archivado de sesiones de mensajería instantánea (MI) a usuarios o conjuntos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="9cb24-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="9cb24-126">Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.</span><span class="sxs-lookup"><span data-stu-id="9cb24-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="9cb24-127">Nueva CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="9cb24-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="9cb24-128">Crea directivas de archivado de sesiones de mensajería instantánea (MI).</span><span class="sxs-lookup"><span data-stu-id="9cb24-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="9cb24-129">Estas directivas permiten archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos o archivar todas las sesiones de mensajería instantánea (MI) entre usuarios internos y socios externos.</span><span class="sxs-lookup"><span data-stu-id="9cb24-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="9cb24-130">Quitar CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="9cb24-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="9cb24-131">Quita el especificado mensajería instantánea (IM) directiva que determina si Skype para Business Server guardará automáticamente todas las sesiones IM que tienen lugar entre los usuarios internos, o bien todas las sesiones de mensajería instantánea entre usuarios internos y los socios federados para el archivado.</span><span class="sxs-lookup"><span data-stu-id="9cb24-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="9cb24-132">Conjunto de CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="9cb24-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="9cb24-133">Modifica una existente mensajería instantánea (IM política de archivado).</span><span class="sxs-lookup"><span data-stu-id="9cb24-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="9cb24-134">Una directiva de archivado le da la capacidad de archivar todas las sesiones de mensajería instantánea y conferencias que tienen lugar entre los usuarios internos; También puede archivar las sesiones que tienen lugar entre los usuarios internos y los socios federados.</span><span class="sxs-lookup"><span data-stu-id="9cb24-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   


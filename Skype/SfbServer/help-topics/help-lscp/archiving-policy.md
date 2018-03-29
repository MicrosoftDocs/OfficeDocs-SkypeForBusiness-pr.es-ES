---
title: Directiva de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Utilizar directivas de archivado para habilitar y deshabilitar el archivado para usuarios alojados en Skype para Business Server. En cada directiva de archivado, puede habilitar o deshabilitar el archivado para una de las siguientes opciones (o ambas):'
ms.openlocfilehash: eea3f7eb71bcf3928e2976b9468cea6bf94b4ab1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-policy"></a><span data-ttu-id="5b287-104">Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="5b287-104">Archiving Policy</span></span>
 
<span data-ttu-id="5b287-105">Utilizar directivas de archivado para habilitar y deshabilitar el archivado para usuarios alojados en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b287-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="5b287-106">En cada directiva de archivado, puede habilitar o deshabilitar el archivado para una de las siguientes opciones (o ambas):</span><span class="sxs-lookup"><span data-stu-id="5b287-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="5b287-107">Comunicaciones internas</span><span class="sxs-lookup"><span data-stu-id="5b287-107">Internal communications</span></span>
    
- <span data-ttu-id="5b287-108">Comunicaciones externas (comunicaciones que incluyen al menos un usuario de fuera de su red interna)</span><span class="sxs-lookup"><span data-stu-id="5b287-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="5b287-109">Las directivas de archivado están formadas por la directiva global y, de forma opcional, por una o varias directivas de archivado de usuario y de sitio:</span><span class="sxs-lookup"><span data-stu-id="5b287-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="5b287-110">**Directiva global** La directiva global se crea de forma predeterminada en todas las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="5b287-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="5b287-111">Puede editarla, pero no eliminarla.</span><span class="sxs-lookup"><span data-stu-id="5b287-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="5b287-112">Si intenta eliminarla, todas las opciones se restablecerán a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5b287-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="5b287-113">**Directiva de sitio (opcional)** Puede especificar uno o más sitios archivado directivas, que cada una de las cuales se puede configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un único sitio.</span><span class="sxs-lookup"><span data-stu-id="5b287-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="5b287-114">Una directiva de sitio reemplaza a la directiva global, pero solo para los sitios especificados en las directivas de sitio de archivado.</span><span class="sxs-lookup"><span data-stu-id="5b287-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="5b287-115">Las directivas de sitio se pueden editar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="5b287-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="5b287-116">**Directiva de usuario (opcional)** Puede especificar uno o más archivado directivas de usuario, que cada uno de los cuales se puede configurar para habilitar y deshabilitar el archivado de comunicaciones internas o externas para un usuario específico o grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="5b287-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="5b287-117">Una directiva de usuario reemplaza a las directivas globales y de sitio, pero solo para los usuarios y grupos de usuarios que tengan asignadas directivas de archivado de nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="5b287-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="5b287-118">Las directivas de usuario se pueden editar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="5b287-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5b287-119">Políticas de archiving se aplican sólo a los usuarios alojados en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b287-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="5b287-120">Si utiliza la integración de Exchange para almacenar archivar los datos en Microsoft Exchange, a continuación, las directivas de Exchange 2013 control archivado para usuarios alojados en Exchange de 2013.</span><span class="sxs-lookup"><span data-stu-id="5b287-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="5b287-121">Para habilitar el archivado de los usuarios, el buzón del usuario debe colocarse en posesión en el lugar.</span><span class="sxs-lookup"><span data-stu-id="5b287-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="5b287-p107">La página **Directiva de archivado** muestra cada directiva de archivado configurada en la implementación. También refleja el nombre de la directiva, el ámbito (global, sitio o usuario) y qué opciones de archivado están habilitadas para cada directiva de archivado. En la página **Directiva de archivado**, dispone de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5b287-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="5b287-125">**Nuevo** Puede agregar uno o varios de cada una de las siguientes políticas de Archiving opcionales:</span><span class="sxs-lookup"><span data-stu-id="5b287-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="5b287-126">Directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="5b287-126">Site policy</span></span>
    
  - <span data-ttu-id="5b287-127">Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="5b287-127">User policy</span></span>
    
- <span data-ttu-id="5b287-128">**Editar** Puede cambiar las opciones de cualquiera de las directivas de archivado que aparecen en la página.</span><span class="sxs-lookup"><span data-stu-id="5b287-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="5b287-129">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b287-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="5b287-130">**Mostrar detalles.** Con esta opción se abre un cuadro de diálogo en el que puede cambiar las opciones de archivado de una directiva de archivado.</span><span class="sxs-lookup"><span data-stu-id="5b287-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="5b287-131">**Seleccionar todo.** Esta opción selecciona todas las directivas de archivado de la lista.</span><span class="sxs-lookup"><span data-stu-id="5b287-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="5b287-132">**Eliminar.** Esta opción elimina todas las directivas de archivado seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="5b287-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="5b287-133">**Acción** Puede utilizar esta opción para habilitar o deshabilitar el archivado de comunicaciones internas o externas en cualquier directiva aparecerán en la página, en lugar de modificar la directiva rápidamente.</span><span class="sxs-lookup"><span data-stu-id="5b287-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="5b287-134">Las opciones disponibles en **Acción** dependen de qué opción esté especificada actualmente en la directiva de archivado.</span><span class="sxs-lookup"><span data-stu-id="5b287-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="5b287-135">Todas las opciones están disponibles, excepto la opción en vigor actualmente para la directiva de archivado.</span><span class="sxs-lookup"><span data-stu-id="5b287-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="5b287-136">Las opciones son estas:</span><span class="sxs-lookup"><span data-stu-id="5b287-136">Options include the following:</span></span>
    
  - <span data-ttu-id="5b287-137">**Habilitar archivado de comunicaciones internas**</span><span class="sxs-lookup"><span data-stu-id="5b287-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="5b287-138">**Deshabilitar archivado de comunicaciones internas**</span><span class="sxs-lookup"><span data-stu-id="5b287-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="5b287-139">**Habilitar archivado de comunicaciones externas**</span><span class="sxs-lookup"><span data-stu-id="5b287-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="5b287-140">**Deshabilitar archivado de comunicaciones externas**</span><span class="sxs-lookup"><span data-stu-id="5b287-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="5b287-141">**Actualizar** Puede actualizar la página **Política de Archiving** para comprobar el estado de las opciones de todas las políticas de Archiving.</span><span class="sxs-lookup"><span data-stu-id="5b287-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="5b287-142">Para obtener más información acerca de la característica de archivado y capacidades, incluida la integración de Exchange, consulte [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [implementar archiving de Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)y [Administrar archiving en Skype para 2015 empresariales de servidor](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="5b287-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>


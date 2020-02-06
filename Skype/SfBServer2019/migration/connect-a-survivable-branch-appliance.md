---
title: Conectar una aplicación de sucursal con funciones de supervivencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Cada dispositivo de sucursal con supervivencia (SBA) está asociado con un grupo de servidores front-end que sirve como registrador de copias de seguridad de la SBA. Cuando el grupo de servidores front-end se migra a Skype empresarial Server 2019, SBA debe estar desvinculado del grupo front-end mientras se actualiza el grupo, una vez que el grupo se ha migrado a Skype empresarial Server 2019, la SBA se puede volver a asociar con la actualización frontal E Grupo ND. Esto implica eliminar la SBA de la topología heredada en el generador de topología y, a continuación, agregar el SBA a la topología de Skype empresarial Server 2019. Los usuarios alojados en el SBA heredado deben moverse primero a otro grupo de servidores front end antes de quitar SBA de la topología. Una vez agregada SBA a la topología de Skype empresarial Server 2019, esos usuarios podrán volver a la SBA. Estos pasos se resumen a continuación:'
ms.openlocfilehash: daeb061936ece02767e3299d2358d8e16ba09218
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813738"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="ee117-108">Conectar una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="ee117-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="ee117-109">Cada dispositivo de sucursal con supervivencia (SBA) está asociado con un grupo de servidores front-end que sirve como registrador de copias de seguridad de la SBA.</span><span class="sxs-lookup"><span data-stu-id="ee117-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="ee117-110">Cuando el grupo de servidores front-end se migra a Skype empresarial Server 2019, SBA debe estar desvinculado del grupo de servidores front-end mientras se actualiza el grupo.</span><span class="sxs-lookup"><span data-stu-id="ee117-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="ee117-111">Una vez que el grupo se ha migrado a Skype empresarial Server 2019, SBA se puede volver a asociar al grupo de servidores front-end actualizado.</span><span class="sxs-lookup"><span data-stu-id="ee117-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="ee117-112">Esto implica eliminar la SBA de la topología heredada en el generador de topología y, a continuación, agregar el SBA a la topología de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ee117-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="ee117-113">Los usuarios alojados en el SBA heredado deben moverse primero a otro grupo de servidores front end antes de quitar SBA de la topología.</span><span class="sxs-lookup"><span data-stu-id="ee117-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="ee117-114">Después de agregar SBA a la topología de Skype empresarial Server 2019, esos usuarios se pueden mover de nuevo a SBA.</span><span class="sxs-lookup"><span data-stu-id="ee117-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="ee117-115">Estos pasos se resumen a continuación:</span><span class="sxs-lookup"><span data-stu-id="ee117-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="ee117-116">Mueva los usuarios alojados en el SBA heredado a otro grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ee117-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="ee117-117">Quite SBA de la topología heredada para desconectar el grupo de servidores front-end existente como registrador de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ee117-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="ee117-118">Agregue SBA a la topología de Skype empresarial Server 2019 y configúrela como registrador de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ee117-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="ee117-119">Mueva a los usuarios de la sucursal al nuevo servidor de Skype empresarial 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="ee117-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="ee117-120">Agregar el sitio de la sucursal de SBA heredado a su topología</span><span class="sxs-lookup"><span data-stu-id="ee117-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="ee117-121">Abra el **generador de topologías**.</span><span class="sxs-lookup"><span data-stu-id="ee117-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="ee117-122">En el panel de la izquierda, haga clic con el botón secundario en **sitios de sucursales**y luego haga clic en **nuevo sitio de sucursal**.</span><span class="sxs-lookup"><span data-stu-id="ee117-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="ee117-123">En el cuadro de diálogo **definir nuevo sitio de sucursal** , haga clic en **nombre**y, a continuación, escriba el nombre del sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ee117-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="ee117-124">Faculta Haga clic en **Descripción**y, a continuación, escriba una descripción para el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ee117-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="ee117-125">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ee117-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="ee117-126">Faculta En el cuadro de diálogo **definir siguiente sitio de sucursal** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ee117-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="ee117-127">Haga clic en **ciudad**y, a continuación, escriba el nombre de la ciudad en la que se encuentra el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ee117-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="ee117-128">Haga clic en **Estado o región**y, a continuación, escriba el nombre del estado o la región en la que se encuentra el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ee117-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="ee117-129">Haga clic en **prefijo internacional**y escriba el código de la llamada de dos dígitos para el país o la región en la que se encuentra el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ee117-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="ee117-130">Haga clic en **siguiente**y, después, si está usando un dispositivo o servidor de sucursal con la mayor supervivencia en este sitio, asegúrese de desactivar la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** .</span><span class="sxs-lookup"><span data-stu-id="ee117-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="ee117-131">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ee117-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="ee117-132">Para asociar SBA heredado al grupo front-end de Skype empresarial Server 2019:</span><span class="sxs-lookup"><span data-stu-id="ee117-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="ee117-133">Expanda el sitio de la sucursal que ha creado.</span><span class="sxs-lookup"><span data-stu-id="ee117-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="ee117-134">Haga clic con el botón derecho en versión heredada y luego haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ee117-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="ee117-135">Haga clic en **equipo de rama superviviente**.</span><span class="sxs-lookup"><span data-stu-id="ee117-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="ee117-136">Siga las instrucciones del asistente que se abre.</span><span class="sxs-lookup"><span data-stu-id="ee117-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="ee117-137">Para obtener información sobre los elementos del asistente, consulte</span><span class="sxs-lookup"><span data-stu-id="ee117-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="ee117-138">Un equipo de sucursal con la supervivencia solo puede asociarse con una tienda de supervisión.</span><span class="sxs-lookup"><span data-stu-id="ee117-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="ee117-139">Si no usa un equipo o servidor de sucursal con la supervivencia en este sitio, desactive la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ee117-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="ee117-140">Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.</span><span class="sxs-lookup"><span data-stu-id="ee117-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    


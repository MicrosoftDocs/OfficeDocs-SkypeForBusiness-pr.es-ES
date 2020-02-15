---
title: Conexión de una aplicación de sucursal con funciones de supervivencia
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
description: 'Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copias de seguridad para SBA. Cuando el grupo de servidores front-end se migra a Skype empresarial Server 2019, la SBA debe estar desasociada del grupo de servidores front-end mientras se actualiza el grupo, una vez que el grupo se ha migrado a Skype empresarial Server 2019, la SBA puede volver a asociarse con la actualización frontal E Grupo ND. Esto implica eliminar la SBA de la topología heredada en el generador de topologías y, a continuación, agregar la SBA a la topología de Skype empresarial Server 2019. Los usuarios hospedados en la SBA heredada deben moverse primero a otro grupo de servidores front-end antes de quitar SBA de la topología. Una vez agregada SBA a la topología de Skype empresarial Server 2019, estos usuarios se pueden volver a mover a SBA. Estos pasos se sintetizan a continuación:'
ms.openlocfilehash: 7f51b9c29d6008ea3606184eb22741a489d056df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027791"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="969e4-108">Conexión de una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="969e4-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="969e4-109">Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copias de seguridad para SBA.</span><span class="sxs-lookup"><span data-stu-id="969e4-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="969e4-110">Cuando el grupo de servidores front-end se migra a Skype empresarial Server 2019, la SBA debe estar desasociada del grupo de servidores front-end mientras se actualiza el grupo.</span><span class="sxs-lookup"><span data-stu-id="969e4-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="969e4-111">Una vez que el grupo se ha migrado a Skype empresarial Server 2019, la SBA se puede volver a asociar con el grupo de servidores front-end actualizado.</span><span class="sxs-lookup"><span data-stu-id="969e4-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="969e4-112">Esto implica eliminar la SBA de la topología heredada en el generador de topologías y, a continuación, agregar la SBA a la topología de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="969e4-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="969e4-113">Los usuarios hospedados en la SBA heredada deben moverse primero a otro grupo de servidores front-end antes de quitar SBA de la topología.</span><span class="sxs-lookup"><span data-stu-id="969e4-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="969e4-114">Una vez agregada SBA a la topología de Skype empresarial Server 2019, estos usuarios se pueden volver a mover a SBA.</span><span class="sxs-lookup"><span data-stu-id="969e4-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="969e4-115">Estos pasos se sintetizan a continuación:</span><span class="sxs-lookup"><span data-stu-id="969e4-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="969e4-116">Mueva los usuarios de sucursal hospedados en SBA heredado a otro grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="969e4-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="969e4-117">Quite SBA de la topología heredada para desconectar el grupo de servidores front-end existente como registrador de reserva.</span><span class="sxs-lookup"><span data-stu-id="969e4-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="969e4-118">Agregue SBA a la topología de Skype empresarial Server 2019 y configure este nuevo grupo de servidores front-end como registrador de reserva.</span><span class="sxs-lookup"><span data-stu-id="969e4-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="969e4-119">Mueva los usuarios de sucursal al nuevo SBA de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="969e4-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="969e4-120">Agregar sitio de sucursal de SBA heredado a la topología</span><span class="sxs-lookup"><span data-stu-id="969e4-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="969e4-121">Abra el **Generador de topologías**.</span><span class="sxs-lookup"><span data-stu-id="969e4-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="969e4-122">En el panel izquierdo, haga clic con el botón secundario en **sitios de sucursal**y haga clic en **nuevo sitio de sucursal**.</span><span class="sxs-lookup"><span data-stu-id="969e4-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="969e4-123">En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en \*\*Nombre \*\* y escriba el nombre del sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="969e4-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="969e4-124">(Opcional) Haga clic en \*\*Descripción \*\* y escriba una descripción significativa para el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="969e4-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="969e4-125">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="969e4-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="969e4-126">(Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="969e4-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="969e4-127">Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="969e4-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="969e4-128">Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="969e4-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="969e4-129">Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="969e4-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="969e4-130">Haga clic en **siguiente**y, si está usando una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, asegúrese de desactivar la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** .</span><span class="sxs-lookup"><span data-stu-id="969e4-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="969e4-131">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="969e4-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="969e4-132">Para asociar la SBA heredada al grupo de servidores front-end de Skype empresarial Server 2019:</span><span class="sxs-lookup"><span data-stu-id="969e4-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="969e4-133">Expanda el sitio de sucursal que ha creado.</span><span class="sxs-lookup"><span data-stu-id="969e4-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="969e4-134">Haga clic con el botón secundario en versión heredada y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="969e4-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="969e4-135">Haga clic en **aplicación de sucursal**con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="969e4-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="969e4-136">Siga las indicaciones del asistente que se abrirá.</span><span class="sxs-lookup"><span data-stu-id="969e4-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="969e4-137">Para obtener información acerca de los elementos del asistente, consulte</span><span class="sxs-lookup"><span data-stu-id="969e4-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="969e4-138">Una aplicación de sucursal con funciones de supervivencia solo se puede asociar con un almacén de supervisión.</span><span class="sxs-lookup"><span data-stu-id="969e4-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="969e4-139">Si no usa una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="969e4-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="969e4-140">Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.</span><span class="sxs-lookup"><span data-stu-id="969e4-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    


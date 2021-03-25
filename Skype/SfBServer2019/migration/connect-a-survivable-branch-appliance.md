---
title: Conectar una aplicación de sucursal con funciones de supervivencia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copia de seguridad para el SBA. Cuando el grupo de servidores front-end se migra a Skype Empresarial Server 2019, el SBA debe desasociarse del grupo de servidores front-end mientras se actualiza el grupo de servidores, Una vez que el grupo se ha migrado a Skype Empresarial Server 2019, el SBA se puede volver a asociar al grupo de servidores front-end actualizado. Esto implica eliminar el SBA de la topología heredada en el Generador de topologías y, a continuación, agregar el SBA a la topología de Skype Empresarial Server 2019. Los usuarios que se aloen en el SBA heredado primero deben moverse a otro grupo de servidores front-end antes de quitar el SBA de la topología. Una vez que el SBA se agrega a la topología de Skype Empresarial Server 2019, dichos usuarios pueden volver a la SBA. Estos pasos se sintetizan a continuación:'
ms.openlocfilehash: e56bae1631a315b6f42042fb6a7bedd4f144a1b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113346"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="149a6-108">Conectar una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="149a6-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="149a6-109">Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copia de seguridad para el SBA.</span><span class="sxs-lookup"><span data-stu-id="149a6-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="149a6-110">Cuando el grupo de servidores front-end se migra a Skype Empresarial Server 2019, el SBA debe desasociarse del grupo de servidores front-end mientras se actualiza el grupo.</span><span class="sxs-lookup"><span data-stu-id="149a6-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="149a6-111">Después de migrar el grupo a Skype Empresarial Server 2019, el SBA se puede volver a asociar al grupo de servidores front-end actualizado.</span><span class="sxs-lookup"><span data-stu-id="149a6-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="149a6-112">Esto implica eliminar el SBA de la topología heredada en el Generador de topologías y, a continuación, agregar el SBA a la topología de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="149a6-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="149a6-113">Los usuarios que se aloen en el SBA heredado primero deben moverse a otro grupo de servidores front-end antes de quitar el SBA de la topología.</span><span class="sxs-lookup"><span data-stu-id="149a6-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="149a6-114">Después de agregar el SBA a la topología de Skype Empresarial Server 2019, dichos usuarios pueden volver a la SBA.</span><span class="sxs-lookup"><span data-stu-id="149a6-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="149a6-115">Estos pasos se sintetizan a continuación:</span><span class="sxs-lookup"><span data-stu-id="149a6-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="149a6-116">Mueva los usuarios de sucursal que se alomen en el SBA heredado a otro grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="149a6-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="149a6-117">Quite SBA de la topología heredada para desconectar el grupo de servidores front-end existente como registrador de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="149a6-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="149a6-118">Agregue SBA a la topología de Skype Empresarial Server 2019 y configure este nuevo grupo de servidores front-end como registrador de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="149a6-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="149a6-119">Mueva los usuarios de sucursal al nuevo SBA de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="149a6-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="149a6-120">Agregar un sitio de sucursal SBA heredado a la topología</span><span class="sxs-lookup"><span data-stu-id="149a6-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="149a6-121">Abra el **Generador de topologías**.</span><span class="sxs-lookup"><span data-stu-id="149a6-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="149a6-122">En el panel izquierdo, haga clic con el botón secundario en **Sitios de sucursal** y, a continuación, haga clic en Nuevo sitio de **sucursal.**</span><span class="sxs-lookup"><span data-stu-id="149a6-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="149a6-123">En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en **Nombre** y escriba el nombre del sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="149a6-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="149a6-124">(Opcional) Haga clic en **Descripción** y escriba una descripción significativa para el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="149a6-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="149a6-125">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="149a6-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="149a6-126">(Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="149a6-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="149a6-127">Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="149a6-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="149a6-128">Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="149a6-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="149a6-129">Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="149a6-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="149a6-130">Haga **clic en** Siguiente y, a continuación, si usa una aplicación de sucursal con funciones de supervivencia o un servidor en este sitio, asegúrese de borrar la casilla Abrir el Nuevo Asistente para supervivencia **cuando** se cierre este asistente.</span><span class="sxs-lookup"><span data-stu-id="149a6-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="149a6-131">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="149a6-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="149a6-132">Para asociar el SBA heredado al grupo de servidores front-end de Skype Empresarial Server 2019:</span><span class="sxs-lookup"><span data-stu-id="149a6-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="149a6-133">Expanda el sitio de sucursal que ha creado.</span><span class="sxs-lookup"><span data-stu-id="149a6-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="149a6-134">Haga clic con el botón secundario en versión heredada y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="149a6-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="149a6-135">Haga **clic en Aplicación de sucursal con funciones de supervivencia.**</span><span class="sxs-lookup"><span data-stu-id="149a6-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="149a6-136">Siga las indicaciones del asistente que se abrirá.</span><span class="sxs-lookup"><span data-stu-id="149a6-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="149a6-137">Para obtener información acerca de los elementos del asistente, vea</span><span class="sxs-lookup"><span data-stu-id="149a6-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="149a6-138">Una aplicación de sucursal con funciones de supervivencia solo se puede asociar a un almacén de supervisión.</span><span class="sxs-lookup"><span data-stu-id="149a6-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="149a6-139">Si no usa una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="149a6-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="149a6-140">Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.</span><span class="sxs-lookup"><span data-stu-id="149a6-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

---
title: Conectar una aplicación de sucursal con funciones de supervivencia
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cada dispositivo de sucursal con funciones de supervivencia (SBA) está asociado con un grupo de servidores Front-End que actúa como un registrador de reserva para la SBA. Cuando el Front-End de grupo de servidores se migra a Skype para Business Server 2019, la SBA debe estar asociado al grupo de servidores Front-End mientras se actualiza el grupo de servidores, una vez que el grupo de servidores se ha migrado a Skype para Business Server 2019, la SBA puede asociarse volver a la actualizada E front- grupo de servidores de ND. Esto implica la eliminación de la SBA de la topología heredada en el generador de topología y, a continuación, agregar la SBA a la Skype para topología empresarial Server 2019. Los usuarios alojados en el heredado que SBA en primer lugar debe moverse a otro grupo de servidores Front-End antes de quitar la SBA de la topología. Una vez que se agrega la SBA a la Skype para Business Server 2019 topología, los usuarios pueden, a continuación, volver a moverse a la SBA. A continuación se resumen estos pasos:'
ms.openlocfilehash: ff35032d9abc5c1435e44dea7aca83d841b404c6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373752"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="fb77c-108">Conectar una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="fb77c-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="fb77c-109">Cada dispositivo de sucursal con funciones de supervivencia (SBA) está asociado con un grupo de servidores Front-End que actúa como un registrador de copia de seguridad para la SBA.</span><span class="sxs-lookup"><span data-stu-id="fb77c-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="fb77c-110">Cuando el grupo de servidores Front-End se migra a Skype para Business Server 2019, la SBA debe estar asociada desde el grupo de servidores Front-End mientras se actualiza el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="fb77c-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="fb77c-111">Después de que el grupo de servidores se ha migrado a Skype para Business Server 2019, se puede volver a asociar con el grupo de servidores Front-End actualizado la SBA.</span><span class="sxs-lookup"><span data-stu-id="fb77c-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="fb77c-112">Esto implica la eliminación de la SBA de la topología heredada en el generador de topología y, a continuación, agregar la SBA a la Skype para topología empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fb77c-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="fb77c-113">Los usuarios alojados en el heredado que SBA en primer lugar debe moverse a otro grupo de servidores Front-End antes de quitar la SBA de la topología.</span><span class="sxs-lookup"><span data-stu-id="fb77c-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="fb77c-114">Después de agrega la SBA a la Skype para Business Server 2019 topología, los usuarios pueden volver a moverse a la SBA.</span><span class="sxs-lookup"><span data-stu-id="fb77c-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="fb77c-115">A continuación se resumen estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fb77c-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="fb77c-116">Mover los usuarios de sucursal hospedados en la SBA heredada a otro grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="fb77c-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="fb77c-117">Quitar la SBA de la topología heredada para desconectar el grupo de servidores Front-End existente como un registrador de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb77c-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="fb77c-118">Agregar la SBA a la Skype para Business Server 2019 topología y configuración de este nuevo grupo de servidores Front-End como registrador de reserva.</span><span class="sxs-lookup"><span data-stu-id="fb77c-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="fb77c-119">Mover los usuarios de sucursal a la nueva Skype para Business Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="fb77c-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="fb77c-120">Agregar el sitio de sucursal SBA heredado a la topología</span><span class="sxs-lookup"><span data-stu-id="fb77c-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="fb77c-121">Abra **el generador de topología**.</span><span class="sxs-lookup"><span data-stu-id="fb77c-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="fb77c-122">En el panel izquierdo, haga clic en **sitios de sucursal**y, a continuación, haga clic en **Nuevo sitio de sucursal**.</span><span class="sxs-lookup"><span data-stu-id="fb77c-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="fb77c-123">En el cuadro de diálogo **Definir nuevo sitio de sucursal** , haga clic en **nombre**y, a continuación, escriba el nombre de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="fb77c-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="fb77c-124">(Opcional) Haga clic en **Descripción**y, a continuación, escriba una descripción significativa para el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="fb77c-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="fb77c-125">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fb77c-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="fb77c-126">(Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal** , realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fb77c-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="fb77c-127">Haga clic en **Ciudad**y, a continuación, escriba el nombre de la ciudad donde se encuentra el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="fb77c-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="fb77c-128">Haga clic en **provincia o región**y, a continuación, escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="fb77c-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="fb77c-129">Haga clic en **El código de país**y, a continuación, escriba el código de llamada de dos dígitos para el país o región en el que se encuentra el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="fb77c-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="fb77c-130">Haga clic en **siguiente**y, a continuación, si se usa una aplicación de sucursal con funciones de supervivencia o servidor en este sitio, asegúrese de desactive la casilla de verificación **Abrir el Asistente nuevo con funciones de supervivencia cuando se cierre este asistente** .</span><span class="sxs-lookup"><span data-stu-id="fb77c-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="fb77c-131">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="fb77c-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="fb77c-132">Para asociar la SBA heredada a la Skype para el grupo de servidores Front-End de Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="fb77c-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="fb77c-133">Expanda el sitio de sucursal que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="fb77c-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="fb77c-134">Haga clic en la versión heredada y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fb77c-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="fb77c-135">Haga clic en **aplicación de sucursal con funciones de supervivencia**.</span><span class="sxs-lookup"><span data-stu-id="fb77c-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="fb77c-136">Siga las instrucciones en el Asistente para la que se abre.</span><span class="sxs-lookup"><span data-stu-id="fb77c-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="fb77c-137">Para obtener información acerca de los elementos del asistente, vea</span><span class="sxs-lookup"><span data-stu-id="fb77c-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="fb77c-138">Una aplicación de sucursal con funciones de supervivencia sólo puede asociarse con un almacén de supervisión.</span><span class="sxs-lookup"><span data-stu-id="fb77c-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="fb77c-139">Si no se usa un servidor o una aplicación de sucursal con funciones de supervivencia en este sitio, desactive la casilla de verificación **Abrir el Asistente nuevo con funciones de supervivencia cuando se cierre este asistente** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="fb77c-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="fb77c-140">Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.</span><span class="sxs-lookup"><span data-stu-id="fb77c-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    


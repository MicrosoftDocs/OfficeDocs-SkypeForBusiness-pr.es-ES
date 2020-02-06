---
title: Restablecer el control de admisión de llamadas
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
description: Si un grupo de servidores front-end heredado hospeda Call Admission Control (CAC), debe mover el alojamiento CAC a un grupo de servidores de Skype empresarial 2019 antes de poder quitar el grupo de aplicaciones para usuario heredado.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812808"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="a79bf-103">Restablecer el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="a79bf-103">Reset call admission control</span></span>

<span data-ttu-id="a79bf-104">Si un grupo de servidores front-end heredado hospeda Call Admission Control (CAC), debe mover el alojamiento CAC a un grupo de servidores de Skype empresarial 2019 antes de poder quitar el grupo de aplicaciones para usuario heredado.</span><span class="sxs-lookup"><span data-stu-id="a79bf-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="a79bf-105">Para restablecer CAC</span><span class="sxs-lookup"><span data-stu-id="a79bf-105">To reset CAC</span></span>

1. <span data-ttu-id="a79bf-106">Abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="a79bf-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="a79bf-107">Haga clic con el botón secundario en el nodo del sitio y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a79bf-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a79bf-108">En **configuración de control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a79bf-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="a79bf-109">En **grupo de servidores front-end para ejecutar el controlador de admisión de llamadas (CAC)**, seleccione el grupo de servidores de Skype empresarial 2019 que va a alojar CAC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a79bf-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="a79bf-110">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="a79bf-110">Publish the topology.</span></span>
    


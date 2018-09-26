---
title: Restablecer el control de admisión de llamadas
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un grupo de servidores Front-End heredado hospeda el control de admisión de llamadas (CAC), debe mover CAC que hospeda a un Skype para Business Server 2019 grupo para poder quitar el grupo de servidores Front-End heredado.
ms.openlocfilehash: 65d56d000c5bcec5f7aae73413c287dee8ab29ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027322"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="1736f-103">Restablecer el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="1736f-103">Reset call admission control</span></span>

<span data-ttu-id="1736f-104">Si un grupo de servidores Front-End heredado hospeda el control de admisión de llamadas (CAC), debe mover CAC que hospeda a un Skype para Business Server 2019 grupo para poder quitar el grupo de servidores Front-End heredado.</span><span class="sxs-lookup"><span data-stu-id="1736f-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="1736f-105">Para restablecer el CAC</span><span class="sxs-lookup"><span data-stu-id="1736f-105">To reset CAC</span></span>

1. <span data-ttu-id="1736f-106">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="1736f-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="1736f-107">Haga clic en el nodo del sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1736f-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="1736f-108">En el cuadro **configuración de Control de admisión de llamadas**, asegúrese de que **Habilitar el Control de admisión de llamadas** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1736f-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="1736f-109">En el **grupo de servidores Front-End para ejecutar el control de admisión de llamadas (CAC)**, seleccione el Skype para Business Server 2019 del grupo que va a alojar el CAC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1736f-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="1736f-110">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="1736f-110">Publish the topology.</span></span>
    


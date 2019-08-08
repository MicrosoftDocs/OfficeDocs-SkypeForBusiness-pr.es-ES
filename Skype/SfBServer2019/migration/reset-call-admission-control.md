---
title: Restablecer el control de admisión de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un grupo de servidores front-end heredado hospeda Call Admission Control (CAC), debe mover el alojamiento CAC a un grupo de servidores de Skype empresarial 2019 antes de poder quitar el grupo de aplicaciones para usuario heredado.
ms.openlocfilehash: 812391eda436906020c41b14a53c8ea18c4b1aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241328"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="942b5-103">Restablecer el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="942b5-103">Reset call admission control</span></span>

<span data-ttu-id="942b5-104">Si un grupo de servidores front-end heredado hospeda Call Admission Control (CAC), debe mover el alojamiento CAC a un grupo de servidores de Skype empresarial 2019 antes de poder quitar el grupo de aplicaciones para usuario heredado.</span><span class="sxs-lookup"><span data-stu-id="942b5-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="942b5-105">Para restablecer CAC</span><span class="sxs-lookup"><span data-stu-id="942b5-105">To reset CAC</span></span>

1. <span data-ttu-id="942b5-106">Abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="942b5-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="942b5-107">Haga clic con el botón secundario en el nodo del sitio y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="942b5-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="942b5-108">En **configuración de control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="942b5-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="942b5-109">En **grupo de servidores front-end para ejecutar el controlador de admisión de llamadas (CAC)**, seleccione el grupo de servidores de Skype empresarial 2019 que va a alojar CAC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="942b5-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="942b5-110">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="942b5-110">Publish the topology.</span></span>
    


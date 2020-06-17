---
title: Restablecer el control de admisión de llamadas
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
description: Si un grupo de servidores front-end heredado hospeda el control de admisión de llamadas (CAC), debe mover el hospedaje de CAC a un grupo de servidores de Skype empresarial Server 2019 antes de poder quitar el grupo de servidores front-end heredado.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753302"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="4b062-103">Restablecer el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="4b062-103">Reset call admission control</span></span>

<span data-ttu-id="4b062-104">Si un grupo de servidores front-end heredado hospeda el control de admisión de llamadas (CAC), debe mover el hospedaje de CAC a un grupo de servidores de Skype empresarial Server 2019 antes de poder quitar el grupo de servidores front-end heredado.</span><span class="sxs-lookup"><span data-stu-id="4b062-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="4b062-105">Para restablecer el CAC</span><span class="sxs-lookup"><span data-stu-id="4b062-105">To reset CAC</span></span>

1. <span data-ttu-id="4b062-106">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="4b062-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="4b062-107">Haga clic con el botón secundario en el nodo del sitio y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4b062-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="4b062-108">En el parámetro **Control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** esté activado.</span><span class="sxs-lookup"><span data-stu-id="4b062-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="4b062-109">En **grupo de servidores front-end para ejecutar el control de admisión de llamadas (CAC)**, seleccione el grupo de servidores de Skype empresarial Server 2019 que va a hospedar el CAC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b062-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="4b062-110">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="4b062-110">Publish the topology.</span></span>
    


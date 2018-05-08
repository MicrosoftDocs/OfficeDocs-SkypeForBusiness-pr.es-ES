---
title: Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenga información acerca de las reglas de normalización para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: c637240d4c193bbec05228d167d77f7bd18c0d04
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="a4257-103">Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="a4257-103">Verify normalization rules for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="a4257-104">Obtenga información acerca de las reglas de normalización para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a4257-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a4257-105">No se deben normalizar órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a4257-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="a4257-106">Revise sus planes de marcado para comprobar que los números de órbita no estén normalizados.</span><span class="sxs-lookup"><span data-stu-id="a4257-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="a4257-107">Si debe crear una regla de normalización adicionales para evitar que su Órbitas que se normalizará, siga el procedimiento descrito en [crear o modificar un plan de marcado de Skype para Business Server 2015](dial-plans.md) para definir una nueva regla de normalización, por lo que este **modelo de coincidencia** identifica el intervalo de Órbitas y **patrón de traducción** es **$1**.</span><span class="sxs-lookup"><span data-stu-id="a4257-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="a4257-108">Por ejemplo, si el intervalo de órbitas de estacionamiento de llamadas se 7000-7999, el **modelo de coincidencia** es **^(7\d{3})$** y **patrón de traducción** es **$1**.</span><span class="sxs-lookup"><span data-stu-id="a4257-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a4257-109">Asegúrese de que la regla de normalización de forma predeterminada en los planes de marcado no contenga **^(\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="a4257-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="a4257-110">De lo contrario, nunca se ejecutará la regla de normalización de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a4257-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a4257-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4257-111">See also</span></span>

#### 

[<span data-ttu-id="a4257-112">Crear o modificar un plan de marcado de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a4257-112">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)


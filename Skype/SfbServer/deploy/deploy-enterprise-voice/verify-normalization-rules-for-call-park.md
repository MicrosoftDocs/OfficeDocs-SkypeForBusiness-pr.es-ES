---
title: Comprobar reglas de normalización para el parque de llamadas en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenga más información sobre las reglas de normalización de llamadas en la telefonía IP empresarial de Skype empresarial.
ms.openlocfilehash: 769d9f9becccf4df24a33a11e8814350cfb091e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766893"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="80695-103">Comprobar reglas de normalización para el parque de llamadas en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="80695-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="80695-104">Obtenga más información sobre las reglas de normalización de llamadas en la telefonía IP empresarial de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="80695-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="80695-105">Las órbitas del parque de llamadas no deben normalizarse.</span><span class="sxs-lookup"><span data-stu-id="80695-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="80695-106">Revise sus planes de marcado para comprobar que los números de órbita no estén normalizados.</span><span class="sxs-lookup"><span data-stu-id="80695-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="80695-107">Si tiene que crear una regla de normalización adicional para evitar que las órbitas se normalizaran, siga el procedimiento de [crear o modificar un plan de marcado en Skype empresarial Server](dial-plans.md) para definir una nueva regla de normalización, de modo que el **patrón para que coincida** identifique el intervalo de la órbita y el **patrón de traducción** es de **$1**.</span><span class="sxs-lookup"><span data-stu-id="80695-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="80695-108">Por ejemplo, si el intervalo de llamadas de la órbita de la órbita es 7000-7999, el **patrón de coincidencia** es **{3}^ (7 \ d) $** y el **patrón de traducción** es **$1**.</span><span class="sxs-lookup"><span data-stu-id="80695-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="80695-109">Asegúrese de que la regla de normalización predeterminada en los planes de marcado no contiene **^\*(\d)**.</span><span class="sxs-lookup"><span data-stu-id="80695-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="80695-110">En caso contrario, la regla de normalización del parque de llamadas nunca se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="80695-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="80695-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="80695-111">See also</span></span>

[<span data-ttu-id="80695-112">Crear o modificar un plan de marcado en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="80695-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)


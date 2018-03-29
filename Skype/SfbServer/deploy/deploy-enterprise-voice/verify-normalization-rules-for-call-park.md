---
title: Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenga información acerca de las reglas de normalización para el parque de llamada en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 4f3651394bbdb5556a83aa34739a86f8d06f1396
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="237ec-103">Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="237ec-103">Verify normalization rules for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="237ec-104">Obtenga información acerca de las reglas de normalización para el parque de llamada en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="237ec-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="237ec-105">No se deben normalizar las órbitas de llamada Park.</span><span class="sxs-lookup"><span data-stu-id="237ec-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="237ec-106">Revise sus planes de marcado para comprobar que los números de órbita no estén normalizados.</span><span class="sxs-lookup"><span data-stu-id="237ec-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="237ec-107">Si debe crear una regla de normalización adicionales para evitar que sus órbitas se normalizan, siga el procedimiento de [crear o modificar un plan de marcado de Skype para Business Server 2015](dial-plans.md) para definir una nueva regla de normalización, por lo que este **modelo de coincidencia** identifica el intervalo de órbita y **modelo de traducción** es **$1**.</span><span class="sxs-lookup"><span data-stu-id="237ec-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="237ec-108">Por ejemplo, si el rango de la órbita de llamada Park es 7000 a 7999, el **modelo de coincidencia** es **^ (7\d {3}) $** y **el modelo de traducción** es **$1**.</span><span class="sxs-lookup"><span data-stu-id="237ec-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="237ec-109">Asegúrese de que no contiene la regla de normalización predeterminada en los planes de marcado **^(\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="237ec-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="237ec-110">De lo contrario, nunca se ejecutará la regla de normalización llamada Park.</span><span class="sxs-lookup"><span data-stu-id="237ec-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="237ec-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="237ec-111">See also</span></span>

#### 

[<span data-ttu-id="237ec-112">Crear o modificar un plan de marcado de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="237ec-112">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)


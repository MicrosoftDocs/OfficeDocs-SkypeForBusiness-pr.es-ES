---
title: Planear el control remoto de llamadas en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: El control remoto de llamadas era una característica de versiones anteriores de Lync Server que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype empresarial Server, esta característica se ha sustituido por una llamada por trabajo. En las versiones de cliente de Skype empresarial Server 2015 y en adelante, el control remoto de llamadas ya no está disponible para su configuración en el cliente y se ha eliminado para su uso.
ms.openlocfilehash: 67010a0bc74ef46dcf204e3b2a905be87c182daf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802510"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="30c01-105">Planear el control remoto de llamadas en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="30c01-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="30c01-106">El control remoto de llamadas era una característica de versiones anteriores de Lync Server que permitía a los usuarios controlar sus teléfonos PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30c01-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="30c01-107">En Skype empresarial Server, esta característica se ha sustituido por una llamada por trabajo.</span><span class="sxs-lookup"><span data-stu-id="30c01-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="30c01-108">*En las versiones de cliente de Skype empresarial Server 2015 y en adelante, el control remoto de llamadas ya no está disponible para su configuración en el cliente y se ha eliminado para su uso.*</span><span class="sxs-lookup"><span data-stu-id="30c01-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="30c01-109">El control remoto de llamadas los usuarios de su organización que estén alojados en servidores front-end que ejecuten Lync Server pueden continuar usando el control remoto de llamadas, incluso si usan un cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="30c01-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="30c01-110">Sin embargo, para los usuarios alojados en Skype empresarial Server, no se admite el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="30c01-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="30c01-111">Consulte la siguiente tabla para ver las combinaciones de servidor o cliente y si admiten el control remoto de llamadas o Vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="30c01-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="30c01-112">**Cliente de Skype empresarial con la interfaz de usuario de Skype habilitada**</span><span class="sxs-lookup"><span data-stu-id="30c01-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="30c01-113">**Cliente de Skype empresarial con IU de Lync habilitada**</span><span class="sxs-lookup"><span data-stu-id="30c01-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="30c01-114">**Cliente de Skype empresarial 2016**</span><span class="sxs-lookup"><span data-stu-id="30c01-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="30c01-115">**Cliente de Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="30c01-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="30c01-116">**Lync 2010 Client**</span><span class="sxs-lookup"><span data-stu-id="30c01-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="30c01-117">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="30c01-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="30c01-118">Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="30c01-118">Call via Work</span></span>  <br/> |<span data-ttu-id="30c01-119">1</span><span class="sxs-lookup"><span data-stu-id="30c01-119">1</span></span> <br/> |<span data-ttu-id="30c01-120">Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="30c01-120">Call via Work</span></span>  <br/> |<span data-ttu-id="30c01-121">1</span><span class="sxs-lookup"><span data-stu-id="30c01-121">1</span></span> <br/> |<span data-ttu-id="30c01-122">1</span><span class="sxs-lookup"><span data-stu-id="30c01-122">1</span></span> <br/> |
| <span data-ttu-id="30c01-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30c01-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="30c01-124">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="30c01-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="30c01-125">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="30c01-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="30c01-126">uno</span><span class="sxs-lookup"><span data-stu-id="30c01-126">1</span></span> <br/> |<span data-ttu-id="30c01-127">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="30c01-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="30c01-128">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="30c01-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="30c01-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="30c01-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="30c01-130">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="30c01-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="30c01-131">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="30c01-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="30c01-132">uno</span><span class="sxs-lookup"><span data-stu-id="30c01-132">1</span></span> <br/> |<span data-ttu-id="30c01-133">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="30c01-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="30c01-134">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="30c01-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="30c01-135">Ninguna característica es compatible.</span><span class="sxs-lookup"><span data-stu-id="30c01-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="30c01-136">Para obtener más información, consulte [control remoto de llamadas](https://go.microsoft.com/fwlink/p/?LinkId=530208) en la documentación de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30c01-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="30c01-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="30c01-137">See also</span></span>

[<span data-ttu-id="30c01-138">Plan de llamadas por trabajo en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="30c01-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="30c01-139">Comparación de características de cliente de escritorio para Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="30c01-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="30c01-140">Realizar una llamada de Skype empresarial, pero con un teléfono PBX de escritorio para el audio</span><span class="sxs-lookup"><span data-stu-id="30c01-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)


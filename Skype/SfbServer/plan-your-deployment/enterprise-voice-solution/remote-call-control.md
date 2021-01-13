---
title: Planear el control remoto de llamadas en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: El control remoto de llamadas era una característica de versiones anteriores de Lync Server que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype Empresarial Server, esta característica se ha reemplazado por Vía trabajo. En las versiones de cliente de Skype Empresarial Server 2015 y en el futuro, el control remoto de llamadas ya no está disponible para configurarse en el cliente y se ha quitado para su uso.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813520"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="2eac4-105">Planear el control remoto de llamadas en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="2eac4-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="2eac4-106">El control remoto de llamadas era una característica de versiones anteriores de Lync Server que permitía a los usuarios controlar sus teléfonos PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2eac4-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="2eac4-107">En Skype Empresarial Server, esta característica se ha reemplazado por Vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="2eac4-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="2eac4-108">*En las versiones de cliente de Skype Empresarial Server 2015 y en el futuro, el control remoto de llamadas ya no está disponible para configurarse en el cliente y se ha quitado para su uso.*</span><span class="sxs-lookup"><span data-stu-id="2eac4-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="2eac4-109">Los usuarios de control remoto de llamadas de su organización que se encuentran en servidores front-end que ejecutan Lync Server pueden seguir usando el control remoto de llamadas, incluso si usan un cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="2eac4-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="2eac4-110">Sin embargo, para los usuarios que están en Skype Empresarial Server, no se admite el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2eac4-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="2eac4-111">Consulte la tabla siguiente para ver las combinaciones de servidor/cliente y si pueden admitir el control remoto de llamadas o Vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="2eac4-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="2eac4-112">**Cliente de Skype Empresarial con la interfaz de usuario de Skype habilitada**</span><span class="sxs-lookup"><span data-stu-id="2eac4-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="2eac4-113">**Cliente de Skype Empresarial con la interfaz de usuario de Lync habilitada**</span><span class="sxs-lookup"><span data-stu-id="2eac4-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="2eac4-114">**Cliente de Skype Empresarial 2016**</span><span class="sxs-lookup"><span data-stu-id="2eac4-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="2eac4-115">**Cliente de Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="2eac4-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="2eac4-116">**Cliente de Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="2eac4-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2eac4-117">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2eac4-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="2eac4-118">Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="2eac4-118">Call via Work</span></span>  <br/> |<span data-ttu-id="2eac4-119">1 </span><span class="sxs-lookup"><span data-stu-id="2eac4-119">1</span></span> <br/> |<span data-ttu-id="2eac4-120">Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="2eac4-120">Call via Work</span></span>  <br/> |<span data-ttu-id="2eac4-121">1 </span><span class="sxs-lookup"><span data-stu-id="2eac4-121">1</span></span> <br/> |<span data-ttu-id="2eac4-122">1 </span><span class="sxs-lookup"><span data-stu-id="2eac4-122">1</span></span> <br/> |
| <span data-ttu-id="2eac4-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eac4-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="2eac4-124">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="2eac4-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="2eac4-125">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="2eac4-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="2eac4-126">1 </span><span class="sxs-lookup"><span data-stu-id="2eac4-126">1</span></span> <br/> |<span data-ttu-id="2eac4-127">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="2eac4-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="2eac4-128">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="2eac4-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="2eac4-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2eac4-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="2eac4-130">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="2eac4-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="2eac4-131">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="2eac4-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="2eac4-132">1 </span><span class="sxs-lookup"><span data-stu-id="2eac4-132">1</span></span> <br/> |<span data-ttu-id="2eac4-133">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="2eac4-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="2eac4-134">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="2eac4-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="2eac4-135">No se admite ninguna característica.</span><span class="sxs-lookup"><span data-stu-id="2eac4-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="2eac4-136">Para obtener más información, [consulte Control remoto de](https://go.microsoft.com/fwlink/p/?LinkId=530208) llamadas en la documentación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2eac4-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2eac4-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="2eac4-137">See also</span></span>

[<span data-ttu-id="2eac4-138">Plan for Call Via Work in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2eac4-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="2eac4-139">Comparación de características de cliente de escritorio para Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="2eac4-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="2eac4-140">Realizar una llamada de Skype Empresarial pero usar el teléfono de escritorio PBX para audio</span><span class="sxs-lookup"><span data-stu-id="2eac4-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)


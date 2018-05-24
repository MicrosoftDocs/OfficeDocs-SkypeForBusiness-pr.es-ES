---
title: Planificar el control remoto de llamadas en Skype Empresarial 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Control remoto de llamadas era una característica en versiones anteriores de Lync Server que habilita a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype para Business Server, esta característica se ha reemplazado con llamar vía trabajo. En las versiones de cliente de Skype para Business Server 2015 y continuas de llamadas hacia delante remoto control ya no está disponible para configurar en el cliente y se ha quitado para su uso.
ms.openlocfilehash: e3a8031a79d547a279b377a45e1e8461cd47a2e7
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="plan-for-remote-call-control-in-skype-for-business-2015"></a><span data-ttu-id="9515b-105">Planificar el control remoto de llamadas en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="9515b-105">Plan for remote call control in Skype for Business 2015</span></span>
 
<span data-ttu-id="9515b-106">Control remoto de llamadas era una característica en versiones anteriores de Lync Server que habilita a los usuarios controlar sus teléfonos PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9515b-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="9515b-107">En Skype para Business Server, esta característica se ha reemplazado con llamar vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="9515b-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="9515b-108">*En las versiones de cliente de Skype para Business Server 2015 y continuas de llamadas hacia delante remoto control ya no está disponible para configurar en el cliente y se ha quitado para su uso.*</span><span class="sxs-lookup"><span data-stu-id="9515b-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="9515b-109">Usuarios de control remoto de llamadas de la organización que están hospedados en los servidores Front-End que ejecutan Lync Server pueden seguir usando el control remoto de llamadas, incluso si están utilizando un Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="9515b-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="9515b-110">Sin embargo, para los usuarios alojados en Skype para Business Server, no se admite el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9515b-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="9515b-111">Consulte la siguiente tabla para ver las combinaciones de servidor o cliente y si admiten el control remoto de llamadas o Vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="9515b-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="9515b-112">**Skype para profesionales 2015 cliente With Skype la interfaz de usuario habilitado**</span><span class="sxs-lookup"><span data-stu-id="9515b-112">**Skype for Business 2015 Client With Skype UI enabled**</span></span>|<span data-ttu-id="9515b-113">**Skype para profesionales 2015 cliente With Lync la interfaz de usuario habilitado**</span><span class="sxs-lookup"><span data-stu-id="9515b-113">**Skype for Business 2015 Client With Lync UI enabled**</span></span>|<span data-ttu-id="9515b-114">**Skype para profesionales de 2016 cliente**</span><span class="sxs-lookup"><span data-stu-id="9515b-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="9515b-115">**Cliente de Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="9515b-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="9515b-116">**Cliente de Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="9515b-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="9515b-117">Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9515b-117">Skype for Business Server 2015</span></span> <br/> |<span data-ttu-id="9515b-118">Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="9515b-118">Call via Work</span></span>  <br/> |<span data-ttu-id="9515b-119">1</span><span class="sxs-lookup"><span data-stu-id="9515b-119">1</span></span> <br/> |<span data-ttu-id="9515b-120">Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="9515b-120">Call via Work</span></span>  <br/> |<span data-ttu-id="9515b-121">1</span><span class="sxs-lookup"><span data-stu-id="9515b-121">1</span></span> <br/> |<span data-ttu-id="9515b-122">1</span><span class="sxs-lookup"><span data-stu-id="9515b-122">1</span></span> <br/> |
| <span data-ttu-id="9515b-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9515b-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="9515b-124">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="9515b-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="9515b-125">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="9515b-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="9515b-126">1</span><span class="sxs-lookup"><span data-stu-id="9515b-126">1</span></span> <br/> |<span data-ttu-id="9515b-127">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="9515b-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="9515b-128">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="9515b-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="9515b-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9515b-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="9515b-130">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="9515b-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="9515b-131">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="9515b-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="9515b-132">1</span><span class="sxs-lookup"><span data-stu-id="9515b-132">1</span></span> <br/> |<span data-ttu-id="9515b-133">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="9515b-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="9515b-134">Control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="9515b-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="9515b-135">Se admite ninguna característica.</span><span class="sxs-lookup"><span data-stu-id="9515b-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="9515b-136">Para obtener más información, vea [Control remoto de llamadas](https://go.microsoft.com/fwlink/p/?LinkId=530208) en la documentación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9515b-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9515b-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="9515b-137">See also</span></span>

#### 

[<span data-ttu-id="9515b-138">Planeación de la llamada vía trabajo en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9515b-138">Plan for Call Via Work in Skype for Business Server 2015</span></span>](call-via-work.md)
  
[<span data-ttu-id="9515b-139">Comparación de características de cliente de escritorio de Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="9515b-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="9515b-140">Realizar una Skype para llamada de negocio pero usar su teléfono de escritorio PBX para audio</span><span class="sxs-lookup"><span data-stu-id="9515b-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)


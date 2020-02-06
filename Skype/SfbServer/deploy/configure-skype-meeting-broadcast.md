---
title: Configurar la implementación local para la difusión de reunión de Skype
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
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumen: Obtenga información sobre los pasos que debe realizar para configurar la difusión de reunión de Skype para su implementación híbrida local de Skype empresarial Server.'
ms.openlocfilehash: 8bdbb163f5ef867711ce109bc923ba0ec8401ffa
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790948"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="ca0b3-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="ca0b3-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="ca0b3-104">**Resumen:** Obtenga más información sobre los pasos que debe realizar para configurar la difusión de reunión de Skype para su implementación híbrida de Skype empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="ca0b3-105">Difusión de reunión de Skype es un servicio en línea que forma parte de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="ca0b3-106">Si está ejecutando Skype empresarial Server local y desea usar difusión de reunión de Skype en su entorno, tendrá que seguir los pasos de configuración de este tema.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="ca0b3-107">Antes de empezar, debe configurar su entorno para que sea híbrido con Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="ca0b3-108">Para más información, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) y [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="ca0b3-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="ca0b3-109">Configurar el entorno híbrido para difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="ca0b3-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="ca0b3-110">Tendrá que seguir estos pasos para preparar el entorno para la difusión de reunión de Skype:</span><span class="sxs-lookup"><span data-stu-id="ca0b3-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="ca0b3-111">Configurar la Federación con recursos de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="ca0b3-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="ca0b3-112">Configurar los dominios federados SIP</span><span class="sxs-lookup"><span data-stu-id="ca0b3-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="ca0b3-113">Configurar la Federación con recursos de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="ca0b3-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="ca0b3-114">Para habilitar la Federación con recursos de Skype empresarial online, debe configurar el acceso externo para un proveedor federado de SIP.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="ca0b3-115">Para hacerlo con el panel de control de Skype empresarial Server, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ca0b3-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="ca0b3-116">Inicie el panel de control de Skype empresarial Server y seleccione **acceso externo** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="ca0b3-117">Seleccione **Proveedores federados SIP** y haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="ca0b3-118">Configure el nuevo proveedor con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="ca0b3-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="ca0b3-119">**Habilitar las comunicaciones con este proveedor:**</span><span class="sxs-lookup"><span data-stu-id="ca0b3-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="ca0b3-120">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="ca0b3-120">Selected</span></span>  <br/> |
|<span data-ttu-id="ca0b3-121">**Nombre del proveedor:**</span><span class="sxs-lookup"><span data-stu-id="ca0b3-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="ca0b3-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="ca0b3-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="ca0b3-123">**Servicio perimetral de acceso (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="ca0b3-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="ca0b3-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca0b3-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="ca0b3-125">**Nivel de verificación predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="ca0b3-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="ca0b3-126">Permita a los usuarios comunicarse con todos los usuarios con este proveedor.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="ca0b3-127">También puede habilitar la Federación con recursos de Skype empresarial online ejecutando el siguiente cmdlet en el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="ca0b3-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="ca0b3-128">Configurar los dominios federados SIP</span><span class="sxs-lookup"><span data-stu-id="ca0b3-128">Configure SIP federated domains</span></span>

<span data-ttu-id="ca0b3-129">A continuación, debe agregar dominios federados SIP a la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="ca0b3-130">Repita estos pasos para cada uno de los dominios enumerados, mediante la creación de 4 nuevos dominios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="ca0b3-131">Estos dominios incluyen los centros de datos regionales que se usan en Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="ca0b3-132">Inicie el panel de control de Skype empresarial Server y seleccione **acceso externo** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="ca0b3-133">Seleccione **Dominios federados SIP** y haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="ca0b3-134">Para el **Nombre de dominio (o FQDN):**, especifique el dominio, repitiendo este procedimiento para cada uno de los siguientes dominios:</span><span class="sxs-lookup"><span data-stu-id="ca0b3-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="ca0b3-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca0b3-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="ca0b3-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca0b3-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="ca0b3-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca0b3-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="ca0b3-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca0b3-138">resources.lync.com</span></span>
    
<span data-ttu-id="ca0b3-139">También puede configurar el acceso externo para los dominios federados de SIP ejecutando los siguientes cmdlets en el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="ca0b3-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="ca0b3-140">Una vez que haya completado estos pasos de configuración, puede empezar a usar difusión de reunión de Skype en su implementación.</span><span class="sxs-lookup"><span data-stu-id="ca0b3-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="ca0b3-141">Para obtener más información sobre la difusión de reunión de Skype, vea [¿Qué es una difusión de reunión de Skype? y la](https://go.microsoft.com/fwlink/?LinkId=617071) [Guía de administrador de difusión de reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="ca0b3-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  


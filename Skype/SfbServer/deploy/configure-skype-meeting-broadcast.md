---
title: Configurar la implementación local para difusión de reunión de Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: obtenga información sobre los pasos que debe realizar para configurar la Difusión de reunión de Skype para su implementación híbrida de Skype Empresarial Server local.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820710"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="3b39c-103">Configurar la implementación local para difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="3b39c-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="3b39c-104">**Resumen:** Obtenga información sobre los pasos que debe realizar para configurar la Difusión de reunión de Skype para su implementación híbrida de Skype Empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="3b39c-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="3b39c-105">Difusión de reunión de Skype es un servicio en línea que forma parte de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b39c-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="3b39c-106">Si está ejecutando Skype Empresarial Server local y desea usar difusión de reunión de Skype en su entorno, tendrá que seguir los pasos de configuración de este tema.</span><span class="sxs-lookup"><span data-stu-id="3b39c-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="3b39c-107">Antes de empezar, el entorno debe configurarse para la implementación híbrida con Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="3b39c-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="3b39c-108">Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="3b39c-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="3b39c-109">Configurar el entorno híbrido para difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="3b39c-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="3b39c-110">Deberá hacer lo siguiente para preparar su entorno para difusión de reunión de Skype:</span><span class="sxs-lookup"><span data-stu-id="3b39c-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="3b39c-111">Configurar la federación con recursos de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3b39c-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="3b39c-112">Configurar dominios federados SIP</span><span class="sxs-lookup"><span data-stu-id="3b39c-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="3b39c-113">Configurar la federación con recursos de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="3b39c-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="3b39c-114">Para habilitar la federación con recursos de Skype Empresarial Online, debe configurar el acceso externo para un proveedor federado SIP.</span><span class="sxs-lookup"><span data-stu-id="3b39c-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="3b39c-115">Para ello, use el Panel de control de Skype Empresarial Server, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3b39c-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="3b39c-116">Inicie el Panel de control de Skype Empresarial Server y seleccione **Acceso externo** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="3b39c-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="3b39c-117">Seleccione **Proveedores federados SIP y** haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3b39c-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="3b39c-118">Configure el nuevo proveedor con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3b39c-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="3b39c-119">**Habilite las comunicaciones con este proveedor:**</span><span class="sxs-lookup"><span data-stu-id="3b39c-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="3b39c-120">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="3b39c-120">Selected</span></span>  <br/> |
|<span data-ttu-id="3b39c-121">**Nombre del proveedor:**</span><span class="sxs-lookup"><span data-stu-id="3b39c-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="3b39c-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="3b39c-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="3b39c-123">**Servicio perimetral de acceso (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="3b39c-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="3b39c-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="3b39c-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="3b39c-125">**Nivel de verificación predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="3b39c-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="3b39c-126">Permitir que los usuarios se comuniquen con todos los usuarios que usan este proveedor.</span><span class="sxs-lookup"><span data-stu-id="3b39c-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="3b39c-127">También puede habilitar la federación con recursos de Skype Empresarial Online ejecutando el siguiente cmdlet en el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="3b39c-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="3b39c-128">Configurar dominios federados SIP</span><span class="sxs-lookup"><span data-stu-id="3b39c-128">Configure SIP federated domains</span></span>

<span data-ttu-id="3b39c-129">A continuación, debe agregar dominios federados SIP a la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="3b39c-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="3b39c-130">Repita estos pasos para cada uno de los dominios enumerados y cree 4 nuevos dominios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="3b39c-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="3b39c-131">Estos dominios son para los centros de datos regionales usados en Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="3b39c-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="3b39c-132">Inicie el Panel de control de Skype Empresarial Server y seleccione **Acceso externo** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="3b39c-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="3b39c-133">Seleccione **Dominios federados SIP y** haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3b39c-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="3b39c-134">Para el **nombre de dominio (o FQDN):**, escriba el dominio, repitiendo este procedimiento para cada uno de los siguientes dominios:</span><span class="sxs-lookup"><span data-stu-id="3b39c-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="3b39c-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3b39c-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="3b39c-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3b39c-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="3b39c-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3b39c-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="3b39c-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="3b39c-138">resources.lync.com</span></span>
    
<span data-ttu-id="3b39c-139">También puede configurar el acceso externo para los dominios federados SIP ejecutando los cmdlets siguientes en el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="3b39c-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="3b39c-140">Una vez que haya completado estos pasos de configuración, puede empezar a usar Difusión de reunión de Skype en su implementación.</span><span class="sxs-lookup"><span data-stu-id="3b39c-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="3b39c-141">Para obtener más información acerca de difusión de reunión de Skype, consulte ¿Qué es [una Difusión](https://go.microsoft.com/fwlink/?LinkId=617071) de reunión de Skype? y guía de administración de [difusión de reunión de Skype.](https://go.microsoft.com/fwlink/?LinkId=617075)</span><span class="sxs-lookup"><span data-stu-id="3b39c-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  


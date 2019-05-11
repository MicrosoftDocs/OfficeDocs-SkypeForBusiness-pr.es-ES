---
title: Configurar la implementación local para la difusión de reunión de Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumen: Obtenga información sobre los pasos que necesarios para llevar a cabo para configurar Difundir presentación de reunión de Skype para su Skype local para la implementación híbrida de Business Server.'
ms.openlocfilehash: 4eb117715905a9d371b725c8da7a992b9fdee6b4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894207"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="870a6-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="870a6-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="870a6-104">**Resumen:** Obtenga información sobre los pasos que necesarios para llevar a cabo para configurar Difundir presentación de reunión de Skype para su Skype local para la implementación híbrida de Business Server.</span><span class="sxs-lookup"><span data-stu-id="870a6-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="870a6-105">Difundir presentación de reunión de Skype es un servicio en línea que forma parte de Office 365.</span><span class="sxs-lookup"><span data-stu-id="870a6-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="870a6-106">Si está ejecutando Skype para Business Server local y desea usar Difundir presentación de reunión de Skype en su entorno, debe seguir los pasos de configuración en este tema.</span><span class="sxs-lookup"><span data-stu-id="870a6-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="870a6-107">Antes de empezar, el entorno debe configurarse para la implementación híbrida con Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="870a6-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="870a6-108">Para más información, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) y [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="870a6-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="870a6-109">Configurar su entorno híbrido para difundir presentación de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="870a6-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="870a6-110">Debe hacer lo siguiente para preparar su entorno para difundir presentación de reunión de Skype:</span><span class="sxs-lookup"><span data-stu-id="870a6-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="870a6-111">Configurar la federación con Skype para recursos en línea de negocio</span><span class="sxs-lookup"><span data-stu-id="870a6-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="870a6-112">Configurar los dominios federados SIP</span><span class="sxs-lookup"><span data-stu-id="870a6-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="870a6-113">Configurar la federación con Skype para recursos en línea de negocio</span><span class="sxs-lookup"><span data-stu-id="870a6-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="870a6-114">Para habilitar la federación con Skype para recursos en línea de negocio, debe configurar el acceso externo para un proveedor SIP federado.</span><span class="sxs-lookup"><span data-stu-id="870a6-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="870a6-115">Para llevar a cabo mediante el uso de la Skype para el Panel de Control de Business Server, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="870a6-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="870a6-116">Inicie el Skype para el Panel de Control de servidor empresarial y seleccione **Acceso externo** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="870a6-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="870a6-117">Seleccione **Proveedores federados SIP** y haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="870a6-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="870a6-118">Configure el nuevo proveedor con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="870a6-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="870a6-119">**Habilitar las comunicaciones con este proveedor:**</span><span class="sxs-lookup"><span data-stu-id="870a6-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="870a6-120">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="870a6-120">Selected</span></span>  <br/> |
|<span data-ttu-id="870a6-121">**Nombre del proveedor:**</span><span class="sxs-lookup"><span data-stu-id="870a6-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="870a6-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="870a6-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="870a6-123">**Servicio perimetral de acceso (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="870a6-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="870a6-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="870a6-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="870a6-125">**Nivel de verificación predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="870a6-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="870a6-126">Permita a los usuarios comunicarse con todos los usuarios con este proveedor.</span><span class="sxs-lookup"><span data-stu-id="870a6-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="870a6-127">También puede habilitar la federación con Skype para recursos en línea de negocio ejecutando el siguiente cmdlet en el Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="870a6-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="870a6-128">Configurar los dominios federados SIP</span><span class="sxs-lookup"><span data-stu-id="870a6-128">Configure SIP federated domains</span></span>

<span data-ttu-id="870a6-129">A continuación, deberá agregar dominios federados SIP a la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="870a6-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="870a6-130">Repita estos pasos para cada uno de los dominios enumerados, mediante la creación de 4 nuevos dominios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="870a6-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="870a6-131">Incluyen estos dominios son para los datos regionales centros usados en Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="870a6-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="870a6-132">Inicie el Skype para el Panel de Control de servidor empresarial y seleccione **Acceso externo** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="870a6-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="870a6-133">Seleccione **Dominios federados SIP** y haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="870a6-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="870a6-134">Para el **Nombre de dominio (o FQDN):**, especifique el dominio, repitiendo este procedimiento para cada uno de los siguientes dominios:</span><span class="sxs-lookup"><span data-stu-id="870a6-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="870a6-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="870a6-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="870a6-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="870a6-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="870a6-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="870a6-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="870a6-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="870a6-138">resources.lync.com</span></span>
    
<span data-ttu-id="870a6-139">También puede configurar el acceso externo para los dominios federados SIP mediante la ejecución de los siguientes cmdlets en el Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="870a6-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="870a6-140">Una vez que haya completado estos pasos de configuración puede empezar a usar Difundir presentación de reunión de Skype en su implementación.</span><span class="sxs-lookup"><span data-stu-id="870a6-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="870a6-141">Para obtener más información acerca de la difusión de reunión de Skype, vea [¿Qué es una reunión de Skype difusión?](https://go.microsoft.com/fwlink/?LinkId=617071) y [Guía de administración de Difundir presentación de Skype reunión](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="870a6-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  


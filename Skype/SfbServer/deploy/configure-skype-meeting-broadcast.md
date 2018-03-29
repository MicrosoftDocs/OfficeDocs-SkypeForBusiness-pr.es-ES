---
title: Configurar la implementación local para la difusión de reunión de Skype
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
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
description: 'Resumen: Conozca los pasos que debe realizar para configurar difusión de reunión de Skype para tu Skype local para la implementación de Business Server híbrido.'
ms.openlocfilehash: e788a263223ea3fa0f4ce9ed844fb5b4eb0ae898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="c99fb-103">Configurar la implementación local para la difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="c99fb-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="c99fb-104">**Resumen:** Obtenga información acerca de los pasos que debe realizar para configurar difusión de reunión de Skype para tu Skype local para la implementación de Business Server híbrido.</span><span class="sxs-lookup"><span data-stu-id="c99fb-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="c99fb-105">Difundir reunión de Skype es un servicio en línea que forma parte de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c99fb-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="c99fb-106">Si está ejecutando Skype para Business Server local y desea utilizar Skype reunión difusión en su entorno, debe seguir los pasos de este tema.</span><span class="sxs-lookup"><span data-stu-id="c99fb-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="c99fb-107">Antes de comenzar, su entorno debe configurarse para híbrido con Skype para los negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="c99fb-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="c99fb-108">Para obtener más información, vea [Planear la conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) y [conectividad de implementación híbrida entre Skype para Business Server y Skype para los negocios en línea](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c99fb-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="c99fb-109">Configurar el entorno de híbrido para difundir reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="c99fb-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="c99fb-110">Debe hacer lo siguiente para preparar el entorno para difundir reunión de Skype:</span><span class="sxs-lookup"><span data-stu-id="c99fb-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="c99fb-111">Configurar la federación con Skype para recursos en línea de negocio</span><span class="sxs-lookup"><span data-stu-id="c99fb-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="c99fb-112">Configurar los dominios federados SIP</span><span class="sxs-lookup"><span data-stu-id="c99fb-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="c99fb-113">Configurar la federación con Skype para recursos en línea de negocio</span><span class="sxs-lookup"><span data-stu-id="c99fb-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="c99fb-114">Para habilitar la federación con Skype para recursos en línea de negocio, debe configurar el acceso externo de un proveedor de SIP federados.</span><span class="sxs-lookup"><span data-stu-id="c99fb-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="c99fb-115">Para ello utilizando el Skype para Panel de Control de Business Server, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c99fb-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="c99fb-116">Inicie el Skype para Business Server Control Panel y seleccione **Acceso externo** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="c99fb-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="c99fb-117">Seleccione **Proveedores federados SIP** y haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c99fb-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="c99fb-118">Configure el nuevo proveedor con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="c99fb-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="c99fb-119">**Habilitar las comunicaciones con este proveedor:**</span><span class="sxs-lookup"><span data-stu-id="c99fb-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="c99fb-120">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="c99fb-120">Selected</span></span>  <br/> |
|<span data-ttu-id="c99fb-121">**Nombre del proveedor:**</span><span class="sxs-lookup"><span data-stu-id="c99fb-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="c99fb-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="c99fb-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="c99fb-123">**Servicio perimetral de acceso (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="c99fb-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="c99fb-124">sipfed.Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="c99fb-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="c99fb-125">**Nivel de verificación predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="c99fb-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="c99fb-126">Permita a los usuarios comunicarse con todos los usuarios con este proveedor.</span><span class="sxs-lookup"><span data-stu-id="c99fb-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="c99fb-127">También puede habilitar la federación con Skype recursos empresariales en línea ejecutando el siguiente cmdlet en el Skype para el Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="c99fb-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="c99fb-128">Configurar los dominios federados SIP</span><span class="sxs-lookup"><span data-stu-id="c99fb-128">Configure SIP federated domains</span></span>

<span data-ttu-id="c99fb-129">A continuación, debe agregar dominios SIP federados a la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="c99fb-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="c99fb-130">Repita estos pasos para cada uno de los dominios enumerados, mediante la creación de 4 nuevos dominios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="c99fb-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="c99fb-131">Incluyen estos dominios son para los datos regionales centros utilizados en Skype para los negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="c99fb-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="c99fb-132">Inicie el Skype para Business Server Control Panel y seleccione **Acceso externo** a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="c99fb-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="c99fb-133">Seleccione **Dominios federados SIP** y haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c99fb-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="c99fb-134">Para el **Nombre de dominio (o FQDN):**, especifique el dominio, repitiendo este procedimiento para cada uno de los siguientes dominios:</span><span class="sxs-lookup"><span data-stu-id="c99fb-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
  - <span data-ttu-id="c99fb-135">noammeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="c99fb-135">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="c99fb-136">emeameetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="c99fb-136">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="c99fb-137">apacmeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="c99fb-137">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="c99fb-138">Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="c99fb-138">resources.lync.com</span></span>
    
<span data-ttu-id="c99fb-139">También puede configurar el acceso externo para dominios SIP federado ejecutando los siguientes cmdlets en el Skype para el Shell de administración de servidor de negocios:</span><span class="sxs-lookup"><span data-stu-id="c99fb-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "emeameetings.lync.com"
```

```
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="c99fb-140">Una vez haya completado estos pasos de configuración puede empezar a usar Skype reunión difusión en su implementación.</span><span class="sxs-lookup"><span data-stu-id="c99fb-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="c99fb-141">Para obtener más información acerca de la difusión de la reunión de Skype, consulte [¿Qué es una reunión de Skype difusión?](https://go.microsoft.com/fwlink/?LinkId=617071) y [Guía de administración de difundir reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="c99fb-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  


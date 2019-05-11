---
title: Implementar vía trabajo en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumen: Obtenga información sobre cómo implementar llamar vía trabajo en Skype para Business Server para algunos o todos los usuarios.'
ms.openlocfilehash: 3518d5a4d2977ae976450dff4e028365bebe0703
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893528"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="8f9dd-103">Implementar vía trabajo en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8f9dd-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="8f9dd-104">**Resumen:** Obtenga información sobre cómo implementar llamar vía trabajo en Skype para Business Server para algunos o todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="8f9dd-105">Siga estos pasos para implementar llamadas vía trabajo para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="8f9dd-106">Se describen las consideraciones de planeación en [Plan para llamar vía trabajo en Skype para Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="8f9dd-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="8f9dd-107">En versiones anteriores de llamada remota de Lync Server control era una característica que habilita a los usuarios controlar sus teléfonos PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="8f9dd-108">En Skype para Business Server, esta característica se ha reemplazado con llamar vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="8f9dd-109">Requisitos previos para la llamada vía trabajo</span><span class="sxs-lookup"><span data-stu-id="8f9dd-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="8f9dd-110">Llamar vía trabajo usa Unified Communications Web API (UCWA), que se instala automáticamente en Skype todos los servidores Front-End de Business Server.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="8f9dd-111">Para habilitar a los usuarios para llamar vía trabajo, también debe tener los siguientes requisitos previos en su lugar:</span><span class="sxs-lookup"><span data-stu-id="8f9dd-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="8f9dd-112">Debe tener un servidor de mediación implementados, ya sea como parte de un servidor Front-End o como una función independiente.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="8f9dd-113">Además, necesita implementar una puerta de enlace IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="8f9dd-114">Todos los usuarios que va a estar habilitados para llamar vía trabajo deben tener una llamada directa (DID) en el sistema de teléfono PBX.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="8f9dd-115">Debe habilitar a todos los usuarios de llamar vía trabajo para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="8f9dd-116">En este caso, debe configurar el Skype para número DID empresarial para cada usuario al número DID correspondiente para el sistema de teléfono PBX correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="8f9dd-117">Todos los usuarios que van a usar llamar vía trabajo deben tener **La configuración automática** seleccionado en su opción de **Conexiones avanzadas** en su Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="8f9dd-118">Esto permite que el cliente descubrir las direcciones URL de UCWA.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="8f9dd-119">La selección predeterminada es **Configuración automática**.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="8f9dd-120">Para cada usuario llamar vía trabajo, habilitar el desvío de llamadas y llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="8f9dd-121">Para cada usuario llamar vía trabajo, asegúrese de que estén habilitadas las conferencias telefónicas y salida de conferencia.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="8f9dd-122">Esto permite a estos usuarios obtener y desconectarse de Skype para conferencias de empresa.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="8f9dd-123">Asegúrese de que la delegación, llamada de equipo y grupo de respuesta se deshabilitan para todos los usuarios llamar vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="8f9dd-124">Implementar Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="8f9dd-124">Deploy Call Via Work</span></span>

<span data-ttu-id="8f9dd-125">Una vez que se cumplan los requisitos previos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f9dd-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="8f9dd-126">Crear un número de teléfono globales para la implementación que Skype para la empresa que se muestra en el identificador de autor de la llamada de la PBX de los usuarios que se va a realizar llamadas de llamar vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="8f9dd-127">Crear una o varias directivas de llamar vía trabajo</span><span class="sxs-lookup"><span data-stu-id="8f9dd-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="8f9dd-128">Asignar una directiva de llamada vía trabajo a cada usuario que va a estar habilitada para llamar vía trabajo</span><span class="sxs-lookup"><span data-stu-id="8f9dd-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="8f9dd-129">Crear el número de teléfono global de Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="8f9dd-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="8f9dd-130">Escriba el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="8f9dd-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="8f9dd-131">Por ejemplo, el siguiente cmdlet establece el número de teléfono global en 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="8f9dd-132">Crear directiva de Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="8f9dd-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="8f9dd-133">Escriba el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="8f9dd-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="8f9dd-134">Por ejemplo, el siguiente cmdlet crea una directiva de llamada vía trabajo denominada ContosoUser1CvWP, requiere que el usuario usar un número de devolución de llamada de administración y establece ese número de devolución de llamada a 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="8f9dd-135">Asignar una directiva de llamada vía trabajo a un usuario</span><span class="sxs-lookup"><span data-stu-id="8f9dd-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="8f9dd-136">Escriba el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="8f9dd-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="8f9dd-137">Por ejemplo, el siguiente cmdlet asigna la directiva de llamada vía trabajo "ContosoUser1CvWP" al usuario denominado **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="8f9dd-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="8f9dd-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f9dd-138">See also</span></span>

[<span data-ttu-id="8f9dd-139">Planeación de la llamada vía trabajo en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8f9dd-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)


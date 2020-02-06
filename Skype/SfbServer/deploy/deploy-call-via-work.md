---
title: Implementación de llamadas mediante el trabajo en Skype empresarial Server
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumen: Aprenda a implementar llamadas mediante el trabajo en Skype empresarial Server para algunos o todos los usuarios.'
ms.openlocfilehash: 9b77207d6618e4a869ae369697bc8395aba81673
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791088"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="ea003-103">Implementación de llamadas mediante el trabajo en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ea003-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="ea003-104">**Resumen:** Aprenda a implementar llamadas mediante el trabajo en Skype empresarial Server para algunos o todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ea003-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="ea003-105">Siga estos pasos para implementar llamadas por trabajo para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="ea003-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="ea003-106">Las consideraciones de planeación se tratan en [plan para llamar mediante el trabajo en Skype empresarial Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="ea003-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="ea003-107">En versiones anteriores de Lync Server, el control remoto de llamadas era una característica que permitía a los usuarios controlar sus teléfonos PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea003-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="ea003-108">En Skype empresarial Server, esta característica se ha sustituido por una llamada por trabajo.</span><span class="sxs-lookup"><span data-stu-id="ea003-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="ea003-109">Requisitos previos para llamar por trabajo</span><span class="sxs-lookup"><span data-stu-id="ea003-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="ea003-110">La llamada a través del trabajo usa la API Web de comunicaciones unificadas (UCWA), que se instala automáticamente en todos los servidores front-end de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ea003-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="ea003-111">Para habilitar a los usuarios para que realicen llamadas por trabajo, también debe disponer de los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="ea003-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="ea003-112">Debe tener un servidor de mediación implementado, ya sea como parte de un servidor front-end o como un rol independiente.</span><span class="sxs-lookup"><span data-stu-id="ea003-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="ea003-113">Además, necesita implementar una puerta de enlace IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="ea003-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="ea003-114">Todos los usuarios que vayan a estar habilitados para realizar llamadas a través del trabajo deben tener un marcado directo (en el sistema telefónico PBX).</span><span class="sxs-lookup"><span data-stu-id="ea003-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="ea003-115">Debe habilitar todas las llamadas a través de usuarios del trabajo para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="ea003-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="ea003-116">Al hacerlo, debe configurar el número de Skype empresarial realizado para cada usuario en el número de ha correspondiente al sistema telefónico PBX correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ea003-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="ea003-117">Todos los usuarios que vayan a usar las llamadas a través del trabajo deben tener la **configuración automática** seleccionada en la opción **conexiones avanzadas** en el cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="ea003-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="ea003-118">Esto permite al cliente descubrir las direcciones URL de UCWA.</span><span class="sxs-lookup"><span data-stu-id="ea003-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="ea003-119">La selección predeterminada es **Configuración automática**.</span><span class="sxs-lookup"><span data-stu-id="ea003-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="ea003-120">Para cada llamada a través de usuario del trabajo, habilitar el desvío de llamadas y las llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="ea003-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="ea003-121">Para cada llamada a través de usuario del trabajo, asegúrese de que la opción de conferencia de acceso telefónico local está habilitada.</span><span class="sxs-lookup"><span data-stu-id="ea003-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="ea003-122">Esto permite a estos usuarios entrar y salir de las conferencias de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="ea003-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="ea003-123">Asegúrese de que la delegación, la llamada de equipo y el grupo de respuesta estén deshabilitadas para cada llamada por usuario del trabajo.</span><span class="sxs-lookup"><span data-stu-id="ea003-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="ea003-124">Implementar Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="ea003-124">Deploy Call Via Work</span></span>

<span data-ttu-id="ea003-125">Una vez que se cumplan los requisitos previos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ea003-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="ea003-126">Cree un número de teléfono global para su implementación en el que se muestra Skype empresarial en la identificación de llamadas de PBX de los usuarios que hacen llamadas a través del trabajo.</span><span class="sxs-lookup"><span data-stu-id="ea003-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="ea003-127">Crear una o más llamadas a través de directivas de trabajo</span><span class="sxs-lookup"><span data-stu-id="ea003-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="ea003-128">Asignar una llamada a través de la Directiva de trabajo a cada usuario que se habilitará para realizar llamadas por trabajo</span><span class="sxs-lookup"><span data-stu-id="ea003-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="ea003-129">Crear el número de teléfono global de Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="ea003-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="ea003-130">Escriba el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea003-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="ea003-131">Por ejemplo, el siguiente cmdlet establece el número de teléfono global en 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="ea003-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="ea003-132">Crear directiva de Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="ea003-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="ea003-133">Escriba el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea003-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="ea003-134">Por ejemplo, el siguiente cmdlet crea una llamada a través de la Directiva de trabajo denominada ContosoUser1CvWP, requiere que el usuario Use un número de devolución de llamada de administrador y establece ese número de devolución de llamada en 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="ea003-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="ea003-135">Asignar una llamada a través de la Directiva de trabajo a un usuario</span><span class="sxs-lookup"><span data-stu-id="ea003-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="ea003-136">Escriba el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea003-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="ea003-137">Por ejemplo, el siguiente cmdlet asigna la llamada a través de la Directiva de trabajo "ContosoUser1CvWP" al usuario denominado **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="ea003-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="ea003-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea003-138">See also</span></span>

[<span data-ttu-id="ea003-139">Plan de llamadas por trabajo en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ea003-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)


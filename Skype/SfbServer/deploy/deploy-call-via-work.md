---
title: Implementar Vía trabajo en Skype Empresarial Server
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumen: obtenga información sobre cómo implementar Vía trabajo en Skype Empresarial Server para algunos o todos los usuarios.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825010"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="bf198-103">Implementar Vía trabajo en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bf198-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="bf198-104">**Resumen:** Obtenga información sobre cómo implementar Vía trabajo en Skype Empresarial Server para algunos o todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bf198-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="bf198-105">Siga estos pasos para implementar Vía trabajo para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bf198-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="bf198-106">Las consideraciones de planeación se analizan en [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span><span class="sxs-lookup"><span data-stu-id="bf198-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="bf198-107">En versiones anteriores del control remoto de llamadas de Lync Server era una característica que permitía a los usuarios controlar sus teléfonos PBX con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf198-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="bf198-108">En Skype Empresarial Server, esta característica se ha reemplazado por Vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="bf198-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="bf198-109">Requisitos previos para Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="bf198-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="bf198-110">Vía trabajo usa la API web de comunicaciones unificadas (UCWA), que se instala automáticamente en todos los servidores front-end de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bf198-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="bf198-111">Para habilitar a los usuarios para Vía trabajo, también debe tener los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="bf198-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="bf198-112">Debe tener implementado un servidor de mediación, ya sea como parte de un servidor front-end o como un rol independiente.</span><span class="sxs-lookup"><span data-stu-id="bf198-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="bf198-113">También debe implementar una puerta de enlace IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="bf198-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="bf198-114">Todos los usuarios que se habilitarán para Vía trabajo deben tener una llamada directa a la extensión (DID) en el sistema telefónico PBX.</span><span class="sxs-lookup"><span data-stu-id="bf198-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="bf198-115">Debe habilitar todos los usuarios de Vía trabajo para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="bf198-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="bf198-116">Al hacerlo, debe configurar el número DID de Skype Empresarial para cada usuario en el número DID correspondiente para el sistema telefónico PBX correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bf198-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="bf198-117">Todos los usuarios que usarán  Vía trabajo deben tener la configuración automática seleccionada en su opción De **conexiones** avanzadas en su cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="bf198-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="bf198-118">Esto permite al cliente detectar las direcciones URL de UCWA.</span><span class="sxs-lookup"><span data-stu-id="bf198-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="bf198-119">**La configuración** automática es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bf198-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="bf198-120">Para cada usuario de Vía trabajo, habilite el reenvío de llamadas y las llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="bf198-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="bf198-121">Para cada usuario de Vía trabajo, asegúrese de que las conferencias de acceso telefónico local y la conferencia de acceso telefónico local estén habilitadas.</span><span class="sxs-lookup"><span data-stu-id="bf198-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="bf198-122">Esto permite a estos usuarios entrar y salir de las conferencias de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="bf198-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="bf198-123">Asegúrese de que la delegación, la llamada de equipo y el grupo de respuesta están deshabilitados para cada usuario de Vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="bf198-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="bf198-124">Implementar llamada a través del trabajo</span><span class="sxs-lookup"><span data-stu-id="bf198-124">Deploy Call Via Work</span></span>

<span data-ttu-id="bf198-125">Una vez que se cumplan los requisitos previos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf198-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="bf198-126">Cree un número de teléfono global para su implementación que Skype Empresarial muestre en el identificador de llamada de PBX de los usuarios que están realizando llamadas vía trabajo.</span><span class="sxs-lookup"><span data-stu-id="bf198-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="bf198-127">Crear una o varias directivas vía trabajo</span><span class="sxs-lookup"><span data-stu-id="bf198-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="bf198-128">Asignar una directiva vía trabajo a cada usuario que se habilitará para Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="bf198-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="bf198-129">Crear el número de teléfono global Vía trabajo</span><span class="sxs-lookup"><span data-stu-id="bf198-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="bf198-130">Escriba el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="bf198-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="bf198-131">Por ejemplo, el siguiente cmdlet establece el número de teléfono global en 1-555-123-4567.</span><span class="sxs-lookup"><span data-stu-id="bf198-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="bf198-132">Crear una directiva vía trabajo</span><span class="sxs-lookup"><span data-stu-id="bf198-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="bf198-133">Escriba el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="bf198-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="bf198-134">Por ejemplo, el siguiente cmdlet crea una directiva vía trabajo llamada ContosoUser1CvWP, requiere que el usuario use un número de devolución de llamada de administrador y establece ese número de devolución de llamada en 1-555-789-1234.</span><span class="sxs-lookup"><span data-stu-id="bf198-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="bf198-135">Asignar una directiva vía trabajo a un usuario</span><span class="sxs-lookup"><span data-stu-id="bf198-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="bf198-136">Escriba el siguiente cmdlet</span><span class="sxs-lookup"><span data-stu-id="bf198-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="bf198-137">Por ejemplo, el siguiente cmdlet asigna la directiva vía trabajo "ContosoUser1CvWP" al usuario llamado **ContosoUser1**.</span><span class="sxs-lookup"><span data-stu-id="bf198-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="bf198-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf198-138">See also</span></span>

[<span data-ttu-id="bf198-139">Plan for Call Via Work in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bf198-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)


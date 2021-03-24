---
title: Bloquear las transferencias de archivos punto a punto
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: En Skype Empresarial Online, puede controlar las transferencias de archivos punto a punto (P2P) como parte de la configuración de directiva de conferencia existente. Sin embargo, esto permite o bloquea las transferencias de archivos para los usuarios, independientemente de si están transfiriendo o no archivos a un usuario de la misma organización o a un usuario federado de otra organización. Siguiendo los pasos siguientes, puede bloquear las transferencias de archivos P2P con organizaciones o partners federados.
ms.openlocfilehash: e2a0bb2f250f89433c09566197df7a56efa7f64f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100626"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="66248-105">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="66248-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="66248-106">En Skype Empresarial Online, puede controlar las transferencias de archivos punto a punto (P2P) como parte de la configuración de directiva de conferencia existente.</span><span class="sxs-lookup"><span data-stu-id="66248-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="66248-107">Sin embargo, esto permite o bloquea las transferencias de archivos para los usuarios, independientemente de si están transfiriendo o no archivos a un usuario de la misma organización o a un usuario federado de otra organización.</span><span class="sxs-lookup"><span data-stu-id="66248-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="66248-108">Siguiendo los pasos siguientes, puede bloquear las transferencias de archivos P2P con organizaciones o partners federados.</span><span class="sxs-lookup"><span data-stu-id="66248-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="66248-109">Un escenario muy común es cuando desea permitir que los usuarios internos usen la transferencia de archivos P2P, pero bloqueen la transferencia de archivos con partners federados.</span><span class="sxs-lookup"><span data-stu-id="66248-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="66248-110">Para este escenario, tendría que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="66248-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="66248-111">Asigne una directiva de conferencia con la transferencia de archivos P2P habilitada _(EnableP2PFileTransfer_ establecido en _True)_ a los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="66248-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="66248-112">Cree un conjunto global de directivas de comunicación de usuarios externos para bloquear las transferencias de archivos P2P externos _(EnableP2PFileTransfer_ establecido en _False)_ y asígnelo a un usuario de su organización.</span><span class="sxs-lookup"><span data-stu-id="66248-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="66248-113">Puede obtener más información sobre esa configuración [aquí.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="66248-113">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="66248-114">Si un usuario federado fuera de su organización intenta enviar un archivo a un usuario donde se ha aplicado la directiva, recibirá un **error** Error de transferencia.</span><span class="sxs-lookup"><span data-stu-id="66248-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="66248-115">Y si un usuario intenta enviar un archivo, recibirá un error de transferencia de **archivos** desactivado.</span><span class="sxs-lookup"><span data-stu-id="66248-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="66248-116">Para que esto funcione, el usuario debe usar una versión compatible de una aplicación de Skype Empresarial para hacer clic y ejecutar 2016 que la admita.</span><span class="sxs-lookup"><span data-stu-id="66248-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="66248-117">Se requiere la siguiente versión mínima del cliente de Hacer clic y ejecutar de Skype Empresarial 2016:</span><span class="sxs-lookup"><span data-stu-id="66248-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="66248-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="66248-118">**Type**</span></span>|<span data-ttu-id="66248-119">**Fecha de lanzamiento**</span><span class="sxs-lookup"><span data-stu-id="66248-119">**Release date**</span></span>|<span data-ttu-id="66248-120">**Versión**</span><span class="sxs-lookup"><span data-stu-id="66248-120">**Version**</span></span>|<span data-ttu-id="66248-121">**Versión**</span><span class="sxs-lookup"><span data-stu-id="66248-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66248-122">First Release para el Canal actual</span><span class="sxs-lookup"><span data-stu-id="66248-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="66248-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="66248-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="66248-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="66248-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="66248-125">Versión 1611 (compilación 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="66248-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="66248-126">Canal actual</span><span class="sxs-lookup"><span data-stu-id="66248-126">Current Channel</span></span>  <br/> |<span data-ttu-id="66248-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="66248-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="66248-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="66248-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="66248-129">Versión 1611 (compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="66248-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="66248-130">Canal diferido</span><span class="sxs-lookup"><span data-stu-id="66248-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="66248-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="66248-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="66248-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="66248-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="66248-133">Versión 1609 (compilación 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="66248-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="66248-134">Los usuarios que usan versiones anteriores de las aplicaciones de Windows de Skype Empresarial o los clientes Mac seguirán siendo capaces de transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="66248-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="66248-135">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66248-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="66248-136">El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="66248-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="66248-137">Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.</span><span class="sxs-lookup"><span data-stu-id="66248-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="66248-138">Instale el [módulo de PowerShell de Teams.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="66248-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="66248-139">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="66248-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="66248-140">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) en una sola ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="66248-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="66248-141">Deshabilitar las transferencias de archivos P2P para su organización</span><span class="sxs-lookup"><span data-stu-id="66248-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="66248-142">De forma predeterminada, _EnableP2PFileTransfer_ está habilitado en la directiva global de la organización.</span><span class="sxs-lookup"><span data-stu-id="66248-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="66248-143">Cuando se creó, a los usuarios se les asignó la _directiva BposSAllModality._</span><span class="sxs-lookup"><span data-stu-id="66248-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="66248-144">Para permitir las transferencias P2P dentro de su organización pero bloquear las transferencias de archivos externos a otra organización, solo tiene que cambiarla a nivel global.</span><span class="sxs-lookup"><span data-stu-id="66248-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="66248-145">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="66248-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="66248-146">Deshabilitar las transferencias de archivos P2P para un usuario</span><span class="sxs-lookup"><span data-stu-id="66248-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="66248-147">Puede aplicar esto a un usuario creando una nueva directiva y concedéndola a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="66248-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="66248-148">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="66248-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="66248-149">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="66248-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="66248-150">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="66248-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="66248-151">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="66248-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="66248-152">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="66248-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="66248-153">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="66248-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="66248-154">Por qué necesita usar Microsoft 365 u Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="66248-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="66248-155">Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="66248-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="66248-156">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="66248-156">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="66248-157">[Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="66248-157">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="66248-158">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="66248-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="66248-159">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="66248-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="66248-160">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="66248-160">Related topics</span></span>
[<span data-ttu-id="66248-161">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="66248-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="66248-162">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="66248-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="66248-163">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="66248-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  

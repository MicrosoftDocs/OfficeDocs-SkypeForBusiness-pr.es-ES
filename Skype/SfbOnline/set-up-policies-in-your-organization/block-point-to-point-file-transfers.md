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
description: En Skype Empresarial Online, puede controlar las transferencias de archivos de punto a punto (P2P) como parte de la configuración de la directiva de conferencias existente. Sin embargo, esto permite o bloquea la transferencia de archivos para los usuarios, tanto si transfieren archivos a un usuario de la misma organización como a un usuario federado de otra organización. Siguiendo los pasos que se indican a continuación, puede bloquear las transferencias de archivos P2P con socios o organizaciones federadas.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814639"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="38e06-105">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="38e06-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="38e06-106">En Skype Empresarial Online, puede controlar las transferencias de archivos de punto a punto (P2P) como parte de la configuración de la directiva de conferencias existente.</span><span class="sxs-lookup"><span data-stu-id="38e06-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="38e06-107">Sin embargo, esto permite o bloquea la transferencia de archivos para los usuarios, tanto si transfieren archivos a un usuario de la misma organización como a un usuario federado de otra organización.</span><span class="sxs-lookup"><span data-stu-id="38e06-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="38e06-108">Siguiendo los pasos que se indican a continuación, puede bloquear las transferencias de archivos P2P con socios o organizaciones federadas.</span><span class="sxs-lookup"><span data-stu-id="38e06-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="38e06-109">Un escenario muy común es cuando quiere permitir que los usuarios internos usen la transferencia de archivos P2P, pero bloquee la transferencia de archivos con partners federados.</span><span class="sxs-lookup"><span data-stu-id="38e06-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="38e06-110">Para este escenario, tendrá que hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38e06-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="38e06-111">Asigne una directiva de conferencia con la transferencia de archivos P2P habilitada _(EnableP2PFileTransfer_ establecido en _True)_ a los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="38e06-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="38e06-112">Cree una directiva de comunicación de usuario externo global para bloquear las transferencias de archivos P2P externos _(enableP2PFileTransfer_ establecido en _False)_ y asígnela a un usuario de su organización.</span><span class="sxs-lookup"><span data-stu-id="38e06-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="38e06-113">Puedes obtener más información sobre esta configuración [aquí.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="38e06-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="38e06-114">Si un usuario federado externo a la organización intenta enviar un archivo a un usuario donde se ha aplicado la directiva, recibirá un error de error **en la transferencia.**</span><span class="sxs-lookup"><span data-stu-id="38e06-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="38e06-115">Y si un usuario intenta enviar un archivo, recibirá un error **de transferencia** de archivo desactivado.</span><span class="sxs-lookup"><span data-stu-id="38e06-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="38e06-116">Para que esto funcione, el usuario debe estar usando una versión compatible de una aplicación de Skype Empresarial 2016 Hacer clic y ejecutar que sea compatible.</span><span class="sxs-lookup"><span data-stu-id="38e06-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="38e06-117">Se requiere la siguiente versión mínima del cliente Hacer clic y ejecutar de Skype Empresarial 2016:</span><span class="sxs-lookup"><span data-stu-id="38e06-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="38e06-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="38e06-118">**Type**</span></span>|<span data-ttu-id="38e06-119">**Fecha de lanzamiento**</span><span class="sxs-lookup"><span data-stu-id="38e06-119">**Release date**</span></span>|<span data-ttu-id="38e06-120">**Versión**</span><span class="sxs-lookup"><span data-stu-id="38e06-120">**Version**</span></span>|<span data-ttu-id="38e06-121">**Versión**</span><span class="sxs-lookup"><span data-stu-id="38e06-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38e06-122">First Release para canal actual</span><span class="sxs-lookup"><span data-stu-id="38e06-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="38e06-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="38e06-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="38e06-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="38e06-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="38e06-125">Versión 1611 (compilación 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="38e06-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="38e06-126">Canal actual</span><span class="sxs-lookup"><span data-stu-id="38e06-126">Current Channel</span></span>  <br/> |<span data-ttu-id="38e06-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="38e06-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="38e06-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="38e06-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="38e06-129">Versión 1611 (compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="38e06-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="38e06-130">Canal diferido</span><span class="sxs-lookup"><span data-stu-id="38e06-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="38e06-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="38e06-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="38e06-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="38e06-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="38e06-133">Versión 1609 (compilación 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="38e06-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="38e06-134">Los usuarios que usan versiones anteriores de aplicaciones windows o clientes Mac de Skype Empresarial todavía podrán transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="38e06-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="38e06-135">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38e06-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="38e06-136">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="38e06-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="38e06-137">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="38e06-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="38e06-138">Compruebe la versión escribiendo _Get-Host_ en la **Windows PowerShell** ventana.</span><span class="sxs-lookup"><span data-stu-id="38e06-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="38e06-139">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38e06-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="38e06-140">Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0.</span><span class="sxs-lookup"><span data-stu-id="38e06-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="38e06-141">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="38e06-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="38e06-142">También necesitará instalar el módulo Windows PowerShell para Teams que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="38e06-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="38e06-143">Si necesita más información, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx)en una única Windows PowerShell ventana.</span><span class="sxs-lookup"><span data-stu-id="38e06-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="38e06-144">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="38e06-144">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="38e06-145">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="38e06-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="38e06-146">En la **Windows PowerShell** de correo electrónico, conéctese a Su Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="38e06-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="38e06-147">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="38e06-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
        >
        > <span data-ttu-id="38e06-148">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="38e06-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="38e06-149">Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="38e06-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="38e06-150">Deshabilitar las transferencias de archivos P2P para su organización</span><span class="sxs-lookup"><span data-stu-id="38e06-150">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="38e06-151">De forma predeterminada, _EnableP2PFileTransfer_ está habilitado en la directiva global de la organización.</span><span class="sxs-lookup"><span data-stu-id="38e06-151">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="38e06-152">Cuando se creó, a los usuarios se les asignó la _directiva BposSAllModality._</span><span class="sxs-lookup"><span data-stu-id="38e06-152">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="38e06-153">Para permitir las transferencias P2P para dentro de la organización pero bloquear las transferencias de archivos externos a otra organización, solo tiene que cambiarlo a nivel global.</span><span class="sxs-lookup"><span data-stu-id="38e06-153">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="38e06-154">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="38e06-154">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="38e06-155">Deshabilitar la transferencia de archivos P2P para un usuario</span><span class="sxs-lookup"><span data-stu-id="38e06-155">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="38e06-156">Para aplicar esto a un usuario, cree una directiva y concédala a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="38e06-156">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="38e06-157">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="38e06-157">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="38e06-158">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="38e06-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="38e06-159">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="38e06-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="38e06-160">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="38e06-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="38e06-161">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="38e06-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="38e06-162">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="38e06-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="38e06-163">¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="38e06-163">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="38e06-164">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="38e06-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="38e06-165">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="38e06-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="38e06-166">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38e06-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="38e06-167">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="38e06-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="38e06-168">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="38e06-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="38e06-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="38e06-169">Related topics</span></span>
[<span data-ttu-id="38e06-170">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="38e06-170">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="38e06-171">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="38e06-171">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="38e06-172">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="38e06-172">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 

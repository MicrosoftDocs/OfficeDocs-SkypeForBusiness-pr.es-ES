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
f1keywords: None
ms.custom:
- Setup
description: En Skype empresarial online, tiene la capacidad de controlar las transferencias de archivos punto a punto (P2P) como parte de la configuración de directivas de conferencia existentes. Sin embargo, esto permite o bloquea las transferencias de archivos para los usuarios, ya sea que transfieran archivos a un usuario que está dentro de la misma organización o a un usuario federado de otra organización. Siguiendo los pasos que se indican a continuación, puede bloquear las transferencias de archivos P2P con organizaciones o socios federados.
ms.openlocfilehash: 8b45067cf0c717fdcda144fc44750b7cf3d0f7f7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297820"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="d4c86-105">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="d4c86-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="d4c86-106">En Skype empresarial online, tiene la capacidad de controlar las transferencias de archivos punto a punto (P2P) como parte de la configuración de directivas de conferencia existentes.</span><span class="sxs-lookup"><span data-stu-id="d4c86-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="d4c86-107">Sin embargo, esto permite o bloquea las transferencias de archivos para los usuarios, ya sea que transfieran archivos a un usuario que está dentro de la misma organización o a un usuario federado de otra organización.</span><span class="sxs-lookup"><span data-stu-id="d4c86-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="d4c86-108">Siguiendo los pasos que se indican a continuación, puede bloquear las transferencias de archivos P2P con organizaciones o socios federados.</span><span class="sxs-lookup"><span data-stu-id="d4c86-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="d4c86-109">Un escenario muy común es cuando desea permitir que los usuarios internos utilicen la transferencia de archivos P2P pero bloquean la transferencia de archivos con socios federados.</span><span class="sxs-lookup"><span data-stu-id="d4c86-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="d4c86-110">Para este escenario, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4c86-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="d4c86-111">Asignar una directiva de conferencia con la transferencia de archivos P2P habilitada (_EnableP2PFileTransfer_ establecida en _true_) a los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="d4c86-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="d4c86-112">Crear una directiva de comunicación de usuario externa global establecida para bloquear las transferencias de archivos P2P externos (_EnableP2PFileTransfer_ establecido en _falso_) y asignarlo a un usuario de su organización.</span><span class="sxs-lookup"><span data-stu-id="d4c86-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="d4c86-113">Puede obtener más información sobre esa configuración [aquí](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="d4c86-113">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="d4c86-114">Si un usuario federado fuera de la organización intenta enviar un archivo a un usuario en el que se ha aplicado la Directiva, recibirá un error de **transferencia fallida** .</span><span class="sxs-lookup"><span data-stu-id="d4c86-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="d4c86-115">Y si un usuario intenta enviar un archivo, recibirá un error al **transferir un archivo** .</span><span class="sxs-lookup"><span data-stu-id="d4c86-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="d4c86-116">Para que esto funcione, el usuario debe estar usando una versión compatible de una 2016 una aplicación de Skype empresarial de hacer clic y ejecutar que la admita.</span><span class="sxs-lookup"><span data-stu-id="d4c86-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="d4c86-117">Se necesita la siguiente versión mínima de Skype empresarial 2016 cliente de hacer clic y ejecutar:</span><span class="sxs-lookup"><span data-stu-id="d4c86-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="d4c86-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d4c86-118">**Type**</span></span>|<span data-ttu-id="d4c86-119">**Fecha de lanzamiento**</span><span class="sxs-lookup"><span data-stu-id="d4c86-119">**Release date**</span></span>|<span data-ttu-id="d4c86-120">**Versión**</span><span class="sxs-lookup"><span data-stu-id="d4c86-120">**Version**</span></span>|<span data-ttu-id="d4c86-121">**Versión**</span><span class="sxs-lookup"><span data-stu-id="d4c86-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d4c86-122">First Release para el canal actual</span><span class="sxs-lookup"><span data-stu-id="d4c86-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="d4c86-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="d4c86-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="d4c86-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="d4c86-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="d4c86-125">Versión 1611 (compilación 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="d4c86-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="d4c86-126">Canal actual</span><span class="sxs-lookup"><span data-stu-id="d4c86-126">Current Channel</span></span>  <br/> |<span data-ttu-id="d4c86-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="d4c86-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="d4c86-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="d4c86-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="d4c86-129">Versión 1611 (compilación 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="d4c86-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="d4c86-130">Canal diferido</span><span class="sxs-lookup"><span data-stu-id="d4c86-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="d4c86-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="d4c86-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="d4c86-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="d4c86-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="d4c86-133">Versión 1609 (compilación 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="d4c86-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="d4c86-134">Los usuarios que usen versiones anteriores de las aplicaciones de Windows de Skype para empresas o clientes de Mac seguirán pudiendo transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="d4c86-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="d4c86-135">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4c86-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="d4c86-136">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="d4c86-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="d4c86-137">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d4c86-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d4c86-138">Para comprobar la versión, escriba _Get-host_ en la ventana de **Windows PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="d4c86-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="d4c86-p106">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="d4c86-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="d4c86-p107">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="d4c86-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="d4c86-145">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="d4c86-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="d4c86-146">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d4c86-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="d4c86-147">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d4c86-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d4c86-148">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="d4c86-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d4c86-149">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="d4c86-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="d4c86-150">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d4c86-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="d4c86-151">Deshabilitar las transferencias de archivos P2P para su organización</span><span class="sxs-lookup"><span data-stu-id="d4c86-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="d4c86-152">De forma predeterminada, _EnableP2PFileTransfer_ está habilitado en la directiva global de la organización.</span><span class="sxs-lookup"><span data-stu-id="d4c86-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="d4c86-153">Cuando se creó, a los usuarios se les asignó la directiva _BposSAllModality_ .</span><span class="sxs-lookup"><span data-stu-id="d4c86-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="d4c86-154">Para permitir las transferencias P2P para dentro de su organización pero bloquear las transferencias de archivos externos a otra organización, solo tiene que cambiarla a nivel global.</span><span class="sxs-lookup"><span data-stu-id="d4c86-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="d4c86-155">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d4c86-155">To do that, run:</span></span>
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="d4c86-156">Deshabilitar las transferencias de archivos P2P para un usuario</span><span class="sxs-lookup"><span data-stu-id="d4c86-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="d4c86-157">Puede aplicar esta función a un usuario creando una nueva Directiva y concediendo a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="d4c86-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="d4c86-158">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="d4c86-158">To do that, run:</span></span> 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d4c86-159">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d4c86-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="d4c86-160">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="d4c86-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d4c86-161">Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="d4c86-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d4c86-162">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="d4c86-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d4c86-163">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d4c86-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d4c86-164">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="d4c86-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d4c86-p112">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="d4c86-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d4c86-167">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4c86-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d4c86-168">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d4c86-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d4c86-169">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d4c86-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="d4c86-170">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d4c86-170">Related topics</span></span>
[<span data-ttu-id="d4c86-171">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="d4c86-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="d4c86-172">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="d4c86-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="d4c86-173">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="d4c86-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 

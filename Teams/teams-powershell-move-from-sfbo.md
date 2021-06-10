---
title: Migrar desde Skype Empresarial Online Connector al módulo Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo pasar de Skype Empresarial Online Connector al módulo Teams PowerShell para administrar Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b08505ca97672d5285c8ff46b0e5d3cf58e9f84
ms.sourcegitcommit: 56bebf42f545af57fdf387faa90e555abc8acd40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "52513873"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="eae9e-103">Migrar desde Skype Empresarial Online Connector al módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="eae9e-103">Migrating from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="eae9e-104">Teams El módulo de PowerShell proporciona un conjunto completo de cmdlets para administrar Teams directamente desde la línea de comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eae9e-104">Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="eae9e-105">Los administradores no necesitan Skype For Business Online Connector para su Teams administración.</span><span class="sxs-lookup"><span data-stu-id="eae9e-105">Administrators do not require Skype For Business Online Connector for their Teams administration.</span></span>

> [!NOTE]
> <span data-ttu-id="eae9e-106">Teams a través de la publicación del Centro de mensajes (MC244740, fechada el 16 de marzo de 2021; MC250940, fechado el 16 de abril de 2021) sobre este cambio.</span><span class="sxs-lookup"><span data-stu-id="eae9e-106">Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.</span></span>
>
> <span data-ttu-id="eae9e-107">Teams El módulo de PowerShell usa la autenticación moderna, pero el Windows de administración remota (WinRM) subyacente debe configurarse para permitir la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="eae9e-107">Teams PowerShell Module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span> <span data-ttu-id="eae9e-108">Vea [Descargar e instalar Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) instrucciones sobre cómo habilitar WinRM para autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="eae9e-108">See [Download and install Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

> [!WARNING]
> <span data-ttu-id="eae9e-109">Skype Empresarial Las conexiones de Conector en línea se rechazarán a partir del 17 de mayo de 2021.</span><span class="sxs-lookup"><span data-stu-id="eae9e-109">Skype for Business Online Connector connections will be rejected starting May 17, 2021.</span></span> <span data-ttu-id="eae9e-110">Póngase en contacto con el soporte técnico de Microsoft para obtener ayuda y soporte técnico para migrar a Teams módulo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eae9e-110">Please contact Microsoft Support for help and support for migrating to Teams PowerShell Module.</span></span>

## <a name="how-to-migrate"></a><span data-ttu-id="eae9e-111">Cómo migrar</span><span class="sxs-lookup"><span data-stu-id="eae9e-111">How to Migrate</span></span>

<span data-ttu-id="eae9e-112">Migrar desde el Skype Empresarial Online Connector a Teams módulo de PowerShell es fácil y sencillo.</span><span class="sxs-lookup"><span data-stu-id="eae9e-112">Migrating from using Skype for Business Online Connector to Teams PowerShell module is easy and simple.</span></span> <span data-ttu-id="eae9e-113">En los pasos siguientes se explica cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="eae9e-113">The below steps explains how to do this.</span></span>

1. <span data-ttu-id="eae9e-114">Instale la versión Teams módulo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eae9e-114">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="eae9e-115">Para ver los pasos, [vea Instalar Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="eae9e-115">For steps, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

2. <span data-ttu-id="eae9e-116">Desinstale Skype Para Empresas Online Connector.</span><span class="sxs-lookup"><span data-stu-id="eae9e-116">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="eae9e-117">Para ello, en el Panel de control, vaya a Programas y **características,** seleccione **Skype Empresarial En línea, Windows PowerShell Módulo** y, a continuación, seleccione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="eae9e-117">To do this, in Control Panel, go to **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span>

3. <span data-ttu-id="eae9e-118">En los scripts de PowerShell, cambie el nombre del módulo al que se hace referencia ```Import-Module``` desde</span><span class="sxs-lookup"><span data-stu-id="eae9e-118">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from</span></span>

    <span data-ttu-id="eae9e-119">`SkypeOnlineConnector` o `LyncOnlineConnector` `MicrosoftTeams` para .</span><span class="sxs-lookup"><span data-stu-id="eae9e-119">`SkypeOnlineConnector` or `LyncOnlineConnector` to `MicrosoftTeams`.</span></span>

    <span data-ttu-id="eae9e-120">Por ejemplo, cambie `Import-Module -Name SkypeOnlineConnector` a `Import-Module -Name MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="eae9e-120">For example, change `Import-Module -Name SkypeOnlineConnector` to `Import-Module -Name MicrosoftTeams`.</span></span>

4. <span data-ttu-id="eae9e-121">Al usar Teams módulo de PowerShell 2.0 o posterior, actualice los scripts que se `New-CsOnlineSession` refieren a `Connect-MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="eae9e-121">When using Teams PowerShell Module 2.0 or later, update your scripts that refers `New-CsOnlineSession` to `Connect-MicrosoftTeams`.</span></span> <span data-ttu-id="eae9e-122">`Import-PsSession`ya no es necesario establecer un Skype Empresarial sesión remota de PowerShell en línea, ya que se realiza de forma implícita al usar `Connect-MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="eae9e-122">`Import-PsSession` is no longer required to establish a Skype for Business Online Remote PowerShell Session as that is done implicit when using `Connect-MicrosoftTeams`.</span></span>

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a><span data-ttu-id="eae9e-123">Soporte técnico en línea</span><span class="sxs-lookup"><span data-stu-id="eae9e-123">Online Support</span></span>

<span data-ttu-id="eae9e-124">Ahorre tiempo iniciando la solicitud de servicio en línea.</span><span class="sxs-lookup"><span data-stu-id="eae9e-124">Save time by starting your service request online.</span></span> <span data-ttu-id="eae9e-125">Te ayudaremos a encontrar una solución o a conectarte con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="eae9e-125">We'll help you find a solution or connect you to technical support.</span></span>

1.  <span data-ttu-id="eae9e-126">Vaya al Centro de administración en [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="eae9e-126">Go to the admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span> <span data-ttu-id="eae9e-127">Si recibe un mensaje que indica que no tiene permiso para acceder a esta página o realizar esta acción, entonces no es administrador. Quién tiene permisos de administrador en mi empresa?</span><span class="sxs-lookup"><span data-stu-id="eae9e-127">If you get a message that says you don't have permission to access this page or perform this action, then you aren't an admin. Who has admin permissions in my business?</span></span>

2.  <span data-ttu-id="eae9e-128">Seleccione **¿Necesita ayuda?** botón.</span><span class="sxs-lookup"><span data-stu-id="eae9e-128">Select the **Need help**? button.</span></span>

3.  <span data-ttu-id="eae9e-129">¿Necesita **ayuda?** panel, díganos con qué necesita ayuda y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="eae9e-129">In the **Need help**? pane, tell us what you need help with, and then press Enter.</span></span>

4.  <span data-ttu-id="eae9e-130">Si los resultados no le ayudan, seleccione **Ponerse en contacto con el soporte técnico.**</span><span class="sxs-lookup"><span data-stu-id="eae9e-130">If the results don't help, select **Contact support**.</span></span>

5.  <span data-ttu-id="eae9e-131">Escriba una descripción del problema, confirme su número de contacto y su dirección de correo electrónico, seleccione el método de contacto que prefiera y, a continuación, seleccione **Contacto.**</span><span class="sxs-lookup"><span data-stu-id="eae9e-131">Enter a description of your issue, confirm your contact number and email address, select your preferred contact method, and then select **Contact me**.</span></span> <span data-ttu-id="eae9e-132">El tiempo de espera esperado se indica en el cuadro ¿Necesita ayuda? panel.</span><span class="sxs-lookup"><span data-stu-id="eae9e-132">The expected wait time is indicated in the Need help? pane.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eae9e-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="eae9e-133">Related topics</span></span>

[<span data-ttu-id="eae9e-134">Instalar Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="eae9e-134">Install Microsoft Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="eae9e-135">Administrar Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="eae9e-135">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="eae9e-136">Teams Notas de la versión de PowerShell</span><span class="sxs-lookup"><span data-stu-id="eae9e-136">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="eae9e-137">Microsoft Teams referencia de cmdlet</span><span class="sxs-lookup"><span data-stu-id="eae9e-137">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="eae9e-138">Skype Empresarial referencia de cmdlet</span><span class="sxs-lookup"><span data-stu-id="eae9e-138">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

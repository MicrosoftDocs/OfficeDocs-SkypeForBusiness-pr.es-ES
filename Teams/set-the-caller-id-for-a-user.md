---
title: Establecer el identificador de llamada de un usuario
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Obtenga información sobre el identificador de llamada predeterminado de Microsoft 365 y Office 365 (el número de teléfono asignado a un usuario), también conocido como Identificador de línea de llamada. Puede cambiar o bloquear el identificador de llamada de un usuario.
ms.openlocfilehash: ff8355b9435d0a21c032ee90b442884c0319221c
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814329"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="54021-104">Establecer el identificador de llamada de un usuario</span><span class="sxs-lookup"><span data-stu-id="54021-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="54021-105">El sistema telefónico de Microsoft 365 y Office 365 proporciona un identificador de llamada predeterminado que es el número de teléfono asignado al usuario.</span><span class="sxs-lookup"><span data-stu-id="54021-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="54021-106">Si lo desea, puede cambiar o bloquear el identificador de llamada (también denominado identificador de línea de llamada) para un usuario.</span><span class="sxs-lookup"><span data-stu-id="54021-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="54021-107">Para obtener más información sobre cómo usar el identificador de llamada en su organización, vaya a Cómo se puede usar la identificación de llamadas [en su organización.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="54021-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="54021-108">Actualmente no se pueden bloquear las llamadas entrantes en Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="54021-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="54021-109">Hay algunos ajustes que puede cambiar:</span><span class="sxs-lookup"><span data-stu-id="54021-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="54021-110">Esto **no es** para las organizaciones locales con Lync o Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="54021-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="54021-p103">**Cambiar el identificador de llamada saliente** Puede reemplazar el identificador de llamada de un usuario, que es de manera predeterminada su propio número de teléfono, por otro número de teléfono. Por ejemplo, puede cambiar el identificador de llamada del usuario de su número de teléfono a un número de teléfono principal de la empresa, o bien cambiar el identificador de línea de llamada del usuario de su número de teléfono a un número de teléfono principal del departamento jurídico. Puede cambiar el número del identificador de llamada por cualquier número de **servicio** en línea (de pago o gratuito).</span><span class="sxs-lookup"><span data-stu-id="54021-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54021-114">Si desea usar el parámetro  _Service_, deberá especificar un número de servicio válido.</span><span class="sxs-lookup"><span data-stu-id="54021-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="54021-115">**Bloquear el identificador de llamada saliente** Puede impedir que el identificador de llamada saliente se envíe en las llamadas RTC salientes de un usuario.</span><span class="sxs-lookup"><span data-stu-id="54021-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="54021-116">Al hacerlo, se bloqueará el número de teléfono para que no se muestre en el teléfono de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="54021-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="54021-117">**Bloquear el identificador de llamada entrante** Puede impedir que un usuario reciba el identificador de llamada en las llamadas RTC entrantes.</span><span class="sxs-lookup"><span data-stu-id="54021-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="54021-118">Las llamadas de emergencia siempre envían el número de teléfono de los usuarios (identificador de llamada).</span><span class="sxs-lookup"><span data-stu-id="54021-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="54021-p105">De manera predeterminada, estos ajustes del identificador de llamada están **desactivados**. Esto significa que el número de teléfono del usuario de Skype Empresarial Online se puede ver cuando el usuario realiza una llamada a un teléfono RTC.</span><span class="sxs-lookup"><span data-stu-id="54021-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="54021-121">Para obtener más información sobre esta configuración y cómo usarla, vaya [Cómo se puede usar la identificación de llamadas en su organización](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="54021-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="54021-122">Establecer la configuración de la directiva de identificador de llamada</span><span class="sxs-lookup"><span data-stu-id="54021-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="54021-123">Para toda la configuración del identificador de llamada en Skype Empresarial Online, debe usar Windows PowerShell y no puede usar el **Centro** de administración de **Skype Empresarial.**</span><span class="sxs-lookup"><span data-stu-id="54021-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="54021-124">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54021-124">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="54021-125">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="54021-125">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="54021-126">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="54021-126">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="54021-127">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="54021-127">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="54021-128">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54021-128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="54021-129">Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0.</span><span class="sxs-lookup"><span data-stu-id="54021-129">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="54021-130">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="54021-130">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="54021-p107">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="54021-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="54021-134">Si necesita más información, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx)en una única Windows PowerShell ventana.</span><span class="sxs-lookup"><span data-stu-id="54021-134">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="54021-135">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="54021-135">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="54021-136">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="54021-136">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="54021-137">En la **Windows PowerShell** de correo electrónico, conéctese a Su Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="54021-137">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   > [!NOTE]
   >
   > <span data-ttu-id="54021-138">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="54021-138">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   > <span data-ttu-id="54021-139">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="54021-139">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
   ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="54021-140">Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell.](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="54021-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="54021-141">Ver toda la configuración de la directiva de identificador de llamada en su organización</span><span class="sxs-lookup"><span data-stu-id="54021-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="54021-142">Para ver toda la configuración de la directiva de identificador de llamada en su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="54021-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="54021-143">Vea más ejemplos y detalles [sobre Get-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793856.aspx)</span><span class="sxs-lookup"><span data-stu-id="54021-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="54021-144">Crear una nueva directiva de identificador de llamada para su organización</span><span class="sxs-lookup"><span data-stu-id="54021-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="54021-145">Para crear una nueva directiva de identificador de llamada que establece el identificador de llamada en anónimo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="54021-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="54021-146">En todos los casos, el campo "Número de servicio" no debe incluir un "+" inicial.</span><span class="sxs-lookup"><span data-stu-id="54021-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="54021-147">Vea más ejemplos y detalles de [New-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793855.aspx)</span><span class="sxs-lookup"><span data-stu-id="54021-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="54021-148">Para aplicar la nueva directiva a Amos Marble, ejecute:</span><span class="sxs-lookup"><span data-stu-id="54021-148">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="54021-149">Vea más sobre el [cmdlet Grant-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793857.aspx)</span><span class="sxs-lookup"><span data-stu-id="54021-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="54021-150">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="54021-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="54021-151">Establecer que el identificador de llamada entrante esté bloqueado</span><span class="sxs-lookup"><span data-stu-id="54021-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="54021-152">Para bloquear el identificador de llamada entrante, ejecute:</span><span class="sxs-lookup"><span data-stu-id="54021-152">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="54021-153">Vea más ejemplos y detalles [de Set-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793854.aspx)</span><span class="sxs-lookup"><span data-stu-id="54021-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="54021-154">Para aplicar la configuración de directiva que ha creado a un usuario de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="54021-154">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="54021-155">Vea más sobre el [cmdlet Grant-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793857.aspx)</span><span class="sxs-lookup"><span data-stu-id="54021-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="54021-156">Quitar una directiva de identificación de llamadas</span><span class="sxs-lookup"><span data-stu-id="54021-156">Remove a caller ID policy</span></span>

<span data-ttu-id="54021-157">Para quitar una directiva de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="54021-157">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="54021-158">Para quitar una directiva de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="54021-158">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="54021-159">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="54021-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="54021-160">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="54021-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="54021-161">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="54021-161">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="54021-162">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="54021-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="54021-163">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="54021-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="54021-164">Seis motivos por los que podría desear usar Windows PowerShell administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="54021-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="54021-165">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="54021-165">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="54021-166">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="54021-166">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="54021-167">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54021-167">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="54021-168">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="54021-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="54021-169">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="54021-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="54021-170">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="54021-170">Related topics</span></span>
[<span data-ttu-id="54021-171">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="54021-171">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="54021-172">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="54021-172">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="54021-173">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="54021-173">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="54021-174">Obtener más información acerca del identificador de línea de llamada y del nombre del usuario de llamada</span><span class="sxs-lookup"><span data-stu-id="54021-174">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="54021-175">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="54021-175">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="54021-176">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="54021-176">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 

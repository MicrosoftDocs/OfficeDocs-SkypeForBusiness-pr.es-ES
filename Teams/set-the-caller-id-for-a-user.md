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
description: Obtenga información sobre el identificador de llamada predeterminado de Microsoft 365 y Office 365 (el número de teléfono asignado por un usuario), también conocido como Identificador de línea de llamadas. Puede cambiar o bloquear el identificador de llamada de un usuario.
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569422"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="1e88e-104">Establecer el identificador de llamada de un usuario</span><span class="sxs-lookup"><span data-stu-id="1e88e-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="1e88e-105">El sistema telefónico de Microsoft 365 y Office 365 proporciona un identificador de llamada predeterminado que es el número de teléfono asignado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1e88e-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="1e88e-106">Si lo desea, puede cambiar o bloquear el identificador de llamada (también denominado identificador de línea de llamada) para un usuario.</span><span class="sxs-lookup"><span data-stu-id="1e88e-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="1e88e-107">Para obtener más información sobre cómo usar el identificador de llamada en su organización, vaya a ¿Cómo se puede usar el [identificador de llamada en su organización?](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="1e88e-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="1e88e-108">Actualmente no se pueden bloquear las llamadas entrantes en Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="1e88e-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="1e88e-109">Hay algunos ajustes que puede cambiar:</span><span class="sxs-lookup"><span data-stu-id="1e88e-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e88e-110">Esto **no es** para las organizaciones locales con Lync o Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1e88e-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="1e88e-p103">**Cambiar el identificador de llamada saliente** Puede reemplazar el identificador de llamada de un usuario, que es de manera predeterminada su propio número de teléfono, por otro número de teléfono. Por ejemplo, puede cambiar el identificador de llamada del usuario de su número de teléfono a un número de teléfono principal de la empresa, o bien cambiar el identificador de línea de llamada del usuario de su número de teléfono a un número de teléfono principal del departamento jurídico. Puede cambiar el número del identificador de llamada por cualquier número de **servicio** en línea (de pago o gratuito).</span><span class="sxs-lookup"><span data-stu-id="1e88e-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e88e-114">Si desea usar el parámetro  _Service_, deberá especificar un número de servicio válido.</span><span class="sxs-lookup"><span data-stu-id="1e88e-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="1e88e-115">**Bloquear su identificador de llamada saliente** Puede bloquear el identificador de llamada saliente para que no se envíe en las llamadas RTC salientes de un usuario.</span><span class="sxs-lookup"><span data-stu-id="1e88e-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="1e88e-116">Al hacerlo, se bloqueará el número de teléfono para que no se muestre en el teléfono de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="1e88e-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="1e88e-117">**Bloquear su identificador de llamada entrante** Puede bloquear que un usuario reciba el identificador de llamada en las llamadas RTC entrantes.</span><span class="sxs-lookup"><span data-stu-id="1e88e-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1e88e-118">Las llamadas de emergencia siempre envían el número de teléfono de los usuarios (identificador de llamada).</span><span class="sxs-lookup"><span data-stu-id="1e88e-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="1e88e-p105">De manera predeterminada, estos ajustes del identificador de llamada están **desactivados**. Esto significa que el número de teléfono del usuario de Skype Empresarial Online se puede ver cuando el usuario realiza una llamada a un teléfono RTC.</span><span class="sxs-lookup"><span data-stu-id="1e88e-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="1e88e-121">Para obtener más información sobre esta configuración y cómo usarla, vaya [Cómo se puede usar la identificación de llamadas en su organización](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="1e88e-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="1e88e-122">Establecer la configuración de la directiva de identificación de llamadas</span><span class="sxs-lookup"><span data-stu-id="1e88e-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="1e88e-123">Para todas las opciones de configuración de Identificador de llamadas en  Skype Empresarial Online, debe usar Windows PowerShell y no puede usar el Centro de administración **de Skype Empresarial.**</span><span class="sxs-lookup"><span data-stu-id="1e88e-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-powershell"></a><span data-ttu-id="1e88e-124">Iniciar PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e88e-124">Start PowerShell</span></span>

- <span data-ttu-id="1e88e-125">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="1e88e-125">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="1e88e-126">Ver toda la configuración de la directiva de identificación de llamadas en su organización</span><span class="sxs-lookup"><span data-stu-id="1e88e-126">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="1e88e-127">Para ver toda la configuración de la directiva de identificación de llamadas de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1e88e-127">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="1e88e-128">Vea más ejemplos y detalles [de Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e88e-128">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="1e88e-129">Crear una nueva directiva de identificación de llamadas para su organización</span><span class="sxs-lookup"><span data-stu-id="1e88e-129">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="1e88e-130">Para crear una nueva directiva de identificador de llamada que establece el id. de autor de la llamada en anónimo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1e88e-130">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="1e88e-131">En todos los casos, el campo "Número de servicio" no debe incluir un "+" inicial.</span><span class="sxs-lookup"><span data-stu-id="1e88e-131">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="1e88e-132">Vea más ejemplos y detalles [para New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e88e-132">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="1e88e-133">Para aplicar la nueva directiva que creó a Amos Marble, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1e88e-133">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="1e88e-134">Vea más sobre el [cmdlet Grant-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793857.aspx)</span><span class="sxs-lookup"><span data-stu-id="1e88e-134">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="1e88e-135">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1e88e-135">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="1e88e-136">Establecerlo para que el identificador de llamada entrante esté bloqueado</span><span class="sxs-lookup"><span data-stu-id="1e88e-136">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="1e88e-137">Para bloquear el identificador de llamada entrante, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1e88e-137">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="1e88e-138">Vea más ejemplos y detalles [para Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e88e-138">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="1e88e-139">Para aplicar la configuración de directiva que creó a un usuario de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1e88e-139">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="1e88e-140">Vea más sobre el [cmdlet Grant-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793857.aspx)</span><span class="sxs-lookup"><span data-stu-id="1e88e-140">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="1e88e-141">Quitar una directiva de identificación de llamadas</span><span class="sxs-lookup"><span data-stu-id="1e88e-141">Remove a caller ID policy</span></span>

<span data-ttu-id="1e88e-142">Para quitar una directiva de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1e88e-142">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="1e88e-143">Para quitar una directiva de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1e88e-143">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1e88e-144">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1e88e-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="1e88e-145">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="1e88e-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1e88e-146">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="1e88e-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1e88e-147">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="1e88e-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1e88e-148">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1e88e-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1e88e-149">Seis razones por las que es posible que desee usar Windows PowerShell administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="1e88e-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="1e88e-150">Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="1e88e-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1e88e-151">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="1e88e-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1e88e-152">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e88e-152">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="1e88e-153">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1e88e-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1e88e-154">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1e88e-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="1e88e-155">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1e88e-155">Related topics</span></span>
[<span data-ttu-id="1e88e-156">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="1e88e-156">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="1e88e-157">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="1e88e-157">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="1e88e-158">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="1e88e-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="1e88e-159">Obtener más información acerca del identificador de línea de llamada y del nombre del usuario de llamada</span><span class="sxs-lookup"><span data-stu-id="1e88e-159">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="1e88e-160">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="1e88e-160">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="1e88e-161">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="1e88e-161">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 

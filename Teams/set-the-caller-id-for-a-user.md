---
title: Establecer el identificador de llamada de un usuario
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Obtenga información sobre Microsoft 365 y Office 365 de llamada predeterminada (número de teléfono asignado por un usuario), también conocido como Identificador de línea de llamada. Puede cambiar o bloquear el identificador de llamada de un usuario.
ms.openlocfilehash: dbbb48952264d82ca24bdd82dbb45538b0428368
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308339"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="34a81-104">Establecer el identificador de llamada de un usuario</span><span class="sxs-lookup"><span data-stu-id="34a81-104">Set the Caller ID for a user</span></span>

<span data-ttu-id="34a81-105">Sistema telefónico en Microsoft 365 proporciona un identificador de llamada predeterminado que es el número de teléfono asignado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="34a81-105">Phone System in Microsoft 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="34a81-106">Si lo desea, puede cambiar o bloquear el identificador de llamada (también denominado identificador de línea de llamada) para un usuario.</span><span class="sxs-lookup"><span data-stu-id="34a81-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="34a81-107">Para obtener más información sobre cómo usar el identificador de llamada en su organización, vaya a ¿Cómo se puede usar el [identificador de llamada en su organización?](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="34a81-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
<span data-ttu-id="34a81-108">De forma predeterminada, la siguiente configuración de identificador de llamada **está desactivada.**</span><span class="sxs-lookup"><span data-stu-id="34a81-108">By default, the following caller ID settings are **turned off**.</span></span> <span data-ttu-id="34a81-109">Esto significa que el Teams de teléfono del usuario puede verse cuando ese usuario realiza una llamada a un teléfono RTC.</span><span class="sxs-lookup"><span data-stu-id="34a81-109">This means that the Teams user's phone number can be seen when that user makes a call to a PSTN phone.</span></span> <span data-ttu-id="34a81-110">Puede cambiar esta configuración de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="34a81-110">You can change these settings as follows:</span></span>
  
- <span data-ttu-id="34a81-111">**Identificador de llamada saliente** Puede reemplazar el identificador de llamada de un usuario, que de forma predeterminada es su número de teléfono, por otro número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="34a81-111">**Outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="34a81-112">Por ejemplo, puede cambiar el identificador de llamada del usuario de su número de teléfono a un número de teléfono principal de la empresa, o bien cambiar el identificador de línea de llamada del usuario de su número de teléfono a un número de teléfono principal del departamento jurídico.</span><span class="sxs-lookup"><span data-stu-id="34a81-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="34a81-113">Puede cambiar el número de identificación de llamadas a cualquier número de servicio en línea (de pago o gratuito).</span><span class="sxs-lookup"><span data-stu-id="34a81-113">You can change the Calling ID number to any online service number (toll or toll-free).</span></span> <span data-ttu-id="34a81-114">También puede cambiar el número de id. de llamada a un número de teléfono local mediante enrutamiento directo asignado a una cuenta de recursos usada por una Operador automático o cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="34a81-114">You can also change the Calling ID number to an on-premises phone number through Direct Routing that is assigned to a resource account used by an Auto Attendant or Call Queue.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="34a81-115">Si desea usar el parámetro *Servicio,* debe especificar un número de servicio válido.</span><span class="sxs-lookup"><span data-stu-id="34a81-115">If you want to use the *Service* parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="34a81-116">**Bloquear el identificador de llamada saliente.**</span><span class="sxs-lookup"><span data-stu-id="34a81-116">**Block outbound caller ID.**</span></span> <span data-ttu-id="34a81-117">Puede bloquear el identificador de llamada saliente para que no se envíe en las llamadas RTC salientes de un usuario.</span><span class="sxs-lookup"><span data-stu-id="34a81-117">You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="34a81-118">Al hacerlo, se bloqueará el número de teléfono para que no se muestre en el teléfono de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="34a81-118">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="34a81-119">**Bloquear el identificador de llamada entrante.**</span><span class="sxs-lookup"><span data-stu-id="34a81-119">**Block incoming caller ID.**</span></span> <span data-ttu-id="34a81-120">Puede bloquear que un usuario reciba el identificador de llamada en las llamadas RTC entrantes.</span><span class="sxs-lookup"><span data-stu-id="34a81-120">You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>

- <span data-ttu-id="34a81-121">**Establecer el nombre de la parte que llama (CNAM).**</span><span class="sxs-lookup"><span data-stu-id="34a81-121">**Set Calling Party Name (CNAM).**</span></span> <span data-ttu-id="34a81-122">Para sus Microsoft Teams usuarios, puede enviar un CNAM en las llamadas RTC salientes.</span><span class="sxs-lookup"><span data-stu-id="34a81-122">For your Microsoft Teams users you can send a CNAM on outbound PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="34a81-123">Las llamadas de emergencia siempre envían el número de teléfono de los usuarios (identificador de llamada).</span><span class="sxs-lookup"><span data-stu-id="34a81-123">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  

  
<span data-ttu-id="34a81-124">Para obtener más información sobre estas opciones de configuración y cómo puede usarlas, vea Cómo se puede usar el [identificador de llamada en su organización.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="34a81-124">To learn more about these settings and how you can use them, see [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="34a81-125">Establecer la configuración de la directiva de identificación de llamadas</span><span class="sxs-lookup"><span data-stu-id="34a81-125">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="34a81-126">Para establecer el identificador de llamada en un número de teléfono de cuenta de recurso y establecer el nombre de la parte que llama, use los cmdlets de PowerShell New-CsCallingLineIdentity o Set-CsCallingLineIdentity en el módulo de PowerShell de Teams 2.3.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="34a81-126">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="34a81-127">(Estas opciones no están disponibles actualmente en el centro Microsoft Teams administración).</span><span class="sxs-lookup"><span data-stu-id="34a81-127">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="34a81-128">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="34a81-128">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a><span data-ttu-id="34a81-129">Ver, crear y aplicar la configuración de directiva</span><span class="sxs-lookup"><span data-stu-id="34a81-129">View, create, and apply policy settings</span></span>

1. <span data-ttu-id="34a81-130">Para ver toda la configuración de la directiva de identificación de llamadas de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="34a81-130">To view all of the caller ID policy settings in your organization, run:</span></span>

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   <span data-ttu-id="34a81-131">Para obtener más información, [vea Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="34a81-131">For more information, see [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
2. <span data-ttu-id="34a81-132">Para crear una nueva directiva de identificador de llamada para su organización, use el cmdlet New-CsCallingIdentity llamada:</span><span class="sxs-lookup"><span data-stu-id="34a81-132">To create a new caller ID policy for your organization, use the New-CsCallingIdentity cmdlet:</span></span>
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    <span data-ttu-id="34a81-133">En todos los casos, el campo "Número de servicio" no debe incluir un "+" inicial.</span><span class="sxs-lookup"><span data-stu-id="34a81-133">In all cases, the "Service Number" field should not include an initial "+".</span></span>

   <span data-ttu-id="34a81-134">Para obtener más información, [vea New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="34a81-134">For more information, see [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
3. <span data-ttu-id="34a81-135">Aplique la nueva directiva que creó con el cmdlet Grant-CsCallingIdentity usuario.</span><span class="sxs-lookup"><span data-stu-id="34a81-135">Apply the new policy you created by using the Grant-CsCallingIdentity cmdlet.</span></span> <span data-ttu-id="34a81-136">Por ejemplo, en el ejemplo siguiente se aplica la nueva directiva al usuario Amos Marble.</span><span class="sxs-lookup"><span data-stu-id="34a81-136">For example, the following example applies the new policy to user Amos Marble.</span></span>
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   <span data-ttu-id="34a81-137">Para obtener más información, vea [Cmdlet Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="34a81-137">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    

4. <span data-ttu-id="34a81-138">Si desea bloquear el identificador de llamada entrante, ejecute:</span><span class="sxs-lookup"><span data-stu-id="34a81-138">If you want to block the incoming caller ID, run:</span></span>
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   <span data-ttu-id="34a81-139">Para obtener más información, [vea Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="34a81-139">For more information, see [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
5. <span data-ttu-id="34a81-140">Para aplicar la configuración de directiva que creó a un usuario de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="34a81-140">To apply the policy setting you created to a user in your organization, run:</span></span>
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   <span data-ttu-id="34a81-141">Para obtener más información, [vea Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="34a81-141">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span></span>

6. <span data-ttu-id="34a81-142">Para crear una nueva directiva de identificador de llamada que establece el identificador de llamada en el número de teléfono de la cuenta de recurso especificada y establece el nombre de la parte llamada en Contoso:</span><span class="sxs-lookup"><span data-stu-id="34a81-142">To create a new Caller ID policy that sets the Caller ID to the phone number of the specified resource account and sets the Calling party name to Contoso:</span></span>

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

<span data-ttu-id="34a81-143">Si ya ha creado una directiva, puede usar el cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) para aplicar la configuración a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="34a81-143">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
    
### <a name="remove-a-policy-setting"></a><span data-ttu-id="34a81-144">Quitar una configuración de directiva</span><span class="sxs-lookup"><span data-stu-id="34a81-144">Remove a policy setting</span></span>

<span data-ttu-id="34a81-145">Para quitar una directiva de su organización, ejecute:</span><span class="sxs-lookup"><span data-stu-id="34a81-145">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="34a81-146">Para quitar una directiva de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="34a81-146">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="34a81-147">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="34a81-147">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="34a81-148">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="34a81-148">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="34a81-149">Con Windows PowerShell, puede administrar Microsoft 365 un único punto de administración que puede simplificar su trabajo diario.</span><span class="sxs-lookup"><span data-stu-id="34a81-149">With Windows PowerShell, you can manage Microsoft 365 using a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="34a81-150">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="34a81-150">To get started with Windows PowerShell, see these topics:</span></span>
    
- [<span data-ttu-id="34a81-151">Una introducción a Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34a81-151">An introduction to Windows PowerShell</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="34a81-152">Seis motivos por los que es posible que desee usar Windows PowerShell administrar Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34a81-152">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="34a81-153">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="34a81-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="34a81-154">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="34a81-154">Learn about these advantages in the following topics:</span></span>
    
- <span data-ttu-id="34a81-155">[Las mejores formas de administrar Microsoft 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="34a81-155">[Best ways to manage Microsoft 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- [<span data-ttu-id="34a81-156">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="34a81-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="34a81-157">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="34a81-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="34a81-158">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="34a81-158">Related topics</span></span>
[<span data-ttu-id="34a81-159">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="34a81-159">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="34a81-160">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="34a81-160">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="34a81-161">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="34a81-161">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="34a81-162">Obtener más información acerca del identificador de línea de llamada y del nombre del usuario de llamada</span><span class="sxs-lookup"><span data-stu-id="34a81-162">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="34a81-163">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="34a81-163">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="34a81-164">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="34a81-164">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

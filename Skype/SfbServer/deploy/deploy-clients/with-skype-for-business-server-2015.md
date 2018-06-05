---
title: Implementar Sistemas de salas de Skype v2 con Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Skype para Business Server 2015.
ms.openlocfilehash: 9705d849027f03a4d4befc6c433f0fe6fb4bc414
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568259"
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a><span data-ttu-id="8a137-103">Implementar Sistemas de salas de Skype v2 con Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a137-103">Deploy Skype Room Systems v2 with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8a137-104">Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8a137-104">Read this topic for information on how to deploy Skype Room Systems v2 with Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8a137-105">En este tema se explica cómo agregar una cuenta de dispositivo para sistemas de salón de Skype v2 cuando tiene una implementación de bosque único, local.</span><span class="sxs-lookup"><span data-stu-id="8a137-105">This topic explains how you add a device account for Skype Room Systems v2 when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="8a137-106">Si tiene un solo bosque, implementación de local con Exchange 2013 SP1 o posterior y Skype para Business Server 2015 o posterior, puede usar los scripts de Windows PowerShell proporcionados para crear cuentas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8a137-106">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="8a137-107">Si utiliza una implementación de varios bosque, puede usar cmdlets de equivalentes que se producen los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="8a137-107">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="8a137-108">Estos cmdlets se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="8a137-108">Those cmdlets are described in this section.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a><span data-ttu-id="8a137-109">Implementar Sistemas de salas de Skype v2 con Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a137-109">Deploy Skype Room Systems v2 with Skype for Business Server 2015</span></span>

<span data-ttu-id="8a137-110">Antes de implementar sistemas de salón de Skype v2 con Skype Business Server 2015, asegúrese de que cumplen los requisitos.</span><span class="sxs-lookup"><span data-stu-id="8a137-110">Before you deploy Skype Room Systems v2 with Skype for Business Server 2015, be sure you have met the requirements.</span></span> <span data-ttu-id="8a137-111">Para obtener más información, vea [requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a137-111">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="8a137-112">Antes de comenzar a implementar sistemas de salón de Skype v2, asegúrese de que tiene los permisos adecuados para ejecutar los cmdlets de asociados.</span><span class="sxs-lookup"><span data-stu-id="8a137-112">Before you begin to deploy Skype Room Systems v2, be sure you have the right permissions to run the associated cmdlets.</span></span>
  
1. <span data-ttu-id="8a137-113">Iniciar una sesión remota de Windows PowerShell desde un PC y conectarse a Exchange.</span><span class="sxs-lookup"><span data-stu-id="8a137-113">Start a remote Windows PowerShell session from a PC and connect to Exchange.</span></span> 
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
 
   ```

   <span data-ttu-id="8a137-114">Tenga en cuenta que $strExchangeServer es el nombre de dominio completo (FQDN) del servidor de Exchange, y $strLyncFQDN es el FQDN de su Skype para la implementación empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8a137-114">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server 2015 deployment.</span></span>
    
2. <span data-ttu-id="8a137-115">Después de establecer una sesión, podrá crear un nuevo buzón y habilitar como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="8a137-115">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="8a137-116">Esto le permitirá la cuenta autenticar a los sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="8a137-116">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
    <span data-ttu-id="8a137-117">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="8a137-117">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="8a137-118">Si está creando un nuevo buzón de recursos:</span><span class="sxs-lookup"><span data-stu-id="8a137-118">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="8a137-119">Puede establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de reunión para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8a137-119">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="8a137-120">Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="8a137-120">You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="8a137-121">Si decide que la contraseña no caduca, puede establecer con los cmdlets de Windows PowerShell demasiado.</span><span class="sxs-lookup"><span data-stu-id="8a137-121">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="8a137-122">Vea Administración de etiquetas para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8a137-122">See Password management for more information.</span></span>
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="8a137-123">Habilite la cuenta en Active Directory, por lo que autenticará a sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="8a137-123">Enable the account in Active Directory so it will authenticate to Skype Room Systems v2.</span></span>
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="8a137-124">Habilitar la cuenta del dispositivo con Skype para Business Server 2015 mediante la habilitación de la cuenta de Active Directory v2 de sistemas de salón de Skype en un Skype para el grupo de servidores de Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="8a137-124">Enable the device account with Skype for Business Server 2015 by enabling your Skype Room Systems v2 Active Directory account on a Skype for Business Server 2015 pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="8a137-125">Tendrá que usar la dirección SIP (protocolo de inicio de sesión) y el controlador de dominio del proyecto</span><span class="sxs-lookup"><span data-stu-id="8a137-125">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span> 
    
7. <span data-ttu-id="8a137-126">**Opcional.**</span><span class="sxs-lookup"><span data-stu-id="8a137-126">**Optional.**</span></span> <span data-ttu-id="8a137-127">También puede permitir v2 de sistemas de salón de Skype realizar y recibir llamadas telefónicas de telefónica conmutada (RTC) de la red mediante la habilitación de Enterprise Voice para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="8a137-127">You can also allow Skype Room Systems v2 to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="8a137-128">Enterprise Voice no es un requisito para sistemas de salón de Skype v2, pero si desea que la funcionalidad de marcado de RTC para el cliente de v2 de sistemas de salón de Skype, aquí es cómo habilitarla:</span><span class="sxs-lookup"><span data-stu-id="8a137-128">Enterprise Voice isn't a requirement for Skype Room Systems v2, but if you want PSTN dialing functionality for the Skype Room Systems v2 client, here's how to enable it:</span></span>
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="8a137-p107">De nuevo, tendrá que reemplazar el controlador de dominio y los números de teléfono que se han proporcionado como ejemplo con su propia información. El valor de parámetro $true no se modifica.</span><span class="sxs-lookup"><span data-stu-id="8a137-p107">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-2015-on-premises"></a><span data-ttu-id="8a137-131">Ejemplo: sala cuenta el programa de instalación de Exchange y de Skype para Business Server 2015 local</span><span class="sxs-lookup"><span data-stu-id="8a137-131">Sample: room account setup in Exchange and Skype for Business Server 2015 on premises</span></span>

```
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) 
-UserPrincipalName rigel1@contoso.com
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false 
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="see-also"></a><span data-ttu-id="8a137-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a137-132">See also</span></span>

[<span data-ttu-id="8a137-133">Planeación de la sala de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="8a137-133">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="8a137-134">Implementación de salón de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="8a137-134">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="8a137-135">Configurar una consola de v2 de sistemas de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="8a137-135">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="8a137-136">Administración de salón de Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="8a137-136">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
---
title: Implementación de salón de Skype v2 de sistemas con Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Skype para Business Server.
ms.openlocfilehash: db4551e91d808161d52e73033df8234001f21de3
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883949"
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a><span data-ttu-id="c643d-103">Implementación de salón de Skype v2 de sistemas con Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c643d-103">Deploy Skype Room Systems v2 with Skype for Business Server</span></span>
  
<span data-ttu-id="c643d-104">En este tema se explica cómo agregar una cuenta de dispositivo para sistemas de salón de Skype v2 cuando tiene una implementación de bosque único, local.</span><span class="sxs-lookup"><span data-stu-id="c643d-104">This topic explains how you add a device account for Skype Room Systems v2 when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="c643d-105">Si tiene un solo bosque, implementación de local con Exchange 2013 SP1 o posterior y Skype para Business Server 2015 o posterior, puede usar los scripts de Windows PowerShell proporcionados para crear cuentas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c643d-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="c643d-106">Si utiliza una implementación de varios bosque, puede usar cmdlets de equivalentes que se producen los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="c643d-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="c643d-107">Estos cmdlets se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="c643d-107">Those cmdlets are described in this section.</span></span>

<span data-ttu-id="c643d-108">La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="c643d-108">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="c643d-109">Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudarle a convertirlas en cuentas de usuario de v2 de Skype salón sistemas compatibles.</span><span class="sxs-lookup"><span data-stu-id="c643d-109">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="c643d-110">Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que se va a usar el dispositivo v2 de sistemas de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="c643d-110">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a><span data-ttu-id="c643d-111">Implementación de salón de Skype v2 de sistemas con Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c643d-111">Deploy Skype Room Systems v2 with Skype for Business Server</span></span>

<span data-ttu-id="c643d-112">Antes de implementar sistemas de salón de Skype v2 con Skype Business Server, debe asegurarse de que cumplen los requisitos.</span><span class="sxs-lookup"><span data-stu-id="c643d-112">Before you deploy Skype Room Systems v2 with Skype for Business Server, be sure you have met the requirements.</span></span> <span data-ttu-id="c643d-113">Para obtener más información, vea [requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c643d-113">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="c643d-114">Antes de comenzar a implementar sistemas de salón de Skype v2, asegúrese de que tiene los permisos adecuados para ejecutar los cmdlets de asociados.</span><span class="sxs-lookup"><span data-stu-id="c643d-114">Before you begin to deploy Skype Room Systems v2, be sure you have the right permissions to run the associated cmdlets.</span></span>
  
1. <span data-ttu-id="c643d-115">Iniciar una sesión remota de Windows PowerShell desde un PC y conectarse a Exchange.</span><span class="sxs-lookup"><span data-stu-id="c643d-115">Start a remote Windows PowerShell session from a PC and connect to Exchange.</span></span> 
    
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

   <span data-ttu-id="c643d-116">Tenga en cuenta que $strExchangeServer es el nombre de dominio completo (FQDN) del servidor de Exchange, y $strLyncFQDN es el FQDN de su Skype para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="c643d-116">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>
    
2. <span data-ttu-id="c643d-117">Después de establecer una sesión, podrá crear un nuevo buzón y habilitar como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="c643d-117">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="c643d-118">Esto le permitirá la cuenta autenticar a los sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="c643d-118">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
    <span data-ttu-id="c643d-119">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="c643d-119">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="c643d-120">Si está creando un nuevo buzón de recursos:</span><span class="sxs-lookup"><span data-stu-id="c643d-120">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="c643d-121">Puede establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de reunión para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c643d-121">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="c643d-122">Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c643d-122">You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="c643d-123">Si decide que la contraseña no caduca, puede establecer con los cmdlets de Windows PowerShell demasiado.</span><span class="sxs-lookup"><span data-stu-id="c643d-123">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="c643d-124">Vea Administración de etiquetas para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c643d-124">See Password management for more information.</span></span>
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="c643d-125">Habilite la cuenta en Active Directory, por lo que autenticará a sistemas de salón de Skype v2.</span><span class="sxs-lookup"><span data-stu-id="c643d-125">Enable the account in Active Directory so it will authenticate to Skype Room Systems v2.</span></span>
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="c643d-126">Habilitar la cuenta del dispositivo con Skype para Business Server mediante la habilitación de la cuenta de Active Directory v2 sistemas de salón de Skype en un Skype para grupo de servidores de negocio:</span><span class="sxs-lookup"><span data-stu-id="c643d-126">Enable the device account with Skype for Business Server by enabling your Skype Room Systems v2 Active Directory account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="c643d-127">Tendrá que usar la dirección SIP (protocolo de inicio de sesión) y el controlador de dominio del proyecto</span><span class="sxs-lookup"><span data-stu-id="c643d-127">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span> 
    
7. <span data-ttu-id="c643d-128">**Opcional.**</span><span class="sxs-lookup"><span data-stu-id="c643d-128">**Optional.**</span></span> <span data-ttu-id="c643d-129">También puede permitir v2 de sistemas de salón de Skype realizar y recibir llamadas telefónicas de telefónica conmutada (RTC) de la red mediante la habilitación de Enterprise Voice para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="c643d-129">You can also allow Skype Room Systems v2 to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="c643d-130">Enterprise Voice no es un requisito para sistemas de salón de Skype v2, pero si desea que la funcionalidad de marcado de RTC para el cliente de v2 de sistemas de salón de Skype, aquí es cómo habilitarla:</span><span class="sxs-lookup"><span data-stu-id="c643d-130">Enterprise Voice isn't a requirement for Skype Room Systems v2, but if you want PSTN dialing functionality for the Skype Room Systems v2 client, here's how to enable it:</span></span>
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="c643d-p108">De nuevo, tendrá que reemplazar el controlador de dominio y los números de teléfono que se han proporcionado como ejemplo con su propia información. El valor de parámetro $true no se modifica.</span><span class="sxs-lookup"><span data-stu-id="c643d-p108">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="c643d-133">Ejemplo: sala cuenta el programa de instalación de Exchange y de Skype para Business Server local</span><span class="sxs-lookup"><span data-stu-id="c643d-133">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c643d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c643d-134">See also</span></span>

[<span data-ttu-id="c643d-135">Configurar cuentas para sistemas de salón de Skype v2</span><span class="sxs-lookup"><span data-stu-id="c643d-135">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="c643d-136">Plan para Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="c643d-136">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="c643d-137">Implementar Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="c643d-137">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="c643d-138">Configurar una consola de Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="c643d-138">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="c643d-139">Administrar Sistemas de salas de Skype v2</span><span class="sxs-lookup"><span data-stu-id="c643d-139">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
---
title: Implementación de salas de equipos de Microsoft con Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos con Skype para Business Server.
ms.openlocfilehash: e5ba372a5990f7c63827f1f8b0426e67ae48b620
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012479"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="e1c49-103">Implementación de salas de equipos de Microsoft con Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e1c49-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="e1c49-104">En este tema se explica cómo agregar una cuenta de dispositivo para salas de equipos de Microsoft cuando tiene una implementación local de bosque único.</span><span class="sxs-lookup"><span data-stu-id="e1c49-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="e1c49-105">Si tiene un solo bosque, implementación de local con Exchange 2013 SP1 o posterior y Skype para Business Server 2015 o posterior, puede usar los scripts de Windows PowerShell proporcionados para crear cuentas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1c49-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="e1c49-106">Si utiliza una implementación de varios bosque, puede usar cmdlets de equivalentes que se producen los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="e1c49-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="e1c49-107">Estos cmdlets se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="e1c49-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="e1c49-108">Antes de comenzar a implementar salones de los equipos de Microsoft, asegúrese de que tiene los permisos adecuados para ejecutar los cmdlets de asociados.</span><span class="sxs-lookup"><span data-stu-id="e1c49-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   <span data-ttu-id="e1c49-109">Tenga en cuenta que $strExchangeServer es el nombre de dominio completo (FQDN) del servidor de Exchange, y $strLyncFQDN es el FQDN de su Skype para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="e1c49-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="e1c49-110">Después de establecer una sesión, podrá crear un nuevo buzón y habilitar como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="e1c49-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="e1c49-111">Esto le permitirá la cuenta autenticar a los salones de los equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1c49-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="e1c49-112">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="e1c49-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="e1c49-113">Si está creando un nuevo buzón de recursos:</span><span class="sxs-lookup"><span data-stu-id="e1c49-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="e1c49-114">Puede establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de reunión para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e1c49-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="e1c49-115">Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="e1c49-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="e1c49-116">Si decide que la contraseña no caduca, puede establecer con los cmdlets de Windows PowerShell demasiado.</span><span class="sxs-lookup"><span data-stu-id="e1c49-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="e1c49-117">Vea Administración de etiquetas para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e1c49-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="e1c49-118">Habilite la cuenta de Active Directory, por lo que va a autenticar a los salones de los equipos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1c49-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="e1c49-119">Habilitar la cuenta del dispositivo con Skype para Business Server mediante la habilitación de su cuenta de salas de equipos de Microsoft Active Directory en un Skype para grupo de servidores de negocio:</span><span class="sxs-lookup"><span data-stu-id="e1c49-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="e1c49-120">Tendrá que usar la dirección SIP (protocolo de inicio de sesión) y el controlador de dominio del proyecto</span><span class="sxs-lookup"><span data-stu-id="e1c49-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="e1c49-121">**Opcional.**</span><span class="sxs-lookup"><span data-stu-id="e1c49-121">**Optional.**</span></span> <span data-ttu-id="e1c49-122">También puede permitir que Microsoft salones de los equipos realizar y recibir llamadas telefónicas de telefónica conmutada (RTC) de la red mediante la habilitación de Enterprise Voice para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="e1c49-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="e1c49-123">Enterprise Voice no es un requisito para salas de equipos de Microsoft, pero si desea que la funcionalidad de marcado de RTC para el cliente de salas de equipos de Microsoft, aquí es cómo habilitarla:</span><span class="sxs-lookup"><span data-stu-id="e1c49-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="e1c49-p106">De nuevo, tendrá que reemplazar el controlador de dominio y los números de teléfono que se han proporcionado como ejemplo con su propia información. El valor de parámetro $true no se modifica.</span><span class="sxs-lookup"><span data-stu-id="e1c49-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="e1c49-126">Ejemplo: sala cuenta el programa de instalación de Exchange y de Skype para Business Server local</span><span class="sxs-lookup"><span data-stu-id="e1c49-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

``` Powershell
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

## <a name="see-also"></a><span data-ttu-id="e1c49-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1c49-127">See also</span></span>

[<span data-ttu-id="e1c49-128">Configurar las cuentas para salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1c49-128">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="e1c49-129">Plan para salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1c49-129">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="e1c49-130">Implementación de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1c49-130">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="e1c49-131">Configurar una consola de salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1c49-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="e1c49-132">Administrar las salas de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1c49-132">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
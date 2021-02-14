---
title: Implementar salas de Microsoft Teams con Skype Empresarial Server
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Skype Empresarial Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662265"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="10410-103">Implementar salas de Microsoft Teams con Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="10410-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="10410-104">En este tema se explica cómo agregar una cuenta de dispositivo para Microsoft Teams Rooms cuando tiene un solo bosque, implementación local.</span><span class="sxs-lookup"><span data-stu-id="10410-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="10410-105">Si tiene un solo bosque, implementación local con Exchange 2013 SP1 o posterior y Skype Empresarial Server 2015 o posterior, puede usar los scripts de Windows PowerShell proporcionados para crear cuentas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="10410-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="10410-106">Si usa una implementación de varios bosques, puede usar cmdlets equivalentes que producirán los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="10410-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="10410-107">Estos cmdlets se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="10410-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="10410-108">Antes de empezar a implementar Salas de Microsoft Teams, asegúrese de que tiene los permisos adecuados para ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="10410-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="10410-109">Tenga en cuenta $strExchangeServer es el nombre de dominio completo (FQDN) de su servidor de Exchange y $strLyncFQDN es el FQDN de la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="10410-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="10410-110">Después de establecer una sesión, debe crear un buzón nuevo y habilitarlo como RoomMailboxAccount, o cambiar la configuración de un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="10410-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="10410-111">Esto permitirá que la cuenta se autentique en Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10410-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="10410-112">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="10410-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="10410-113">Si está creando un nuevo buzón de recursos:</span><span class="sxs-lookup"><span data-stu-id="10410-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="10410-114">Puede establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de reunión de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="10410-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="10410-115">Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="10410-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="10410-116">Si decide que la contraseña no expire, también puede establecerla con Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="10410-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="10410-117">Vea Administración de etiquetas para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="10410-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="10410-118">Habilite la cuenta en Active Directory para que se autentique en Salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10410-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="10410-119">Habilite la cuenta del dispositivo con Skype Empresarial Server habilitando su cuenta de Microsoft Teams Rooms Active Directory en un grupo de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="10410-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="10410-120">Tendrá que usar la dirección SIP (protocolo de inicio de sesión) y el controlador de dominio del proyecto</span><span class="sxs-lookup"><span data-stu-id="10410-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="10410-121">**Opcional.**</span><span class="sxs-lookup"><span data-stu-id="10410-121">**Optional.**</span></span> <span data-ttu-id="10410-122">También puede permitir que los salas de Microsoft Teams realicen y reciban llamadas telefónicas con red telefónica conmutada (RTC) habilitando Telefonía IP empresarial para su cuenta.</span><span class="sxs-lookup"><span data-stu-id="10410-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="10410-123">Telefonía IP empresarial no es un requisito para Salas de Microsoft Teams, pero si desea la funcionalidad de marcación RTC para el cliente de salas de Microsoft Teams, aquí le explicamos cómo habilitarlo:</span><span class="sxs-lookup"><span data-stu-id="10410-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="10410-p106">De nuevo, tendrá que reemplazar el controlador de dominio y los números de teléfono que se han proporcionado como ejemplo con su propia información. El valor de parámetro $true no se modifica.</span><span class="sxs-lookup"><span data-stu-id="10410-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="10410-126">Ejemplo: configuración de cuenta de sala en Exchange y Skype Empresarial Server local</span><span class="sxs-lookup"><span data-stu-id="10410-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="10410-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="10410-127">Related topics</span></span>

[<span data-ttu-id="10410-128">Configurar cuentas de Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10410-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="10410-129">Plan para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10410-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="10410-130">Implementar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10410-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="10410-131">Configurar una consola de sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10410-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="10410-132">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10410-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

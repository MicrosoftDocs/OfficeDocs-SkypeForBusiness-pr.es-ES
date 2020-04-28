---
title: Implementar salas de Microsoft Teams con Skype empresarial Server
ms.author: v-lanac
author: lanachin
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
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Skype empresarial Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9e827f4d1fc020160b59f26dffde960394c3a69e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905272"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="86c01-103">Implementar salas de Microsoft Teams con Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="86c01-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="86c01-104">En este tema se explica cómo agregar una cuenta de dispositivo para salas de Microsoft Teams cuando tiene una implementación local de un solo bosque.</span><span class="sxs-lookup"><span data-stu-id="86c01-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="86c01-105">Si tiene una implementación local de un solo bosque con Exchange 2013 SP1 o posterior y Skype empresarial Server 2015 o posterior, puede usar los scripts de Windows PowerShell proporcionados para crear cuentas de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="86c01-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="86c01-106">Si está usando una implementación de varios bosques, puede usar cmdlets equivalentes que produzcan los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="86c01-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="86c01-107">Estos cmdlets se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="86c01-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="86c01-108">Antes de empezar a implementar salas de Microsoft Teams, asegúrese de tener los permisos correctos para ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="86c01-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="86c01-109">Tenga en cuenta que $strExchangeServer es el nombre de dominio completo (FQDN) del servidor de Exchange y $strLyncFQDN es el FQDN de su implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="86c01-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="86c01-110">Después de establecer una sesión, cree un nuevo buzón de correo y lo habilite como RoomMailboxAccount, o cambie la configuración de un buzón de sala existente.</span><span class="sxs-lookup"><span data-stu-id="86c01-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="86c01-111">Esto permitirá que la cuenta se autentique en las salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86c01-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="86c01-112">Si va a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="86c01-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="86c01-113">Si va a crear un nuevo buzón de recursos:</span><span class="sxs-lookup"><span data-stu-id="86c01-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="86c01-114">Puede establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de reunión de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="86c01-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="86c01-115">Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="86c01-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="86c01-116">Si decide que la contraseña no haya expirado, puede establecerla con los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="86c01-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="86c01-117">Vea Administración de etiquetas para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86c01-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="86c01-118">Habilite la cuenta en Active Directory para que se autentique en las salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86c01-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="86c01-119">Habilite la cuenta del dispositivo con Skype empresarial Server habilitando la cuenta de Active Directory de las salas de Microsoft Teams en un grupo de servidores de Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="86c01-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="86c01-120">Tendrá que usar la dirección SIP (protocolo de inicio de sesión) y el controlador de dominio del proyecto</span><span class="sxs-lookup"><span data-stu-id="86c01-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="86c01-121">**Opcional.**</span><span class="sxs-lookup"><span data-stu-id="86c01-121">**Optional.**</span></span> <span data-ttu-id="86c01-122">También puedes permitir que las salas de Microsoft Teams realicen y reciban llamadas de red de telefonía pública conmutada (RTC) habilitando la telefonía IP empresarial de tu cuenta.</span><span class="sxs-lookup"><span data-stu-id="86c01-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="86c01-123">La telefonía IP empresarial no es un requisito para las salas de Microsoft Teams, pero si quiere la función de marcado RTC para el cliente de Microsoft Teams Rooms, a continuación se explica cómo habilitarla:</span><span class="sxs-lookup"><span data-stu-id="86c01-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="86c01-p106">De nuevo, tendrá que reemplazar el controlador de dominio y los números de teléfono que se han proporcionado como ejemplo con su propia información. El valor de parámetro $true no se modifica.</span><span class="sxs-lookup"><span data-stu-id="86c01-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="86c01-126">Ejemplo: configuración de la cuenta Room en Exchange y Skype empresarial Server local</span><span class="sxs-lookup"><span data-stu-id="86c01-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="86c01-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="86c01-127">Related topics</span></span>

[<span data-ttu-id="86c01-128">Configurar cuentas para salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86c01-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="86c01-129">Plan para Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86c01-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="86c01-130">Implementar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86c01-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="86c01-131">Configurar una consola de sala de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86c01-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="86c01-132">Administrar Salas de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86c01-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

---
title: Scripts de configuración de salas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a66067d2-22b0-48f1-a5d0-e0cd0ece2e5a
description: Lea este tema para encontrar scripts de ejemplo para el aprovisionamiento de las cuentas de Sistema de salas de Skype.
ms.openlocfilehash: 7c462dea9f1a885fbf8a4fb4f6aeee4ca4f8c3d3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235029"
---
# <a name="skype-room-system-room-setup-scripts"></a><span data-ttu-id="a52b5-103">Scripts de configuración de salas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="a52b5-103">Skype Room System room setup scripts</span></span>
 
<span data-ttu-id="a52b5-104">Lea este tema para encontrar scripts de ejemplo para el aprovisionamiento de las cuentas de Sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="a52b5-104">Read this topic to find sample scripts for provisioning Skype Room System accounts.</span></span>
  
<span data-ttu-id="a52b5-105">En esta sección se muestran ejemplos de secuencias de comandos que se pueden usar para aprovisionar cuentas del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="a52b5-105">This section illustrates sample scripts that can be used to provision Skype Room System accounts.</span></span> <span data-ttu-id="a52b5-106">Estos scripts se muestran únicamente para fines ilustrativos y solo deben usarse previa consulta con el experto o administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="a52b5-106">These scripts are for illustrative purposes only and should be used only after consulting with your IT expert or domain administrator.</span></span>
  
## <a name="example-setup-script-skype-for-business-and-exchange-server-on-premises"></a><span data-ttu-id="a52b5-107">Script de configuración de ejemplo: Skype empresarial y Exchange Server (local)</span><span class="sxs-lookup"><span data-stu-id="a52b5-107">Example Setup Script: Skype for Business and Exchange Server (On Premises)</span></span>

```
# On Exchange 
Set-Mailbox -Identity confroom@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a 
Lync Meeting to take advantage of enhanced meeting experience from LRS"

Set-CalendarProcessing -id confroom@contoso.com -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse 
$true -AdditionalResponse "This is an LRS room!" -DeleteSubject $false -AutomateProcessing AutoAccept 
# The following is used to preserve the Lync Meeting invitations - so create these based on your Lync Federated partners# Per Lync Federated Partner as a Recommended Practice to ensure Meetings show in Lync with Join#New-RemoteDomain -DomainName Microsoft.com -Name Microsoft$true#Set-RemoteDomain -Identity Microsoft -TNEFEnabled $true
Set-ADAccountPassword -Identity "conference room"# Paste the next command on its own. Enter a blank password first, then enter the new password "password" twiceEnable-ADAccount -Identity "confroom"# On LyncEnable-CsMeetingRoom -SipAddress "sip:confroom@contoso.com" -RegistrarPool cie-srv-02.contoso.com -Identity 'conference room' 
Set-CsMeetingRoom -Identity "conference room" -LineURI "tel:+14255551669;ext=1669" -EnterpriseVoiceEnabled $true
```

## <a name="example-setup-script-skype-for-business-and-exchange-server-online"></a><span data-ttu-id="a52b5-108">Script de configuración de ejemplo: Skype empresarial y Exchange Server online</span><span class="sxs-lookup"><span data-stu-id="a52b5-108">Example Setup Script: Skype for Business and Exchange Server Online</span></span>

<span data-ttu-id="a52b5-109">Asegúrese de haber revisado los siguientes requisitos previos antes de ejecutar el script:</span><span class="sxs-lookup"><span data-stu-id="a52b5-109">Make sure you've reviewed the following prerequisites before running the script:</span></span>
  
- <span data-ttu-id="a52b5-110">Microsoft Online Services - Asistente para el inicio de sesión para profesionales de TI BETA</span><span class="sxs-lookup"><span data-stu-id="a52b5-110">Microsoft Online Services Sign-In Assistant for IT Professionals BETA</span></span>
    
- <span data-ttu-id="a52b5-111">Módulo Microsoft Azure Active Directory para Windows PowerShell (versión de 64 bits) o (versión de 32 bits)</span><span class="sxs-lookup"><span data-stu-id="a52b5-111">Windows Azure Active Directory Module for Windows PowerShell (64-bit version) or (32-bit version)</span></span>
    
- <span data-ttu-id="a52b5-112">Módulo de Windows PowerShell para Lync Online</span><span class="sxs-lookup"><span data-stu-id="a52b5-112">Windows PowerShell Module for Lync Online</span></span>
    
- <span data-ttu-id="a52b5-113">Reinicie si es necesario</span><span class="sxs-lookup"><span data-stu-id="a52b5-113">Reboot if needed</span></span>
    
```
# Note you have to enter each command one at a time and update any bold fields for your environment
$rm="LyncRoom"
$org='YourTenantName.onmicrosoft.com'
$rmURI="$rm@$org"$newpass='MyPass@word1'# This Section Signs into Remote PowerShell
$cred=Get-Credential admin@$org
$sess=New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication basic -ConnectionUri https://ps.outlook.com/powershell
Import-PSSession $sess
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred
Import-PSSession $cssess -AllowClobber
Connect-MsolService -Credential $cred# This Section Create the Calendar Mailbox and Enables it for Lync
New-Mailbox -MicrosoftOnlineServicesID $rmURI -room -Name $rm -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
 -EnableRoomMailboxAccount $true

Set-CalendarProcessing -Identity $rmURI -DeleteSubject $false -AutomateProcessing AutoAccept 
Set-CalendarProcessing -Identity $rmURI -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse $true -AdditionalResponse
 "This is an LRS room!"# Configure the Account to Not Expire
Set-MsolUser -UserPrincipalName $rm -PasswordNeverExpires $true# You need to detect your Lync Pool Registrar name. Using a normal Offic365/LyncOnline user account from your tenant, run the next command and update the RegistrarPool value for the second command coming up
Get-CsOnlineUser -Identity 'admin@YourTenantName.onmicrosoft.com' | fl *registrar*# Update with above result
Enable-CsMeetingRoom -Identity $rmURI -RegistrarPool "sippoolsn20a07.infra.lync.com" -SipAddressType EmailAddress
# If the previous command fails with an error regarding the account name not being found you might need to wait and try again in a few minutes. If you wait too long, you'll need to sign in again to remote PowerShell as detailed above.
```



---
title: Implementar Salas de Microsoft Teams con Skype Empresarial Server
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
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Skype Empresarial Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662265"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Implementar Salas de Microsoft Teams con Skype Empresarial Server
  
En este tema se explica cómo agregar una cuenta de dispositivo para Salas de Microsoft Teams cuando tiene una implementación local de un solo bosque.
  
Si tiene una implementación local de un solo bosque con Exchange 2013 SP1 o posterior y Skype Empresarial Server 2015 o posterior, puede usar los scripts de Windows PowerShell proporcionados para crear cuentas de dispositivo. Si usa una implementación de varios bosques, puede usar cmdlets equivalentes que producirán los mismos resultados. Estos cmdlets se describen en esta sección.

  
Antes de empezar a implementar Salas de Microsoft Teams, asegúrese de que tiene los permisos adecuados para ejecutar los cmdlets asociados.
  

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

   Tenga en cuenta que $strExchangeServer es el nombre de dominio completo (FQDN) de su servidor de Exchange y $strLyncFQDN es el FQDN de su Skype Empresarial Server implementación.

2. Después de establecer una sesión, creará un buzón nuevo y lo habilitará como RoomMailboxAccount, o bien cambiará la configuración de un buzón de sala existente. Esto permitirá que la cuenta se autentique para Salas de Microsoft Teams.

    Si va a cambiar un buzón de recursos existente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Si va a crear un buzón de recursos nuevo:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Puede establecer varias propiedades Exchange en la cuenta del dispositivo para mejorar la experiencia de reunión de los usuarios. Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Si decide que la contraseña no expire, también puede establecerla con Windows PowerShell cmdlets. Vea Administración de etiquetas para obtener más información.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Habilite la cuenta en Active Directory para que se autentique para Salas de Microsoft Teams.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Habilite la cuenta del dispositivo con Skype Empresarial Server habilitando su cuenta Salas de Microsoft Teams Active Directory en un Skype Empresarial Server grupo de servidores:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Tendrá que usar la dirección SIP (protocolo de inicio de sesión) y el controlador de dominio del proyecto

7. **Opcional.** También puede permitir que Salas de Microsoft Teams y reciba llamadas telefónicas de red telefónica conmutada (RTC) activando Telefonía IP empresarial para su cuenta. Telefonía IP empresarial no es un requisito para Salas de Microsoft Teams, pero si desea la funcionalidad de marcado RTC para el cliente de Salas de Microsoft Teams, aquí le explicamos cómo habilitarlo:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   De nuevo, tendrá que reemplazar el controlador de dominio y los números de teléfono que se han proporcionado como ejemplo con su propia información. El valor de parámetro $true no se modifica.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Ejemplo: configuración de cuenta de salón en Exchange y Skype Empresarial Server local

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

## <a name="related-topics"></a>Temas relacionados

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)

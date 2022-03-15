---
title: Implementar Salas de Microsoft Teams con Skype Empresarial Server
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Skype Empresarial Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 358fa9295ec150f9c57a18252c76d309078b8e29
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503487"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Implementar Salas de Microsoft Teams con Skype Empresarial Server
  
En este tema se explica cómo agregar una cuenta de recursos para Salas de Microsoft Teams cuando tiene una implementación local de un solo bosque.
  
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
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Si va a crear un buzón de recursos nuevo:

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Puede establecer varias propiedades de Exchange en la Salas de Teams de recursos para mejorar la experiencia de reunión de los usuarios. Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. Desactive la expiración de la contraseña en la cuenta de recursos.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. Habilite la cuenta de recursos en Active Directory para que se autentique en Salas de Microsoft Teams.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. Habilite la cuenta de recursos con Skype Empresarial Server habilitando su cuenta Salas de Microsoft Teams Active Directory en un Skype Empresarial Server grupo de servidores:

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    Cambie los atributos `-DomainController` y `-RegistrarPool` a los valores adecuados para su entorno.

7. **Opcional.** También puede permitir que Salas de Microsoft Teams y reciba llamadas telefónicas de red telefónica conmutada (RTC) al habilitar Telefonía IP empresarial para su cuenta. Telefonía IP empresarial no es un requisito para Salas de Microsoft Teams, pero si desea la funcionalidad de marcado RTC para Salas de Microsoft Teams, aquí le explicamos cómo habilitarla:

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   De nuevo, tendrá que reemplazar el controlador de dominio y los números de teléfono que se han proporcionado como ejemplo con su propia información. El valor de parámetro $true no se modifica. También tendrá que reemplazar los nombres de directiva de directiva de voz y plan de marcado.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Ejemplo: configuración de cuenta de salón en Exchange y Skype Empresarial Server local

``` Powershell
New-Mailbox -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) -UserPrincipalName ConferenceRoom01@contoso.com

Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"

Enable-CsMeetingRoom -Identity ConferenceRoom01@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity ConferenceRoom01 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName dk
Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName e15dp2.contoso.com
```

## <a name="related-topics"></a>Temas relacionados

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)

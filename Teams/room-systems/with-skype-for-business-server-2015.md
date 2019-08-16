---
title: Implementar salas de Microsoft Teams con Skype empresarial Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Skype empresarial Server.
ms.openlocfilehash: 0c970adeae5531b76b1ebfe55ab750efe8bd3ba3
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427769"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Implementar salas de Microsoft Teams con Skype empresarial Server
  
En este tema se explica cómo agregar una cuenta de dispositivo para salas de Microsoft Teams cuando tiene una implementación local de un solo bosque.
  
Si tiene una implementación local de un solo bosque con Exchange 2013 SP1 o posterior y Skype empresarial Server 2015 o posterior, puede usar los scripts de Windows PowerShell proporcionados para crear cuentas de dispositivos. Si está usando una implementación de varios bosques, puede usar cmdlets equivalentes que produzcan los mismos resultados. Estos cmdlets se describen en esta sección.

  
Antes de empezar a implementar salas de Microsoft Teams, asegúrese de tener los permisos correctos para ejecutar los cmdlets asociados.
  

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

   Tenga en cuenta que $strExchangeServer es el nombre de dominio completo (FQDN) del servidor de Exchange y $strLyncFQDN es el FQDN de su implementación de Skype empresarial Server.

2. Después de establecer una sesión, cree un nuevo buzón de correo y lo habilite como RoomMailboxAccount, o cambie la configuración de un buzón de sala existente. Esto permitirá que la cuenta se autentique en las salas de Microsoft Teams.

    Si va a cambiar un buzón de recursos existente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Si va a crear un nuevo buzón de recursos:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Puede establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de reunión de los usuarios. Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Si decide que la contraseña no haya expirado, puede establecerla con los cmdlets de Windows PowerShell. Vea Administración de etiquetas para obtener más información.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Habilite la cuenta en Active Directory para que se autentique en las salas de Microsoft Teams.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Habilite la cuenta del dispositivo con Skype empresarial Server habilitando la cuenta de Active Directory de las salas de Microsoft Teams en un grupo de servidores de Skype empresarial:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Tendrá que usar la dirección SIP (protocolo de inicio de sesión) y el controlador de dominio del proyecto

7. **Opcional.** También puedes permitir que las salas de Microsoft Teams realicen y reciban llamadas de red de telefonía pública conmutada (RTC) habilitando la telefonía IP empresarial de tu cuenta. La telefonía IP empresarial no es un requisito para las salas de Microsoft Teams, pero si quiere la función de marcado RTC para el cliente de Microsoft Teams Rooms, a continuación se explica cómo habilitarla:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   De nuevo, tendrá que reemplazar el controlador de dominio y los números de teléfono que se han proporcionado como ejemplo con su propia información. El valor de parámetro $true no se modifica.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Ejemplo: configuración de la cuenta Room en Exchange y Skype empresarial Server local

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

## <a name="see-also"></a>Vea también

[Configurar cuentas para salas de Microsoft Teams](room-systems-v2-configure-accounts.md)

[Plan para salas de Microsoft Teams](skype-room-systems-v2-0.md)
  
[Implementar salas de Microsoft Teams](room-systems-v2.md)
  
[Configurar una consola de salas de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

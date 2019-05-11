---
title: Implementación de salas de equipos de Microsoft con Skype para Business Server
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: f62006dc3f83d6f60c224f8e75ba4958ff0a7bfc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915800"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Implementación de salas de equipos de Microsoft con Skype para Business Server
  
En este tema se explica cómo agregar una cuenta de dispositivo para salas de equipos de Microsoft cuando tiene una implementación local de bosque único.
  
Si tiene un solo bosque, implementación de local con Exchange 2013 SP1 o posterior y Skype para Business Server 2015 o posterior, puede usar los scripts de Windows PowerShell proporcionados para crear cuentas de dispositivo. Si utiliza una implementación de varios bosque, puede usar cmdlets de equivalentes que se producen los mismos resultados. Estos cmdlets se describen en esta sección.

  
Antes de comenzar a implementar salones de los equipos de Microsoft, asegúrese de que tiene los permisos adecuados para ejecutar los cmdlets de asociados.
  

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

   Tenga en cuenta que $strExchangeServer es el nombre de dominio completo (FQDN) del servidor de Exchange, y $strLyncFQDN es el FQDN de su Skype para la implementación de Business Server.

2. Después de establecer una sesión, podrá crear un nuevo buzón y habilitar como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente. Esto le permitirá la cuenta autenticar a los salones de los equipos de Microsoft.

    Si va a cambiar un buzón de recursos existente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Si está creando un nuevo buzón de recursos:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Puede establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de reunión para los usuarios. Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Si decide que la contraseña no caduca, puede establecer con los cmdlets de Windows PowerShell demasiado. Vea Administración de etiquetas para obtener más información.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Habilite la cuenta de Active Directory, por lo que va a autenticar a los salones de los equipos de Microsoft.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Habilitar la cuenta del dispositivo con Skype para Business Server mediante la habilitación de su cuenta de salas de equipos de Microsoft Active Directory en un Skype para grupo de servidores de negocio:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Tendrá que usar la dirección SIP (protocolo de inicio de sesión) y el controlador de dominio del proyecto

7. **Opcional.** También puede permitir que Microsoft salones de los equipos realizar y recibir llamadas telefónicas de telefónica conmutada (RTC) de la red mediante la habilitación de Enterprise Voice para su cuenta. Enterprise Voice no es un requisito para salas de equipos de Microsoft, pero si desea que la funcionalidad de marcado de RTC para el cliente de salas de equipos de Microsoft, aquí es cómo habilitarla:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   De nuevo, tendrá que reemplazar el controlador de dominio y los números de teléfono que se han proporcionado como ejemplo con su propia información. El valor de parámetro $true no se modifica.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Ejemplo: sala cuenta el programa de instalación de Exchange y de Skype para Business Server local

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

[Configurar las cuentas para salas de equipos de Microsoft](room-systems-v2-configure-accounts.md)

[Plan para salas de equipos de Microsoft](skype-room-systems-v2-0.md)
  
[Implementación de salas de equipos de Microsoft](room-systems-v2.md)
  
[Configurar una consola de salas de equipos de Microsoft](console.md)
  
[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

---
title: Implementar Sistemas de salas de Skype v2 con Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lea este tema para obtener información sobre cómo implementar sistemas de salas de Skype v2 con Skype para Business Server 2015.
ms.openlocfilehash: 904835e766283791f52c0dc1d1221a0d7253e3e1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a>Implementar Sistemas de salas de Skype v2 con Skype Empresarial Server 2015
 
Lea este tema para obtener información sobre cómo implementar sistemas de salas de Skype v2 con Skype para Business Server 2015.
  
En este tema se explica cómo agregar una cuenta de dispositivo para sistemas de salas de Skype v2 cuando tiene una implementación de bosque único, local.
  
Si tiene un solo bosque, implementación de local con Exchange 2013 SP1 o posterior y Skype para Business Server 2015 o posterior, puede utilizar las secuencias de comandos de Windows PowerShell proporcionados para crear cuentas de dispositivo. Si utiliza una implementación de varios bosque, puede utilizar cmdlets equivalentes que se generan los mismos resultados. Estos cmdlets se describen en esta sección.
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a>Implementar Sistemas de salas de Skype v2 con Skype Empresarial Server 2015

Antes de implementar sistemas de salas de Skype v2 con Skype para Business Server 2015, asegúrese de que cumple los requisitos. Para obtener más información, vea [requisitos de los sistemas de salas de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Antes de empezar a implementar sistemas de salas de Skype v2, asegúrese de que tiene los permisos adecuados para ejecutar los cmdlets asociados.
  
1. Iniciar una sesión remota de Windows PowerShell desde un PC y conectar a Exchange. 
    
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

   Tenga en cuenta que $strExchangeServer es el nombre de dominio completo (FQDN) del servidor de Exchange, y $strLyncFQDN es el nombre completo de su Skype para la implementación de Business Server 2015.
    
2. Después de establecer una sesión, podrá crear un nuevo buzón y habilitarlo como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente. Esto permitirá que la cuenta autenticar a los sistemas de salas de Skype v2.
    
    Si va a cambiar un buzón de recursos existente:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Si desea crear un nuevo buzón de recursos:
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Puede establecer diversas propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de reunión para las personas. Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Si decide que la contraseña no caduca, puede establecer con los cmdlets de Windows PowerShell demasiado. Vea Administración de etiquetas para obtener más información.
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Habilitar la cuenta en Active Directory, por lo que se autenticará en sistemas de salas de Skype v2.
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Habilitar la cuenta del dispositivo con Skype para Business Server 2015 habilitando la cuenta de Active Directory v2 de sistemas de salas de Skype en un Skype para Business Server 2015 pool:
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Tendrá que usar la dirección SIP (protocolo de inicio de sesión) y el controlador de dominio del proyecto 
    
7. **Opcional.** También puede permitir a sistemas de salas de Skype v2 hacer y recibir llamadas telefónicas de telefónica pública conmutada (PSTN) de red habilitando la Telefonía IP empresarial para su cuenta. Telefonía IP empresarial no es un requisito para los sistemas de salas de Skype v2, pero si desea la funcionalidad marcado PSTN para el cliente de sistemas de salas de Skype v2, explicamos cómo habilitarla:
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01

   ```

   De nuevo, tendrá que reemplazar el controlador de dominio y los números de teléfono que se han proporcionado como ejemplo con su propia información. El valor de parámetro $true no se modifica.
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-2015-on-premises"></a>Ejemplo: sala de cuenta configurado en Exchange y Skype para Business Server 2015 en locales

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

## <a name="see-also"></a>Vea también

#### 

[Plan para la sala de Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implementar sala de Skype v2 de sistemas](room-systems-v2.md)
  
[Configurar una consola de sistemas de salas de Skype v2](console.md)
  
[Administrar espacio de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


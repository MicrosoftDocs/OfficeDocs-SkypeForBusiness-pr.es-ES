---
title: Implementar Sistemas de salas de Skype v2 con Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información sobre cómo implementar sistemas de salas de Skype v2 con Office 365.
ms.openlocfilehash: b05afbf973e814c5adf7b8a8490aefa0cbb04886
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>Implementar Sistemas de salas de Skype v2 con Office 365 
 
Lea este tema para obtener información sobre cómo implementar sistemas de salas de Skype v2 con Office 365.
  
En este tema se describe cómo agregar una cuenta de dispositivo para sistemas de salas de Skype v2 cuando tiene una implementación en línea de Office 365.
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a>Implementar Sistemas de salas de Skype v2 con Office 365 

Antes de implementar sistemas de salas de Skype v2 con Office 365, asegúrese de que cumple los requisitos. Para obtener más información, vea [requisitos de los sistemas de salas de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Para habilitar Skype para el negocio, debe tener lo siguiente:
  
- Skype para los negocios en línea (Plan 2) o superior en su plan de Office 365. El plan debe admitir la funcionalidad de conferencias.
    
- Si necesita Telefonía IP empresarial (telefonía PSTN) mediante proveedores de servicios de telefonía para sistemas de salas de Skype v2 necesita Skype para los negocios en línea (Plan 3).
    
- Los usuarios de inquilinos deben tener buzones de Exchange.
    
- Tu cuenta de Skype sala sistemas v2 requieren un Skype para los negocios en línea (Plan 2) o Skype para licencia de negocios en línea (Plan 3), pero no requiere una licencia de Exchange Online.
    
### <a name="add-a-device-account"></a>Agregar una cuenta de dispositivo

1. Inicie una sesión remota de Windows PowerShell en un PC y conectarse a Exchange. Asegúrese de tener los permisos adecuados establecidos para ejecutar los cmdlets asociados. Estos son algunos ejemplos de cmdlets que puede utilizar y modificar en su entorno.
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. Después de establecer una sesión, podrá crear un nuevo buzón y habilitarlo como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente. Esto permitirá que la cuenta autenticar a los sistemas de salas de Skype v2.
    
  Si va a cambiar un buzón de recursos existente:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

  Si desea crear un nuevo buzón de recursos:
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para mejorar la experiencia de la reunión, es necesario configurar diversas propiedades de Exchange en la cuenta del dispositivo. Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. Tendrá que conectarse a Azure Active Directory para aplicar algunas de las configuraciones de la cuenta. Para conectarse a Azure AD, ejecute el siguiente cmdlet:
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. 	Si no desea que expire la contraseña, ejecute el cmdlet Set-MsolUser con la opción PasswordNeverExpires como sigue:   
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   También puede configurar un número de teléfono para la sala de la siguiente manera:
    
   ```
   Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. La cuenta del dispositivo debe tener una licencia válida de Office 365, o Exchange y Skype para empresas no funcionará. Si dispone de la licencia, debe asignar una ubicación de uso a la cuenta del dispositivo, esto determina qué SKU de las licencias están disponibles para su cuenta. Puede utilizar MsolAccountSku de Get para recuperar una lista de SKU disponibles para los clientes de Office 365, como sigue:
    
   ```
   Get-MsolAccountSku
   ```

   A continuación, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. A continuación, debe habilitar la cuenta del dispositivo con Skype para el negocio. Asegúrese de que su entorno cumpla los requisitos definidos en los [requisitos de los sistemas de salas de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).
    
   Iniciar una sesión remota de Windows PowerShell de los siguientes (asegúrese de instalar Skype para componentes de PowerShell en línea de negocio):
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   A continuación, habilitar su cuenta de Skype sala sistemas v2 para Skype para Business Server ejecutando el siguiente cmdlet:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtener la información de RegistrarPool de la nueva cuenta de usuario que el programa de instalación, como se muestra en este ejemplo:
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > No se podrían crear nuevas cuentas de usuario en la misma agrupación de registrar como cuentas de usuario existentes en el arrendatario. El comando anterior evitará errores en la configuración de cuenta debido a esta situación. 
  
Después de completar los pasos anteriores para habilitar tu cuenta de Skype sala sistemas v2 en Skype para los negocios en línea, debe asignar una licencia a dispositivos de sistemas de salas de Skype v2. Mediante el portal de administración de Office 365, asignar ambos un Skype para los negocios en línea (Plan 2) o un Skype para licencia de negocios en línea (Plan 3) para el dispositivo.
  
### <a name="assign-a-license-to-your-account"></a>Asignar una licencia a su cuenta

1. Inicio de sesión como un administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en Administrador de la aplicación.
    
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
    
3. Seleccione la cuenta de Skype sala sistemas v2 y haga clic o puntee en el icono de lápiz, que significa modificar.
    
4. Haga clic en la opción **Licencias**.
    
5. En la sección **asignación de licencias** , debe seleccionar Skype para los negocios en línea (Plan 2) o Skype para los negocios en línea (Plan 3), en función de su licencia y que haya decidido en cuanto a la necesidad de Telefonía IP empresarial. Tendrá que utilizar una licencia de Plan 3 si desea utilizar la nube PBX en sistemas de salas de Skype v2. Para la conectividad de voz, como mínimo necesitará PBX en la nube. Después deberá configurar la voz híbrida o las llamadas RTC en función del método de conectividad con RTC.
    
6. Haga clic en **Guardar** para completar la tarea.
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Ejemplo: Cuenta de sala de instalación de Exchange Online y Skype para los negocios en línea

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> De esta manera, se agregan CloudPBX y PSTNCallingDomesticAndInternational. Además, deberá usar la interfaz de administración para asignar un número de teléfono. 
  
## <a name="see-also"></a>Vea también

#### 

[Plan para la sala de Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implementar sala de Skype v2 de sistemas](room-systems-v2.md)
  
[Configurar una consola de sistemas de salas de Skype v2](console.md)
  
[Administrar espacio de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


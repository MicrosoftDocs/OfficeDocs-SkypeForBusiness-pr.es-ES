---
title: Implementar Sistemas de salas de Skype v2 con Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Office 365.
ms.openlocfilehash: 8226ee1f7ca91176380d9db8404487c076ac4135
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19502034"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>Implementar Sistemas de salas de Skype v2 con Office 365 
 
Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Office 365.
  
En este tema se describe cómo agregar una cuenta de dispositivo para sistemas de salón de Skype v2 cuando tiene una implementación en línea de Office 365.
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a>Implementar Sistemas de salas de Skype v2 con Office 365 

Antes de implementar sistemas de salón de Skype v2 con Office 365, asegúrese de que cumplen los requisitos. Para obtener más información, vea [requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Para habilitar Skype para la empresa, debe tener lo siguiente:
  
- Skype para profesionales Online (Plan 2) o superior en su plan de Office 365. El plan debe admitir la funcionalidad de conferencias.
    
- Si necesita Enterprise Voice (telefonía PSTN) con proveedores de servicios de telefonía para sistemas de salón de Skype v2 necesita Skype para profesionales en línea (planeación de 3).
    
- Los usuarios de inquilinos deben tener los buzones de Exchange.
    
- Su cuenta de Skype salón sistemas v2 requieren un Skype para profesionales Online (Plan 2) o Skype para licencia empresarial en línea (planeación de 3), pero no requiere una licencia de Exchange Online.
    
### <a name="add-a-device-account"></a>Agregar una cuenta de dispositivo

1. Iniciar una sesión remota de Windows PowerShell en un PC y conectarse a Exchange. Asegúrese de tener los permisos adecuados establecidos para ejecutar los cmdlets asociados. Estos son algunos ejemplos de cmdlets que puede utilizar y modificar en su entorno.
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. Después de establecer una sesión, podrá crear un nuevo buzón y habilitar como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente. Esto le permitirá la cuenta autenticar a los sistemas de salón de Skype v2.
    
  Si va a cambiar un buzón de recursos existente:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

  Si está creando un nuevo buzón de recursos:
    
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
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Skype para la empresa no funcionará. Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta. Puede usar Get-MsolAccountSku para recuperar una lista de SKU disponibles para el inquilino de Office 365, como se indica a continuación:
    
   ```
   Get-MsolAccountSku
   ```

   A continuación, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. A continuación, deberá habilitar la cuenta del dispositivo con Skype para la empresa. Asegúrese de que su entorno cumple los requisitos definidos en [los requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).
    
   Iniciar una sesión remota de Windows PowerShell de manera (asegúrese de instalar Skype para componentes de PowerShell en línea de negocio):
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   A continuación, habilitar su cuenta de Skype salón sistemas v2 de Skype para Business Server ejecutando el siguiente cmdlet:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtener la información de RegistrarPool de la nueva cuenta de usuario que se va al programa de instalación, tal como se muestra en este ejemplo:
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > No se pueden crear nuevas cuentas de usuario en el mismo grupo de registrador como cuentas de usuario existentes en el inquilino. El comando anterior se evitará que los errores en el programa de instalación de cuenta debido a esta situación. 
  
Una vez haya completado los pasos anteriores para habilitar su cuenta de v2 de sistemas de salón de Skype en Skype para profesionales en línea, debe asignar una licencia a dispositivos de sistemas de salón de Skype v2. Uso del portal administrativo de Office 365, asignar puede ser un Skype para profesionales Online (Plan 2) o un Skype para licencia empresarial Online (Plan 3) para el dispositivo.
  
### <a name="assign-a-license-to-your-account"></a>Asignar una licencia a su cuenta

1. Inicio de sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.
    
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
    
3. Seleccione la cuenta de v2 de sistemas de salón de Skype y, a continuación, haga clic en o puntee en el icono de lápiz, que significa que editar.
    
4. Haga clic en la opción **Licencias**.
    
5. En la sección **asignación de licencias** , es necesario seleccionar Skype para profesionales Online (Plan 2) o Skype para profesionales Online (Plan 3), en función de la concesión de licencias y que haya decidido en cuanto a la necesidad de Enterprise Voice. Debe utilizar una licencia de planeación 3 si desea usar en la nube PBX en sistemas de salón de Skype v2. Para la conectividad de voz, como mínimo necesitará PBX en la nube. Después deberá configurar la voz híbrida o las llamadas RTC en función del método de conectividad con RTC.
    
6. Haga clic en **Guardar** para completar la tarea.
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Ejemplo: Cuenta de sala del programa de instalación de Exchange Online y Skype para profesionales en línea

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

[Planeación de la sala de Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implementación de salón de Skype v2 de sistemas](room-systems-v2.md)
  
[Configurar una consola de v2 de sistemas de salón de Skype](console.md)
  
[Administración de salón de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


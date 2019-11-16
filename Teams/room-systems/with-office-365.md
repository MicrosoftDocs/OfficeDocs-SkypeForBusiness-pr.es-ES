---
title: Implementar Salas de Microsoft Teams con Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Office 365.
ms.openlocfilehash: 467a7300a2912dcaffe66a44f0f6e181d36ced1c
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675444"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Implementar Salas de Microsoft Teams con Office 365

Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Office 365, donde Microsoft Teams o Skype empresarial y Exchange están conectados.

La forma más sencilla de configurar cuentas de usuario es configurarlas con Windows PowerShell remoto. Microsoft proporciona [SkypeRoomProvisioningScript. PS1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario compatibles con salas de Microsoft Teams. Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que usará el dispositivo de salas de Microsoft Teams.

## <a name="requirements"></a>Requisitos

Antes de implementar salas de Microsoft Teams con Office 365, asegúrese de que cumple con los requisitos. Para obtener más información, consulte [requisitos de salas de Microsoft Teams](requirements.md).

Para habilitar Skype empresarial, debe disponer de lo siguiente:

- Skype empresarial online (plan 2 o un plan basado en la empresa) o superior en el plan 365 de Office. El plan debe permitir las capacidades de conferencia de acceso telefónico local.

- Si necesita capacidades de acceso telefónico desde una reunión, necesitará una licencia de audioconferencia y sistema telefónico.  Si necesita poder llamar desde una reunión, necesitará un plan de llamadas nacionales o nacionales e internacionales.

- Los usuarios de inquilinos deben tener buzones de Exchange.

- Su cuenta de salas de Microsoft Teams requiere, como mínimo, una licencia de Skype empresarial online (plan 2), pero no requiere una licencia de Exchange Online. Para obtener más información, vea [licencias de salas de Microsoft Teams](skype-room-systems-v2.md) .

Para obtener más información sobre los planes de Skype empresarial online, consulte la [Descripción del servicio de Skype empresarial online](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Agregar una cuenta de dispositivo

1. Conéctese a Exchange Online PowerShell. Para obtener instrucciones, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. En Exchange Online PowerShell, cree un nuevo buzón de sala o modifique un buzón de sala existente. De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que tendrá que agregar una cuenta al crear o modificar un buzón de sala que le permita autenticarse con sistemas de la sala de Skype v2.

   - Para crear un nuevo buzón de sala, use la siguiente sintaxis:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este ejemplo crea un nuevo buzón de sala con la siguiente configuración:

     - Nombre: proyecto-Rigel-01

     - Alias: ProjectRigel01

     - Cuenta: ProjectRigel01@contoso.onmicrosoft.com

     - Contraseña de la cuenta: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar un buzón de sala existente, use la siguiente sintaxis:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este ejemplo habilita la cuenta del buzón de sala existente que tiene el valor de alias ProjectRigel02 y establece la contraseña en 9898P@ $ $W 0rd. Observe que la cuenta se ProjectRigel02@contoso.onmicrosoft.com por el valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) y [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. En Exchange Online PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de la reunión:

   - AutomateProcessing: AutoAccept (los organizadores de reuniones reciben directamente la decisión de reserva de la sala sin intervención humana: gratis = aceptar; ocupado = rechazar).

   - AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la convocatoria de reunión).

   - DeleteComments: $false (mantener el texto en el cuerpo del mensaje de las convocatorias de reunión entrantes).

   - DeleteSubject: $false (mantener el asunto de las convocatorias de reunión entrantes).

   - RemovePrivateProperty: $false (garantiza que la marca privada que envió el organizador de la reunión en la convocatoria de reunión original permanece como se especifica).

   - AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión).

   - AdditionalResponse: "este es un salón de reunión de Skype". (El texto adicional que se agregará a la convocatoria de reunión).

   En este ejemplo se configuran estas opciones de configuración en el buzón de sala denominado Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, consulte [set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conéctese a MS online PowerShell para establecer la configuración de Active Directory `Connect-MsolService -Credential $cred` ejecutando el cmdlet de PowerShell.   Para obtener más información sobre Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible. 

5. Si no desea que la contraseña caduque, use la siguiente sintaxis:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Este ejemplo establece la contraseña de la cuenta ProjectRigel01@contoso.onmicrosoft.com para que nunca expire.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   También puede configurar un número de teléfono para la cuenta ejecutando el siguiente comando:

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. La cuenta del dispositivo debe tener una licencia válida de Office 365, o bien Exchange y Microsoft Teams o Skype empresarial no funcionarán. Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de dispositivo, lo cual determina qué SKU de licencia están disponibles para su cuenta. Puedes usar`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar una lista de las SKU disponibles para su inquilino de Office 365 de la siguiente manera:

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   A continuación, puede Agregar una licencia mediante el`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   Para obtener instrucciones detalladas, consulte [asignar licencias a cuentas de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. A continuación, debe habilitar la cuenta del dispositivo con Skype empresarial. Asegúrese de que su entorno cumple con los requisitos definidos en [los requisitos de salas de Microsoft Teams](requirements.md).

   Inicie una sesión remota de [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de la siguiente manera (Asegúrese de [instalar los componentes de PowerShell de Skype empresarial online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   A continuación, habilite la cuenta de salas de Microsoft Teams para Skype empresarial Server ejecutando el siguiente cmdlet:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtenga la información de RegistrarPool de la nueva cuenta de usuario que se está configurando, como se muestra en este ejemplo:

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Es posible que no se creen nuevas cuentas de usuario en el mismo grupo de registradores que las cuentas de usuario existentes en el inquilino. El comando anterior evitará errores en la configuración de la cuenta debido a esta situación.

Una vez completados los pasos anteriores para habilitar su cuenta de salas de Microsoft Teams en Microsoft Teams o Skype empresarial online, debe asignar una licencia a un dispositivo de salas de Microsoft Teams. Con el portal administrativo de Office 365, asigne una licencia de Skype empresarial online (plan 2) o de Skype empresarial online (Plan 3) al dispositivo.

### <a name="assign-a-license-to-your-account"></a>Asignar una licencia a su cuenta

1. Inicie sesión como administrador de inquilinos, abra el portal administrativo de Office 365 y haga clic en la aplicación de administrador.

2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.

3. Seleccione la cuenta salas de Microsoft Teams y, a continuación, haga clic o pulse en el icono de lápiz, que significa editar.

4. Haga clic en la opción **Licencias**.

5. En la sección **asignar licencias** , debe seleccionar Skype empresarial online (plan 2) o Skype empresarial online (Plan 3), en función de sus licencias y de lo que haya decidido en términos de necesidad de telefonía IP empresarial. Tendrá que usar una licencia de Plan 3 Si quiere usar PBX en la nube en salas de Microsoft Teams. Para la conectividad de voz, como mínimo necesitará PBX en la nube. Después deberá configurar la voz híbrida o las llamadas RTC en función del método de conectividad con RTC. Para obtener más información, vea [licencias de salas de Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .

6. Haga clic en **Guardar** para completar la tarea.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Ejemplo: configuración de la cuenta de sala en Exchange Online y Skype empresarial online

Comandos de Exchange Online PowerShell:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Comandos de Azure Active Directory PowerShell:

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

Comando de PowerShell de Skype empresarial:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> De esta manera, se agregan CloudPBX y PSTNCallingDomesticAndInternational. Además, tendrá que usar la interfaz de administración para asignar un número de teléfono.

## <a name="validate"></a>Valide

Para la validación, debe poder usar cualquier cliente de Skype empresarial para iniciar sesión en la cuenta que ha creado.

## <a name="see-also"></a>Vea también

[Configurar cuentas para salas de Microsoft Teams](room-systems-v2-configure-accounts.md)

[Plan para salas de Microsoft Teams](skype-room-systems-v2-0.md)

[Implementar salas de Microsoft Teams](room-systems-v2.md)

[Configurar una consola de salas de Microsoft Teams](console.md)

[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

[Licencias Rooms de Microsoft Teams](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)

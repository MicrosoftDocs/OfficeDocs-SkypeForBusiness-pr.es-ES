---
title: Implementación de salas de equipos de Microsoft con Office 365
ms.author: jambirk
author: jambirk
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos con Office 365.
ms.openlocfilehash: 462f5a6727a3c67e221b0d7ac019849ed3eb6f52
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33363035"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Implementación de salas de equipos de Microsoft con Office 365

Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos con Office 365, donde Microsoft Teams o Skype para empresas y Exchange estén en línea.

La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante Windows PowerShell remoto. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudar a convertirlas en cuentas de usuario compatibles con salones de los equipos de Microsoft. Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que se va a usar el dispositivo de salas de equipos de Microsoft.

## <a name="requirements"></a>Requisitos

Antes de implementar Microsoft salones de los equipos con Office 365, asegúrese de que cumplen los requisitos. Para obtener más información, vea [requisitos de salas de equipos de Microsoft](requirements.md).

Para habilitar Skype para la empresa, debe tener lo siguiente:

- Skype para profesionales Online (Plan 2 o un plan de empresa) o superior en su plan de Office 365. El plan debe permitir que las capacidades de conferencia de acceso telefónico.

- Si necesita capacidades de marcado de una reunión, necesitará una conferencia de audio y la licencia del sistema telefónico.  Si necesita las capacidades de acceso telefónico de salida de una reunión, necesitará un nacionales o nacional e internacional de llamada Plan.

- Los usuarios de inquilinos deben tener los buzones de Exchange.

- Su cuenta de salas de equipos de Microsoft requieren como mínimo un Skype para licencia empresarial Online (Plan 2), pero no requiere una licencia de Exchange Online. Para obtener información detallada, vea [Salones de licencias de los equipos de Microsoft](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) .

Para obtener información detallada en Skype para planes de negocios de en línea, vea la [Skype para la descripción de servicio en línea de negocio](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Agregar una cuenta de dispositivo

1. Conectarse a Exchange Online PowerShell. Para obtener instrucciones, vea [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. En Exchange Online PowerShell, cree un nuevo buzón de sala o modifique un buzón de sala existente. De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que necesitará para agregar una cuenta al crear o modificar un buzón de sala que le permite autenticar con sistemas de salas de Skype v2.

   - Para crear un nuevo buzón de sala, use la siguiente sintaxis:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:

     - Nombre: Proyecto-Rigel-01

     - Alias: ProjectRigel01

     - Cuenta: ProjectRigel01@contoso.onmicrosoft.com

     - Contraseña de la cuenta: P@$$W0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar un buzón de sala existente, use la siguiente sintaxis:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     En este ejemplo se habilita la cuenta para el buzón de sala existente que tiene el valor de alias ProjectRigel02 y se establece la contraseña en 9898P@$$W0rd. Tenga en cuenta que la cuenta será ProjectRigel02@contoso.onmicrosoft.com debido al valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para obtener información de parámetro y detallada sobre la sintaxis, vea [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) y [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. En Exchange Online PowerShell, configure las opciones siguientes en el buzón de sala para mejorar la experiencia de reunión:

   - AutomateProcessing: AutoAccept (los organizadores de reuniones reciben la decisión de reserva de sala directamente sin intervención humana: libre = acepte; ocupado = rechazar.)

   - AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la convocatoria de reunión).

   - DeleteComments: $false (mantener el texto del cuerpo del mensaje de convocatorias de reunión entrantes).

   - DeleteSubject: $false (conservar el asunto de convocatorias de reunión entrantes).

   - RemovePrivateProperty: $false (garantiza la marca privada que se envió el organizador de la reunión original permanece tal como se especifica de solicitudes).

   - AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión).

   - AdditionalResponse: "ésta es una sala de reuniones de Skype!" (El texto adicional para agregar a la convocatoria de reunión).

   En este ejemplo se configura estas opciones de configuración en el buzón de sala denominado Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obtener información de parámetro y detallada sobre la sintaxis, vea [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conectarse a MS Online PowerShell para realizar la configuración de Active Directory mediante la ejecución de la `Connect-MsolService -Credential $cred` cmdlet de powershell.   Para obtener información detallada acerca de Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. Si no desea que la contraseña a punto de caducar, use la siguiente sintaxis:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   En este ejemplo se establece la contraseña de la cuenta ProjectRigel01@contoso.onmicrosoft.com para que no expire nunca.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   También puede establecer un número de teléfono de la cuenta, ejecute el comando siguiente:

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Microsoft Teams o Skype para la empresa no funcionará. Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta. Puede usar`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar una lista de SKU disponibles para el inquilino de Office 365 de la siguiente manera:

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   A continuación, puede agregar una licencia mediante la`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).

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

   Para obtener instrucciones detalladas, consulte [asignar licencias a cuentas de usuario con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. A continuación, deberá habilitar la cuenta del dispositivo con Skype para la empresa. Asegúrese de que su entorno cumple los requisitos definidos en [los requisitos de salas de equipos de Microsoft](requirements.md).

   Iniciar una [sesión de Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de remota como se muestra a continuación (asegúrese de [instalar Skype para componentes de PowerShell en línea de negocio](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   A continuación, habilitar la cuenta de salones de los equipos de Microsoft para Skype para Business Server ejecutando el siguiente cmdlet:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtener la información de RegistrarPool de la nueva cuenta de usuario que se va al programa de instalación, tal como se muestra en este ejemplo:

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > No se pueden crear nuevas cuentas de usuario en el mismo grupo de registrador como cuentas de usuario existentes en el inquilino. El comando anterior se evitará que los errores en el programa de instalación de cuenta debido a esta situación.

Una vez haya completado los pasos anteriores para habilitar la cuenta de salas de equipos de Microsoft en Microsoft Teams o Skype para profesionales en línea, debe asignar una licencia a dispositivo de salas de equipos de Microsoft. Uso del portal administrativo de Office 365, asignar puede ser un Skype para profesionales Online (Plan 2) o un Skype para licencia empresarial Online (Plan 3) para el dispositivo.

### <a name="assign-a-license-to-your-account"></a>Asignar una licencia a su cuenta

1. Inicio de sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.

2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.

3. Seleccione la cuenta de salas de equipos de Microsoft y, a continuación, haga clic en o puntee en el icono de lápiz, que significa que editar.

4. Haga clic en la opción **Licencias**.

5. En la sección **asignación de licencias** , es necesario seleccionar Skype para profesionales Online (Plan 2) o Skype para profesionales Online (Plan 3), en función de la concesión de licencias y que haya decidido en cuanto a la necesidad de Enterprise Voice. Debe utilizar una licencia de planeación 3 si desea usar en la nube PBX en salas de equipos de Microsoft. Para la conectividad de voz, como mínimo necesitará PBX en la nube. Después deberá configurar la voz híbrida o las llamadas RTC en función del método de conectividad con RTC. Para obtener más información, vea [las licencias de salas de equipos de Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .

6. Haga clic en **Guardar** para completar la tarea.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Ejemplo: Cuenta de sala del programa de instalación de Exchange Online y Skype para profesionales en línea

Comandos de PowerShell en Exchange Online:

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

Skype para comandos de PowerShell de negocio:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> De esta manera, se agregan CloudPBX y PSTNCallingDomesticAndInternational. Además, debe usar la interfaz de administración para asignar a un número de teléfono.

## <a name="validate"></a>Validar

Para la validación, debe usar cualquier Skype para clientes empresariales para iniciar sesión en la cuenta que creó.

## <a name="see-also"></a>Vea también

[Configurar las cuentas para salas de equipos de Microsoft](room-systems-v2-configure-accounts.md)

[Plan para salas de equipos de Microsoft](skype-room-systems-v2-0.md)

[Implementación de salas de equipos de Microsoft](room-systems-v2.md)

[Configurar una consola de salas de equipos de Microsoft](console.md)

[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

[Licencias de salas de equipos de Microsoft](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)

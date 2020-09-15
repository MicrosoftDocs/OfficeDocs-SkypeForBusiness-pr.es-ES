---
title: Implementar salas de Microsoft Teams con Microsoft 365 u Office 365
ms.author: v-lanac
author: lanachin
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Microsoft 365 u Office 365, donde Teams o Skype empresarial y Exchange están conectados.
ms.openlocfilehash: ee1f4da5cbcb65ab58c032ac651e0b563167a35b
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814799"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Implementar salas de Microsoft Teams con Microsoft 365 u Office 365

Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Microsoft 365 u Office 365, donde Microsoft Teams o Skype empresarial y Exchange están conectados.

La forma más sencilla de configurar cuentas de usuario es configurarlas con Windows PowerShell remoto. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario compatibles con salas de Microsoft Teams. Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que usará el dispositivo de salas de Microsoft Teams.

## <a name="requirements"></a>Requisitos

Antes de implementar salas de Microsoft Teams con Microsoft 365 u Office 365, asegúrese de que cumple con los requisitos. Para obtener más información, consulte [requisitos de salas de Microsoft Teams](requirements.md).

Para habilitar Skype empresarial, debe disponer de lo siguiente:

- Skype empresarial online (plan 2 o un plan basado en la empresa) o superior en su plan de 365 u Office 365 de Microsoft. El plan debe permitir las capacidades de conferencia de acceso telefónico local.

- Si necesita capacidades de acceso telefónico desde una reunión, necesitará una licencia de audioconferencia y sistema telefónico.  Si necesita capacidades de llamada saliente de una reunión, necesitará una licencia de audioconferencia.

- Los usuarios de inquilinos deben tener buzones de Exchange.

- Su cuenta de salas de Microsoft Teams requiere, como mínimo, una licencia de Skype empresarial online (plan 2), pero no requiere una licencia de Exchange Online. Para obtener más información, vea [licencias de salas de Microsoft Teams](rooms-licensing.md) .

Para obtener más información sobre los planes de Skype empresarial online, consulte la [Descripción del servicio de Skype empresarial online](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Agregar una cuenta de dispositivo

1. Conéctese a Exchange Online PowerShell. Para obtener instrucciones, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. En Exchange Online PowerShell, cree un nuevo buzón de sala o modifique un buzón de sala existente. De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que tendrá que agregar una cuenta al crear o modificar un buzón de sala que le permita autenticarse con sistemas de la sala de Skype v2.

   - Para crear un nuevo buzón de sala, use la siguiente sintaxis:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este ejemplo crea un nuevo buzón de sala con la siguiente configuración:

     - Nombre: Rigel-01

     - Alias: Rigel1

     - Cuenta: Rigel1@contoso.onmicrosoft.com

     - Contraseña de la cuenta: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar un buzón de sala existente, use la siguiente sintaxis:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este ejemplo habilita la cuenta del buzón de sala existente que tiene el valor de alias Rigel2 y establece la contraseña en 9898P@ $ $W 0rd. Observe que la cuenta se Rigel2@contoso.onmicrosoft.com por el valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
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

   En este ejemplo se configuran estas opciones de configuración en el buzón de sala denominado Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, consulte [set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conéctese a MS online PowerShell para establecer la configuración de Active Directory ejecutando el `Connect-MsolService -Credential $cred` cmdlet de PowerShell.   Para obtener más información sobre Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible. 

5. Si no desea que la contraseña caduque, use la siguiente sintaxis:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```
   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Este ejemplo establece la contraseña de la cuenta Rigel1@contoso.onmicrosoft.com para que nunca expire.

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName Rigel1@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   También puede configurar un número de teléfono para la cuenta ejecutando el siguiente comando:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. La cuenta del dispositivo debe tener una licencia válida de Microsoft 365 o de Office 365, o bien Exchange y Microsoft Teams, o bien Skype empresarial no funcionará. Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de dispositivo, lo cual determina qué SKU de licencia están disponibles para su cuenta. Puedes usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar una lista de las SKU disponibles para su organización de Microsoft 365 u Office 365 de la siguiente manera:

   ```Powershell
   Get-MsolAccountSku
   ```
   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   A continuación, puede Agregar una licencia mediante el `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ``` 
   <!-- 
   ```Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   Para obtener instrucciones detalladas, consulte [asignar licencias a cuentas de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. A continuación, debe habilitar la cuenta del dispositivo con Skype empresarial. Asegúrese de que su entorno cumple con los requisitos definidos en [los requisitos de salas de Microsoft Teams](requirements.md).

   Inicie una sesión remota de [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de la siguiente manera (Asegúrese de [instalar los componentes de PowerShell de Skype empresarial online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):
   
> [!NOTE]
> En este momento, el conector de Skype empresarial online forma parte del módulo de PowerShell más reciente de Teams.
>
> Si está usando la [versión pública de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)más reciente de PowerShell, no necesita instalar el conector de Skype empresarial online.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   A continuación, habilite la cuenta de salas de Microsoft Teams para Skype empresarial Server ejecutando el siguiente cmdlet:

   ``` Powershell
   $rm="Rigel1@contoso.onmicrosoft.com"
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtenga la información de RegistrarPool de la nueva cuenta de usuario que se está configurando, como se muestra en este ejemplo:

    ``` Powershell
    $rm="Rigel1@contoso.onmicrosoft.com"
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > New user accounts might not be created on the same registrar pool as existing user accounts in the tenant. The command above will prevent errors in account setup due to this situation.

### <a name="assign-a-license-to-your-account"></a>Asignar una licencia a su cuenta

1. Inicie sesión como administrador de inquilinos, abra el centro de administración de Microsoft 365 y haga clic en la aplicación de administrador.

2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.

3. Seleccione la cuenta salas de Microsoft Teams y, a continuación, haga clic o pulse en el icono de lápiz, que significa editar.

4. Haga clic en la opción **Licencias**.

5. En la sección **asignar licencias** , debe seleccionar Skype empresarial online (plan 2) o Skype empresarial online (Plan 3), en función de sus licencias y de lo que haya decidido en términos de necesidad de telefonía IP empresarial. Tendrá que usar una licencia de Plan 3 Si quiere usar PBX en la nube en salas de Microsoft Teams. Para la conectividad de voz, como mínimo necesitará PBX en la nube. Después deberá configurar la voz híbrida o las llamadas RTC en función del método de conectividad con RTC. Para obtener más información, vea [licencias de salas de Microsoft Teams](rooms-licensing.md) .

6. Haga clic en **Guardar** para completar la tarea.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Ejemplo: configuración de la cuenta de sala en Exchange Online y Skype empresarial online

Comandos de Exchange Online PowerShell:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Comandos de Azure Active Directory PowerShell:

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
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

[Configurar cuentas para salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Implementar Salas de Microsoft Teams](rooms-deploy.md)

[Configurar una consola de sala de Microsoft Teams](console.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Licencias Rooms de Microsoft Teams](rooms-licensing.md)

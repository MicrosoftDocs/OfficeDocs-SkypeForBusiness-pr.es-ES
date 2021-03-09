---
title: Implementar salas de Microsoft Teams con Microsoft 365 u Office 365
ms.author: v-cichur
author: cichur
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
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Microsoft 365 u Office 365, donde Teams o Skype Empresarial y Exchange están en línea.
ms.openlocfilehash: 7a25fb17e4b9fce4a51c6e2be5828ecafff59894
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569126"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Implementar salas de Microsoft Teams con Microsoft 365 u Office 365

Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Microsoft 365 u Office 365, donde Microsoft Teams o Skype Empresarial y Exchange están en línea.

La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante la configuración Windows PowerShell. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario compatibles de Salas de Microsoft Teams. Si lo prefiere, puede seguir los pasos que se indican a continuación para configurar las cuentas que usará el dispositivo Salas de Microsoft Teams.

## <a name="requirements"></a>Requisitos

Antes de implementar Microsoft Teams Rooms con Microsoft 365 u Office 365, asegúrese de que ha cumplido los requisitos. Para obtener más información, vea [Requisitos de salas de Microsoft Teams.](requirements.md)

Para habilitar Skype Empresarial, debe tener lo siguiente:

- Skype Empresarial Online (Plan 2 o un plan basado en la empresa) o superior en su plan de Microsoft 365 u Office 365. El plan debe permitir las capacidades de conferencias de acceso telefónico local.

- Si necesita funcionalidades de acceso telefónico local de una reunión, necesitará una licencia de audioconferencia y sistema telefónico.  Si necesita funcionalidades de acceso telefónico local de una reunión, necesitará una licencia de audioconferencia.

- Los usuarios inquilinos deben tener buzones de Exchange.

- Su cuenta de Salas de Microsoft Teams requiere como mínimo una licencia de Skype Empresarial Online (Plan 2), pero no requiere una licencia de Exchange Online. Vea [Licencias de salas de Microsoft Teams](rooms-licensing.md) para obtener más información.

Para obtener más información sobre los planes de Skype Empresarial Online, consulte la Descripción del servicio en línea [de Skype Empresarial.](https://technet.microsoft.com/library/jj822172.aspx)

### <a name="add-a-device-account"></a>Agregar una cuenta de dispositivo

1. Conéctese a Exchange Online PowerShell. Para obtener instrucciones, vea [Conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. En Exchange Online PowerShell, cree un nuevo buzón de sala o modifique un buzón de sala existente. De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que tendrá que agregar una cuenta al crear o modificar un buzón de sala que le permita autenticarse con Sistemas de salón de Skype v2.

   - Para crear un buzón de sala nuevo, use la sintaxis siguiente:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:

     - Nombre: Rigel-01

     - Alias: Rigel1

     - Cuenta: Rigel1@contoso.onmicrosoft.com

     - Contraseña de la cuenta: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar un buzón de sala existente, use la sintaxis siguiente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     En este ejemplo, se habilita la cuenta para el buzón de sala existente que tiene el valor de alias Rigel2 y se establece la contraseña en 9898P@$$W 0rd. Tenga en cuenta que la cuenta se Rigel2@contoso.onmicrosoft.com debido al valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Nuevo buzón](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) y Conjunto [de buzones.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

3. En Exchange Online PowerShell, configure las siguientes opciones de configuración en el buzón de sala para mejorar la experiencia de la reunión:

   - AutomateProcessing: AutoAccept (Los organizadores de la reunión reciben la decisión de reserva de sala directamente sin intervención humana: gratis = aceptar; ocupado = rechazar).

   - AddOrganizerToSubject: $false (El organizador de la reunión no se agrega al asunto de la solicitud de reunión).

   - DeleteComments: $false (Conservar cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).

   - DeleteSubject: $false (Mantener el asunto de las solicitudes de reunión entrantes).

   - RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).

   - AddAdditionalResponse: $true (El texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).

   - AdditionalResponse: "Esta es una sala de reuniones de Skype" (El texto adicional que se agregará a la solicitud de reunión).

   En este ejemplo se configuran estas opciones en el buzón de sala denominado Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conéctese a MS Online PowerShell para realizar la configuración de Active Directory ejecutando el `Connect-MsolService -Credential $cred` cmdlet de PowerShell. Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.

5. Si no desea que la contraseña expire, use la sintaxis siguiente:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   En este ejemplo se establece la contraseña de la cuenta Rigel1@contoso.onmicrosoft.com que nunca expire.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   También puede establecer un número de teléfono para la cuenta ejecutando el siguiente comando:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> Si la contraseña no está establecida en Nunca expirar, la cuenta ya no iniciará sesión en el dispositivo cuando la cuenta llegue al período de expiración. La contraseña tendrá que cambiarse para la cuenta y también actualizarse localmente en el dispositivo MTR.

6. La cuenta del dispositivo debe tener una licencia válida de Microsoft 365 u Office 365, o Exchange y Microsoft Teams o Skype Empresarial no funcionarán. Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de dispositivo, lo que determina qué SKU de licencia están disponibles para su cuenta. Puede usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar una lista de SKU disponibles para su organización de Microsoft 365 u Office 365 de la siguiente manera:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   A continuación, puede agregar una licencia con el `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. En este ejemplo se agrega la licencia de sala de reuniones a la cuenta:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Para obtener instrucciones detalladas, vea Asignar licencias a cuentas de usuario con PowerShell de [Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   También puede agregar funcionalidades de Sistema telefónico a esta cuenta, pero primero tiene que configurarla. Vea [¿Qué es el sistema telefónico?](../what-is-phone-system-in-office-365.md) para obtener más información. En este ejemplo se agrega el plan de llamadas RTC nacionales e internacionales:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. A continuación, debe habilitar la cuenta del dispositivo con Skype Empresarial. Asegúrese de que su entorno cumple los requisitos definidos en [los requisitos de salas de Microsoft Teams.](requirements.md)

   Inicie una sesión [Windows PowerShell sesión](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) remota de la siguiente manera (asegúrese de instalar componentes de PowerShell de Skype [Empresarial Online):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

> [!NOTE]
> Skype Empresarial Online Connector forma parte actualmente del último módulo de PowerShell de Teams.
>
> Si usa la última versión pública de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   Obtenga la información de RegistrarPool de la nueva cuenta de usuario que se está configurando, como se muestra en este ejemplo:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   A continuación, habilite su cuenta de Salas de Microsoft Teams para Skype Empresarial Server ejecutando el siguiente cmdlet:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Es posible que las nuevas cuentas de usuario no se crean en el mismo grupo de registradores que las cuentas de usuario existentes en el inquilino. El comando anterior evitará errores en la configuración de la cuenta debido a esta situación.

## <a name="validate"></a>Validar

Para la validación, debería poder usar cualquier cliente de Skype Empresarial para iniciar sesión en la cuenta que creó.

## <a name="see-also"></a>Consulte también

[Configurar cuentas para salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Implementar Salas de Microsoft Teams](rooms-deploy.md)

[Configurar una consola de sala de Microsoft Teams](console.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Licencias de salas de Microsoft Teams](rooms-licensing.md)

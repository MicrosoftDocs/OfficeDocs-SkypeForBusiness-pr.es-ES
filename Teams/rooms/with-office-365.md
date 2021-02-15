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
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Microsoft 365 u Office 365, donde Teams o Skype Empresarial y Exchange están ambos en línea.
ms.openlocfilehash: 4ec54763379e4a13a69eb3e08019924708873faf
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196214"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Implementar salas de Microsoft Teams con Microsoft 365 u Office 365

Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Microsoft 365 u Office 365, donde Microsoft Teams o Skype Empresarial y Exchange están ambos en línea.

La manera más sencilla de configurar las cuentas de usuario es configurarlas mediante cuentas de Windows PowerShell. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario, o validar las cuentas de recursos existentes que tiene con el fin de ayudarle a convertirlas en cuentas de usuario compatibles de Salas de Microsoft Teams. Si lo prefiere, puede seguir los pasos que se indican a continuación para configurar las cuentas que usará el dispositivo de Microsoft Teams Rooms.

## <a name="requirements"></a>Requisitos

Antes de implementar Salas de Microsoft Teams con Microsoft 365 u Office 365, asegúrese de que cumple los requisitos. Para obtener más información, consulte los [requisitos de salas de Microsoft Teams.](requirements.md)

Para habilitar Skype Empresarial, debe tener lo siguiente:

- Skype Empresarial Online (plan 2 o plan basado en Enterprise) o superior en su plan de Microsoft 365 u Office 365. El plan debe permitir las capacidades de conferencias de acceso telefónico local.

- Si necesita funcionalidades de acceso telefónico local de una reunión, necesitará una licencia de Audioconferencia y sistema telefónico.  Si necesita funcionalidades de llamada a una reunión, necesitará una licencia de Audioconferencia.

- Los usuarios inquilinos deben tener buzones de Exchange.

- Su cuenta de Microsoft Teams Rooms requiere como mínimo una licencia de Skype Empresarial Online (Plan 2), pero no requiere una licencia de Exchange Online. Consulte [las licencias de Salas de Microsoft Teams](rooms-licensing.md) para obtener más información.

Para obtener más información sobre los planes de Skype Empresarial Online, consulte la [Descripción del servicio de Skype Empresarial Online.](https://technet.microsoft.com/library/jj822172.aspx)

### <a name="add-a-device-account"></a>Agregar una cuenta de dispositivo

1. Conéctese a Exchange Online PowerShell. Para obtener instrucciones, [consulte Conectarse a Exchange Online PowerShell.](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. En Exchange Online PowerShell, cree un nuevo buzón de sala o modifique un buzón de sala existente. De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que tendrá que agregar una cuenta al crear o modificar un buzón de sala que permita la autenticación con Sistemas de sala de Skype v2.

   - Para crear un nuevo buzón de sala, use la siguiente sintaxis:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     En este ejemplo se crea un buzón de sala con los valores siguientes:

     - Nombre: Rigel-01

     - Alias: Rigel1

     - Cuenta: Rigel1@contoso.onmicrosoft.com

     - Contraseña de la cuenta: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar un buzón de sala existente, use la siguiente sintaxis:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     En este ejemplo se habilita la cuenta para el buzón de sala existente que tiene el valor alias Rigel2 y se establece la contraseña en 9898P@$$W 0rd. Tenga en cuenta que la cuenta se Rigel2@contoso.onmicrosoft.com debido al valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para obtener sintaxis detallada e información de parámetros, vea [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) y [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

3. En Exchange Online PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de reunión:

   - AutomateProcessing: AutoAccept (los organizadores de reuniones reciben la decisión de reserva de la sala directamente sin intervención humana: free = accept; busy = decline).

   - AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la solicitud de reunión).

   - DeleteComments: $false (mantenga cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).

   - DeleteSubject: $false (mantener el asunto de las solicitudes de reunión entrantes).

   - RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).

   - AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).

   - Respuesta adicional: "¡Esta es una sala de reuniones de Skype!". (El texto adicional que se agregará a la solicitud de reunión).

   Este ejemplo configura estas opciones en el buzón de sala denominado Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obtener sintaxis detallada e información sobre los parámetros, [vea Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Conéctese a MS Online PowerShell para establecer la configuración de Active Directory ejecutando el `Connect-MsolService -Credential $cred` cmdlet de PowerShell. Para obtener más información sobre Active Directory, [consulte Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

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
> Si la contraseña no se establece en Nunca expirar, la cuenta ya no se inicia sesión en el dispositivo cuando la cuenta llegue al período de expiración. A continuación, deberá cambiar la contraseña de la cuenta y también actualizarse localmente en el dispositivo MTR.

6. La cuenta del dispositivo debe tener una licencia válida de Microsoft 365 u Office 365, o Exchange y Microsoft Teams o Skype Empresarial no funcionarán. Si tienes la licencia, tienes que asignar una ubicación de uso a tu cuenta del dispositivo( esto determina qué SKU de licencia están disponibles para tu cuenta). Puede usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar una lista de SKU disponibles para su organización de Microsoft 365 u Office 365 de la siguiente manera:

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

   Para obtener instrucciones [detalladas, consulte Asignar licencias a cuentas de usuario con PowerShell de Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   También puede agregar funcionalidades de Sistema telefónico a esta cuenta, pero primero tiene que configurarla. Consulte [¿Qué es el sistema telefónico?](../what-is-phone-system-in-office-365.md) para obtener más información. En este ejemplo se agrega el plan de llamadas RTC nacionales e internacionales:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. A continuación, debe habilitar la cuenta del dispositivo con Skype Empresarial. Asegúrese de que su entorno cumple los requisitos definidos en los [requisitos de Salas de Microsoft Teams.](requirements.md)

   Inicie una sesión [de Windows PowerShell remota](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de la siguiente manera (asegúrese de instalar los componentes de [PowerShell de Skype Empresarial Online):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

> [!NOTE]
> Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.
>
> Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Obtenga la información de RegistrarPool de la nueva cuenta de usuario que se está configurando, como se muestra en este ejemplo:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   A continuación, habilite la cuenta de Salas de Microsoft Teams para Skype Empresarial Server ejecutando el siguiente cmdlet:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Es posible que no se puedan crear cuentas de usuario nuevas en el mismo grupo de registradores que las cuentas de usuario existentes en el espacio empresarial. El comando anterior evitará errores en la configuración de la cuenta debido a esta situación.

## <a name="validate"></a>Validar

Para la validación, debería poder usar cualquier cliente de Skype Empresarial para iniciar sesión en la cuenta que creó.

## <a name="see-also"></a>Consulte también

[Configurar cuentas de Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Implementar Salas de Microsoft Teams](rooms-deploy.md)

[Configurar una consola de sala de Microsoft Teams](console.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Licencias de salas de Microsoft Teams](rooms-licensing.md)

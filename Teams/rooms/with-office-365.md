---
title: Implementar Salas de Microsoft Teams con Microsoft 365 o Office 365
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Microsoft 365 o Office 365, donde Teams o Skype Empresarial y Exchange están en línea.
ms.openlocfilehash: e3f72c86f88ab449b48b80d6bef06d0858c44b53
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355649"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Implementar Salas de Microsoft Teams con Microsoft 365 o Office 365

Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Microsoft 365 o Office 365, donde Microsoft Teams y Exchange están en línea.

## <a name="requirements"></a>Requirements

Antes de implementar Salas de Microsoft Teams con Microsoft 365 o Office 365, asegúrese de que ha cumplido los requisitos. Para obtener más información, [vea Salas de Microsoft Teams requisitos.](requirements.md)

### <a name="add-a-resource-account"></a>Agregar una cuenta de recursos

1. Conectar para Exchange Online PowerShell. Para obtener instrucciones, [vea Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. En Exchange Online PowerShell, cree un buzón de sala o modifique un buzón de sala existente. De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que tendrá que agregar una cuenta al crear o modificar un buzón de sala que le permita autenticarse con Microsoft Teams.

   - Para crear un buzón de sala nuevo, use la sintaxis siguiente:

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:

     - Cuenta: ConferenceRoom01@contoso.com
  
     - Nombre: ConferenceRoom01

     - Alias: ConferenceRoom01

     - Contraseña de la cuenta: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar un buzón de sala existente, use la sintaxis siguiente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     En este ejemplo, se habilita la cuenta del buzón de sala existente que tiene el valor de alias ConferenceRoom02 y se establece la contraseña en 9898P@$$W 0rd. Tenga en cuenta que la cuenta se ConferenceRoom02@contoso.com debido al valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Nuevo buzón](/powershell/module/exchange/mailboxes/new-mailbox) y Conjunto [de buzones.](/powershell/module/exchange/mailboxes/set-mailbox)

3. En Exchange Online PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de la reunión:

   - AutomateProcessing: AutoAccept (los organizadores de la reunión reciben la decisión de reserva de sala directamente sin intervención humana).

   - AddOrganizerToSubject: $false (El organizador de la reunión no se agrega al asunto de la solicitud de reunión).

   - DeleteComments: $false (Conservar cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).

   - DeleteSubject: $false (Mantener el asunto de las solicitudes de reunión entrantes).

   - RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).

   - AddAdditionalResponse: $true (El texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).

   - AdditionalResponse: "Esta es una sala Microsoft Teams reunión" (El texto adicional que se agregará a la solicitud de reunión).

   En este ejemplo se configuran estas opciones en el buzón de sala denominado ConferenceRoom01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conectar a MS Online PowerShell para realizar la configuración de Active Directory ejecutando el `Connect-MsolService` Cmdlet de PowerShell. Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.

5. Establezca la contraseña para que nunca expire con la sintaxis siguiente:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   En este ejemplo se establece la contraseña de la cuenta ConferenceRoom01@contoso.onmicrosoft.com que nunca expire.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   También puede establecer un número de teléfono para la cuenta ejecutando el siguiente comando:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > Si la contraseña no está establecida en Nunca expirar, la cuenta ya no iniciará sesión en el dispositivo cuando la cuenta llegue al período de expiración. La contraseña tendrá que cambiarse para la cuenta y también actualizarse localmente en Salas de Teams. Los usuarios no pueden unirse a reuniones Salas de Teams mientras la contraseña ha expirado.

6. La cuenta de recursos debe tener una licencia Microsoft 365 o Office 365, o Exchange y Microsoft Teams no funcionarán. Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de recursos, lo que determina qué SKU de licencia están disponibles para su cuenta. Puede usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar una lista de SKU disponibles para su Microsoft 365 o Office 365 organización de la siguiente manera:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   A continuación, puede agregar una licencia con el `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. En este ejemplo se agrega Sala de reuniones licencia a la cuenta:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Para obtener instrucciones [detalladas,](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)vea Asignar licencias a cuentas de usuario con Office 365 PowerShell.

   También puede agregar Sistema telefónico a esta cuenta, pero primero tiene que configurarla. Vea [¿Qué Sistema telefónico?](../what-is-phone-system-in-office-365.md) para obtener más información. En este ejemplo se agrega el plan de llamadas RTC nacionales e internacionales:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName ConferenceRoom01@contoso.com -AddLicenses "Contoso:MCOPSTN2"
   ```


## <a name="validate"></a>Validar

Para la validación, debería poder usar cualquier Microsoft Teams cliente para iniciar sesión en la cuenta que creó.

## <a name="see-also"></a>Vea también

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Implementar Salas de Microsoft Teams](rooms-deploy.md)

[Configurar una consola de sala de Microsoft Teams](console.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Salas de Microsoft Teams licencias](rooms-licensing.md)

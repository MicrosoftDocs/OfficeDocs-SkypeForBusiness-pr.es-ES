---
title: Crear cuentas de recursos de Microsoft Teams para las barras de colaboración de Microsoft Teams mediante PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información sobre cómo implementar barras de colaboración para Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268071"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Crear una cuenta de recursos de Microsoft 365 con PowerShell

Lea este tema para obtener información sobre cómo crear cuentas de recursos para las barras de colaboración de Microsoft Teams con PowerShell.

La forma más sencilla de crear una cuenta de recursos es mediante el centro de administración de Microsoft 365. [Consulte este artículo para obtener información sobre cómo hacerlo](resource-account-ui.md).

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Requisitos

Antes de implementar salas de Microsoft Teams con Office 365, asegúrese de que cumple con los requisitos. Para obtener más información, consulte [implementar barras de colaboración para Microsoft Teams](collab-bar-deploy.md).

- Si necesita capacidades de RTC para la barra de colaboración, necesitará una licencia de sistema telefónico.

- Las cuentas de recursos deben tener buzones de Exchange. Puesto que se trata de cuentas de recursos, no se necesita una licencia de Exchange. Recomendamos el uso de la licencia de salas de reuniones para cuentas de recursos.


### <a name="add-a-resource-account"></a>Agregar una cuenta de recursos

1. Conéctese a Exchange Online PowerShell. Para obtener instrucciones, consulte [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).

2. En Exchange Online PowerShell, cree un nuevo buzón de sala o modifique un buzón de sala existente.

   - Para crear un nuevo buzón de sala, use la siguiente sintaxis:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este ejemplo crea un nuevo buzón de sala con la siguiente configuración:

     - Nombre: Huddle-Room-01

     - Alias: HuddleRoom01

     - Cuenta: huddleroom01@contoso.onmicrosoft.com

     - Contraseña de la cuenta: P@ $ $W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Para modificar un buzón de sala existente, use la siguiente sintaxis:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este ejemplo habilita la cuenta del buzón de sala existente que tiene el valor de alias HuddleRoom02 y establece la contraseña en 808P@ $ $W 0rd. Observe que la cuenta se HuddleRoom02@contoso.onmicrosoft.com por el valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) y [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. En Exchange Online PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de la reunión:

   - AutomateProcessing: AutoAccept (los organizadores de reuniones reciben directamente la decisión de reserva de la sala sin intervención humana: gratis = aceptar; ocupado = rechazar).

   - AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la convocatoria de reunión).

   - DeleteComments: $false (mantener el texto en el cuerpo del mensaje de las convocatorias de reunión entrantes).

   - DeleteSubject: $false (mantener el asunto de las convocatorias de reunión entrantes).

   - RemovePrivateProperty: $false (garantiza que la marca privada que envió el organizador de la reunión en la convocatoria de reunión original permanece como se especifica).

   - AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión).

   - AdditionalResponse: "este salón tiene una barra de colaboración para Microsoft Teams." (El texto adicional que se agregará a la convocatoria de reunión).

   En este ejemplo se configuran estas opciones de configuración en el buzón de sala denominado Huddle-Room-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, consulte [set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conéctese a MS online PowerShell para establecer la configuración de Active Directory ejecutando el `Connect-MsolService -Credential $cred` cmdlet de PowerShell.   Para obtener más información sobre Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible. 

5. Configure la contraseña de huddleroom01@contoso.onmicrosoft.com para que no expire con la siguiente sintaxis:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. La cuenta de recursos debe tener una licencia válida de Office 365, preferiblemente la SKU de la sala de reuniones. También necesita asignar una ubicación de uso a su cuenta de dispositivo, lo cual determina qué SKU de licencia están disponibles para su cuenta. Puede usar `Get-MsolAccountSku` para recuperar una lista de las SKU disponibles para su inquilino de Office 365.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Puede asignar la licencia mediante Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Para obtener instrucciones detalladas, consulte [asignar licencias a cuentas de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).




[Configurar cuentas para las barras de colaboración de Microsoft Teams con PowerShell](resource-account-ps.md)

[Implementar barras de colaboración para Microsoft Teams](collab-bar-deploy.md)

[Barras de colaboración para licencias de Microsoft Teams](../rooms/rooms-licensing.md)



---
title: Crear Microsoft Teams de recursos para barras de colaboración para Microsoft Teams usar PowerShell
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
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115608"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Crear una Microsoft 365 de recursos con PowerShell

Lea este tema para obtener información sobre cómo crear cuentas de recursos para barras de colaboración Microsoft Teams usar PowerShell.

La forma más sencilla de crear una cuenta de recursos es mediante el centro Microsoft 365 administración. [Vea este artículo sobre cómo hacerlo](resource-account-ui.md).

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Requirements

Antes de implementar Salas de Microsoft Teams con Office 365, asegúrese de que ha cumplido los requisitos. Para obtener más información, vea [Implementar barras de colaboración para Microsoft Teams](collab-bar-deploy.md).

- Si necesita funcionalidades RTC para la barra de colaboración, necesitará Sistema telefónico licencia.

- Las cuentas de recursos deben tener Exchange buzones de correo. Como se trata de cuentas de recursos, no Exchange licencia. Se recomienda el uso de la licencia salas de reuniones para cuentas de recursos.


### <a name="add-a-resource-account"></a>Agregar una cuenta de recursos

1. Conectar para Exchange Online PowerShell. Para obtener instrucciones, [vea Conectar para Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).

2. En Exchange Online PowerShell, cree un buzón de sala o modifique un buzón de sala existente.

   - Para crear un buzón de sala nuevo, use la sintaxis siguiente:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:

     - Nombre: Huddle-Room-01

     - Alias: HuddleRoom01

     - Cuenta: huddleroom01@contoso.onmicrosoft.com

     - Contraseña de la cuenta: P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Para modificar un buzón de sala existente, use la sintaxis siguiente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este ejemplo habilita la cuenta para el buzón de sala existente que tiene el valor de alias HuddleRoom02 y establece la contraseña en 808P@$$W 0rd. Tenga en cuenta que la cuenta se HuddleRoom02@contoso.onmicrosoft.com debido al valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Nuevo buzón](/powershell/module/exchange/mailboxes/new-mailbox) y Conjunto [de buzones.](/powershell/module/exchange/mailboxes/set-mailbox)


3. En Exchange Online PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de la reunión:

   - AutomateProcessing: AutoAccept (Los organizadores de la reunión reciben la decisión de reserva de sala directamente sin intervención humana: gratis = aceptar; ocupado = rechazar).

   - AddOrganizerToSubject: $false (El organizador de la reunión no se agrega al asunto de la solicitud de reunión).

   - DeleteComments: $false (Conservar cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).

   - DeleteSubject: $false (Mantener el asunto de las solicitudes de reunión entrantes).

   - RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).

   - AddAdditionalResponse: $true (El texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).

   - AdditionalResponse: "Esta sala tiene una barra de colaboración para Microsoft Teams!" (El texto adicional que se agregará a la solicitud de reunión).

   En este ejemplo se configuran estas opciones en el buzón de sala llamado Huddle-Room-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conectar PowerShell de MS Online para realizar la configuración de Active Directory ejecutando el `Connect-MsolService -Credential $cred` cmdlet de powershell.   Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible. 

5. Establezca la contraseña de huddleroom01@contoso.onmicrosoft.com que no expire con la sintaxis siguiente:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. La cuenta de recursos debe tener una licencia Office 365, preferiblemente la SKU Sala de reuniones recursos. También debe asignar una ubicación de uso a su cuenta de dispositivo, lo que determina qué SKU de licencia están disponibles para su cuenta. Puede usarlo para recuperar una lista de SKU disponibles `Get-MsolAccountSku` para su Office 365 inquilino.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Puede asignar la licencia con Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Para obtener instrucciones [detalladas,](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)vea Asignar licencias a cuentas de usuario con Office 365 PowerShell.




[Configurar cuentas para barras de colaboración para Microsoft Teams usar PowerShell](resource-account-ps.md)

[Implementar barras de colaboración para Microsoft Teams](collab-bar-deploy.md)

[Barras de colaboración para Microsoft Teams licencias](../rooms/rooms-licensing.md)
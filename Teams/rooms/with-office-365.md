---
title: Implementar Salas de Microsoft Teams con Office 365
ms.author: czawideh
author: cazawideh
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Office 365.
ms.openlocfilehash: f54e7f7e201127b0a61c99f09fee2084378dbbd9
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503717"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Implementar Salas de Microsoft Teams con Office 365

Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Office 365.

## <a name="requirements"></a>Requirements

Antes de implementar Salas de Microsoft Teams con Office 365, asegúrese de que ha cumplido los requisitos. Para obtener más información, [vea Salas de Microsoft Teams requisitos.](requirements.md)

### <a name="add-a-resource-account"></a>Agregar una cuenta de recursos

1. Conectar para Exchange Online PowerShell. Para obtener instrucciones, [vea Conectar para Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. En Exchange Online PowerShell, cree un buzón de sala nuevo o modifique un buzón de sala existente. De forma predeterminada, los buzones de sala no tienen cuentas asociadas. Tendrá que agregar una cuenta al crear o modificar un buzón de sala que le permita autenticarse.

   - Para crear un buzón de sala nuevo, use la sintaxis siguiente:

     ``` PowerShell
     New-Mailbox -Name '<Unique Name>' -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:

     - Nombre: Sala de conferencias 01

     - Alias: ConferenceRoom01

     - Cuenta: ConferenceRoom01@contoso.com

     - Contraseña de la cuenta: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name 'Conference Room 01' -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar un buzón de sala existente, use la sintaxis siguiente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     En este ejemplo, se habilita la cuenta para el buzón de sala existente que tiene el valor de alias ConferenceRoom02 y se establece la contraseña en 9898P@$$W 0rd.

     ``` PowerShell
     Set-Mailbox -Identity 'ConferenceRoom02' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Nuevo buzón](/powershell/module/exchange/mailboxes/new-mailbox) y [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).


3. En Exchange Online PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de reunión:

   - AutomateProcessing: AutoAccept (El buzón toma automáticamente una decisión de reserva de sala directamente sin intervención humana).

   - AddOrganizerToSubject: $false (El organizador de la reunión no se agrega al asunto de la solicitud de reunión).

   - DeleteComments: $false (Conservar cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).

   - DeleteSubject: $false (Mantener el asunto de las solicitudes de reunión entrantes).

   - RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).

   - AddAdditionalResponse: $true (El texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).

   - AdditionalResponse: "Esta es una sala Microsoft Teams reunión" (El texto adicional que se agregará a la solicitud de reunión).

   En este ejemplo se configuran estas opciones en el buzón de sala denominado Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity 'ConferenceRoom01' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse 'This is a Microsoft Teams meeting room!'
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).
   
4. Conectar a MS Online PowerShell establezca valores de Active Directory ejecutando el cmdlet de powershell "Conectar-MsolService -Credential $cred". Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible. 

5. Se recomienda encarecidamente deshabilitar la expiración de contraseñas en Salas de Teams cuentas. A continuación se muestra un ejemplo de cómo deshabilitar la expiración de contraseña para la cuenta ConferenceRoom01:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```


1. La cuenta de recursos debe tener una licencia Office 365 para poder conectarse a Microsoft Teams. También debe asignar una ubicación de uso a su cuenta de dispositivo, lo que determina qué SKU de licencia están disponibles para su cuenta. Puede usar para `Get-MsolAccountSku` recuperar una lista de SKU disponibles para su Office 365 inquilino. Puede agregar una licencia con el `Set-MsolUserLicense` cmdlet.

   En este ejemplo se asigna la Sala de reuniones a un usuario basado en EE. UU.

  ``` PowerShell
   Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
  ``` 


   Para obtener instrucciones [detalladas, vea Asignar licencias a cuentas de usuario con Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).


## <a name="validate"></a>Validar

Para la validación, debería poder usar cualquier Microsoft Teams cliente para iniciar sesión en la cuenta que creó.

## <a name="see-also"></a>Vea también
[Actualizar buzones de sala con metadatos adicionales para mejorar la experiencia de búsqueda y sugerencias de sala](/powershell/module/exchange/set-place)

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Implementar Salas de Microsoft Teams](rooms-deploy.md)

[Configurar una consola de sala de Microsoft Teams](console.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Salas de Microsoft Teams licencias](rooms-licensing.md)

---
title: Implementar Salas de Microsoft Teams con Exchange local (híbrido)
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams en un entorno híbrido con Exchange local.
ms.openlocfilehash: ea05ef6b6bf6e13ee907d84d1d48200c0cea5a09
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767233"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>Implementar Salas de Microsoft Teams con Exchange local (híbrido)

Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams en un entorno híbrido con Exchange local y Microsoft Teams.
  
Si su organización tiene una combinación de servicios, con algunos hospedados localmente y otros hospedados en línea, la configuración dependerá de dónde se hospeda cada servicio. En este tema se tratan las implementaciones híbridas para Salas de Microsoft Teams con Exchange hospedadas localmente. Dado que hay muchas variaciones diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas. El siguiente proceso funcionará para muchas configuraciones. Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para lograr el mismo resultado final que se documenta aquí y para otras opciones de implementación.
  
## <a name="requirements"></a>Requirements

Antes de implementar Salas de Microsoft Teams con Exchange local, asegúrese de que ha cumplido los requisitos. Para obtener más información, [vea Salas de Microsoft Teams requisitos.](requirements.md)

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar el buzón de correo remoto y establecer propiedades

1. [Abra el Exchange de administración](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o conéctese a su servidor Exchange con [PowerShell remoto.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. En Exchange PowerShell, cree un buzón de sala nuevo o modifique un buzón de sala existente. De forma predeterminada, los buzones de sala no tienen cuentas asociadas, por lo que tendrá que agregar una cuenta al crear o modificar un buzón de sala que le permita autenticarse con Microsoft Teams.

   - Para crear un buzón de sala nuevo, use la sintaxis siguiente:

     ``` PowerShell
     New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     
     En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:

     - Cuenta: ConferenceRoom01@contoso.com
  
     - Nombre: ConferenceRoom01

     - Alias: ConferenceRoom01

     - Contraseña de la cuenta: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
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

3. En Exchange PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de reunión:

   - AutomateProcessing: AutoAccept (los organizadores de reuniones reciben las decisiones de reserva de salas directamente sin intervención humana).

   - AddOrganizerToSubject: $false (El organizador de la reunión no se agrega al asunto de la solicitud de reunión).

   - DeleteComments: $false (Conservar cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).

   - DeleteSubject: $false (Mantener el asunto de las solicitudes de reunión entrantes).

   - RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).

   - AddAdditionalResponse: $true (El texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).

   - AdditionalResponse: "Esta es una sala Microsoft Teams reunión" (El texto adicional que se agregará a la solicitud de reunión).

   En este ejemplo se configuran estas opciones en el buzón de sala denominado ConferenceRoom01.

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="set-password-to-never-expire"></a>Establecer la contraseña para que nunca expire

1. En la herramienta Usuarios y equipos de **Active Directory,** busque la cuenta Salas de Microsoft Teams, haga clic con el botón derecho en ella y seleccione **Propiedades.**

2. Active la **casilla Contraseña nunca expira y,** a continuación, haga clic en **Aceptar.**

   > [!NOTE]
   > Seleccionar **Contraseña nunca expira es** un requisito para Salas de Microsoft Teams. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, deberá crear una excepción para cada cuenta Salas de Microsoft Teams cuenta.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Asignar una Microsoft 365 o Office 365 licencia

1. Conectar Azure Active Directory. Para obtener más información Azure Active Directory, [vea Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible. 

2. La cuenta de recursos debe tener una licencia Microsoft 365 o Office 365, o Exchange y Microsoft Teams no funcionarán. Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de recursos, lo que determina qué SKU de licencia están disponibles para su cuenta. Puede usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar una lista de SKU disponibles.

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

3. A continuación, puede agregar una licencia con el `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. En este ejemplo se agrega Sala de reuniones licencia a la cuenta:

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

Para la validación, debería poder usar cualquier cliente para iniciar sesión en esta cuenta.
  
## <a name="related-topics"></a>Temas relacionados

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)

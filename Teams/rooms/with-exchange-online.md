---
title: Implementar Salas de Microsoft Teams con Exchange Online
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Exchange Online.
ms.openlocfilehash: ad3b621ef541fcec471e329d1696e4f7000f4cb5
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503747"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implementar Salas de Microsoft Teams con Exchange Online

Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Exchange Online.
  
Si su organización tiene una combinación de servicios, con algunos hospedados localmente y otros hospedados en línea, la configuración dependerá de dónde se hospeda cada servicio. En este tema se tratan las implementaciones híbridas para Salas de Microsoft Teams con Exchange hospedados en línea. Dado que hay muchas variaciones diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas. El siguiente proceso funcionará para muchas configuraciones. Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para lograr el mismo resultado final que se documenta aquí y para otras opciones de implementación.

## <a name="requirements"></a>Requirements

Antes de implementar Salas de Microsoft Teams con Exchange Online, asegúrese de que ha cumplido los requisitos. Para obtener más información, [vea Salas de Microsoft Teams requisitos.](requirements.md)
  
Para implementar Salas de Microsoft Teams con Exchange Online, siga los pasos siguientes. Asegúrese de que tiene los permisos adecuados para ejecutar los cmdlets. 

   > [!NOTE]
   >  El [Azure Active Directory de Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) de esta sección (por ejemplo, Set-MsolUser) se ha probado al configurar cuentas para Salas de Microsoft Teams. Es posible que otros cmdlets funcionen, pero no se han probado en este escenario específico.

Si implementó servicios de federación de Active Directory (AD FS), es posible que tenga que convertir la cuenta de usuario en un usuario administrado antes de seguir estos pasos y, después, convertir el usuario de nuevo en un usuario federado después de completar estos pasos.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Crear una cuenta y configurar las propiedades de Exchange

1. Inicie una sesión Windows PowerShell sesión remota en un equipo y conéctese a Exchange Online siguiente:

    ``` Powershell
   Connect-ExchangeOnline
    ```

2. Después de establecer una sesión, creará un buzón nuevo y lo habilitará como RoomMailboxAccount, o bien cambiará la configuración de un buzón de sala existente. Esto permitirá que la cuenta se autentique en Salas de Microsoft Teams.

   Si va a cambiar un buzón de recursos existente:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si va a crear un buzón de recursos nuevo:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name 'ConferenceRoom01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para mejorar la experiencia de la reunión, deberá establecer las Exchange en la cuenta de usuario de la siguiente manera:

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Rooms enabled  room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Agregar una cuenta de correo electrónico para su cuenta de dominio local

1. En **la herramienta Ad** Usuarios y equipos de Active Directory, haga clic con el botón derecho en el contenedor o unidad organizativa en el que se crearán las cuentas de Salas de Microsoft Teams, haga clic en Nuevo **y, a** continuación, haga clic en **Usuario**.
2. Escriba el nombre para mostrar (- Identidad) del cmdlet anterior (Set-Mailbox o New-Mailbox) en el  cuadro Nombre completo y el alias en el cuadro Nombre **de inicio de sesión de** usuario. Haga clic en **Siguiente**.
3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.

    > [!NOTE]
    > Seleccionar **Contraseña nunca expira es** un requisito para Salas de Microsoft Teams. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, deberá crear una excepción para cada cuenta Salas de Microsoft Teams usuario.
  
4. Haga clic en **Finalizar** para crear la cuenta.
5. Después de crear la cuenta, ejecute una sincronización de directorios. Esto se puede lograr mediante [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) en PowerShell. Cuando se complete, vaya a la página del usuario y compruebe que las dos cuentas creadas en los pasos anteriores se han combinado.

### <a name="assign-an-office-365-license"></a>Asignar una licencia de Office 365

1. En primer lugar, conéctese a Azure AD para aplicar algunas opciones de configuración de la cuenta. Puede ejecutar este cmdlet para conectarse. Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.

    ``` PowerShell
   Connect-MsolService
    ```

2. La cuenta de usuario necesita tener una licencia Office 365 para conectarse a Microsoft Teams. Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de usuario, esto determina qué SKU de licencia están disponibles para su cuenta.
3. Use "Get-MsolAccountSku" para recuperar una lista de SKU disponibles para su Office 365 inquilino.
4. Una vez que haya listado las SKU, puede agregar una licencia con el "Set-MsolUserLicense" <!-- Set-AzureADUserLicense--> cmdlet. 

    ```PowerShell
     Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM
    ```

## <a name="validate"></a>Validar

Para la validación, debería poder usar cualquier Microsoft Teams cliente para iniciar sesión en la cuenta que creó.
  
## <a name="see-also"></a>Vea también

[Actualizar buzones de sala con metadatos adicionales para mejorar la experiencia de búsqueda y sugerencias de sala](/powershell/module/exchange/set-place)

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)

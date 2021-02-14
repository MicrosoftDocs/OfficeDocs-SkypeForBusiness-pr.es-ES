---
title: Implementar Salas de Microsoft Teams con Exchange Online
ms.author: dstrome
author: dstrome
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Exchange Online y Skype Empresarial Server local.
ms.openlocfilehash: 82fa0b1b521c7dd2feadcca2030869b746a444aa
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662315"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implementar Salas de Microsoft Teams con Exchange Online

Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Exchange Online y Skype Empresarial Server local.
  
Si su organización tiene una combinación de servicios, con algunos hospedados de forma local y otros en línea, la configuración dependerá de dónde se hospeda cada servicio. Este tema trata sobre las implementaciones híbridas de salas de Microsoft Teams con Exchange alojado en línea. Debido a que hay tantas variantes diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas. El proceso siguiente funcionará para muchas configuraciones. Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para lograr el mismo resultado final que se ha documentado aquí y para otras opciones de implementación.

La manera más sencilla de configurar las cuentas de usuario es configurarlas mediante cuentas de Windows PowerShell. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario, o validar las cuentas de recursos existentes que tiene con el fin de ayudarle a convertirlas en cuentas de usuario compatibles de Salas de Microsoft Teams. Si lo prefiere, puede seguir los pasos que se indican a continuación para configurar las cuentas que usará el dispositivo de Microsoft Teams Rooms.

## <a name="requirements"></a>Requisitos

Antes de implementar salas de Microsoft Teams con Exchange Online, asegúrese de que cumple los requisitos. Para obtener más información, consulte los [requisitos de salas de Microsoft Teams.](requirements.md)
  
Para implementar salas de Microsoft Teams con Exchange Online, siga los pasos que se indican a continuación. Asegúrese de tener los permisos necesarios para ejecutar los cmdlets asociados. 

   > [!NOTE]
   >  El Módulo Azure Active Directory para [Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) de esta sección (por ejemplo, Set-MsolUser) se ha probado al configurar cuentas para dispositivos de Salas de Microsoft Teams. Sin embargo, es posible que otros cmdlets funcionen, pero que no se hayan probado en este escenario específico.

Si implementó Servicios de federación de Active Directory (AD FS), es posible que tenga que convertir la cuenta de usuario en un usuario administrado antes de seguir estos pasos y, después, convertir el usuario en un usuario federado después de completar estos pasos.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Crear una cuenta y configurar las propiedades de Exchange

1. Inicie una sesión de Windows PowerShell remota en un equipo y conéctese a Exchange Online de la siguiente manera:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Después de establecer una sesión, debe crear un buzón nuevo y habilitarlo como RoomMailboxAccount, o cambiar la configuración de un buzón de sala existente. Esto permitirá que la cuenta se autentique en Salas de Microsoft Teams.

   Si va a cambiar un buzón de recursos existente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si está creando un nuevo buzón de recursos:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para mejorar la experiencia de reunión, deberá establecer las propiedades de Exchange en la cuenta de usuario de la siguiente manera:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Agregar una cuenta de correo electrónico para su cuenta de dominio local

1. En la herramienta AD Usuarios y equipos de **Active Directory,** haga clic con el botón derecho en el contenedor o en la unidad organizativa en la que se crearán sus cuentas de Salas de Microsoft Teams, haga clic en Nuevo **y,** a continuación, haga clic en **Usuario.**
2. Escriba el nombre para mostrar (-Identidad) del cmdlet anterior (Set-Mailbox o New-Mailbox) en el cuadro Nombre completo y el alias en el cuadro Nombre de inicio de sesión **de** usuario.  Haga clic en **Siguiente**.
3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.

    > [!NOTE]
    > Seleccionar la **contraseña nunca expira es** un requisito de Skype Empresarial Server en salas de Microsoft Teams. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, tendrá que crear una excepción para cada cuenta de usuario de Salas de Microsoft Teams.
  
4. Haga clic en **Finalizar** para crear la cuenta.
5. Después de crear la cuenta, ejecute una sincronización de directorios. Para ello, use [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) en PowerShell. Cuando haya finalizado, vaya a la página de usuarios y compruebe que las dos cuentas creadas en los pasos anteriores se han combinado.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Asignar una licencia de Microsoft 365 u Office 365

1. En primer lugar, conéctese a Azure AD para aplicar algunos ajustes de la cuenta. Puede ejecutar este cmdlet para conectarse. Para obtener más información sobre Active Directory, [consulte Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. La cuenta de usuario debe tener una licencia válida de Microsoft 365 u Office 365 para garantizar que Exchange y Skype Empresarial Server funcionen. Si tiene la licencia, tendrá que asignar una ubicación de uso a su cuenta de usuario( esto determina qué SKU de licencia están disponibles para su cuenta). Podrá realizar la tarea en un paso siguiente.
3. A continuación, usa `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> para recuperar una lista de SKU disponibles para su organización de Microsoft 365 u Office 365.
4. Una vez que haya listado las SKU, puede agregar una licencia con el `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK). 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Habilitar la cuenta de usuario con Skype Empresarial Server

1. Crea una sesión Windows PowerShell sesión remota desde un equipo de la siguiente manera:

> [!NOTE]
> Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.
>
> Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

    ``` Powershell
    Import-Module -Name MicrosoftTeams
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Para habilitar la cuenta de Salas de Microsoft Teams para Skype Empresarial Server, ejecute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Si no está seguro de qué valor usar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un usuario existente de Skype Empresarial Server mediante este comando.

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Asignar una licencia de Skype Empresarial Server a su cuenta de Microsoft Teams Rooms

1. Inicie sesión como administrador de inquilinos, abra el Centro de administración de Microsoft 365 y haga clic en la aplicación Administración.
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
3. Haga clic en la cuenta de Salas de Microsoft Teams y, a continuación, haga clic en el icono de lápiz para editar la información de la cuenta.
4. Haga clic en **Licencias**.
5. En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial. Tendrá que usar una licencia de Plan 3 si desea usar Telefonía IP empresarial en Salas de Microsoft Teams.
6. Haga clic en **Guardar**.

Para la validación, debería poder usar cualquier cliente de Skype Empresarial para iniciar sesión en esta cuenta.

> [!NOTE]
> Si actualmente usa LAS SKU de E1, E3, E4 o E5 con el Plan 2 de Skype Empresarial con Audioconferencia o con Sistema telefónico y un plan de llamadas, estos seguirán funcionando. Sin embargo, considere la posibilidad de pasar a un modelo de licencia más sencillo como se describe en la Actualización de licencias de salas de reuniones de [Teams,](rooms-licensing.md)cuando las licencias actuales expiren.

> [!IMPORTANT]
> Si usa Skype Empresarial Plan 2, solo puede usar las salas de Microsoft Teams en modo solo para Skype Empresarial, lo que significa que todas sus reuniones serán reuniones de Skype Empresarial. Para habilitar su sala de reuniones para las reuniones de Microsoft Teams, le recomendamos que compre la licencia de Sala de reuniones.
  
## <a name="related-topics"></a>Temas relacionados

[Configurar cuentas de Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)

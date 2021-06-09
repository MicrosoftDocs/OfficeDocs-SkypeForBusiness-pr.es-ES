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
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Exchange Online y Skype Empresarial Server locales.
ms.openlocfilehash: 2f92f85ddf39c5e1a813492b3092eeeef9b77e4c
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796684"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implementar Salas de Microsoft Teams con Exchange Online

Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams con Exchange Online y Skype Empresarial Server locales.
  
Si su organización tiene una combinación de servicios, con algunos hospedados localmente y otros hospedados en línea, la configuración dependerá de dónde se hospeda cada servicio. En este tema se tratan las implementaciones híbridas para Salas de Microsoft Teams con Exchange en línea. Dado que hay muchas variaciones diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas. El siguiente proceso funcionará para muchas configuraciones. Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para lograr el mismo resultado final que se documenta aquí y para otras opciones de implementación.

La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante el uso de Windows PowerShell. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario Salas de Microsoft Teams compatibles. Si lo prefiere, puede seguir los pasos que se indican a continuación para configurar las cuentas que Salas de Microsoft Teams dispositivo usará.

## <a name="requirements"></a>Requirements

Antes de implementar Salas de Microsoft Teams con Exchange Online, asegúrese de que ha cumplido los requisitos. Para obtener más información, [vea Salas de Microsoft Teams requisitos.](requirements.md)
  
Para implementar Salas de Microsoft Teams con Exchange Online, siga los pasos siguientes. Asegúrese de tener los permisos necesarios para ejecutar los cmdlets asociados. 

   > [!NOTE]
   >  El Azure Active Directory de Windows PowerShell [cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) de esta sección (por ejemplo, Set-MsolUser) se ha probado al configurar cuentas para Salas de Microsoft Teams dispositivos. Es posible que otros cmdlets funcionen, pero no se han probado en este escenario específico.

Si implementó servicios de federación de Active Directory (AD FS), es posible que tenga que convertir la cuenta de usuario en un usuario administrado antes de seguir estos pasos y, después, convertir el usuario de nuevo en un usuario federado después de completar estos pasos.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Crear una cuenta y configurar las propiedades de Exchange

1. Inicie una sesión Windows PowerShell sesión remota en un equipo y conéctese a Exchange Online siguiente:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Después de establecer una sesión, creará un buzón nuevo y lo habilitará como RoomMailboxAccount, o bien cambiará la configuración de un buzón de sala existente. Esto permitirá que la cuenta se autentique en Salas de Microsoft Teams.

   Si va a cambiar un buzón de recursos existente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si va a crear un buzón de recursos nuevo:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para mejorar la experiencia de la reunión, deberá establecer las Exchange en la cuenta de usuario de la siguiente manera:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Agregar una cuenta de correo electrónico para su cuenta de dominio local

1. En la herramienta Ad Usuarios y equipos de **Active Directory,** haga clic con el botón derecho en el contenedor o unidad organizativa en el que se crearán las cuentas de Salas de Microsoft Teams, haga clic en Nuevo y, a continuación, haga clic en **Usuario.**
2. Escriba el nombre para mostrar (- Identidad) del cmdlet anterior (Set-Mailbox o New-Mailbox) en el cuadro Nombre completo y el alias en el cuadro Nombre **de inicio de** sesión de usuario.  Haga clic en **Siguiente**.
3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.

    > [!NOTE]
    > Seleccionar **Contraseña nunca expira es** un requisito para Skype Empresarial Server en Salas de Microsoft Teams. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, deberá crear una excepción para cada cuenta Salas de Microsoft Teams usuario.
  
4. Haga clic en **Finalizar** para crear la cuenta.
5. Después de crear la cuenta, ejecute una sincronización de directorios. Esto se puede lograr mediante [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) en PowerShell. Cuando se complete, vaya a la página de usuarios y compruebe que las dos cuentas creadas en los pasos anteriores se han combinado.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Asignar una Microsoft 365 o Office 365 licencia

1. En primer lugar, conéctese a Azure AD para aplicar algunas opciones de configuración de la cuenta. Puede ejecutar este cmdlet para conectarse. Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. La cuenta de usuario debe tener una licencia Microsoft 365 o Office 365 para asegurarse de que Exchange y Skype Empresarial Server funcionarán. Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de usuario, esto determina qué SKU de licencia están disponibles para su cuenta. Hará la tarea en un paso siguiente.
3. A continuación, use `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> para recuperar una lista de SKU disponibles para su Microsoft 365 o Office 365 organización.
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

> [!NOTE]
> Si está configurando Salas de Teams para unirse Microsoft Teams reuniones, no es necesario que realice los pasos siguientes. Los pasos siguientes solo son necesarios si desea habilitar la compatibilidad con Skype Empresarial.

1. Cree una sesión de Windows PowerShell remoto desde un equipo como se muestra a continuación:

> [!NOTE]
> El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams.
>
> Si usa la versión pública más [reciente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar el Skype Empresarial Online Connector.

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. Para habilitar su Salas de Microsoft Teams de Skype Empresarial Server, ejecute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Si no está seguro de qué valor usar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un usuario Skype Empresarial Server existente con este comando

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Asignar una Skype Empresarial Server a su Salas de Microsoft Teams cuenta

> [!NOTE]
> Si está configurando Salas de Teams para unirse Microsoft Teams reuniones, no es necesario que realice los pasos siguientes. Los pasos siguientes solo son necesarios si desea habilitar la compatibilidad con Skype Empresarial.

1. Inicie sesión como administrador de inquilinos, abra el Microsoft 365 de administración y haga clic en la aplicación Administrador.
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
3. Haga clic en Salas de Microsoft Teams cuenta y, a continuación, haga clic en el icono del lápiz para editar la información de la cuenta.
4. Haga clic en **Licencias**.
5. En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial. Tendrá que usar una licencia de Plan 3 si desea usar Telefonía IP empresarial en Salas de Microsoft Teams.
6. Haga clic en **Guardar**.

Para la validación, debería poder usar cualquier Skype Empresarial cliente para iniciar sesión en esta cuenta.

> [!NOTE]
> Si actualmente usa SKU de E1, E3, E4 o E Skype Empresarial 5 con un plan 2 con audioconferencias o con Sistema telefónico y un plan de llamadas, estos seguirán funcionando. Sin embargo, debería considerar la posibilidad de cambiar a un modelo de licencias más sencillo, como se describe [en Teams Sala de reuniones actualización](rooms-licensing.md)de licencias, después de que expiren las licencias actuales.

> [!IMPORTANT]
> Si usa Skype Empresarial Plan 2, solo puede usar el Salas de Microsoft Teams en el modo solo Skype Empresarial, lo que significa que todas las reuniones se Skype Empresarial reuniones. Para habilitar la sala de reuniones Microsoft Teams reuniones, le recomendamos que compre la licencia Sala de reuniones reunión.
  
## <a name="related-topics"></a>Temas relacionados

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)

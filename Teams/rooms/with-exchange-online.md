---
title: Implementar Salas de Microsoft Teams con Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Exchange Online.
ms.openlocfilehash: e53fd2ebd25ef6b625ada84b60d58e42e8c13a28
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628426"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implementar Salas de Microsoft Teams con Exchange Online

Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams con Exchange Online y Skype empresarial Server local.
  
Si su organización tiene una combinación de servicios, con algunos locales hospedados y alojados en línea, la configuración dependerá de dónde se hospede cada servicio. En este tema se tratan las implementaciones híbridas de las salas de Microsoft Teams con Exchange hospedado en línea. Puesto que existen tantas variantes diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas. El siguiente proceso funciona para muchas configuraciones. Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para obtener el mismo resultado final que se explica aquí, así como para otras opciones de implementación.

La forma más sencilla de configurar cuentas de usuario es configurarlas con Windows PowerShell remoto. Microsoft proporciona [SkypeRoomProvisioningScript. PS1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario compatibles con salas de Microsoft Teams. Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que usará el dispositivo de salas de Microsoft Teams.

## <a name="requirements"></a>Requisitos

Antes de implementar salas de Microsoft Teams con Exchange Online, asegúrese de que cumple con los requisitos. Para obtener más información, consulte [requisitos de salas de Microsoft Teams](requirements.md).
  
Para implementar salas de Microsoft Teams con Exchange Online, siga los pasos que se indican a continuación. Asegúrese de tener los permisos necesarios para ejecutar los cmdlets asociados. 

   > [!NOTE]
   >  El [módulo Azure Active Directory para cmdlets de Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) de esta sección (por ejemplo, Set-MsolUser) se ha probado en la configuración de cuentas para dispositivos de salas de Microsoft Teams. Sin embargo, es posible que otros cmdlets funcionen, pero que no hayan sido probados en este escenario específico.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Crear una cuenta y configurar las propiedades de Exchange

1. Inicie una sesión remota de Windows PowerShell en un equipo PC y conéctese a Exchange online de la siguiente manera:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. Después de establecer una sesión, cree un nuevo buzón de correo y lo habilite como RoomMailboxAccount, o cambie la configuración de un buzón de sala existente. Esto permitirá que la cuenta se autentique en las salas de Microsoft Teams.

   Si va a cambiar un buzón de recursos existente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si va a crear un nuevo buzón de recursos:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para mejorar la experiencia de la reunión, tendrá que configurar las propiedades de Exchange en la cuenta de usuario de la siguiente manera:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Agregar una cuenta de correo electrónico para su cuenta de dominio local

1. En la herramienta **ad de usuarios y equipos de Active** Directory, haga clic con el botón secundario en el contenedor o la unidad organizativa en el que se crearán las cuentas de las salas de Microsoft Teams, haga clic en **nuevo**y, a continuación, haga clic en **usuario**.
2. Escriba el nombre para mostrar (-Identity) del cmdlet anterior (Set-Mailbox o New-Mailbox) en el cuadro **nombre completo** y el alias en el cuadro **nombre de inicio de sesión de usuario** . Haga clic en **Siguiente**.
3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.

    > [!NOTE]
    > La selección de la **contraseña nunca expira** es un requisito de Skype empresarial Server en las salas de Microsoft Teams. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, tendrá que crear una excepción para cada cuenta de usuario de salas de Microsoft Teams.
  
4. Haga clic en **Finalizar** para crear la cuenta.
5. Una vez que haya creado la cuenta, ejecute una sincronización de directorios. Esto se puede llevar a cabo con [set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) en PowerShell. Cuando haya finalizado, vaya a la página usuarios y compruebe que las dos cuentas creadas en los pasos anteriores se hayan fusionado.

### <a name="assign-an-office-365-license"></a>Asignar una licencia de Office 365

1. En primer lugar, conéctese a Azure AD para aplicar la configuración de la cuenta. Puede ejecutar este cmdlet para conectarse. Para obtener más información sobre Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible. 

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. La cuenta de usuario debe tener una licencia válida de Office 365 para garantizar que Exchange y Skype empresarial Server funcionen. Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de usuario, lo cual determina qué SKU de licencia están disponibles para su cuenta. Realizará la tarea en un paso siguiente.
3. A continuación, use`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> para recuperar una lista de las SKU disponibles para su inquilino de Office 365.
4. Una vez que haya finalizado la lista de las SKU, puede Agregar una licencia con el`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK). 

    ```PowerShell
      Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Habilitar la cuenta de usuario con Skype empresarial Server

1. Cree una sesión remota de Windows PowerShell desde un equipo informático de la siguiente manera:

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Para habilitar la cuenta de Microsoft Teams Rooms para Skype empresarial Server, ejecute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Si no está seguro de qué valor usar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un usuario existente de Skype empresarial Server mediante este comando

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Asignar una licencia de Skype empresarial Server a su cuenta de salas de Microsoft Teams

1. Inicie sesión como administrador de inquilinos, abra el portal administrativo de Office 365 y haga clic en la aplicación de administrador.
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
3. Haga clic en la cuenta salas de Microsoft Teams y, a continuación, haga clic en el icono de lápiz para editar la información de la cuenta.
4. Haga clic en **Licencias**.
5. En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial. Tendrá que usar una licencia de Plan 3 Si quiere usar la telefonía IP empresarial en salas de Microsoft Teams.
6. Haga clic en **Guardar **.

Para la validación, debe poder usar cualquier cliente de Skype empresarial para iniciar sesión en esta cuenta.

> [!NOTE]
> Si actualmente usa las SKU de E1, E3, E4 o E5 con Skype empresarial plan 2 con conferencias de audio o con el sistema telefónico de Office 365 y un plan de llamadas, estos seguirán funcionando. Sin embargo, debe considerar la posibilidad de cambiar a un modelo de licencias más sencillo, como se describe en [Teams, actualización de licencias de sala de reuniones](rooms-licensing.md), después de que venzan las licencias actuales.

> [!IMPORTANT]
> Si está usando Skype empresarial plan 2, solo puede usar las salas de Microsoft Teams en modo de solo Skype empresarial, lo que significa que todas sus reuniones serán reuniones de Skype empresarial. Para habilitar las reuniones de Microsoft Teams en su sala de reuniones, le recomendamos que compre la licencia sala de reuniones.
  
## <a name="see-also"></a>Vea también

[Configurar cuentas para salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para salas de Microsoft Teams](rooms-plan.md)
  
[Implementar salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de salas de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)

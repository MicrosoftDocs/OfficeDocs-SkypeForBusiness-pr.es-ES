---
title: Implementar salones de equipos de Microsoft con Exchange Online
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos con Exchange Online.
ms.openlocfilehash: 1dc4e73fea7376033d8914cd1814e1edeb68e7d5
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33363038"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implementar salones de equipos de Microsoft con Exchange Online

Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos con Exchange Online y Skype para Business Server local.
  
Si su organización tiene una mezcla de servicios, con algunas hospedado en local y algunas alojado en línea, a continuación, la configuración depende de donde se hospeda cada servicio. En este tema se trata las implementaciones híbridas en salas de equipos de Microsoft con Exchange alojado en línea. Debido a que hay muchas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todos ellos. El siguiente proceso funcionará para muchas configuraciones. Si el proceso no es adecuado para el programa de instalación, se recomienda que use Windows PowerShell para lograr el mismo resultado final, tal como se describe aquí y para otras opciones de implementación.

La forma más sencilla de configurar las cuentas de usuario es configurarlas mediante Windows PowerShell remoto. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudar a convertirlas en cuentas de usuario compatibles con salones de los equipos de Microsoft. Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que se va a usar el dispositivo de salas de equipos de Microsoft.

## <a name="requirements"></a>Requisitos

Antes de implementar Microsoft salones de los equipos con Exchange Online, debe asegurarse de que cumplen los requisitos. Para obtener más información, vea [requisitos de salas de equipos de Microsoft](requirements.md).
  
Para implementar Microsoft salones de los equipos con Exchange Online, siga los pasos siguientes. Asegúrese de tener los permisos necesarios para ejecutar los cmdlets asociados.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Crear una cuenta y configurar las propiedades de Exchange

1. Iniciar una sesión remota de Windows PowerShell en un PC y conectarse a Exchange Online, como se indica a continuación:

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. Después de establecer una sesión, podrá crear un nuevo buzón y habilitar como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente. Esto le permitirá la cuenta autenticar en Microsoft los equipos locales.

   Si va a cambiar un buzón de recursos existente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si está creando un nuevo buzón de recursos:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para mejorar la experiencia de reunión, debe establecer las propiedades de Exchange en la cuenta de usuario de la siguiente manera:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Agregar una cuenta de correo electrónico para su cuenta de dominio local

1. Herramienta de **usuarios de Active Directory y AD de equipos** , haga clic en el contenedor o la unidad organizativa que sus salones de los equipos de Microsoft se crearán cuentas en, haga clic en **nuevo**y, a continuación, haga clic en **usuario**.
2. Escriba el nombre para mostrar (-Identity) desde el cmdlet anterior (Set-Mailbox o New-Mailbox) en el cuadro **nombre completo** y el alias en el cuadro **nombre de inicio de sesión de usuario** . Haga clic en **Siguiente**.
3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.

    > [!NOTE]
    > Selección de **la contraseña nunca caduca** es un requisito para Skype para Business Server en salas de equipos de Microsoft. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, debe crear una excepción para cada cuenta de usuario de salas de equipos de Microsoft.
  
4. Haga clic en **Finalizar** para crear la cuenta.
5. Tras crear la cuenta, ejecute una sincronización de directorios. Cuando finalice, vaya a la página de usuarios y compruebe que las dos cuentas que ha creado en los pasos anteriores se han fusionado.

### <a name="assign-an-office-365-license"></a>Asignar una licencia de Office 365

1. En primer lugar, conéctese a Azure AD para aplicar algunas opciones de configuración de cuenta. Puede ejecutar este cmdlet para conectarse.

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. La cuenta de usuario debe tener una licencia válida de Office 365 para asegurarse de que Exchange y Skype para Business Server funcionarán. Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de usuario: Esto determina qué SKU de las licencias están disponibles para su cuenta. Podrá realizar la asignación en un paso siguiente.
3. A continuación, usar`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> para recuperar una lista de SKU disponibles para el inquilino de Office 365.
4. Una vez que la lista fuera de las SKU, puede agregar una licencia utilizando la`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK). 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Habilitar la cuenta de usuario con Skype para Business Server

1. Crear una sesión remota de Windows PowerShell desde un PC de la siguiente manera:

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Para habilitar la cuenta de salas de equipos de Microsoft para Skype para Business Server, ejecute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Si no está seguro de qué valor debe utilizar para el parámetro RegistrarPool en el entorno, puede obtener el valor de una existente Skype para usuario Business Server con este comando

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Asignar un Skype para licencia de servidor empresarial a su cuenta de salas de equipos de Microsoft

1. Inicie sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
3. Haga clic en la cuenta de salas de equipos de Microsoft y, a continuación, haga clic en el icono de lápiz para editar la información de cuenta.
4. Haga clic en **Licencias**.
5. En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial. Debe utilizar una licencia de planeación 3 si desea usar Enterprise Voice en salas de equipos de Microsoft.
6. Haga clic en **Guardar **.

Para la validación, debe usar cualquier Skype para clientes empresariales para iniciar sesión en esta cuenta.
  
## <a name="see-also"></a>Vea también

[Configurar las cuentas para salas de equipos de Microsoft](room-systems-v2-configure-accounts.md)

[Plan para salas de equipos de Microsoft](skype-room-systems-v2-0.md)
  
[Implementación de salas de equipos de Microsoft](room-systems-v2.md)
  
[Configurar una consola de salas de equipos de Microsoft](console.md)
  
[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

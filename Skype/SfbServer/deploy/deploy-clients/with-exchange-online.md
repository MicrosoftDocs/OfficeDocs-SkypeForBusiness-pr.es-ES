---
title: Implementar Sistemas de salas de Skype v2 con Exchange Online (híbrida)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lea este tema para obtener información sobre cómo implementar sistemas de salas de Skype v2 con Exchange Online.
ms.openlocfilehash: 4fea489c2ae8c3e2fbf8205936ad3ddbff52927a
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online-hybrid"></a>Implementar Sistemas de salas de Skype v2 con Exchange Online (híbrida)
 
Lea este tema para obtener información sobre cómo implementar sistemas de salas de Skype v2 con Exchange Online.
  
Si su organización tiene una mezcla de servicios, con algunas alojadas en locales y algunos se alojan en línea, su configuración dependerá donde se hospeda cada servicio. Este tema trata las implementaciones híbrido para sistemas de salas de Skype v2 con Exchange alojado en línea. Porque hay muchas diversas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todos ellos. El siguiente proceso de trabajo para muchas configuraciones. Si el proceso no es adecuado para la instalación, le recomendamos que utilice Windows PowerShell (consulte el Apéndice: PowerShell) para lograr el mismo resultado final, tal como se describe aquí y para otras opciones de implementación. A continuación, debe utilizar la secuencia de comandos de Windows PowerShell para comprobar la configuración de sistemas de salas de Skype v2. (Consulte la secuencia de comandos de comprobación de la cuenta.)
  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>Implementar Sistemas de salas de Skype v2 con Exchange Online

Antes de implementar sistemas de salas de Skype v2 con Exchange Online, asegúrese de que cumple los requisitos. Para obtener más información, vea [requisitos de los sistemas de salas de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Para implementar sistemas de salas de Skype v2 con Exchange Online, siga los siguientes pasos. Asegúrese de tener los permisos necesarios para ejecutar los cmdlets asociados. 
  
### <a name="create-an-account-and-set-exchange-properties"></a>Crear una cuenta y configurar las propiedades de Exchange

1. Iniciar una sesión remota de Windows PowerShell en un PC y conectarse a Exchange Online como sigue:
    
  ```
  Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic 
-AllowRedirection

  ```

2. Después de establecer una sesión, podrá crear un nuevo buzón y habilitarlo como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente. Esto permitirá que la cuenta autenticar en sistemas de salas de Skype v2.
    
   Si va a cambiar un buzón de recursos existente:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si desea crear un nuevo buzón de recursos:
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para mejorar la experiencia de la reunión, debe establecer las propiedades de Exchange en la cuenta de usuario de la siguiente manera:
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. Debe conectarse a Azure AD para aplicar algunas de las configuraciones de la cuenta. Puede ejecutar este cmdlet para conectarse.
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Agregar una cuenta de correo electrónico para su cuenta de dominio local

1. En la herramienta de **usuarios de Active Directory y equipos de AD** , haga clic en la carpeta o la unidad organizativa que sus sistemas de sala de Skype se crearán cuentas de v2, haga clic en **nuevo**y haga clic en **usuario**.
    
2. Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.


3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.
    
    > [!NOTE]
    > Seleccione la **contraseña nunca caduca** es un requisito para Skype para Business Server 2015 en sistemas de salas de Skype v2. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, debe crear una excepción para cada cuenta de usuario de sistemas de salas de Skype v2.
  
4. Haga clic en **Finalizar** para crear la cuenta.
    
5. Tras crear la cuenta, ejecute una sincronización de directorios. Cuando finalice, vaya a la página de usuarios y compruebe que las dos cuentas que ha creado en los pasos anteriores se han fusionado.
    
### <a name="assign-an-office-365-license"></a>Asignar una licencia de Office 365

1. La cuenta de usuario debe tener una licencia válida de Office 365 para asegurarse de que funcionará Exchange y Skype para Business Server 2015. Si dispone de la licencia, debe asignar una ubicación de uso a su cuenta de usuario: Esto determina qué SKU de las licencias están disponibles para su cuenta.
    
2. A continuación, utilice MsolAccountSku de Get para recuperar una lista de SKU disponibles para los clientes de Office 365.
    
3. Una vez que tenga la lista de las SKU, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a>Habilitar la cuenta de usuario con Skype Empresarial Server 2015

1. Cree una sesión remota de Windows PowerShell desde un PC de la manera siguiente:
    
  ```
  Import-Module LyncOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber

  ```

2. Para habilitar tu cuenta de Skype sala sistemas v2 para Skype para Business Server 2015, ejecute este comando:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Si no está seguro de qué valor debe utilizar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un Skype existente para usuario Business Server 2015 mediante este comando
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a>Asignar una licencia de Skype Empresarial Server 2015 a su cuenta de Sistemas de salas de Skype v2

1. Inicie sesión como un administrador de inquilinos, abrir el Portal de administración de Office 365 y haga clic en Administrador de la aplicación.
    
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
    
3. Haga clic en la cuenta de Skype sala sistemas v2 y, a continuación, haga clic en el icono de lápiz para editar la información de cuenta.
    
4. Haga clic en **Licencias**.
    
5. En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial. Tendrá que utilizar una licencia de Plan 3 si desea utilizar la Telefonía IP empresarial en su v2 sistemas de salas de Skype.
    
6. Haga clic en **Guardar**.
    
Para la validación, puede utilizar cualquier Skype para Business client para iniciar sesión en esta cuenta.
  
## <a name="see-also"></a>Vea también

#### 

[Plan para la sala de Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implementar sala de Skype v2 de sistemas](room-systems-v2.md)
  
[Configurar una consola de sistemas de salas de Skype v2](console.md)
  
[Administrar espacio de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


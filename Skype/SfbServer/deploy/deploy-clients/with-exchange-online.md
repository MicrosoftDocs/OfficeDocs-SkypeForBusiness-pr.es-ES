---
title: Implementar Sistemas de salas de Skype v2 con Exchange Online (híbrida)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Exchange Online.
ms.openlocfilehash: f97b4a140a220440c18c5a3094af01299da9dddf
ms.sourcegitcommit: 6340d0050a51790e40b7ab8e4e89348251ba184f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "19649615"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online-hybrid"></a>Implementar Sistemas de salas de Skype v2 con Exchange Online (híbrida)
 
Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 con Exchange Online.
  
Si su organización tiene una mezcla de servicios, con algunas hospedado en local y algunas alojado en línea, a continuación, la configuración depende de donde se hospeda cada servicio. Este tema tratan las implementaciones híbridas en sistemas de salón de Skype v2 con Exchange alojado en línea. Debido a que hay muchas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todos ellos. El siguiente proceso funcionará para muchas configuraciones. Si el proceso no es adecuado para el programa de instalación, se recomienda que use Windows PowerShell (consulte el Apéndice: PowerShell) para lograr el mismo resultado final, tal como se describe aquí y para otras opciones de implementación. A continuación, debe usar la secuencia de comandos de Windows PowerShell proporcionada para comprobar el programa de instalación de sistemas de salón de Skype v2. (Vea la secuencia de comandos de comprobación de cuenta).
  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>Implementar Sistemas de salas de Skype v2 con Exchange Online

Antes de implementar sistemas de salón de Skype v2 con Exchange Online, debe asegurarse de que cumplen los requisitos. Para obtener más información, vea [requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Para implementar sistemas de salón de Skype v2 con Exchange Online, siga los pasos siguientes. Asegúrese de tener los permisos necesarios para ejecutar los cmdlets asociados. 
  
### <a name="create-an-account-and-set-exchange-properties"></a>Crear una cuenta y configurar las propiedades de Exchange

1. Iniciar una sesión remota de Windows PowerShell en un PC y conectarse a Exchange Online, como se indica a continuación:
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. Después de establecer una sesión, podrá crear un nuevo buzón y habilitar como un RoomMailboxAccount o cambiar la configuración de un buzón de sala existente. Esto le permitirá la cuenta autenticar en sistemas de salón de Skype v2.
    
   Si va a cambiar un buzón de recursos existente:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Si está creando un nuevo buzón de recursos:
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para mejorar la experiencia de reunión, debe establecer las propiedades de Exchange en la cuenta de usuario de la siguiente manera:
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. Debe conectarse a Azure AD para aplicar algunas de las configuraciones de la cuenta. Puede ejecutar este cmdlet para conectarse.
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Agregar una cuenta de correo electrónico para su cuenta de dominio local

1. Herramienta de **usuarios de Active Directory y AD de equipos** , haga clic en la carpeta o unidad organizativa que los sistemas de salón de Skype se crearán cuentas de v2 en, haga clic en **nuevo**y haga clic en **usuario**.
    
2. Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.


3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.
    
    > [!NOTE]
    > Selección de **la contraseña nunca caduca** es un requisito para Skype para Business Server 2015 en sistemas de salón de Skype v2. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, debe crear una excepción para cada cuenta de usuario de sistemas de salón de Skype v2.
  
4. Haga clic en **Finalizar** para crear la cuenta.
    
5. Tras crear la cuenta, ejecute una sincronización de directorios. Cuando finalice, vaya a la página de usuarios y compruebe que las dos cuentas que ha creado en los pasos anteriores se han fusionado.
    
### <a name="assign-an-office-365-license"></a>Asignar una licencia de Office 365

1. La cuenta de usuario debe tener una licencia válida de Office 365 para asegurarse de que funcionará Exchange y Skype para Business Server 2015. Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de usuario: Esto determina qué SKU de las licencias están disponibles para su cuenta.
    
2. A continuación, use Get-MsolAccountSku para recuperar una lista de SKU disponibles para el inquilino de Office 365.
    
3. Una vez que tenga la lista de las SKU, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a>Habilitar la cuenta de usuario con Skype Empresarial Server 2015

1. Crear una sesión remota de Windows PowerShell desde un PC de la siguiente manera:
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Para habilitar su cuenta de Skype salón sistemas v2 de Skype para Business Server 2015, ejecute este comando:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Si no está seguro de qué valor debe utilizar para el parámetro RegistrarPool en el entorno, puede obtener el valor de una existente Skype para usuario Business Server 2015 con este comando
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a>Asignar una licencia de Skype Empresarial Server 2015 a su cuenta de Sistemas de salas de Skype v2

1. Inicie sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.
    
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
    
3. Haga clic en la cuenta de Skype salón sistemas v2 y, a continuación, haga clic en el icono de lápiz para editar la información de cuenta.
    
4. Haga clic en **Licencias**.
    
5. En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial. Debe utilizar una licencia de planeación 3 si desea usar Enterprise Voice en su v2 de sistemas de salón de Skype.
    
6. Haga clic en **Guardar**.
    
Para la validación, debe usar cualquier Skype para clientes empresariales para iniciar sesión en esta cuenta.
  
## <a name="see-also"></a>Vea también

#### 

[Planeación de la sala de Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implementación de salón de Skype v2 de sistemas](room-systems-v2.md)
  
[Configurar una consola de v2 de sistemas de salón de Skype](console.md)
  
[Administración de salón de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


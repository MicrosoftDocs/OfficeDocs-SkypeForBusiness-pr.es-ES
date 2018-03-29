---
title: Implementar Sistemas de salas de Skype v2 con Exchange local (híbrida)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: Lea este tema para obtener información sobre cómo implementar sistemas de salas de Skype v2 en un entorno híbrido con Exchange en las instalaciones.
ms.openlocfilehash: a0a53b7f8be916d1c0c1a69a23a0f8c604420d9a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises-hybrid"></a>Implementar Sistemas de salas de Skype v2 con Exchange local (híbrida)
 
Lea este tema para obtener información sobre cómo implementar sistemas de salas de Skype v2 en un entorno híbrido con Exchange en las instalaciones.
  
Si su organización tiene una mezcla de servicios, con algunas alojadas en locales y algunos se alojan en línea, su configuración dependerá donde se hospeda cada servicio. Este tema trata las implementaciones híbrido para sistemas de salas de Skype v2 con Exchange alojado en locales. Porque hay muchas diversas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todos ellos. El siguiente proceso de trabajo para muchas configuraciones. Si el proceso no es adecuado para la instalación, se recomienda utilizar Windows PowerShell para lograr el mismo resultado final, tal como se describe aquí y para otras opciones de implementación. A continuación, debe utilizar la secuencia de comandos de Windows PowerShell para comprobar la configuración de sistemas de salas de Skype v2. (Consulte la secuencia de comandos de comprobación de la cuenta.)
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Implementar Sistemas de salas de Skype v2 con Exchange local

Antes de implementar sistemas de salas de Skype v2 con Exchange en las instalaciones, asegúrese de que cumple los requisitos. Para obtener más información, vea [requisitos de los sistemas de salas de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Si está implementando sistemas de salas de Skype v2 con Exchange en las instalaciones, se va a utilizar herramientas administrativas de Active Directory para agregar una dirección de correo electrónico de su cuenta de dominio local. Esta cuenta se sincronizará con Office 365. Tendrá que hacer lo siguiente:
  
- Crear una cuenta y sincronizarla con Active Directory
    
- Habilitar el buzón de correo remoto y establecer propiedades
    
- Asignar una licencia de Office 365.
    
- Habilitar la cuenta del dispositivo con Skype para Business Server. Para ello, el entorno deberá cumplir con los requisitos previos que se detallan aquí:
    
  - Debe tener Skype para los negocios en línea (Plan 2) o superior en su plan de Office 365. El plan debe admitir la funcionalidad de conferencias.
    
  - Si necesita Telefonía IP empresarial (telefonía PSTN) mediante proveedores de servicios de telefonía para sistemas de salas de Skype v2 necesita Skype para los negocios en línea (Plan 3).
    
  - Los usuarios de inquilinos deben tener buzones de Exchange.
    
  - Tu cuenta de Skype sala sistemas v2 requieren un Skype para los negocios en línea (Plan 2) o Skype para licencia de negocios en línea (Plan 3), pero no requiere una licencia de Exchange Online.
    
- Asignar un Skype para licencia Business Server a tu cuenta de Skype sala sistemas v2.
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a>Crear una cuenta y sincronizarla con Active Directory

1. En la herramienta **y equipos AD de usuarios de Active Directory** , haga clic en la carpeta o la unidad organizativa que sus sistemas de sala de Skype se crearán cuentas de v2, haga clic en **nuevo**y, a continuación, haga clic en **usuario**.
    
2. Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.
    
3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.
    
    > [!NOTE]
    > Seleccione la **contraseña nunca caduca** es un requisito para Skype para Business Server en sistemas de salas de Skype v2. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, debe crear una excepción para cada cuenta de dispositivo v2 de sistemas de salas de Skype.
  
4. Tras crear la cuenta, ejecute una sincronización de directorios. Cuando es completa, vaya a la página de usuarios en el centro de administración de Office 365 y compruebe que la cuenta que creó en los pasos anteriores ha combinado en línea.
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar el buzón de correo remoto y establecer propiedades

1. Habilitar el buzón remoto, abra el shell de administración de Exchange local con permisos de administrador y ejecute el siguiente comando:
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -RemoteRoutingAddress 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. Iniciar una sesión remota de Windows PowerShell y conectarse a Microsoft Exchange. De los inquilinos de Office 365, ejecute los comandos siguientes:
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://outlook.office365.com/ps1-liveid/' -Credential $cred -Authentication Basic -AllowRedirection 
   Import-PSSession $sess
   ```

3. Para mejorar la experiencia de la reunión, debe establecer las propiedades de Exchange en la cuenta del dispositivo de la siguiente manera:
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    Para obtener más información acerca de las propiedades que debe establecer, vea Propiedades de Exchange.
    
4. Tendrá que conectarse a Azure AD para aplicar algunas de las configuraciones de la cuenta. Puede ejecutar este comando para conectarse:
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a>Asignar una licencia de Office 365

1. La cuenta del dispositivo debe tener una licencia válida de Office 365 para asegurarse de que Exchange y Skype para Business Server funcionarán. Si dispone de la licencia, debe asignar una ubicación de uso a la cuenta del dispositivo, esto determina qué SKU de las licencias están disponibles para su cuenta.
    
2. A continuación, utilice MsolAccountSku de Get para recuperar una lista de SKU disponibles para los clientes de Office 365.
    
3. Una vez que tenga la lista de las SKU, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a>Habilitar la cuenta del dispositivo con Skype Empresarial

1. Cree una sesión remota de Windows PowerShell desde un PC de la manera siguiente:
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar tu cuenta de Skype sala sistemas v2 para Skype para Business Server, ejecute este comando:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Si no está seguro de qué valor debe utilizar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un Skype existente para usuario Business Server usando este comando
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a>Asignar una licencia de Skype Empresarial a su cuenta de Sistemas de salas de Skype v2.

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


---
title: Implementar Sistemas de salas de Skype v2 con Exchange local
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
description: Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 en un entorno híbrido con Exchange local.
ms.openlocfilehash: 4fd9b1f2ef7f40f0dac72bd97c25b59d18698154
ms.sourcegitcommit: 4e9f4e2297cea3372a97f4ea178eb75ba6f8753f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2018
ms.locfileid: "19887837"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Implementar Sistemas de salas de Skype v2 con Exchange local
 
Lea este tema para obtener información acerca de cómo implementar sistemas de salón de Skype v2 en un entorno híbrido con Exchange local y Skype para profesionales en línea.
  
Si su organización tiene una mezcla de servicios, con algunas hospedado en local y algunas alojado en línea, a continuación, la configuración depende de donde se hospeda cada servicio. Este tema tratan las implementaciones híbridas en sistemas de salón de Skype v2 con Exchange hospedado localmente. Debido a que hay muchas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todos ellos. El siguiente proceso funcionará para muchas configuraciones. Si el proceso no es adecuado para el programa de instalación, se recomienda que use Windows PowerShell para lograr el mismo resultado final, tal como se describe aquí y para otras opciones de implementación. 

Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudarle a convertirlas en cuentas de usuario de v2 de Skype salón sistemas compatibles. Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que se va a usar el dispositivo v2 de sistemas de salón de Skype.
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Implementar Sistemas de salas de Skype v2 con Exchange local

Antes de implementar sistemas de salón de Skype v2 con Exchange local, debe asegurarse de que cumplen los requisitos. Para obtener más información, vea [requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Si va a implementar sistemas de salón de Skype v2 con Exchange local, va a usar las herramientas administrativas de Active Directory para agregar una dirección de correo electrónico para su cuenta de dominio local. Esta cuenta se sincronizará con Office 365. Tendrá que hacer lo siguiente:
  
- Crear una cuenta y sincronizarla con Active Directory
    
- Habilitar el buzón de correo remoto y establecer propiedades
    
- Asignar una licencia de Office 365.
    
- Habilitar la cuenta del dispositivo con Skype para Business Server. Para ello, el entorno deberá cumplir con los requisitos previos que se detallan aquí:
    
  - Debe tener Skype para profesionales Online (Plan 2) o superior en su plan de Office 365. El plan debe admitir la funcionalidad de conferencias.
    
  - Si necesita Enterprise Voice (telefonía PSTN) con proveedores de servicios de telefonía para sistemas de salón de Skype v2 necesita Skype para profesionales en línea (planeación de 3).
    
  - Los usuarios de inquilinos deben tener los buzones de Exchange.
    
  - Su cuenta de Skype salón sistemas v2 requieren un Skype para profesionales Online (Plan 2) o Skype para licencia empresarial en línea (planeación de 3), pero no requiere una licencia de Exchange Online.
    
- Asignar un Skype para licencia de servidor empresarial a su cuenta de Skype salón sistemas v2.
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a>Crear una cuenta y sincronizarla con Active Directory

1. En la herramienta de **usuarios de Active Directory y AD de equipos** , haga clic en la carpeta o unidad organizativa que los sistemas de salón de Skype se crearán cuentas de v2, haga clic en **nuevo**y, a continuación, haga clic en **usuario**.
    
2. Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.
    
3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.
    
    > [!NOTE]
    > Selección de **la contraseña nunca caduca** es un requisito para Skype para Business Server en sistemas de salón de Skype v2. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, debe crear una excepción para cada cuenta de dispositivo v2 de sistemas de salón de Skype.
  
4. Tras crear la cuenta, ejecute una sincronización de directorios. Una vez finalizada, vaya a la página de los usuarios en el centro de administración de Office 365 y compruebe que la cuenta creada en los pasos anteriores se combinado en línea.
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar el buzón de correo remoto y establecer propiedades

1. Habilitar el buzón remoto, abra el shell de administración de Exchange local con permisos de administrador y ejecute el siguiente comando:
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. Iniciar una sesión remota de Windows PowerShell y conectarse a Microsoft Exchange. Desde el inquilino de Office 365, ejecute los siguientes comandos:
    
   ```
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess = New-PSSession -ConfigurationName Microsoft.Exchange -Credential $cred -AllowRedirection -Authentication Basic -ConnectionUri "https://<ExchangeServerFQDN>/PowerShell"
   Import-PSSession $sess
   ```

3. Para mejorar la experiencia de reunión, debe establecer las propiedades de Exchange en la cuenta del dispositivo de la siguiente manera:
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    Para obtener más información acerca de las propiedades que necesita establecer, vea las propiedades de Exchange.
    
4. Tendrá que conectarse a Azure AD para aplicar algunas de las configuraciones de la cuenta. Puede ejecutar este comando para conectarse:
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a>Asignar una licencia de Office 365

1. La cuenta del dispositivo debe tener una licencia válida de Office 365 para asegurarse de que Exchange y Skype para Business Server funcionarán. Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta.
    
2. A continuación, use Get-MsolAccountSku para recuperar una lista de SKU disponibles para el inquilino de Office 365.
    
3. Una vez que tenga la lista de las SKU, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a>Habilitar la cuenta del dispositivo con Skype Empresarial

1. Crear una sesión remota de Windows PowerShell desde un PC de la siguiente manera:
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar su cuenta de Skype salón sistemas v2 de Skype para Business Server, ejecute este comando:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Si no está seguro de qué valor debe utilizar para el parámetro RegistrarPool en el entorno, puede obtener el valor de una existente Skype para usuario Business Server con este comando
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a>Asignar una licencia de Skype Empresarial a su cuenta de Sistemas de salas de Skype v2.

1. Inicie sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.
    
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
    
3. Haga clic en la cuenta de Skype salón sistemas v2 y, a continuación, haga clic en el icono de lápiz para editar la información de cuenta.
    
4. Haga clic en **Licencias**.
    
5. En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial. Debe utilizar una licencia de planeación 3 si desea usar Enterprise Voice en su v2 de sistemas de salón de Skype.
    
6. Haga clic en **Guardar**.
    
Para la validación, debe usar cualquier Skype para clientes empresariales para iniciar sesión en esta cuenta.
  
## <a name="see-also"></a>Vea también

[Configurar cuentas para sistemas de salón de Skype v2](room-systems-v2-configure-accounts.md)

[Planeación de la sala de Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implementación de salón de Skype v2 de sistemas](room-systems-v2.md)
  
[Configurar una consola de v2 de sistemas de salón de Skype](console.md)
  
[Administración de salón de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)


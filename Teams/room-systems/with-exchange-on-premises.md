---
title: Implementar Salas de Microsoft Teams con Exchange local
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos en un entorno híbrido con Exchange local.
ms.openlocfilehash: 7ab9a582e26db15159677343d9edddd6bd9c45f9
ms.sourcegitcommit: 751035e1d35fc79a6b74955d7c6c46ecea0645e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2019
ms.locfileid: "34082725"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Implementar Salas de Microsoft Teams con Exchange local

Lea este tema para obtener información acerca de cómo implementar Microsoft salones de los equipos en un entorno híbrido con Exchange en local y Microsoft Teams o Skype para profesionales en línea.
  
Si su organización tiene una mezcla de servicios, con algunas hospedado en local y algunas alojado en línea, a continuación, la configuración depende de donde se hospeda cada servicio. En este tema se trata las implementaciones híbridas en salas de equipos de Microsoft con Exchange hospedado localmente. Debido a que hay muchas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todos ellos. El siguiente proceso funcionará para muchas configuraciones. Si el proceso no es adecuado para el programa de instalación, se recomienda que use Windows PowerShell para lograr el mismo resultado final, tal como se describe aquí y para otras opciones de implementación.

Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), una secuencia de comandos que le ayudarán a crear nuevas cuentas de usuario o validar cuentas de recursos existentes que tienen con el fin de ayudar a convertirlas en cuentas de usuario compatibles con salones de los equipos de Microsoft. Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que se va a usar el dispositivo de salas de equipos de Microsoft.
  
## <a name="requirements"></a>Requisitos

Antes de implementar Microsoft salones de los equipos con Exchange local, debe asegurarse de que cumplen los requisitos. Para obtener más información, vea [requisitos de salas de equipos de Microsoft](requirements.md).
  
Si va a implementar Microsoft salones de los equipos con Exchange local, va a usar las herramientas administrativas de Active Directory para agregar una dirección de correo electrónico para su cuenta de dominio local. Esta cuenta se sincronizará con Office 365. Tendrá que hacer lo siguiente:
  
- Crear una cuenta y sincronizarla con Active Directory

- Habilitar el buzón de correo remoto y establecer propiedades

- Asignar una licencia de Office 365.

- Habilitar la cuenta del dispositivo con Skype para Business Server. Para ello, el entorno deberá cumplir con los requisitos previos que se detallan aquí:

  - Debe tener Skype para profesionales Online (Plan 2) o superior en su plan de Office 365. El plan debe admitir la funcionalidad de conferencias.
  
  - - Si necesita Enterprise Voice (telefonía PSTN) con proveedores de servicios de telefonía para salas de equipos de Microsoft necesita Skype para profesionales en línea (planeación de 3).
  
  - - Los usuarios de inquilinos deben tener los buzones de Exchange.
  
  - - Su cuenta de salas de equipos de Microsoft requieren una Skype para profesionales Online (Plan 2) o Skype para licencia empresarial en línea (planeación de 3), pero no requiere una licencia de Exchange Online.

- Asignar un Skype para licencia de servidor empresarial a su cuenta de salas de equipos de Microsoft.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Crear una cuenta y sincronizarla con Active Directory

1. En la herramienta de **equipos y usuarios de Active Directory** , haga clic en la carpeta o unidad organizativa que sus salones de los equipos de Microsoft se crearán cuentas en, haga clic en **nuevo**y, a continuación, haga clic en **usuario**.

2. Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.

3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.

    > [!NOTE]
    > Selección de **la contraseña nunca caduca** es un requisito para Skype para Business Server en salas de equipos de Microsoft. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, debe crear una excepción para cada cuenta de dispositivo de salas de equipos de Microsoft.
  
4. Tras crear la cuenta, ejecute una sincronización de directorios. Una vez finalizada, vaya a la página de los usuarios en el centro de administración de Microsoft 365 y compruebe que la cuenta creada en los pasos anteriores se combinado en línea.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar el buzón de correo remoto y establecer propiedades

1. [Abra el Shell de administración de Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [conectarse a su servidor de Exchange mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. En Exchange PowerShell, crear un buzón de correo para la cuenta (la cuenta de buzón de correo habilitar) ejecutando el siguiente comando:

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Para obtener información de parámetro y detallada sobre la sintaxis, consulte [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. En PowerShell de Exchange, configure las opciones siguientes en el buzón de sala para mejorar la experiencia de reunión:

   - AutomateProcessing: AutoAccept (los organizadores de reuniones reciben la decisión de reserva de sala directamente sin intervención humana: libre = acepte; ocupado = rechazar.)

   - AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la convocatoria de reunión).

   - DeleteComments: $false (mantener el texto del cuerpo del mensaje de convocatorias de reunión entrantes).

   - DeleteSubject: $false (conservar el asunto de convocatorias de reunión entrantes).

   - RemovePrivateProperty: $false (garantiza la marca privada que se envió el organizador de la reunión original permanece tal como se especifica de solicitudes).

   - AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión).

   - AdditionalResponse: "ésta es una sala de reuniones de Skype!" (El texto adicional para agregar a la convocatoria de reunión).

   En este ejemplo se configura estas opciones de configuración en el buzón de sala denominado Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obtener información de parámetro y detallada sobre la sintaxis, vea [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-an-office-365-license"></a>Asignar una licencia de Office 365

1. Conectar con Azure Active Directory. Para obtener información detallada acerca de Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > No se admite [de Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) . 

2. La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Microsoft Teams no funcionará. Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta. Puede usar`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar una lista de SKU disponibles.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. A continuación, puede agregar una licencia mediante la`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Para obtener instrucciones detalladas, consulte [asignar licencias a cuentas de usuario con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Habilitar la cuenta del dispositivo

Skype para PowerShell en línea de negocio se usa para administrar los servicios de Microsoft Teams y Skype para profesionales en línea.

1. Crear una sesión remota de Windows PowerShell desde un PC de la siguiente manera:

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar la cuenta de salas de equipos de Microsoft, ejecute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Si no está seguro de qué valor debe utilizar para el parámetro RegistrarPool en el entorno, puede obtener el valor de un usuario existente con este comando:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Asignar una licencia a su cuenta de salas de equipos de Microsoft

1. Inicie sesión como administrador de inquilinos, abra el Portal de administración de Office 365 y haga clic en la aplicación de administración.
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
3. Haga clic en la cuenta de salas de equipos de Microsoft y, a continuación, haga clic en el icono de lápiz para editar la información de cuenta.
4. Haga clic en **Licencias**.
5. En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial. Debe utilizar una licencia de planeación 3 si desea usar Enterprise Voice en sus salones de los equipos de Microsoft.
6. Haga clic en **Guardar **.

Para la validación, debe utilizar a cualquier cliente para iniciar sesión en esta cuenta.
  
## <a name="see-also"></a>Vea también

[Configurar las cuentas para salas de equipos de Microsoft](room-systems-v2-configure-accounts.md)

[Plan para salas de equipos de Microsoft](skype-room-systems-v2-0.md)
  
[Implementación de salas de equipos de Microsoft](room-systems-v2.md)
  
[Configurar una consola de salas de equipos de Microsoft](console.md)
  
[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

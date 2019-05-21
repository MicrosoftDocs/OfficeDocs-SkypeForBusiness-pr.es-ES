---
title: Implementar Salas de Microsoft Teams con Exchange local
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams en un entorno híbrido con Exchange local.
ms.openlocfilehash: 7e855ece643d3412047b4d01a9250b17f699ac98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288486"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Implementar Salas de Microsoft Teams con Exchange local

Lea este tema para obtener información sobre cómo implementar salas de Microsoft Teams en un entorno híbrido con Exchange local y Microsoft Teams o Skype empresarial online.
  
Si su organización tiene una combinación de servicios, con algunos locales hospedados y alojados en línea, la configuración dependerá de dónde se hospede cada servicio. En este tema se tratan las implementaciones híbridas de salas de Microsoft Teams con Exchange hospedado de forma local. Puesto que existen tantas variantes diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas. El siguiente proceso funciona para muchas configuraciones. Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para obtener el mismo resultado final que se explica aquí, así como para otras opciones de implementación.

Microsoft proporciona [SkypeRoomProvisioningScript. PS1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario compatibles con salas de Microsoft Teams. Si lo prefiere, puede seguir los pasos siguientes para configurar las cuentas que usará el dispositivo de salas de Microsoft Teams.
  
## <a name="requirements"></a>Requisitos

Antes de implementar salas de Microsoft Teams con Exchange local, asegúrese de que cumple con los requisitos. Para obtener más información, consulte [requisitos de salas de Microsoft Teams](requirements.md).
  
Si implementa salas de Microsoft Teams con Exchange local, usará las herramientas administrativas de Active Directory para agregar una dirección de correo electrónico a su cuenta de dominio local. Esta cuenta se sincronizará con Office 365. Tendrá que hacer lo siguiente:
  
- Crear una cuenta y sincronizarla con Active Directory

- Habilitar el buzón de correo remoto y establecer propiedades

- Asignar una licencia de Office 365.

- Habilite la cuenta del dispositivo con Skype empresarial Server. Para ello, el entorno deberá cumplir con los requisitos previos que se detallan aquí:

  - Necesitará tener Skype empresarial online (plan 2) o una versión posterior en el plan 365 de Office. El plan debe admitir la funcionalidad de conferencias.
  
  - - Si necesita Enterprise Voice (telefonía RTC) con proveedores de servicios de telefonía para salas de Microsoft Teams, necesita Skype empresarial online (Plan 3).
  
  - - Los usuarios de inquilinos deben tener buzones de Exchange.
  
  - - Su cuenta de salas de Microsoft Teams necesita una licencia de Skype empresarial online (plan 2) o de Skype empresarial online (Plan 3), pero no requiere una licencia de Exchange Online.

- Asigne una licencia de Skype empresarial Server a su cuenta de salas de Microsoft Teams.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Crear una cuenta y sincronizarla con Active Directory

1. En la herramienta **usuarios y equipos de Active** Directory, haga clic con el botón derecho en la carpeta o unidad organizativa en la que se crearán las cuentas de las salas de Microsoft Teams, haga clic en **nuevo**y, a continuación, haga clic en **usuario**.

2. Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.

3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.

    > [!NOTE]
    > La selección de la **contraseña nunca expira** es un requisito de Skype empresarial Server en las salas de Microsoft Teams. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, tendrá que crear una excepción para cada cuenta de dispositivo de salas de Microsoft Teams.
  
4. Tras crear la cuenta, ejecute una sincronización de directorios. Cuando haya finalizado, vaya a la página usuarios del centro de administración de Microsoft 365 y compruebe que la cuenta creada en los pasos anteriores se ha fusionado en línea.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar el buzón de correo remoto y establecer propiedades

1. [Abra el shell de administración de Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [Conéctese a su servidor de Exchange con PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. En Exchange PowerShell, busque un buzón para la cuenta (para habilitar el buzón de correo) ejecutando el siguiente comando:

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, consulte [enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. En Exchange PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de reunión:

   - AutomateProcessing: AutoAccept (los organizadores de reuniones reciben directamente la decisión de reserva de la sala sin intervención humana: gratis = aceptar; ocupado = rechazar).

   - AddOrganizerToSubject: $false (el organizador de la reunión no se agrega al asunto de la convocatoria de reunión).

   - DeleteComments: $false (mantener el texto en el cuerpo del mensaje de las convocatorias de reunión entrantes).

   - DeleteSubject: $false (mantener el asunto de las convocatorias de reunión entrantes).

   - RemovePrivateProperty: $false (garantiza que la marca privada que envió el organizador de la reunión en la convocatoria de reunión original permanece como se especifica).

   - AddAdditionalResponse: $true (el texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión).

   - AdditionalResponse: "este es un salón de reunión de Skype". (El texto adicional que se agregará a la convocatoria de reunión).

   En este ejemplo se configuran estas opciones de configuración en el buzón de sala denominado Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, consulte [set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-an-office-365-license"></a>Asignar una licencia de Office 365

1. Conéctese a Azure Active Directory. Para obtener más información sobre Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible. 

2. La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Microsoft Teams no funcionarán. Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de dispositivo, lo cual determina qué SKU de licencia están disponibles para su cuenta. Puedes usar`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar una lista de las SKU disponibles.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. A continuación, puede Agregar una licencia mediante el`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).

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

   Para obtener instrucciones detalladas, consulte [asignar licencias a cuentas de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Habilitar la cuenta del dispositivo

Skype empresarial online PowerShell se usa para administrar servicios tanto para Microsoft Teams como para Skype empresarial online.

1. Cree una sesión remota de Windows PowerShell desde un equipo informático de la siguiente manera:

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar la cuenta de salas de Microsoft Teams, ejecute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Si no está seguro de qué valor usar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un usuario existente mediante este comando:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Asignar una licencia a su cuenta de salas de Microsoft Teams

1. Inicie sesión como administrador de inquilinos, abra el portal administrativo de Office 365 y haga clic en la aplicación de administrador.
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
3. Haga clic en la cuenta salas de Microsoft Teams y, a continuación, haga clic en el icono de lápiz para editar la información de la cuenta.
4. Haga clic en **Licencias**.
5. En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial. Tendrá que usar una licencia de Plan 3 Si desea usar la telefonía IP empresarial en sus salas de Microsoft Teams.
6. Haga clic en **Guardar **.

Para la validación, debe poder usar cualquier cliente para iniciar sesión en esta cuenta.
  
## <a name="see-also"></a>Vea también

[Configurar cuentas para salas de Microsoft Teams](room-systems-v2-configure-accounts.md)

[Plan para salas de Microsoft Teams](skype-room-systems-v2-0.md)
  
[Implementar salas de Microsoft Teams](room-systems-v2.md)
  
[Configurar una consola de salas de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

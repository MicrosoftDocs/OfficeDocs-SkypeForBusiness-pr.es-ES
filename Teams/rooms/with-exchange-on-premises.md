---
title: Implementar Salas de Microsoft Teams con Exchange local
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams en un entorno híbrido con Exchange local.
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117358"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Implementar Salas de Microsoft Teams con Exchange local

Lea este tema para obtener información sobre cómo implementar Salas de Microsoft Teams en un entorno híbrido con Exchange local y Microsoft Teams o Skype Empresarial Online.
  
Si su organización tiene una combinación de servicios, con algunos hospedados localmente y otros hospedados en línea, la configuración dependerá de dónde se hospeda cada servicio. En este tema se tratan las implementaciones híbridas para Salas de Microsoft Teams con Exchange hospedadas localmente. Dado que hay muchas variaciones diferentes en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas. El siguiente proceso funcionará para muchas configuraciones. Si el proceso no es adecuado para su configuración, le recomendamos que use Windows PowerShell para lograr el mismo resultado final que se documenta aquí y para otras opciones de implementación.

Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que le ayudará a crear nuevas cuentas de usuario o validar las cuentas de recursos existentes que tiene para ayudarle a convertirlas en cuentas de usuario Salas de Microsoft Teams compatibles. Si lo prefiere, puede seguir los pasos que se indican a continuación para configurar las cuentas que Salas de Microsoft Teams dispositivo usará.
  
## <a name="requirements"></a>Requirements

Antes de implementar Salas de Microsoft Teams con Exchange local, asegúrese de que ha cumplido los requisitos. Para obtener más información, [vea Salas de Microsoft Teams requisitos.](requirements.md)
  
Si va a implementar Salas de Microsoft Teams con Exchange local, va a usar las herramientas administrativas de Active Directory para agregar una dirección de correo electrónico para su cuenta de dominio local. Esta cuenta se sincronizará con Microsoft 365 o Office 365. Tendrá que hacer lo siguiente:
  
- Crear una cuenta y sincronizarla con Active Directory

- Habilitar el buzón de correo remoto y establecer propiedades

- Asigne una Microsoft 365 o Office 365 licencia.

- Habilite la cuenta del dispositivo con Skype Empresarial Server. Para ello, el entorno deberá cumplir con los requisitos previos que se detallan aquí:

  - Necesitará tener Skype Empresarial en línea (Plan 2) o superior en su plan Microsoft 365 o Office 365 plan. El plan debe admitir la funcionalidad de conferencias.
  
  - Si necesita Telefonía IP empresarial (telefonía RTC) con proveedores de servicios de telefonía para Salas de Microsoft Teams necesita Skype Empresarial En línea (Plan 3).

  - Al configurar una cuenta de salón con Microsoft Teams o Skype Empresarial En línea, el número de teléfono debe asignarse antes de que la cuenta se habilite como una cuenta de salón.
  
  - Los usuarios de inquilino deben tener Exchange buzones de correo.
  
  - Su Salas de Microsoft Teams cuenta requiere una licencia de Skype Empresarial Online (Plan 2) o Skype Empresarial Online (Plan 3), pero no requiere una licencia Exchange Online usuario.

- Asigne una Skype Empresarial Server a su Salas de Microsoft Teams cuenta.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Crear una cuenta y sincronizarla con Active Directory

1. En la herramienta Usuarios y equipos de **Active Directory,** haga clic con el botón derecho en la carpeta o unidad organizativa en la que se crearán las cuentas de Salas de Microsoft Teams, haga clic en Nuevo y, a continuación, haga clic en **Usuario.**

2. Escriba el nombre para mostrar del anterior cmdlet en el cuadro **Nombre completo** y el alias en el cuadro **Nombre de inicio de sesión de usuario**. Haga clic en **Siguiente**.

3. Escriba la contraseña de la cuenta. Tendrá que volver a escribirla para verificarla. Asegúrese de que la casilla **La contraseña nunca expira** sea la única opción activada.

    > [!NOTE]
    > Seleccionar **Contraseña nunca expira es** un requisito para Skype Empresarial Server en Salas de Microsoft Teams. Es posible que las reglas de dominio prohíban las contraseñas que no expiran. Si es así, deberá crear una excepción para cada cuenta Salas de Microsoft Teams dispositivo.
  
4. Tras crear la cuenta, ejecute una sincronización de directorios. Cuando haya finalizado, vaya a la página usuarios de su centro de administración de Microsoft 365 y compruebe que la cuenta creada en los pasos anteriores se ha combinado con la en línea.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar el buzón de correo remoto y establecer propiedades

1. [Abra el Exchange de administración](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o conéctese a su servidor Exchange con [PowerShell remoto.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. En Exchange PowerShell, cree un buzón para la cuenta (habilitar el buzón de la cuenta) ejecutando el siguiente comando:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Habilitar buzón.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. En Exchange PowerShell, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de reunión:

   - AutomateProcessing: AutoAccept (Los organizadores de la reunión reciben la decisión de reserva de sala directamente sin intervención humana: gratis = aceptar; ocupado = rechazar).

   - AddOrganizerToSubject: $false (El organizador de la reunión no se agrega al asunto de la solicitud de reunión).

   - DeleteComments: $false (Conservar cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes).

   - DeleteSubject: $false (Mantener el asunto de las solicitudes de reunión entrantes).

   - RemovePrivateProperty: $false (Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado).

   - AddAdditionalResponse: $true (El texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión).

   - AdditionalResponse: "Esta es una sala Skype reunión" (El texto adicional que se agregará a la solicitud de reunión).

   En este ejemplo se configuran estas opciones en el buzón de sala Project-Rigel-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Asignar una Microsoft 365 o Office 365 licencia

1. Conectar Azure Active Directory. Para obtener más información sobre Active Directory, vea [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) no es compatible. 

2. La cuenta del dispositivo debe tener una licencia Microsoft 365 o Office 365, o Exchange y Microsoft Teams no funcionarán. Si tiene la licencia, debe asignar una ubicación de uso a su cuenta de dispositivo, lo que determina qué SKU de licencia están disponibles para su cuenta. Puede usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar una lista de SKU disponibles.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. A continuación, puede agregar una licencia con el `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).

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

   Para obtener instrucciones [detalladas,](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)vea Asignar licencias a cuentas de usuario con Office 365 PowerShell.

### <a name="enable-the-device-account"></a>Habilitar la cuenta del dispositivo

Skype Empresarial PowerShell en línea se usa para administrar servicios para Microsoft Teams y Skype Empresarial Online.

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

2. Obtener la dirección SIP de la cuenta:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. **Opcional.** Si desea asignar un número de teléfono a la cuenta, la operación debe realizarse en este momento. Si desea asignar un número de teléfono de enrutamiento directo:

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    Si va a asignar un número de teléfono proporcionado por Microsoft, use el cmdlet siguiente después de haber aprovisionado al usuario con una licencia de Plan de llamadas:
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. Para habilitar su Salas de Microsoft Teams cuenta, ejecute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Si no está seguro del valor que debe usar para el parámetro RegistrarPool en su entorno, puede obtener el valor de un usuario existente con este comando:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Asignar una licencia a su Salas de Microsoft Teams cuenta

1. Inicie sesión como administrador de inquilinos, abra el Microsoft 365 de administración y haga clic en la aplicación Administrador.
2. Haga clic en **Usuarios y grupos** y después haga clic en **Agregar usuarios, restablecer contraseñas, y más**.
3. Haga clic en Salas de Microsoft Teams cuenta y, a continuación, haga clic en el icono del lápiz para editar la información de la cuenta.
4. Haga clic en **Licencias**.
5. En **Asignar licencias**, seleccione Skype Empresarial (plan 2) o Skype Empresarial (plan 3), según sus requisitos de licencia y de telefonía IP empresarial. Tendrá que usar una licencia de Plan 3 si desea usar Telefonía IP empresarial en su Salas de Microsoft Teams.
6. Haga clic en **Guardar**.

Para la validación, debería poder usar cualquier cliente para iniciar sesión en esta cuenta.
  
## <a name="related-topics"></a>Temas relacionados

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)
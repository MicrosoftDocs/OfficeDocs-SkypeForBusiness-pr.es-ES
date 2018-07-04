---
title: Implementación de equipos de Microsoft para el concentrador de superficie
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Configuración de administración para Microsoft Teams para concentrador de superficie.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192183"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Implementación de equipos de Microsoft para el concentrador de superficie
======================================

Antes de implementar Microsoft Teams Microsoft Surface concentrador, asegúrese de que haya cumplido con el hardware, sistema operativo y otros requisitos. Para obtener más información, consulte la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/en-us/surface-hub/).

## <a name="set-up-user-accounts"></a>Configurar las cuentas de usuario
 
Para configurar las cuentas de usuario que se pueden usar con los equipos de superficie de concentradores, crear la cuenta del dispositivo, como lo haría para compatibilidad con Skype para la empresa. La cuenta del dispositivo debe tener la autenticación multifactor deshabilitada (para permitir el inicio de sesión automático) para los siguientes servicios dependientes de los equipos en Office 365:  
- Exchange 
- SharePoint 
- Aplicaciones de Office 

## <a name="add-a-device-account"></a>Agregar una cuenta de dispositivo 

1\. Iniciar una sesión remota de Windows PowerShell en un PC y conectarse a Exchange. Asegúrese de que tiene los permisos correctos establecer ejecutar los cmdlets asociados. Estos son algunos ejemplos de cmdlets que puede utilizar y modificar en su entorno.

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2\. Después de establecer una sesión, deberá crear un nuevo buzón de correo y habilitarlo como RoomMailboxAccount o bien, cambiar la configuración de un buzón de correo existente. Esto le permitirá la cuenta autenticar a los equipos.

Si va a cambiar un buzón de recursos existente:

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

Si va a crear un buzón de recursos nuevo:

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3\. Para mejorar la experiencia de la reunión, es necesario configurar diversas propiedades de Exchange en la cuenta del dispositivo. Si desea ver qué propiedades hay que configurar, consulte la sección sobre propiedades de Exchange.

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

4\. Tendrá que conectarse a Azure Active Directory para aplicar algunas de las configuraciones de la cuenta. Para conectarse a Azure AD, ejecute el siguiente cmdlet:

```
Connect-MsolService -Credential $cred
```

5\. 	Si no desea que expire la contraseña, ejecute el cmdlet Set-MsolUser con la opción PasswordNeverExpires como sigue:   

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

También puede configurar un número de teléfono para la sala de la siguiente manera:

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

6\. La cuenta del dispositivo debe tener una licencia válida de Office 365 o Exchange y Skype para la empresa no funcionará. Si dispone de la licencia, debe asignar una ubicación de uso para su cuenta de dispositivo: Esto determina qué SKU de las licencias están disponibles para su cuenta. Puede usar Get-MsolAccountSku para recuperar una lista de SKU disponibles para el inquilino de Office 365, como se indica a continuación:
 
```
Get-MsolAccountSku
```

A continuación, puede agregar una licencia mediante el cmdlet Set-MsolUserLicense. En este caso, $strLicense es el código de SKU que ve (por ejemplo, contoso:STANDARDPACK).

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

7\. A continuación, tiene que habilitar la cuenta del dispositivo con los equipos de superficie de concentrador. Asegúrese de que su entorno cumple los requisitos definidos en la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/en-us/surface-hub/).

Iniciar una sesión remota de Windows PowerShell de manera (asegúrese de instalar Skype para componentes de PowerShell en línea de negocio):

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

A continuación, habilitar sus equipos para la cuenta de concentrador de superficie ejecutando el siguiente cmdlet:

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

Obtener la información de RegistrarPool de la nueva cuenta de usuario que se va al programa de instalación, tal como se muestra en este ejemplo:

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> No se pueden crear nuevas cuentas de usuario en el mismo grupo de registrador como cuentas de usuario existentes en el inquilino. El comando anterior se evitará que los errores en el programa de instalación de cuenta debido a esta situación. 

Una vez haya completado los pasos anteriores para habilitar los equipos de la cuenta de concentrador de superficie, debe asignar una licencia para el dispositivo de v2 de concentrador de superficie. Uso del portal administrativo de Office 365, asignar los equipos de una licencia de concentrador de superficie para el dispositivo.

### <a name="assign-a-license-to-the-account"></a>Asignar una licencia a la cuenta

1. Inicie sesión como administrador de inquilinos, abra el centro de administración de Office 365 y haga clic en la aplicación de administración.
2. Haga clic en **usuarios y grupos**y, a continuación, haga clic en **Agregar usuarios, restablecer contraseñas y mucho más**.
3. Seleccione los equipos de cuenta de superficie concentrador y, a continuación, haga clic en o puntee en el icono de lápiz, que significa que editar.
4. Haga clic en la opción de **licencias** .
5. En la sección **asignación de licencias** , es necesario seleccionar el plan, dependiendo de su licencia.
6. Haga clic en **Guardar** para completar la tarea.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Instalación de los equipos para exponer concentrador desde el almacén de Microsoft 

Estas instrucciones incluyen las soluciones alternativas actuales para la instalación de los equipos de concentrador de superficie de Microsoft Store. 
 
1. Inicie el almacén de Windows:<br>
   a. Puntee en **Iniciar** > **todas las aplicaciones** > **configuración**.<br> b. Puntee en **dispositivo de concentrador de superficie de cuenta, administración**.<br>
   c. En la izquierda, puntee en la ficha **aplicaciones y características** .<br> d. En la derecha, puntee en el botón **Abrir almacén** . 
2. De Microsoft Store, busque *Los equipos de Microsoft*. Se mostrarán los **Equipos de Microsoft para el concentrador de superficie (vista previa)** . Puntee en el botón **obtener la aplicación** para instalar.  
3. Una vez finalizada la instalación, reinicie el concentrador de superficie. 
4. Una vez reiniciado el concentrador de superficie, debe ser capaz de iniciar la aplicación de los equipos desde el menú **Inicio** y unirse a una reunión desde el calendario. 

## <a name="make-teams-the-default-vtc-application"></a>Hacer que los equipos de la aplicación de VTC predeterminada

Los equipos pueden ser configurados para que sea la aplicación predeterminada de VTC en lugar de Skype para la empresa. Una directiva de Mobile Device Management (MDM) debe aplicarse en el dispositivo del concentrador de superficie. 
 
Hay dos opciones para configurar las directivas de MDM: 

- Si tiene una directiva configurada, agregarlo a través de la aplicación de administración de dispositivos. 
- Si no tiene configurada una directiva de remota, tenemos un archivo de paquete suministrados que se puede cargar en una clave USB.

### <a name="device-management-configuration"></a>Configuración de administración de dispositivos

El siguiente es un ejemplo de adición de una directiva MDM configurada desde una entidad de certificación MDM central. Si se trata de la red corporativa, puede usar las siguientes instrucciones textual, incluida la cuenta de usuario. 
 
1. En la sección **Administración de dispositivos** , puntee en **+**.<br>
   Se abrirá el cuadro de diálogo **Conectar a trabajar o escuela** . 
2. Escriba la dirección de correo electrónico de la directiva y la contraseña cuando se le solicite.<br>
   **Nota:**  Hay un error en el sistema operativo que no actualice automáticamente la interfaz de usuario después de haber especificado su cuenta de administración de dispositivos. Debe cerrar y volver a abrir Configuración para poder ver la cuenta que aparece. 
3. Tardará unos minutos sincronizar la configuración de directiva MDM. Si desea forzar una sincronización, puntee en el botón **cuenta MDM** y, a continuación, puntee en el botón **Info** . Este modo se abrirá la ventana de información donde, a continuación, puntee en **sincronización**. 
4. Para comprobar que tiene lo que necesita, puede comprobar el registro. Debería ver dos claves en **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**. <br><br>
   El valor DWORD **VtcAppMeetingHandlingMode** indica que los equipos es la aplicación predeterminada. Se reconocen los siguientes valores. <br><br>
    |Número | Valor   |
    |-------|---------|
    |0      | SkypePreferred            |
    |1      | VtcPreferred (equipos)      |
    |2      | VtcExclusive (sólo en los equipos) |

    El **VtcCallAppPackageId** es el nombre del paquete de los equipos instalado. Si esto no se muestra, asegúrese de que ha instalado el paquete de los equipos y volver a sincronizar. 
 
### <a name="configure-mdm-via-usb-key"></a>Configurar MDM a través de la clave USB 
 
Los paquetes se pueden encontrar en esta [página de descarga](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Elija la adecuada para el paquete que va a instalar y cópielo a una clave USB. El archivo .ppkg correcto para usar depende del paquete de los equipos que se ha instalado desde el almacén y la directiva que desea aplicar (Skype exclusivo, Skype preferido, los equipos preferidos, exclusiva de los equipos). 
 
1. Adjunta la clave USB en el dispositivo del concentrador de superficie. 
2. Abra la aplicación de **configuración** en un dispositivo concentrador de superficie. 
3. Abra **administración de cuentas de dispositivo concentrador expuesta**.
4. Abra **administración de dispositivos**. 
5. Haga clic en **Agregar o quitar un paquete de aprovisionamiento**. 
6. Haga clic en **Agregar paquete**.
7. Seleccione la opción de **Medios extraíble** en el menú desplegable. 
8. Agregue el **Allowbuildspreview.ppkg**y, a continuación, seleccione el paquete de concentrador de superficie que desee agregar. 
9. Reinicie el dispositivo concentrador de superficie. 

> [!NOTE]
> Si no se admite su dispositivo o dispositivos de su organización parte del programa de información confidencial de Windows y se encuentra en países cubiertos por el Reglamento General de protección de datos (GDPR) (o ha cambiado manualmente la configuración de telemetría en básico), a continuación, debe volver a comprobar que se ha permitido telemetría completo antes de unirse a la información confidencial de programa. GDPR cambiar el comportamiento predeterminado de los dispositivos de concentradores de la superficie de la UE para establecer telemetría en básico.
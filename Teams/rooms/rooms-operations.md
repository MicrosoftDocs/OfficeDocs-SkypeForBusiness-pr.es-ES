---
title: Salas de Microsoft Teams mantenimiento y operaciones
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Obtenga información sobre la administración de Salas de Microsoft Teams.
ms.openlocfilehash: d57f84aa07c90b6a75693f0cbf739402a6e90a4c
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125475"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Salas de Microsoft Teams mantenimiento y operaciones
 
 
Salas de Microsoft Teams es la solución de conferencias de Microsoft diseñada para transformar su sala de reuniones en una experiencia enriquecida y colaborativa. Los usuarios disfrutarán de su familiar Microsoft Teams o interfaz de Skype Empresarial y los administradores de TI apreciarán una aplicación de Windows 10 Salas de Teams fácil de implementar y administrar. Salas de Microsoft Teams está diseñado para aprovechar el equipo existente para facilitar la instalación y llevar Microsoft Teams o Skype Empresarial a la sala de reuniones.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Recopilación de registros en Salas de Microsoft Teams
<a name="Logs"> </a>

Para recopilar registros en Teams centro de administración, vaya a **Teams dispositivos > Salas de Teams en Windows**. Seleccione el nombre para mostrar del dispositivo para el que desea registros. En el panel superior, selecciona "Descargar registros de dispositivos". Una vez confirmado, los registros estarán listos para su descarga en la pestaña Historial pasados unos minutos.

También puede usar PowerShell para recopilar registros. Debe invocar el script de colección de registros que se incluye con la aplicación de Salas de Microsoft Teams. En [el modo de administración](rooms-operations.md), inicia un símbolo del sistema con privilegios elevados y ejecuta el siguiente comando:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Los registros se enviarán como un archivo ZIP en c:\rigel.

### <a name="managing-disk-space"></a>Administrar el espacio en disco
<a name="Space"> </a>

Los registros descargados en el dispositivo pueden ocupar espacio en disco. Si los registros no se limpian periódicamente, pueden interferir con la funcionalidad normal de la sala. Salas de Teams elimina los registros descargados después de 30 días. Los administradores de TI pueden invalidar la limpieza de registro mediante la configuración del registro del dispositivo.

|Setting|Permite|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\PPI\SkypeSettings\LogCleanupAgeThreshold  <br/> |Limpia los registros después de 30 días.  <br/> |
  
## <a name="front-of-room-display-settings"></a>Configuración frontal de la pantalla de la sala
<a name="Display"> </a>

Configure las opciones de las pantallas frontales de la sala para admitir el Control de electrónica del consumidor (CEC) o habilitar el modo PC.
  
Si deseas que una pantalla frontal de la sala cambie automáticamente a Salas de Teams cuando se reactiva del modo de espera, deben cumplirse ciertas condiciones. Esta característica es opcional, pero es compatible con Salas de Microsoft Teams software, siempre que el hardware subyacente admita la característica. Un televisor de consumidor que se usa como frente de la pantalla de la habitación debe admitir la característica de Control de electrónica de consumidor (CEC) de HDMI.  Dependiendo de la base o consola seleccionada (que podría no admitir CEC, consulte la documentación de soporte técnico del fabricante), un controlador como un [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron puede ser necesario para habilitar el comportamiento deseado.

### <a name="scale-and-resolution"></a>Escala y resolución

Para obtener Salas de Teams experiencia diseñada, las pantallas frontales deben cumplir los requisitos de resolución y escala.

Para establecer la escala y la resolución de la pantalla frontal de salas de forma remota, consulte [Administrar una configuración de consola de Salas de Microsoft Teams de forma remota con un archivo de configuración XML](xml-config-file.md#set-front-of-room-scale-and-resolution).

Para establecer la escala y la resolución manualmente en la configuración del administrador del salón de Teams:

1. En la sala de Teams, cambiar al [modo de administración](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. Seleccione el icono de inicio. A continuación, **Configuración > pantalla de > del sistema**

3. Ve a **Escala y diseño**, **cambia el tamaño del texto, las aplicaciones y otros elementos** y establece el ajuste de escala en el 100 %.

4. Establece la resolución de pantalla en 1080p. Si tienes monitores duales, establece la escala y la resolución de ambas pantallas.

5. A continuación, selecciona el icono inicio y escribe **Símbolo del sistema**. Seleccione **Ejecutar como administrador**.

6. Ejecute el siguiente comando:

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```

7. Reinicia el dispositivo.
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Restablecimiento Salas de Microsoft Teams (restauración de fábrica)
<a name="Reset"> </a>

Si Salas de Microsoft Teams no se ejecuta correctamente, realizar un restablecimiento de fábrica puede ser de ayuda. Para ello, usa la [Microsoft Teams Herramienta de recuperación de salas](recovery-tool.md) y sigue las instrucciones de restauración de fábrica.

> [!NOTE]
> Hay un problema conocido en el que la Salas de Microsoft Teams puede dejar de usarse si la opción **Mantener mis archivos: quita aplicaciones y opciones de configuración, pero mantiene sus archivos personales** seleccionados durante el proceso de Windows Restablecer. *No* use esta opción.
  
## <a name="supported-remote-options"></a>Opciones remotas admitidas
<a name="RemoteOptions"> </a>

La tabla siguiente resume las operaciones remotas posibles y los métodos que se pueden utilizar para llevarlas a cabo.
  

|Grupo de trabajo |No unido a dominio|Unido a dominio|
|:-----|:-----|:-----|
|Reinicio  <br/> |centro de administración de Teams  <br/> Escritorio remoto  <br/> PowerShell remoto  <br/> | <br/>Escritorio remoto (requiere una configuración adicional)  <br/> PowerShell remoto (requiere configuración adicional)  <br/> Configuration Manager  <br/> |
|Actualizar SO  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Actualización de aplicaciones  <br/> |Tienda Windows  <br/> |Tienda Windows  <br/> Configuration Manager  <br/> |
|Configuración de la cuenta  <br/> |centro de administración de Teams  <br/> |centro de administración de Teams  <br/> |
|Registros de acceso  <br/> |centro de administración de Teams  <br/> Powershell  <br/> |centro de administración de Teams <br/> Powershell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configuración de directiva de grupo para Salas de Microsoft Teams
<a name="GroupPolicy"> </a>

Esta sección trata sobre la configuración del sistema que Salas de Microsoft Teams depende de que funcione correctamente. 

La unión de Salas de Teams a un dominio de Active Directory ofrece las siguientes ventajas:

- La Salas de Teams de unión a dominios le permite conceder derechos administrativos a los usuarios y grupos del dominio. Al hacer esto, no tendrá que acordarse de la contraseña de la cuenta de administrador de nivel de máquina local.

- Puede implementar Windows configuración de calidad de servicio en Salas de Teams.

- Si usa Skype Empresarial, la unión a un dominio de la Salas de Teams automatiza la importación de la cadena de certificados raíz privada de su organización.

Al unir Salas de Teams a un dominio, es necesario que cree una unidad organizativa (UO) independiente, de modo que pueda proporcionar exclusiones de objetos de directiva de grupo (GPO) a la unidad organizativa donde residen todos los objetos Salas de Teams. Deshabilite toda la herencia de GPO para que la configuración de directiva de grupo no compatible no se aplique a Salas de Teams. Cree objetos de máquina en la unidad organizativa antes de unir Salas de Teams al dominio para garantizar que no se apliquen las directivas de grupo aplicadas a la unidad organizativa de los equipos predeterminados.

> [!NOTE]
> Incluso si crea una unidad organizativa independiente y bloquea la herencia, hay algunas directivas de grupo que podrían causar problemas si tienen sin invalidación establecida. Una directiva de grupo con el conjunto Sin invalidación supera una unidad organizativa con el conjunto de herencia de directivas de bloqueo.

Muchas organizaciones tienen los siguientes GPO, que afectan a Salas de Teams funcionalidad. Asegúrese de invalidar o bloquear la herencia de estos:

  - Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)
  - Directivas relacionadas de administración de energía
  - Requerir pasos de autenticación adicionales
  - Negar el acceso a las unidades locales
  - Avisar a los usuarios de conexiones de red lentas
  - Iniciar un programa determinado en el inicio de sesión
  - Crear otra cuenta de usuario de dominio en todas las máquinas con unión a dominio.
  - Insertar Windows Update en Salas de Teams

Al unir Salas de Microsoft Teams a un dominio, asegúrese de que las directivas de grupo no invaliden la configuración de la tabla siguiente.

|Setting|Permite|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permite que Salas de Microsoft Teams arranque  <br/> |
|Administración de energía:\> en CA, apaga la pantalla después de 10 minutos  <br/> Administración de energía:\> en LA AC, nunca ponga el sistema en suspensión  <br/> |Permite que Salas de Microsoft Teams desactive las pantallas conectadas y se reactive automáticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local. Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado. Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.   <br/> |Permite que la cuenta de Skype siempre inicie sesión  <br/> |

> [!NOTE]
> Cuando Salas de Microsoft Teams es compatible con la siguiente versión de Windows 10 sistema operativo, Salas de Teams se actualiza automáticamente a la siguiente versión a través de Windows Update. Salas de Microsoft Teams no deben actualizarse a la siguiente versión de Windows 10 manualmente o mediante la habilitación de directivas de grupo de Windows Update para empresas (WUFB) "Seleccione el nivel de preparación de Windows para las actualizaciones que desea recibir" y "Seleccionar cuándo se reciben las versiones preliminares y las actualizaciones de características" a través de GPO. Salas de Teams con estas directivas de grupo habilitadas se sabe que tiene problemas con las actualizaciones del sistema operativo Windows 10.

## <a name="remote-management-using-powershell"></a>Administración remota con PowerShell
<a name="RemotePS"> </a>

Puede realizar las siguientes operaciones de administración de forma remota mediante PowerShell (consulte la tabla siguiente para obtener ejemplos de script):
  
- Obtener dispositivos conectados
- Obtener estado de la aplicación
- Obtener información del sistema
- Reiniciar el sistema
- Recuperar registros
- Transferir archivos (requiere un Salas de Microsoft Teams unido a un dominio)
    
> [!NOTE]
> Esta funcionalidad está desactivada de manera predeterminada. Debe habilitar PowerShell remoto para su entorno en el sistema Salas de Microsoft Teams para realizar las siguientes operaciones. Consulte la documentación sobre **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** para obtener información sobre cómo habilitar PowerShell remoto.
  
Por ejemplo, puede habilitar PowerShell remoto de esta manera:
  
1. Inicie sesión como administrador en un dispositivo Salas de Microsoft Teams.
2. Abra un símbolo del sistema con privilegios elevados de PowerShell.
3. Escriba el siguiente comando: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Abra la directiva de seguridad local y agregue el grupo de seguridad *Administradores* a **Directivas** >  **de seguridad Configuración** >  **LocalA assignment** >  **RightsUserAccess este equipo desde la red**.

Para ejecutar una operación de administración:
  
1. Inicie sesión en un equipo con credenciales de cuenta que tengan permiso para ejecutar comandos de PowerShell en un dispositivo Salas de Microsoft Teams.
2. Abra un símbolo del sistema de PowerShell normal en el equipo.
3. Copie el texto del comando de la tabla siguiente y péguelo en el símbolo del sistema.
4. Reemplace  `<Device fqdn>` los campos por valores FQDN apropiados para su entorno.
5. Reemplace  *\<path\>*  por el nombre de archivo y la ruta de acceso local del archivo de configuración SkypeSettings.xml maestro (o imagen de tema).
    
Para obtener dispositivos conectados
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Obtener estado de la aplicación
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

Obtener información del sistema
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Reiniciar el sistema
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Recuperar registros
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Insertar un archivo de configuración XML (o gráfico de tema)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Actualizaciones de software
<a name="SWupdate"> </a>

De forma predeterminada, Salas de Microsoft Teams intenta conectarse a la Tienda Windows para obtener la última versión del software de Salas de Microsoft Teams. Por lo tanto, Salas de Teams requiere acceso regular a Internet. Antes de ponerte en contacto con Microsoft con problemas de soporte técnico, asegúrate de que Salas de Microsoft Teams se carga con la versión más reciente de la aplicación.
  
Salas de Microsoft Teams se conecta a Windows Update para recuperar las actualizaciones de firmware del sistema operativo y dispositivos periféricos. También se conecta a la Microsoft Store para recuperar las actualizaciones de la aplicación.

Si necesitas administrar manualmente las actualizaciones de aplicaciones, pero no puedes seguir el procedimiento normal de [Microsoft Store para Empresas](https://businessstore.microsoft.com/store) [Distribuir aplicaciones sin conexión](/microsoft-store/distribute-offline-apps), puedes adquirir Salas de Teams paquetes de actualización para realizar actualizaciones de aplicaciones en sistemas operativos compatibles. Es posible que la versión de actualización no coincida con la versión de Store y que no coincida siempre con la compilación disponible más reciente. Consulta [Actualizar manualmente un dispositivo Salas de Microsoft Teams](manual-update.md) para obtener más información.

## <a name="admin-mode-and-device-management"></a>Modo de administrador y administración de dispositivos
<a name="AdminMode"> </a>

Algunas funciones de administración, como instalar manualmente un certificado de ENTIDAD de certificación privada, requieren la colocación de Salas de Teams en modo de administración. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Cambiar al modo de administración y volver cuando se ejecuta la aplicación Salas de Microsoft Teams

1. Cuelgue las llamadas en curso y vuelva a la pantalla principal.
2. Selecciona el icono de engranaje y abre el menú (las opciones son **Configuración**, **Accesibilidad** y **Reiniciar dispositivo**).
3. Seleccione **Configuración**.
4. Escriba la contraseña de administrador. Se abrirá la pantalla Configuración.  Si el dispositivo no está unido a un dominio, se usará la cuenta administrativa local (nombre de usuario "Administrador") de forma predeterminada. La contraseña predeterminada para esta cuenta es 'sfb'. Cambie esta contraseña tan pronto como sea posible. Si el equipo está unido a un dominio, puede iniciar sesión con una cuenta de dominio con los privilegios adecuados.
5. Seleccione **Windows Configuración** en la columna izquierda.
6. Inicie sesión en el escritorio con sus credenciales de administrador. Tendrás los privilegios necesarios para administrar el dispositivo.
7. Realice las tareas de administración que sean necesarias.
8.  Reinicia el equipo cuando hayas terminado.
    
La consola volverá a su modo de funcionamiento normal. El siguiente procedimiento requiere que agregue un teclado al dispositivo si no hay ninguno todavía.  
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Cambiar al modo de administración y volver atrás cuando se bloquea la aplicación Salas de Microsoft Teams

1. Presione rápidamente la tecla Windows cinco veces. De este modo accederá a la pantalla de inicio de sesión de Windows.  
2. Inicie sesión en el escritorio con sus credenciales de administrador.
3. Realice las tareas de administración que sean necesarias.
4. Reinicia el equipo cuando hayas terminado.

    > [!NOTE]
    > Este método no cierra la sesión del usuario de Skype o finaliza correctamente la aplicación, pero la usarías si la aplicación no respondía y el otro método no estaba disponible. 

   La consola se reinicia en su modo de funcionamiento normal, ejecutando la aplicación Salas de Microsoft Teams. Puede quitar el teclado si ha conectado uno para completar este procedimiento.
   ## <a name="troubleshooting-tips"></a>Sugerencias para la solución de problemas
   <a name="TS"> </a>

- Es posible que las invitaciones a reuniones no aparezcan cuando se envían a través de los límites del dominio (por ejemplo, entre dos empresas). En estos casos, los administradores de TI deben decidir si permitir que los usuarios externos programen una reunión. Consulte el artículo de la Exchange cmdlet de PowerShell [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), específicamente el parámetro 'ProcessExternalMeetingMessages'.
- Salas de Microsoft Teams no admite Exchange redirecciones de Detección automática a través de Exchange 2010.
- En general, es recomendable que los administradores de TI deshabiliten los puntos de conexión de audio que no quieran usar.
- En el caso de que se muestre una imagen reflejada en la vista previa de la sala, el administrador de TI puede corregirlo activando la energía de la cámara o volteando la orientación de la imagen con la configuración de la cámara.
- Ha habido casos de pérdida de acceso táctil a la consola. En estos casos, el problema a veces se resuelve reiniciando Salas de Teams.
- Ha habido casos de pérdida de audio local al conectar un PC a la consola mediante una transmisión integrada. En esos casos, el problema de reproducción de audio local se puede resolver reiniciando el PC.

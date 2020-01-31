---
title: Mantenimiento y operaciones de salas de Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Lea este tema para obtener información sobre la administración de salas de Microsoft Teams, la nueva generación de sistemas de salas de Skype.
ms.openlocfilehash: 0eb68e74368a9ae4463ab5f6a9721a844b151152
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628666"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Mantenimiento y operaciones de salas de Microsoft Teams 
 
Lea este tema para obtener información sobre la administración de salas de Microsoft Teams, la nueva generación de sistemas de salas de Skype.
  
Salas de Microsoft Teams es la solución de conferencias más reciente de Microsoft diseñada para transformar su sala de reuniones en una experiencia enriquecida y colaborativa. Los usuarios disfrutarán de una interfaz familiar de Microsoft Teams o Skype empresarial, y los administradores de ti apreciarán una aplicación de reunión de Skype de Windows 10 fácil de implementar y administrar. Salas de Microsoft Teams se ha diseñado para aprovechar los equipos existentes, como los paneles LCD, y así facilitar la instalación de Microsoft Teams o Skype empresarial en la sala de reuniones.
  
Con la configuración adicional, la administración remota puede usar Microsoft Azure monitor, como se describe en [planear la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-plan.md), [implementar la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-deploy.md)y [administrar dispositivos de salas de Microsoft Teams con Azure monitor](azure-monitor-deploy.md). También puede [administrar la configuración de la consola de salones de Microsoft Teams de forma remota con un archivo de configuración XML](xml-config-file.md), lo que incluye aplicar un tema de presentación personalizado. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Recopilar registros en salas de Microsoft Teams
<a name="Logs"> </a>

Para recopilar registros, debe invocar el script de la colección de registros que se incluye con la aplicación salas de Microsoft Teams. En el modo de administración, inicie un símbolo del sistema con privilegios elevados y emita el siguiente comando:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Los registros se mostrarán como un archivo ZIP en c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Configuración de la pantalla frontal de la sala
<a name="Display"> </a>

Configure la pantalla frontal de la sala en modo Extendido. De esta manera, se asegurará de que la interfaz de usuario de la consola no esté duplicada en la pantalla al encender la pantalla.
  
> [!NOTE]
> Si desea que la pantalla frontal de la sala de espera cambie automáticamente a una fuente de video activa (como una consola de MTR) cuando el origen se reactiva al modo de espera, deben cumplirse ciertas condiciones. Esta característica es opcional pero es compatible con el software de las salas de Microsoft Teams, siempre que el hardware subyacente admita esta característica. Un televisor de consumo que se usa como parte frontal de la presentación de la sala debe admitir la característica control de electrónica de consumo (CEC) de HDMI.  Según el Dock o la consola seleccionados (que podrían no admitir CEC, consulte la documentación de asistencia del fabricante), es posible que se necesite un controlador como, por ejemplo, [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron para habilitar el comportamiento deseado. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Restablecimiento de las salas de Microsoft Teams (restauración de fábrica)
<a name="Reset"> </a>

Si las salas de Microsoft Teams no se ejecutan correctamente, la realización de un restablecimiento de fábrica puede ayudar. Para ello, use la [herramienta de recuperación de salones de Microsoft Teams](recovery-tool.md) y siga las instrucciones de restauración de fábrica.

> [!NOTE]
> Existe un problema conocido por el que las salas de Microsoft Teams pueden quedar inutilizables si la opción **mantener mis archivos: quita las aplicaciones y la configuración, pero mantiene su opción de archivos personales** está seleccionada durante el proceso de restablecimiento de Windows. *No* use esta opción.
  
## <a name="supported-remote-options"></a>Opciones remotas admitidas
<a name="RemoteOptions"> </a>

La tabla siguiente resume las operaciones remotas posibles y los métodos que se pueden utilizar para llevarlas a cabo.
  

|Grupo de trabajo |No unido a dominio|Unido a dominio|
|:-----|:-----|:-----|
|Reinicio  <br/> |Escritorio remoto  <br/> Powershell remoto  <br/> |Escritorio remoto (requiere una configuración adicional)  <br/> PowerShell remoto (requiere una configuración adicional)  <br/> Configuration Manager  <br/> |
|Actualizar SO  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Actualización de aplicaciones  <br/> |Tienda Windows  <br/> |Tienda Windows  <br/> Configuration Manager  <br/> |
|Configuración de cuenta de Skype  <br/> |No se admite actualmente  <br/> |No se admite actualmente  <br/> |
|Registros de acceso  <br/> |No se admite actualmente  <br/> |No se admite actualmente  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configuración de directivas de grupo para salas de Microsoft Teams
<a name="GroupPolicy"> </a>

En esta sección se describe la configuración del sistema de donde depende Microsoft Teams Rooms para funcionar correctamente. Al unir salas de Microsoft Teams a un dominio, asegúrese de que la Directiva de grupo no invalide la configuración de la tabla siguiente.
  

|Configuración|Posible|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permite arrancar las salas de Microsoft Teams  <br/> |
|Administración de energía\> : on AC, apagar la pantalla después de 10 minutos  <br/> Administración de energía\> : on AC, no poner el sistema en suspensión  <br/> |Permite que las salas de Microsoft Teams desactiven las pantallas adjuntas y se reactiven automáticamente.  <br/> |
|net accounts /maxpwage:unlimited  <br/> O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local. Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado. Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.  <br/> |Permite que la cuenta de Skype siempre inicie sesión  <br/> |
   
La transferencia de archivos mediante directivas de grupo se trata en [configurar un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).

> [!NOTE]
> Si el dispositivo de salas de Microsoft Teams es compatible con la siguiente versión del sistema operativo Windows 10, el dispositivo se actualizará automáticamente a la siguiente versión a través de Windows Update. Las salas de Microsoft Teams no se deben actualizar de forma manual a la siguiente versión de Windows 10 o mediante la habilitación de directivas de grupo de Windows Update para empresas (WUFB) "Seleccione el nivel de disponibilidad de Windows para las actualizaciones que desea recibir" y "seleccione Cuándo se preparan las compilaciones y Se reciben actualizaciones de características "a través de GPO. Se sabe que un dispositivo con estas directivas de grupo se encuentra con problemas con la aplicación de Microsoft Team Rooms con la actualización del sistema operativo Windows 10.

## <a name="remote-management-using-powershell"></a>Administración remota con PowerShell
<a name="RemotePS"> </a>

Puede realizar las siguientes operaciones de administración de forma remota con PowerShell (consulte la tabla siguiente para ver ejemplos de scripts):
  
- Obtener dispositivos conectados
- Obtener estado de la aplicación
- Obtener información del sistema
- Reiniciar el sistema
- Recuperar registros
- Transferir archivos (requiere un dominio unido a salas de Microsoft Teams)
    
> [!NOTE]
> Esta funcionalidad está desactivada de manera predeterminada. Debe habilitar PowerShell remoto para su entorno en el sistema Microsoft Teams Rooms para realizar las siguientes acciones. Para obtener más información sobre cómo habilitar PowerShell remoto, consulte la documentación de **[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** .
  
Por ejemplo, puede habilitar PowerShell remoto de esta manera:
  
1. Inicie sesión como administrador en un dispositivo de salas de Microsoft Teams.
2. Abra un símbolo del sistema de PowerShell con privilegios elevados.
3. Escriba el siguiente comando: Enable-PSRemoting -force

Para ejecutar una operación de administración:
  
1. Inicie sesión en un equipo PC con credenciales de cuenta que tengan permiso para ejecutar comandos de PowerShell en un dispositivo de salas de Microsoft Teams.
2. Abra un símbolo del sistema de PowerShell normal en el equipo.
3. Copie el texto del comando de la tabla siguiente y péguelo en el símbolo del sistema.
4. Reemplace `<Device fqdn>` los campos con valores FQDN apropiados para su entorno.
5. Reemplazar * \<path\> * con el nombre de archivo y la ruta de acceso local del archivo de configuración Master SkypeSettings. XML (o la imagen del tema).
    
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

Insertar un archivo de configuración XML (o un gráfico de tema)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Actualizaciones de software
<a name="SWupdate"> </a>

De forma predeterminada, Microsoft Teams Rooms intenta conectarse a la tienda Windows para obtener la versión más reciente del software de las salas de Microsoft Teams, por lo que el dispositivo necesitará acceso normal a Internet. Antes de ponerse en contacto con Microsoft para obtener problemas de soporte técnico, asegúrese de que el dispositivo salas de Microsoft Teams se ha cargado con la última versión de la aplicación.
  
De forma predeterminada, Microsoft Teams Rooms se conecta a Windows Update para recuperar el sistema operativo y las actualizaciones de firmware de dispositivos periféricos USB y las instala fuera de las horas laborales configuradas. Para configurar horarios comerciales, puede iniciar sesión en la cuenta de administrador y ejecutar la aplicación Configuración.
  
Si desea administrar las actualizaciones manualmente y no puede seguir el procedimiento normal de [Microsoft Store para empresas](https://businessstore.microsoft.com/store) para [distribuir aplicaciones sin conexión](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), puede adquirir el archivo appx y las dependencias correspondientes del [Kit de implementación](https://go.microsoft.com/fwlink/?linkid=851168) (de las instrucciones para [configurar una consola de Microsoft Team Rooms](console.md)) que se pueden usar con Configuration Manager. La versión del kit de implementación se retrasó tras la publicación de la tienda, por lo que es posible que no coincida siempre con la compilación más reciente disponible.
  
### <a name="to-update-using-powershell"></a>Para actualizar con PowerShell

1. Extrae el paquete del [MSI](https://go.microsoft.com/fwlink/?linkid=851168) de instalación a un recurso al que pueda acceder el dispositivo.
2. Ejecute la siguiente secuencia de comandos dirigida a los dispositivos de salas de \<Microsoft\> Teams, lo que cambia el uso compartido en el dispositivo compartido según corresponda:
    
```PowerShell
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>Modo de administrador y administración de dispositivos
<a name="AdminMode"> </a>

Algunas funciones de administración, como instalar manualmente un certificado de CA privada, requieren colocar el dispositivo Surface Pro en el modo de administrador. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Cambiar al modo de administración y volver cuando se ejecuta la aplicación salas de Microsoft Teams

1. Cuelgue todas las llamadas en curso y vuelva a la pantalla de inicio.
2. Seleccione el icono de engranaje y muestre el menú (las opciones son **configuración**, **accesibilidad**y **reiniciar dispositivo** ).
3. Seleccione **Configuración**.
4. Introduzca la contraseña de administrador. Se abrirá la pantalla Configuración.  Si el dispositivo no está unido a un dominio, se usará la cuenta administrativa local (nombre de usuario "administrador") de forma predeterminada. La contraseña predeterminada de esta cuenta es ' SFB ', cámbiela lo antes posible. Si el equipo está unido a un dominio, puede iniciar sesión con una cuenta de dominio con privilegios apropiados. 
5. Seleccione **configuración de Windows** en la columna de la izquierda.
6. Seleccione **Ir a inicio de sesión de administrador**.
7. Introduzca la contraseña de administrador. De este modo, se cierra la sesión de la aplicación y se le dirige a la pantalla de inicio de sesión de Windows. 
8. Inicie sesión en el escritorio con sus credenciales de administrador. Tendrá los privilegios necesarios para administrar el dispositivo.
9. Realice las tareas de administración que sean necesarias.
10. Cierre la sesión de la cuenta del administrador.
11. Vuelva a salas de Microsoft Teams seleccionando el icono de cuenta de usuario en el extremo izquierdo de la pantalla y seleccionando **Skype**.
    
    Si el usuario de **Skype** no aparece en la lista, es posible que tenga que seleccionar **otro usuario** y escribir **.\skype** como nombre de usuario e iniciar sesión.
    
Ahora, la consola vuelve a su modo de funcionamiento normal. El procedimiento siguiente requiere que adjunte un teclado al dispositivo si todavía no hay ninguno adjunto. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Cambiar al modo de administración y volver cuando se bloquea la aplicación salas de Microsoft Teams

1. Presione rápidamente la tecla Windows cinco veces. De este modo accederá a la pantalla de inicio de sesión de Windows. 
2. Inicie sesión en el escritorio con sus credenciales de administrador.
3. Realice las tareas de administración que sean necesarias.
4. Reinicie el equipo cuando haya terminado.

    > [!NOTE]
    > Este método no registra al usuario de Skype desactivado o finaliza correctamente la aplicación, pero lo usaría si la aplicación no responde y el otro método no estaba disponible. 

   La consola se reinicia a su modo de funcionamiento normal y ejecuta la aplicación salas de Microsoft Teams. Puede quitar el teclado, si está adjunto, para poder llevar a cabo este procedimiento.
   ## <a name="troubleshooting-tips"></a>Sugerencias para la solución de problemas
   <a name="TS"> </a>

- Es posible que las invitaciones a reuniones no aparezcan cuando se envíen a través de los límites del dominio (por ejemplo, entre dos compañías). En estos casos, los administradores de ti deberían decidir si permiten a los usuarios externos programar una reunión.
- Salas de Microsoft Teams no es compatible con el redireccionamiento de Exchange Autodiscover a través de Exchange 2010.
- En general, para los administradores de ti es recomendable deshabilitar los puntos de conexión de audio que no tengan la intención de usar.
- En el caso de que una imagen reflejada aparezca en la vista previa de la sala, el administrador de TI puede corregir desconectando y volviendo a conectar la cámara o volteando la orientación de la imagen con el control remoto de la cámara.
- Ha habido casos de pérdida de acceso táctil a la consola. En estos casos, a veces el problema se resuelve reiniciando el sistema de salas de Microsoft Teams.
- Ha habido casos de pérdida de audio local al conectar un PC a la consola mediante una transmisión integrada. En esos casos, el problema de reproducción de audio local se puede resolver reiniciando el PC.
    

---
title: Operaciones y mantenimiento de salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Lea este tema para obtener información sobre la administración de salas de Microsoft Teams, la próxima generación de Sistemas de salas de Skype.
ms.openlocfilehash: a6ab68200002035632314ac976cd45a2ee4ff714
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662465"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Operaciones y mantenimiento de salas de Microsoft Teams 
 
Lea este tema para obtener información sobre la administración de salas de Microsoft Teams, la próxima generación de Sistemas de salas de Skype.
  
Salas de Microsoft Teams es la última solución de conferencias de Microsoft diseñada para transformar su sala de reuniones en una experiencia colaborativa y completa. Los usuarios disfrutarán de la interfaz familiar de Microsoft Teams o Skype Empresarial, y los administradores de TI apreciarán una aplicación de reunión de Skype para Windows 10 fácil de implementar y administrar. Las salas de Microsoft Teams están diseñadas para aprovechar los equipos existentes, como los paneles DE AE PARA facilitar la instalación, y así llevar Microsoft Teams o Skype Empresarial a su sala de reuniones.
  
Con la configuración adicional, la administración remota es posible con Microsoft Azure Monitor, como se describe en Planear la administración de salas de Microsoft Teams con [Azure Monitor,](azure-monitor-plan.md)Implementar la administración de salas de Microsoft Teams con [Azure Monitor,](azure-monitor-deploy.md)administrar dispositivos de Salas de Microsoft Teams con [Azure Monitor.](azure-monitor-deploy.md) También puede administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración [XML,](xml-config-file.md)que incluye la aplicación de un tema de visualización personalizada. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Recopilar registros en Salas de Microsoft Teams
<a name="Logs"> </a>

Para recopilar registros, debe invocar el script de colección de registros que se incluye con la aplicación Microsoft Teams Rooms. En el modo de administración, inicie un símbolo del sistema con privilegios elevados y ejecute el comando siguiente:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Los registros se mostrarán como un archivo ZIP en c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Configuración de la pantalla frontal de la sala
<a name="Display"> </a>

Configure la pantalla frontal de la sala en modo Extendido. Si lo hace, se asegurará de que la interfaz de usuario de la consola no está duplicada en esa pantalla cuando se encienda la pantalla durante el ciclo de vida.
  
> [!NOTE]
> Si desea que la pantalla frontal de la sala cambie automáticamente a una fuente de vídeo activa (como una consola MTR) cuando el origen se reactiva del modo de espera, deben cumplirse ciertas condiciones. Esta característica es opcional, pero es compatible con el software salas de Microsoft Teams, siempre que el hardware subyacente admita la característica. Un televisor de consumidor usado frente a la pantalla de la sala debe admitir la característica de control de consumidores electronices (CEC) de HDMI.  En función de la base o consola seleccionada (que podría no ser compatible con CEC, consulte la documentación de soporte técnico del fabricante), es posible que se necesite un controlador como [HD-REM-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron para habilitar el comportamiento deseado. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Restablecimiento de salas de Microsoft Teams (restauración de fábrica)
<a name="Reset"> </a>

Si Salas de Microsoft Teams no funciona bien, realizar un restablecimiento de fábrica puede ayudar. Para ello, use la herramienta de [recuperación](recovery-tool.md) de sala de Microsoft Teams y siga las instrucciones de restauración de fábrica.

> [!NOTE]
> Hay un problema conocido por el que los salas de Microsoft Teams pueden quedar inutilizables si la opción Mantener mis archivos - Quita aplicaciones y opciones de **configuración,** pero mantiene la opción de archivos personales seleccionada durante el proceso de restablecimiento de Windows. No *use* esta opción.
  
## <a name="supported-remote-options"></a>Opciones remotas admitidas
<a name="RemoteOptions"> </a>

La tabla siguiente resume las operaciones remotas posibles y los métodos que se pueden utilizar para llevarlas a cabo.
  

|Grupo de trabajo |No unido a dominio|Unido a dominio|
|:-----|:-----|:-----|
|Reinicio  <br/> |Escritorio remoto  <br/> Powershell remoto  <br/> |Escritorio remoto (requiere una configuración más precisa)  <br/> PowerShell remoto (requiere configuración adicional)  <br/> Configuration Manager  <br/> |
|Actualizar SO  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Actualización de aplicaciones  <br/> |Tienda Windows  <br/> |Tienda Windows  <br/> Configuration Manager  <br/> |
|Configuración de cuenta de Skype  <br/> |No se admite actualmente  <br/> |No se admite actualmente  <br/> |
|Registros de acceso  <br/> |No se admite actualmente  <br/> |No se admite actualmente  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configuración de la directiva de grupo para Salas de Microsoft Teams
<a name="GroupPolicy"> </a>

Esta sección trata sobre la configuración del sistema de la que depende Microsoft Teams Rooms para que funcione correctamente. Al unirse a Salas de Microsoft Teams en un dominio, asegúrese de que la directiva de grupo no invalide la configuración de la tabla siguiente.
  

|Setting|Permite|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permite que Microsoft Teams Rooms se inicie  <br/> |
|Administración de energía: \> en ca, apagar la pantalla después de 10 minutos  <br/> Administración de energía: \> en AC, nunca ponga el sistema en suspensión  <br/> |Permite a los salas de Microsoft Teams desactivar las pantallas adjuntas y reactivar automáticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local. Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado. Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.  <br/> |Permite que la cuenta de Skype siempre inicie sesión  <br/> |
   
La transferencia de archivos mediante directivas de grupo se describe [en Configurar un elemento de archivo.](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

> [!NOTE]
> Cuando el dispositivo de Salas de Microsoft Teams es compatible con la siguiente versión del sistema operativo Windows 10, el dispositivo se actualiza automáticamente a la siguiente versión a través de Windows Update. El dispositivo de salas de Microsoft Teams no debe actualizarse a la siguiente versión de Windows 10 manualmente o habilitar las directivas de grupo de Windows Update para empresas (WUFB) "Seleccionar el nivel de preparación de Windows para las actualizaciones que desea recibir" y "Seleccionar cuándo se reciben las compilaciones de vista previa y las actualizaciones de características" a través de GPO. Se sabe que un dispositivo con estas directivas de grupo habilitadas tiene problemas con la actualización del sistema operativo Windows 10 de la aplicación microsoft Teams Rooms.

## <a name="remote-management-using-powershell"></a>Administración remota con PowerShell
<a name="RemotePS"> </a>

Puede realizar las siguientes operaciones de administración de forma remota con PowerShell (consulte la tabla siguiente para obtener ejemplos de scripts):
  
- Obtener dispositivos conectados
- Obtener estado de la aplicación
- Obtener información del sistema
- Reiniciar el sistema
- Recuperar registros
- Transferir archivos (requiere salas de Microsoft Teams unida a un dominio)
    
> [!NOTE]
> Esta funcionalidad está desactivada de manera predeterminada. Debe habilitar PowerShell remoto para su entorno en el sistema de salas de Microsoft Teams para realizar las siguientes operaciones. Consulte la documentación sobre **[Habilitar PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** para obtener información sobre cómo habilitar PowerShell remoto.
  
Por ejemplo, puede habilitar PowerShell remoto de esta manera:
  
1. Inicie sesión como administrador en un dispositivo de Microsoft Teams Rooms.
2. Abra un símbolo del sistema con privilegios elevados de PowerShell.
3. Escriba el comando siguiente: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Abra la directiva de seguridad local y agregue el grupo de seguridad Administradores al grupo de seguridad Configuración local Directivas locales: Derechos de usuario *asignados* a este equipo  >    >    >  **desde la red.**

Para ejecutar una operación de administración:
  
1. Inicie sesión en un equipo con credenciales de cuenta que tengan permiso para ejecutar comandos de PowerShell en un dispositivo de Microsoft Teams Rooms.
2. Abra un símbolo del sistema de PowerShell normal en el equipo.
3. Copie el texto del comando de la tabla siguiente y péguelo en el mensaje.
4. Reemplace  `<Device fqdn>` los campos por valores FQDN adecuados para su entorno.
5. Reemplace  *\<path\>*  por el nombre de archivo y la ruta local del patrón SkypeSettings.xml de configuración (o imagen del tema).
    
Para obtener dispositivos adjuntos
  
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

De forma predeterminada, Salas de Microsoft Teams intenta conectarse a la Tienda Windows para obtener la última versión del software salas de Microsoft Teams, por lo que el dispositivo requiere acceso regular a Internet. Antes de ponerse en contacto con Microsoft con problemas de soporte técnico, asegúrese de que el dispositivo de Salas de Microsoft Teams está cargado con la última versión de la aplicación.
  
De forma predeterminada, los salas de Microsoft Teams se conectan a Windows Update para recuperar las actualizaciones de firmware del dispositivo periférico USB y del sistema operativo, y los instala fuera del horario laboral configurado. Para configurar horarios comerciales, puede iniciar sesión en la cuenta de administrador y ejecutar la aplicación Configuración.
  
Si desea administrar las actualizaciones manualmente y no puede seguir el procedimiento habitual para que [Microsoft Store](https://businessstore.microsoft.com/store) para Empresas distribuya aplicaciones sin [conexión,](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)puede adquirir el archivo APPX adecuado y las dependencias del [kit](https://go.microsoft.com/fwlink/?linkid=851168) de implementación (en las instrucciones para configurar una consola de Microsoft [Teams Rooms)](console.md)que se puede usar con Configuration Manager. La versión del kit de implementación se encuentra por detrás de la versión de Store, por lo que es posible que no coincida siempre con la compilación disponible más reciente.
  
### <a name="to-update-using-powershell"></a>Para actualizar con PowerShell

1. Extraiga el paquete del [MSI de instalación](https://go.microsoft.com/fwlink/?linkid=851168) para compartir el dispositivo al que puede acceder.
2. Ejecute el siguiente script dirigido a los dispositivos de Salas de Microsoft Teams, cambiando \<share\> al recurso compartido de dispositivos según corresponda:
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Modo de administrador y administración de dispositivos
<a name="AdminMode"> </a>

Algunas funciones de administración, como la instalación manual de un certificado de entidad de certificación privada, requieren colocar el dispositivo Surface Pro en modo de administración. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Cambiar al modo de administración y volver cuando se está ejecutando la aplicación Salas de Microsoft Teams

1. Cuelga las llamadas en curso y vuelve a la pantalla principal.
2. Seleccione el icono de engranaje y aparecerá el menú (las opciones son **Configuración,** **Accesibilidad** y **Reiniciar dispositivo).**
3. Seleccione **Configuración**.
4. Introduzca la contraseña de administrador. Se abrirá la pantalla Configuración.  Si el dispositivo no está unido al dominio, la cuenta administrativa local (nombre de usuario "Administrador") se usará de forma predeterminada. La contraseña predeterminada para esta cuenta es "sfb", cambie la contraseña tan pronto como sea posible. Si el equipo está unido a un dominio, puede iniciar sesión con una cuenta de dominio con el privilegio adecuado. 
5. Seleccione **Configuración de Windows** en la columna izquierda.
6. Seleccione **Ir a inicio de sesión de administrador**.
7. Introduzca la contraseña de administrador. De este modo, se cierra la sesión de la aplicación y se le dirige a la pantalla de inicio de sesión de Windows. 
8. Inicie sesión en el escritorio con sus credenciales de administrador. Tendrás los privilegios necesarios para administrar el dispositivo.
9. Realice las tareas de administración que sean necesarias.
10. Cierre la sesión de la cuenta del administrador.
11. Para volver a salas de Microsoft Teams, seleccione el icono de la cuenta de usuario en el extremo izquierdo de la pantalla y, después, **seleccione Skype.**
    
    Si el **usuario de Skype** no aparece  en la lista, es posible que tenga que seleccionar otro usuario, escribir **.\skype** como nombre de usuario e iniciar sesión.
    
La consola ha vuelto a su modo de operación normal. El procedimiento siguiente requiere que adjunte un teclado al dispositivo si aún no está conectado. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Cambiar al modo de administración y volver cuando se bloquea la aplicación Salas de Microsoft Teams

1. Presione rápidamente la tecla Windows cinco veces. De este modo accederá a la pantalla de inicio de sesión de Windows. 
2. Inicie sesión en el escritorio con sus credenciales de administrador.
3. Realice las tareas de administración que sean necesarias.
4. Reinicie el equipo cuando haya terminado.

    > [!NOTE]
    > Este método no cierra la sesión del usuario de Skype ni la cierra con agraciación, pero la usa si la aplicación no responde y el otro método no está disponible. 

   La consola se reiniciará en su modo de funcionamiento normal, ejecutando la aplicación Salas de Microsoft Teams. Puede quitar el teclado si estaba conectado para permitirle realizar este procedimiento.
   ## <a name="troubleshooting-tips"></a>Sugerencias para la solución de problemas
   <a name="TS"> </a>

- Es posible que las invitaciones a reuniones no aparezcan al enviarse a través de límites de dominio (por ejemplo, entre dos empresas). En estos casos, los administradores de TI deben decidir si permiten a los usuarios externos programar una reunión.
- Salas de Microsoft Teams no admite redireccionamientos de detección automática de Exchange a través de Exchange 2010.
- En general, es una buena práctica que los administradores de TI deshabilite los extremos de audio que no quieren usar.
- En el caso de que una imagen reflejada aparezca en la vista previa de la sala, el administrador de TI puede corregir desconectando y volviendo a conectar la cámara o volteando la orientación de la imagen con el control remoto de la cámara.
- Ha habido casos de pérdida de acceso táctil a la consola. En estos casos, el problema se resuelve a veces reiniciando el sistema de salas de Microsoft Teams.
- Ha habido casos de pérdida de audio local al conectar un PC a la consola mediante una transmisión integrada. En esos casos, el problema de reproducción de audio local se puede resolver reiniciando el PC.
    

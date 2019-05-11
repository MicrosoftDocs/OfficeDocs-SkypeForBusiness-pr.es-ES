---
title: Operaciones y mantenimiento de salas de equipos de Microsoft
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Lea este tema para obtener más información acerca de la administración de salas de equipos de Microsoft, la próxima generación de sistemas de salón de Skype.
ms.openlocfilehash: 384920dc64d16dd9a50d7eee6e8546ad9920044e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916331"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Operaciones y mantenimiento de salas de equipos de Microsoft 
 
Lea este tema para obtener más información acerca de la administración de salas de equipos de Microsoft, la próxima generación de sistemas de salón de Skype.
  
Salones de los equipos de Microsoft es la solución de conferencia más reciente de Microsoft diseñada para transformar la sala de reuniones en una experiencia enriquecida y en colaboración. Los usuarios disfrutarán de su Teams Microsoft familiar o Skype para la interfaz de negocios y los administradores de TI apreciará una aplicación de Windows 10 Skype reunión fácil de implementar y administrada. Salones de los equipos de Microsoft está diseñado para sacar provecho de equipamiento existente como paneles LCD para facilitar la de instalación para incorporar Microsoft Teams o Skype para la empresa en la sala de reuniones.
  
Con una configuración adicional, es posible usar el Monitor de Azure de Microsoft como se describe en la [administración de planeación de salas de equipos de Microsoft con el Monitor de Azure](azure-monitor-plan.md), [administración de implementación de salas de equipos de Microsoft con el Monitor de Azure](azure-monitor-deploy.md), [administrar administración remota Dispositivos de salas de equipos de Microsoft con el Monitor de Azure](azure-monitor-deploy.md). Es posible que también la [configuración de forma remota con un archivo de configuración XML de la consola de administración de salas de equipos de Microsoft](xml-config-file.md), que incluye la aplicación de un tema de presentación personalizada. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Recopilar registros en salas de equipos de Microsoft
<a name="Logs"> </a>

Para recopilar los registros, se debe invocar la secuencia de comandos de la colección de registro que se distribuye con la aplicación de salas de equipos de Microsoft. En el modo de administrador, inicie un símbolo del sistema con privilegios elevados y emita el siguiente comando:
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Los registros de será salida como un archivo ZIP en c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Configuración de la pantalla frontal de la sala
<a name="Display"> </a>

Configure la pantalla frontal de la sala en modo Extendido. Al hacerlo, se asegurará de que la consola de la interfaz de usuario que no se repitan en que se muestran cuando se interrumpa la alimentación en la presentación.
  
> [!NOTE]
> Si se usa un televisor como pantalla, debe ser compatible con la característica Control de electrónica de consumidor (CEC) de HDMI o habilitarla para que puede cambiar automáticamente a un origen de vídeo activo desde el modo de espera. Esta característica no es compatible con todos los televisores. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Restablecimiento de salas de equipos de Microsoft (restauración de fábrica)
<a name="Reset"> </a>

Si salones de los equipos de Microsoft no se está ejecutando bien, realizar un restablecimiento de fábrica puede ayudarle a. Esto puede realizarse en la aplicación de configuración en la ficha **recuperación** bajo **restablecer este equipo**, seleccione **empezar a**y, a continuación, **Quitar todo el contenido**. Siga las indicaciones restantes para restablecer el dispositivo.
  
> [!NOTE]
> Hay un problema conocido donde las salas de los equipos de Microsoft puede convertirse en no se puede usar si se selecciona la opción de **Guardar los archivos - quita aplicaciones y configuración, pero mantiene los archivos personales** durante el proceso de restablecimiento de Windows. Hacer _no_ usar esta opción.
  
## <a name="supported-remote-options"></a>Opciones remotas admitidas
<a name="RemoteOptions"> </a>

La tabla siguiente resume las operaciones remotas posibles y los métodos que se pueden utilizar para llevarlas a cabo.
  

|**Grupo de trabajo **|**No unido a dominio**|**Unido a dominio**|
|:-----|:-----|:-----|
|Reinicio  <br/> |Escritorio remoto  <br/> Powershell remoto  <br/> |Escritorio remoto (requiere una configuración adicional)  <br/> Powershell remoto (requiere una configuración adicional)  <br/> SCCM  <br/> |
|Actualizar SO  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Actualización de aplicaciones  <br/> |Tienda Windows  <br/> |Tienda Windows  <br/> SCCM  <br/> |
|Configuración de cuenta de Skype  <br/> |No se admite actualmente  <br/> |No se admite actualmente  <br/> |
|Registros de acceso  <br/> |No se admite actualmente  <br/> |No se admite actualmente  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configuración de directiva de grupo para salas de equipos de Microsoft
<a name="GroupPolicy"> </a>

En esta sección, se explica la configuración del sistema que depende de salas de equipos de Microsoft para que funcione correctamente. Al unirse a salones de los equipos de Microsoft a un dominio, asegúrese de que la directiva de grupo no invalidar la configuración en la siguiente tabla.
  

|**Configuración**|**Permite**|
|:-----|:-----|
|HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = 1 (REG_SZ)  <br/> |Permite salones de los equipos de Microsoft para que se inicie  <br/> |
|Administración de energía -\> en AC, desactivar pantalla después de 10 minutos  <br/> Administración de energía -\> en AC, nunca colocar del sistema al modo de suspensión  <br/> |Permite salones de los equipos de Microsoft desactivar muestra adjunto y reactivar automáticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local. Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado. Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.  <br/> |Permite que la cuenta de Skype siempre inicie sesión  <br/> |
   
Transferencia de archivos mediante directivas de grupo se describe en [configurar un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Administración remota con PowerShell
<a name="RemotePS"> </a>

Puede realizar las siguientes operaciones de administración de forma remota mediante el uso de PowerShell (vea la tabla siguiente para ejemplos de secuencia de comandos):
  
- Obtener dispositivos conectados
    
- Obtener estado de la aplicación
    
- Obtener información del sistema
    
- Reiniciar el sistema
    
- Recuperar registros
    
- Transferencia de archivos (requiere un salones unido a un dominio de los equipos de Microsoft)
    
> [!NOTE]
> Esta funcionalidad está desactivada de manera predeterminada. Tiene que habilitar PowerShell remoto para el entorno en el sistema de salas de equipos de Microsoft para llevar a cabo las operaciones que aparece a continuación. Consulte la documentación en **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** para obtener información acerca de cómo habilitar PowerShell remoto.
  
Por ejemplo, puede habilitar PowerShell remoto de esta manera:
  
1. Inicie sesión como administrador en un dispositivo de salas de equipos de Microsoft.
    
2. Abra un símbolo del sistema de PowerShell comando con privilegios elevados.
    
3. Escriba el siguiente comando: Enable-PSRemoting -force
    
Para ejecutar una operación de administración:
  
1. Inicie sesión en un equipo con las credenciales de cuenta que tiene permiso para ejecutar los comandos de PowerShell en un dispositivo de salas de equipos de Microsoft.
    
2. Abra un símbolo PowerShell regular en su PC.
    
3. Copie el texto del comando de la tabla siguiente y péguelo en el símbolo del sistema.
    
4. Reemplace `<Device fqdn>` campos con valores FQDN apropiados para su entorno.
    
5. Reemplace * \<ruta de acceso\> * con el nombre de archivo y ruta de acceso local del archivo de configuración de SkypeSettings.xml maestra (o imagen de tema).
    
Para obtener los dispositivos conectados
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Obtener estado de la aplicación
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

Obtener información del sistema
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Reiniciar el sistema
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Recuperar registros
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Inserción de un archivo de configuración XML (o gráficos)
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Actualizaciones de software
<a name="SWupdate"> </a>

De forma predeterminada, salones de los equipos de Microsoft intenta conectarse a la tienda de Windows para obtener la versión más reciente del software de salas de equipos de Microsoft, por lo que el dispositivo requiere acceso a internet de regular. Antes de ponerse en contacto con Microsoft con problemas de soporte técnico, asegúrese de que el dispositivo de salas de equipos de Microsoft se carga con la versión más reciente de la aplicación.
  
De forma predeterminada, salones de los equipos de Microsoft se conecta a Windows Update para recuperar el sistema operativo y actualizaciones de firmware del dispositivo periférico USB y las instala fuera del horario configurado. Para configurar horarios comerciales, puede iniciar sesión en la cuenta de administrador y ejecutar la aplicación Configuración.
  
Si desea administrar manualmente las actualizaciones y no puede seguir el procedimiento normal para el [Almacén de Microsoft para la empresa](https://businessstore.microsoft.com/store) para [distribuir las aplicaciones sin conexión](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), puede adquirir el archivo APPX correspondiente y las dependencias desde el [kit de implementación](https://go.microsoft.com/fwlink/?linkid=851168) (desde las instrucciones para [Configurar una consola de salas de equipos de Microsoft](console.md)) que se pueden utilizar con SCCM. La versión del kit de implementación queda muy por detrás de la versión de almacenamiento, por lo que es posible que no siempre coincide con la compilación más reciente disponible.
  
### <a name="to-update-using-powershell"></a>Para actualizar el uso de Powershell

1. Extraer el paquete de la instalación que se puede tener acceso a [MSI](https://go.microsoft.com/fwlink/?linkid=851168) en un recurso compartido del dispositivo.
    
2. Ejecute el siguiente script de identificación de los dispositivos de salas de equipos de Microsoft, cambiar \<compartir\> al dispositivo compartir según corresponda:
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>Modo de administrador y administración de dispositivos
<a name="AdminMode"> </a>

Algunas funciones de administración, al igual que la instalación manual de un certificado de entidad de certificación privado, requieren colocar el dispositivo Surface Pro en modo de administrador. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Cambia al modo de administrador y cuando se ejecuta la aplicación de salas de equipos de Microsoft

1. Colgar las llamadas en curso y volver a la pantalla principal.
    
2. Seleccione el icono del engranaje y abrir el menú (son de las opciones de **configuración**, la **accesibilidad**y **Reinicie el dispositivo** ).
    
3. Seleccione **Configuración**.
    
4. Introduzca la contraseña de administrador. Se abrirá la pantalla Configuración.
    
    > [!NOTE]
    > Si el dispositivo no está unido a un dominio, se usará la cuenta administrativa local (nombre de usuario "Admin") de forma predeterminada. La contraseña predeterminada de esta cuenta es "sfb", aunque se recomienda a la organización que la cambie por motivos de seguridad tan pronto como sea posible. Si el equipo está unido a un dominio, puede iniciar sesión con una cuenta de dominio con privilegios de forma adecuada. 
  
5. Seleccione **Configuración de Windows** en la columna izquierda.
    
6. Seleccione **Ir a inicio de sesión de administrador**.
    
7. Introduzca la contraseña de administrador. De este modo, se cierra la sesión de la aplicación y se le dirige a la pantalla de inicio de sesión de Windows. 
    
8. Inicie sesión en el escritorio con sus credenciales de administrador. Tendrá los privilegios necesarios para administrar el dispositivo.
    
9. Realice las tareas de administración que sean necesarias.
    
10. Cierre la sesión de la cuenta del administrador.
    
11. Volver a salones de los equipos de Microsoft, seleccione el icono de la cuenta de usuario en el extremo izquierdo de la pantalla y, a continuación, seleccione **Skype**.
    
    Si el usuario de **Skype** no aparece, es posible que deba seleccione **otro usuario** y escriba **. \skype** como el nombre de usuario y de inicio de sesión.
    
La consola ahora es nuevo en el modo de funcionamiento normal. El siguiente procedimiento requiere adjuntar un teclado al dispositivo si uno no está asociado. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Cambia al modo de administrador y cuando se bloquea la aplicación de salas de equipos de Microsoft

1. Presione rápidamente la tecla Windows cinco veces. De este modo accederá a la pantalla de inicio de sesión de Windows. 
    
2. Inicie sesión en el escritorio con sus credenciales de administrador.
    
    > [!NOTE]
    > Este método no cierre la sesión del usuario de Skype o finalizar correctamente la aplicación, pero usaría si no se responde a la aplicación y el otro método no estaba disponible. 
  
3. Realice las tareas de administración que sean necesarias.
    
4. Cuando haya terminado, reinicie el equipo.
    
   La consola se reinicia en su modo de funcionamiento normal, que se ejecuta la aplicación de salas de equipos de Microsoft. Puede quitar el teclado, si estaba asociado para que pueda llevar a cabo este procedimiento.
   ## <a name="troubleshooting-tips"></a>Sugerencias para la solución de problemas
   <a name="TS"> </a>

- No es posible que aparezcan las invitaciones a reuniones cuando se envían a través de los límites del dominio (por ejemplo, entre las dos compañías). En estos casos, los administradores de TI deben decidir si desea permitir que los usuarios externos programar una reunión.
    
- Salones de los equipos de Microsoft no admite redirecciones de detección automática de Exchange a través de Exchange 2010.
    
- En general, es una práctica recomendada para los administradores de TI deshabilitar los extremos de audio que no desea utilizar.
    
- En el caso de que una imagen reflejada aparezca en la vista previa de la sala, el administrador de TI puede corregir desconectando y volviendo a conectar la cámara o volteando la orientación de la imagen con el control remoto de la cámara.
    
- Ha habido casos de pérdida de acceso táctil a la consola. En estos casos, el problema a veces se resuelve reiniciando el sistema de salas de equipos de Microsoft.
    
- Ha habido casos de pérdida de audio local al conectar un PC a la consola mediante una transmisión integrada. En esos casos, el problema de reproducción de audio local se puede resolver reiniciando el PC.
    

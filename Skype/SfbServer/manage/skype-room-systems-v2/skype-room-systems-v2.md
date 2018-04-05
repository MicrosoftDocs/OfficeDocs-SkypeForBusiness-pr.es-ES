---
title: Administrar Sistemas de salas de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Lea este tema para obtener información acerca de la administración de sistemas de salas de Skype v2, la próxima generación de sistemas de salas de Skype.
ms.openlocfilehash: 562dbeea19fb732caf9348e2bfd632da3579e71a
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="manage-skype-room-systems-v2"></a>Administrar Sistemas de salas de Skype v2
 
Lea este tema para obtener información acerca de la administración de sistemas de salas de Skype v2, la próxima generación de sistemas de salas de Skype.
  
Sistemas de salas de Skype v2 es la más reciente solución de conferencia de Microsoft diseñada para transformar un Skype enriquecido, colaboración de experiencia empresarial en la sala de reunión. Los usuarios disfrutarán de su familiar Skype para la interfaz de negocio y los administradores de TI podrán apreciar una aplicación de Windows 10 Skype reunión implementan y administran con facilidad. Sistemas de salas de Skype v2 está diseñado para aprovechar los equipos existentes como los paneles LCD para la facilidad de instalación para poner Skype para los negocios en la sala de reunión.
  
Con una configuración adicional, es posible usar Microsoft Operations Management Suite (OMS) como se describe en la [administración de sistemas de salas de Skype Plan v2 con OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [implementar sistemas de salas de Skype v2 administración con OMS](../../deploy/deploy-clients/with-oms.md)y [administrar administración remota Dispositivos de sistemas de salas de Skype v2 con OMS](oms.md). También puede [administrar un v2 de sistemas de salas de Skype la configuración de consola remota con un archivo de configuración XML](xml-config-file.md), que incluye la aplicación de un tema de la presentación personalizada. 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a>Recopilación de registros en los Sistemas de salas de Skype v2
<a name="Logs"> </a>

Para recopilar los registros, se debe invocar la secuencia de comandos de la colección de registro que se incluye con la sistemas de salas de Skype v2 app. En modo de administrador, inicie un símbolo del sistema con privilegios elevados y emita el comando siguiente:
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Los registros estarán salida como un archivo ZIP en c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Configuración de la pantalla frontal de la sala
<a name="Display"> </a>

Configure la pantalla frontal de la sala en modo Extendido. Al hacerlo, se asegurará de que la interfaz de usuario de la consola no se duplique en esa pantalla al desconectar y volver a conectar la pantalla.
  
> [!NOTE]
> Una televisión de consumo que se utiliza como un frente de las necesidades de visualización de sala para soporte o habilitar la característica de Control de electrónica de consumo (CEC) de HDMI por lo que puede cambiar automáticamente a un origen de vídeo activo en modo de espera. Esta característica no se admite en todos los televisores. 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a>Restablecer los Sistemas de salas de Skype v2 (a valores de fábrica)
<a name="Reset"> </a>

Si los sistemas de salas de Skype v2 no se está ejecutando bien, realizar un restablecimiento de fábrica puede ayudar. Esto se puede hacer en la aplicación de configuración de la ficha de "Recuperación" bajo el encabezado "Restablecer este PC", seleccione "comenzar" seguido de "Quitar todo". Siga los mensajes que queden como desee para restablecer el dispositivo.
  
> [!NOTE]
> Hay un problema conocido donde v2 de los sistemas de salas de Skype puede quedar inutilizable si está seleccionada la opción "Mantener mis archivos - quita aplicaciones y configuración pero mantiene los archivos personales" durante el proceso de restablecimiento de Windows. **No** use esta opción.
  
## <a name="supported-remote-options"></a>Opciones remotas admitidas
<a name="RemoteOptions"> </a>

La tabla siguiente resume las operaciones remotas posibles y los métodos que se pueden utilizar para llevarlas a cabo.
  

|**Grupo de trabajo**|**No pertenencia a un dominio**|**Pertenencia a un dominio**|
|:-----|:-----|:-----|
|Reinicio  <br/> |Escritorio remoto  <br/> Powershell remoto  <br/> |Escritorio remoto (requiere configuración adicional)  <br/> Powershell remoto (requiere configuración adicional)  <br/> SCCM  <br/> |
|Actualizar SO  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Actualización de aplicaciones  <br/> |Tienda Windows  <br/> |Tienda Windows  <br/> SCCM  <br/> |
|Configuración de cuenta de Skype  <br/> |No se admite actualmente  <br/> |No se admite actualmente  <br/> |
|Registros de acceso  <br/> |No se admite actualmente  <br/> |No se admite actualmente  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a>Configurar la directiva de grupo para los Sistemas de salas de Skype v2
<a name="GroupPolicy"> </a>

Esta sección describe la configuración del sistema que depende de sistemas de salas de Skype v2 para funcionar correctamente. Al unirse a sistemas de salas de Skype v2 a un dominio, asegúrese de que la directiva de grupo no sobrescribe la configuración siguiente:
  

|**Configuración**|**Permite**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1  <br/> |Permite sistemas de salas de Skype v2 para iniciarse  <br/> |
|Administración de energía -\> de CA, desactivar pantalla después de 10 minutos  <br/> Administración de energía -\> con corriente Alterna, nunca ponga el sistema en modo de suspensión  <br/> |Permite a los sistemas de salas de Skype v2 desactivar muestra adjunto y reactivará automáticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local. Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado. Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.  <br/> |Permite que la cuenta de Skype siempre inicie sesión  <br/> |
   
Transferir archivos mediante directivas de grupo se describe en [configurar un elemento de archivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Administración remota con PowerShell
<a name="RemotePS"> </a>

Con PowerShell, es posible ejecutar las siguientes operaciones de administración de manera remota (la tabla a continuación muestra ejemplos de script):
  
- Obtener dispositivos conectados
    
- Obtener estado de la aplicación
    
- Obtener información del sistema
    
- Reiniciar el sistema
    
- Recuperar registros
    
- Transferencia de archivos (requiere un dominio unido sistemas de salas de Skype v2)
    
> [!NOTE]
> Esta funcionalidad está desactivada de manera predeterminada. Debe habilitar PowerShell remoto para su entorno en el sistema de sistemas de salas de Skype v2 realizar las operaciones siguientes. Consulte la documentación de **[Enable-PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)** para obtener información sobre cómo habilitar PowerShell remoto.
  
Por ejemplo, puede habilitar PowerShell remoto de esta manera:
  
1. Iniciar sesión como administrador en un dispositivo de sistemas de salas de Skype v2.
    
2. Inicie un símbolo de sistema de PowerShell con privilegios elevados.
    
3. Escriba el siguiente comando: Enable-PSRemoting - forzar
    
Para ejecutar una operación de administración:
  
1. Iniciar sesión en un equipo con credenciales de cuenta que tiene permiso para ejecutar comandos de PowerShell en un dispositivo de sistemas de salas de Skype v2.
    
2. Inicie un símbolo de sistema de PowerShell común en su PC.
    
3. Copie el texto del comando en la tabla a continuación y péguelo en el símbolo del sistema.
    
4. Reemplazar `<Device fqdn>` campos con valores FQDN apropiados para su entorno.
    
5. Reemplazar * \<path\> * con el nombre de archivo y la ruta de acceso local del archivo de configuración principal de SkypeSettings.xml (o imagen de tema).
    
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

Insertar un archivo XML de configuración (o un gráfico del tema)
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Actualizaciones de software
<a name="SWupdate"> </a>

De forma predeterminada, sistemas de salas de Skype v2 intentará conectar con el almacén de Windows para obtener la versión más reciente del software de los sistemas de salas de Skype v2, por lo que el dispositivo requerirá acceso regular de internet. Asegúrese de que el dispositivo de los sistemas de salas de Skype v2 se carga con la versión más reciente de la aplicación, antes de ponerse en contacto con Microsoft con problemas de soporte técnico.
  
De forma predeterminada, sistemas de salas de Skype v2 se conectarse a Windows Update para recuperar sistema operativo así como firmware periférico USB las actualizaciones e instalarlas fuera del horario comercial configurado. Para configurar horarios comerciales, puede iniciar sesión en la cuenta de administrador y ejecutar la aplicación Configuración.
  
Si desea administrar las actualizaciones manualmente y no puede seguir el procedimiento normal para el [Almacén de Microsoft para el negocio](https://businessstore.microsoft.com/en-us/store) para [distribuir las aplicaciones sin conexión](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps), puede adquirir el archivo APPX apropiado y dependencias desde el [kit de implementación](https://go.microsoft.com/fwlink/?linkid=851168) (desde las instrucciones para [Configurar una consola de sistemas de salas de Skype v2](../../deploy/deploy-clients/console.md)) que puede utilizarse con SCCM. La versión del kit de implementación queda atrás el lanzamiento del almacén, por lo que no siempre coincida con la compilación más reciente disponible.
  
### <a name="to-update-using-powershell"></a>Para actualizar el uso de Powershell

1. Extraiga el paquete de instalación de [MSI](https://go.microsoft.com/fwlink/?linkid=851168) a un recurso compartido de dispositivo accesible.
    
2. Ejecute el siguiente script dirigidas a los sistemas de sala de Skype v2 dispositivos, cambiar \<compartir\> al dispositivo comparta según corresponda:
    
  ```
  Add-AppxPackage -Update -ForceApplicationShutdown -Path \\<share>\Rigel\x64\Ship\AppPackages\*\*.appx -DependencyPath (Get-ChildItem \\<share>\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx | Foreach-Object {$_.FullName}) 

  ```

## <a name="admin-mode-and-device-management"></a>Modo de administrador y administración de dispositivos
<a name="AdminMode"> </a>

Para realizar algunas funciones de administración, como la instalación manual de un certificado de entidad de certificación privado, es necesario poner el dispositivo Surface 4 en el modo de administrador.  
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a>Cambiar al modo de administrador, y cuando se ejecuta la aplicación de sistemas de salas de Skype v2

1. Cuelgue las llamadas que haya en curso y vuelva a la pantalla de inicio.
    
2. Haga clic en el icono de engranaje y abrir el menú (opciones son **configuración**, **accesibilidad**y **Reinicie el dispositivo** ).
    
3. Seleccione **Configuración**.
    
4. Introduzca la contraseña de administrador. Se abrirá la pantalla Configuración.
    
    > [!NOTE]
    > Si el dispositivo no está unido a un dominio, se utilizará la cuenta del administrador local (nombre de usuario "Administrador") de forma predeterminada. La contraseña predeterminada de esta cuenta es "sfb", aunque se recomienda a la organización que la cambie por motivos de seguridad tan pronto como sea posible. Si la máquina está unida a un dominio, puede iniciar sesión con una cuenta de dominio que tenga los privilegios adecuados. 
  
5. Haga clic en **Configuración de Windows** en la columna izquierda.
    
6. Seleccione **Ir a inicio de sesión de administrador**.
    
7. Introduzca la contraseña de administrador. De este modo, se cierra la sesión de la aplicación y se le dirige a la pantalla de inicio de sesión de Windows. 
    
8. Inicie sesión en el escritorio con sus credenciales de administrador. Tendrá los privilegios necesarios para administrar el dispositivo.
    
9. Realice las tareas de administración que sean necesarias.
    
10. Cierre la sesión de la cuenta del administrador.
    
11. Volver a sistemas de salas de Skype v2 seleccionando el icono de la cuenta de usuario en el extremo izquierdo de la pantalla y seleccione **Skype**.
    
    Si el usuario de **Skype** no aparece, tendrá que seleccionar **otro usuario** e introduzca **. \skype** como el nombre de usuario y de inicio de sesión.
    
 La consola está ahora en su modo de funcionamiento normal. El procedimiento siguiente requiere adjuntar un teclado al dispositivo si uno no está asociado. 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a>Cambiar al modo de administrador, y cuando se bloquea la aplicación de sistemas de salas de Skype v2

1. Presione rápidamente la tecla Windows cinco veces. De este modo accederá a la pantalla de inicio de sesión de Windows.  
    
2. Inicie sesión en el escritorio con las credenciales de administrador.
    
    > [!NOTE]
    > Con este método no se cierra la sesión del usuario de Skype ni finaliza la aplicación, pero solo lo debe usar si la aplicación no responde y el otro método no está disponible. 
  
3. Realice las tareas de administración que sean necesarias.
    
4. Reinicie la máquina cuando termine.
    
 La consola se reiniciará en su modo de funcionamiento normal, ejecutar la aplicación de sistemas de salas de Skype v2. Si adjuntó el teclado, puede quitarlo para que pueda llevar a cabo este procedimiento.
## <a name="troubleshooting-tips"></a>Sugerencias para la solución de problemas
<a name="TS"> </a>

- Las invitaciones a reuniones no aparezcan cuando se envían a través de los límites del dominio (por ejemplo, entre dos empresas). En tales casos, los administradores de TI deben decidir si desea permitir que los usuarios externos programar una reunión o no.
    
- Sistemas de salas de Skype v2 no admite redirecciones de detección automática de Exchange a través de Exchange 2010.
    
- Por lo general, recomendamos que los administradores de TI deshabiliten todos los extremos de audio que no vayan a ser utilizados.
    
- En el caso de que una imagen reflejada aparezca en la vista previa de la sala, el administrador de TI puede corregir desconectando y volviendo a conectar la cámara o volteando la orientación de la imagen con el control remoto de la cámara.
    
- Ha habido casos de pérdida de acceso táctil a la consola. En tales casos, el problema a veces se resuelve reiniciando el sistema v2 de sistemas de salas de Skype.
    
- Ha habido casos de pérdida de audio local al conectar un PC a la consola mediante una transmisión integrada. En esos casos, el problema de reproducción de audio local se puede resolver reiniciando el PC.
    
## <a name="see-also"></a>Vea también
<a name="TS"> </a>

#### 

[Plan para la sala de Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implementar sala de Skype v2 de sistemas](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurar una consola de sistemas de salas de Skype v2](../../deploy/deploy-clients/console.md)
  
[Administrar una configuración de la consola de sistemas de salas de Skype v2 de forma remota con un archivo de configuración XML](xml-config-file.md)


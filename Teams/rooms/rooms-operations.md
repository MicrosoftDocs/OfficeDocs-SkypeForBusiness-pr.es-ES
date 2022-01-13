---
title: Salas de Microsoft Teams mantenimiento y operaciones
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
ms.localizationpriority: medium
description: Lea este tema para obtener información sobre la administración de Salas de Microsoft Teams.
ms.openlocfilehash: 2238712b269475891074016c1099a33c56004595
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015050"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Salas de Microsoft Teams mantenimiento y operaciones
 
Lea este tema para obtener información sobre la administración de Salas de Microsoft Teams.
  
Salas de Microsoft Teams es la solución de conferencias de Microsoft diseñada para transformar su sala de reuniones en una experiencia colaborativa y rica. Los usuarios disfrutarán de su interfaz Microsoft Teams o Skype Empresarial y los administradores de TI apreciarán una aplicación Windows 10 Salas de Teams implementada y administrada fácilmente. Salas de Microsoft Teams está diseñado para aprovechar el equipamiento existente para facilitar la instalación para Microsoft Teams o Skype Empresarial en la sala de reuniones.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Recopilación de registros en Salas de Microsoft Teams
<a name="Logs"> </a>

Para recopilar registros en Teams de administración, vaya a Teams **dispositivos > Salas de Teams en Windows**. Seleccione el nombre para mostrar del dispositivo para el que desea los registros. En el panel superior, seleccione "Descargar registros de dispositivos". Una vez que confirme, los registros estarán listos para su descarga en la pestaña Historial después de unos minutos.

También puede usar PowerShell para recopilar registros. Debe invocar el script de la colección de registros que se incluye con la aplicación Salas de Microsoft Teams registro. En [modo administrador,](rooms-operations.md)inicie un símbolo del sistema con privilegios elevados y ejecute el siguiente comando:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Los registros se mostrarán como un archivo ZIP en c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Configuración de la pantalla frontal de la sala
<a name="Display"> </a>

Configure la configuración de las pantallas frontales de la sala para admitir consumer electronics control(CEC) o habilitar el modo PC.
  
Si desea que una pantalla frontal de la sala cambie automáticamente a Salas de Teams cuando se reactiva del modo de espera, deben cumplirse determinadas condiciones. Esta característica es opcional, pero es compatible Salas de Microsoft Teams software, siempre que el hardware subyacente admita la característica. Un televisor para consumidores que se usa como pantalla frontal de la sala debe admitir la característica control de electrónica de consumo (CEC) de HDMI.  Dependiendo de la base o consola seleccionada (que podría no ser compatible con CEC, consulte documentación de soporte técnico del fabricante), es posible que sea necesario un controlador como [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron para habilitar el comportamiento deseado.
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Salas de Microsoft Teams restablecer (restauración de fábrica)
<a name="Reset"> </a>

Si Salas de Microsoft Teams funciona bien, realizar un restablecimiento de fábrica puede ser de ayuda. Para ello, use la herramienta Microsoft Teams [recuperación](recovery-tool.md) de sala y siga las instrucciones de restauración de fábrica.

> [!NOTE]
> Existe un problema conocido por el que el Salas de Microsoft Teams puede quedar inutilizable si la opción Mantener mis archivos: quita aplicaciones y **configuración,** pero mantiene seleccionada la opción archivos personales durante el proceso de Windows Restablecer. No *use* esta opción.
  
## <a name="supported-remote-options"></a>Opciones remotas admitidas
<a name="RemoteOptions"> </a>

La tabla siguiente resume las operaciones remotas posibles y los métodos que se pueden utilizar para llevarlas a cabo.
  

|Grupo de trabajo |No unido a dominio|Unido a dominio|
|:-----|:-----|:-----|
|Reinicio  <br/> |Teams de administración  <br/> Escritorio remoto  <br/> PowerShell remoto  <br/> | <br/>Escritorio remoto (requiere una configuración adicional)  <br/> PowerShell remoto (requiere una configuración adicional)  <br/> Configuration Manager  <br/> |
|Actualizar SO  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Actualización de aplicaciones  <br/> |Tienda Windows  <br/> |Tienda Windows  <br/> Configuration Manager  <br/> |
|Configuración de la cuenta  <br/> |Teams de administración  <br/> |Teams de administración  <br/> |
|Registros de acceso  <br/> |Teams de administración  <br/> PowerShell  <br/> |Teams de administración <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurar la directiva de grupo para Salas de Microsoft Teams
<a name="GroupPolicy"> </a>

Esta sección trata la configuración del sistema Salas de Microsoft Teams depende de que funcione correctamente. 

Unirse Salas de Teams a un dominio de Active Directory proporciona las siguientes ventajas:

- La unión a Salas de Teams permite conceder derechos administrativos a usuarios y grupos de dominios. Al hacer esto, no tendrá que acordarse de la contraseña de la cuenta de administrador de nivel de máquina local.

- Puede implementar la Windows calidad del servicio en Salas de Teams.

- Si usa Skype Empresarial, unirse al dominio Salas de Teams automatiza la importación de la cadena de certificados raíz privada de su organización.

Al unirse Salas de Teams a un dominio, es necesario que cree una unidad organizativa (OU) independiente para que pueda proporcionar exclusiones de objetos de directiva de grupo (GPO) a la unidad organizativa donde residen todos los Salas de Teams grupo. Deshabilite toda la herencia de GPO para que la configuración de directiva de grupo no compatible no se aplique a Salas de Teams. Cree objetos de equipo en la unidad organizativa antes de unirse Salas de Teams al dominio para asegurarse de que las directivas de grupo aplicadas a la unidad organizativa predeterminada de los equipos no se aplican.

> [!NOTE]
> Incluso si crea una unidad organizativa independiente y bloquea la herencia, hay algunas directivas de grupo que podrían causar problemas si no tienen ningún conjunto de invalidación. Una directiva de grupo con un conjunto sin invalidación supera a una unidad organizativa con el conjunto de herencia de directivas de bloques.

Muchas organizaciones tienen los siguientes GPO, que afectan Salas de Teams funcionalidad. Asegúrese de invalidar o bloquear la herencia de estos:

  - Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)
  - Directivas relacionadas de administración de energía
  - Requerir pasos de autenticación adicionales
  - Negar el acceso a las unidades locales
  - Avisar a los usuarios de conexiones de red lentas
  - Iniciar un programa determinado en el inicio de sesión
  - Crear otra cuenta de usuario de dominio en todas las máquinas con unión a dominio.
  - Insertar Windows actualizar a Salas de Teams

Al unirse Salas de Microsoft Teams a un dominio, asegúrese de que las directivas de grupo no invaliden la configuración de la tabla siguiente.

|Setting|Permite|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permite Salas de Microsoft Teams inicio  <br/> |
|Power Management: \> en CA, desactiva la pantalla después de 10 minutos  <br/> Power Management: \> en CA, nunca ponga el sistema en suspensión  <br/> |Permite Salas de Microsoft Teams para desactivar las pantallas adjuntas y reactivar automáticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> O medios alternativos para deshabilitar la opción de caducidad de la contraseña en la cuenta local. Si esto no se realiza, la cuenta de Skype no podrá iniciar sesión indicando que la contraseña ha caducado. Tenga en cuenta que esto afectará todas las cuentas locales de la máquina y, por consiguiente, si no se configura esto, la cuenta administrativa del cuadro eventualmente también caducará.   <br/> |Permite que la cuenta de Skype siempre inicie sesión  <br/> |

> [!NOTE]
> Cuando Salas de Microsoft Teams es compatible con la siguiente versión del sistema operativo Windows 10, Salas de Teams automáticamente a la siguiente versión a través de Windows actualización. Salas de Microsoft Teams no debe actualizarse Windows 10 la próxima versión de Windows 10 manualmente o mediante la habilitación de directivas de grupo de actualización para empresas (WUFB) de Windows "Seleccione el nivel de preparación Windows para las actualizaciones que desea recibir" y "Seleccionar cuándo se reciben compilaciones de vista previa y actualizaciones de características" a través de GPO. Salas de Teams con estas directivas de grupo habilitadas se sabe que tienen problemas con las Windows 10 del sistema operativo.

## <a name="remote-management-using-powershell"></a>Administración remota con PowerShell
<a name="RemotePS"> </a>

Puede realizar las siguientes operaciones de administración de forma remota mediante PowerShell (consulte la tabla siguiente para obtener ejemplos de script):
  
- Obtener dispositivos conectados
- Obtener estado de la aplicación
- Obtener información del sistema
- Reiniciar el sistema
- Recuperar registros
- Transferir archivos (requiere un Salas de Microsoft Teams)
    
> [!NOTE]
> Esta funcionalidad está desactivada de manera predeterminada. Debe habilitar PowerShell remoto para su entorno en el Salas de Microsoft Teams para realizar las siguientes operaciones. Consulte la documentación sobre **[Habilitar-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** para obtener información sobre cómo habilitar PowerShell remoto.
  
Por ejemplo, puede habilitar PowerShell remoto de esta manera:
  
1. Inicie sesión como administrador en Salas de Microsoft Teams dispositivo.
2. Abra un símbolo del sistema de PowerShell con privilegios elevados.
3. Escriba el siguiente comando: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Abra la directiva de seguridad local y agregue el grupo de seguridad *Administradores* a Seguridad **Configuración** Directivas locales Asignación de derechos de usuario Acceso a este equipo  >    >    >  **desde la red.**

Para ejecutar una operación de administración:
  
1. Inicie sesión en un equipo con credenciales de cuenta que tengan permiso para ejecutar comandos de PowerShell en un Salas de Microsoft Teams dispositivo.
2. Abra un símbolo del sistema de PowerShell normal en el equipo.
3. Copie el texto del comando de la tabla siguiente y péguelo en el mensaje.
4. Reemplace  `<Device fqdn>` campos con valores FQDN adecuados para su entorno.
5. Reemplace por el nombre de archivo y la ruta  *\<path\>*  de acceso local del patrón SkypeSettings.xml de configuración (o imagen del tema).
    
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

De forma predeterminada, Salas de Microsoft Teams intenta conectarse a Windows Store para obtener la versión más reciente de Salas de Microsoft Teams software. Por lo tanto, Salas de Teams requiere acceso a Internet regular. Antes de ponerse en contacto con Microsoft con problemas de soporte técnico, asegúrese de que Salas de Microsoft Teams está cargado con la última versión de la aplicación.
  
Salas de Microsoft Teams se conecta a Windows update para recuperar las actualizaciones de firmware de dispositivos periféricos y del sistema operativo. Teams room está configurado para instalarlos a partir de las 2:00 a.m. hora local.
  
Si debe administrar las actualizaciones manualmente debido a limitaciones en el acceso Windows la tienda y, por lo tanto, no puede seguir el procedimiento normal de [Microsoft Store para Empresas](https://businessstore.microsoft.com/store) para distribuir aplicaciones sin [conexión,](/microsoft-store/distribute-offline-apps)puede adquirir el archivo APPX adecuado y las dependencias del [kit](https://go.microsoft.com/fwlink/?linkid=851168) de implementación (de las instrucciones para Configurar [un Salas de Microsoft Teams consola](console.md)) que se puede usar con Configuration Manager. La versión del kit de implementación se encuentra por detrás de la versión de store, por lo que es posible que no coincida siempre con la compilación disponible más reciente.
  
### <a name="to-update-using-powershell"></a>Para actualizar con PowerShell

1. Extraiga el paquete del [MSI de instalación](https://go.microsoft.com/fwlink/?linkid=851168) a un recurso compartido al que puede acceder el dispositivo.
2. Ejecute el siguiente script dirigido a Salas de Microsoft Teams dispositivos, cambiando al \<share\> recurso compartido de dispositivos según corresponda:
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Modo de administrador y administración de dispositivos
<a name="AdminMode"> </a>

Algunas funciones de administración, como instalar manualmente un certificado de CA privado, requieren colocar Salas de Teams en modo administrador. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Cambiar al modo administrador y volver cuando la aplicación Salas de Microsoft Teams está ejecutándose

1. Cuelgue las llamadas en curso y vuelva a la pantalla principal.
2. Selecciona el icono Engranaje y muestra el menú (las opciones son **Configuración,** **Accesibilidad** y **Reiniciar dispositivo).**
3. Seleccione **Configuración**.
4. Escriba la contraseña del administrador. Se abrirá la pantalla Configuración.  Si el dispositivo no está unido a un dominio, la cuenta administrativa local (nombre de usuario "Administrador") se usará de forma predeterminada. La contraseña predeterminada para esta cuenta es "sfb". Cambie esta contraseña lo antes posible. Si el equipo está unido a un dominio, puede iniciar sesión con una cuenta de dominio con privilegios adecuados.
5. Seleccione **Windows Configuración** en la columna izquierda.
6. Inicie sesión en el escritorio con sus credenciales de administrador. Tendrás los privilegios necesarios para administrar el dispositivo.
7. Realice las tareas de administración que sean necesarias.
8.  Reinicie el equipo cuando haya terminado.
    
La consola volverá a su modo de funcionamiento normal. El siguiente procedimiento requiere que agregue un teclado al dispositivo si no hay ninguno todavía.  
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Cambiar al modo administrador y volver cuando se bloquea Salas de Microsoft Teams aplicación

1. Presione rápidamente la tecla Windows cinco veces. De este modo accederá a la pantalla de inicio de sesión de Windows.  
2. Inicie sesión en el escritorio con sus credenciales de administrador.
3. Realice las tareas de administración que sean necesarias.
4. Reinicie el equipo cuando haya terminado.

    > [!NOTE]
    > Este método no cierra la sesión del usuario de Skype o termina correctamente la aplicación, pero la usaría si la aplicación no respondía y el otro método no estaba disponible. 

   La consola se reinicia en su modo de funcionamiento normal, ejecutando la Salas de Microsoft Teams aplicación. Puede quitar el teclado si ha adjuntado uno para completar este procedimiento.
   ## <a name="troubleshooting-tips"></a>Sugerencias para la solución de problemas
   <a name="TS"> </a>

- Es posible que las invitaciones a reuniones no aparezcan cuando se envían a través de los límites del dominio (por ejemplo, entre dos empresas). En estos casos, los administradores de TI deben decidir si permiten a los usuarios externos programar una reunión. Vea el artículo sobre el cmdlet Exchange PowerShell [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), específicamente el parámetro "ProcessExternalMeetingMessages".
- Salas de Microsoft Teams no es compatible con Exchange de detección automática a través Exchange 2010.
- En general, es una buena práctica para los administradores de TI deshabilitar los puntos de conexión de audio que no tienen intención de usar.
- En el caso de que se muestre una imagen reflejada en la vista previa de la sala, el administrador de TI puede corregir si gira la potencia de la cámara o voltear la orientación de la imagen con la configuración de la cámara.
- Ha habido casos de pérdida de acceso táctil a la consola. En estos casos, el problema a veces se resuelve reiniciando Salas de Teams.
- Ha habido casos de pérdida de audio local al conectar un PC a la consola mediante una transmisión integrada. En esos casos, el problema de reproducción de audio local se puede resolver reiniciando el PC.

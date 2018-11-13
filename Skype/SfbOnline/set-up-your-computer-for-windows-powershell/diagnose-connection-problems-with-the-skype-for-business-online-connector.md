---
title: Diagnosticar problemas de conexión con el conector de Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Solución de problemas de creación de una sesión remota de PowerShell para conectarse a Skype para profesionales Online, incluidos Import-Module, shell simultánea, Live ID y errores de permiso.
ms.openlocfilehash: 576c7cb3cc083fcdf609419a45bf7fab7a64269b
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295900"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosticar problemas de conexión con el conector de Skype Empresarial Online

En este tema se proporciona información que le ayudarán a diagnosticar y resolver problemas que pueden surgir cuando se intenta crear una sesión remota de PowerShell de Microsoft que se conecta a Skype para profesionales en línea. Consulte las siguientes secciones:
  
- [Error de Import-Module causado por la directiva de ejecución de Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Error de Import-Module causados por una versión incorrecta de Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [No se pudo conectar al servidor de identificador de Live Meeting](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [No se pudo cargar el módulo de Live ID](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Inicio de sesión para el usuario](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [El usuario no tiene permiso para administrar este inquilino](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Capacidad para conectarse al inquilino está deshabilitada en Skype para profesionales en línea](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Se superó el número máximo de shells simultáneos para este usuario en Skype para profesionales en línea](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [Se superó el número máximo de shells simultáneos para este inquilino en Skype para profesionales en línea](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Error de Import-Module causado por la directiva de ejecución de Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

La directiva de ejecución de PowerShell ayuda a determinar qué archivos de configuración se pueden cargar en la consola de PowerShell y que secuencias de comandos de un usuario pueden ejecutar desde esa consola. Como mínimo, el Skype para el módulo del conector en línea de negocio no se puede importar a menos que se ha establecido la directiva de ejecución en RemoteSigned. Si no es así, recibirá el siguiente mensaje de error al intentar importar el módulo:
  
- **Error**: <em>Import-Module: archivo C:\\archivos de programa\\archivos comunes\\Microsoft Lync Server 2013\\módulos\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 no se puede cargar porque en ejecución las secuencias de comandos está deshabilitada en este sistema. Para obtener más información, vea about_Execution_Policies en https://go.microsoft.com/fwlink/?LinkID=135170.</em>

- **Resolución**: para resolver este problema, inicie PowerShell como administrador y, a continuación, ejecute el siguiente comando:
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    Para obtener información detallada acerca de la directiva de ejecución, vea [Acerca de las directivas de ejecución](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Error de Import-Module causados por una versión incorrecta de Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

El Skype para el módulo del conector en línea de negocio se puede ejecutar sólo en Windows PowerShell 3.0. Si se intenta importar el módulo en una versión anterior de PowerShell, se producirá un error en el proceso de importación con un mensaje de error similar al siguiente:
  
  - **Error**: *Import-Module: la versión de la carga PowerShell es '2.0'. El módulo ' D:\\archivos de programa\\archivos comunes\\Microsoft Lync Server 2013\\módulos\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requiere una versión mínima de PowerShell de '3.0' para ejecutar. Comprobación de la instalación de la PowerShell y vuelva a intentarlo.*

- **Resolución**: la única forma de solucionar este problema es instalar Windows PowerShell 3.0, que está disponible desde Microsoft Download Center en [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
## <a name="failed-to-connect-to-live-id-server"></a>No se pudo conectar al servidor de identificador de Live Meeting
<a name="BKMKFailedConnect"> </a>

Normalmente hay tres razones, ¿por qué es posible que producirá un error en el intento de conexión con el siguiente mensaje de error:

  - **Error**: *Get-CsWebTicket: no se pudo conectar los servidores de Windows live id. Asegúrese de que el proxy está habilitado o equipo tiene conexión de red con servidores de identificador de live.*

- **Resolución**: a menudo este error significa que no se está ejecutando el Asistente de inicio de sesión de Microsoft Online Services. Puede comprobar el estado de este servicio ejecutando el comando siguiente desde el símbolo del sistema de PowerShell: 
    ```
    Get-Service "msoidsvc"
    ```
    Si no se está ejecutando el servicio, inicie el servicio mediante el uso de este comando:
    ```
    Start-Service "msoidsvc"
    ```

    Si el servicio se está ejecutando, puede tratarse de problemas con la conexión de red entre el equipo y el servidor de autenticación de Microsoft Live ID. Para comprobar esto, abra Internet Explorer y vaya a [ https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Intente iniciar sesión en Office 365 desde allí. Si se produce un error, probablemente está experimentando problemas de conexión de red.
  
    Con menos frecuencia, es posible que se ha configurado el URI de conexión para el servidor de autenticación de Microsoft Live ID en el valor incorrecto. Si ya ha determinado que el inicio de sesión de Ayudante se está ejecutando y que no está experimentando problemas de conectividad de red, esto podría ser el problema. En este caso, póngase en contacto con soporte técnico de Office 365.
  
## <a name="failed-to-load-live-id-module"></a>No se pudo cargar el módulo de Live ID
<a name="BKMKFailedLoad"> </a>

Uno de los requisitos previos para el uso de PowerShell para administrar Skype para profesionales en línea es instalar al Asistente de inicio de sesión de Microsoft Online Services. Si el Asistente de inicio de sesión no está instalado, recibirá el siguiente mensaje de error cuando intenta establecer una sesión remota con Skype para empresarial en línea:

- **Error**: *Get-CsWebTicket: no se puede cargar el módulo de Live Id. Asegúrese de seguro correcto se instala la versión del Ayudante para el inicio de sesión de Live Id.*

- **Resolución**: Ayudante para el inicio de sesión de la Microsoft Online Services está disponible en Microsoft Download Center en [Microsoft Asistente en línea de servicios de inicio de sesión para RTW de profesionales de TI](https://www.microsoft.com/en-us/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Inicio de sesión para el usuario
<a name="BKMKLogonFailed"> </a>

Cuando intenta establecer una conexión remota con Skype para profesionales en línea, debe proporcionar el nombre de usuario y la contraseña de un Skype válido para la cuenta de usuario en línea de negocio. Si no lo hace, se producirá un error de inicio de sesión junto con un mensaje de error similar al siguiente:

- **Error**: *Get-CsWebTicket: error de inicio de sesión para el usuario 'kenmyer@litwareinc.com'. Cree un nuevo objeto PSCredential, asegurándose de que se han utilizado el nombre de usuario correcto y la contraseña.*

- **Resolución**: si piensa que está usando una cuenta de usuario válido y que tiene la contraseña correcta, intente volver a iniciar la sesión. Si se produce un error, use las mismas credenciales y que intente iniciar sesión en [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Si no puede iniciar sesión existe, póngase en contacto con el soporte técnico de Office 365. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>El usuario no tiene permiso para administrar este inquilino
<a name="BKMKUserPermission"> </a>

No puede realizar una toSkype de conexión de PowerShell remoto para profesionales en línea a menos que sea miembro del grupo de administradores de inquilinos. Si no lo está, se producirá un error en el intento de conexión y recibirá el mensaje de error siguiente:

- **Error**: *New-PSSession: error de procesamiento de datos desde el servidor remoto admin.vdomain.com [admin.vdomain.com] con el siguiente mensaje de error: el usuario 'user@foo.com' no tiene permiso para administrar este inquilino. Se pueden conceder permisos mediante la asignación de usuario a la función adecuada de RBAC. Para obtener más información, vea la [Resolución de problemas remota](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Resolución**: si piensa que están o, se supone que un miembro del grupo de administradores de inquilinos, deberá ponerse en contacto con soporte técnico de Office 365.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Capacidad para conectarse al inquilino está deshabilitada en Skype para profesionales en línea
<a name="BKMKAbilityConnect"> </a>

Para usar PowerShell para administrar Skype para profesionales en línea, se debe establecer la propiedad EnableRemotePowerShellAccess de su inquilino de la directiva de PowerShell `True`. Si no es así, se producirá un error en la conexión y recibirá el mensaje de error siguiente:

- **Error**: *New-PSSession: error de procesamiento de datos desde el servidor remoto admin.vdomain.com [admin.vdomain.com] con el siguiente mensaje de error: se ha deshabilitado la capacidad para conectarse a este inquilino mediante el uso de una sesión remota de PowerShell. Póngase en contacto con ayuda de Lync para comprobar la directiva de Powershell inquilino de este inquilino. Para obtener más información, vea la [Resolución de problemas remota](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Solución**: Si aparece este mensaje de error, que necesitará para ponerse en contacto con soporte técnico de Office 365 y obtener acceso remoto de PowerShell habilitado.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Se superó el número máximo de shells simultáneos para este usuario en Skype para profesionales en línea
<a name="BKMKMaxNumberShellsUser"> </a>

Cada administrador se permite un máximo de tres conexiones remotas simultáneas a Skype para profesionales en línea. Si tiene tres conexiones de PowerShell remotas copia de seguridad y en ejecución, cualquier intento de realizar un cuarto simultáneas conexión se producirá un error, con el mensaje de error siguiente:

- **Error**: *New-PSSession: [admin.vdomain.com] no pudo conectar al servidor remoto admin.vdomain.com con el siguiente mensaje de error: el WS-Management no puede procesar la solicitud. Se superó el número máximo de shells simultáneos para este usuario. Cerrar shells existentes o aumentar la cuota para este usuario. Para obtener más información, vea el [Troubleshooting remoto] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Resolución**: es la única forma de resolver este problema cerrar una o varias de las conexiones de la anteriores. Cuando haya terminado con un Skype para la sesión en línea de negocio, se recomienda que utilice el cmdlet **Remove-PSSession** para terminar la sesión. Esto le ayudará a evitar que este problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Se superó el número máximo de shells simultáneos para este inquilino en Skype para profesionales en línea
<a name="BKMKMaxNumberShellsTenant"> </a>

Aunque cada administrador se puede tener como máximo tres conexiones simultáneas a un Skype para inquilino empresarial en línea, inquilino único no puede tener más de nueve conexiones simultáneas. Por ejemplo, tres administradores es posible que cada uno tiene tres sesiones abiertas. Si un administrador de la cuarto intenta realizar una conexión (lo que resulta en un total de 10 conexiones simultáneas), este intento se producirá un error, con el mensaje de error siguiente:
  
- **Error**: *New-PSSession: [admin.vdomain.com] no pudo conectar al servidor remoto admin.vdomain.com con el siguiente mensaje de error: el WS-Management no puede procesar la solicitud. Se superó el número máximo de shells simultáneos para este inquilino. Cerrar shells existentes o aumentar la cuota para este inquilino. Para obtener más información, vea el [Troubleshooting remoto] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Resolución**: es la única forma de resolver este problema cerrar una o varias de las conexiones de la anteriores. Cuando haya terminado con un Skype para la sesión en línea de negocio, se recomienda que use el cmdlet **Remove-PSSession** para terminar de esa sesión. Esto le ayudará a evitar que este problema.  
 
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 

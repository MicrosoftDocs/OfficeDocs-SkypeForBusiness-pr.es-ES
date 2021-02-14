---
title: Diagnosticar problemas de conexión con el conector de Skype Empresarial Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Solucione problemas al crear una sesión de PowerShell remota para conectarse a Skype Empresarial Online, incluidos los errores de importación y módulo, shell simultáneo, Live ID y permisos.
ms.openlocfilehash: 019ef023b325227be046aae1e855573449453864
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204881"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosticar problemas de conexión con el conector de Skype Empresarial Online

Este tema proporciona información que le ayudará a diagnosticar y resolver los problemas que pueden ocurrir cuando intenta crear una sesión remota de Microsoft PowerShell que se conecta a Skype Empresarial Online. Vea las secciones siguientes:
  
- [Error de importación y módulo causado por una Windows PowerShell de ejecución](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Error de importación y módulo causado por una versión incorrecta del Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [La autenticación moderna falla cuando se ha deshabilitado la autenticación WinRM Basic](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Error al conectarse al servidor Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Error al cargar el módulo Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Error de inicio de sesión para el usuario](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [El usuario no tiene permiso para administrar este inquilino](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Se ha deshabilitado la posibilidad de conectarse al inquilino en Skype Empresarial Online.](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Se ha superado el número máximo de shells simultáneos de este usuario en Skype Empresarial Online.](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Se ha superado el número máximo de shells simultáneos para este espacio empresarial en Skype Empresarial Online.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> De forma predeterminada, las sesiones de PowerShell se tiempo de espera después de 60 minutos. Para volver a conectarse, tiene que cerrar la sesión e iniciar una nueva sesión de PowerShell. Una nueva versión de Skype Empresarial [Online, Windows PowerShell Module (2046.123 - Publicada el 2/10/2019),](https://www.microsoft.com/download/details.aspx?id=39366)se ha iniciado recientemente, que incluye un nuevo cmdlet llamado **Enable-CsOnlineSessionForReconnection** que reduce el problema de tiempo de espera de 60 minutos.
> La sesión de PowerShell vuelve a conectarse y se autentica, lo que permite que se vuelva a usar sin tener que iniciar una nueva instancia para volver a conectarse.



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module error causado por una Windows PowerShell de ejecución
<a name="BKMKPowerShellExecutionPolicy"> </a>

La directiva de ejecución de PowerShell le ayuda a determinar qué archivos de configuración se pueden cargar en la consola de PowerShell y qué scripts puede ejecutar un usuario desde esa consola. Como mínimo, el módulo del conector de Skype Empresarial Online no se puede importar a menos que la directiva de ejecución se haya establecido en RemoteSigned. Si no lo ha hecho, recibirá el siguiente mensaje de error cuando intente importar el módulo:
  
- **Error**: Importar-Módulo : Archivo C: Archivos de programa Archivos comunes <em>Microsoft Lync Server \\ \\ \\ 2013 Módulos \\ \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 no se puede cargar porque los scripts de ejecución están deshabilitados en este sistema. Para obtener más información, consulte about_Execution_Policies en https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Resolución** Para resolver este problema, inicie PowerShell como administrador y, después, ejecute el siguiente comando:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Para obtener más información sobre las directivas de ejecución, vea [Acerca de las directivas de ejecución.](https://go.microsoft.com/fwlink/?LinkID=135170)
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module Error causado por una versión incorrecta de Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

El módulo conector de Skype Empresarial Online solo se puede ejecutar en Windows PowerShell 3.0. Si intenta importar el módulo en una versión anterior de PowerShell, el proceso de importación producirá un error similar a este mensaje de error:
  
  - **Error**: *Import-Module: La versión del PowerShell cargado es '2.0'. El módulo "D: Archivos de programa Archivos \\ \\ comunes: Módulos de Lync Server 2013 LyncOnlineConnectorLyncOnlineConnector.psd1" requiere una versión mínima de PowerShell de \\ \\ \\ \\ "3.0" para ejecutarse. Compruebe la instalación de PowerShell e inténtelo de nuevo.*

- **Resolución:** la única forma de solucionar este problema es instalar Windows PowerShell 3.0, que está disponible en el Centro de descarga de Microsoft en [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>La autenticación moderna falla cuando se ha deshabilitado la autenticación WinRM Basic
<a name="BKMKWinRMBasicAuth"> </a>

La última versión del módulo Del conector de Skype Empresarial Online usa la autenticación moderna, pero el cliente de Administración remota de Windows (WinRM) subyacente debe estar configurado para permitir la autenticación básica.  La autenticación moderna usa tokens de portador que normalmente se pasan en el *encabezado Autorización: portador.* Windows PowerShell, en el que se basa PowerShell de Skype Empresarial, no se permite la manipulación de este encabezado.  En su lugar, PowerShell de Skype Empresarial usa *el encabezado Authorization: Basic* para pasar el token del portador.

Vea [Descargar e instalar Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) para obtener instrucciones sobre cómo habilitar WinRM para la autenticación básica.

## <a name="failed-to-connect-to-live-id-server"></a>Error al conectarse al servidor Live ID
<a name="BKMKFailedConnect"> </a>

Por lo general, hay tres motivos por los que se puede producir un error en el intento de conexión con el siguiente mensaje de error:

  - **Error**: *Get-CsWebWebWeb : Error al conectar los servidores de id. directos. Asegúrese de que el proxy está habilitado o de que el equipo tiene conexión de red a servidores de id. directos.*

- **Resolución:** este error suele significar que el Microsoft Online Services de inicio de sesión no se está ejecutando. Puede comprobar el estado de este servicio ejecutando el comando siguiente desde el símbolo del sistema de PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Si el servicio no se está ejecutando, inicie el servicio con este comando:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Si el servicio se está ejecutando, es posible que tenga problemas con la conexión de red entre su equipo y el servidor de autenticación de Id. de Microsoft Live. Para comprobarlo, abra Internet Explorer y vaya a [ https://login.microsoftonline.com/ .](https://login.microsoftonline.com/.) Intente iniciar sesión en Microsoft 365 u Office 365 desde allí. Si se produce un error en esta opción, probablemente tenga problemas de conexión de red.
  
    Con menos comunes, es posible que el URI de conexión del servidor de autenticación de Id. de Microsoft Live se haya configurado en el valor incorrecto. Si ya ha determinado que el Asistente para Sign-In se está ejecutando y que no está experimentando problemas de conectividad de red, este podría ser el problema. En este caso, póngase en contacto con el Soporte técnico de Microsoft.
  
## <a name="failed-to-load-live-id-module"></a>Error al cargar el módulo Live ID
<a name="BKMKFailedLoad"> </a>

Uno de los requisitos previos para usar PowerShell para administrar Skype Empresarial Online es instalar el asistente para Microsoft Online Services inicio de sesión. Si el Asistente para inicio de sesión no está instalado, recibirá el siguiente mensaje de error cuando intente establecer una sesión remota con Skype Empresarial Online:

- **Error**: *Get-CsWebWebWeb : No se puede cargar el módulo Live Id. Asegúrese de que está instalada la versión correcta* del Asistente para inicio de sesión de Live Id.

- **Resolución:** el asistente Microsoft Online Services inicio de sesión está disponible en el Centro de descarga de Microsoft en Microsoft Online Services Sign-In para profesionales de TI [(RTW)](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Error de inicio de sesión para el usuario
<a name="BKMKLogonFailed"> </a>

Cuando intente realizar una conexión remota a Skype Empresarial Online, debe proporcionar el nombre de usuario y la contraseña de una cuenta de usuario válida de Skype Empresarial Online. Si no lo hace, se producirá un error de inicio de sesión junto con un mensaje de error similar a este:

- **Error**: Get-CsWebWebWeb : Error de inicio de sesión *para el usuario 'kenmyer@litwareinc.com'. Cree un nuevo objeto PSCredential y asegúrese* de que ha usado el nombre de usuario y la contraseña correctos.

- **Resolución:** si cree que usa una cuenta de usuario válida y tiene la contraseña correcta, intente iniciar sesión de nuevo. Si se produce un error, use las mismas credenciales e intente iniciar sesión en [https://login.microsoftonline.com/](https://login.microsoftonline.com/) . Si no puedes iniciar sesión allí, ponte en contacto con el soporte técnico de Microsoft. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>El usuario no tiene permiso para administrar este inquilino
<a name="BKMKUserPermission"> </a>

No puede realizar una conexión remota de PowerShell aSkype para empresas Online a menos que sea miembro del grupo Administradores de inquilinos. Si no lo está, se producirá un error en el intento de conexión y recibirá el siguiente mensaje de error:

- **Error**: New-PSSession : [admin.vdomain.com] Error al procesar datos del servidor remoto admin.vdomain.com con el siguiente mensaje de error: El usuario "user@foo.com" no tiene permiso para administrar este espacio *empresarial. Para conceder permisos, asigne al usuario el rol RBAC adecuado. Para obtener más información, vea solución [remota de problemas.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Resolución:** si cree que es o se supone que es miembro del grupo Administradores de inquilinos, deberá ponerse en contacto con el soporte técnico de Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Se ha deshabilitado la posibilidad de conectarse al inquilino en Skype Empresarial Online.
<a name="BKMKAbilityConnect"> </a>

Para usar PowerShell para administrar Skype Empresarial Online, la propiedad EnableRemotePowerShellAccess de la directiva de PowerShell del espacio empresarial debe establecerse en  `True` . Si no es así, se producirá un error en la conexión y recibirá el siguiente mensaje de error:

- **Error**: New-PSSession : [admin.vdomain.com] Se produjo un error en el procesamiento de los datos del servidor remoto admin.vdomain.com con el siguiente mensaje de error: Se deshabilitó la capacidad de conectarse a este inquilino mediante una sesión remota *de PowerShell. Póngase en contacto con la Ayuda de Lync para comprobar la directiva de PowerShell de inquilino de este inquilino. Para obtener más información, vea solución [remota de problemas.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Resolución:** si ve este mensaje de error, deberá ponerse en contacto con el soporte técnico de Microsoft y habilitar el acceso remoto de PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Se ha superado el número máximo de shells simultáneos de este usuario en Skype Empresarial Online.
<a name="BKMKMaxNumberShellsUser"> </a>

A cada administrador se le permite un máximo de tres conexiones remotas simultáneas a Skype Empresarial Online. Si tiene tres conexiones powerShell remotas activas y en ejecución, se producirá un error en cualquier intento de realizar una cuarta conexión simultánea y aparecerá el siguiente mensaje de error:

- **Error**: New-PSSession : [admin.vdomain.com] No se pudo conectar al servidor remoto admin.vdomain.com con el siguiente mensaje de error: El servicio WS-Management no puede *procesar la solicitud. Se ha excedido el número máximo de shells simultáneos para este usuario. Cierre los shells existentes o eleva la cuota de este usuario. Para obtener más https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 información, consulte [Solución remota de problemas](*

- **Resolución:** la única forma de resolver este problema es cerrar una o varias de las conexiones anteriores. Cuando haya terminado con una sesión de Skype Empresarial Online, le recomendamos que use el cmdlet **Remove-PSSession** para finalizar la sesión. Esto le ayudará a evitar este problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Se ha superado el número máximo de shells simultáneos para este espacio empresarial en Skype Empresarial Online.
<a name="BKMKMaxNumberShellsTenant"> </a>

Aunque cada administrador puede tener hasta tres conexiones simultáneas a un inquilino de Skype Empresarial Online, ningún inquilino puede tener más de 20 conexiones simultáneas. Por ejemplo, podría haber seis administradores cada uno con tres sesiones abiertas. Si un cuarto administrador intenta realizar más de 2 conexiones (lo que da como resultado un total de 21 conexiones simultáneas), se producirá un error en este intento y aparecerá el siguiente mensaje de error:
  
- **Error**: New-PSSession : [admin.vdomain.com] No se pudo conectar al servidor remoto admin.vdomain.com con el siguiente mensaje de error: El servicio WS-Management no puede *procesar la solicitud. Se ha excedido el número máximo de shells simultáneos para este inquilino. Cierre los shells existentes o eleva la cuota de este inquilino. Para obtener más https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 información, consulte [Solución remota de problemas](*

- **Resolución:** la única forma de resolver este problema es cerrar una o varias de las conexiones anteriores. Cuando haya terminado con una sesión de Skype Empresarial Online, le recomendamos que use el cmdlet **Remove-PSSession** para finalizar esa sesión. Esto le ayudará a evitar este problema.  
 
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 

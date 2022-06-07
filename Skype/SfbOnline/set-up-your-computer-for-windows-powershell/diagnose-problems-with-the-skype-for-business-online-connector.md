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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Solución de problemas al crear una sesión de PowerShell remota para conectarse a Skype Empresarial Online, incluidos los errores de módulo de importación, shell simultáneo, Live ID y permisos.
ms.openlocfilehash: c2092da0324a147b182ce7715e757f1ed039aa65
ms.sourcegitcommit: 1ac37cc27d4ccb3e1dae20ca1929214e17be2075
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2022
ms.locfileid: "65913398"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosticar problemas de conexión con el conector de Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este tema proporciona información que le ayudará a diagnosticar y resolver problemas que pueden producirse al intentar crear una sesión remota de Microsoft PowerShell que se conecte a Skype Empresarial Online. Consulte las siguientes secciones:
  
- [Error del módulo de importación causado por la directiva de ejecución de Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Error de importación y módulo causado por una versión incorrecta de Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Se produce un error de autenticación moderna cuando se ha deshabilitado la autenticación básica de WinRM](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Error al conectarse al servidor de Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
      
- [Error al iniciar sesión para el usuario](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [El usuario no tiene permiso para administrar este inquilino](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [La capacidad de conectarse al espacio empresarial se ha deshabilitado en Skype Empresarial Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Se ha superado el número máximo de shells simultáneos para este usuario en Skype Empresarial Online](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Se ha superado el número máximo de shells simultáneos para este espacio empresarial en Skype Empresarial Online.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module error causado por la directiva de ejecución de Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

La directiva de ejecución de PowerShell ayuda a determinar qué archivos de configuración se pueden cargar en la consola de PowerShell y qué scripts puede ejecutar un usuario desde esa consola. Como mínimo, el módulo conector de Skype Empresarial Online no se puede importar a menos que la directiva de ejecución se haya establecido en RemoteSigned. Si no es así, recibirá el siguiente mensaje de error cuando intente importar el módulo:
  
- **Error**: <em>Módulo de importación: Archivo C:\\Archivos\\de programa Archivos\\comunes Módulos de Microsoft Lync Server 2013\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 no se puede cargar porque los scripts en ejecución están deshabilitados\\en este sistema. Para obtener más información, consulte about_Execution_Policies en https://go.microsoft.com/fwlink/?LinkID=135170.</em>

- **Resolución** Para resolver este problema, inicie PowerShell como administrador y, a continuación, ejecute el siguiente comando:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Para obtener más información sobre la directiva de ejecución, vea [Acerca de las directivas de ejecución](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module Error causado por una versión incorrecta de Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

El módulo Conector de Skype Empresarial Online solo se puede ejecutar en Windows PowerShell 3.0. Si intenta importar el módulo en una versión anterior de PowerShell, se producirá un error en el proceso de importación con un mensaje de error similar a este mensaje:
  
  - **Error**: *Import-Module : La versión del PowerShell cargado es '2.0'. El módulo 'D:\\Archivos\\de programa Archivos comunes\\Módulos\\de Microsoft Lync Server 2013\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requiere una versión mínima de PowerShell de '3.0' para ejecutarse. Compruebe la instalación del PowerShell e inténtelo de nuevo.*

- **Resolución**: La única manera de solucionar este problema es instalar Windows PowerShell 3.0, que está disponible desde el Centro de descarga de Microsoft en [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>Se produce un error de autenticación moderna cuando se ha deshabilitado la autenticación básica de WinRM
<a name="BKMKWinRMBasicAuth"> </a>

La última versión del módulo Conector de Skype Empresarial Online usa autenticación moderna, pero el cliente de Administración remota de Windows (WinRM) subyacente debe configurarse para permitir la autenticación básica.  La autenticación moderna usa tokens del portador, que normalmente se pasan en el encabezado *Authorization: Bearer* . Windows PowerShell, en el que se basa PowerShell de Skype Empresarial, no permite la manipulación de este encabezado.  En su lugar, PowerShell de Skype Empresarial usa el encabezado *Authorization: Basic* para pasar el token del portador.

Consulte [Descargar e instalar Windows PowerShell](./download-and-install-windows-powershell-5-1.md) para obtener instrucciones sobre cómo habilitar WinRM para la autenticación básica.

## <a name="failed-to-connect-to-live-id-server"></a>Error al conectarse al servidor de Live ID
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> La autenticación de Live ID ha quedado en desuso para Skype Empresarial Online Connector. Use el Módulo de PowerShell de Teams para administrar el inquilino en línea. Al administrar entornos híbridos, actualice a la actualización acumulativa más reciente o use la autenticación oAuth.

Por lo general, existen tres motivos por los que el intento de conexión puede fallar con el siguiente mensaje de error:

  - **Error**: *Get-CsWebTicket : No se pudo conectar los servidores live ID. Asegúrese de que el proxy está habilitado o de que el equipo tiene conexión de red a servidores id. activos.*

- **Resolución**: este error suele indicar que el Asistente para el inicio de sesión de Microsoft Online Services no se está ejecutando. Puede comprobar el estado de este servicio ejecutando el siguiente comando desde el símbolo del sistema de PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Si el servicio no se está ejecutando, inicie el servicio mediante este comando:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Si el servicio se está ejecutando, es posible que tenga problemas con la conexión de red entre el equipo y el servidor de autenticación de Microsoft Live ID. Para comprobarlo, abre Internet Explorer y ve a [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Intente iniciar sesión en Microsoft 365 u Office 365 desde allí. Si se produce un error, probablemente esté experimentando problemas de conexión de red.
  
    Con menos frecuencia, es posible que el URI de conexión para el servidor de autenticación de Microsoft Live ID se haya configurado en el valor incorrecto. Si ya ha determinado que el Asistente para Sign-In se está ejecutando y que no está experimentando problemas de conectividad de red, este podría ser el problema. En este caso, ponte en contacto con soporte técnico de Microsoft.
  
## <a name="logon-failed-for-the-user"></a>Error en el inicio de sesión del usuario
<a name="BKMKLogonFailed"> </a>

Al intentar realizar una conexión remota a Skype Empresarial Online, debe proporcionar el nombre de usuario y la contraseña de una cuenta de usuario válida de Skype Empresarial Online. Si no lo hace, se producirá un error de inicio de sesión junto con un mensaje de error similar a este mensaje:

- **Error**: *Get-CsWebTicket : Error de inicio de sesión del usuario "kenmyer@litwareinc.com". Cree un nuevo objeto PSCredential, asegurándose de que ha usado el nombre de usuario y la contraseña correctos.*

- **Resolución**: Si cree que está usando una cuenta de usuario válida y que tiene la contraseña correcta, intente iniciar sesión de nuevo. Si se produce un error, use las mismas credenciales e intente iniciar sesión en [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Si no puedes iniciar sesión allí, ponte en contacto con soporte técnico de Microsoft. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>El usuario no tiene permiso para administrar este inquilino
<a name="BKMKUserPermission"> </a>

No puede realizar una conexión remota de PowerShell aSkype para empresas Online a menos que sea miembro del grupo Administradores de inquilinos. Si no lo está, se producirá un error en el intento de conexión y recibirá el siguiente mensaje de error:

- **Error**: *New-PSSession: [admin.vdomain.com] El procesamiento de datos del servidor remoto admin.vdomain.com falló con el siguiente mensaje de error: El usuario 'user@foo.com' no tiene permiso para administrar este inquilino. Se pueden conceder permisos asignando al usuario el rol RBAC adecuado. Para obtener más información, consulte [Solución de problemas remota](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Resolución**: si crees que eres o se supone que eres miembro del grupo Administradores de inquilinos, deberás ponerte en contacto con el soporte técnico de Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>La capacidad de conectarse al espacio empresarial se ha deshabilitado en Skype Empresarial Online
<a name="BKMKAbilityConnect"> </a>

Para usar PowerShell para administrar Skype Empresarial Online, la propiedad EnableRemotePowerShellAccess de la directiva de PowerShell de su espacio empresarial debe establecerse en  `True`. Si no es así, se producirá un error en la conexión y recibirá el siguiente mensaje de error:

- **Error**: *New-PSSession: [admin.vdomain.com] El procesamiento de datos del servidor remoto admin.vdomain.com error con el siguiente mensaje de error: Se ha deshabilitado la capacidad para conectarse a este espacio empresarial mediante una sesión de PowerShell remota. Póngase en contacto con la ayuda de Lync para comprobar la directiva de PowerShell de inquilino de este inquilino. Para obtener más información, consulte [Solución de problemas remota](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Resolución**: si ve este mensaje de error, deberá ponerse en contacto con el soporte técnico de Microsoft y habilitar el acceso remoto a PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Se ha superado el número máximo de shells simultáneos para este usuario en Skype Empresarial Online
<a name="BKMKMaxNumberShellsUser"> </a>

A cada administrador se le permite un máximo de tres conexiones remotas simultáneas a Skype Empresarial Online. Si tiene tres conexiones remotas de PowerShell en funcionamiento, se producirá un error al intentar realizar una cuarta conexión simultánea, con el siguiente mensaje de error: 

- **Error**: *New-PSSession: [admin.vdomain.com] La conexión al servidor remoto admin.vdomain.com error con el siguiente mensaje de error: El servicio WS-Management no puede procesar la solicitud. Se ha superado el número máximo de shells simultáneos para este usuario. Cerrar shells existentes o aumentar la cuota para este usuario. Para obtener más información, consulte [Solución de problemas remota](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Resolución**: La única manera de resolver este problema es cerrar una o varias de las conexiones anteriores. Cuando haya terminado con una sesión de Skype Empresarial Online, le recomendamos que use el cmdlet **Remove-PSSession** para finalizar la sesión. Esto le ayudará a evitar este problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Se ha superado el número máximo de shells simultáneos para este espacio empresarial en Skype Empresarial Online.
<a name="BKMKMaxNumberShellsTenant"> </a>

Aunque cada administrador puede tener hasta tres conexiones simultáneas a un inquilino de Skype Empresarial Online, no se permite que un único inquilino tenga más de 20 conexiones simultáneas. Por ejemplo, seis administradores podrían tener tres sesiones abiertas cada uno. Si un cuarto administrador intenta realizar más de dos conexiones (lo que da como resultado un total de 21 conexiones simultáneas), se producirá un error en este intento, con el siguiente mensaje de error:
  
- **Error**: *New-PSSession: [admin.vdomain.com] La conexión al servidor remoto admin.vdomain.com error con el siguiente mensaje de error: El servicio WS-Management no puede procesar la solicitud. Se ha superado el número máximo de shells simultáneos para este inquilino. Cerrar shells existentes o aumentar la cuota para este inquilino. Para obtener más información, consulte [Solución de problemas remota](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Resolución**: La única manera de resolver este problema es cerrar una o varias de las conexiones anteriores. Cuando haya terminado con una sesión de Skype Empresarial Online, le recomendamos que use el cmdlet **Remove-PSSession** para finalizar esa sesión. Esto le ayudará a evitar este problema.  
 
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración de Skype Empresarial Online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  

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
description: Solución de problemas de creación de una sesión de PowerShell remota para conectarse a Skype empresarial online, incluidos los errores de módulo de importación, de Shell simultáneo, de Live ID y de permisos.
ms.openlocfilehash: 019ef023b325227be046aae1e855573449453864
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204881"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosticar problemas de conexión con el conector de Skype Empresarial Online

Este tema proporciona información que le ayudará a diagnosticar y resolver problemas que se pueden producir al intentar crear una sesión remota de Microsoft PowerShell que se conecte a Skype empresarial online. Vea las secciones siguientes:
  
- [Importación-error de módulo causado por la Directiva de ejecución de Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Importación: error de módulo causado por una versión incorrecta de Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [No se puede realizar la autenticación moderna cuando se ha deshabilitado la autenticación básica de WinRM](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Error al conectarse al servidor de Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Error al cargar el módulo Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Error al iniciar sesión para el usuario](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [El usuario no tiene permiso para administrar este inquilino.](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [La posibilidad de conectar con el inquilino se ha deshabilitado en Skype empresarial online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Se ha superado el número máximo de shells simultáneos para este usuario en Skype empresarial online](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Se ha superado el número máximo de shells simultáneos para este inquilino en Skype empresarial online](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> De forma predeterminada, el tiempo de espera de las sesiones de PowerShell es de 60 minutos. Para volver a conectarse, debe cerrar la sesión e iniciar una nueva sesión de PowerShell. Se ha iniciado una nueva versión de [Skype empresarial online, módulo Windows PowerShell (2046,123-publicado en 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366), que incluye un cmdlet nuevo denominado **enable-CsOnlineSessionForReconnection** que mitiga el problema de tiempo de espera de 60 minutos.
> La sesión de PowerShell se vuelve a conectar y se autentica, lo que permite reutilizarla sin tener que iniciar una nueva instancia para volver a conectarse.



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Importación-error de módulo causado por la Directiva de ejecución de Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

La Directiva de ejecución de PowerShell ayuda a determinar qué archivos de configuración se pueden cargar en la consola de PowerShell y qué scripts puede ejecutar un usuario desde esa consola. Como mínimo, el módulo conector de Skype empresarial online no se puede importar a menos que la Directiva de ejecución se haya establecido como RemoteSigned. Si no es así, recibirá el siguiente mensaje de error al intentar importar el módulo:
  
- **Error**: <em>Import-Module: archivo C: archivos \\ comunes de programa archivos \\ comunes los \\ módulos 2013 de Microsoft Lync Server \\ \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup. psm1 no se pueden cargar porque la ejecución de scripts está deshabilitada en este sistema. Para obtener más información, consulte about_Execution_Policies en https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Resolución** Para resolver este problema, inicie PowerShell como administrador y, a continuación, ejecute el siguiente comando:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Para obtener más información sobre la Directiva de ejecución, consulte [acerca de las directivas de ejecución](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Importación: error de módulo causado por una versión incorrecta de Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

El módulo conector de Skype empresarial online solo puede ejecutarse en Windows PowerShell 3,0. Si intenta importar el módulo en una versión anterior de PowerShell, el proceso de importación fallará con un mensaje de error similar a este:
  
  - **Error**: *Import-Module: la versión de PowerShell cargada es "2,0". El módulo: archivos \\ comunes de programa archivos de \\ \\ Microsoft Lync Server \\ 2013 \\ LyncOnlineConnector \\ LyncOnlineConnector. psd1 ' requiere una versión mínima de PowerShell de ' 3,0 ' para ejecutar. Verifica la instalación de PowerShell e inténtalo de nuevo.*

- **Resolución**: la única forma de corregir este problema es instalar Windows PowerShell 3,0, que está disponible en el centro de descarga de Microsoft en [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>No se puede realizar la autenticación moderna cuando se ha deshabilitado la autenticación básica de WinRM
<a name="BKMKWinRMBasicAuth"> </a>

La versión más reciente del módulo conector de Skype empresarial online usa la autenticación moderna, pero el cliente de administración remota de Windows (WinRM) subyacente debe estar configurado para permitir la autenticación básica.  La autenticación moderna usa tokens portadores que normalmente se pasan en la *autorización:* encabezado del portador. Windows PowerShell, en el que se ha creado PowerShell de Skype empresarial, no permite manipular este encabezado.  En su lugar, PowerShell de Skype empresarial usa la *autorización: encabezado básico* para pasar el token del portador.

Consulte [Descargar e instalar Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) para obtener instrucciones sobre cómo habilitar WinRM para la autenticación básica.

## <a name="failed-to-connect-to-live-id-server"></a>Error al conectarse al servidor de Live ID
<a name="BKMKFailedConnect"> </a>

Normalmente hay tres razones por las que el intento de conexión podría fallar con el mensaje de error siguiente:

  - **Error**: *Get-CsWebTicket: no se pudo conectar servidores de Live ID. Asegúrese de que el proxy está habilitado o que el equipo tiene conexión de red con servidores de Live ID.*

- **Resolución**: a menudo este error significa que el Asistente para el inicio de sesión de Microsoft Online Services no se está ejecutando. Para comprobar el estado de este servicio, ejecute el siguiente comando desde el símbolo del sistema de PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Si el servicio no se está ejecutando, inícielo con este comando:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Si el servicio se está ejecutando, es posible que se estén encontrando problemas con la conexión de red entre el equipo y el servidor de autenticación de Microsoft Live ID. Para comprobarlo, abra Internet Explorer y vaya a [ https://login.microsoftonline.com/ .](https://login.microsoftonline.com/.) Intente iniciar sesión en Microsoft 365 u Office 365 desde allí. Si esto no funciona, probablemente esté experimentando problemas de conexión de red.
  
    Normalmente, es posible que el URI de conexión del servidor de autenticación de Microsoft Live ID se haya configurado en un valor incorrecto. Si ya ha determinado que el Asistente para inicio de sesión se está ejecutando y no experimenta problemas de conectividad de red, puede deberse a este problema. En este caso, póngase en contacto con el soporte técnico de Microsoft.
  
## <a name="failed-to-load-live-id-module"></a>Error al cargar el módulo Live ID
<a name="BKMKFailedLoad"> </a>

Uno de los requisitos previos para usar PowerShell para administrar Skype empresarial online es instalar el ayudante para el inicio de sesión de Microsoft Online Services. Si el Asistente para inicio de sesión no está instalado, recibirá el siguiente mensaje de error al intentar establecer una sesión remota con Skype empresarial online:

- **Error**: *Get-CsWebTicket: no se puede cargar el módulo Live ID. Asegúrese de que está instalada la versión correcta del Asistente para inicio de sesión de Live ID.*

- **Solución**: el ayudante para el inicio de sesión de Microsoft Online Services está disponible en el centro de descarga de Microsoft en [Microsoft Online Services-ayudante para el inicio de sesión para profesionales de ti RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Error al iniciar sesión para el usuario
<a name="BKMKLogonFailed"> </a>

Al intentar establecer una conexión remota con Skype empresarial online, debe suministrar el nombre de usuario y la contraseña de una cuenta de usuario de Skype empresarial online válida. De lo contrario, se producirá un error de inicio de sesión y un mensaje de error similar al siguiente:

- **Error**: *Get-CsWebTicket: error de inicio de sesión del usuario ' kenmyer@litwareinc.com '. Cree un nuevo objeto PSCredential, asegurándose de que ha usado el nombre de usuario y la contraseña correctos.*

- **Resolución**: Si cree que está usando una cuenta de usuario válida y tiene la contraseña correcta, intente iniciar sesión de nuevo. Si esto no funciona, use las mismas credenciales e intente iniciar sesión en [https://login.microsoftonline.com/](https://login.microsoftonline.com/) . Si no puede iniciar sesión en ella, póngase en contacto con el soporte técnico de Microsoft. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>El usuario no tiene permiso para administrar este inquilino.
<a name="BKMKUserPermission"> </a>

No puede hacer una conexión de PowerShell remota toSkype a menos que sea miembro del grupo de administradores de inquilinos. Si no es así, se producirá un error en el intento de conexión y recibirá el siguiente mensaje de error:

- **Error**: *New-PSSession: [admin.vdomain.com] error al procesar datos desde el servidor remoto admin.vdomain.com con el siguiente mensaje de error: el usuario "User@foo.com" no tiene permiso para administrar este inquilino. Los permisos se pueden conceder asignando al usuario al rol RBAC adecuado. Para obtener más información, consulte [solución de problemas remota](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Resolución**: Si cree que es un miembro del grupo de administradores de inquilinos, tendrá que ponerse en contacto con el soporte técnico de Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>La posibilidad de conectar con el inquilino se ha deshabilitado en Skype empresarial online
<a name="BKMKAbilityConnect"> </a>

Para usar PowerShell para administrar Skype empresarial online, la propiedad EnableRemotePowerShellAccess de su Directiva de PowerShell de inquilino debe establecerse en `True` . Si no es así, la conexión fallará y recibirá el siguiente mensaje de error:

- **Error**: *New-PSSession: [admin.vdomain.com] error al procesar datos desde el servidor remoto admin.vdomain.com con el siguiente mensaje de error: se ha deshabilitado la capacidad de conectar con este inquilino mediante una sesión de PowerShell remota. Póngase en contacto con la ayuda de Lync para comprobar la Directiva de PowerShell de inquilino de este inquilino. Para obtener más información, consulte [solución de problemas remota](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Resolución**: Si ve este mensaje de error, tendrá que ponerse en contacto con el soporte técnico de Microsoft y habilitar el acceso remoto de PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Se ha superado el número máximo de shells simultáneos para este usuario en Skype empresarial online
<a name="BKMKMaxNumberShellsUser"> </a>

Cada administrador puede tener un máximo de tres conexiones remotas simultáneas a Skype empresarial online. Si tiene tres conexiones remotas de PowerShell en funcionamiento, cualquier intento de realizar una cuarta conexión simultánea producirá un error, con el siguiente mensaje de error:

- **Error**: *New-PSSession: [admin.vdomain.com] error al conectar con el servidor remoto admin.vdomain.com con el siguiente mensaje de error: el servicio WS-Management no puede procesar la solicitud. Se ha superado el número máximo de shells simultáneos para este usuario. Cierre las shells existentes o aumente la cuota de este usuario. Para obtener más información, consulte la [solución de problemas remotos] ( https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Resolución**: la única forma de resolver este problema es cerrar una o más de las conexiones anteriores. Cuando haya terminado con una sesión de Skype empresarial online, le recomendamos que use el cmdlet **Remove-PSSession** para finalizar la sesión. Esto le ayudará a evitar este problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Se ha superado el número máximo de shells simultáneos para este inquilino en Skype empresarial online
<a name="BKMKMaxNumberShellsTenant"> </a>

Aunque cada administrador puede tener hasta tres conexiones simultáneas a un inquilino de Skype empresarial online, ningún inquilino puede tener más de 20 conexiones simultáneas. Por ejemplo, seis administradores pueden tener tres sesiones abiertas cada una. Si un cuarto administrador intenta hacer más de 2 conexiones (lo que da como resultado un total de 21 conexiones simultáneas), se producirá un error en este intento, con el siguiente mensaje de error:
  
- **Error**: *New-PSSession: [admin.vdomain.com] error al conectar con el servidor remoto admin.vdomain.com con el siguiente mensaje de error: el servicio WS-Management no puede procesar la solicitud. Se ha superado el número máximo de shells simultáneos para este inquilino. Cierre las shells existentes o aumente la cuota de este inquilino. Para obtener más información, consulte la [solución de problemas remotos] ( https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Resolución**: la única forma de resolver este problema es cerrar una o más de las conexiones anteriores. Cuando haya terminado con una sesión de Skype empresarial online, le recomendamos que use el cmdlet **Remove-PSSession** para finalizar la sesión. Esto le ayudará a evitar este problema.  
 
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración de Skype empresarial online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 

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
description: Solucione problemas al crear una sesión remota de PowerShell para conectarse a Skype Empresarial Online, incluidos los errores importar-módulo, shell simultáneo, Id. de vida y permisos.
ms.openlocfilehash: 02952ea878424cb0b5e84337051c30660101d144
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238901"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosticar problemas de conexión con el conector de Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En este tema se proporciona información que le ayudará a diagnosticar y resolver problemas que pueden ocurrir al intentar crear una sesión remota de Microsoft PowerShell que se conecta a Skype Empresarial Online. Vea las secciones siguientes:
  
- [Error import-module causado por Windows PowerShell de ejecución](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Error import-module causado por una versión incorrecta de Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Se produce un error en la autenticación moderna cuando se ha deshabilitado la autenticación básica de WinRM](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Error al conectarse a Live ID Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Error al cargar el módulo Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Error al iniciar sesión para el usuario](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [El usuario no tiene permiso para administrar este espacio empresarial](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [La capacidad para conectarse al inquilino se ha deshabilitado en Skype Empresarial Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Se ha superado el número máximo de shells simultáneos para este usuario en Skype Empresarial Online](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Se ha superado el número máximo de shells simultáneos para este espacio empresarial Skype Empresarial online](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> De forma predeterminada, las sesiones de PowerShell se desalome después de 60 minutos. Para volver a conectar, tiene que cerrar la sesión e iniciar una nueva sesión de PowerShell. Recientemente se ha lanzado una nueva versión de [Skype Empresarial Online, módulo de Windows PowerShell (2046.123 - Publicada el 10/2/2019),](https://www.microsoft.com/download/details.aspx?id=39366)que incluye un nuevo cmdlet llamado **Enable-CsOnlineSessionForReconnection** que mitiga el problema de tiempo de espera de 60 minutos.
> La sesión de PowerShell se vuelve a conectar y se autentica, lo que permite que se vuelva a usar sin tener que iniciar una nueva instancia para volver a conectarse.



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module error causado por Windows PowerShell de ejecución
<a name="BKMKPowerShellExecutionPolicy"> </a>

La directiva de ejecución de PowerShell ayuda a determinar qué archivos de configuración se pueden cargar en la consola de PowerShell y qué scripts puede ejecutar un usuario desde esa consola. Como mínimo, el módulo Skype Empresarial Online Connector no se puede importar a menos que la directiva de ejecución se haya establecido en RemoteSigned. Si no lo ha hecho, recibirá el siguiente mensaje de error al intentar importar el módulo:
  
- **Error**: Importar-Módulo: Archivo C: Archivos de programa Archivos comunes <em> \\ \\ \\ Módulos de Microsoft Lync Server 2013 \\ \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 no se puede cargar porque la ejecución de scripts está deshabilitada en este sistema. Para obtener más información, vea about_Execution_Policies en https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Resolución** Para resolver este problema, inicie PowerShell como administrador y, a continuación, ejecute el siguiente comando:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Para obtener más información sobre la directiva de ejecución, vea [Acerca de las directivas de ejecución.](/powershell/module/microsoft.powershell.core/about/about_execution_policies)
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module error causado por una versión incorrecta de Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

El Skype Empresarial Online Connector solo se puede ejecutar en Windows PowerShell 3.0. Si intenta importar el módulo en una versión anterior de PowerShell, el proceso de importación producirá un error con un mensaje de error similar a este mensaje:
  
  - **Error**: *Import-Module: la versión de PowerShell cargada es "2.0". El módulo 'D: Archivos comunes de programa \\ \\ \\ Módulos de Microsoft Lync Server 2013 LyncOnlineConnectorLyncOnlineConnector.psd1' requiere una versión mínima de PowerShell de \\ \\ \\ "3.0" para ejecutarse. Compruebe la instalación de PowerShell e inténtelo de nuevo.*

- **Resolución:** La única forma de solucionar este problema es instalar Windows PowerShell 3.0, que está disponible en el Centro de descarga de Microsoft en [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>Se produce un error en la autenticación moderna cuando se ha deshabilitado la autenticación básica de WinRM
<a name="BKMKWinRMBasicAuth"> </a>

La última versión del módulo Skype Empresarial Online Connector usa la autenticación moderna, pero el cliente Windows administración remota (WinRM) subyacente debe configurarse para permitir la autenticación básica.  La autenticación moderna usa tokens de portador, que normalmente se pasan en el *encabezado Authorization: Bearer.* Windows PowerShell, en el que Skype Empresarial PowerShell está creado, no permite la manipulación de este encabezado.  En su lugar, Skype Empresarial PowerShell usa el *encabezado Authorization: Basic* para pasar el token de portador.

Vea [Descargar e instalar Windows PowerShell](./download-and-install-windows-powershell-5-1.md) instrucciones sobre cómo habilitar WinRM para autenticación básica.

## <a name="failed-to-connect-to-live-id-server"></a>Error al conectarse a Live ID Server
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> La autenticación de live id. ha quedado en desuso para Skype Conector en línea para empresas. Use el Teams powershell para administrar el espacio empresarial en línea. Al administrar entornos híbridos, actualice a la última actualización acumulativa o use la autenticación de oAuth.

Normalmente, hay tres motivos por los que el intento de conexión podría fallar con el siguiente mensaje de error:

  - **Error:** *Get-CsWebTicket: Error al conectar servidores de id. en directo. Asegúrese de que el proxy está habilitado o de que el equipo tiene conexión de red a servidores de id. en directo.*

- **Resolución:** a menudo este error significa que el Microsoft Online Services inicio de sesión no se está ejecutando. Puede comprobar el estado de este servicio ejecutando el siguiente comando desde el símbolo del sistema de PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Si el servicio no se está ejecutando, inicie el servicio con este comando:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Si el servicio se está ejecutando, es posible que tenga problemas con la conexión de red entre el equipo y el servidor de autenticación de Id. de Microsoft Live ID. Para comprobarlo, abra Internet Explorer y vaya a [ https://login.microsoftonline.com/ .](https://login.microsoftonline.com/.) Intente iniciar sesión en Microsoft 365 o Office 365 desde allí. Si se produce un error, es probable que tenga problemas de conexión de red.
  
    Con menor razón, es posible que el URI de conexión de Microsoft Live ID Authentication Server se haya configurado con el valor incorrecto. Si ya ha determinado que el Asistente para Sign-In está ejecutándose y que no está experimentando problemas de conectividad de red, este podría ser el problema. En este caso, póngase en contacto con el soporte técnico de Microsoft.
  
## <a name="failed-to-load-live-id-module"></a>Error al cargar el módulo Live ID
<a name="BKMKFailedLoad"> </a>

Uno de los requisitos previos para usar PowerShell para administrar Skype Empresarial Online es instalar el Asistente para Microsoft Online Services inicio de sesión. Si el Asistente para inicio de sesión no está instalado, recibirá el siguiente mensaje de error al intentar establecer una sesión remota con Skype Empresarial Online:

- **Error:** *Get-CsWebTicket: No se puede cargar el módulo Id. de live. Asegúrese de que la versión correcta del Asistente* para inicio de sesión de Live Id está instalada.

- **Resolución:** el Asistente Microsoft Online Services inicio de sesión está disponible en el Centro de descarga de Microsoft en Microsoft Online Services Sign-In Asistente para profesionales de TI [RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Error de inicio de sesión para el usuario
<a name="BKMKLogonFailed"> </a>

Al intentar realizar una conexión remota a Skype Empresarial Online, debe proporcionar el nombre de usuario y la contraseña de una cuenta de usuario Skype Empresarial en línea. Si no lo hace, el inicio de sesión producirá un error junto con un mensaje de error similar a este mensaje:

- **Error**: Get-CsWebTicket: Error de inicio de sesión para el usuario *'kenmyer@litwareinc.com'. Cree un nuevo objeto PSCredential para* asegurarse de que ha usado el nombre de usuario y la contraseña correctos.

- **Resolución:** Si cree que usa una cuenta de usuario válida y que tiene la contraseña correcta, intente iniciar sesión de nuevo. Si se produce un error, use las mismas credenciales e intente iniciar sesión en [https://login.microsoftonline.com/](https://login.microsoftonline.com/) . Si no puedes iniciar sesión allí, ponte en contacto con el soporte técnico de Microsoft. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>El usuario no tiene permiso para administrar este espacio empresarial
<a name="BKMKUserPermission"> </a>

No puede realizar una conexión remota de PowerShell aSkype para empresas Online a menos que sea miembro del grupo Administradores de inquilinos. Si no lo está, se producirá un error en el intento de conexión y recibirá el siguiente mensaje de error:

- **Error:** New-PSSession : [admin.vdomain.com] Error al procesar datos desde el servidor remoto admin.vdomain.com con el siguiente mensaje de error: el usuario "user@foo.com" no tiene permiso para administrar este *espacio empresarial. Los permisos se pueden conceder asignando al usuario el rol de RBAC adecuado. Para obtener más información, vea solución [de problemas remota.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Resolución:** Si cree que es o se supone que es un miembro del grupo Administradores de inquilinos, tendrá que ponerse en contacto con el soporte técnico de Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>La capacidad para conectarse al inquilino se ha deshabilitado en Skype Empresarial Online
<a name="BKMKAbilityConnect"> </a>

Para usar PowerShell para administrar Skype Empresarial Online, la propiedad EnableRemotePowerShellAccess de la directiva de PowerShell de inquilino debe establecerse en `True` . Si no es así, se producirá un error en la conexión y recibirá el siguiente mensaje de error:

- **Error:** New-PSSession : [admin.vdomain.com] El procesamiento de datos desde un servidor remoto admin.vdomain.com ha producido un error con el siguiente mensaje de error: se ha deshabilitado la capacidad de conectarse a este espacio empresarial mediante una sesión remota de *PowerShell. Póngase en contacto con la Ayuda de Lync para comprobar la directiva de Powershell de inquilino de este inquilino. Para obtener más información, vea solución [de problemas remota.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Resolución:** Si ve este mensaje de error, tendrá que ponerse en contacto con el soporte técnico de Microsoft y habilitar el acceso remoto de PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Se ha superado el número máximo de shells simultáneos para este usuario en Skype Empresarial Online
<a name="BKMKMaxNumberShellsUser"> </a>

A cada administrador se le permite un máximo de tres conexiones remotas simultáneas a Skype Empresarial Online. Si tiene tres conexiones remotas de PowerShell en ejecución, cualquier intento de realizar una cuarta conexión simultánea producirá un error, con el siguiente mensaje de error:

- **Error:** New-PSSession : [admin.vdomain.com] Error al conectarse al servidor remoto admin.vdomain.com con el siguiente mensaje de error: el servicio WS-Management no puede *procesar la solicitud. Se ha superado el número máximo de shells simultáneos para este usuario. Cierre los shells existentes o suba la cuota para este usuario. Para obtener más https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 información, vea [Solución remota de problemas](*

- **Resolución:** la única manera de resolver este problema es cerrar una o varias de las conexiones anteriores. Cuando haya terminado con una sesión Skype Empresarial online, le recomendamos que use el cmdlet **Remove-PSSession** para finalizar la sesión. Esto le ayudará a evitar este problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Se ha superado el número máximo de shells simultáneos para este espacio empresarial Skype Empresarial online
<a name="BKMKMaxNumberShellsTenant"> </a>

Aunque a cada administrador se le permite tener hasta tres conexiones simultáneas a un espacio empresarial de Skype Empresarial Online, no se permite que un único inquilino tenga más de 20 conexiones simultáneas. Por ejemplo, es posible que seis administradores tengan tres sesiones abiertas cada una. Si un cuarto administrador intenta realizar más de dos conexiones (lo que da como resultado un total de 21 conexiones simultáneas), este intento producirá un error, con el siguiente mensaje de error:
  
- **Error:** New-PSSession : [admin.vdomain.com] Error al conectarse al servidor remoto admin.vdomain.com con el siguiente mensaje de error: el servicio WS-Management no puede *procesar la solicitud. Se ha superado el número máximo de shells simultáneos para este espacio empresarial. Cierre los shells existentes o suba la cuota de este espacio empresarial. Para obtener más https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 información, vea [Solución remota de problemas](*

- **Resolución:** la única manera de resolver este problema es cerrar una o varias de las conexiones anteriores. Cuando haya terminado con una sesión Skype Empresarial online, le recomendamos que use el cmdlet **Remove-PSSession** para finalizar esa sesión. Esto le ayudará a evitar este problema.  
 
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  

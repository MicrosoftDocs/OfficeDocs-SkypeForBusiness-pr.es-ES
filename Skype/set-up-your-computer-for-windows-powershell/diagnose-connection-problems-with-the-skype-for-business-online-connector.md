---
title: "Diagnosticar problemas de conexión con el Skype para Business Connector en línea"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "Solucionar problemas al crear una sesión de PowerShell remota para conectar con Skype para los negocios en línea, incluyendo Import-Module, shell simultánea, Live ID y errores de permiso."
ms.openlocfilehash: 447b53784d316f07275e5c5ca877fe4b5289292d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosticar problemas de conexión con el Skype para Business Connector en línea

Este tema proporciona información que le ayudará a diagnosticar y resolver problemas que pueden producirse cuando intenta crear una sesión de Microsoft PowerShell remoto que se conecta a Skype para los negocios en línea. Consulte las siguientes secciones:
  
- [Error de importación módulo causada por la directiva de ejecución de Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Error de Import-Module causado por una versión incorrecta de Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [No se pudo conectar a Live ID de servidor](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [No se pudo cargar el módulo Live ID](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Inicio de sesión para el usuario](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [El usuario no tiene permiso para administrar este arrendatario](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Capacidad para conectarse a los inquilinos se deshabilitó en Skype para los negocios en línea](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Se superó el número máximo de shells simultáneos para este usuario en Skype para los negocios en línea](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [Se superó el número máximo de shells simultáneos para este arrendatario en Skype para los negocios en línea](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Error de importación módulo causada por la directiva de ejecución de Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

La directiva de ejecución de PowerShell ayuda a determinar qué archivos de configuración se pueden cargar en la consola de PowerShell y que un usuario de secuencias de comandos pueden ejecutar desde esa consola. Como mínimo, no se puede importar el Skype para el módulo de Business Connector en línea, a menos que se ha establecido la directiva de ejecución en RemoteSigned. Si no es así, recibirá el siguiente mensaje de error cuando intenta importar el módulo:
  
- **Error**: *Import-Module: archivo C:\\archivos de programa\\archivos comunes\\2013 de Microsoft Lync Server\\módulos\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 no se puede cargar porque está ejecutando las secuencias de comandos está deshabilitada en este sistema. Para obtener más información, vea about_Execution_Policies en https://go.microsoft.com/fwlink/?LinkID=135170.*

- **Resolución** Para resolver este problema, iniciar PowerShell como administrador y, a continuación, ejecute el siguiente comando:
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    Para obtener más información acerca de la directiva de ejecución, vea [Acerca de las directivas de ejecución](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Error de Import-Module causado por una versión incorrecta de Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

El Skype para el módulo de Business Connector en línea se puede ejecutar sólo en 3.0 de Windows PowerShell. Si intenta importar el módulo con una versión anterior de PowerShell, se producirá un error en el proceso de importación con un mensaje de error similar al siguiente:
  
  - **Error**: *Import-Module: la versión de la carga PowerShell es '2.0'. El módulo ' D:\\archivos de programa\\archivos comunes\\2013 de Microsoft Lync Server\\módulos\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requiere una versión mínima de PowerShell de '3.0' para ejecutar. Comprobar la instalación de la PowerShell y vuelva a intentarlo.*

- **Resolución**: la única manera de solucionar este problema es instalar Windows PowerShell 3.0, que está disponible en Microsoft Download Center en [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
## <a name="failed-to-connect-to-live-id-server"></a>No se pudo conectar a Live ID de servidor
<a name="BKMKFailedConnect"> </a>

Normalmente hay tres razones de por qué puede fallar el intento de conexión con el siguiente mensaje de error:

  - **Error**: *Get CsWebTicket: error al conectar a servidores de live id. Asegúrese de que el proxy está habilitado o equipo tiene conexión de red a servidores de id live.*

- **Resolución**: a menudo este error significa que no se está ejecutando el Asistente de inicio de sesión de Microsoft Online Services. Puede comprobar el estado de este servicio ejecutando el comando siguiente desde el símbolo del sistema de PowerShell: 
    ```
    Get-Service "msoidsvc"
    ```
    Si el servicio no se está ejecutando, inicie el servicio mediante este comando:
    ```
    Start-Service "msoidsvc"
    ```

    Si está ejecutando el servicio, podría encontrar problemas con la conexión de red entre el equipo y el servidor de autenticación de Microsoft Live ID. Para comprobar esto, abra Internet Explorer y vaya a [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Intente iniciar sesión en Office 365 desde allí. Si esto no funciona, probablemente está experimentando problemas de conexión de red.
  
    Con menos frecuencia, es posible que se haya configurado el URI de conexión para el servidor de autenticación de Microsoft Live ID a un valor incorrecto. Si ya ha determinado que el inicio de sesión Ayudante se está ejecutando y que no experimenta problemas de conectividad de red, esto puede ser el problema. En este caso, póngase en contacto con el soporte técnico de Office 365.
  
## <a name="failed-to-load-live-id-module"></a>No se pudo cargar el módulo Live ID
<a name="BKMKFailedLoad"> </a>

Uno de los requisitos previos para el uso de PowerShell para administrar Skype para los negocios en línea es instalar al Ayudante de inicio de sesión de Microsoft Online Services. Si el Ayudante de inicio de sesión no está instalado, recibirá el siguiente mensaje de error cuando intenta establecer una sesión remota con Skype para los negocios en línea:

- **Error**: *Get CsWebTicket: no se puede cargar el módulo Live Id. Asegúrate de seguro correcto se instala la versión del Asistente de inicio de sesión de Live Id.*

- **Resolución**: Asistente de inicio de sesión el Microsoft Online Services está disponible en Microsoft Download Center en el [Asistente Microsoft Online Services inicio de sesión para RTW de profesionales de TI](https://www.microsoft.com/en-us/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Inicio de sesión para el usuario
<a name="BKMKLogonFailed"> </a>

Cuando intenta establecer una conexión remota con Skype para los negocios en línea, debe proporcionar el nombre de usuario y la contraseña de un Skype válida para la cuenta de usuario de negocios en línea. Si no lo hace, se producirá un error de inicio de sesión junto con un mensaje de error similar al siguiente:

- **Error**: *Get CsWebTicket: error de inicio de sesión del usuario 'kenmyer@litwareinc.com'. Cree un nuevo objeto PSCredential, asegurándose de que se han utilizado el nombre de usuario y la contraseña.*

- **Resolución**: si piensa que está utilizando una cuenta de usuario válida y que tiene la contraseña correcta, iniciar sesión de nuevo. Si se produce un error, usar las mismas credenciales e intente iniciar sesión en [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Si no puede iniciar sesión allí, póngase en contacto con el soporte técnico de Office 365. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>El usuario no tiene permiso para administrar este arrendatario
<a name="BKMKUserPermission"> </a>

No puede realizar una toSkype de conexión remota de PowerShell para los negocios en línea, a menos que sea un miembro del grupo de administradores de inquilinos. Si no está, se producirá un error en el intento de conexión y recibirá el siguiente mensaje de error:

- **Error**: *New-PSSession: error al procesar los datos del servidor remoto admin.vdomain.com [admin.vdomain.com] con el siguiente mensaje de error: el usuario 'user@foo.com' no tiene permiso para administrar este arrendatario. Los permisos pueden concederse mediante la asignación de usuario a la función adecuada de RBAC. Para obtener más información, vea la [Resolución de problemas remota](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Resolución**: si piensa que está o se supone que un miembro del grupo de administradores de inquilinos, deberá ponerse en contacto con soporte técnico de Office 365.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Capacidad para conectarse a los inquilinos se deshabilitó en Skype para los negocios en línea
<a name="BKMKAbilityConnect"> </a>

Para usar PowerShell para administrar Skype para los negocios en línea, debe establecerse la propiedad EnableRemotePowerShellAccess de la directiva de PowerShell arrendatario en `True`. Si no es así, se producirá un error en la conexión y recibirá el siguiente mensaje de error:

- **Error**: *New-PSSession: error al procesar los datos del servidor remoto admin.vdomain.com [admin.vdomain.com] con el siguiente mensaje de error: se ha deshabilitado la capacidad de conectarse a este arrendatario mediante una sesión remota de PowerShell. Póngase en contacto con ayuda de Lync para comprobar la directiva de Powershell de inquilinos de este arrendatario. Para obtener más información, vea la [Resolución de problemas remota](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Resolución**: Si aparece este mensaje de error, deberá ponerse en contacto con el soporte técnico de Office 365 y obtener acceso de PowerShell remoto habilitado.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Se superó el número máximo de shells simultáneos para este usuario en Skype para los negocios en línea
<a name="BKMKMaxNumberShellsUser"> </a>

Cada administrador se permite un máximo de tres conexiones remotas simultáneas en Skype para los negocios en línea. Si tiene tres conexiones remotas de PowerShell para arriba y ejecutando, cualquier intento de realizar simultáneamente una cuarta conexión dará error con el mensaje de error siguiente:

- **Error**: *New-PSSession: error de conexión a servidor remoto admin.vdomain.com [admin.vdomain.com] con el siguiente mensaje de error: The WS-Management no puede procesar la solicitud. Se superó el número máximo de shells simultáneos para este usuario. Cierre shells existentes o aumentar la cuota para este usuario. Para obtener más información, consulte el [resolución remota de problemas](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*

- **Resolución**: la única forma de resolver este problema es cerrar uno o más de las conexiones anteriores. Cuando haya terminado con un Skype para la sesión de negocios en línea, le recomendamos que utilice el cmdlet **Remove-PSSession** para terminar la sesión. Esto ayudará a evitar este problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Se superó el número máximo de shells simultáneos para este arrendatario en Skype para los negocios en línea
<a name="BKMKMaxNumberShellsTenant"> </a>

Aunque cada administrador puede tener como máximo tres conexiones simultáneas a un Skype para inquilinos de negocios en línea, no solo usuario puede tener más de nueve conexiones simultáneas. Por ejemplo, tres administradores pueden tener cada uno tres sesiones abiertas. Si un administrador cuarto intenta realizar una conexión (resultantes de un total de 10 conexiones simultáneas), este intento producirá un error, con el siguiente mensaje de error:
  
- **Error**: *New-PSSession: error de conexión a servidor remoto admin.vdomain.com [admin.vdomain.com] con el siguiente mensaje de error: The WS-Management no puede procesar la solicitud. Se superó el número máximo de shells simultáneos para este arrendatario. Cierre shells existentes o aumentar la cuota para este arrendatario. Para obtener más información, consulte el [resolución remota de problemas](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*

- **Resolución**: la única forma de resolver este problema es cerrar uno o más de las conexiones anteriores. Cuando haya terminado con un Skype para la sesión de negocios en línea, le recomendamos que utilice el cmdlet **Remove-PSSession** para terminar esa sesión. Esto ayudará a evitar este problema.  
 
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


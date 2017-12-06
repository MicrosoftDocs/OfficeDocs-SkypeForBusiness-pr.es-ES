---
title: "Diagnosticar problemas de conexión con la Skype para Business Connector en línea"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
description: "Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors."
---

# Diagnosticar problemas de conexión con la Skype para Business Connector en línea

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](866fadfd-16e2-4134-95db-c6aed7678416.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/866fadfd-16e2-4134-95db-c6aed7678416). 
  
Este tema proporciona información que le ayudará a diagnosticar y resolver los problemas que pueden producirse cuando intenta crear una sesión remota Microsoft PowerShell que se conecta a Skype Empresarial Online. Vea las secciones siguientes:
  
- [Error de importación módulo causado por la directiva de ejecución de Windows PowerShell](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_PowerShellExecutionPolicy)
    
- [Error de importación módulo causados por la versión incorrecta de Windows PowerShell](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_IncorrectVersion)
    
- [Error al conectarse al servidor de ID de Live](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_FailedConnect)
    
- [Error al cargar el módulo de Live ID](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_FailedLoad)
    
- [Inicio de sesión para el usuario](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_LogonFailed)
    
- [El usuario no tiene permiso para administrar este inquilino](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_UserPermission)
    
- [Capacidad de conectar a inquilino se ha deshabilitado en Skype empresarial Online](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_AbilityConnect)
    
- [Se superó el número máximo de conchas simultáneas para este usuario de Skype empresarial Online](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_MaxNumberShellsUser)
    
- [Se superó el número máximo de conchas simultáneas este inquilino en Skype empresarial Online](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_MaxNumberShellsTenant)
    
## Error de importación módulo causado por la directiva de ejecución de Windows PowerShell
<a name="BKMK_PowerShellExecutionPolicy"> </a>

La directiva de ejecución de PowerShell ayuda a determinar qué archivos de configuración se pueden cargar en la consola de PowerShell y que secuencias de comandos de un usuario pueden ejecutar desde la consola. Como mínimo, la Módulo de conector de Skype Empresarial Online no se pueden importar a menos que se estableció la directiva de ejecución en RemoteSigned. Si no es así, recibirá el siguiente mensaje de error cuando intenta importar el módulo:
  
```
Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
```

Para resolver este problema, inicie PowerShell como administrador y, a continuación, ejecute el siguiente comando:
  
```
Set-ExecutionPolicy RemoteSigned
```

Para obtener más información acerca de la directiva de ejecución, vea [Acerca de las directivas de ejecución](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## Error de importación módulo causados por la versión incorrecta de Windows PowerShell
<a name="BKMK_IncorrectVersion"> </a>

El Módulo de conector de Skype Empresarial Online se puede ejecutar sólo en Windows PowerShell 3.0. Si intenta importar el módulo en una versión anterior de PowerShell, se producirá un error en el proceso de importación con un mensaje de error similar a este:
  
```
Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.
```

La única manera de solucionar este problema es instalar Windows PowerShell 3.0, que está disponible en la Centro de descarga de Microsoft en [http://www.microsoft.com/en-us/download/details.aspx?id=29939](http://www.microsoft.com/en-us/download/details.aspx?id=29939).
  
## Error al conectarse al servidor de ID de Live
<a name="BKMK_FailedConnect"> </a>

Normalmente, hay dos motivos por qué puede fallar el intento de conexión con el siguiente mensaje de error:
  
```
Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.
```

A menudo este error significa que no se está ejecutando el Microsoft Online Services - Ayudante para inicio de sesión. Puede comprobar el estado de este servicio, ejecute el siguiente comando desde el símbolo de PowerShell:
  
```
Get-Service "msoidsvc"
```

Si no se está ejecutando el servicio, inicie el servicio con este comando:
  
```
Start-Service "msoidsvc"
```

Si está ejecutando el servicio, puede encontrar problemas con la conexión de red entre el equipo y el servidor de autenticación de Microsoft Live ID. Para comprobarlo, abra Internet Explorer y vaya a [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Intente iniciar sesión en Office 365 desde allí. Si esto no funciona, probablemente está experimentando problemas de conexión de red.
  
Menos frecuencia, es posible que se ha configurado el URI de conexión para Microsoft Live ID de autenticación de servidor para el valor de error. Si ya ha determinado que está ejecutando el inicio de sesión de asistente y que no está experimentando problemas de conectividad de red, puede ser el problema. En este caso, póngase en contacto con Office 365 soporte técnico.
  
## Error al cargar el módulo de Live ID
<a name="BKMK_FailedLoad"> </a>

Uno de los requisitos previos para usar PowerShell para administrar Skype Empresarial Online es instalar la Microsoft Online Services - Ayudante para inicio de sesión. Si no está instalado el Asistente para inicio de sesión, recibirá el siguiente mensaje de error cuando intenta establecer una sesión remota con Skype Empresarial Online:
  
```
Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.
```

La Microsoft Online Services - Ayudante para inicio de sesión está disponible en la Centro de descarga de Microsoft al [Asistente Microsoft Online Services inicio de sesión para RTW de profesionales de TI](https://www.microsoft.com/en-us/download/details.aspx?id=28177).
  
## Inicio de sesión para el usuario
<a name="BKMK_LogonFailed"> </a>

Cuando intenta conectarse a Skype Empresarial Online remoto, debe proporcionar el nombre de usuario y contraseña de una cuenta de usuario válida Skype Empresarial Online. Si no lo hace, se producirá un error de inicio de sesión junto con un mensaje de error similar al siguiente:
  
```
Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.
```

Si cree que está usando una cuenta de usuario válida y tiene la contraseña correcta, intente iniciar la sesión de nuevo. Si se produce un error, usar las mismas credenciales e intente iniciar sesión en [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Si no puede iniciar sesión allí, póngase en contacto con Office 365 soporte técnico.
  
## El usuario no tiene permiso para administrar este inquilino
<a name="BKMK_UserPermission"> </a>

No puede realizar una conexión de remoto PowerShell aSkype Empresarial Online a menos que sea miembro del grupo de administradores de inquilinos. Si no es así, se producirá un error en el intento de conexión y recibirá el siguiente mensaje de error:
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the about_Remote_Troubleshooting Help topic.
```

Si cree que sean o se supone que un miembro del grupo de administradores de inquilinos, deberá ponerse en contacto con Office 365 soporte técnico.
  
## Capacidad de conectar a inquilino se ha deshabilitado en Skype empresarial Online
<a name="BKMK_AbilityConnect"> </a>

Para usar PowerShell para administrar Skype Empresarial Online, la propiedad EnableRemotePowerShellAccess de la directiva de PowerShell de inquilinos debe establecerse en  `True`. Si no es así, se producirá un error en la conexión y recibirá el siguiente mensaje de error:
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

Si ve este mensaje de error, deberá ponerse en contacto Office 365 soporte técnico y obtener acceso remoto PowerShell habilitado.
  
## Se superó el número máximo de conchas simultáneas para este usuario de Skype empresarial Online
<a name="BKMK_MaxNumberShellsUser"> </a>

Cada administrador se permite un máximo de tres conexiones remotas simultáneas a Skype Empresarial Online. Si tiene conexiones de tres remoto PowerShell hacia arriba y ejecutando, cualquier intento de realizar una cuarta simultáneas conexión producirá, con el siguiente mensaje de error:
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the about_Remote_Troubleshooting Help topic.
```

La única manera de resolver este problema es cerrar una o varias de las conexiones anterior. Cuando haya terminado con una sesión de Skype Empresarial Online, le recomendamos que use el cmdlet **Remove-PSSession** para terminar la sesión. Esto le ayudará a evitar este problema.
  
## Se superó el número máximo de conchas simultáneas este inquilino en Skype empresarial Online
<a name="BKMK_MaxNumberShellsTenant"> </a>

Aunque cada administrador puede tener hasta tres conexiones simultáneas a un inquilino Skype Empresarial Online, inquilino solo no puede tener más de nueve conexiones simultáneas. Por ejemplo, tres administradores pueden cada una tiene tres sesiones abiertas. Si el Administrador de un cuarto intenta conectarse (resultado: un total de 10 conexiones simultáneas), este intento producirá, con el siguiente mensaje de error:
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

La única manera de resolver este problema es cerrar una o varias de las conexiones anterior. Cuando haya terminado con una sesión de Skype Empresarial Online, le recomendamos que use el cmdlet **Remove-PSSession** para terminar la sesión. Esto le ayudará a evitar este problema.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  


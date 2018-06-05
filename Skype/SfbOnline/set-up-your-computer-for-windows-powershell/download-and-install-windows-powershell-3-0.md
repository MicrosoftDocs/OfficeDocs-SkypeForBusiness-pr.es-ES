---
title: Descargue e instale Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Descargar, instalar y, a continuación, use Windows PowerShell 3.0 para crear una sesión remota de PowerShell que se conecta a Skype para profesionales en línea.
ms.openlocfilehash: 6679e9749efd6ee09a7c26f383b1b411caadb43e
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19493996"
---
# <a name="download-and-install-windows-powershell-30"></a>Descargue e instale Windows PowerShell 3.0

Si está utilizando Windows 8.1, Windows 8, Windows Server 2012 R2 o Windows Server 2012, ya debe tener Windows PowerShell 3.0. Que es debido a que esta aplicación viene preinstalada con los sistemas operativos. 
  
Si ejecuta Windows 7 o Windows Server 2008 R2, es posible que también esté ejecutando Windows PowerShell 3.0. Sin embargo, también es posible que puede es posible que esté ejecutando versión 2.0 en su lugar, la versión que se incluía originalmente con estos sistemas operativos. Para determinar qué versión de Microsoft PowerShelll usa, realice lo siguiente en el equipo con Windows 7 o Windows Server 2008 R2:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**y, a continuación, haga clic en **Windows PowerShell**.
    
2. En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:
    
    ```
   Get-Host | Select-Object Version
   ```

3. A continuación, se debe mostrar información similar a la siguiente en la ventana de la consola:
    
    ```
    Version
    -------
    3.0
    ```

    Si el número de versión devuelto es 3.0, a continuación, ejecuta Windows PowerShell 3.0. Si el número de versión devuelto no es 3.0, necesitará instalar Windows PowerShell 3.0. Puede descargar Windows Management Framework 3.0, que incluye Windows PowerShell 3.0, desde el [Centro de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
Una vez haya comprobado que Windows PowerShell 3.0 está instalado, debe asegurarse de que PowerShell se ha configurado para la ejecución de secuencias de comandos remotos. Para ello, inicie PowerShell como administrador. En Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, realice lo siguiente:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**, haga clic en **Windows PowerShell**y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Si ejecuta Windows 8, complete este procedimiento en su lugar:
  
1. Obtener acceso a la barra de accesos, haga clic en **Buscar**y, a continuación, haga clic en **Windows PowerShell**. Puede tener acceso rápidamente a la barra de accesos en cualquier equipo de Windows 8 (pantalla táctil o sin pantalla táctil) manteniendo presionada la tecla de Windows y presionando C.
    
2. En la barra de herramientas en la parte inferior de la pantalla, haga clic en **Ejecutar como administrador**.
    
3. Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Después de que se está ejecutando PowerShell, debe cambiar la directiva de ejecución para permitir la ejecución de secuencias de comandos remotos. En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Cuando se ejecuta el comando anterior, es posible que reciba el siguiente mensaje de error: > *Set-ExecutionPolicy: acceso a la clave del registro ' HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' ha sido denegado.* Normalmente, este mensaje de error se produce si no se está ejecutando PowerShell con credenciales de administrador. Cierre la sesión de PowerShell e iniciar una sesión de nuevo como administrador.
 
Para comprobar que se ha configurado correctamente la directiva de ejecución, escriba lo siguiente en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:
  
```
Get-ExecutionPolicy
```

Si se obtiene el siguiente valor, a continuación, todo lo que se ha configurado correctamente:
  
```
RemoteSigned
```

Si no se está ejecutando actualmente Windows PowerShell 3.0, también debe descargar e instalar Windows Management Framework 3.0 desde Microsoft Download Center. Se trata de un paquete de instalación que incluye Windows PowerShell 3.0 y administración remota de Windows (WinRM) 3.0. Este paquete de instalación puede ser necesario si ejecuta Windows 7 y aún no ha actualizado a Windows PowerShell 3.0. Si ejecuta Windows Server 2012, Windows Server 2012 R2, Windows 8 o Windows 8.1, no debería haber necesidad de instalar Windows PowerShell 3.0. Windows PowerShell 3.0 viene preinstalado en dichos sistemas operativos.
  
Antes de instalar Windows Management Framework 3.0:
  
- Asegúrese de que ha descargado la versión correcta del paquete de instalación. Si está ejecutando la versión de 64 bits de Windows 7, descargue el archivo Windows6.1-KB2506143-x64.msu. Si está ejecutando la versión de 32 bits de Windows 7, descargue el archivo Windows6.1-KB2506143-x86.msu.
    
- Si ejecuta Windows 7 en su equipo, asegúrese de que ha instalado Service Pack 1 de Windows 7.
    
Si no está seguro de qué versión de Windows está ejecutando o no está seguro de si ha instalado el Service Pack 1 de Windows 7, haga clic en **Inicio**, haga clic en **equipo**y, a continuación, haga clic en **Propiedades**. Esta información se notificará en el cuadro de diálogo del sistema.
  
Para instalar Windows Management Framework 3.0, complete el siguiente procedimiento:
  
1. Haga doble clic en el. En el archivo de instalación MSU ( **Windows6.1-KB2506143-x64.msu** o **Windows6.1-KB2506143-x86.msu**).
    
2. En el Asistente de descargar e instalar actualizaciones, en la página **Lea estos términos de licencia (1 de 1)** , haga clic en ****.
    
3. Una vez finalizada la instalación, haga clic en **Reiniciar ahora** para reiniciar el equipo.
    
Una vez se haya reiniciado el equipo, compruebe que puede iniciar Windows PowerShell y que la aplicación se puede ejecutar bajo credenciales administrativas. Para hacer esto:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**, haga clic en **Windows PowerShell** y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. Si el Control de cuentas de usuario aparece el cuadro de diálogo, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Cuando aparezca la consola de PowerShell, a continuación, debe comprobar que el servicio WinRM se está ejecutando y se ha configurado correctamente. Para comprobar que se está ejecutando el servicio, escriba el siguiente comando en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:
  
```
Get-Service winrm
```

A continuación, se mostrará información sobre el servicio WinRM en pantalla:
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

Si el servicio de estado no es igual a "Ejecutar", inicie el servicio WinRM por escribiendo el siguiente comando y, a continuación, presione ENTRAR:
  
```
Start-Service winrm
```

Una vez que haya iniciado el servicio, ejecute el siguiente comando para asegurarse de que WinRM usa la autenticación básica:
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Se mostrará en la pantalla información similar a la siguiente:
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

Si la autenticación básica se ha establecido en true, a continuación, estará listo usar PowerShell para conectarse a Skype para profesionales en línea.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>See also
[Configurar el equipo para Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 
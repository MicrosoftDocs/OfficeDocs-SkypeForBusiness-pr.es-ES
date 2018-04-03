---
title: Descargar e instalar Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
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
description: Descargar, instalar y, a continuación, utilice 3.0 de Windows PowerShell para crear una sesión de PowerShell remoto que se conecta a Skype para los negocios en línea.
ms.openlocfilehash: 56e0c885d25510156b7336e63f83c89c29b07fb4
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="download-and-install-windows-powershell-30"></a>Descargar e instalar Windows PowerShell 3.0

Si utilizas Windows 8.1, Windows 8, Windows Server 2012 R2 o Windows Server 2012, ya debe tener 3.0 de Windows PowerShell. Eso es porque esta aplicación viene preinstalada con esos sistemas operativos. 
  
Si está ejecutando Windows 7 o Windows Server 2008 R2, es posible que también esté ejecutando 3.0 de Windows PowerShell. Sin embargo, también es posible que se puede ejecutar la versión 2.0 en su lugar, la versión que se incluía originalmente con esos sistemas operativos. Para determinar qué versión de Microsoft PowerShelll usa, realice lo siguiente en el equipo de Windows 7 o Windows Server 2008 R2:
  
1. Haga clic en **Inicio**, seleccione **Todos los programas**, **Accesorios**, **Windows PowerShell**y, a continuación, haga clic en **Windows PowerShell**.
    
2. En la consola de PowerShell, escriba el comando siguiente y presione ENTRAR:
    
    ```
   Get-Host | Select-Object Version
   ```

3. A continuación, se debe mostrar la información similar al siguiente en la ventana de la consola:
    
    ```
    Version
    -------
    3.0
    ```

    Si el número de versión devuelto es 3.0, significa que está ejecutando Windows PowerShell 3.0. Si el número de versión devuelto no es 3.0, necesitará instalar Windows PowerShell 3.0. Windows Management Framework 3.0, que incluye Windows PowerShell 3.0, se puede descargar desde el [Centro de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
Después de comprobar que está instalado Windows PowerShell 3.0, debe asegurarse de que PowerShell se ha configurado para ejecutar secuencias de comandos remotos. Para ello, iniciar PowerShell como administrador. En Windows 7, Windows Server 2008 R2, Windows Server 2012 o 2012 R2 de Windows Server, realice lo siguiente:
  
1. Haga clic en **Inicio**, seleccione **Todos los programas**, **Accesorios**, haga clic en **Windows PowerShell**, haga **De Windows PowerShell**y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Si está ejecutando Windows 8, realice este procedimiento en su lugar:
  
1. Tener acceso a la barra de encantos, haga clic en **Buscar**y, a continuación, haga clic en **Windows PowerShell**. Se puede acceder rápidamente a la barra de encantos en cualquier equipo Windows 8 (pantalla táctil o sin pantalla táctil) manteniendo presionada la tecla Windows y presionando C.
    
2. En la barra de herramientas en la parte inferior de la pantalla, haga clic en **Ejecutar como administrador**.
    
3. Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Después de PowerShell se ejecuta, debe cambiar la directiva de ejecución para permitir la ejecución de secuencias de comandos remotos. En la consola de PowerShell, escriba el comando siguiente y presione ENTRAR:
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
Para comprobar que se ha configurado correctamente la directiva de ejecución, escriba lo siguiente en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:
  
```
Get-ExecutionPolicy
```

Si se obtendrá el valor siguiente, a continuación, todo lo que se ha configurado correctamente:
  
```
RemoteSigned
```

Si no se está ejecutando actualmente Windows PowerShell 3.0, también deberá descargar e instalar Windows Management Framework 3.0 desde Microsoft Download Center. Se trata de un paquete de instalación que incluye 3.0 de Windows PowerShell y administración remota de Windows (WinRM) 3.0. Este paquete de instalación puede ser necesario si ejecutan Windows 7 y aún no ha actualizado a Windows PowerShell 3.0. Si está ejecutando Windows Server 2012, 2012 R2 de Windows Server, Windows 8 o Windows 8.1, no deben ser necesidad de instalar Windows PowerShell 3.0. 3.0 de Windows PowerShell viene preinstalado en esos sistemas operativos.
  
Antes de instalar Windows Management Framework 3.0:
  
- Asegúrese de que ha descargado la versión correcta del paquete de instalación. Si está ejecutando la versión de 64 bits de Windows 7, descargue el archivo Windows6.1-KB2506143-x64.msu. Si está ejecutando la versión de 32 bits de Windows 7, descargue el archivo Windows6.1-KB2506143-x86.msu.
    
- Si está ejecutando Windows 7 en su equipo, asegúrese de que ha instalado el Service Pack 1 de Windows 7.
    
Si no está seguro de qué versión de Windows está ejecutando o no está seguro si ha instalado el Service Pack 1 de Windows 7, haga clic en **Inicio**, haga clic en **equipo**y, a continuación, haga clic en **Propiedades**. Esta información se registrará en el cuadro de diálogo del sistema.
  
Para instalar Windows Management Framework 3.0, siga el procedimiento siguiente:
  
1. Haga doble clic en el. Archivo de instalación de MSU ( **archivo Windows6.1-KB2506143-x86.msu**o **Windows6.1-KB2506143-x64.msu** ).
    
2. En el Asistente de descargar e instalar actualizaciones, en la página **Lea los términos de licencia (1 de 1)** , haga clic en ****.
    
3. Cuando la instalación esté completa, haga clic en **Reiniciar ahora** para reiniciar el equipo.
    
Una vez reiniciado el equipo, compruebe que puede iniciar Windows PowerShell y que la aplicación se puede ejecutar con credenciales administrativas. Para hacer esto:
  
1. Haga clic en **Inicio**, seleccione **Todos los programas**, **Accesorios**, haga clic en **Windows PowerShell**, haga **De Windows PowerShell** y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. Si el Control de cuenta de usuario aparecerá el cuadro de diálogo, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Cuando aparezca la consola de PowerShell, a continuación, debe comprobar que el servicio WinRM se está ejecutando y que se ha configurado correctamente. Para comprobar que el servicio se está ejecutando, escriba el comando siguiente en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:
  
```
Get-Service winrm
```

A continuación, se mostrará información sobre el servicio WinRM en pantalla:
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

Si el servicio de estado no es igual a "Ejecutar", escriba el comando siguiente y presione ENTRAR para iniciar el servicio de WinRM:
  
```
Start-Service winrm
```

Una vez iniciado el servicio, ejecute el siguiente comando para asegurarse de que WinRM está utilizando autenticación básica:
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Se mostrará información similar a la siguiente pantalla:
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

Si la autenticación básica se ha establecido en true, y esté listo para usar PowerShell para conectar con Skype para los negocios en línea.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>See also
[Configurar el equipo para Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 
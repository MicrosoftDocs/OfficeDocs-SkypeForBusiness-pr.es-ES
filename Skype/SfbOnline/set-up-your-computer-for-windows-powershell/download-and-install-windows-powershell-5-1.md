---
title: Descargar e instalar Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
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
- LIL_Placement
description: Descargue, instale y, a continuación, use Windows PowerShell 5.1 para crear una sesión de PowerShell remota que se conecte a Skype Empresarial Online.
ms.openlocfilehash: 64d1ed1b3e3031f5186a09289ab6e1d9088840cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029101"
---
# <a name="download-and-install-windows-powershell-51"></a>Descargar e instalar Windows PowerShell 5.1

Si usa la Actualización de aniversario de Windows 10 o Windows Server 2016, ya debería tener Windows PowerShell 5.1. Esto se debe a que esta aplicación viene preinstalada con esos sistemas operativos.
  
Para determinar qué versión de Microsoft PowerShelll está usando, haga lo siguiente en su equipo con Windows 7 o Windows Server 2008 R2 o Windows Server 2012:
  
1. Haga clic en **Inicio,** **en Todos los programas,** en  **Accesorios,** Windows PowerShell clic en **Windows PowerShell.**
    
2. En la consola de PowerShell, escriba el comando siguiente y, después, presione ENTRAR:
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. A continuación, se mostrará información similar a la siguiente en la ventana de consola:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Si el número de versión devuelto es 5.1, entonces está ejecutando Windows PowerShell 5.1. Si el número de versión devuelto no es 5.1, tendrá que instalar Windows PowerShell 5.1. Puede descargar Windows Management Framework 5.1, que incluye Windows PowerShell 5.1, desde el [Centro de descarga de Microsoft.](https://www.microsoft.com/download/details.aspx?id=54616)
  
Después de comprobar que Windows PowerShell 5.1 está instalado, debe asegurarse de que PowerShell se ha configurado para ejecutar scripts remotos. Para ello, inicie PowerShell como administrador. En Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, haga lo siguiente:
  
1. Haga clic **en** Inicio,  **en Todos** los programas, en Accesorios, en **Windows PowerShell,** haga clic con el botón derecho en **Windows PowerShell** y, a continuación, haga clic en Ejecutar **como administrador.**
    
2. Si aparece **el cuadro de diálogo Control** de cuentas de usuario, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Si está ejecutando Windows 8, complete este procedimiento en su lugar:
  
1. Acceda a la barra de accesos, haga clic **en Buscar** y, a continuación, haga clic con el **botón Windows PowerShell.** Puede acceder rápidamente a la barra de accesos en cualquier equipo con Windows 8 (pantalla táctil o no táctil) manteniendo presionada la tecla Windows y presionando C.
    
2. En la barra de herramientas de la parte inferior de la pantalla, haga clic **en Ejecutar como administrador.**
    
3. Si aparece **el cuadro de diálogo Control** de cuentas de usuario, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Después de ejecutar PowerShell, debe cambiar la directiva de ejecución para permitir la ejecución de scripts remotos. En la consola de PowerShell, escriba el comando siguiente y, después, presione ENTRAR:
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Cuando ejecute el comando anterior, es posible que reciba el siguiente mensaje de error: > *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE \\ SOFTWARE \\ Microsoft \\ PowerShell \\ 1 \\ ShellIds \\ Micrsoft.PowerShell' se ha denegado.* Este mensaje de error suele aparecer si no está ejecutando PowerShell con credenciales de administrador. Cierre la sesión de PowerShell e inicie una nueva sesión como administrador.
 
Para comprobar que la directiva de ejecución se ha configurado correctamente, escriba lo siguiente en el símbolo del sistema de PowerShell y, después, presione ENTRAR:
  
```PowerShell
Get-ExecutionPolicy
```

Si vuelve a obtener el siguiente valor, todo se ha configurado correctamente:
  
`RemoteSigned`

Si actualmente no está ejecutando Windows PowerShell 5.1, también necesitará descargar e instalar Windows Management Framework 5.1 desde el Centro de descarga de Microsoft. Este es un paquete de instalación que incluye Windows PowerShell 5.1 y Windows Remote Management (WinRM) 3.0. Este paquete de instalación podría ser necesario si, por ejemplo, ejecuta Windows 7 SP1 y aún no se ha actualizado a Windows PowerShell 5.1. Si ejecuta la Actualización de aniversario de Windows Server 2016 o Windows 10, no es necesario instalar Windows PowerShell 5.1. Windows PowerShell 5.1 viene preinstalado en esos sistemas operativos.
  
Antes de instalar Windows Management Framework 5.1:
  
- Asegúrese de que ha descargado la versión correcta del paquete de instalación. Si está ejecutando la versión de 64 bits de Windows 7 SP1, descargue el archivo Win7AndW2K8R2-KB3191566-x64.ZIP. Si está ejecutando la versión de 32 bits de Windows 7, descargue el archivo Win7-KB3191566-x86.ZIP.
    
- Si está ejecutando Windows 7 en su equipo, asegúrese de que ha instalado Windows 7 Service Pack 1.

Si no está seguro de qué versión de Windows está ejecutando, o no está seguro de si ha instalado Windows 7 Service Pack 1, haga clic en **Inicio,** haga clic con el botón secundario en Equipo y, a continuación, haga clic en **Propiedades.** Esta información se mostrará en el cuadro de diálogo Sistema.
  
Para instalar Windows Management Framework 5.1, complete el procedimiento descrito en [Instalar y configurar WMF 5.1.](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure)
  
Después de reiniciar el equipo, compruebe que Windows PowerShell se puede iniciar y que la aplicación se puede ejecutar con credenciales administrativas. Para ello:
  
1. Haga **clic en** Inicio, en **Todos** los programas, en **Accesorios,** en **Windows PowerShell,** haga clic con el botón derecho en Windows PowerShell y, a **continuación,** haga clic **en Ejecutar como administrador.**
    
2. Si aparece el cuadro de diálogo Control de cuentas de usuario, haga clic en **Sí** para comprobar que quiere ejecutar PowerShell con credenciales de administrador.
    
Cuando aparezca la consola de PowerShell, deberá comprobar que el servicio WinRM se está ejecutando y que se ha configurado correctamente. Para comprobar que el servicio se está ejecutando, escriba el comando siguiente en el símbolo del sistema de PowerShell y, después, presione ENTRAR:
  
```PowerShell
Get-Service winrm
```

La información sobre el servicio WinRM se mostrará entonces en pantalla:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Si el estado del servicio no es igual a "En ejecución", inicie el servicio WinRM escribiendo el comando siguiente y presionando ENTRAR:
  
```PowerShell
Start-Service winrm
```

Una vez que se haya iniciado el servicio, ejecute el siguiente comando para asegurarse de que WinRM está usando autenticación básica:
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Información similar a la siguiente se mostrará en pantalla:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Si se ha establecido la autenticación básica en true, ya está listo para usar PowerShell para conectarse a Skype Empresarial Online.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 

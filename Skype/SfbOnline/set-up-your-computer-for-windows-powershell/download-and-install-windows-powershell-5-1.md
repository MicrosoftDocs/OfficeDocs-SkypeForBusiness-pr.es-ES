---
title: Descargue e instale Windows PowerShell 5.1
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Descargar, instalar y, a continuación, use Windows PowerShell 5.1 para crear una sesión remota de PowerShell que se conecta a Skype para profesionales en línea.
ms.openlocfilehash: 63f4924a30bfc910679f23a617cc5252ecc5b6aa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198072"
---
# <a name="download-and-install-windows-powershell-51"></a>Descargue e instale Windows PowerShell 5.1

Si está utilizando Windows 10 aniversario Update o Windows Server 2016, ya debe tener Windows PowerShell 5.1. Que es debido a que esta aplicación viene preinstalada con los sistemas operativos.
  
Para determinar qué versión de Microsoft PowerShelll usa, realice lo siguiente en el equipo de Windows Server 2008 R2 o Windows Server 2012 o Windows 7:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**y, a continuación, haga clic en **Windows PowerShell**.
    
2. En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:
    
   ```
   Get-Host | Select-Object Version
   ```

3. A continuación, se debe mostrar información similar a la siguiente en la ventana de la consola:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Si el número de versión devuelto es 5.1, a continuación, ejecuta Windows PowerShell 5.1. Si el número de versión devuelto no es 5.1, necesitará instalar Windows PowerShell 5.1. Windows Management Framework 5.1, que incluye Windows PowerShell 5.1, puede descargar desde el [Centro de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).
  
Una vez haya comprobado que está instalado Windows PowerShell 5.1, debe asegurarse de que PowerShell se ha configurado para la ejecución de secuencias de comandos remotos. Para ello, inicie PowerShell como administrador. En Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, realice lo siguiente:
  
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
  
`RemoteSigned`

Si no se está ejecutando actualmente Windows PowerShell 5.1, también debe descargar e instalar Windows Management Framework 5.1 desde Microsoft Download Center. Se trata de un paquete de instalación que incluye Windows PowerShell 5.1 y administración remota de Windows (WinRM) 3.0. Este paquete de instalación puede ser necesario si, por ejemplo, está ejecutando Windows 7 SP1 y aún no ha actualizado a Windows PowerShell 5.1. Si ejecuta Windows Server 2016, o una actualización de Windows 10 aniversario, no debería haber necesidad de instalar Windows PowerShell 5.1. Windows PowerShell 5.1 viene preinstalado en dichos sistemas operativos.
  
Antes de instalar Windows Management Framework 5.1:
  
- Asegúrese de que ha descargado la versión correcta del paquete de instalación. Si está ejecutando la versión de 64 bits de Windows 7 SP1, descargue el archivo Win7AndW2K8R2-KB3191566-x64.ZIP. Si está ejecutando la versión de 32 bits de Windows 7, descargue el archivo Win7-KB3191566-x86.ZIP.
    
- Si ejecuta Windows 7 en su equipo, asegúrese de que ha instalado Service Pack 1 de Windows 7.

Si no está seguro de qué versión de Windows está ejecutando o no está seguro de si ha instalado el Service Pack 1 de Windows 7, haga clic en **Inicio**, haga clic en **equipo**y, a continuación, haga clic en **Propiedades**. Esta información se notificará en el cuadro de diálogo del sistema.
  
Para instalar Windows Management Framework 5.1, complete el procedimiento de [instalación y configuración de WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)
  
Una vez se haya reiniciado el equipo, compruebe que puede iniciar Windows PowerShell y que la aplicación se puede ejecutar bajo credenciales administrativas. Para hacer esto:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**, haga clic en **Windows PowerShell** y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. Si el Control de cuentas de usuario aparece el cuadro de diálogo, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Cuando aparezca la consola de PowerShell, a continuación, debe comprobar que el servicio WinRM se está ejecutando y se ha configurado correctamente. Para comprobar que se está ejecutando el servicio, escriba el siguiente comando en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:
  
```
Get-Service winrm
```

A continuación, se mostrará información sobre el servicio WinRM en pantalla:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Si el servicio de estado no es igual a "Ejecutar", inicie el servicio WinRM por escribiendo el siguiente comando y, a continuación, presione ENTRAR:
  
```
Start-Service winrm
```

Una vez que haya iniciado el servicio, ejecute el siguiente comando para asegurarse de que WinRM usa la autenticación básica:
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Se mostrará en la pantalla información similar a la siguiente:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Si la autenticación básica se ha establecido en true, a continuación, estará listo usar PowerShell para conectarse a Skype para profesionales en línea.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 

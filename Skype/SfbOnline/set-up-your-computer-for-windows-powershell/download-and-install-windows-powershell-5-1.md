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
description: Descargue, instale y, a continuación, use Windows PowerShell 5.1 para crear una sesión remota de PowerShell que se conecte a Skype Empresarial Online.
ms.openlocfilehash: af3d4346b699c6511b17b0cce0e881c91ceb927cb4a9e5cba57674fb96751b77
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308041"
---
# <a name="download-and-install-windows-powershell-51"></a>Descargar e instalar Windows PowerShell 5.1

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Si usa la actualización Windows 10 aniversario o Windows Server 2016, ya debería tener Windows PowerShell 5.1. Esto se debe a que esta aplicación viene preinstalada con esos sistemas operativos.
  
Para determinar qué versión de Microsoft PowerShelll usa, haga lo siguiente en su Windows 7 o Windows Server 2008 R2 o Windows Server 2012 equipo:
  
1. Haga **clic en** Inicio, en Todos los **programas,** en Accesorios, en **Windows PowerShell** y, a continuación, haga clic **en Windows PowerShell**. 
    
2. En la consola de PowerShell, escriba el comando siguiente y, después, presione ENTRAR:
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. La información similar a la siguiente debería mostrarse en la ventana de la consola:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Si el número de versión devuelto es 5.1, está ejecutando Windows PowerShell 5.1. Si el número de versión devuelto no es 5.1, tendrá que instalar Windows PowerShell 5.1. Puede descargar Windows Management Framework 5.1, que incluye Windows PowerShell 5.1, desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=54616).
  
Después de comprobar que Windows PowerShell 5.1 está instalado, debe asegurarse de que PowerShell se ha configurado para ejecutar scripts remotos. Para ello, inicie PowerShell como administrador. En Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2 realice lo siguiente:
  
1. Haga clic **en** Inicio , **en Todos** los programas, en **Accesorios,** en Windows PowerShell, haga clic con el botón derecho **en Windows PowerShell** y, a continuación, haga clic en Ejecutar **como administrador.**
    
2. Si aparece **el cuadro de diálogo Control de** cuentas de usuario, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Si está ejecutando Windows 8, complete este procedimiento en su lugar:
  
1. Acceda a la barra Accesos, haga clic **en Buscar** y, a continuación, haga clic con el botón derecho **en Windows PowerShell**. Puede acceder rápidamente Windows 8 la barra de accesos en cualquier equipo (pantalla táctil o no táctil) manteniendo presionada la tecla Windows y presionando C.
    
2. En la barra de herramientas de la parte inferior de la pantalla, haga clic **en Ejecutar como administrador.**
    
3. Si aparece **el cuadro de diálogo Control de** cuentas de usuario, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Después de ejecutar PowerShell, debe cambiar la directiva de ejecución para permitir la ejecución de scripts remotos. En la consola de PowerShell, escriba el comando siguiente y, después, presione ENTRAR:
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Al ejecutar el comando anterior, es posible que reciba el siguiente mensaje de error:> Set-ExecutionPolicy: Se deniega el acceso a la clave del Registro *HKEY_LOCAL_MACHINE \\ SOFTWARE Microsoft \\ \\ PowerShell \\ 1 \\ ShellIds \\ Micrsoft.PowerShell'.* Este mensaje de error suele producirse si no ejecuta PowerShell con credenciales de administrador. Cierre la sesión de PowerShell e inicie una nueva sesión como administrador.
 
Para comprobar que la directiva de ejecución se ha configurado correctamente, escriba lo siguiente en el símbolo del sistema de PowerShell y, después, presione ENTRAR:
  
```PowerShell
Get-ExecutionPolicy
```

Si vuelve a obtener el siguiente valor, todo se ha configurado correctamente:
  
`RemoteSigned`

Si actualmente no está ejecutando Windows PowerShell 5.1, también tendrá que descargar e instalar Windows Management Framework 5.1 desde el Centro de descarga de Microsoft. Este es un paquete de instalación que incluye Windows PowerShell 5.1 y Windows remoto (WinRM) 3.0. Este paquete de instalación puede ser necesario si, por ejemplo, está ejecutando Windows 7 SP1 y aún no se ha actualizado a Windows PowerShell 5.1. Si está ejecutando Windows Server 2016 o Windows 10 de aniversario, no debe haber necesidad de instalar Windows PowerShell 5.1. Windows PowerShell 5.1 viene preinstalado en esos sistemas operativos.
  
Antes de instalar Windows Management Framework 5.1:
  
- Asegúrese de que ha descargado la versión correcta del paquete de instalación. Si ejecuta la versión de 64 bits de Windows 7 SP1, descargue el archivo Win7AndW2K8R2-KB3191566-x64.ZIP. Si ejecuta la versión de 32 bits de Windows 7, descargue el archivo Win7-KB3191566-x86.ZIP.
    
- Si está ejecutando Windows 7 en el equipo, asegúrese de que ha instalado Windows 7 Service Pack 1.

Si no está seguro de qué versión de Windows está ejecutando o no está seguro de si ha instalado Windows 7 Service Pack 1, haga clic en Inicio **,** haga clic con el botón derecho en Equipo y, a continuación, haga clic en **Propiedades.** Esta información se mostrará en el cuadro de diálogo Sistema.
  
Para instalar Windows Management Framework 5.1, complete el procedimiento en Instalar [y configurar WMF 5.1.](/powershell/scripting/wmf/setup/install-configure)
  
Después de reiniciar el equipo, compruebe que Windows PowerShell puede iniciarse y que la aplicación se puede ejecutar con credenciales administrativas. Para ello:
  
1. Haga clic **en** Inicio , **en Todos los** programas, en **Accesorios,** en Windows PowerShell, haga clic con el botón derecho en **Windows PowerShell y,** a continuación, haga clic en Ejecutar **como administrador.**
    
2. Si aparece el cuadro de diálogo Control de cuentas de usuario, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Cuando aparezca la consola de PowerShell, deberá comprobar que el servicio WinRM se está ejecutando y se ha configurado correctamente. Para comprobar que el servicio se está ejecutando, escriba el siguiente comando en el símbolo del sistema de PowerShell y, después, presione ENTRAR:
  
```PowerShell
Get-Service winrm
```

La información sobre el servicio WinRM se mostrará en pantalla:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Si el estado del servicio no es igual a "En ejecución", inicie el servicio WinRM escribiendo el siguiente comando y presionando ENTRAR:
  
```PowerShell
Start-Service winrm
```

Una vez que se haya iniciado el servicio, ejecute el siguiente comando para asegurarse de que WinRM usa la autenticación básica:
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Se mostrará en pantalla información similar a la siguiente:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Si la autenticación básica se ha establecido en true, está listo para usar PowerShell para conectarse a Skype Empresarial Online.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  

---
title: Descargar e instalar Windows PowerShell 5,1
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
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Descargue, instale y use Windows PowerShell 5,1 para crear una sesión remota de PowerShell que se conecte a Skype empresarial online.
ms.openlocfilehash: 5afca0ef1fd5d7437c3974de1424a664c99ab1a1
ms.sourcegitcommit: 9c54fd0a51ece8624155dc543d5df922834aa51e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2019
ms.locfileid: "35701561"
---
# <a name="download-and-install-windows-powershell-51"></a>Descargar e instalar Windows PowerShell 5,1

Si está usando la actualización de aniversario de Windows 10 o Windows Server 2016, ya tiene Windows PowerShell 5,1. Esto se debe a que esta aplicación viene preinstalada con esos sistemas operativos.
  
Para determinar qué versión de Microsoft PowerShell está usando, haga lo siguiente en su equipo con Windows 7 o Windows Server 2008 R2 o Windows Server 2012:
  
1. Haga clic en **Inicio**, en **todos los programas**, en **accesorios**, en **Windows PowerShell**y, por último, en **Windows PowerShell**.
    
2. En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:
    
   ```
   Get-Host | Select-Object Version
   ```

3. A continuación, debe mostrarse información similar a la siguiente en la ventana de la consola:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Si el número de versión devuelto es 5,1, quiere decir que está ejecutando Windows PowerShell 5,1. Si el número de versión devuelto no es 5,1, tendrá que instalar Windows PowerShell 5,1. Puede descargar Windows Management Framework 5,1, que incluye Windows PowerShell 5,1, desde el [centro de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).
  
Después de comprobar que Windows PowerShell 5,1 está instalado, debe asegurarse de que PowerShell se ha configurado para ejecutar scripts remotos. Para ello, inicie PowerShell como administrador. En Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, haga lo siguiente:
  
1. Haga clic en **Inicio**, seleccione **todos los programas**, **accesorios**, **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell**y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. Si aparece el cuadro de diálogo **control de cuentas de usuario** , haga clic en **sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Si está ejecutando Windows 8, realice este procedimiento:
  
1. Acceda a la barra de accesos, haga clic en **Buscar**y luego haga clic con el botón derecho en **Windows PowerShell**. Puede acceder rápidamente a la barra de accesos en cualquier equipo con Windows 8 (pantalla táctil o pantalla no táctil) si mantiene presionada la tecla Windows y presiona C.
    
2. En la barra de herramientas de la parte inferior de la pantalla, haga clic en **Ejecutar como administrador**.
    
3. Si aparece el cuadro de diálogo **control de cuentas de usuario** , haga clic en **sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Una vez que PowerShell se esté ejecutando, debe cambiar la Directiva de ejecución para permitir la ejecución de scripts remotos. En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Al ejecutar el comando anterior, es posible que reciba el siguiente mensaje de error: *>\\Set-ExecutionPolicy: acceso al software\\key'HKEY_LOCAL_MACHINE del registro\\de\\Microsoft\\PowerShell 1 ShellIds\\Micrsoft. PowerShell ' se* ha denegado. Este mensaje de error suele ocurrir si no ejecuta PowerShell con credenciales de administrador. Cierre la sesión de PowerShell y comience una nueva sesión como administrador.
 
Para comprobar que la Directiva de ejecución se ha configurado correctamente, escriba lo siguiente en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:
  
```
Get-ExecutionPolicy
```

Si obtiene el siguiente valor, todo se ha configurado correctamente:
  
`RemoteSigned`

Si actualmente no ejecuta Windows PowerShell 5,1, también tendrá que descargar e instalar Windows Management Framework 5,1 desde el centro de descarga de Microsoft. Este es un paquete de instalación que incluye Windows PowerShell 5,1 y Windows Remote Management (WinRM) 3,0. Este paquete de instalación podría ser necesario si, por ejemplo, se ejecuta Windows 7 SP1 y aún no se ha actualizado a Windows PowerShell 5,1. Si está ejecutando Windows Server 2016 o la actualización de aniversario de Windows 10, no es necesario instalar Windows PowerShell 5,1. Windows PowerShell 5,1 viene preinstalado en esos sistemas operativos.
  
Antes de instalar Windows Management Framework 5,1:
  
- Asegúrese de haber descargado la versión correcta del paquete de instalación. Si está ejecutando la versión de 64 bits de Windows 7 SP1, descargue el archivo Win7AndW2K8R2-KB3191566-x64. ZIP. Si está ejecutando la versión de 32 bits de Windows 7, descargue el archivo Win7-KB3191566-x86. ZIP.
    
- Si está ejecutando Windows 7 en su equipo, asegúrese de haber instalado Windows 7 Service Pack 1.

Si no está seguro de qué versión de Windows está ejecutando o si no está seguro de si ha instalado el Service Pack 1 de Windows 7, haga clic en **Inicio**, haga clic con el botón secundario en **equipo**y, a continuación, haga clic en **propiedades**. Esta información se notificará en el cuadro de diálogo sistema.
  
Para instalar Windows Management Framework 5,1, complete el procedimiento de [instalación y configuración de WMF 5,1](https://docs.microsoft.com/powershell/wmf/setup/install-configure).
  
Después de reiniciar el equipo, compruebe que Windows PowerShell puede iniciarse y que la aplicación se puede ejecutar con credenciales administrativas. Para ello, haga lo siguiente:
  
1. Haga clic en **Inicio**, seleccione **todos los programas**, **accesorios**, **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell** y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. Si aparece el cuadro de diálogo control de cuentas de usuario, haga clic en **sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Cuando aparezca la consola de PowerShell, debe comprobar que el servicio WinRM se está ejecutando y se ha configurado correctamente. Para comprobar que el servicio se está ejecutando, escriba el siguiente comando en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:
  
```
Get-Service winrm
```

Aparecerá la información sobre el servicio WinRM en la pantalla:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Si el estado del servicio no es "en ejecución", inicie el servicio WinRM escribiendo el siguiente comando y, a continuación, presione ENTRAR:
  
```
Start-Service winrm
```

Después de que el servicio se haya iniciado, ejecute el siguiente comando para asegurarse de que WinRM esté usando la autenticación básica:
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

En la pantalla se mostrará información similar a la siguiente:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Si la autenticación básica se ha establecido en true, está listo para usar PowerShell para conectarse a Skype empresarial online.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 

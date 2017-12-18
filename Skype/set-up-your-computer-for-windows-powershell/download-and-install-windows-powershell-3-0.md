---
title: "Descargar e instalar Windows PowerShell 3.0"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: LIL_Placement
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4

description: "Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online."
---

# Descargar e instalar Windows PowerShell 3.0

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Si está utilizando Windows 8.1, Windows 8, Windows Server 2012 R2 o Windows Server 2012, ya que debería tener Windows PowerShell 3.0. Eso es porque viene preinstalada con los sistemas operativos de esta aplicación.
  
Si está ejecutando Windows 7 o Windows Server 2008 R2, es posible que también esté ejecutando Windows PowerShell 3.0. Sin embargo, también es posible que es posible que esté ejecutando versión 2.0 en su lugar, la versión que se incluye originalmente con los sistemas operativos. Para determinar qué versión de Microsoft PowerShell l está utilizando, haga lo siguiente en el equipo de Windows 7 o Windows Server 2008 R2:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, **Accesorios**, haga clic en **Windows PowerShell** y, a continuación, haga clic en **Windows PowerShell**.
    
2. En la consola de PowerShell, escriba el comando siguiente y presione ENTRAR:
    
  ```
  Get-Host | Select-Object Version
  ```

3. A continuación, se debe mostrar la información similar al siguiente, en la ventana de la consola:
    
  ```
  Version
-------
3.0
  ```

Si el número de versión devuelto es 3.0, está ejecutando Windows PowerShell 3.0. Si el número de versión devuelto no es 3.0, tendrá que instalar Windows PowerShell 3.0. Puede descargar Windows Management Framework 3.0, que incluye Windows PowerShell 3.0, desde el [Centro de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
Después de haber comprobado que Windows PowerShell 3.0 está instalado, debe asegurarse de PowerShell se ha configurado para ejecutar secuencias de comandos remotos. Para ello, empiece PowerShell como administrador. En Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2 haga lo siguiente:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, **Accesorios**, haga clic en **Windows PowerShell**, haga clic en **Windows PowerShell** y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. Si aparece el cuadro de diálogo **Control de cuentas de usuario**, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Si está ejecutando Windows 8, siga este procedimiento en su lugar:
  
1. Obtener acceso a la barra accesos, haga clic en **Buscar** y, a continuación, haga clic en **Windows PowerShell**. Se puede acceder rápidamente a la barra de accesos en cualquier equipo Windows 8 (pantalla táctil o sin pantalla táctil) manteniendo presionada la tecla Windows y presionando C.
    
2. En la barra de herramientas en la parte inferior de la pantalla, haga clic en **Ejecutar como administrador**.
    
3. Si aparece el cuadro de diálogo **Control de cuentas de usuario**, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Después de que se está ejecutando PowerShell, debe cambiar la directiva de ejecución para permitir la ejecución de scripts remotos. En la consola de PowerShell, escriba el comando siguiente y presione ENTRAR:
  
```
Set-ExecutionPolicy RemoteSigned -Force
```

> [!NOTE]
> Cuando se ejecuta el comando anterior, puede recibir el siguiente mensaje de error: > Set-ExecutionPolicy: Obtener acceso a la key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell del registro ' denegado. > Este mensaje de error suele ocurre si no se están ejecutando PowerShell con credenciales de administrador. Cerrar la sesión de PowerShell y a continuación, inicie una nueva sesión como administrador. 
  
Para comprobar que la directiva de ejecución se ha configurado correctamente, escriba lo siguiente en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:
  
```
Get-ExecutionPolicy
```

Si se obtiene el siguiente valor, a continuación, todo lo que se ha configurado correctamente:
  
```
RemoteSigned
```

Si no se están ejecutando actualmente Windows PowerShell 3.0, también deberá descargar e instalar Windows Management Framework 3.0 desde Microsoft Download Center. Se trata de un paquete de instalación que incluye Windows PowerShell 3.0 y administración remota de Windows (WinRM) 3.0. El paquete de instalación podría ser necesario si está ejecutando Windows 7 y aún no ha actualizado a Windows PowerShell 3.0. Si está ejecutando Windows Server 2012, Windows Server 2012 R2, Windows 8 o Windows 8.1, no debería necesidad de instalar Windows PowerShell 3.0. Windows PowerShell 3.0 viene preinstalado en los sistemas operativos.
  
Antes de instalar Windows Management Framework 3.0:
  
- Asegúrese de que ha descargado la versión correcta del paquete de instalación. Si está ejecutando la versión de 64 bits de Windows 7, descargue el archivo archivo Windows6.1-KB2506143-x64.msu. Si está ejecutando la versión de 32 bits de Windows 7, descargue el archivo archivo Windows6.1-KB2506143-x86.msu.
    
- Si está ejecutando Windows 7 en el equipo, asegúrese de que ha instalado el Service Pack 1 de Windows 7.
    
Si no está seguro de qué versión de Windows está ejecutando o no está seguro de si ha instalado el Service Pack 1 de Windows 7, haga clic en **Inicio**, haga clic en **equipo** y, a continuación, haga clic en **Propiedades**. Esta información se registrará en el cuadro de diálogo del sistema.
  
Para instalar Windows Management Framework 3.0, realice el siguiente procedimiento:
  
1. Haga doble clic en el. Archivo de instalación MSU ( **archivo Windows6.1-KB2506143-x64.msu** o **archivo Windows6.1-KB2506143-x86.msu** ).
    
2. En el Asistente de descargar e instalar actualizaciones, en la página **Lea los términos de licencia (1 de 1)**, haga clic en .
    
3. Cuando termine la instalación, haga clic en **Reiniciar ahora** para reiniciar el equipo.
    
Después de que se reinicia el equipo, compruebe que puede empezar a Windows PowerShell y que se puede ejecutar la aplicación con credenciales administrativas. Para hacer esto:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, **Accesorios**, haga clic en **Windows PowerShell**, haga clic en **Windows PowerShell** y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. Si aparece el cuadro de diálogo Control de cuentas de usuario, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.
    
Cuando aparezca la consola PowerShell, a continuación, debe comprobar que el servicio WinRM está ejecutando y se ha configurado correctamente. Para comprobar que se está ejecutando el servicio, escriba el comando siguiente en el símbolo de PowerShell y, a continuación, presione ENTRAR:
  
```
Get-Service winrm
```

A continuación, se mostrará información sobre el servicio WinRM en pantalla:
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

Si el servicio de estado no es igual a "Ejecutar", inicie el servicio WinRM escribiendo el siguiente comando y, a continuación, presione ENTRAR:
  
```
Start-Service winrm
```

Después de que se ha iniciado el servicio, ejecute el comando siguiente para asegurarse de que WinRM está utilizando la autenticación básica:
  
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

Si se ha establecido autenticación básica en true, y esté listo para usar PowerShell para conectarse a Skype Empresarial Online.
  
||
|:-----|
|![Icono pequeño de LinkedIn Learning](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **¿Usa Office 365 por primera vez?**         Descubra cursos en vídeo gratuitos para **administradores de Office 365 y profesionales de TI**, ofrecidos por LinkedIn Learning. |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  


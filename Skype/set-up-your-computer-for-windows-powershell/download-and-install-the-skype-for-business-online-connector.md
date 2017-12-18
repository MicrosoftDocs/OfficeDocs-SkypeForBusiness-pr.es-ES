---
title: "Descargue e instale el Skype para módulo Business Connector en línea"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
description: "Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online.
"
---

# Descargue e instale el Skype para módulo Business Connector en línea

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
La Módulo de conector de Skype Empresarial Online incluye el cmdlet **New-CsOnlineSession**, que permite crear una sesión remota Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que es compatible sólo en equipos de 64 bits (consulte[Configurar el equipo para Skype para la administración empresarial Online con Windows PowerShell](set-up-your-computer-for-skype-for-business-online-management-using-windows-powe.md) para obtener más información), puede descargarse desde el Centro de descarga de Microsoft en[https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Descargar el archivo SkypeOnlinePowershell.exe y, a continuación, complete el procedimiento siguiente:
  
1. Haga doble clic en el archivo **SkypeOnlinePowershell.exe**.
    
2. En la Skype Empresarial Online, Asistente de configuración de Windows PowerShell, en la página **Términos de licencia del Software de Microsoft**, seleccione **acepto los términos del contrato de licencia** y, a continuación, haga clic en **instalar**. Si aparece el cuadro de diálogo **Control de cuentas de usuario**, haga clic en **Sí** para continuar con la instalación.
    
3. En la página de **completado el Skype empresarial Online, módulo de Windows PowerShell**, haga clic en **Finalizar**.
    
El programa de instalación copia la Módulo de conector de Skype Empresarial Online (y el cmdlet **New-CsOnlineSession** ) en el equipo. Para tener acceso al módulo, iniciar una sesión de Windows PowerShell con credenciales de administrador y, a continuación, ejecute el siguiente comando:
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Si no desea escribir este comando cada vez que inicie Windows PowerShell, puede agregar el comando a su perfil de Windows PowerShell. Para ello, escriba el comando siguiente en el símbolo de Windows PowerShell y, a continuación, presione ENTRAR:
  
```
notepad.exe $profile
```

Cuando aparezca el Bloc de notas, agregue la línea siguiente a la parte inferior de los comandos que ya están en el perfil (si existe):
  
```
Import-Module SkypeOnlineConnector
```

Guarde el archivo. La próxima vez que inicie Windows PowerShell, el Módulo de conector de Skype Empresarial Online se importarán automáticamente. Tenga en cuenta que recibirá un mensaje de error y no se cargará el módulo, si no se están ejecutando Windows PowerShell con credenciales de administrador.
  
Además de instalar el Módulo de conector de Skype Empresarial Online, SkypeOnlinePowershell.exe también instala tres componentes adicionales: 1) la identidad servicio cliente Runtime biblioteca (IDCRL), utilizado para controlar la autenticación del cliente Skype Empresarial Online; (2) .NET framework 4.5; y, 3) el paquete de Microsoft Visual C++ 2012 redistribuible (x64) (versión 11.0.50727). .NET framework 4.5 proporciona la infraestructura utilizada para crear y ejecutar aplicaciones. NET, incluyendo Windows PowerShell. El paquete redistribuible de Visual C++ instala los componentes de tiempo de ejecución de Visual C++ para equipos que no tienen instalado Microsoft Visual Studio 2012.
  
Para comprobar el número de versión del módulo de conector que está instalado actualmente en el equipo, abra el Panel de Control, abra **programas y características** y, a continuación, busque el número de versión de **Skype empresarial Online, módulo de Windows PowerShell**.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  


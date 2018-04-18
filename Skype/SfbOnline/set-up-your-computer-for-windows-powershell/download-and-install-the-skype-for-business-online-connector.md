---
title: Descargue e instale el Skype para el módulo de Business Connector en línea
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: 'Descargar, instalar y, a continuación, utilizar el Skype para Business Connector en línea para crear una sesión remota de Windows PowerShell que se conecta a Skype para los negocios en línea. '
ms.openlocfilehash: dde4071b95f7565bee67b7869c23881c97218f54
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Descargue e instale el Skype para el módulo de Business Connector en línea

El Skype para el módulo de Business Connector en línea incluye el cmdlet **New-CsOnlineSession** , que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype para los negocios en línea. Este módulo, que sólo se admite en equipos de 64 bits (consulte [Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obtener más información), se puede descargar desde Microsoft Download Center en [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Descargue el archivo SkypeOnlinePowershell.exe y, a continuación, complete el procedimiento siguiente:
  
1. Haga doble clic en el archivo **SkypeOnlinePowershell.exe** .
    
2. En Skype para los negocios en línea, Asistente para la instalación de Windows PowerShell, en la página **Términos de licencia del Software de Microsoft** , seleccione **acepto los términos del contrato de licencia**y, a continuación, haga clic en **instalar**. Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para continuar con la instalación.
    
3. En la página de **completado el Skype para los negocios en línea, módulo de Windows PowerShell** , haga clic en **Finalizar**.
    
El programa de instalación copia el Skype para el módulo de Business Connector en línea (y el cmdlet **New-CsOnlineSession** ) en el equipo. Para tener acceso al módulo, iniciar una sesión de Windows PowerShell con credenciales de administrador y, a continuación, ejecute el siguiente comando:
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Si no desea escribir este comando cada vez que inicie Windows PowerShell, puede agregar el comando a su perfil de Windows PowerShell. Para ello, escriba el comando siguiente en el símbolo del sistema de Windows PowerShell y, a continuación, presione ENTRAR:
  
```
notepad.exe $profile
```

 Cuando aparezca el Bloc de notas, agregue la siguiente línea al final de los comandos que ya están en el perfil (si existe):
  
```
Import-Module SkypeOnlineConnector
```

Guarde el archivo. La próxima vez que inicie Windows PowerShell, se importará automáticamente el Skype para el módulo de Business Connector en línea. Tenga en cuenta que recibirá un mensaje de error y no se cargará el módulo, si no está ejecutando Windows PowerShell con credenciales de administrador.
  
Además de instalar el Skype para el módulo de Business Connector en línea, SkypeOnlinePowershell.exe también instala tres componentes adicionales: 1) la identidad servicio cliente Runtime Library (IDCRL), utilizado para controlar la autenticación del cliente Skype para empresas En línea; 2).NET Framework 4.5; y, 3) Microsoft Visual C++ 2012 (x64) paquete redistribuible (versión 11.0.50727). .NET Framework 4.5 proporciona la infraestructura utilizada para generar y ejecutar aplicaciones. NET, incluidos Windows PowerShell. El paquete redistribuible de Visual C++ instala componentes de tiempo de ejecución de Visual C++ para equipos que no tienen instalado Microsoft Visual Studio 2012.
  
Para comprobar el número de versión del módulo de conector que está instalado actualmente en el equipo, abra Panel de Control, abra **programas y características**y, a continuación, compruebe el número de versión para el **Skype para los negocios en línea, módulo de Windows PowerShell**.
  
## <a name="related-topics"></a>See also
[Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
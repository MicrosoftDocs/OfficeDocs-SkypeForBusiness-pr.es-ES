---
title: Descargue e instale el Skype para el módulo del conector en línea de negocio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: 'Descargar, instalar y, a continuación, use el Skype para Business Connector en línea para crear una sesión remota de Windows PowerShell que se conecta a Skype para profesionales en línea. '
ms.openlocfilehash: deffed8da6b5b7a7c2ae522782f5316744de3394
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858335"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Descargue e instale el Skype para el módulo del conector en línea de negocio

El Skype para módulo Business Connector Online incluye el cmdlet **New-CsOnlineSession** , que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype para profesionales en línea. En este módulo, que sólo se admite en equipos de 64 bits (vea [Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obtener más información), se pueden descargar desde Microsoft Download Center en [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Descargue el archivo SkypeOnlinePowershell.exe y, a continuación, complete el siguiente procedimiento:
  
1. Haga doble clic en el archivo **SkypeOnlinePowershell.exe** .
    
2. En Skype para profesionales en línea, Asistente de instalación de Windows PowerShell, en la página **Términos de licencia del Software de Microsoft** , seleccione **acepto los términos del contrato de licencia**y, a continuación, haga clic en **instalar**. Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para continuar con la instalación.
    
3. En la página de **completado el Skype para Online de negocio, módulo de Windows PowerShell** , haga clic en **Finalizar**.
    
El programa de instalación copia el Skype para el módulo del conector en línea de negocio (y el cmdlet **New-CsOnlineSession** ) a su equipo. Para tener acceso al módulo, iniciar una sesión de Windows PowerShell con credenciales de administrador y, a continuación, ejecute el siguiente comando:
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Si no desea que se escriba este comando cada vez que inicie Windows PowerShell, puede agregar el comando a su perfil de Windows PowerShell. Para ello, escriba el siguiente comando en el símbolo del sistema de Windows PowerShell y, a continuación, presione ENTRAR:
  
```
notepad.exe $profile
```

 Cuando aparezca el Bloc de notas, agregue la línea siguiente a la parte inferior de los comandos que ya están en el perfil (si hay alguno):
  
```
Import-Module SkypeOnlineConnector
```

Guarde el archivo. La próxima vez que inicie Windows PowerShell, automáticamente se importará la Skype para el módulo del conector en línea de negocio. Tenga en cuenta que recibirá un mensaje de error y no se cargará el módulo, si no se está ejecutando Windows PowerShell con credenciales de administrador.
  
Además de instalar el Skype para el módulo del conector en línea de negocio, SkypeOnlinePowershell.exe también instala tres componentes adicionales: 1) la identidad de servicio de cliente en tiempo de ejecución biblioteca (IDCRL), usado para controlar la autenticación de cliente para Skype para la empresa En línea; (2) .NET framework 4.5; y, 3) el paquete de Microsoft Visual C++ 2012 redistribuible (x64) (versión 11.0.50727). .NET framework 4.5 proporciona la infraestructura que se usa para generar y ejecutar aplicaciones. NET, incluyendo Windows PowerShell. El paquete redistribuible de Visual C++ instala los componentes de tiempo de ejecución de Visual C++ para equipos que no tienen instalado Microsoft Visual Studio 2012.
  
Para comprobar el número de versión del módulo de conector que actualmente está instalado en su equipo, abra el Panel de Control, abra **programas y características**y, a continuación, compruebe el número de versión para el **Skype para Online de negocio, módulo de Windows PowerShell**.
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
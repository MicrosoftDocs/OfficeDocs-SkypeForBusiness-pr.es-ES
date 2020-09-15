---
title: Descargar e instalar el módulo conector de Skype empresarial online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: Descargue, instale y use el conector de Skype empresarial online para crear una sesión remota de Windows PowerShell que se conecte a Skype empresarial online.
ms.openlocfilehash: 3928e77e5bac77dbfe89f7be5e762dd0d8ff93eb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814569"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Descargar e instalar el módulo conector de Skype empresarial online

> [!NOTE]
> La versión pública más reciente de [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) está integrada en el conector de Skype empresarial online y ofrece un único módulo para la administración de PowerShell de Teams.

El módulo conector de Skype empresarial online incluye el cmdlet **New-CsOnlineSession** , que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype empresarial online. Este módulo, que solo es compatible con los equipos de 64 bits (consulte [configurar el equipo para la administración de Skype empresarial online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obtener más información), se puede descargar desde el centro de descarga de Microsoft en [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) . Descargue el archivo de SkypeOnlinePowershell.exe y, a continuación, realice el siguiente procedimiento:
  
1. Haga doble clic en el archivo **SkypeOnlinePowershell.exe** .
    
2. En el Asistente para la instalación de Skype empresarial online, en la página **términos de licencia del software de Microsoft** , seleccione Acepto **los términos del contrato de licencia**y, a continuación, haga clic en **instalar**. Si aparece el cuadro de diálogo **control de cuentas de usuario** , haga clic en **sí** para continuar con la instalación.
    
3. En la página **completado de Skype empresarial online, módulo de Windows PowerShell** , haga clic en **Finalizar**.
    
El programa de instalación copia el módulo del conector de Skype empresarial online (y el cmdlet **New-CsOnlineSession** ) en el equipo. Para acceder al módulo, inicie una sesión de Windows PowerShell con credenciales de administrador y, a continuación, ejecute el siguiente comando:
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

Si no desea escribir este comando cada vez que inicie Windows PowerShell, puede Agregar el comando a su perfil de Windows PowerShell. Para ello, escriba el siguiente comando en el símbolo del sistema de Windows PowerShell y, a continuación, presione ENTRAR:
  
```PowerShell
notepad.exe $profile
```

 Cuando aparezca el Bloc de notas, agregue la línea siguiente en la parte inferior de los comandos que ya están en el perfil (si hay alguno):
  
```PowerShell
Import-Module SkypeOnlineConnector
```

Guarde el archivo. La próxima vez que inicie Windows PowerShell, el módulo conector de Skype empresarial online se importará automáticamente. Tenga en cuenta que recibirá un mensaje de error y el módulo no se cargará, si no está ejecutando Windows PowerShell con credenciales de administrador.
  
Además de instalar el módulo conector de Skype empresarial online, SkypeOnlinePowershell.exe también instala tres componentes adicionales: 1) la biblioteca de tiempo de ejecución de cliente del servicio de identidad (IDCRL), que se usa para controlar la autenticación del cliente a Skype empresarial online. 2) .NET Framework 4,5; y 3) el paquete redistribuible de Microsoft Visual C++ 2012 (x64) (versión 11.0.50727). .NET Framework 4,5 proporciona la infraestructura que se usa para crear y ejecutar aplicaciones .NET, incluido Windows PowerShell. El paquete redistribuible de Visual C++ instala componentes de tiempo de ejecución de Visual C++ para equipos que no tienen instalado Microsoft Visual Studio 2012.
  
Para comprobar el número de versión del módulo de conector instalado actualmente en el equipo, abra el panel de control, Abra **programas y características**y, a continuación, compruebe el número de versión de **Skype empresarial online, módulo de Windows PowerShell**.
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración de Skype empresarial online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 

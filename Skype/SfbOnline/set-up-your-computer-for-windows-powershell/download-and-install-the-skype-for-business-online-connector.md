---
title: Descargar e instalar el módulo Conector de Skype Empresarial Online
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
description: Descargue, instale y, a continuación, use el conector de Skype Empresarial Online para crear una sesión de Windows PowerShell remota que se conecte a Skype Empresarial Online.
ms.openlocfilehash: 3928e77e5bac77dbfe89f7be5e762dd0d8ff93eb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814569"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Descargar e instalar el módulo Conector de Skype Empresarial Online

> [!NOTE]
> La última [versión pública de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) de Teams se integra con Skype Empresarial Online Connector, proporcionando un módulo único para la administración de PowerShell de Teams.

El módulo conector de Skype Empresarial Online incluye el cmdlet **New-CsOnlineSession,** que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits (consulte Configurar el equipo para la administración de Skype Empresarial Online con [Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obtener más información), puede descargarse desde el Centro de descarga de Microsoft [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) en. Descargue el SkypeOnlinePowershell.exe archivo y, después, complete el procedimiento siguiente:
  
1. Haga doble clic en **elSkypeOnlinePowershell.exe** archivo.
    
2. En el asistente de configuración de Skype Empresarial Online, Windows PowerShell, en la página Términos de licencia del software de **Microsoft,** seleccione Acepto los términos en el Contrato de licencia y, a continuación, haga clic en **Instalar.** Si aparece **el cuadro de diálogo Control** de cuentas de usuario, haga clic en **Sí** para continuar con la instalación.
    
3. En la **página Completado de Skype Empresarial Online, Windows PowerShell Módulo,** haga clic en **Finalizar.**
    
El programa de instalación copia el módulo del conector de Skype Empresarial Online (y el cmdlet **New-CsOnlineSession)** a su equipo. Para obtener acceso al módulo, inicie una sesión Windows PowerShell sesión bajo credenciales de administrador y, a continuación, ejecute el siguiente comando:
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

Si no quiere escribir este comando cada vez que inicie una Windows PowerShell, puede agregar el comando a su perfil Windows PowerShell usuario. Para ello, escriba el siguiente comando en el Windows PowerShell y, a continuación, presione ENTRAR:
  
```PowerShell
notepad.exe $profile
```

 Cuando aparezca el Bloc de notas, agregue la siguiente línea a la parte inferior de los comandos que ya están en el perfil (si los hay):
  
```PowerShell
Import-Module SkypeOnlineConnector
```

Guarde el archivo. La próxima vez que inicie Windows PowerShell, el módulo conector de Skype Empresarial Online se importará automáticamente. Tenga en cuenta que recibirá un mensaje de error y el módulo no se cargará si no está ejecutando Windows PowerShell credenciales de administrador.
  
Además de instalar el módulo del conector de Skype Empresarial Online, SkypeOnlinePowershell.exe también instala tres componentes adicionales: 1) la biblioteca runtime de cliente de servicio de identidad (IDCRL), que se usa para administrar la autenticación de cliente a Skype Empresarial Online; 2) .NET Framework 4.5; y, 3) el paquete redistribuible de Microsoft Visual C++ 2012 (x64) (versión 11.0.50727). .NET Framework 4.5 proporciona la infraestructura usada para crear y ejecutar aplicaciones .NET, incluidas Windows PowerShell. El paquete redistribuible de Visual C++ instala componentes de tiempo de ejecución de Visual C++ para equipos que no tienen Microsoft Visual Studio 2012 instalado.
  
Para comprobar el número de versión del módulo Conector que está instalado actualmente en su equipo, abra el Panel de control, abra Programas y características y, a continuación, compruebe el número de versión de Skype Empresarial **Online, Windows PowerShell Module.**
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 

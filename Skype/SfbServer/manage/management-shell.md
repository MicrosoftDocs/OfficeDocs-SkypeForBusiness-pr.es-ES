---
title: Shell de administración de Skype Empresarial Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: El Skype para Shell de administración de Business Server proporciona la interfaz de línea de comandos para la administración y la administración de servidores. Se basa en Windows PowerShell e incluye un completo conjunto de cmdlets de gestión y administración que son específicos de Skype y los productos de servidor heredados de Lync.
ms.openlocfilehash: 243ff7a684bb14f73ef9f4836ce00e8048fbb236
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884205"
---
# <a name="skype-for-business-server-management-shell"></a>Shell de administración de Skype Empresarial Server
 
El Skype para Shell de administración de Business Server proporciona la interfaz de línea de comandos para la administración y la administración de servidores. Se basa en Windows PowerShell e incluye un completo conjunto de cmdlets de gestión y administración que son específicos de Skype y los productos de servidor heredados de Lync.
  
Windows PowerShell permite administrar las aplicaciones de Microsoft desde la línea de comandos. Incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Windows PowerShell se introdujo por primera vez como una versión descargable para el sistema operativo Windows más tarde en 2006 y se ha incorporado como la interfaz de línea de comandos para la administración de Microsoft Exchange Server 2007. Lo se ha incorporado a la mayoría de los productos de Microsoft Server, incluidos los servidores de Lync y Skype a partir de Lync Server 2010. Hay más de 700 cmdlets específicos de Lync y Skype disponibles en el Skype para Shell de administración de servidor empresarial.
  
> [!NOTE]
> Skype para referencia del cmdlet de negocio se ha trasladado al docs.microsoft.com. Al hacer clic en los vínculos siguientes le llevará a la nueva página de docs.microsoft.com. El contenido es ahora contribuciones de la Comunidad de origen y están disponibles para abrir a través de depósito. ¿Está interesado en que han contribuido? Desproteger el archivo Léame de la repo aquí:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype para Business Server se distribuye con más de 700 cmdlets que permiten a los administradores administrar Skype para Business Server mediante el Skype para Shell de administración de servidor empresarial. Puede obtener ayuda sobre un cmdlet directamente desde la línea de comandos al escribir lo siguiente:
  
```
Get-Help New-CsVoicePolicy -Full
```

El comando anterior recupera toda la ayuda disponible para el cmdlet **New-CsVoicePolicy**. Si desea ver la ayuda de otro cmdlet, cambie **New-CsVoicePolicy** por el nombre del cmdlet cuya ayuda desea obtener.
  
Para obtener una lista de todos los cmdlets disponibles para administrar Skype Empresarial Server, escriba lo siguiente en el símbolo del sistema del shell: 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Cosas que debe saber acerca de Windows PowerShell en Skype para Business Server:
  
- Para ejecutar la Skype para cmdlets de Business Server, abra el Skype para Shell de administración de servidor empresarial.
    
    > [!CAUTION]
    > Si abre una ventana de Windows PowerShell en lugar de la Skype para Shell de administración de servidor empresarial, de forma predeterminada es es posible que no pueda ejecutar los cmdlets de Skype. Para ejecutar Skype para Business Server cmdlets de Windows PowerShell, escriba lo siguiente en primer lugar en el símbolo del sistema de Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- Skype para Shell de administración de Business Server se instala automáticamente en cada Skype para Business Server Enterprise Edition servidor Front-End o servidor Standard Edition.
    
- Puede actualizar el Skype para el contenido de Ayuda del Shell de administración de servidor empresarial ejecutando el cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . El cmdlet Update-Help descarga e instala los archivos de ayuda más recientes disponibles para todos los módulos instalados en el equipo, incluidas las actualizaciones de Skype para cmdlets de negocio.
    
    De forma predeterminada, el cmdlet **Update-Help** actualizará todos los módulos instalados en su Skype para Business Server. Si desea actualizar solo determinados módulos, puede usar el parámetro _Module_ a fin de limitar el ámbito del cmdlet. En el ejemplo siguiente se actualiza sólo la Skype para módulo empresarial.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Si necesita actualizar la Ayuda en los servidores que no están conectados a internet, puede usar el cmdlet [Guardar-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) para obtener la versión más reciente de la Ayuda y guardarlo en una ubicación que especifique. A continuación, puede usar el cmdlet **Update-Help** con el parámetro _- SourcePath_ en servidores que no está conectado a internet para obtener la ayuda actualizada desde la ubicación seleccionada. En el ejemplo siguiente se muestra cómo guardar los archivos de ayuda en un recurso compartido de red y, a continuación, actualice la ayuda para el Skype para módulo empresarial desde el recurso compartido de archivos.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obtener información más detallada, consulte la [Ayuda actualizable](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Si está usando PowerShell de forma remota debe permitir la comunicación a través de un firewall. Para obtener más información acerca de los usos de comunicación remota de PowerShell de puertos, vea [¿qué Does PowerShell comunicación remota de uso del puerto?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    


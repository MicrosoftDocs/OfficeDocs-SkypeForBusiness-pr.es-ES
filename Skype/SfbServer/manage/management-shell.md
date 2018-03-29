---
title: Shell de administración de Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: El Skype para el Shell de administración de servidor empresarial proporciona la interfaz de línea de comandos para la gestión y administración de servidores. Se basa en Windows PowerShell e incluye un completo conjunto de cmdlets de gestión y administración que son específicos de Skype y los productos heredados de Lync server.
ms.openlocfilehash: e4eb5f183af29dd5f9932fb15cdb86a0f78e7840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-management-shell"></a>Shell de administración de Skype Empresarial Server 2015
 
El Skype para el Shell de administración de servidor empresarial proporciona la interfaz de línea de comandos para la gestión y administración de servidores. Se basa en Windows PowerShell e incluye un completo conjunto de cmdlets de gestión y administración que son específicos de Skype y los productos heredados de Lync server.
  
Windows PowerShell le permite administrar las aplicaciones de Microsoft desde la línea de comandos. Incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Windows PowerShell se presentó como una versión descargable para el sistema operativo Windows más tarde en 2006 y fue incorporado como la interfaz de línea de comandos para la administración de Microsoft Exchange Server 2007. Se ha incorporado en la mayoría de los productos de Microsoft Server, incluyendo servidores de Lync y Skype a partir de Lync Server 2010. Hay más de 700 cmdlets específicos de Lync y Skype en el Skype para el Shell de administración de servidor de empresa.
  
> [!NOTE]
> Skype para referencia de cmdlet de negocio se ha movido a docs.microsoft.com. Haciendo clic en los vínculos siguientes le llevará a la nueva página de docs.microsoft.com. El contenido es ahora contribuciones de la Comunidad de origen y están disponibles para abrir a través de GitHub. ¿Está interesado en contribuir? Consulte el archivo Léame en el repo aquí:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype para Business Server 2015 incluye más de 700 cmdlets que permiten a los administradores administrar Skype para Business Server usando el Skype para el Shell de administración de servidor de empresa. Puede obtener ayuda sobre un cmdlet directamente desde la línea de comandos al escribir lo siguiente:
  
```
Get-Help New-CsVoicePolicy -Full
```

El comando anterior recupera la Ayuda completa disponible para el cmdlet **New-CsVoicePolicy** . Para ver la Ayuda de un cmdlet diferente, sustituya **CsVoicePolicy de nuevo** con el nombre del cmdlet para el que desea recibir ayuda.
  
Para obtener una lista de todos los cmdlets disponibles para administrar Skype Empresarial Server, escriba lo siguiente en el símbolo del sistema del shell: 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Cosas que saber acerca de Windows PowerShell en Skype para Business Server:
  
- Para ejecutar el Skype para Business Server cmdlets, abra el Skype para el Shell de administración de servidor de empresa.
    
    > [!CAUTION]
    > Si abre una ventana de Windows PowerShell, en lugar del Skype para el Shell de administración de servidor empresarial, de forma predeterminada no es capaz de ejecutar los cmdlets de Skype. Para ejecutar Skype para los cmdlets Business Server desde Windows PowerShell, primero escriba lo siguiente en el símbolo del sistema de Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- Skype para el Shell de administración de servidor empresarial se instala automáticamente en cada Skype para servidor Business Server Enterprise Edition servidor Front-End o Standard Edition.
    
- Puede actualizar el Skype para el contenido de la Ayuda de Shell de administración de servidor empresarial ejecutando el cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . El cmdlet Update-Help se descarga e instala los archivos de ayuda más recientes disponibles para todos los módulos instalados en el equipo, incluidas las actualizaciones de Skype para los cmdlets del negocio.
    
    De forma predeterminada, el cmdlet **Update-Help** actualizará todos los módulos instalados en su Skype para Business Server. Si desea actualizar sólo algunos módulos, puede utilizar el parámetro _Module_ para limitar el ámbito del cmdlet. En el ejemplo siguiente se actualiza sólo el Skype para el módulo de negocios.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Si necesita actualizar la Ayuda en los servidores que no están conectados a internet, puede usar el cmdlet de [Guardar-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) para obtener la versión más reciente de la Ayuda y guárdelo en una ubicación que especifique. A continuación, puede utilizar el cmdlet **Update-Help** con el parámetro _- SourcePath_ en servidores no conectados a internet para obtener la ayuda actualizada de la ubicación seleccionada. En el ejemplo siguiente se muestra cómo guardar los archivos de ayuda en un recurso compartido de red y, a continuación, actualizar la ayuda para el Skype para el módulo de negocios desde el recurso compartido de archivo.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
// Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obtener más información, consulte la [Ayuda actualizables](https://technet.microsoft.com/library/hh847735.aspx).
    


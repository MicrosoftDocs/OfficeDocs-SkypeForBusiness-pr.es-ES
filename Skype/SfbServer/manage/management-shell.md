---
title: Shell de administración de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: El shell de administración de Skype empresarial proporciona la interfaz de línea de comandos para la administración y administración del servidor. Se ha creado en Windows PowerShell e incluye un conjunto completo de cmdlets de administración y administración específicos de Skype y los productos heredados de Lync Server.
ms.openlocfilehash: ce031b15e2146036d77c7336aa9c2b73f000fe4a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279595"
---
# <a name="skype-for-business-server-management-shell"></a>Shell de administración de Skype Empresarial Server
 
El shell de administración de Skype empresarial proporciona la interfaz de línea de comandos para la administración y administración del servidor. Se ha creado en Windows PowerShell e incluye un conjunto completo de cmdlets de administración y administración específicos de Skype y los productos heredados de Lync Server.
  
Windows PowerShell le permite administrar aplicaciones de Microsoft desde la línea de comandos. Incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Windows PowerShell se presentó por primera vez como una versión descargable para el sistema operativo Windows en 2006, y se incorporó como la interfaz de línea de comandos para la capacidad de administración de Microsoft Exchange Server 2007. Se ha incorporado en la mayoría de los productos de servidor de Microsoft, incluidos los de Lync y Skype, a partir de Lync Server 2010. Hay más de 700 cmdlets específicos de Lync y Skype disponibles en el shell de administración de Skype empresarial Server.
  
> [!NOTE]
> La referencia del cmdlet de Skype empresarial se ha movido a docs.microsoft.com. Al hacer clic en los vínculos siguientes te llevará a la nueva página de docs.microsoft.com. El contenido ahora está abierto y disponible para las contribuciones de la comunidad a través de GitHub. ¿Está interesado en colaborar? Consulte el archivo Léame en el repositorio aquí:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype empresarial Server incluye más de 700 cmdlets que permiten a los administradores administrar Skype empresarial Server mediante el shell de administración de Skype empresarial Server. Puede obtener ayuda sobre un cmdlet directamente desde la línea de comandos al escribir lo siguiente:
  
```
Get-Help New-CsVoicePolicy -Full
```

El comando anterior recupera toda la ayuda disponible para el cmdlet **New-CsVoicePolicy**. Si desea ver la ayuda de otro cmdlet, cambie **New-CsVoicePolicy** por el nombre del cmdlet cuya ayuda desea obtener.
  
Para obtener una lista de todos los cmdlets disponibles para administrar Skype Empresarial Server, escriba lo siguiente en el símbolo del sistema del shell: 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Cosas que debe saber sobre Windows PowerShell en Skype empresarial Server:
  
- Para ejecutar los cmdlets de Skype empresarial Server, abra el shell de administración de Skype empresarial Server.
    
    > [!CAUTION]
    > Si abre una ventana de Windows PowerShell en lugar del shell de administración de Skype empresarial Server, de forma predeterminada, es posible que no pueda ejecutar los cmdlets de Skype. Para ejecutar los cmdlets de Skype empresarial Server desde Windows PowerShell, en primer lugar escriba lo siguiente en el símbolo del sistema de Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- El shell de administración de Skype empresarial Server se instala automáticamente en todos los servidores front-end de Skype empresarial Server Enterprise Edition o Standard Edition.
    
- Puede actualizar el contenido de la ayuda del shell de administración de Skype empresarial Server ejecutando el cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . El cmdlet Update-Help descarga e instala los archivos de ayuda más recientes disponibles para todos los módulos instalados en el equipo, incluidas las actualizaciones de los cmdlets de Skype empresarial.
    
    De forma predeterminada, el cmdlet **Update-Help** actualiza todos los módulos instalados en su servidor de Skype empresarial. Si desea actualizar solo determinados módulos, puede usar el parámetro _Module_ a fin de limitar el ámbito del cmdlet. En el siguiente ejemplo se actualiza únicamente el módulo de Skype empresarial.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Si necesita actualizar la ayuda en servidores que no están conectados a Internet, puede usar el cmdlet [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) para obtener la última versión de la ayuda y guardarla en la ubicación que especifique. Después, puede usar el cmdlet **Update-Help** con el parámetro _-SourcePath_ en servidores que no están conectados a Internet para obtener la ayuda actualizada desde la ubicación que seleccionó. En el ejemplo siguiente se muestra cómo guardar los archivos de ayuda en un recurso compartido de archivos de red y, a continuación, actualizar la ayuda del módulo Skype empresarial desde el recurso compartido de archivos.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obtener información más detallada, consulte [acerca de la ayuda actualizable](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Si está usando PowerShell de forma remota, es posible que tenga que permitir la comunicación a través de un firewall. Para obtener más información sobre los puertos que usa la comunicación remota de PowerShell, vea [¿qué puerto usa el servicio de comunicación remota de PowerShell?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)
    


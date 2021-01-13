---
title: Shell de administración de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: El Shell de administración de Skype Empresarial Server proporciona la interfaz de línea de comandos para la administración y administración de servidores. Se basa en Windows PowerShell e incluye un conjunto completo de cmdlets de administración y administración que son específicos de Skype y los productos de lync server heredados.
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816540"
---
# <a name="skype-for-business-server-management-shell"></a>Shell de administración de Skype Empresarial Server
 
El Shell de administración de Skype Empresarial Server proporciona la interfaz de línea de comandos para la administración y administración de servidores. Se basa en Windows PowerShell e incluye un conjunto completo de cmdlets de administración y administración que son específicos de Skype y los productos de lync server heredados.
  
Windows PowerShell permite administrar aplicaciones de Microsoft desde la línea de comandos. Incluye un entorno de línea de comandos, comandos específicos de producto y un lenguaje de scripting completo. Windows PowerShell se introdujo por primera vez como una versión descargable para el sistema operativo Windows a finales de 2006 y se incorporó como la interfaz de línea de comandos para la capacidad de administración de Microsoft Exchange Server 2007. Se ha incorporado a la mayoría de los productos de Microsoft Server, incluidos los servidores de Lync y Skype a partir de Lync Server 2010. Hay más de 700 cmdlets específicos de Lync y Skype disponibles en el Shell de administración de Skype Empresarial Server.
  
> [!NOTE]
> La referencia del cmdlet de Skype Empresarial se ha movido a docs.microsoft.com. Al hacer clic en los vínculos siguientes, te llevará a la nueva docs.microsoft.com página. El contenido ahora tiene código abierto y está disponible para las contribuciones de la comunidad a través de GitHub. ¿Está interesado en colaborar? Echa un vistazo a README en el repositorio aquí: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype Empresarial Server incluye más de 700 cmdlets que permiten a los administradores administrar Skype Empresarial Server mediante el Shell de administración de Skype Empresarial Server. Puede recuperar ayuda para un cmdlet directamente desde la línea de comandos escribiendo un comando similar al siguiente:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

El comando anterior recupera toda la ayuda disponible para el cmdlet **New-CsVoicePolicy**. Si desea ver la ayuda de otro cmdlet, reemplace la referencia a **New-CsVoicePolicy** por el nombre del cmdlet cuya información de ayuda desea recuperar.
  
Para recuperar una lista completa de cmdlets disponibles para administrar Skype Empresarial Server, escriba lo siguiente en el símbolo del sistema del shell: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Cosas que debe saber sobre Windows PowerShell en Skype Empresarial Server:
  
- Para ejecutar los cmdlets de Skype Empresarial Server, abra el Shell de administración de Skype Empresarial Server.
    
    > [!CAUTION]
    > Si abre una ventana Windows PowerShell en lugar del Shell de administración de Skype Empresarial Server, es posible que no pueda ejecutar los cmdlets de Skype de forma predeterminada. Para ejecutar cmdlets de Skype Empresarial Server desde dentro de Windows PowerShell, escriba primero lo siguiente en el símbolo del sistema Windows PowerShell comando: >  `Import-Module SkypeforBusiness`
  
- El Shell de administración de Skype Empresarial Server se instala automáticamente en todos los servidores front-end o Standard Edition de Skype Empresarial Server Enterprise Edition.
    
- Puede actualizar el contenido de ayuda del Shell de administración de Skype Empresarial Server ejecutando el cmdlet [Update-Help.](https://technet.microsoft.com/library/hh849720.aspx) El cmdlet Update-Help descarga e instala los archivos de ayuda más recientes disponibles para todos los módulos instalados en el equipo, incluidas las actualizaciones de los cmdlets de Skype Empresarial.
    
    De forma predeterminada, el cmdlet **Update-Help** actualizará todos los módulos instalados en Skype Empresarial Server. Si desea actualizar solo determinados módulos, puede usar el parámetro _Module_ para limitar el ámbito del cmdlet. En el siguiente ejemplo solo se actualiza el módulo de Skype Empresarial.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Si necesita actualizar la Ayuda en servidores que no están conectados a Internet, puede usar el cmdlet [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) para obtener la versión más reciente de la ayuda y guardarla en la ubicación que especifique. A continuación, puede usar el cmdlet **Update-Help** con el parámetro _-SourcePath_ en servidores que no están conectados a Internet para obtener la ayuda actualizada de la ubicación seleccionada. En el siguiente ejemplo se muestra cómo guardar los archivos de ayuda en un recurso compartido de archivos de red y, a continuación, actualizar la ayuda para el módulo de Skype Empresarial desde el recurso compartido de archivos.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obtener información más detallada, consulte [Acerca de la Ayuda actualizable.](https://technet.microsoft.com/library/hh847735.aspx)
    
    > [!NOTE]
    > Si usa PowerShell de forma remota, es posible que tenga que permitir la comunicación a través de un firewall. Para obtener más información sobre los puertos que usa la comunicación remota de PowerShell, vea ¿Qué puerto usa la comunicación remota [de PowerShell?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    


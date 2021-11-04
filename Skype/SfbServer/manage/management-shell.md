---
title: Shell de administración de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: El Shell Skype Empresarial Server administración proporciona la interfaz de línea de comandos para la administración y administración del servidor. Se basa en Windows PowerShell e incluye un conjunto completo de cmdlets de administración y administración que son específicos de Skype productos de lync server heredados.
ms.openlocfilehash: 2d8caadfb1dfe80af74861cf20fa0b155dd20d1a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750319"
---
# <a name="skype-for-business-server-management-shell"></a>Shell de administración de Skype Empresarial Server
 
El Shell Skype Empresarial Server administración proporciona la interfaz de línea de comandos para la administración y administración del servidor. Se basa en Windows PowerShell e incluye un conjunto completo de cmdlets de administración y administración que son específicos de Skype productos de lync server heredados.
  
Windows PowerShell permite administrar aplicaciones de Microsoft desde la línea de comandos. Incluye un entorno de línea de comandos, comandos específicos de producto y un lenguaje de scripting completo. Windows PowerShell se introdujo por primera vez como una versión descargable para el sistema operativo Windows a finales de 2006, y se incorporó como la interfaz de línea de comandos para la capacidad de administración de Microsoft Exchange Server 2007. Se ha incorporado a la mayoría de los productos de Microsoft Server, incluidos los servidores lync y Skype a partir de Lync Server 2010. Hay más de 700 cmdlets de Lync Skype específicos disponibles en el Shell Skype Empresarial Server administración.
  
> [!NOTE]
> Skype Empresarial referencia del cmdlet se ha movido a docs.microsoft.com. Al hacer clic en los vínculos siguientes, te llevará a la nueva docs.microsoft.com página. El contenido ahora es de código abierto y está disponible para las contribuciones de la comunidad a través de GitHub. ¿Está interesado en contribuir? Consulte readme en el repositorio aquí: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype Empresarial Server incluye más de 700 cmdlets que permiten a los administradores administrar Skype Empresarial Server mediante el Shell Skype Empresarial Server administración. Puede recuperar ayuda para un cmdlet directamente desde la línea de comandos escribiendo un comando similar al siguiente:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

El comando anterior recupera toda la ayuda disponible para el cmdlet **New-CsVoicePolicy**. Si desea ver la ayuda de otro cmdlet, reemplace la referencia a **New-CsVoicePolicy** por el nombre del cmdlet cuya información de ayuda desea recuperar.
  
Para recuperar una lista completa de cmdlets disponibles para administrar Skype Empresarial Server, escriba lo siguiente en el símbolo del sistema del shell: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Cosas que debe saber Windows PowerShell en Skype Empresarial Server:
  
- Para ejecutar los cmdlets Skype Empresarial Server, abra el Shell Skype Empresarial Server administración.
    
    > [!CAUTION]
    > Si abre una ventana Windows PowerShell en lugar del Shell de administración de Skype Empresarial Server, es posible que no pueda ejecutar los cmdlets Skype de forma predeterminada. Para ejecutar Skype Empresarial Server cmdlets desde dentro de Windows PowerShell, escriba primero lo siguiente en el símbolo del sistema Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- Skype Empresarial Server El Shell de administración se instala automáticamente en todos Skype Empresarial Server Enterprise Edition servidor front-end o Standard Edition servidor.
    
- Puede actualizar el contenido de Skype Empresarial Server ayuda del Shell de administración mediante la ejecución del cmdlet [Update-Help.](/powershell/module/microsoft.powershell.core/update-help) El cmdlet Update-Help descarga e instala los archivos de ayuda más recientes disponibles para todos los módulos instalados en el equipo, incluidas las actualizaciones de Skype Empresarial cmdlets.
    
    De forma predeterminada, el cmdlet **Update-Help** actualizará todos los módulos instalados en el Skype Empresarial Server. Si desea actualizar solo determinados módulos, puede usar el parámetro _Module_ para limitar el ámbito del cmdlet. En el siguiente ejemplo solo se actualiza el Skype Empresarial módulo.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Si necesita actualizar la Ayuda en servidores que no están conectados a Internet, puede usar el cmdlet [Save-Help](/powershell/module/microsoft.powershell.core/save-help) para obtener la versión más reciente de la ayuda y guardarla en una ubicación que especifique. A continuación, puede usar el cmdlet **Update-Help** con el parámetro _-SourcePath_ en servidores que no están conectados a Internet para obtener la ayuda actualizada de la ubicación seleccionada. En el ejemplo siguiente se muestra cómo guardar los archivos de ayuda en un recurso compartido de archivos de red y, a continuación, actualizar la ayuda del módulo Skype Empresarial del recurso compartido de archivos.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obtener información más detallada, consulte [About Updatable Help](/powershell/module/microsoft.powershell.core/about/about_updatable_help).
    
    > [!NOTE]
    > Si usa PowerShell de forma remota, es posible que tenga que permitir la comunicación a través de un firewall. Para obtener más información sobre los puertos que usa la comunicación remota de PowerShell, vea ¿Qué puerto [usa PowerShell Remoting?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).

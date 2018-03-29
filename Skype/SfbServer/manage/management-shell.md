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
# <a name="skype-for-business-server-2015-management-shell"></a><span data-ttu-id="cc07e-104">Shell de administración de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc07e-104">Skype for Business Server 2015 Management Shell</span></span>
 
<span data-ttu-id="cc07e-105">El Skype para el Shell de administración de servidor empresarial proporciona la interfaz de línea de comandos para la gestión y administración de servidores.</span><span class="sxs-lookup"><span data-stu-id="cc07e-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="cc07e-106">Se basa en Windows PowerShell e incluye un completo conjunto de cmdlets de gestión y administración que son específicos de Skype y los productos heredados de Lync server.</span><span class="sxs-lookup"><span data-stu-id="cc07e-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="cc07e-107">Windows PowerShell le permite administrar las aplicaciones de Microsoft desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="cc07e-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="cc07e-108">Incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo.</span><span class="sxs-lookup"><span data-stu-id="cc07e-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="cc07e-109">Windows PowerShell se presentó como una versión descargable para el sistema operativo Windows más tarde en 2006 y fue incorporado como la interfaz de línea de comandos para la administración de Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="cc07e-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="cc07e-110">Se ha incorporado en la mayoría de los productos de Microsoft Server, incluyendo servidores de Lync y Skype a partir de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cc07e-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="cc07e-111">Hay más de 700 cmdlets específicos de Lync y Skype en el Skype para el Shell de administración de servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="cc07e-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc07e-112">Skype para referencia de cmdlet de negocio se ha movido a docs.microsoft.com. Haciendo clic en los vínculos siguientes le llevará a la nueva página de docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cc07e-112">Skype for Business cmdlet reference has moved to docs.microsoft.com. Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="cc07e-113">El contenido es ahora contribuciones de la Comunidad de origen y están disponibles para abrir a través de GitHub.</span><span class="sxs-lookup"><span data-stu-id="cc07e-113">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="cc07e-114">¿Está interesado en contribuir?</span><span class="sxs-lookup"><span data-stu-id="cc07e-114">Interested in contributing?</span></span> <span data-ttu-id="cc07e-115">Consulte el archivo Léame en el repo aquí:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="cc07e-115">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="cc07e-116">Skype para Business Server 2015 incluye más de 700 cmdlets que permiten a los administradores administrar Skype para Business Server usando el Skype para el Shell de administración de servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="cc07e-116">Skype for Business Server 2015 ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="cc07e-117">Puede obtener ayuda sobre un cmdlet directamente desde la línea de comandos al escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cc07e-117">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="cc07e-118">El comando anterior recupera la Ayuda completa disponible para el cmdlet **New-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="cc07e-118">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="cc07e-119">Para ver la Ayuda de un cmdlet diferente, sustituya **CsVoicePolicy de nuevo** con el nombre del cmdlet para el que desea recibir ayuda.</span><span class="sxs-lookup"><span data-stu-id="cc07e-119">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="cc07e-120">Para obtener una lista de todos los cmdlets disponibles para administrar Skype Empresarial Server, escriba lo siguiente en el símbolo del sistema del shell:</span><span class="sxs-lookup"><span data-stu-id="cc07e-120">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="cc07e-121">Cosas que saber acerca de Windows PowerShell en Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="cc07e-121">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="cc07e-122">Para ejecutar el Skype para Business Server cmdlets, abra el Skype para el Shell de administración de servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="cc07e-122">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="cc07e-123">Si abre una ventana de Windows PowerShell, en lugar del Skype para el Shell de administración de servidor empresarial, de forma predeterminada no es capaz de ejecutar los cmdlets de Skype.</span><span class="sxs-lookup"><span data-stu-id="cc07e-123">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="cc07e-124">Para ejecutar Skype para los cmdlets Business Server desde Windows PowerShell, primero escriba lo siguiente en el símbolo del sistema de Windows PowerShell: >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="cc07e-124">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="cc07e-125">Skype para el Shell de administración de servidor empresarial se instala automáticamente en cada Skype para servidor Business Server Enterprise Edition servidor Front-End o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cc07e-125">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="cc07e-126">Puede actualizar el Skype para el contenido de la Ayuda de Shell de administración de servidor empresarial ejecutando el cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cc07e-126">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="cc07e-127">El cmdlet Update-Help se descarga e instala los archivos de ayuda más recientes disponibles para todos los módulos instalados en el equipo, incluidas las actualizaciones de Skype para los cmdlets del negocio.</span><span class="sxs-lookup"><span data-stu-id="cc07e-127">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="cc07e-128">De forma predeterminada, el cmdlet **Update-Help** actualizará todos los módulos instalados en su Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc07e-128">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="cc07e-129">Si desea actualizar sólo algunos módulos, puede utilizar el parámetro _Module_ para limitar el ámbito del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cc07e-129">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="cc07e-130">En el ejemplo siguiente se actualiza sólo el Skype para el módulo de negocios.</span><span class="sxs-lookup"><span data-stu-id="cc07e-130">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="cc07e-131">Si necesita actualizar la Ayuda en los servidores que no están conectados a internet, puede usar el cmdlet de [Guardar-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) para obtener la versión más reciente de la Ayuda y guárdelo en una ubicación que especifique.</span><span class="sxs-lookup"><span data-stu-id="cc07e-131">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="cc07e-132">A continuación, puede utilizar el cmdlet **Update-Help** con el parámetro _- SourcePath_ en servidores no conectados a internet para obtener la ayuda actualizada de la ubicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cc07e-132">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="cc07e-133">En el ejemplo siguiente se muestra cómo guardar los archivos de ayuda en un recurso compartido de red y, a continuación, actualizar la ayuda para el Skype para el módulo de negocios desde el recurso compartido de archivo.</span><span class="sxs-lookup"><span data-stu-id="cc07e-133">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
// Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="cc07e-134">Para obtener más información, consulte la [Ayuda actualizables](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="cc07e-134">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    


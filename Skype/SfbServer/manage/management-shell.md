---
title: Shell de administración de Skype Empresarial Server
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
ms.openlocfilehash: 34bf761cfa6d9cfe648360319084b3a304d9f6e6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997359"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="59435-104">Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="59435-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="59435-105">El Skype para Shell de administración de Business Server proporciona la interfaz de línea de comandos para la administración y la administración de servidores.</span><span class="sxs-lookup"><span data-stu-id="59435-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="59435-106">Se basa en Windows PowerShell e incluye un completo conjunto de cmdlets de gestión y administración que son específicos de Skype y los productos de servidor heredados de Lync.</span><span class="sxs-lookup"><span data-stu-id="59435-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="59435-107">Windows PowerShell permite administrar las aplicaciones de Microsoft desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="59435-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="59435-108">Incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo.</span><span class="sxs-lookup"><span data-stu-id="59435-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="59435-109">Windows PowerShell se introdujo por primera vez como una versión descargable para el sistema operativo Windows más tarde en 2006 y se ha incorporado como la interfaz de línea de comandos para la administración de Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59435-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="59435-110">Lo se ha incorporado a la mayoría de los productos de Microsoft Server, incluidos los servidores de Lync y Skype a partir de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59435-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="59435-111">Hay más de 700 cmdlets específicos de Lync y Skype disponibles en el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="59435-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="59435-112">Skype para referencia del cmdlet de negocio se ha trasladado al docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="59435-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="59435-113">Al hacer clic en los vínculos siguientes le llevará a la nueva página de docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="59435-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="59435-114">El contenido es ahora contribuciones de la Comunidad de origen y están disponibles para abrir a través de depósito.</span><span class="sxs-lookup"><span data-stu-id="59435-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="59435-115">¿Está interesado en que han contribuido?</span><span class="sxs-lookup"><span data-stu-id="59435-115">Interested in contributing?</span></span> <span data-ttu-id="59435-116">Desproteger el archivo Léame de la repo aquí:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="59435-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="59435-117">Skype para Business Server se distribuye con más de 700 cmdlets que permiten a los administradores administrar Skype para Business Server mediante el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="59435-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="59435-118">Puede obtener ayuda sobre un cmdlet directamente desde la línea de comandos al escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="59435-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="59435-119">El comando anterior recupera la Ayuda completa disponible para el cmdlet **New-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="59435-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="59435-120">Para ver la Ayuda de un cmdlet diferente, sustituya **New-CsVoicePolicy** con el nombre del cmdlet para la que desea obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="59435-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="59435-121">Para obtener una lista de todos los cmdlets disponibles para administrar Skype Empresarial Server, escriba lo siguiente en el símbolo del sistema del shell:</span><span class="sxs-lookup"><span data-stu-id="59435-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="59435-122">Cosas que debe saber acerca de Windows PowerShell en Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="59435-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="59435-123">Para ejecutar la Skype para cmdlets de Business Server, abra el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="59435-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="59435-124">Si abre una ventana de Windows PowerShell en lugar de la Skype para Shell de administración de servidor empresarial, de forma predeterminada es es posible que no pueda ejecutar los cmdlets de Skype.</span><span class="sxs-lookup"><span data-stu-id="59435-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="59435-125">Para ejecutar Skype para Business Server cmdlets de Windows PowerShell, escriba lo siguiente en primer lugar en el símbolo del sistema de Windows PowerShell: >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="59435-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="59435-126">Skype para Shell de administración de Business Server se instala automáticamente en cada Skype para Business Server Enterprise Edition servidor Front-End o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="59435-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="59435-127">Puede actualizar el Skype para el contenido de Ayuda del Shell de administración de servidor empresarial ejecutando el cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="59435-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="59435-128">El cmdlet Update-Help descarga e instala los archivos de ayuda más recientes disponibles para todos los módulos instalados en el equipo, incluidas las actualizaciones de Skype para cmdlets de negocio.</span><span class="sxs-lookup"><span data-stu-id="59435-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="59435-129">De forma predeterminada, el cmdlet **Update-Help** actualizará todos los módulos instalados en su Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="59435-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="59435-130">Si desea actualizar solo determinadas módulos, puede usar el parámetro de _módulo_ para limitar el ámbito del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="59435-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="59435-131">En el ejemplo siguiente se actualiza sólo la Skype para módulo empresarial.</span><span class="sxs-lookup"><span data-stu-id="59435-131">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="59435-132">Si necesita actualizar la Ayuda en los servidores que no están conectados a internet, puede usar el cmdlet [Guardar-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) para obtener la versión más reciente de la Ayuda y guardarlo en una ubicación que especifique.</span><span class="sxs-lookup"><span data-stu-id="59435-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="59435-133">A continuación, puede usar el cmdlet **Update-Help** con el parámetro _- SourcePath_ en servidores que no está conectado a internet para obtener la ayuda actualizada desde la ubicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="59435-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="59435-134">En el ejemplo siguiente se muestra cómo guardar los archivos de ayuda en un recurso compartido de red y, a continuación, actualice la ayuda para el Skype para módulo empresarial desde el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="59435-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="59435-135">Para obtener información más detallada, consulte la [Ayuda actualizable](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="59435-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="59435-136">Si está usando PowerShell de forma remota debe permitir la comunicación a través de un firewall.</span><span class="sxs-lookup"><span data-stu-id="59435-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="59435-137">Para obtener más información acerca de los usos de comunicación remota de PowerShell de puertos, vea [¿qué Does PowerShell comunicación remota de uso del puerto?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="59435-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    


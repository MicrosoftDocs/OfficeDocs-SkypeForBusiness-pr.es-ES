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
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="a4451-104">Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a4451-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="a4451-105">El Shell de administración de Skype Empresarial Server proporciona la interfaz de línea de comandos para la administración y administración de servidores.</span><span class="sxs-lookup"><span data-stu-id="a4451-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="a4451-106">Se basa en Windows PowerShell e incluye un conjunto completo de cmdlets de administración y administración que son específicos de Skype y los productos de lync server heredados.</span><span class="sxs-lookup"><span data-stu-id="a4451-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="a4451-107">Windows PowerShell permite administrar aplicaciones de Microsoft desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a4451-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="a4451-108">Incluye un entorno de línea de comandos, comandos específicos de producto y un lenguaje de scripting completo.</span><span class="sxs-lookup"><span data-stu-id="a4451-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="a4451-109">Windows PowerShell se introdujo por primera vez como una versión descargable para el sistema operativo Windows a finales de 2006 y se incorporó como la interfaz de línea de comandos para la capacidad de administración de Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a4451-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="a4451-110">Se ha incorporado a la mayoría de los productos de Microsoft Server, incluidos los servidores de Lync y Skype a partir de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a4451-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="a4451-111">Hay más de 700 cmdlets específicos de Lync y Skype disponibles en el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a4451-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4451-112">La referencia del cmdlet de Skype Empresarial se ha movido a docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a4451-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="a4451-113">Al hacer clic en los vínculos siguientes, te llevará a la nueva docs.microsoft.com página.</span><span class="sxs-lookup"><span data-stu-id="a4451-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="a4451-114">El contenido ahora tiene código abierto y está disponible para las contribuciones de la comunidad a través de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a4451-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="a4451-115">¿Está interesado en colaborar?</span><span class="sxs-lookup"><span data-stu-id="a4451-115">Interested in contributing?</span></span> <span data-ttu-id="a4451-116">Echa un vistazo a README en el repositorio aquí: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="a4451-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="a4451-117">Skype Empresarial Server incluye más de 700 cmdlets que permiten a los administradores administrar Skype Empresarial Server mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a4451-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="a4451-118">Puede recuperar ayuda para un cmdlet directamente desde la línea de comandos escribiendo un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4451-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="a4451-119">El comando anterior recupera toda la ayuda disponible para el cmdlet **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="a4451-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="a4451-120">Si desea ver la ayuda de otro cmdlet, reemplace la referencia a **New-CsVoicePolicy** por el nombre del cmdlet cuya información de ayuda desea recuperar.</span><span class="sxs-lookup"><span data-stu-id="a4451-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="a4451-121">Para recuperar una lista completa de cmdlets disponibles para administrar Skype Empresarial Server, escriba lo siguiente en el símbolo del sistema del shell:</span><span class="sxs-lookup"><span data-stu-id="a4451-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="a4451-122">Cosas que debe saber sobre Windows PowerShell en Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="a4451-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="a4451-123">Para ejecutar los cmdlets de Skype Empresarial Server, abra el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a4451-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a4451-124">Si abre una ventana Windows PowerShell en lugar del Shell de administración de Skype Empresarial Server, es posible que no pueda ejecutar los cmdlets de Skype de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a4451-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="a4451-125">Para ejecutar cmdlets de Skype Empresarial Server desde dentro de Windows PowerShell, escriba primero lo siguiente en el símbolo del sistema Windows PowerShell comando: >  `Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="a4451-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="a4451-126">El Shell de administración de Skype Empresarial Server se instala automáticamente en cada servidor front-end o servidor Standard Edition de Skype Empresarial Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a4451-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="a4451-127">Puede actualizar el contenido de ayuda del Shell de administración de Skype Empresarial Server ejecutando el cmdlet [Update-Help.](https://technet.microsoft.com/library/hh849720.aspx)</span><span class="sxs-lookup"><span data-stu-id="a4451-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="a4451-128">El cmdlet Update-Help descarga e instala los archivos de ayuda más recientes disponibles para todos los módulos instalados en el equipo, incluidas las actualizaciones de los cmdlets de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="a4451-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="a4451-129">De forma predeterminada, el cmdlet **Update-Help** actualizará todos los módulos instalados en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a4451-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="a4451-130">Si desea actualizar solo determinados módulos, puede usar el parámetro _Module_ para limitar el ámbito del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a4451-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="a4451-131">En el siguiente ejemplo solo se actualiza el módulo de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="a4451-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="a4451-132">Si necesita actualizar la Ayuda en servidores que no están conectados a Internet, puede usar el cmdlet [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) para obtener la versión más reciente de la ayuda y guardarla en la ubicación que especifique.</span><span class="sxs-lookup"><span data-stu-id="a4451-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="a4451-133">A continuación, puede usar el cmdlet **Update-Help** con el parámetro _-SourcePath_ en servidores que no están conectados a Internet para obtener la ayuda actualizada de la ubicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a4451-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="a4451-134">En el siguiente ejemplo se muestra cómo guardar los archivos de ayuda en un recurso compartido de archivos de red y, a continuación, actualizar la ayuda para el módulo de Skype Empresarial desde el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="a4451-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="a4451-135">Para obtener información más detallada, consulte [Acerca de la Ayuda actualizable.](https://technet.microsoft.com/library/hh847735.aspx)</span><span class="sxs-lookup"><span data-stu-id="a4451-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a4451-136">Si usa PowerShell de forma remota, es posible que tenga que permitir la comunicación a través de un firewall.</span><span class="sxs-lookup"><span data-stu-id="a4451-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="a4451-137">Para obtener más información sobre los puertos que usa la comunicación remota de PowerShell, vea ¿Qué puerto usa la comunicación remota [de PowerShell?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="a4451-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    


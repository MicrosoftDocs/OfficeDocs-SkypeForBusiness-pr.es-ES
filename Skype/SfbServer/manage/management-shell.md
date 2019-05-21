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
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="fa3a8-104">Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="fa3a8-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="fa3a8-105">El shell de administración de Skype empresarial proporciona la interfaz de línea de comandos para la administración y administración del servidor.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="fa3a8-106">Se ha creado en Windows PowerShell e incluye un conjunto completo de cmdlets de administración y administración específicos de Skype y los productos heredados de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="fa3a8-107">Windows PowerShell le permite administrar aplicaciones de Microsoft desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="fa3a8-108">Incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="fa3a8-109">Windows PowerShell se presentó por primera vez como una versión descargable para el sistema operativo Windows en 2006, y se incorporó como la interfaz de línea de comandos para la capacidad de administración de Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="fa3a8-110">Se ha incorporado en la mayoría de los productos de servidor de Microsoft, incluidos los de Lync y Skype, a partir de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="fa3a8-111">Hay más de 700 cmdlets específicos de Lync y Skype disponibles en el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa3a8-112">La referencia del cmdlet de Skype empresarial se ha movido a docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="fa3a8-113">Al hacer clic en los vínculos siguientes te llevará a la nueva página de docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="fa3a8-114">El contenido ahora está abierto y disponible para las contribuciones de la comunidad a través de GitHub.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="fa3a8-115">¿Está interesado en colaborar?</span><span class="sxs-lookup"><span data-stu-id="fa3a8-115">Interested in contributing?</span></span> <span data-ttu-id="fa3a8-116">Consulte el archivo Léame en el repositorio aquí:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="fa3a8-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="fa3a8-117">Skype empresarial Server incluye más de 700 cmdlets que permiten a los administradores administrar Skype empresarial Server mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="fa3a8-118">Puede obtener ayuda sobre un cmdlet directamente desde la línea de comandos al escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa3a8-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="fa3a8-119">El comando anterior recupera toda la ayuda disponible para el cmdlet **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="fa3a8-120">Si desea ver la ayuda de otro cmdlet, cambie **New-CsVoicePolicy** por el nombre del cmdlet cuya ayuda desea obtener.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="fa3a8-121">Para obtener una lista de todos los cmdlets disponibles para administrar Skype Empresarial Server, escriba lo siguiente en el símbolo del sistema del shell:</span><span class="sxs-lookup"><span data-stu-id="fa3a8-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="fa3a8-122">Cosas que debe saber sobre Windows PowerShell en Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="fa3a8-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="fa3a8-123">Para ejecutar los cmdlets de Skype empresarial Server, abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="fa3a8-124">Si abre una ventana de Windows PowerShell en lugar del shell de administración de Skype empresarial Server, de forma predeterminada, es posible que no pueda ejecutar los cmdlets de Skype.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="fa3a8-125">Para ejecutar los cmdlets de Skype empresarial Server desde Windows PowerShell, en primer lugar escriba lo siguiente en el símbolo del sistema de Windows PowerShell: >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="fa3a8-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="fa3a8-126">El shell de administración de Skype empresarial Server se instala automáticamente en todos los servidores front-end de Skype empresarial Server Enterprise Edition o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="fa3a8-127">Puede actualizar el contenido de la ayuda del shell de administración de Skype empresarial Server ejecutando el cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="fa3a8-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="fa3a8-128">El cmdlet Update-Help descarga e instala los archivos de ayuda más recientes disponibles para todos los módulos instalados en el equipo, incluidas las actualizaciones de los cmdlets de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="fa3a8-129">De forma predeterminada, el cmdlet **Update-Help** actualiza todos los módulos instalados en su servidor de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="fa3a8-130">Si desea actualizar solo determinados módulos, puede usar el parámetro _Module_ a fin de limitar el ámbito del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="fa3a8-131">En el siguiente ejemplo se actualiza únicamente el módulo de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-131">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="fa3a8-132">Si necesita actualizar la ayuda en servidores que no están conectados a Internet, puede usar el cmdlet [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) para obtener la última versión de la ayuda y guardarla en la ubicación que especifique.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="fa3a8-133">Después, puede usar el cmdlet **Update-Help** con el parámetro _-SourcePath_ en servidores que no están conectados a Internet para obtener la ayuda actualizada desde la ubicación que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="fa3a8-134">En el ejemplo siguiente se muestra cómo guardar los archivos de ayuda en un recurso compartido de archivos de red y, a continuación, actualizar la ayuda del módulo Skype empresarial desde el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="fa3a8-135">Para obtener información más detallada, consulte [acerca de la ayuda actualizable](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa3a8-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa3a8-136">Si está usando PowerShell de forma remota, es posible que tenga que permitir la comunicación a través de un firewall.</span><span class="sxs-lookup"><span data-stu-id="fa3a8-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="fa3a8-137">Para obtener más información sobre los puertos que usa la comunicación remota de PowerShell, vea [¿qué puerto usa el servicio de comunicación remota de PowerShell?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)</span><span class="sxs-lookup"><span data-stu-id="fa3a8-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    


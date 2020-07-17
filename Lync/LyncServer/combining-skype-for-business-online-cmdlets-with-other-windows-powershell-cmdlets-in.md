---
title: Combinar los cmdlets de Skype empresarial online con otros cmdlets de Windows PowerShell en
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd4f08370e5aeab6688fdbf2ce13a3e5ccb11a37
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="e4256-102">Combinar los cmdlets de Skype empresarial online con otros cmdlets de Windows PowerShell en</span><span class="sxs-lookup"><span data-stu-id="e4256-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4256-103">_**Última modificación del tema:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="e4256-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="e4256-104">Al conectarse a Skype empresarial online mediante Windows PowerShell, aproximadamente 40 cmdlets de Skype empresarial online estarán disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="e4256-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="e4256-105">Sin embargo, no está limitado a usar solo esos cmdlets 40 al administrar Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="e4256-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="e4256-106">Además de los cmdlets de Skype empresarial online, también puede usar otros cmdlets de Windows PowerShell que estén instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e4256-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="e4256-107">(Al instalar Windows PowerShell 3,0, también se instalan cientos de cmdlets de Windows PowerShell principales). Los comandos pueden combinar y hacer coincidir los cmdlets de Skype empresarial online y cualquier otro cmdlet disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e4256-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="e4256-108">Aunque un curso completo de Windows PowerShell 3,0 va más allá del ámbito de este artículo, a continuación se muestran algunos ejemplos que muestran por qué es posible que desee combinar y hacer coincidir los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e4256-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="e4256-109">En primer lugar, ninguno de los cmdlets de Skype empresarial online incluye un comando Print y no se puede encontrar dicho comando en la consola de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4256-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="e4256-110">¿Cómo se obtiene una copia impresa de la información recuperada por un cmdlet?</span><span class="sxs-lookup"><span data-stu-id="e4256-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="e4256-111">Una forma de hacerlo es recuperar la información y enviarla al cmdlet **out-Printer** :</span><span class="sxs-lookup"><span data-stu-id="e4256-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="e4256-112">Como no se incluye ningún parámetro adicional, toda la información devuelta por **el cmdlet out-Printer** se imprimirá en la impresora predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e4256-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="e4256-113">De forma similar, ninguno de los cmdlets de Skype empresarial online incluye un parámetro que permite guardar datos en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e4256-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="e4256-114">Pero esto es correcto: este comando usa el cmdlet **out-File** para guardar la información devuelta en el archivo de texto C: \\ logs \\Tenants.txt:</span><span class="sxs-lookup"><span data-stu-id="e4256-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="e4256-115">Y este comando usa el cmdlet **Select-Object** para limitar los datos que se devuelven y que se muestran en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="e4256-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="e4256-116">En este ejemplo, el cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) recupera información de todos los usuarios de Skype empresarial online y, a continuación, el cmdlet **Select-Object** se usa para limitar los datos que se muestran al valor de identidad del usuario y a su Directiva de archivado:</span><span class="sxs-lookup"><span data-stu-id="e4256-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="e4256-117">Como habrá cientos de cmdlets disponibles para su uso en el equipo, es posible que tenga dificultades para determinar qué cmdlets son los cmdlets de Skype empresarial online y cuáles no.</span><span class="sxs-lookup"><span data-stu-id="e4256-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="e4256-118">Para obtener una lista de los cmdlets de Skype empresarial online (y solo los cmdlets de Skype empresarial online), primero debe determinar el nombre del módulo temporal de Windows PowerShell que contiene todos los cmdlets de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="e4256-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="e4256-119">Para ello, ejecute este comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e4256-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="e4256-120">La información similar a la siguiente aparecerá en la pantalla:</span><span class="sxs-lookup"><span data-stu-id="e4256-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="e4256-121">El módulo con el script de ModuleType es el módulo que contiene los cmdlets de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="e4256-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="e4256-122">Para obtener una lista de estos cmdlets, ejecute el cmdlet **get-command** , usando el nombre del módulo de script como el nombre del módulo:</span><span class="sxs-lookup"><span data-stu-id="e4256-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="e4256-123">Es posible tener varios módulos con un valor de ModuleType igual a script.</span><span class="sxs-lookup"><span data-stu-id="e4256-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="e4256-124">En ese caso, puede ejecutar el siguiente comando para averiguar qué módulo incluye el cmdlet **Get-CsTenant** :</span><span class="sxs-lookup"><span data-stu-id="e4256-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="e4256-125">El módulo devuelto para el cmdlet **Get-CsTenant** será el módulo que contiene todos los cmdlets de Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="e4256-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="e4256-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4256-126">See Also</span></span>


<span data-ttu-id="e4256-127">[Introducción a Windows PowerShell y Skype empresarial online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4256-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


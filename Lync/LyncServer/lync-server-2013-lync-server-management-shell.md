---
title: 'Lync Server 2013: Shell de administración de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d8ba2330e59d4f352407d94c6e73f96a5fff816
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="41883-102">Shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41883-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41883-103">_**Última modificación del tema:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="41883-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41883-104">La referencia del cmdlet de Skype empresarial se ha movido a docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="41883-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="41883-105">Al hacer clic en los siguientes vínculos, se le llevará a la nueva página de docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="41883-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="41883-106">El contenido se encuentra ahora abierto y disponible para contribuciones de la comunidad a través de GitHub.</span><span class="sxs-lookup"><span data-stu-id="41883-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="41883-107">¿Está interesado en colaborar?</span><span class="sxs-lookup"><span data-stu-id="41883-107">Interested in contributing?</span></span> <span data-ttu-id="41883-108">Consulte el archivo Léame en el repositorio aquí:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="41883-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="41883-109">Microsoft Lync Server 2010 introdujo un gran conjunto de características nuevas y mejoradas en comparación con lo que estaba disponible en Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="41883-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="41883-110">Una de las mejoras es la manera de administrar la implementación.</span><span class="sxs-lookup"><span data-stu-id="41883-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="41883-111">Por ejemplo, hay una nueva interfaz de usuario, denominada panel de control de Lync Server, que representa un gran cambio de lo que la mayoría de las personas se usan con Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="41883-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="41883-112">La otra mejora importante de la administración es la inclusión de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41883-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="41883-113">Windows PowerShell le permite administrar las aplicaciones de Microsoft desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="41883-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="41883-114">Incluye un entorno de línea de comandos, comandos específicos de producto y un lenguaje de scripting completo.</span><span class="sxs-lookup"><span data-stu-id="41883-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="41883-115">Windows PowerShell se introdujo por primera vez como una versión descargable para el sistema operativo Windows más tarde en 2006 y se incorporó como la interfaz de línea de comandos para la administración de Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="41883-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="41883-116">A partir de ese punto, continuó creciendo y se ha incorporado a la mayoría de los productos de servidor de Microsoft, la más reciente es Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41883-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="41883-117">Lync Server 2010 presentaba cerca de 550 cmdlets específicos del producto que puede usar para administrar todos los aspectos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="41883-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="41883-118">Las secciones siguientes contienen una lista de cmdlets y sus descripciones.</span><span class="sxs-lookup"><span data-stu-id="41883-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="41883-119">Esta información también está disponible directamente desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="41883-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="41883-120">Basta con escribir lo siguiente en el símbolo del sistema del shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="41883-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="41883-121">Por ejemplo, para obtener ayuda en el símbolo del sistema sobre el cmdlet **New-CsVoicePolicy**, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41883-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="41883-122">Aspectos que debe conocer sobre Windows PowerShell en Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="41883-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="41883-123">Para ejecutar los cmdlets de Lync Server, abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41883-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="41883-124">Si abre una ventana de Windows PowerShell en lugar del shell de administración de Lync Server, de forma predeterminada, no podrá ejecutar los cmdlets de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41883-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="41883-125">Para ejecutar los cmdlets de Lync Server desde dentro de Windows PowerShell, primero escriba lo siguiente en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="41883-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="41883-126">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="41883-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="41883-127">El shell de administración de Lync Server se instala automáticamente en cada servidor front-end de Lync Server Enterprise Edition o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="41883-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="41883-128">La información nueva y actualizada, los scripts de ejemplo y la ayuda para empezar y aprender más acerca de Windows PowerShell y los cmdlets de 2013 de Microsoft Lync Server están disponibles [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)en el blog de Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41883-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


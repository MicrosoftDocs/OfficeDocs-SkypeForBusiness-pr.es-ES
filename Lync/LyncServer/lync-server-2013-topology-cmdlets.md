---
title: 'Lync Server 2013: cmdlets de topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology cmdlets
ms:assetid: 3ed739a7-d58d-475d-8240-fa8d2c6dc7e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415648(v=OCS.15)
ms:contentKeyID: 48183942
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7524098f256587820beaabe31a8162591ba595d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="fe6ac-102">Cmdlets de topología Jn Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe6ac-102">Topology cmdlets jn Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe6ac-103">_**Última modificación del tema:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="fe6ac-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="fe6ac-104">Muchos de los cmdlets de topología incluidos en Microsoft Lync Server 2013 están diseñados para su uso con la configuración y el generador de topología; por eso, hay varios cmdlets de topología que los administradores suelen llamar directamente.</span><span class="sxs-lookup"><span data-stu-id="fe6ac-104">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="fe6ac-105">Sin embargo, habrá ocasiones en que los administradores necesiten usar estos cmdlets; por ejemplo, después de crear nuevas cuentas Kerberos, debe ejecutar el cmdlet [enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15)) para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="fe6ac-105">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="fe6ac-106">Además, es probable que los administradores ejecuten cmdlets como [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15)) y [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15)) para asegurarse de que Lync Server 2013 se haya instalado correctamente y de que funcione de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="fe6ac-106">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="fe6ac-107">Cmdlets de topología</span><span class="sxs-lookup"><span data-stu-id="fe6ac-107">Topology Cmdlets</span></span>

<span data-ttu-id="fe6ac-108">A continuación se muestra una lista de cmdlets que se relacionan directamente con la administración de la topología de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="fe6ac-108">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="fe6ac-109">**Topología**</span><span class="sxs-lookup"><span data-stu-id="fe6ac-109">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="fe6ac-110">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-110">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fe6ac-111">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-111">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe6ac-112">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-112">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fe6ac-113">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-113">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe6ac-114">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-114">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe6ac-115">[Publicar-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-115">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe6ac-116">[Prueba-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-116">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fe6ac-117">[Exportar-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-117">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe6ac-118">[Importar-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-118">[Import-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fe6ac-119">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-119">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fe6ac-120">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-120">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe6ac-121">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-121">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe6ac-122">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-122">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fe6ac-123">[Prueba-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-123">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fe6ac-124">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fe6ac-124">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe6ac-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe6ac-125">See Also</span></span>


[<span data-ttu-id="fe6ac-126">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe6ac-126">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


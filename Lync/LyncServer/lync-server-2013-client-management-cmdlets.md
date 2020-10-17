---
title: 'Lync Server 2013: cmdlets de administración de clientes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client management cmdlets
ms:assetid: 0384f8ab-453d-49d6-aaa7-52439e27b7e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398087(v=OCS.15)
ms:contentKeyID: 48183261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f141ecdcf55347ac5ace63eaa8733a8b88bb58b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507877"
---
# <a name="client-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="09127-102">Cmdlets de administración de clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09127-102">Client management cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09127-103">_**Última modificación del tema:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="09127-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="09127-104">La administración de clientes consiste principalmente en determinar qué aplicaciones cliente (como Microsoft Lync 2013) se permitirá iniciar sesión en Lync Server 2013 y determinar las capacidades disponibles para las aplicaciones cliente una vez que hayan iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="09127-104">Client management consists primarily of determining which client applications (such as Microsoft Lync 2013) will be allowed to log on to Lync Server 2013 and determining the capabilities available to those client applications after they have logged on.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="09127-105">Para obtener más información acerca de los cmdlets, vea el blog de Lync Server &nbsp; Windows PowerShell en <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A> .</span><span class="sxs-lookup"><span data-stu-id="09127-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="09127-106">El contenido de cada blog y su dirección URL están sujetos a cambio sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="09127-106">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="client-management-cmdlets"></a><span data-ttu-id="09127-107">Cmdlets de administración de clientes</span><span class="sxs-lookup"><span data-stu-id="09127-107">Client Management Cmdlets</span></span>

<span data-ttu-id="09127-108">La mayoría de las tareas de administración que se aplican a la administración de clientes se pueden realizar desde el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09127-108">Most management tasks that apply to client management can be performed from the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="09127-109">Estas mismas tareas se pueden realizar con cmdlets desde el shell de administración de Lync Server o desde un script.</span><span class="sxs-lookup"><span data-stu-id="09127-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="09127-110">El uso de un script permite automatizar determinadas tareas.</span><span class="sxs-lookup"><span data-stu-id="09127-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="09127-111">A continuación se presenta una lista de cmdlets directamente relacionados con la administración de clientes:</span><span class="sxs-lookup"><span data-stu-id="09127-111">The following is a list of cmdlets that relate directly to client management:</span></span>

  - <span></span>  
    <span data-ttu-id="09127-112">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-112">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-113">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-113">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-114">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-114">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-115">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-115">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-116">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-116">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="09127-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="09127-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="09127-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="09127-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="09127-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09127-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


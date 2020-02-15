---
title: 'Lync Server 2013: modificar un tronco en el generador de topologías'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5b4c69fdf4b7dbad79f4b9c2627e74ea855cd02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="3670a-102">Modificar un tronco en el generador de topologías en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3670a-102">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3670a-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3670a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3670a-104">Siga estos pasos para modificar la dirección IP de medios alternativa y el identificador alternativo por omisión de tronco.</span><span class="sxs-lookup"><span data-stu-id="3670a-104">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="3670a-105">Para modificar la dirección IP de medios alternativa de un tronco</span><span class="sxs-lookup"><span data-stu-id="3670a-105">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="3670a-106">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3670a-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3670a-107">Ejecute el cmdlet Set-CsPstnGateway y modifique el campo AlternateBypassId en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3670a-107">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="3670a-108">Para modificar el BypassID alternativo de un tronco</span><span class="sxs-lookup"><span data-stu-id="3670a-108">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="3670a-109">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3670a-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3670a-110">Ejecute el cmdlet Set-CsPstnGateway y modifique el campo AlternateBypassId en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3670a-110">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>


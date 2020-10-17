---
title: 'Lync Server 2013: modificar un tronco en el generador de topologías'
description: 'Lync Server 2013: modificar un tronco en el generador de topologías.'
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
ms.openlocfilehash: 5f453997664dbe3048a7aa915732b4d95a932dd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550486"
---
# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="99edf-103">Modificar un tronco en el generador de topologías en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99edf-103">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99edf-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="99edf-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="99edf-105">Siga estos pasos para modificar la dirección IP de medios alternativa y el identificador alternativo por omisión de tronco.</span><span class="sxs-lookup"><span data-stu-id="99edf-105">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="99edf-106">Para modificar la dirección IP de medios alternativa de un tronco</span><span class="sxs-lookup"><span data-stu-id="99edf-106">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="99edf-107">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="99edf-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="99edf-108">Ejecute el cmdlet Set-CsPstnGateway y modifique el campo AlternateBypassId en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99edf-108">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="99edf-109">Para modificar el BypassID alternativo de un tronco</span><span class="sxs-lookup"><span data-stu-id="99edf-109">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="99edf-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="99edf-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="99edf-111">Ejecute el cmdlet Set-CsPstnGateway y modifique el campo AlternateBypassId en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99edf-111">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>


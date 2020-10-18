---
title: Migrar dispositivos analógicos
description: Migrar dispositivos analógicos.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f7f92142fb6a3ced37cded1a223038ec1876d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579406"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="db615-103">Migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="db615-103">Migrate analog devices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db615-104">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="db615-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="db615-105">Lync Server proporciona soporte para dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="db615-105">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="db615-106">En concreto, los dispositivos analógicos compatibles son los teléfonos de audio analógicos y los equipos de fax analógicos.</span><span class="sxs-lookup"><span data-stu-id="db615-106">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="db615-107">Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en su entorno de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db615-107">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="db615-108">Después de migrar de Lync Server 2010 a Lync Server 2013, también debe migrar los objetos de contacto asociados con los dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="db615-108">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="db615-109">Use el shell de administración de Lync Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos de Lync Server 2010 y, a continuación, mover dichos objetos al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db615-109">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="db615-110">Para migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="db615-110">To migrate analog devices</span></span>

1.  <span data-ttu-id="db615-111">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="db615-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="db615-112">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db615-112">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="db615-113">Compruebe que todos los objetos de contacto se han movido al grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="db615-113">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="db615-114">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db615-114">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="db615-115">Compruebe que todos los objetos de contacto están ahora asociados con el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db615-115">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


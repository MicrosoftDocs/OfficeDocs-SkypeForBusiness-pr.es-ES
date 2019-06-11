---
title: Migrar dispositivos analógicos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66866ee7cb6dafecb2c30b53d04a50f849f09c94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="af171-102">Migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="af171-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af171-103">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="af171-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="af171-104">Lync Server proporciona compatibilidad con dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="af171-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="af171-105">Específicamente, los dispositivos analógicos compatibles son teléfonos de audio analógicos y equipos de fax analógico.</span><span class="sxs-lookup"><span data-stu-id="af171-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="af171-106">Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en el entorno de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af171-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="af171-107">Después de migrar de Lync Server 2010 a Lync Server 2013, también debe migrar los objetos de contacto asociados con los dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="af171-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="af171-108">Use el shell de administración de Lync Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos de Lync Server 2010 y, a continuación, mueva esos objetos al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af171-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="af171-109">Para migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="af171-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="af171-110">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="af171-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="af171-111">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="af171-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="af171-112">Compruebe que todos los objetos de contacto se han movido al grupo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af171-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="af171-113">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="af171-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="af171-114">Compruebe que todos los objetos de contacto están asociados con el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af171-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


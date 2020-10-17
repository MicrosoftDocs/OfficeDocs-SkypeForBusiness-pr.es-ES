---
title: Migrar dispositivos analógicos
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
ms.openlocfilehash: feb0f29f9a217676829ff3869fcda3759359944b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503617"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="f07ba-102">Migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="f07ba-102">Migrate analog devices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f07ba-103">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f07ba-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f07ba-104">Lync Server proporciona soporte para dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="f07ba-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="f07ba-105">En concreto, los dispositivos analógicos compatibles son los teléfonos de audio analógicos y los equipos de fax analógicos.</span><span class="sxs-lookup"><span data-stu-id="f07ba-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="f07ba-106">Puede configurar las puertas de enlace calificadas para que admitan el uso de dispositivos analógicos en su entorno de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f07ba-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="f07ba-107">Después de migrar de Lync Server 2010 a Lync Server 2013, también debe migrar los objetos de contacto asociados con los dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="f07ba-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="f07ba-108">Use el shell de administración de Lync Server para recuperar primero todos los objetos de contacto asociados con los dispositivos analógicos de Lync Server 2010 y, a continuación, mover dichos objetos al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f07ba-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="f07ba-109">Para migrar dispositivos analógicos</span><span class="sxs-lookup"><span data-stu-id="f07ba-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="f07ba-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f07ba-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f07ba-111">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f07ba-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="f07ba-112">Compruebe que todos los objetos de contacto se han movido al grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f07ba-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="f07ba-113">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f07ba-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="f07ba-114">Compruebe que todos los objetos de contacto están ahora asociados con el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f07ba-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


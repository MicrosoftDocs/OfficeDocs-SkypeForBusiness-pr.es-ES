---
title: 'Lync Server 2013: habilitar QoS para dispositivos que no se basan en Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d993a6905dfad9f5f2eda10a48553f2ae29b58ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="6e383-102">Habilitar QoS en Lync Server 2013 para dispositivos que no se basan en Windows</span><span class="sxs-lookup"><span data-stu-id="6e383-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e383-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6e383-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6e383-104">Al instalar Microsoft Lync Server 2013, no se habilitará la calidad de servicio (QoS) en los dispositivos usados en su organización que usen un sistema operativo que no sea Windows.</span><span class="sxs-lookup"><span data-stu-id="6e383-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="6e383-105">Para comprobarlo, ejecute el siguiente comando desde el shell de administración de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6e383-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="6e383-106">Suponiendo que no haya realizado cambios en la configuración de los elementos multimedia, debe obtener información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="6e383-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="6e383-107">Si la propiedad EnableQoS se establece en false (como en la salida anterior), significa que la calidad de servicio no está habilitada para los equipos y dispositivos que usan un sistema operativo que no sea Windows.</span><span class="sxs-lookup"><span data-stu-id="6e383-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="6e383-108">QoS está habilitado de forma predeterminada para los dispositivos de Lync Phone Edition; sin embargo, es posible deshabilitar la calidad de servicio para Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="6e383-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="6e383-109">Para habilitar la calidad de servicio en el ámbito global, ejecute el siguiente comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="6e383-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="6e383-110">El comando anterior habilita QoS en el ámbito global; sin embargo, es importante tener en cuenta que la configuración de los medios también se puede aplicar al ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="6e383-110">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="6e383-111">Si necesita habilitar la calidad de servicio para un sitio, debe incluir la identidad de las opciones de configuración al llamar a set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6e383-111">If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="6e383-112">Por ejemplo, este comando habilita QoS para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="6e383-112">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="6e383-113">¿Necesita habilitar QoS en el ámbito del sitio?</span><span class="sxs-lookup"><span data-stu-id="6e383-113">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="6e383-114">Eso depende.</span><span class="sxs-lookup"><span data-stu-id="6e383-114">That depends.</span></span> <span data-ttu-id="6e383-115">La configuración asignada al ámbito del sitio tiene prioridad sobre la configuración asignada al ámbito global.</span><span class="sxs-lookup"><span data-stu-id="6e383-115">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="6e383-116">Supongamos que tiene QoS habilitado en el ámbito global, pero está deshabilitado en el ámbito del sitio (para el sitio de Redmond). En ese caso, la calidad de servicio se deshabilitará para el sitio de Redmond; Esto se debe a que la configuración del sitio tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="6e383-116">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="6e383-117">Para habilitar QoS para el sitio de Redmond, tendrá que hacerlo usando las opciones de configuración de medios que se aplican a ese sitio.</span><span class="sxs-lookup"><span data-stu-id="6e383-117">To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="6e383-118">Si desea habilitar simultáneamente QoS para todos los valores de configuración multimedia (independientemente del ámbito), ejecute este comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="6e383-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="6e383-119">Puede deshabilitar QoS para dispositivos que usan un sistema operativo distinto de Windows si establece el valor de la propiedad EnableQoS en false.</span><span class="sxs-lookup"><span data-stu-id="6e383-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="6e383-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6e383-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="6e383-121">Esto le ofrece la posibilidad de implementar QoS en algunas partes de su red (por ejemplo, en el sitio de Redmond) mientras deja la calidad de servicio deshabilitada en otras partes de la red.</span><span class="sxs-lookup"><span data-stu-id="6e383-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="6e383-122">QoS solo se puede habilitar y deshabilitar mediante Windows PowerShell estas opciones no están disponibles en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e383-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Habilitación de la QoS para dispositivos que no están basados en Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Obtenga información sobre cómo habilitar QoS para los dispositivos usados en su organización que usan un sistema operativo distinto de Windows.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814180"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="67108-103">Habilitar QoS en Skype Empresarial Server para dispositivos que no están basados en Windows</span><span class="sxs-lookup"><span data-stu-id="67108-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="67108-104">Al instalar Skype Empresarial Server, la calidad de servicio (QoS) no se habilitará para los dispositivos usados en su organización que usen un sistema operativo distinto de Windows.</span><span class="sxs-lookup"><span data-stu-id="67108-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="67108-105">Para comprobarlo, ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="67108-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="67108-106">Suponiendo que no haya realizado ningún cambio en las opciones de configuración multimedia, debería obtener información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="67108-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="67108-107">Si la propiedad EnableQoS se establece en False (como en la salida anterior), significa que la calidad de servicio no está habilitada para equipos y dispositivos que usan un sistema operativo distinto de Windows.</span><span class="sxs-lookup"><span data-stu-id="67108-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="67108-108">Para habilitar la calidad de servicio en el ámbito global, ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="67108-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="67108-109">El comando anterior habilita QoS en el ámbito global; sin embargo, es importante tener en cuenta que los valores de configuración multimedia también se pueden aplicar al ámbito de sitio.</span><span class="sxs-lookup"><span data-stu-id="67108-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="67108-110">Si necesita habilitar calidad de servicio para un sitio, debe incluir la identidad de las opciones de configuración al llamar a Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="67108-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="67108-111">Por ejemplo, este comando habilita QoS para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="67108-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="67108-112">¿Tiene que habilitar QoS en el ámbito de sitio?</span><span class="sxs-lookup"><span data-stu-id="67108-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="67108-113">Depende.</span><span class="sxs-lookup"><span data-stu-id="67108-113">That depends.</span></span> <span data-ttu-id="67108-114">La configuración asignada al ámbito de sitio tiene prioridad sobre la configuración asignada al ámbito global.</span><span class="sxs-lookup"><span data-stu-id="67108-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="67108-115">Supongamos que tiene QoS habilitada en el ámbito global, pero deshabilitada en el ámbito de sitio (para el sitio Redmond).</span><span class="sxs-lookup"><span data-stu-id="67108-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="67108-116">En ese caso, la calidad de servicio se deshabilitaría para el sitio redmond; esto se debe a que la configuración del sitio tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="67108-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="67108-117">Para habilitar QoS para el sitio redmond, tendría que hacerlo con las opciones de configuración de medios aplicadas a ese sitio.</span><span class="sxs-lookup"><span data-stu-id="67108-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="67108-118">Si desea habilitar QoS simultáneamente para todas las opciones de configuración de medios (independientemente del ámbito), ejecute este comando desde el Shell de administración de LSkype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="67108-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="67108-119">Puede deshabilitar QoS para dispositivos que usan un sistema operativo distinto de Windows estableciendo el valor de la propiedad EnableQoS en False.</span><span class="sxs-lookup"><span data-stu-id="67108-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="67108-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67108-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="67108-121">Esto le ofrece la capacidad de implementar QoS en algunas partes de su red (por ejemplo, en el sitio de Redmond) a la vez que se deja la calidad de servicio deshabilitada en otras partes de la red.</span><span class="sxs-lookup"><span data-stu-id="67108-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="67108-122">QoS solo se puede habilitar y deshabilitar mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67108-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="67108-123">Estas opciones no están disponibles en el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="67108-123">These options are not available in the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="67108-124">Los clientes de Skype Empresarial para iOS versión 6.17 y posteriores ahora admiten QoS.</span><span class="sxs-lookup"><span data-stu-id="67108-124">Skype for Business clients for iOS Version 6.17 and later now support QoS.</span></span>  <span data-ttu-id="67108-125">Esta funcionalidad qoS solo se aplica a los clientes de Skype Empresarial y a los dispositivos de teléfono IP que se registran directamente en un servidor interno de skype empresarial o de grupo de Lync en redes administradas.</span><span class="sxs-lookup"><span data-stu-id="67108-125">This QoS capability is only applicable to Skype for Business clients and IP phone devices which are registered directly to an internal Skype for Business or Lync pool Server on managed networks.</span></span> <span data-ttu-id="67108-126">QoS no es aplicable para el tráfico enrutado a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="67108-126">QoS is not applicable for traffic routed over the Internet.</span></span>




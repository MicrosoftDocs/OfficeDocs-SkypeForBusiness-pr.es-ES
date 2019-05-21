---
title: Habilitación de la QoS para dispositivos que no están basados en Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga información sobre cómo habilitar QoS para los dispositivos usados en su organización que usan un sistema operativo que no sea Windows.
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279413"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="f55b2-103">Habilitar QoS en Skype empresarial Server para dispositivos que no se basan en Windows</span><span class="sxs-lookup"><span data-stu-id="f55b2-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="f55b2-104">Al instalar Skype empresarial Server, la calidad de servicio (QoS) no se habilitará para los dispositivos usados en su organización que usen un sistema operativo que no sea Windows.</span><span class="sxs-lookup"><span data-stu-id="f55b2-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="f55b2-105">Para comprobarlo, ejecute el siguiente comando desde el shell de ServerManagement de Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="f55b2-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="f55b2-106">Suponiendo que no ha realizado ningún cambio en la configuración de los medios, debe obtener información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="f55b2-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="f55b2-107">Si la propiedad EnableQoS se establece en false (como en la salida anterior), significa que la calidad de servicio no está habilitada para los equipos y dispositivos que usan un sistema operativo que no sea Windows.</span><span class="sxs-lookup"><span data-stu-id="f55b2-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="f55b2-108">Para habilitar la calidad de servicio en el ámbito global, ejecute el siguiente comando desde el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f55b2-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="f55b2-109">El comando anterior habilita QoS en el ámbito global; sin embargo, es importante tener en cuenta que la configuración de los medios también se puede aplicar al ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="f55b2-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="f55b2-110">Si necesita habilitar la calidad de servicio para un sitio, debe incluir la identidad de las opciones de configuración al llamar a set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f55b2-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="f55b2-111">Por ejemplo, este comando habilita QoS para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="f55b2-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="f55b2-112">¿Necesita habilitar QoS en el ámbito del sitio?</span><span class="sxs-lookup"><span data-stu-id="f55b2-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="f55b2-113">Eso depende.</span><span class="sxs-lookup"><span data-stu-id="f55b2-113">That depends.</span></span> <span data-ttu-id="f55b2-114">La configuración asignada al ámbito del sitio tiene prioridad sobre la configuración asignada al ámbito global.</span><span class="sxs-lookup"><span data-stu-id="f55b2-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="f55b2-115">Supongamos que tiene QoS habilitado en el ámbito global, pero está deshabilitado en el ámbito del sitio (para el sitio de Redmond).</span><span class="sxs-lookup"><span data-stu-id="f55b2-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="f55b2-116">En ese caso, la calidad de servicio sería deshabilitada para el sitio de Redmond; Esto se debe a que la configuración del sitio tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="f55b2-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="f55b2-117">Para habilitar QoS para el sitio de Redmond, tendría que hacerlo usando la configuración de medios aplicada a ese sitio.</span><span class="sxs-lookup"><span data-stu-id="f55b2-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="f55b2-118">Si desea habilitar simultáneamente QoS para todos los valores de configuración multimedia (independientemente del ámbito), ejecute este comando desde el shell de administración de LSkype para empresas:</span><span class="sxs-lookup"><span data-stu-id="f55b2-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="f55b2-119">Puede deshabilitar QoS para dispositivos que usan un sistema operativo distinto de Windows si establece el valor de la propiedad EnableQoS en false.</span><span class="sxs-lookup"><span data-stu-id="f55b2-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="f55b2-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f55b2-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="f55b2-121">Esto le ofrece la posibilidad de implementar QoS en algunas partes de su red (por ejemplo, en el sitio de Redmond) mientras deja la calidad de servicio deshabilitada en otras partes de la red.</span><span class="sxs-lookup"><span data-stu-id="f55b2-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="f55b2-122">QoS solo se puede habilitar y deshabilitar mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55b2-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="f55b2-123">Estas opciones no están disponibles en el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f55b2-123">These options are not available in the Skype for Business Server Control Panel.</span></span>



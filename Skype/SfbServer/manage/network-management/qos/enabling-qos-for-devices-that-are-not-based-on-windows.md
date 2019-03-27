---
title: Habilitación de la QoS para dispositivos que no están basados en Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga información sobre cómo habilitar QoS para dispositivos que se usan en la organización que usan un sistema operativo distinto de Windows.
ms.openlocfilehash: b1f3dae2d2b499b334995d7754282c56872ce111
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887123"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="b3639-103">Habilitar QoS en Skype para Business Server para los dispositivos que no están basados en Windows</span><span class="sxs-lookup"><span data-stu-id="b3639-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="b3639-104">Al instalar Skype para Business Server, la calidad de servicio (QoS) no se habilitará para todos los dispositivos usados en la organización que usan un sistema operativo distinto de Windows.</span><span class="sxs-lookup"><span data-stu-id="b3639-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="b3639-105">Puede comprobarlo ejecutando el siguiente comando desde dentro de la Skype para profesionales ServerManagement Shell:</span><span class="sxs-lookup"><span data-stu-id="b3639-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="b3639-106">Suponiendo que no ha realizado ningún cambio en las opciones de configuración de medios, debería obtener información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3639-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="b3639-107">Si la propiedad EnableQoS está establecida en False (como se muestra en el resultado anterior) que significa que la calidad de servicio no está habilitado para los equipos y dispositivos que usan un sistema operativo distinto de Windows.</span><span class="sxs-lookup"><span data-stu-id="b3639-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="b3639-108">Para habilitar la calidad de servicio en el ámbito global, ejecute el siguiente comando desde dentro de la Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="b3639-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="b3639-109">El comando anterior permite QoS en el ámbito global; Sin embargo, es importante tener en cuenta que también se pueden aplicar opciones de configuración de medios al ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="b3639-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="b3639-110">Si necesita habilitar la calidad de servicio para un sitio, debe incluir la identidad de las opciones de configuración cuando se llama a Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b3639-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="b3639-111">Por ejemplo, este comando habilita QoS para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="b3639-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="b3639-112">¿Necesita habilitar QoS en el ámbito del sitio?</span><span class="sxs-lookup"><span data-stu-id="b3639-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="b3639-113">Eso depende.</span><span class="sxs-lookup"><span data-stu-id="b3639-113">That depends.</span></span> <span data-ttu-id="b3639-114">La configuración asignada al ámbito del sitio tiene prioridad sobre la configuración asignada al ámbito global.</span><span class="sxs-lookup"><span data-stu-id="b3639-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="b3639-115">Suponga que tiene QoS habilitado en el ámbito global pero está deshabilitado en el ámbito del sitio (para el sitio de Redmond).</span><span class="sxs-lookup"><span data-stu-id="b3639-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="b3639-116">En ese caso, se desactivará la calidad de servicio para el sitio de Redmond; eso es porque la configuración del sitio tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="b3639-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="b3639-117">Para habilitar QoS para el sitio de Redmond, tendría hacerlo usando las opciones de configuración de medios aplicado a ese sitio.</span><span class="sxs-lookup"><span data-stu-id="b3639-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="b3639-118">Si desea habilitar de manera simultánea QoS para todas las opciones de configuración de medios (independientemente del ámbito), ejecute este comando desde dentro de la LSkype de consola de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="b3639-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="b3639-119">Puede deshabilitar QoS para dispositivos que usan un sistema operativo distinto de Windows estableciendo el valor de la propiedad EnableQoS en False.</span><span class="sxs-lookup"><span data-stu-id="b3639-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="b3639-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b3639-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="b3639-121">Esto le ofrece la posibilidad de implementar QoS en algunas partes de la red (por ejemplo, en el sitio de Redmond) dejando deshabilitados en otras partes de la red de calidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="b3639-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="b3639-122">QoS sólo puede habilitar y deshabilitar mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3639-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="b3639-123">Estas opciones no están disponibles en el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b3639-123">These options are not available in the Skype for Business Server Control Panel.</span></span>



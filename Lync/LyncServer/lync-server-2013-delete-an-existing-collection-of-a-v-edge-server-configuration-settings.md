---
title: Eliminar una colección existente de opciones de configuración del servidor perimetral A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901562812e7847a6c205f042922dca6383ad6254
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="bccca-102">Eliminar una colección existente de opciones de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bccca-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bccca-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bccca-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bccca-p101">El servicio perimetral A/V constituye un modo de que los usuarios internos (aquellos que han iniciado sesión en la red de la organización) puedan compartir audio y vídeo con los usuarios externos (aquellos que no han iniciado sesión en la red de la organización). El servicio perimetral A/V se administra principalmente a mediante la configuración de servidor perimetral A/V, que se puede definir en el ámbito de sitio o en el ámbito de servicio (esto es, se puede configurar para un solo servidor perimetral A/V).</span><span class="sxs-lookup"><span data-stu-id="bccca-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="bccca-106">Al instalar Lync Server, se crea una colección global de opciones de configuración perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="bccca-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="bccca-107">Esta colección global no se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="bccca-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="bccca-108">Sin embargo, puede usar Windows PowerShell y el cmdlet Remove-CsAVEdgeConfiguration para "restablecer" la recopilación global; Esto simplemente significa que todos los valores de propiedad de la colección global se restablecerán a su valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bccca-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="bccca-109">Por ejemplo, si ha establecido la propiedad MaxTokenLifetime para 16 horas, esa propiedad se restablecerá a su valor predeterminado de 8 horas.</span><span class="sxs-lookup"><span data-stu-id="bccca-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="bccca-p103">En cambio, las colecciones de opciones de configuración personalizadas que haya creado (ya sea en el ámbito de sitio o de servicio) se pueden eliminar con el cmdlet Remove-CsAVEdgeConfiguration. Si elimina la configuración de sitio, los servidores perimetrales A/V de dicho sitio pasarán a administrarse mediante la configuración global y, si elimina la configuración de servicio, el servidor se administrará por medio de su configuración de sitio (si la hay) o por la configuración global (en caso de que no haya configuración de sitio disponible).</span><span class="sxs-lookup"><span data-stu-id="bccca-p103">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet. If you delete site settings then A/V Edge servers in that site will be managed by the global settings. If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="bccca-113">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="bccca-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="bccca-114">Para restablecer la colección global</span><span class="sxs-lookup"><span data-stu-id="bccca-114">To reset the global collection</span></span>

  - <span data-ttu-id="bccca-115">Con el siguiente comando se restablece la colección global de la configuración de servidor perimetral A/V:</span><span class="sxs-lookup"><span data-stu-id="bccca-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="bccca-116">Para quitar una colección del ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="bccca-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="bccca-117">Con este comando se quita la configuración de servidor perimetral A/V que se ha usado en el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="bccca-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="bccca-118">Para quitar una colección del ámbito de servicio</span><span class="sxs-lookup"><span data-stu-id="bccca-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="bccca-119">Con este comando se quita la configuración utilizada en el servidor perimetral A/V atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="bccca-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bccca-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="bccca-120">See Also</span></span>


[<span data-ttu-id="bccca-121">Devolver información de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bccca-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="bccca-122">Crear o modificar una colección de opciones de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bccca-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="bccca-123">Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bccca-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="bccca-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bccca-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


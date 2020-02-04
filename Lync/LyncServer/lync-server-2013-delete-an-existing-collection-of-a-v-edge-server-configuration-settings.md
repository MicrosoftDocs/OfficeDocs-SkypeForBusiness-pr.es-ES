---
title: Eliminar una colección existente de parámetros de configuración del servidor perimetral A/V
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
ms.openlocfilehash: 7cc085cd6ac39c4712647795c5baf06eaa68f77a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="12820-102">Eliminar una colección existente de valores de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12820-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12820-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="12820-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="12820-104">El servicio perimetral A/V proporciona a los usuarios internos (los usuarios que han iniciado sesión en la red de la organización) una forma de compartir audio y vídeo con usuarios externos (usuarios que no han iniciado sesión en la red de su organización).</span><span class="sxs-lookup"><span data-stu-id="12820-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="12820-105">El servicio perimetral A/V se administra principalmente usando la configuración de borde de A/V, la configuración que se puede configurar en el ámbito del sitio o en el ámbito del servicio (es decir, se puede configurar para un servidor perimetral de A/V individual).</span><span class="sxs-lookup"><span data-stu-id="12820-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="12820-106">Al instalar Lync Server, se crea una colección global de las opciones de configuración del borde A/V.</span><span class="sxs-lookup"><span data-stu-id="12820-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="12820-107">No se puede eliminar esta colección global.</span><span class="sxs-lookup"><span data-stu-id="12820-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="12820-108">Sin embargo, puede usar Windows PowerShell y el cmdlet Remove-CsAVEdgeConfiguration para "restablecer" la colección global; eso simplemente significa que todos los valores de propiedad de la colección global se restablecerán a su valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="12820-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="12820-109">Por ejemplo, si ha establecido la propiedad MaxTokenLifetime en 16 horas, esa propiedad se restablecerá a su valor predeterminado de 8 horas.</span><span class="sxs-lookup"><span data-stu-id="12820-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="12820-110">Sin embargo, las colecciones de configuración personalizadas que haya creado en el ámbito del sitio o en el ámbito del servicio se pueden eliminar con el cmdlet Remove-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="12820-110">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="12820-111">Si elimina la configuración del sitio, los servidores perimetrales A/V de ese sitio serán administrados por la configuración global.</span><span class="sxs-lookup"><span data-stu-id="12820-111">If you delete site settings then A/V Edge servers in that site will be managed by the global settings.</span></span> <span data-ttu-id="12820-112">Si elimina la configuración de ámbito de servicio, ese servidor se administrará por la configuración del sitio, si existe, o por la configuración global, si no hay ninguna configuración de sitio disponible.</span><span class="sxs-lookup"><span data-stu-id="12820-112">If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="12820-113">Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="12820-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="12820-114">Para restablecer la colección global</span><span class="sxs-lookup"><span data-stu-id="12820-114">To reset the global collection</span></span>

  - <span data-ttu-id="12820-115">El siguiente comando restablece la colección global de valores de configuración de borde A/V:</span><span class="sxs-lookup"><span data-stu-id="12820-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="12820-116">Para quitar una colección del ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="12820-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="12820-117">Este comando quita la configuración del borde A/V que se aplica al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="12820-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="12820-118">Para quitar una colección del ámbito de servicio</span><span class="sxs-lookup"><span data-stu-id="12820-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="12820-119">Este comando quita la configuración aplicada al servidor perimetral A/V atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="12820-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12820-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="12820-120">See Also</span></span>


[<span data-ttu-id="12820-121">Devolver información de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12820-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="12820-122">Crear o modificar una colección de valores de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12820-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="12820-123">Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12820-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="12820-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="12820-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


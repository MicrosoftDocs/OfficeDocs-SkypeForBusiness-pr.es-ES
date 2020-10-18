---
title: Crear o modificar una colección de opciones de configuración del servidor perimetral A/V
description: Cree o modifique una colección de opciones de configuración del servidor perimetral A/V.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cdf7dca19446f4eac584564eed776f7fde47bfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578346"
---
# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4f796-103">Crear o modificar una colección de opciones de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f796-103">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f796-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4f796-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4f796-p101">El servicio perimetral A/V constituye un modo de que los usuarios internos (aquellos que han iniciado sesión en la red de la organización) puedan compartir audio y vídeo con los usuarios externos (aquellos que no han iniciado sesión en la red de la organización). El servicio perimetral A/V se administra principalmente a mediante la configuración de servidor perimetral A/V, que se puede definir en el ámbito de sitio o en el ámbito de servicio (esto es, se puede configurar para un solo servidor perimetral A/V).</span><span class="sxs-lookup"><span data-stu-id="4f796-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="4f796-107">Al instalar Lync Server, se crea una colección global de opciones de configuración perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="4f796-107">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="4f796-108">Además de esto, puede usar Windows PowerShell y el cmdlet New-CsAVEdgeConfiguration para crear una nueva configuración en el ámbito de sitio o el ámbito de servicio (es decir, para un servidor perimetral A/V individual).</span><span class="sxs-lookup"><span data-stu-id="4f796-108">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="4f796-109">Si crea nuevos valores, tenga en cuenta que:</span><span class="sxs-lookup"><span data-stu-id="4f796-109">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="4f796-110">Los valores configurados en el ámbito del servicio (es decir, en un servidor individual) tienen prioridad sobre todo.</span><span class="sxs-lookup"><span data-stu-id="4f796-110">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="4f796-p103">
Las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones configuradas en el ámbito global. Pero las opciones del ámbito de servicio tienen prioridad sobre las opciones del ámbito de sitio.</span><span class="sxs-lookup"><span data-stu-id="4f796-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="4f796-113">Se usarán los valores del ámbito global solo si no hay valores del servicio configurados en el servidor individual y si no hay ninguna valores del sitio para el sitio donde se encuentra el servidor.</span><span class="sxs-lookup"><span data-stu-id="4f796-113">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="4f796-114">Los valores pueden modificarse después con el cmdlet Set-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4f796-114">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="4f796-115">Para obtener más información, consulte los temas de ayuda para los cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) y [set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="4f796-115">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="4f796-116">Para crear una nueva configuración perimetral a/V en el ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="4f796-116">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="4f796-117">El comando siguiente crea una nueva colección de valores de configuración del servicio perimetral A/V para el sitio Redmond.</span><span class="sxs-lookup"><span data-stu-id="4f796-117">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="4f796-118">Para crear una configuración de servidor perimetral a/V personalizada en el ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="4f796-118">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="4f796-p105">Ya que no se incluyeron parámetros adicionales, estos nuevos valores usarán los valores predeterminados para el servicio perimetral A/V. Como alternativa, puede agregar parámetros adicionales y valores de parámetros para crear una colección personalizada. Por ejemplo, este comando establece la propiedad MaxTokenLifetime en 4 horas (04 horas : 00 minutos : 00 segundos):</span><span class="sxs-lookup"><span data-stu-id="4f796-p105">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service. Alternatively, you can add additional parameters and parameter values to create a custom collection. For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="4f796-122">Para crear una configuración de servidor perimetral a/V personalizada en el ámbito de servicio</span><span class="sxs-lookup"><span data-stu-id="4f796-122">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="4f796-123">Este comando crea una colección similar aplicada al servidor perimetral A/V atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="4f796-123">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="4f796-124">Para modificar la configuración de servidor perimetral A/V existente</span><span class="sxs-lookup"><span data-stu-id="4f796-124">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="4f796-125">En este ejemplo, se usa el cmdlet de Set-CsAVEdgeConfiguration para cambiar la vigencia máxima del token en el sitio Redmond a 12 horas:</span><span class="sxs-lookup"><span data-stu-id="4f796-125">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f796-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f796-126">See Also</span></span>


[<span data-ttu-id="4f796-127">Devolver información de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f796-127">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="4f796-128">Eliminar una colección existente de opciones de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f796-128">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="4f796-129">Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f796-129">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="4f796-130">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f796-130">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="4f796-131">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4f796-131">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Crear o modificar una colección de parámetros de configuración del servidor perimetral A/V
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
ms.openlocfilehash: 5c4b45b34b5c52d0eb138fbc16c37e5aaee7262b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a1afc-102">Crear o modificar una colección de valores de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1afc-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1afc-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a1afc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a1afc-104">El servicio perimetral A/V proporciona a los usuarios internos (los usuarios que han iniciado sesión en la red de la organización) una forma de compartir audio y vídeo con usuarios externos (usuarios que no han iniciado sesión en la red de su organización).</span><span class="sxs-lookup"><span data-stu-id="a1afc-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="a1afc-105">El servicio perimetral A/V se administra principalmente usando la configuración de borde de A/V, la configuración que se puede configurar en el ámbito del sitio o en el ámbito del servicio (es decir, se puede configurar para un servidor perimetral de A/V individual).</span><span class="sxs-lookup"><span data-stu-id="a1afc-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="a1afc-106">Al instalar Lync Server, se crea una colección global de las opciones de configuración del borde A/V.</span><span class="sxs-lookup"><span data-stu-id="a1afc-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="a1afc-107">Además, puede usar Windows PowerShell y el cmdlet New-CsAVEdgeConfiguration para crear una nueva configuración en el ámbito del sitio o en el ámbito del servicio (es decir, para un servidor perimetral A/V individual).</span><span class="sxs-lookup"><span data-stu-id="a1afc-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="a1afc-108">Si crea una nueva configuración, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1afc-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="a1afc-109">La configuración establecida en el ámbito del servicio (es decir, en un servidor individual) tiene prioridad sobre todo.</span><span class="sxs-lookup"><span data-stu-id="a1afc-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="a1afc-110">La configuración establecida en el ámbito del sitio tiene prioridad sobre la configuración establecida en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="a1afc-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="a1afc-111">Sin embargo, la configuración del ámbito del servicio también reemplaza la configuración del ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="a1afc-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="a1afc-112">La configuración del ámbito global se usará solo si no hay ninguna configuración de servicio establecida en el servidor individual y no hay configuración de sitio para el sitio en el que se encuentra el servidor.</span><span class="sxs-lookup"><span data-stu-id="a1afc-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="a1afc-113">Después, cualquiera de la configuración se puede modificar mediante el cmdlet Set-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a1afc-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="a1afc-114">Para obtener más información, consulte los temas de ayuda de los cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) y [set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="a1afc-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="a1afc-115">Para crear una configuración de borde a/V nueva en el ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="a1afc-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="a1afc-116">El siguiente comando crea una nueva colección de valores de configuración de borde A/V para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="a1afc-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="a1afc-117">Para crear una configuración de borde personalizada a/V en el ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="a1afc-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="a1afc-118">Dado que no se incluyeron parámetros adicionales, esta nueva configuración usará los valores predeterminados para el servicio de borde A/V.</span><span class="sxs-lookup"><span data-stu-id="a1afc-118">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service.</span></span> <span data-ttu-id="a1afc-119">También puede agregar parámetros adicionales y valores de parámetro para crear una colección personalizada.</span><span class="sxs-lookup"><span data-stu-id="a1afc-119">Alternatively, you can add additional parameters and parameter values to create a custom collection.</span></span> <span data-ttu-id="a1afc-120">Por ejemplo, este comando establece la propiedad MaxTokenLifetime en 4 horas (04 horas: 00 minutos: 00 segundos):</span><span class="sxs-lookup"><span data-stu-id="a1afc-120">For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="a1afc-121">Para crear una configuración de borde personalizada a/V en el ámbito de servicio</span><span class="sxs-lookup"><span data-stu-id="a1afc-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="a1afc-122">Este comando crea una colección similar que se aplica al servidor perimetral A/V atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="a1afc-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="a1afc-123">Para modificar la configuración de borde a/V existente</span><span class="sxs-lookup"><span data-stu-id="a1afc-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="a1afc-124">En este ejemplo, el cmdlet Set-CsAVEdgeConfiguration se usa para cambiar la vigencia máxima del token para el sitio de Redmond a 12 horas:</span><span class="sxs-lookup"><span data-stu-id="a1afc-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1afc-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1afc-125">See Also</span></span>


[<span data-ttu-id="a1afc-126">Devolver información de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1afc-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="a1afc-127">Eliminar una colección existente de valores de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1afc-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="a1afc-128">Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1afc-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="a1afc-129">[Nuevo: CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a1afc-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="a1afc-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a1afc-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: obtener información de configuración del servidor perimetral A/V'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920c45abf98678c3e866650e094b9e4a52a418a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="dd4b0-102">Devolver información de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd4b0-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd4b0-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dd4b0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dd4b0-p101">El servicio perimetral A/V constituye un modo de que los usuarios internos (aquellos que han iniciado sesión en la red de la organización) puedan compartir audio y vídeo con los usuarios externos (aquellos que no han iniciado sesión en la red de la organización). El servicio perimetral A/V se administra principalmente a mediante la configuración de servidor perimetral A/V, que se puede definir en el ámbito de sitio o en el ámbito de servicio (esto es, se puede configurar para un solo servidor perimetral A/V).</span><span class="sxs-lookup"><span data-stu-id="dd4b0-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="dd4b0-106">Para devolver información acerca de las opciones de configuración del servidor perimetral A/V en uso en su organización, debe usar Windows PowerShell y el cmdlet Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="dd4b0-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="dd4b0-107">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="dd4b0-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="dd4b0-108">La información devuelta desde el cmdlet Get-CsAVEdgeConfiguration tendrá un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="dd4b0-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="dd4b0-109">Para devolver información de todas las opciones de configuración del servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="dd4b0-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="dd4b0-110">El siguiente comando devuelve información sobre todas las opciones de configuración del servidor perimetral A/V que actualmente usa la organización:</span><span class="sxs-lookup"><span data-stu-id="dd4b0-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="dd4b0-111">Para devolver información sobre las opciones de configuración del servidor perimetral A/V en el ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="dd4b0-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="dd4b0-p103">Para devolver información sobre una colección específica de opciones de configuración del servidor perimetral A/V, especifique la identidad de esa colección al ejecutar el cmdlet Get-CsAVEdgeConfiguration. Por ejemplo, este comando devuelve información solo para las opciones aplicadas al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="dd4b0-p103">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet. For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="dd4b0-114">Para devolver información sobre las opciones de configuración del servidor perimetral A/V con ámbito de servicio</span><span class="sxs-lookup"><span data-stu-id="dd4b0-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="dd4b0-115">Este comando devuelve información solo para las opciones aplicadas a un servidor perimetral A/V específico:</span><span class="sxs-lookup"><span data-stu-id="dd4b0-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd4b0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd4b0-116">See Also</span></span>


[<span data-ttu-id="dd4b0-117">Crear o modificar una colección de opciones de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd4b0-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="dd4b0-118">Eliminar una colección existente de opciones de configuración del servidor perimetral A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd4b0-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="dd4b0-119">Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd4b0-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


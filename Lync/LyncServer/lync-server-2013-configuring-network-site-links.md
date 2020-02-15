---
title: 'Lync Server 2013: configuración de vínculos de sitios de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: face7287ecf65a75e335b63f0a657c4534891277
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="4f357-102">Configuración de vínculos a sitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f357-102">Configuring network site links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f357-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4f357-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4f357-104">En una configuración de control de admisión de llamadas (CAC), puede crear directivas entre sitios de red que definen las limitaciones de ancho de banda entre los sitios que están directamente vinculados.</span><span class="sxs-lookup"><span data-stu-id="4f357-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="4f357-105">Cuando los sitios de red comparten un vínculo directo, es posible definir limitaciones de ancho de banda para las conexiones de audio y vídeo entre ambos sitos.</span><span class="sxs-lookup"><span data-stu-id="4f357-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="4f357-106">No puede usar el panel de control de Lync Server para configurar directivas de sitio de red, esto se puede hacer solo mediante el uso de cmdlets desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f357-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="4f357-107">Puede crear, modificar y quitar un vínculo de sitio de red (también conocido como una directiva entre sitios de red) desde el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f357-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="4f357-108">Para crear un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="4f357-108">To create a network site link</span></span>

1.  <span data-ttu-id="4f357-109">Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4f357-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4f357-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f357-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4f357-111">Desde el símbolo del sistema, escriba el comando siguiente, usando los valores aplicables a su configuración:</span><span class="sxs-lookup"><span data-stu-id="4f357-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="4f357-112">En este ejemplo se crea un nuevo vínculo de sitio\_de red denominado Reno Portland que establece las limitaciones de ancho de banda entre los sitios de red Reno y Portland.</span><span class="sxs-lookup"><span data-stu-id="4f357-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="4f357-113">El perfil de la directiva de sitios de red y de ancho de banda debe existir antes de ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="4f357-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="4f357-114">Para obtener descripciones de parámetros detalladas, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f357-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="4f357-115">Para recuperar una lista de perfiles de directivas de ancho de banda que puedan aplicarse al vínculo de sitio de red, ejecute el cmdlet **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="4f357-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="4f357-116">Para obtener más información, consulte [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f357-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="4f357-117">Para modificar un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="4f357-117">To modify a network site link</span></span>

1.  <span data-ttu-id="4f357-118">Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4f357-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4f357-119">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f357-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4f357-120">Use el cmdlet **Set-CsNetworkInterSitePolicy** para modificar las propiedades de un vínculo de sitio de red.</span><span class="sxs-lookup"><span data-stu-id="4f357-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="4f357-121">Puede modificar uno de los sitios conectados (o ambos), y también puede modificar el perfil de directiva de banda de ancha asociado al vínculo.</span><span class="sxs-lookup"><span data-stu-id="4f357-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="4f357-122">Este es un ejemplo de cómo modificar el perfil de directiva de ancho de banda de un\_vínculo a sitios denominado Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="4f357-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="4f357-123">Para obtener descripciones de parámetros detalladas, consulte [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f357-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="4f357-124">Para eliminar un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="4f357-124">To delete a network site link</span></span>

1.  <span data-ttu-id="4f357-125">Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4f357-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4f357-126">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f357-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4f357-127">Use el cmdlet **Remove-CsNetworkInterSitePolicy** para quitar un vínculo de sitio de red.</span><span class="sxs-lookup"><span data-stu-id="4f357-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="4f357-128">En el siguiente ejemplo se elimina el\_vínculo de sitio de red Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="4f357-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="4f357-129">Para obtener descripciones de parámetros detalladas, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f357-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f357-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f357-130">See Also</span></span>


[<span data-ttu-id="4f357-131">Cmdlets de control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f357-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="4f357-132">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4f357-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="4f357-133">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4f357-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="4f357-134">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4f357-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="4f357-135">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4f357-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="4f357-136">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="4f357-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


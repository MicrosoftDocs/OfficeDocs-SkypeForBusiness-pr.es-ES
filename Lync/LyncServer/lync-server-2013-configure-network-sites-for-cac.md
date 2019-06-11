---
title: 'Lync Server 2013: configuración de sitios de red para CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 528ed67243fb0ab0451abf504a458afc420d94ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="e66ed-102">Configurar sitios de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e66ed-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e66ed-103">_**Última modificación del tema:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="e66ed-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="e66ed-104">Si ya ha creado sitios de red para la omisión de E9-1-1 o multimedia, puede modificar los sitios de red existentes para aplicar un perfil de directiva de ancho de banda mediante el cmdlet <STRONG>set-CsNetworkSite</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e66ed-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="e66ed-105">Para obtener un ejemplo de cómo modificar un sitio de red, vea <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e66ed-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e66ed-106">Los *sitios de red* son las oficinas o ubicaciones dentro de cada región de la red de control de admisión de llamadas (CAC), E9-1-1 y las implementaciones por omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="e66ed-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="e66ed-107">Use los procedimientos siguientes para crear sitios de red que se alineen con los sitios de red en la topología de red de ejemplo de CAC.</span><span class="sxs-lookup"><span data-stu-id="e66ed-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="e66ed-108">Estos procedimientos muestran cómo crear y configurar sitios de red que están limitados por el ancho de banda WAN y, por lo tanto, requieren directivas de ancho de banda que limitan el flujo de tráfico de audio o vídeo en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="e66ed-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="e66ed-109">En el ejemplo CAC Deployment, la región de Norteamérica tiene seis sitios.</span><span class="sxs-lookup"><span data-stu-id="e66ed-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="e66ed-110">Tres de estos sitios están limitados por el ancho de banda WAN: Reno, Portland y Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="e66ed-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="e66ed-111">Los otros tres sitios, que *no* están limitados por el ancho de banda de WAN: Nueva York, Chicago y Detroit.</span><span class="sxs-lookup"><span data-stu-id="e66ed-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="e66ed-112">Para obtener un ejemplo de cómo crear o modificar esos otros sitios de red, consulte [crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="e66ed-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="e66ed-113">Para ver la topología de red de ejemplo, vea [ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="e66ed-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="e66ed-114">En el siguiente procedimiento, se usa el shell de administración de Lync Server para crear un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="e66ed-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="e66ed-115">Para obtener detalles sobre el uso del panel de control de Lync Server para crear un sitio de red, consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e66ed-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="e66ed-116">Para crear sitios de red para el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="e66ed-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="e66ed-117">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e66ed-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e66ed-118">Ejecute el cmdlet **New-CsNetworkSite** para crear sitios de red y aplicar un perfil de directiva de ancho de banda adecuado a cada sitio.</span><span class="sxs-lookup"><span data-stu-id="e66ed-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="e66ed-119">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e66ed-119">For example, run:</span></span>
    
       ```
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="e66ed-120">Para finalizar la creación de sitios de red para la topología de ejemplo completa, repita el paso 2 para los sitios de red con limitaciones de ancho de banda de las regiones EMEA y APAC.</span><span class="sxs-lookup"><span data-stu-id="e66ed-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


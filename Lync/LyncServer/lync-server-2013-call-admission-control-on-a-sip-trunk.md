---
title: 'Lync Server 2013: control de admisión de llamadas en un tronco SIP'
description: 'Lync Server 2013: control de admisión de llamadas en un tronco SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3667ef4608b221a1607b6bbe0d89d390cb1dd402
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563166"
---
# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="6375b-103">Control de admisión de llamadas en un tronco SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6375b-103">Call admission control on a SIP trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6375b-104">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="6375b-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="6375b-p101">Para implementar el control de admisión de llamadas (CAC) en un tronco SIP, debe crear un sitio de red para representar al proveedor de servicios de telefonía de Internet (ITSP). Para aplicar valores de directivas de ancho de banda al tronco SIP, debe crear una directiva entre el sitio de red de su empresa y el sitio de red que cree para representar al ITSP.</span><span class="sxs-lookup"><span data-stu-id="6375b-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="6375b-107">La siguiente ilustración muestra un ejemplo de implementación de CAC en un tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="6375b-107">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="6375b-108">**Configuración de CAC en un tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="6375b-108">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="6375b-109">![Diagrama de enlace troncal SIP de control de admisión de llamadas](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Diagrama de enlace troncal SIP de control de admisión de llamadas")</span><span class="sxs-lookup"><span data-stu-id="6375b-109">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="6375b-110">Para configurar el CAC en un tronco SIP, deberá realizar las siguientes tareas durante la implementación de CAC:</span><span class="sxs-lookup"><span data-stu-id="6375b-110">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="6375b-111">Cree un sitio de red para representar al ITSP.</span><span class="sxs-lookup"><span data-stu-id="6375b-111">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="6375b-112">Asocie el sitio de red a una región de red adecuada y asigne un ancho de banda de cero para el audio y el vídeo de este sitio de red.</span><span class="sxs-lookup"><span data-stu-id="6375b-112">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="6375b-113">Para obtener más información, consulte [Configure Network Sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="6375b-113">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6375b-114">Para el ITSP, no funciona esta configuración de sitio de red.</span><span class="sxs-lookup"><span data-stu-id="6375b-114">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="6375b-115">Los valores de la directiva de ancho de banda se aplican, en realidad, en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="6375b-115">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="6375b-116">Cree un vínculo entre sitios para el tronco SIP, usando los valores de los parámetros correspondientes al sitio que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="6375b-116">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="6375b-117">Por ejemplo, use el nombre del sitio de red de su empresa como el valor del parámetro NetworkSiteID1 y el sitio de red ITSP como el valor del parámetro NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="6375b-117">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="6375b-118">Para obtener más información, consulte [Create Network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="6375b-118">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="6375b-119">Consulte también la documentación del shell de administración de Lync Server para el cmdlet New-CsNetworkInterSitePolicy.</span><span class="sxs-lookup"><span data-stu-id="6375b-119">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="6375b-120">Consulte a su ITSP la dirección IP del punto de terminación de medios del controlador de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="6375b-120">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="6375b-121">Agregue esa dirección IP con una máscara de subred de 32 al sitio de red que representa al ITSP.</span><span class="sxs-lookup"><span data-stu-id="6375b-121">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="6375b-122">Para obtener más información, consulte [asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="6375b-122">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


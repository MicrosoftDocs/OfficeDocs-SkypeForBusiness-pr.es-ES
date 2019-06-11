---
title: 'Lync Server 2013: configurar el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86961c9f282e1a486bf7cf94eda494d37c415cf6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="79ed2-102">Configurar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79ed2-102">Configure call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79ed2-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="79ed2-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="79ed2-104">El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre.</span><span class="sxs-lookup"><span data-stu-id="79ed2-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="79ed2-105">CAC controla el tráfico en tiempo real solo para audio y vídeo, y no afecta al tráfico de datos.</span><span class="sxs-lookup"><span data-stu-id="79ed2-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="79ed2-106">CAC puede enrutar la llamada a través de una ruta de Internet cuando la ruta de acceso WAN predeterminada no tiene el ancho de banda requerido.</span><span class="sxs-lookup"><span data-stu-id="79ed2-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="79ed2-107">Para obtener más información, consulte [planificación de control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="79ed2-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="79ed2-108">Esta sección proporciona un conjunto de procedimientos de ejemplo que muestran cómo implementar y administrar CAC en su red.</span><span class="sxs-lookup"><span data-stu-id="79ed2-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="79ed2-109">Antes de implementar CAC, debe reunir toda la información necesaria para la topología de red de su empresa, como se describe en <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">ejemplo: recopilación de los requisitos para el control de admisión de llamadas en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="79ed2-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="79ed2-110">Además, asegúrese de que los componentes de CAC se han instalado y activado, tal y como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="79ed2-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="79ed2-111">Todos los ejemplos de implementación y administración de CAC en esta sección se realizan mediante el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79ed2-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="79ed2-112">Como alternativa, también puede usar la sección <STRONG>configuración de red</STRONG> del panel de control de Lync Server para administrar CAC.</span><span class="sxs-lookup"><span data-stu-id="79ed2-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="79ed2-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="79ed2-113">In This Section</span></span>

  - [<span data-ttu-id="79ed2-114">Configurar regiones de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79ed2-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="79ed2-115">Crear perfiles de directiva de ancho de banda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79ed2-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="79ed2-116">Configurar sitios de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79ed2-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="79ed2-117">Asociar subredes con sitios de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79ed2-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="79ed2-118">Crear vínculos de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79ed2-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="79ed2-119">Crear rutas interregional de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79ed2-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="79ed2-120">Crear directivas de intersitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79ed2-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="79ed2-121">Habilitar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79ed2-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="79ed2-122">Lista de comprobación de la implementación de control de admisión para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79ed2-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


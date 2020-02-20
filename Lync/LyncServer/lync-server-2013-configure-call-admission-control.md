---
title: 'Lync Server 2013: configurar el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad0d297981bec3fe133e88a090a3c60a97f1ec9d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="5258e-102">Configurar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5258e-102">Configure call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5258e-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5258e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5258e-104">El control de admisión de llamadas es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre.</span><span class="sxs-lookup"><span data-stu-id="5258e-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="5258e-105">Esta solución controla el tráfico en tiempo real únicamente para el audio y el vídeo, y no afecta al tráfico de datos.</span><span class="sxs-lookup"><span data-stu-id="5258e-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="5258e-106">Puede enrutar la llamada a través de una ruta de acceso de Internet, si la ruta de acceso WAN predeterminada no dispone del ancho de banda requerido.</span><span class="sxs-lookup"><span data-stu-id="5258e-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="5258e-107">Para obtener más información, consulte [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="5258e-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="5258e-108">En esta sección se proporciona un conjunto de procedimientos de ejemplo donde se describe cómo implementar y administrar el control de admisión de llamadas en una red.</span><span class="sxs-lookup"><span data-stu-id="5258e-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5258e-109">Antes de implementar el CAC, debe recopilar toda la información necesaria para la topología de red de la empresa, como se describe en <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">ejemplo: reunión de los requisitos para el control de admisión de llamadas en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="5258e-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="5258e-110">Asegúrese también de que los componentes de CAC se hayan instalado y activado, como se describe en <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="5258e-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5258e-111">Todos los ejemplos de implementación y administración de CAC en esta sección se realizan mediante el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5258e-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="5258e-112">Como alternativa, también puede usar la sección <STRONG>configuración de red</STRONG> del panel de control de Lync Server para administrar el CAC.</span><span class="sxs-lookup"><span data-stu-id="5258e-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5258e-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5258e-113">In This Section</span></span>

  - [<span data-ttu-id="5258e-114">Configurar regiones de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5258e-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="5258e-115">Crear perfiles de directiva de ancho de banda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5258e-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="5258e-116">Configurar sitios de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5258e-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="5258e-117">Asociar subredes a sitios de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5258e-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="5258e-118">Crear vínculos de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5258e-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="5258e-119">Crear rutas entre regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5258e-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="5258e-120">Crear directivas entre sitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5258e-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="5258e-121">Habilitar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5258e-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="5258e-122">Lista de comprobación para la implementación del control de admisión de llamadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5258e-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


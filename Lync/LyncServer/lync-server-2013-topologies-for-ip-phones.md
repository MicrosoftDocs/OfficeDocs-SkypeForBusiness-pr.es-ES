---
title: 'Lync Server 2013: topologías para teléfonos IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3247783acb0f65fb069f418c4a66a4c53b1a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="eb771-102">Topologías para teléfonos IP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb771-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb771-103">_**Última modificación del tema:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="eb771-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="eb771-104">Esta sección proporciona una descripción general del proceso de conectividad y explica las diferencias entre el modo en que un teléfono IP se conecta en una red interna y externa.</span><span class="sxs-lookup"><span data-stu-id="eb771-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb771-105">Lync Server proporciona compatibilidad con los siguientes teléfonos IP: el Aastra 6721ip de área común, Aastra teléfono de escritorio 6725ip, teléfono IP HP 4110 (teléfono de área común), teléfono IP HP 4120 (teléfono de escritorio), teléfono IP de escritorio Polycom, teléfono IP de escritorio Polycom CX700, IP Polycom CX500 teléfono de área común y teléfono de conferencia IP Polycom CX3000.</span><span class="sxs-lookup"><span data-stu-id="eb771-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="eb771-106">De esos teléfonos, todos excepto el Polycom CX700 pueden ejecutar Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="eb771-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="eb771-107">El siguiente diagrama describe todos los componentes implicados en la conectividad de dispositivos dentro del entorno corporativo.</span><span class="sxs-lookup"><span data-stu-id="eb771-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="eb771-108">**Topología interna**</span><span class="sxs-lookup"><span data-stu-id="eb771-108">**Internal Topology**</span></span>

<span data-ttu-id="eb771-109">![3d88893e-df57-46e3-855A-a1d24589030a] (images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855A-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="eb771-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb771-110">La figura anterior es una representación lógica, no una visión general física.</span><span class="sxs-lookup"><span data-stu-id="eb771-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="eb771-111">Por ejemplo, los servicios de dominio de Active Directory (AD DS) rara vez se encuentran en el mismo equipo que cualquier componente de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eb771-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="eb771-112">El almacén de usuario puede encontrarse en el servidor back-end o en los servidores de archivado y supervisión.</span><span class="sxs-lookup"><span data-stu-id="eb771-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="eb771-113">El shell de administración de Lync Server, el servidor Web y los servicios de actualización forman parte de la función de servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="eb771-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="eb771-114">En el siguiente diagrama se ofrece información general sobre los componentes que se utilizan cuando el dispositivo se encuentra fuera de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="eb771-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="eb771-115">**Topología externa**</span><span class="sxs-lookup"><span data-stu-id="eb771-115">**External Topology**</span></span>

<span data-ttu-id="eb771-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3] (images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="eb771-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb771-117">El servicio Web de actualización de dispositivos proporciona un sitio web externo e interno, pero solo se muestra el externo.</span><span class="sxs-lookup"><span data-stu-id="eb771-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="eb771-118">La ubicación del registrador y la dirección URL del servicio Web de actualización de dispositivos para la organización se deben publicar en DNS si se va a habilitar el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="eb771-118">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled.</span></span> <span data-ttu-id="eb771-119">Además, el servidor perimetral debe implementarse y configurarse correctamente para permitir las comunicaciones externas desde el dispositivo al entorno corporativo y viceversa.</span><span class="sxs-lookup"><span data-stu-id="eb771-119">Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back.</span></span> <span data-ttu-id="eb771-120">Esto se omite del diagrama anterior porque la implementación perimetral no es específica de la Conectividad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eb771-120">This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


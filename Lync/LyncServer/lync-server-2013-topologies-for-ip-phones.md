---
title: 'Lync Server 2013: topologías para teléfonos IP'
description: 'Lync Server 2013: topologías para teléfonos IP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a151a83a69e1f7e14dcbed8d8ab1038157fa839
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549136"
---
# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="9f067-103">Topologías para teléfonos IP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f067-103">Topologies for IP phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f067-104">_**Última modificación del tema:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="9f067-104">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="9f067-105">En este tema, se describe el proceso de conectividad y se explican las diferencias de la conexión de un teléfono IP en una red interna y en una red externa.</span><span class="sxs-lookup"><span data-stu-id="9f067-105">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f067-106">Lync Server proporciona compatibilidad con los siguientes teléfonos IP: el Aastra 6721ip Common Area Phone, Aastra 6725ip teléfono de escritorio, HP 4110 IP Phone (teléfono de área común), HP 4120 IP Phone (teléfono de escritorio), teléfono de escritorio Polycom CX600 IP, teléfono de escritorio Polycom CX700, teléfono de área común Polycom CX500 y teléfono de conferencia Polycom CX3000 IP.</span><span class="sxs-lookup"><span data-stu-id="9f067-106">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="9f067-107">De esos teléfonos, todos excepto Polycom CX700 pueden ejecutar Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="9f067-107">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="9f067-108">En el diagrama siguiente, se describen todos los componentes utilizados en la conectividad del dispositivo dentro del entorno corporativo.</span><span class="sxs-lookup"><span data-stu-id="9f067-108">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="9f067-109">**Topología interna**</span><span class="sxs-lookup"><span data-stu-id="9f067-109">**Internal Topology**</span></span>

<span data-ttu-id="9f067-110">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="9f067-110">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f067-111">La figura anterior constituye una representación lógica, no una descripción física.</span><span class="sxs-lookup"><span data-stu-id="9f067-111">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="9f067-112">Por ejemplo, los servicios de dominio de Active Directory (AD DS) rara vez se ubican en el mismo equipo que los componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f067-112">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="9f067-113">El almacén de usuarios puede estar en el servidor back-end, o en los servidores de archivado o de supervisión.</span><span class="sxs-lookup"><span data-stu-id="9f067-113">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="9f067-114">El shell de administración de Lync Server, el servidor Web y los servicios de actualización forman parte del rol de servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="9f067-114">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="9f067-115">En el diagrama siguiente, se muestran los componentes utilizados cuando el dispositivo se encuentra fuera de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="9f067-115">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="9f067-116">**Topología externa**</span><span class="sxs-lookup"><span data-stu-id="9f067-116">**External Topology**</span></span>

<span data-ttu-id="9f067-117">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="9f067-117">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f067-118">El servicio web de actualización de dispositivos proporciona un sitio web externo e interno, pero aquí solo se muestra uno externo.</span><span class="sxs-lookup"><span data-stu-id="9f067-118">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="9f067-p103">La ubicación del registrador y la dirección URL del servicio web de actualización de dispositivos para la organización deben publicarse en DNS si se habilitará el acceso externo. Además, el servidor perimetral se debe implementar y configurar correctamente para permitir las comunicaciones externas del dispositivo al entorno corporativo, y viceversa. Esto se omite en el diagrama anterior porque la implementación perimetral no es específica de la conectividad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9f067-p103">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled. Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back. This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


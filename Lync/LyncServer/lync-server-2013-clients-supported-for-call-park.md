---
title: 'Lync Server 2013: Clientes admitidos para el estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b9ac77a82cf8d833c3f06a8fe3c738e2501937
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="990aa-102">Clientes admitidos para el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="990aa-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="990aa-103">_**Última modificación del tema:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="990aa-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="990aa-104">En esta sección se identifican los clientes que se pueden usar para detener llamadas y los clientes que se pueden usar para recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="990aa-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="990aa-105">Clientes compatibles con el estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="990aa-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="990aa-106">Se pueden estacionar las llamadas de cualquier IP, central de conmutación (PBX), red telefónica conmutada (RTC) o teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="990aa-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="990aa-p101">Únicamente se pueden estacionar las llamadas de audio. No se pueden estacionar los mensajes instantáneos ni las conferencias.</span><span class="sxs-lookup"><span data-stu-id="990aa-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="990aa-109">Los siguientes clientes pueden usar el activador de llamadas para detener llamadas:</span><span class="sxs-lookup"><span data-stu-id="990aa-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="990aa-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="990aa-110">Lync 2013</span></span>

  - <span data-ttu-id="990aa-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="990aa-111">Lync 2010</span></span>

  - <span data-ttu-id="990aa-112">Operador de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="990aa-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="990aa-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="990aa-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="990aa-114">Los teléfonos móviles no pueden usar el parque de llamadas para detener llamadas.</span><span class="sxs-lookup"><span data-stu-id="990aa-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="990aa-115">Clientes compatibles con la recuperación de llamadas</span><span class="sxs-lookup"><span data-stu-id="990aa-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="990aa-p102">Los intervalos de órbitas están configurados como bloques de extensiones virtuales (extensiones sin ningún usuario ni teléfono asignado). Cuando configuras órbitas como extensiones virtuales, teléfonos móviles y teléfono RTC, no puedes recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="990aa-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="990aa-118">Los usuarios federados no pueden recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="990aa-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="990aa-119">Los siguientes clientes pueden recuperar llamadas estacionadas en el parque de llamadas:</span><span class="sxs-lookup"><span data-stu-id="990aa-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="990aa-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="990aa-120">Lync 2013</span></span>

  - <span data-ttu-id="990aa-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="990aa-121">Lync 2010</span></span>

  - <span data-ttu-id="990aa-122">Operador de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="990aa-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="990aa-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="990aa-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="990aa-124">Teléfonos IP de área común</span><span class="sxs-lookup"><span data-stu-id="990aa-124">IP common area phones</span></span>

  - <span data-ttu-id="990aa-125">Teléfonos no basados en IP que están conectados a la infraestructura de Lync Server 2013, incluidos teléfonos de área común y teléfonos de central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="990aa-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


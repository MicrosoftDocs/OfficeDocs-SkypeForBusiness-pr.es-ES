---
title: 'Lync Server 2013: clientes compatibles con el estacionamiento de llamadas'
description: 'Lync Server 2013: clientes compatibles con el estacionamiento de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a923f0e62c246a12b811628d578ab571f4f13e36
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543496"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="8dd41-103">Clientes compatibles con el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dd41-103">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dd41-104">_**Última modificación del tema:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="8dd41-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="8dd41-105">En esta sección se indican los clientes que se pueden usar para estacionar llamadas y los clientes que se pueden usar para recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8dd41-105">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="8dd41-106">Clientes admitidos para el estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="8dd41-106">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="8dd41-107">Se pueden estacionar las llamadas de cualquier IP, PBX, RTC o teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="8dd41-107">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8dd41-p101">Únicamente se pueden estacionar las llamadas de audio. No se pueden estacionar los mensajes instantáneos ni las conferencias.</span><span class="sxs-lookup"><span data-stu-id="8dd41-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="8dd41-110">Los siguientes clientes pueden usar el estacionamiento de llamadas para estacionar llamadas:</span><span class="sxs-lookup"><span data-stu-id="8dd41-110">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="8dd41-111">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8dd41-111">Lync 2013</span></span>

  - <span data-ttu-id="8dd41-112">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8dd41-112">Lync 2010</span></span>

  - <span data-ttu-id="8dd41-113">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="8dd41-113">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="8dd41-114">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8dd41-114">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8dd41-115">Los teléfonos móviles no pueden usar el estacionamiento de llamadas para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="8dd41-115">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="8dd41-116">Clientes admitidos para la recuperación de llamadas</span><span class="sxs-lookup"><span data-stu-id="8dd41-116">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="8dd41-p102">Los intervalos de órbitas están configurados como bloques de extensiones virtuales (extensiones sin ningún usuario ni teléfono asignado). Cuando configura órbitas como extensiones virtuales, teléfonos móviles y teléfono RTC, no puede recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8dd41-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="8dd41-119">Los usuarios asociados no pueden recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8dd41-119">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="8dd41-120">Los siguientes clientes pueden recuperar llamadas estacionadas en el estacionamiento de llamadas:</span><span class="sxs-lookup"><span data-stu-id="8dd41-120">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="8dd41-121">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8dd41-121">Lync 2013</span></span>

  - <span data-ttu-id="8dd41-122">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8dd41-122">Lync 2010</span></span>

  - <span data-ttu-id="8dd41-123">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="8dd41-123">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="8dd41-124">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8dd41-124">Lync Phone Edition</span></span>

  - <span data-ttu-id="8dd41-125">Teléfonos IP de área común</span><span class="sxs-lookup"><span data-stu-id="8dd41-125">IP common area phones</span></span>

  - <span data-ttu-id="8dd41-126">Teléfonos no IP que están conectados a la infraestructura de Lync Server 2013, incluidos los teléfonos de área común y los teléfonos de central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="8dd41-126">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


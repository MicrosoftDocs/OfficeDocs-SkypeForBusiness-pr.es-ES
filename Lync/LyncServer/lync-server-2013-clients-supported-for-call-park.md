---
title: 'Lync Server 2013: clientes compatibles con el estacionamiento de llamadas'
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
ms.openlocfilehash: 5c59dde334b592b2dc78920a8c61e6322867475f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="8ea0b-102">Clientes compatibles con el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ea0b-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ea0b-103">_**Última modificación del tema:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="8ea0b-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="8ea0b-104">En esta sección se indican los clientes que se pueden usar para estacionar llamadas y los clientes que se pueden usar para recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8ea0b-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="8ea0b-105">Clientes admitidos para el estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="8ea0b-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="8ea0b-106">Se pueden estacionar las llamadas de cualquier IP, PBX, RTC o teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="8ea0b-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ea0b-p101">Únicamente se pueden estacionar las llamadas de audio. No se pueden estacionar los mensajes instantáneos ni las conferencias.</span><span class="sxs-lookup"><span data-stu-id="8ea0b-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="8ea0b-109">Los siguientes clientes pueden usar el estacionamiento de llamadas para estacionar llamadas:</span><span class="sxs-lookup"><span data-stu-id="8ea0b-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="8ea0b-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8ea0b-110">Lync 2013</span></span>

  - <span data-ttu-id="8ea0b-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8ea0b-111">Lync 2010</span></span>

  - <span data-ttu-id="8ea0b-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="8ea0b-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="8ea0b-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8ea0b-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ea0b-114">Los teléfonos móviles no pueden usar el estacionamiento de llamadas para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="8ea0b-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="8ea0b-115">Clientes admitidos para la recuperación de llamadas</span><span class="sxs-lookup"><span data-stu-id="8ea0b-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="8ea0b-p102">Los intervalos de órbitas están configurados como bloques de extensiones virtuales (extensiones sin ningún usuario ni teléfono asignado). Cuando configura órbitas como extensiones virtuales, teléfonos móviles y teléfono RTC, no puede recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8ea0b-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="8ea0b-118">Los usuarios asociados no pueden recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="8ea0b-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="8ea0b-119">Los siguientes clientes pueden recuperar llamadas estacionadas en el estacionamiento de llamadas:</span><span class="sxs-lookup"><span data-stu-id="8ea0b-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="8ea0b-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8ea0b-120">Lync 2013</span></span>

  - <span data-ttu-id="8ea0b-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8ea0b-121">Lync 2010</span></span>

  - <span data-ttu-id="8ea0b-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="8ea0b-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="8ea0b-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8ea0b-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="8ea0b-124">Teléfonos IP de área común</span><span class="sxs-lookup"><span data-stu-id="8ea0b-124">IP common area phones</span></span>

  - <span data-ttu-id="8ea0b-125">Teléfonos no IP que están conectados a la infraestructura de Lync Server 2013, incluidos los teléfonos de área común y los teléfonos de central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="8ea0b-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


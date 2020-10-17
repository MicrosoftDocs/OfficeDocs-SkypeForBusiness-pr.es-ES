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
ms.openlocfilehash: 74e9231c99754f0916d1ddf94ba36d1dce81fb1f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499267"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="74444-102">Clientes compatibles con el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74444-102">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74444-103">_**Última modificación del tema:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="74444-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="74444-104">En esta sección se indican los clientes que se pueden usar para estacionar llamadas y los clientes que se pueden usar para recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="74444-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="74444-105">Clientes admitidos para el estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="74444-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="74444-106">Se pueden estacionar las llamadas de cualquier IP, PBX, RTC o teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="74444-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74444-p101">Únicamente se pueden estacionar las llamadas de audio. No se pueden estacionar los mensajes instantáneos ni las conferencias.</span><span class="sxs-lookup"><span data-stu-id="74444-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="74444-109">Los siguientes clientes pueden usar el estacionamiento de llamadas para estacionar llamadas:</span><span class="sxs-lookup"><span data-stu-id="74444-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="74444-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="74444-110">Lync 2013</span></span>

  - <span data-ttu-id="74444-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="74444-111">Lync 2010</span></span>

  - <span data-ttu-id="74444-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="74444-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="74444-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="74444-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74444-114">Los teléfonos móviles no pueden usar el estacionamiento de llamadas para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="74444-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="74444-115">Clientes admitidos para la recuperación de llamadas</span><span class="sxs-lookup"><span data-stu-id="74444-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="74444-p102">Los intervalos de órbitas están configurados como bloques de extensiones virtuales (extensiones sin ningún usuario ni teléfono asignado). Cuando configura órbitas como extensiones virtuales, teléfonos móviles y teléfono RTC, no puede recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="74444-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="74444-118">Los usuarios asociados no pueden recuperar llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="74444-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="74444-119">Los siguientes clientes pueden recuperar llamadas estacionadas en el estacionamiento de llamadas:</span><span class="sxs-lookup"><span data-stu-id="74444-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="74444-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="74444-120">Lync 2013</span></span>

  - <span data-ttu-id="74444-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="74444-121">Lync 2010</span></span>

  - <span data-ttu-id="74444-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="74444-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="74444-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="74444-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="74444-124">Teléfonos IP de área común</span><span class="sxs-lookup"><span data-stu-id="74444-124">IP common area phones</span></span>

  - <span data-ttu-id="74444-125">Teléfonos no IP que están conectados a la infraestructura de Lync Server 2013, incluidos los teléfonos de área común y los teléfonos de central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="74444-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


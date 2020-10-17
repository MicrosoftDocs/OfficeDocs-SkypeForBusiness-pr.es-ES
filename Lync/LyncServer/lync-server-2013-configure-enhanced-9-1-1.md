---
title: 'Lync Server 2013: configurar 9-1-1 mejorado'
description: 'Lync Server 2013: configurar 9-1-1 mejorado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7a2a9ed10e7f29f53a4dfff6dff926ded18d38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553336"
---
# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="cc76e-103">Configurar 9-1-1 mejorado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc76e-103">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc76e-104">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="cc76e-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="cc76e-105">Enhanced 9-1-1 (E9-1-1) es una característica de notificación de emergencia que asocia el número de teléfono de la persona que llama con una dirección de la ciudad o la calle.</span><span class="sxs-lookup"><span data-stu-id="cc76e-105">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address.</span></span> <span data-ttu-id="cc76e-106">Con esta información, el punto de respuesta de seguridad pública (PSAP) puede enviar inmediatamente los servicios de emergencia al autor de la llamada en peligro.</span><span class="sxs-lookup"><span data-stu-id="cc76e-106">Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="cc76e-107">Para admitir E9-1-1, Lync Server 2013 debe poder asociar correctamente una ubicación con un cliente y asegurarse de que esta información se usa para enrutar la llamada de emergencia al PSAP más cercano.</span><span class="sxs-lookup"><span data-stu-id="cc76e-107">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="cc76e-108">Para obtener más información acerca de la planeación de una implementación de E9-1-1, consulte [Planning for Emergency Services (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="cc76e-108">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc76e-109">Lync Server 2013 solo admite E9-1-1 en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="cc76e-109">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="cc76e-110">Para implementar E9-1-1, tiene que configurar una conexión SIP a un proveedor de servicios E9-1-1 calificado o implementar una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en teléfono conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="cc76e-110">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="cc76e-111">Para obtener más información, consulte <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">enhanced 9-1-1 (E9-1-1) y Mediation Server in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cc76e-111">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="cc76e-112">Para obtener más información sobre cómo configurar conexiones troncales, consulte <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">configurar un tronco con la omisión de medios en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cc76e-112">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cc76e-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cc76e-113">In This Section</span></span>

  - [<span data-ttu-id="cc76e-114">Configurar una ruta de voz E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc76e-114">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="cc76e-115">Crear directivas de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc76e-115">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="cc76e-116">Configurar la información del sitio para E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc76e-116">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="cc76e-117">Configurar la base de datos de ubicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc76e-117">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="cc76e-118">Configurar las características avanzadas de E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc76e-118">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


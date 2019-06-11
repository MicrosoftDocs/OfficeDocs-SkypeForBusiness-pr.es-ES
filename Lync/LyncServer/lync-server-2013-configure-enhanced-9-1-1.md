---
title: 'Lync Server 2013: Configurar 9-1-1 mejorado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef94e3de028f66684972fa6a3c95d4e63c35b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="90bb3-102">Configurar 9-1-1 mejorado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90bb3-102">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90bb3-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="90bb3-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="90bb3-p101">9-1-1 mejorado (E9-1-1) es una característica de notificación de emergencia que asocia el número de teléfono de la persona que llama con una dirección postal o una calle. Con esta información, el PSAP (punto de respuesta de seguridad pública) puede enviar servicios de emergencia de forma inmediata a la persona que llama y tiene dificultades.</span><span class="sxs-lookup"><span data-stu-id="90bb3-p101">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address. Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="90bb3-106">Para admitir E9-1-1, Lync Server 2013 debe poder asociar correctamente una ubicación con un cliente y asegurarse de que esta información se use para enrutar la llamada de emergencia a la PSAP más cercana.</span><span class="sxs-lookup"><span data-stu-id="90bb3-106">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="90bb3-107">Para obtener más información sobre cómo planear una implementación de E9-1-1, consulte [planificación de servicios de emergencia (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="90bb3-107">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="90bb3-108">Lync Server 2013 solo admite E9-1-1 dentro de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="90bb3-108">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="90bb3-109">Para implementar E9-1-1, necesita configurar una conexión SIP a un proveedor de servicios E9-1-1 calificado o implementar una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios de telefonía pública conmutada (RTC) y E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="90bb3-109">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="90bb3-110">Para obtener más información, consulte <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">enhanced 9-1-1 (E9-1-1) and Media Server in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="90bb3-110">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="90bb3-111">Para obtener más información sobre cómo configurar conexiones troncales, vea <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">configurar un tronco con la omisión de medios en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="90bb3-111">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="90bb3-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="90bb3-112">In This Section</span></span>

  - [<span data-ttu-id="90bb3-113">Configurar una ruta de voz E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90bb3-113">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="90bb3-114">Crear directivas de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90bb3-114">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="90bb3-115">Configurar la información del sitio para E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90bb3-115">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="90bb3-116">Configure the location database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90bb3-116">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="90bb3-117">Configurar características avanzadas de E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90bb3-117">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Control de admisión de llamadas con un PBX o una puerta de enlace RTC de terceros
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1996b56a50dbe616c8dc6e9b9b1c779c564b185
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="10b98-102">Control de admisión de llamadas con un PBX o una puerta de enlace RTC de terceros en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10b98-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10b98-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="10b98-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="10b98-104">En este tema se describen ejemplos de cómo el servicio de control de admisión de llamadas (CAC) puede implementarse en el vínculo entre la interfaz de la puerta de enlace del servidor de mediación y una puerta de enlace de la red telefónica conmutada (RTC) o de la central de conmutación (PBX) de terceros.</span><span class="sxs-lookup"><span data-stu-id="10b98-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="10b98-105">Caso 1: servicio de control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="10b98-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="10b98-106">El CAC puede implementarse en el vínculo WAN de la interfaz de la puerta de enlace del servidor de mediación con una puerta de enlace RTC o PBX de terceros.</span><span class="sxs-lookup"><span data-stu-id="10b98-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="10b98-107">**Caso 1: servicio de control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC**</span><span class="sxs-lookup"><span data-stu-id="10b98-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="10b98-108">![Caso 1: CAC entre la puerta de enlace RTC del servidor] de mediación (images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Caso 1: CAC entre la puerta de enlace RTC del servidor") de mediación</span><span class="sxs-lookup"><span data-stu-id="10b98-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="10b98-109">En este ejemplo, se aplica CAC entre el servidor de mediación y una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="10b98-109">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="10b98-110">Si un usuario del cliente de Lync en el sitio de red 1 coloca una llamada RTC a través de la puerta de enlace RTC en el sitio de red 2, los medios fluyen por el vínculo WAN.</span><span class="sxs-lookup"><span data-stu-id="10b98-110">If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="10b98-111">Por tanto, se llevan a cabo dos comprobaciones de CAC para cada sesión de RTC:</span><span class="sxs-lookup"><span data-stu-id="10b98-111">Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="10b98-112">Entre la aplicación cliente de Lync y el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="10b98-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="10b98-113">Entre el servidor de mediación y la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="10b98-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="10b98-114">Esto funciona tanto para las llamadas RTC entrantes a un cliente en el sitio de red 1 como para las llamadas RTC salientes desde una aplicación cliente en el sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="10b98-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="10b98-115">Asegúrate de que la subred IP a la que pertenece la puerta de enlace RTC esté configurada y asociada con el sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="10b98-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="10b98-116">Asegúrese de que la subred IP a la que pertenecen ambas interfaces del servidor de mediación está configurada y asociada con el sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="10b98-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="10b98-117">Para obtener más información, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">asociar una subred con un sitio de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="10b98-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="10b98-118">Caso 2: CAC entre el servidor de mediación y un PBX de terceros con punto de terminación de los medios</span><span class="sxs-lookup"><span data-stu-id="10b98-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="10b98-119">Esta configuración es similar a la del caso 1.</span><span class="sxs-lookup"><span data-stu-id="10b98-119">This configuration is similar to Case 1.</span></span> <span data-ttu-id="10b98-120">En ambos casos, el servidor de mediación sabe qué dispositivo finaliza los medios en el extremo opuesto al vínculo WAN y la dirección IP de la puerta de enlace o PBX con punto de terminación de medios (MTP) está configurada en el servidor de mediación como el próximo salto.</span><span class="sxs-lookup"><span data-stu-id="10b98-120">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="10b98-121">**Caso 2: servicio de control de admisión de llamadas entre el servidor de mediación y una PBX de terceros con MTP**</span><span class="sxs-lookup"><span data-stu-id="10b98-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="10b98-122">![Caso 2: CAC entre el servidor de mediación PBX con MTP] (images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Caso 2: CAC entre el servidor de mediación PBX con MTP")</span><span class="sxs-lookup"><span data-stu-id="10b98-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="10b98-123">En este ejemplo, se aplica CAC entre el servidor de mediación y PBX/MTP.</span><span class="sxs-lookup"><span data-stu-id="10b98-123">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="10b98-124">Si un usuario del cliente de Lync en el sitio de red 1 coloca una llamada RTC a través de la PBX/MTP que se encuentra en el sitio de red 2, los medios se transmiten a través del vínculo WAN.</span><span class="sxs-lookup"><span data-stu-id="10b98-124">If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="10b98-125">Por tanto, se llevan a cabo dos comprobaciones de CAC para cada sesión de RTC:</span><span class="sxs-lookup"><span data-stu-id="10b98-125">Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="10b98-126">Entre la aplicación cliente de Lync y el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="10b98-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="10b98-127">Entre el servidor de mediación y la PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="10b98-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="10b98-128">Esto funciona tanto para las llamadas RTC entrantes a un cliente en el sitio de red 1 como para las llamadas RTC salientes desde un cliente en el sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="10b98-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="10b98-129">Asegúrate de que la subred IP a la que pertenece el MTP esté configurada y asociada con el sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="10b98-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="10b98-130">Asegúrese de que la subred IP a la que pertenecen ambas interfaces del servidor de mediación está configurada y asociada con el sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="10b98-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="10b98-131">Para obtener más información, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">asociar una subred con un sitio de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="10b98-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="10b98-132">Caso 3: CAC entre el servidor de mediación y un sistema PBX de terceros sin un punto de terminación de medios</span><span class="sxs-lookup"><span data-stu-id="10b98-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="10b98-133">El caso 3 es ligeramente diferente a los dos primeros casos.</span><span class="sxs-lookup"><span data-stu-id="10b98-133">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="10b98-134">Si no hay ningún MTP en la PBX de terceros, para una solicitud de sesión saliente al PBX de terceros, el servidor de mediación no sabrá dónde se cerrarán los medios en el límite de PBX.</span><span class="sxs-lookup"><span data-stu-id="10b98-134">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="10b98-135">En este caso, los medios fluyen directamente entre el servidor de mediación y el dispositivo de extremo de terceros.</span><span class="sxs-lookup"><span data-stu-id="10b98-135">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="10b98-136">**Caso 3: servicio de control de admisión de llamadas entre el servidor de mediación y una PBX de terceros sin MTP**</span><span class="sxs-lookup"><span data-stu-id="10b98-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="10b98-137">![Caso 3: CAC entre el servidor de mediación PBX no MTP] (images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Caso 3: CAC entre el servidor de mediación PBX no MTP")</span><span class="sxs-lookup"><span data-stu-id="10b98-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="10b98-138">En este ejemplo, si un usuario del cliente de Lync en el sitio de red 1 realiza una llamada a un usuario a través de la PBX, el servidor de mediación puede realizar comprobaciones CAC solo en el segmento proxy (entre la aplicación cliente de Lync y el servidor de mediación).</span><span class="sxs-lookup"><span data-stu-id="10b98-138">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server).</span></span> <span data-ttu-id="10b98-139">Dado que el servidor de mediación no tiene información sobre el dispositivo de extremo durante la solicitud de la sesión, las comprobaciones de CAC no se pueden realizar en el vínculo WAN (entre el servidor de mediación y el extremo de terceros) antes del establecimiento.</span><span class="sxs-lookup"><span data-stu-id="10b98-139">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="10b98-140">Sin embargo, una vez establecida la sesión, el servidor de mediación facilita la contabilidad del ancho de banda que se usa en el tronco.</span><span class="sxs-lookup"><span data-stu-id="10b98-140">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="10b98-141">Para las llamadas que se originan desde el extremo de terceros, la información sobre el dispositivo de punto final está disponible en el momento de la solicitud de sesión y la comprobación CAC se puede realizar en ambos lados del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="10b98-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="10b98-142">Asegúrate de que la subred IP a la que pertenecen los dispositivos de extremo esté configurada y asociada con el sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="10b98-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="10b98-143">Asegúrese de que la subred IP a la que pertenecen ambas interfaces del servidor de mediación está configurada y asociada con el sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="10b98-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="10b98-144">Para obtener más información, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">asociar una subred con un sitio de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="10b98-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


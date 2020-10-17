---
title: Control de admisión de llamadas con una puerta de enlace RTC o PBX de terceros
description: Control de admisión de llamadas con una puerta de enlace RTC o PBX de terceros.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aaab42992047ecedcc00ea1ecf5cf69023e51097
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545666"
---
# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="f3bf6-103">Control de admisión de llamadas en Lync Server 2013 con una puerta de enlace RTC o PBX de terceros</span><span class="sxs-lookup"><span data-stu-id="f3bf6-103">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3bf6-104">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f3bf6-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f3bf6-105">En este tema se explican ejemplos de cómo el servicio de control de admisión de llamadas puede implementarse en el vínculo entre la interfaz de puerta de enlace del servidor de mediación y una puerta de enlace la red telefónica conmutada (RTC) o central de conmutación (PBX) de terceros.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-105">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="f3bf6-106">Caso 1: Control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="f3bf6-106">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="f3bf6-107">El control de admisión de llamadas puede implementarse en el vínculo WAN de la interfaz de puerta de enlace del servidor de mediación con una puerta de enlace RTC o PBX de terceros.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-107">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="f3bf6-108">**Caso 1: Control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC**</span><span class="sxs-lookup"><span data-stu-id="f3bf6-108">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="f3bf6-109">![Caso 1: CAC entre la puerta de enlace RTC del servidor de mediación](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Caso 1: CAC entre la puerta de enlace RTC del servidor de mediación")</span><span class="sxs-lookup"><span data-stu-id="f3bf6-109">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="f3bf6-p101">En este ejemplo, el control de admisión de llamadas se aplica entre el servidor de mediación y una puerta de enlace RTC. Si un usuario del cliente de Lync realiza en el Sitio de red 1 una llamada RTC a través de la puerta de enlace RTC del Sitio de red 2, los medios se transmiten mediante el vínculo WAN. Por tanto, se llevan a cabo dos comprobaciones de control de admisión de llamadas para cada sesión RTC:</span><span class="sxs-lookup"><span data-stu-id="f3bf6-p101">In this example, CAC is applied between the Mediation Server and a PSTN gateway. If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link. Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="f3bf6-113">Entre la aplicación cliente Lync y el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="f3bf6-113">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="f3bf6-114">Entre el servidor de mediación y la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="f3bf6-114">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="f3bf6-115">Esto funciona tanto para las llamadas RTC entrantes a un cliente en el Sitio de red 1 como para las llamadas RTC salientes desde una aplicación cliente en el Sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-115">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f3bf6-116">Asegúrese de que la subred IP a la que pertenezca la puerta de enlace RTC esté configurada y asociada con el Sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-116">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="f3bf6-117">Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-117">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="f3bf6-118">Para obtener más información, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">asociar una subred a un sitio de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-118">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="f3bf6-119">Caso 2: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros con punto de terminación de medios (MTP, Media Termination Point)</span><span class="sxs-lookup"><span data-stu-id="f3bf6-119">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="f3bf6-p102">Esta configuración es similar a la del Caso 1. En ambos casos, el servidor de mediación sabe en qué dispositivo terminan los medios en el extremo opuesto del vínculo WAN, y la dirección IP de la puerta de enlace RTC o de la PBX que tiene el MTP está configurada en el servidor de mediación como siguiente salto.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-p102">This configuration is similar to Case 1. In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="f3bf6-122">**Caso 2: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros con MTP**</span><span class="sxs-lookup"><span data-stu-id="f3bf6-122">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="f3bf6-123">![Caso 2: CAC entre el servidor de mediación PBX con MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Caso 2: CAC entre el servidor de mediación PBX con MTP")</span><span class="sxs-lookup"><span data-stu-id="f3bf6-123">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="f3bf6-p103">En este ejemplo, el control de admisión de llamadas se aplica entre el servidor de mediación y el MTP o la PBX. Si un usuario del cliente de Lync realiza en el Sitio de red 1 una llamada RTC a través de la PBX o el MTP del Sitio de red 2, los medios se transmiten mediante el vínculo WAN. Por tanto, se llevan a cabo dos comprobaciones de control de admisión de llamadas para cada sesión RTC:</span><span class="sxs-lookup"><span data-stu-id="f3bf6-p103">In this example, CAC is applied between the Mediation Server and the PBX/MTP. If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link. Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="f3bf6-127">Entre la aplicación cliente Lync y el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="f3bf6-127">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="f3bf6-128">Entre el servidor de mediación y la PBX o el MTP</span><span class="sxs-lookup"><span data-stu-id="f3bf6-128">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="f3bf6-129">Esto funciona tanto para las llamadas RTC entrantes a un cliente en el Sitio de red 1 como para las llamadas RTC salientes desde un cliente en el Sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-129">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f3bf6-130">Asegúrese de que la subred IP a la que pertenezca el MTP esté configurada y asociada con el Sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-130">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="f3bf6-131">Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-131">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="f3bf6-132">Para obtener más información, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">asociar una subred a un sitio de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-132">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="f3bf6-133">Caso 3: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros sin MTP</span><span class="sxs-lookup"><span data-stu-id="f3bf6-133">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="f3bf6-p104">El Caso 3 es ligeramente diferente a los dos primeros casos. Si no hay ningún MTP en la PBX de terceros, en el caso de una solicitud de sesión saliente enviada a la PBX de terceros, el servidor de mediación no sabe dónde terminarán los medios en el límite de la PBX. En tal caso, los medios se transmiten directamente entre el servidor de mediación y el dispositivo del extremo de terceros.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-p104">Case 3 is slightly different from the first two cases. If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary. In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="f3bf6-137">**Caso 3: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros sin MTP**</span><span class="sxs-lookup"><span data-stu-id="f3bf6-137">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="f3bf6-138">![Caso 3: CAC entre el servidor de mediación (PBX) no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Caso 3: CAC entre el servidor de mediación (PBX) no MTP")</span><span class="sxs-lookup"><span data-stu-id="f3bf6-138">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="f3bf6-p105">En este ejemplo, si un usuario del cliente de Lync realiza una llamada a un usuario en el Sitio de red 1 a través de la PBX, el servidor de mediación solo podrá realizar comprobaciones de control de admisión de llamadas en la sección del proxy (entre la aplicación cliente Lync y el servidor de mediación). Dado que el servidor de mediación no tiene información sobre el dispositivo del extremo, durante el proceso de solicitud de la sesión, no pueden realizarse comprobaciones de control de admisión de llamadas en el vínculo WAN (entre el servidor de mediación y el extremo de terceros) antes del establecimiento de llamada. Sin embargo, una vez establecida la sesión, el servidor de mediación facilita la cantidad de ancho de banda usada en el tronco.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-p105">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server). Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment. After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="f3bf6-142">Para las llamadas realizadas desde el extremo de terceros, la información sobre el dispositivo del extremo está disponible en el momento de la solicitud de la sesión y la comprobación de control de admisión de llamadas puede realizarse en ambas partes del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-142">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f3bf6-143">Asegúrese de que la subred IP a la que pertenezca el dispositivo del extremo esté configurada y asociada con el Sitio de red 2.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-143">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="f3bf6-144">Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-144">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="f3bf6-145">Para obtener más información, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">asociar una subred a un sitio de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f3bf6-145">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


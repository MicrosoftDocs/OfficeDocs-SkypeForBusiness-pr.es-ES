---
title: 'Lync Server 2013: enrutamiento de Location-Based para conferencias'
description: 'Lync Server 2013: enrutamiento de Location-Based para conferencias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 979c835e03bbf87c9a9bf86b030cb9a8f4e138e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554856"
---
# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="7afea-103">Location-Based el enrutamiento para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7afea-103">Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7afea-104">_**Última modificación del tema:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="7afea-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="7afea-105">Location-Based enrutamiento permite restringir el enrutamiento de las llamadas entre los extremos de VoIP y los extremos de RTC en función de la ubicación de las partes en la llamada.</span><span class="sxs-lookup"><span data-stu-id="7afea-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="7afea-106">Con la actualización acumulativa 2 de Lync Server 2013, se pueden aplicar reglas de enrutamiento Location-Based en reuniones de Lync (es decir, conferencias) para evitar el desvío de llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="7afea-106">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="7afea-107">La aplicación supervisa una conferencia activa y aplica Location-Based restricciones de enrutamiento en función de la ubicación de los usuarios que participan.</span><span class="sxs-lookup"><span data-stu-id="7afea-107">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="7afea-108">La aplicación de conferencia de Location-Based enrutamiento además permite la obligatoriedad de Location-Based restricciones de enrutamiento a las transferencias de consulta que implican extremos de RTC.</span><span class="sxs-lookup"><span data-stu-id="7afea-108">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7afea-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7afea-109">In This Section</span></span>

  - [<span data-ttu-id="7afea-110">Información general sobre el enrutamiento de Location-Based para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7afea-110">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="7afea-111">Enrutamiento basado en ubicación y transferencias de llamadas de asesoría en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7afea-111">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="7afea-112">Requisitos para Location-Based el enrutamiento para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7afea-112">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="7afea-113">Configuración del enrutamiento de Location-Based para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7afea-113">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


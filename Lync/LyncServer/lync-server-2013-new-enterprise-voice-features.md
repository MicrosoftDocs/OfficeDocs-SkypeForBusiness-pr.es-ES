---
title: 'Lync Server 2013: nuevas características de Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Enterprise Voice features
ms:assetid: db0ad7b9-e469-4c29-89d9-52fed018ef08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398964(v=OCS.15)
ms:contentKeyID: 48185591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c18c766fbb1116ecad92e7122892abbb0d983d5c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="ff6db-102">Nuevas características de Enterprise Voice en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff6db-102">New Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff6db-103">_**Última modificación del tema:** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="ff6db-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="ff6db-104">Lync Server 2013 presenta varias características nuevas de administración de llamadas y enrutamiento que mejoran la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="ff6db-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="ff6db-105">Lync Server 2013 admite varios troncos entre servidores de mediación y puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="ff6db-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="ff6db-106">Un *tronco* es una asociación lógica entre un número de puerto y un servidor de mediación con un número de puerto y una puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="ff6db-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="ff6db-107">Esto significa que un servidor de mediación puede tener varios troncos en puertas de enlace diferentes y una puerta de enlace puede tener varios troncos en diferentes servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="ff6db-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="ff6db-108">El enrutamiento entre tronco permite que Lync Server 2013 pueda interconectar un IP-PBX con una puerta de enlace de red telefónica conmutada (RTC) o interconectar varios sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="ff6db-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="ff6db-109">Lync Server 2013 actúa como el pegamento (es decir, la interconexión) entre diferentes sistemas de telefonía.</span><span class="sxs-lookup"><span data-stu-id="ff6db-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="ff6db-110">Microsoft Lync Server 2013 realiza mejoras en las áreas del desvío de llamadas, las llamadas simultáneas, la administración del correo de voz y la presentación del identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="ff6db-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="ff6db-111">Estas características enriquecen la experiencia de llamadas de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="ff6db-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="ff6db-112">Lync Server 2013 presenta las siguientes mejoras nuevas para la telefonía IP empresarial:</span><span class="sxs-lookup"><span data-stu-id="ff6db-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="ff6db-113">Nuevas características de llamada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff6db-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="ff6db-114">Nueva característica del identificador de llamada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff6db-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="ff6db-115">Nueva característica de correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff6db-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="ff6db-116">Nueva característica de tronco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff6db-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="ff6db-117">Nueva característica de tronco cruzado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff6db-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="ff6db-118">Nuevas características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff6db-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>


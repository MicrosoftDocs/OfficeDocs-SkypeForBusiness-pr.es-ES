---
title: 'Lync Server 2013: Nueva característica de tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 962da42567ffcc1c0d541b74266ac5bb1b4653c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="38034-102">Nueva característica de tronco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38034-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38034-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="38034-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="38034-104">En Microsoft Lync Server 2013, se pueden definir varios troncos entre un servidor de mediación y una puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="38034-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="38034-105">Microsoft Lync Server 2010 solo se permite para un único tronco entre un servidor de mediación y una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="38034-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="38034-106">Esta característica proporciona la flexibilidad de definir troncos adicionales.</span><span class="sxs-lookup"><span data-stu-id="38034-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="38034-107">Un tronco es una asociación lógica entre un FQDN de servidor de mediación y un puerto de escucha y una puerta de enlace de RTC y un puerto de escucha.</span><span class="sxs-lookup"><span data-stu-id="38034-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="38034-108">Esta nueva capacidad permite una definición de troncal sencilla para la resistencia (donde se pueden usar varios servidores de mediación para enrutar llamadas a la misma puerta de enlace PSTN), para la interoperabilidad de PBX, en la que se pueden usar varios troncos con diferentes directivas relacionadas entre y IP-PBX y un servidor de mediación, y para las configuraciones de troncal de SIP, donde los servidores de mediación en diferentes sitios tienen troncos SIP a la portadora a la que hace referencia el mismo FQDN de portador.</span><span class="sxs-lookup"><span data-stu-id="38034-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="38034-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="38034-109">See Also</span></span>


[<span data-ttu-id="38034-110">Nuevas características de la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38034-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


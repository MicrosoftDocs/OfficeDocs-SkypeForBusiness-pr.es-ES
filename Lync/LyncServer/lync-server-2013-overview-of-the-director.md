---
title: 'Lync Server 2013: Información general sobre el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51ee90020be9d23384c5ed90ca1f8095156eaf56
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="9f6bd-102">Información general sobre el director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f6bd-102">Overview of the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f6bd-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="9f6bd-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="9f6bd-104">Un director es un servidor que ejecuta Lync Server 2013 que autentica solicitudes de usuario, pero no aloja cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="9f6bd-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="9f6bd-105">De manera opcional, puede implementar un director en los dos escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="9f6bd-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="9f6bd-106">Si habilita el acceso de usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un director.</span><span class="sxs-lookup"><span data-stu-id="9f6bd-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="9f6bd-107">En este escenario, el director autentica a los usuarios externos y, a continuación, pasa su tráfico a los servidores internos.</span><span class="sxs-lookup"><span data-stu-id="9f6bd-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="9f6bd-108">Cuando se usa un director para autenticar usuarios externos, libera servidores de grupo de servidores front-end de la sobrecarga de realizar la autenticación de estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="9f6bd-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="9f6bd-109">También ayuda a aislar grupos internos de aplicaciones para el usuario contra tráfico malintencionado, como ataques de denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="9f6bd-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="9f6bd-110">Si la red se inunda con tráfico externo no válido en tal ataque, este tráfico finaliza en el director.</span><span class="sxs-lookup"><span data-stu-id="9f6bd-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="9f6bd-111">Si implementa varios grupos front-end en un sitio central agregando un director a ese sitio, podrá optimizar las solicitudes de autenticación y mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9f6bd-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="9f6bd-112">En este escenario, todas las solicitudes se dirigen al Director, que a su vez las enruta al grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="9f6bd-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


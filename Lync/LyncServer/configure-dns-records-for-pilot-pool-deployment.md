---
title: Configurar registros DNS para una implementación de grupo de servidores piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26f8c04773c31e60e5faa8fd9df2b1e08331f5c7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="d16d2-102">Configurar registros DNS para una implementación de grupo de servidores piloto</span><span class="sxs-lookup"><span data-stu-id="d16d2-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d16d2-103">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="d16d2-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="d16d2-104">Antes de implementar el grupo piloto de Lync Server 2013, debe actualizar las entradas de host DNS A para el grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="d16d2-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="d16d2-105">Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="d16d2-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="d16d2-106">**Para configurar los registros de host DNS A**</span><span class="sxs-lookup"><span data-stu-id="d16d2-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="d16d2-107">En el servidor del Sistema de nombres de dominio (DNS), haga clic en **Inicio**, \*\*Herramientas administrativas \*\* y, a continuación, en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d16d2-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="d16d2-108">En el árbol de la consola del dominio, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio en el que se instalará Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d16d2-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="d16d2-109">Haga clic en **Host nuevo (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="d16d2-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="d16d2-110">Haga clic en **nombre**, escriba el nombre de host para el grupo de servidores de Lync Server 2013 (el nombre de dominio se asume de la zona en la que está definido el registro y no es necesario especificarlo como parte del registro A).</span><span class="sxs-lookup"><span data-stu-id="d16d2-110">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="d16d2-111">Haga clic en **dirección IP**, escriba la dirección IP del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d16d2-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="d16d2-112">Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d16d2-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="d16d2-113">Cuando haya terminado, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="d16d2-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


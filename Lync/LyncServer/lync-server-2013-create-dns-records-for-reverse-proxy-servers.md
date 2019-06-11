---
title: 'Lync Server 2013: Crear registros DNS para servidores de proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5608e3dd851c943e890fe3f718a38c2df02c1c08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="a51e0-102">Crear registros DNS para servidores de proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51e0-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a51e0-103">_**Última modificación del tema:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="a51e0-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="a51e0-104">Crear registros DNS A externos que apunten a la interfaz externa pública de la aplicación Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, el servidor de Forefront Threat Management Gateway 2010 o el enrutamiento de solicitudes de Internet Information Server, como se describe en [configurar DNS para compatibilidad con Edge en Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span><span class="sxs-lookup"><span data-stu-id="a51e0-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="a51e0-105">Necesita registros DNS para los FQDN de servicio Web externo para cada grupo, el director (o grupo de directores) y cada dirección URL simple.</span><span class="sxs-lookup"><span data-stu-id="a51e0-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="a51e0-106">Los registros DNS mínimos para la resolución del cliente en el proxy inverso, se deben crear los siguientes registros:</span><span class="sxs-lookup"><span data-stu-id="a51e0-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="a51e0-107">Registros de host (A) que definen los servicios web externos publicados para los grupos de directores y directores (por ejemplo, **webdirext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="a51e0-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="a51e0-108">Registros de host (A) que definen los servicios web externos publicados para servicios web externos hospedados en cualquier grupo de servidores front-end y roles de servidor Standard Edition (por ejemplo, **webext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="a51e0-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="a51e0-109">Registros de host (A) para las direcciones URL simples (por ejemplo, **Dialin.contoso.com** y **meet.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="a51e0-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="a51e0-110">Registro host (A) para el registro externo Discover de Lync y también proporciona un puntero a Autodiscover para todas las aplicaciones Web, incluidos Lync Web App, programador y movilidad (por ejemplo, **lyncdiscover.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="a51e0-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="a51e0-111">Registros de host (A) para la dirección URL de Office Web Apps Server (por ejemplo, **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="a51e0-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="a51e0-112">Para obtener más información, consulte [Resumen de DNS-proxy inverso en Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="a51e0-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


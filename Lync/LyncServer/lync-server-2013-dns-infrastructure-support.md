---
title: 'Lync Server 2013: compatibilidad con la infraestructura de DNS'
description: 'Lync Server 2013: compatibilidad con la infraestructura de DNS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea65907eba13367fd92e546d62994d10907bf89
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574456"
---
# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="107b3-103">Compatibilidad con la infraestructura de DNS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="107b3-103">DNS infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="107b3-104">_**Última modificación del tema:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="107b3-104">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="107b3-105">Lync Server 2013 requiere el sistema de nombres de dominio (DNS) y lo usa de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="107b3-105">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="107b3-106">Para detectar los servidores o grupos de servidores internos para las comunicaciones entre servidores.</span><span class="sxs-lookup"><span data-stu-id="107b3-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="107b3-107">Para permitir a los clientes detectar el servidor Standard Edition o el grupo front-end que se usa para diversas transacciones SIP.</span><span class="sxs-lookup"><span data-stu-id="107b3-107">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="107b3-108">Para asociar las direcciones URL simples para conferencias con los servidores que hospedan dichas conferencias.</span><span class="sxs-lookup"><span data-stu-id="107b3-108">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="107b3-109">Para permitir a los clientes y servidores externos conectarse a los servidores perimetrales o el proxy inverso HTTP para la mensajería instantánea o las conferencias.</span><span class="sxs-lookup"><span data-stu-id="107b3-109">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="107b3-110">Para permitir que los dispositivos de comunicaciones unificadas (UC) que no se hayan registrado detecten el grupo front-end o el servidor Standard Edition que ejecuta el servicio web de actualización de dispositivos, obtenga las actualizaciones y envíe los registros.</span><span class="sxs-lookup"><span data-stu-id="107b3-110">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="107b3-111">Para permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="107b3-111">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="107b3-112">Para el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="107b3-112">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="107b3-113">Lync Server 2013 no admite nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="107b3-113">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="107b3-114">El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="107b3-114">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="107b3-115">De manera predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="107b3-115">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="107b3-116">Topology Builder usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="107b3-116">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="107b3-117">Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio.</span><span class="sxs-lookup"><span data-stu-id="107b3-117">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="107b3-118"><STRONG>Utilice únicamente caracteres estándar </STRONG> (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo de sus servidores Lync, servidores perimetrales y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="107b3-118"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="107b3-119">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="107b3-119">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="107b3-120">Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (es decir, cuando el FQDN se debe asignar al nombre de sujeto en el certificado).</span><span class="sxs-lookup"><span data-stu-id="107b3-120">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


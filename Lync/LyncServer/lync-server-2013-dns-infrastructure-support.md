---
title: 'Lync Server 2013: compatibilidad con la infraestructura de DNS'
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
ms.openlocfilehash: b36437de04b3e7924085fe95b9f10b13e47cb867
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="bc3c4-102">Compatibilidad con la infraestructura de DNS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc3c4-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc3c4-103">_**Última modificación del tema:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="bc3c4-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="bc3c4-104">Lync Server 2013 requiere el sistema de nombres de dominio (DNS) y lo usa de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="bc3c4-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="bc3c4-105">Para detectar los servidores o grupos de servidores internos para las comunicaciones entre servidores.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="bc3c4-106">Para permitir a los clientes detectar el servidor Standard Edition o el grupo front-end que se usa para diversas transacciones SIP.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="bc3c4-107">Para asociar las direcciones URL simples para conferencias con los servidores que hospedan dichas conferencias.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="bc3c4-108">Para permitir a los clientes y servidores externos conectarse a los servidores perimetrales o el proxy inverso HTTP para la mensajería instantánea o las conferencias.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="bc3c4-109">Para permitir que los dispositivos de comunicaciones unificadas (UC) que no se hayan registrado detecten el grupo front-end o el servidor Standard Edition que ejecuta el servicio web de actualización de dispositivos, obtenga las actualizaciones y envíe los registros.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="bc3c4-110">Para permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="bc3c4-111">Para el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc3c4-112">Lync Server 2013 no admite nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="bc3c4-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bc3c4-113">El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="bc3c4-114">De manera predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="bc3c4-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="bc3c4-115">Topology Builder usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="bc3c4-116">Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="bc3c4-117"><STRONG>Utilice únicamente caracteres estándar </STRONG> (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo de sus servidores Lync, servidores perimetrales y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="bc3c4-118">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="bc3c4-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="bc3c4-119">Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (es decir, cuando el FQDN se debe asignar al nombre de sujeto en el certificado).</span><span class="sxs-lookup"><span data-stu-id="bc3c4-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Compatibilidad con infraestructura de DNS'
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
ms.openlocfilehash: 6d192388d03bb96a5d630a230ab4bd35e22c3217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="0b787-102">Compatibilidad con infraestructura de DNS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b787-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b787-103">_**Última modificación del tema:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="0b787-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="0b787-104">Lync Server 2013 requiere el sistema de nombres de dominio (DNS) y lo usa de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="0b787-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="0b787-105">Para detectar los servidores o grupos de servidores internos para las comunicaciones de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="0b787-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="0b787-106">Para permitir que los clientes descubran el grupo de servidores front-end o el servidor Standard Edition usado para varias transacciones SIP.</span><span class="sxs-lookup"><span data-stu-id="0b787-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="0b787-107">Para asociar las direcciones URL simples a las conferencias con los servidores que hospedan esas conferencias.</span><span class="sxs-lookup"><span data-stu-id="0b787-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="0b787-108">Para permitir que los servidores y clientes externos se conecten a servidores perimetrales o al proxy inverso HTTP para mensajería instantánea (mi) o conferencias.</span><span class="sxs-lookup"><span data-stu-id="0b787-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="0b787-109">Para habilitar los dispositivos de comunicaciones unificadas (UC) que no han iniciado sesión para detectar el grupo de servidores front-end o el servidor Standard Edition que ejecuta el servicio Web de actualización de dispositivos, obtener actualizaciones y enviar registros.</span><span class="sxs-lookup"><span data-stu-id="0b787-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="0b787-110">Para permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que introducir direcciones URL en la configuración del dispositivo de forma manual.</span><span class="sxs-lookup"><span data-stu-id="0b787-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="0b787-111">Para el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="0b787-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b787-112">Lync Server 2013 no admite nombres de dominio internacionalizados (IDNs).</span><span class="sxs-lookup"><span data-stu-id="0b787-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0b787-113">El nombre que especifique debe ser idéntico al nombre de equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0b787-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="0b787-114">De forma predeterminada, el nombre de equipo en el caso de un equipo que no está unido a un dominio es un nombre corto, no un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="0b787-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="0b787-115">El Generador de topologías usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="0b787-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="0b787-116">Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="0b787-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="0b787-117"><STRONG>Utilice únicamente caracteres estándar</STRONG> (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos.</span><span class="sxs-lookup"><span data-stu-id="0b787-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="0b787-118">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="0b787-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="0b787-119">Los caracteres no estándar en una dirección URL o un FQDN a menudo no son compatibles con DNS externas y CA públicas (es decir, cuando el FQDN debe asignarse al SN en el certificado).</span><span class="sxs-lookup"><span data-stu-id="0b787-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


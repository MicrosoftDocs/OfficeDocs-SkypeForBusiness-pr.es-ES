---
title: 'Lync Server 2013: Planeación de la detección automática'
description: 'Lync Server 2013: Planeación de detección automática.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28a6a3a317f063151eadde7c5de51b02a46b482
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544636"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="2e532-103">Planeación de la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e532-103">Planning for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e532-104">_**Última modificación del tema:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="2e532-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="2e532-105">La detección automática se introdujo para Lync Server en la actualización acumulativa de Lync Server 2010: noviembre de 2011.</span><span class="sxs-lookup"><span data-stu-id="2e532-105">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="2e532-106">El objetivo principal de esta implementación inicial de la detección automática era proporcionar un medio para que Lync Mobile encuentre el servicio de movilidad (MCX).</span><span class="sxs-lookup"><span data-stu-id="2e532-106">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="2e532-107">El servicio Detección automática de Lync Server 2013 ahora es un servicio que usan todos los clientes para localizar servicios de servidor y de usuario.</span><span class="sxs-lookup"><span data-stu-id="2e532-107">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="2e532-108">El servicio Detección automática de Microsoft Lync Server 2013 se ejecuta en los directores y servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2e532-108">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2e532-109">Para obtener información más técnica sobre la detección automática y lo que se comunica a los clientes, consulte <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2e532-109">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="2e532-110">La movilidad sigue siendo un escenario distinto y los servicios de movilidad aún requieren una planificación especial.</span><span class="sxs-lookup"><span data-stu-id="2e532-110">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="2e532-111">Para obtener más información, consulte <A href="lync-server-2013-planning-for-mobility.md">Planning for Mobility in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2e532-111">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2e532-112">Cuando se introdujo la detección automática en Lync Server 2010, había comprometerse con la necesidad de implementar un servicio que requiriera cambios potenciales en los certificados en las implementaciones de servidor existentes.</span><span class="sxs-lookup"><span data-stu-id="2e532-112">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="2e532-113">La detección automática podría usarse a través del puerto TCP 443 para HTTPS o a través del puerto TCP 80 para HTTP.</span><span class="sxs-lookup"><span data-stu-id="2e532-113">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="2e532-114">Si se decidió usar HTTPS, es necesario volver a emitir certificados en servidores proxy inversos, directores y servidores front-end para poder dar cabida a los `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` registros DNS y necesarios.</span><span class="sxs-lookup"><span data-stu-id="2e532-114">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="2e532-115">Si la decisión fue usar HTTP, la reemisión de certificados podría evitarse mediante el uso de registros CNAME (o alias) de DNS para usar los nombres existentes en los certificados.</span><span class="sxs-lookup"><span data-stu-id="2e532-115">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="2e532-116">El uso de HTTP significa que las comunicaciones iniciales no están cifradas.</span><span class="sxs-lookup"><span data-stu-id="2e532-116">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="2e532-117">Como Lync Server 2013 usa detección automática para todos los clientes, el escenario principal es usar HTTPS de manera exclusiva y crear certificados con lyncdiscover.\<domain\></span><span class="sxs-lookup"><span data-stu-id="2e532-117">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\></span></span> <span data-ttu-id="2e532-118">como parte de la configuración de los servidores proxy inversos, los directores y los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2e532-118">as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="2e532-119">Si va a implementar la detección automática en una implementación actualizada desde Lync Server 2010, es posible que desee usar HTTP para evitar volver a emitir certificados.</span><span class="sxs-lookup"><span data-stu-id="2e532-119">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="2e532-120">En las secciones siguientes se proporciona una guía para ambos escenarios.</span><span class="sxs-lookup"><span data-stu-id="2e532-120">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2e532-121">La lista de nombres alternativos de sujeto en los certificados usados por la regla de publicación de servicios web externos debe contener un <EM>lyncdiscover. &lt; entrada &gt; sipdomain</EM> para cada dominio SIP dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="2e532-121">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="2e532-122">Para obtener información detallada sobre las entradas de nombre alternativo de sujeto que son necesarias para los directores, los servidores front-end y los proxies inversos, consulte <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate Summary-Autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2e532-122">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2e532-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2e532-123">In This Section</span></span>

  - [<span data-ttu-id="2e532-124">Resumen de certificado-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e532-124">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="2e532-125">Resumen de Puerto-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e532-125">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="2e532-126">Resumen de DNS-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e532-126">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="2e532-127">Híbrido y dividido-dominio-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e532-127">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


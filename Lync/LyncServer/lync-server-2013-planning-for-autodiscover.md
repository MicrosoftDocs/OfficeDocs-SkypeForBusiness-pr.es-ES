---
title: 'Lync Server 2013: planeamiento de la detección automática'
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
ms.openlocfilehash: 709b27059e1908a45b4b473f5380215bbd499d27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="99b37-102">Planificación de la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99b37-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99b37-103">_**Última modificación del tema:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="99b37-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="99b37-104">La detección automática se presentó en Lync Server en la actualización acumulativa para Lync Server 2010: noviembre de 2011.</span><span class="sxs-lookup"><span data-stu-id="99b37-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="99b37-105">El principal objetivo de esta implementación inicial de la detección automática es proporcionar un medio para que Lync Mobile encuentre el servicio de movilidad (MCX).</span><span class="sxs-lookup"><span data-stu-id="99b37-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="99b37-106">El servicio de detección automática de Lync Server 2013 es un servicio usado por todos los clientes para ubicar servicios de servidor y de usuario.</span><span class="sxs-lookup"><span data-stu-id="99b37-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="99b37-107">El servicio de detección automática de Microsoft Lync Server 2013 se ejecuta en directores y servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="99b37-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="99b37-108">Para obtener más información técnica sobre la detección automática y sobre lo que se comunica a los clientes, consulte Descripción de la <A href="lync-server-2013-understanding-autodiscover.md">detección automática en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="99b37-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="99b37-109">La movilidad sigue siendo un escenario diferenciado y los servicios de movilidad aún requieren una planificación especial.</span><span class="sxs-lookup"><span data-stu-id="99b37-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="99b37-110">Para obtener más información, consulte <A href="lync-server-2013-planning-for-mobility.md">planificación de movilidad en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="99b37-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="99b37-111">Cuando se introdujo la detección automática en Lync Server 2010, había comprometeciones que era necesario realizar para implementar un servicio que requiriera posibles cambios de certificados en las implementaciones existentes de servidor.</span><span class="sxs-lookup"><span data-stu-id="99b37-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="99b37-112">La detección automática podría usarse en el puerto TCP 443 para HTTPS o en el puerto TCP 80 para HTTP.</span><span class="sxs-lookup"><span data-stu-id="99b37-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="99b37-113">Si se tomó la decisión de usar HTTPS, es necesario volver a emitir certificados en los servidores proxy inversos, directores y servidores de aplicaciones para el usuario para poder `lyncdiscover.<domain>` dar `lyncdiscoverinternal.<domain>` cabida a los registros necesarios y DNS.</span><span class="sxs-lookup"><span data-stu-id="99b37-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="99b37-114">Si la decisión fue utilizar HTTP, la reemisión de certificados podría evitarse mediante el uso de registros CNAME (o alias) DNS para usar los nombres existentes en los certificados.</span><span class="sxs-lookup"><span data-stu-id="99b37-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="99b37-115">El uso de HTTP significa que las comunicaciones iniciales no estaban cifradas.</span><span class="sxs-lookup"><span data-stu-id="99b37-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="99b37-116">Puesto que Lync Server 2013 usa la detección automática para todos los clientes, el escenario principal es usar HTTPS de forma exclusiva y para crear certificados con lyncdiscover. \<dominio\> como parte de la configuración de servidores proxy inversos, directores y servidores de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="99b37-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="99b37-117">Si implementa la detección automática en una implementación actualizada de Lync Server 2010, es posible que desee usar HTTP para evitar la emisión de certificados.</span><span class="sxs-lookup"><span data-stu-id="99b37-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="99b37-118">En las siguientes secciones se proporciona una guía para ambos escenarios.</span><span class="sxs-lookup"><span data-stu-id="99b37-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="99b37-119">La lista de nombres alternativos de asunto en certificados usados por la regla de publicación de servicios web externos debe contener un <EM>lyncdiscover.&lt; sipdomain&gt; </EM> entrada para cada dominio SIP de su organización.</span><span class="sxs-lookup"><span data-stu-id="99b37-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="99b37-120">Para obtener información sobre las entradas de nombre alternativo de asunto necesarias para los directores, servidores de aplicaciones para el usuario y proxy inversos, consulte <A href="lync-server-2013-certificate-summary-autodiscover.md">Resumen del certificado: detección automática en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="99b37-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="99b37-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="99b37-121">In This Section</span></span>

  - [<span data-ttu-id="99b37-122">Resumen del certificado: detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99b37-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="99b37-123">Resumen de puertos-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99b37-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="99b37-124">Resumen de DNS-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99b37-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="99b37-125">Híbrida y dividida en dominios: detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99b37-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


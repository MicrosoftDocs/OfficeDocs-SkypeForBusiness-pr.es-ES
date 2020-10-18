---
title: 'Lync Server 2013: requisitos de certificado para movilidad'
description: 'Lync Server 2013: requisitos de certificado para movilidad.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51af74b3efc1ffcb4fe38d7431e315f9b55af943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575206"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="bb8d7-103">Requisitos de certificados para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8d7-103">Certificate requirements for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb8d7-104">_**Última modificación del tema:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="bb8d7-104">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="bb8d7-105">Si implementa la característica de movilidad y admite la detección automática para clientes móviles, debe incluir algunas entradas de nombre alternativo del sujeto en certificados para admitir conexiones seguras desde clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="bb8d7-105">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="bb8d7-106">Debe incluir entradas de nombre alternativo del sujeto para la detección automática en los siguientes certificados:</span><span class="sxs-lookup"><span data-stu-id="bb8d7-106">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="bb8d7-107">Grupo de servidores Director</span><span class="sxs-lookup"><span data-stu-id="bb8d7-107">Director pool</span></span>

  - <span data-ttu-id="bb8d7-108">Grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="bb8d7-108">Front End pool</span></span>

  - <span data-ttu-id="bb8d7-109">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="bb8d7-109">Reverse proxy</span></span>

<span data-ttu-id="bb8d7-110">En esta sección se describen las entradas de nombre alternativo del sujeto necesarias en los certificados para la detección automática.</span><span class="sxs-lookup"><span data-stu-id="bb8d7-110">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb8d7-111">La reemisión de certificados usando una entidad de certificación interna suele ser un proceso sencillo, pero agregar varias entradas de nombre alternativo del sujeto a certificados públicos usados por el proxy inverso puede resultar caro.</span><span class="sxs-lookup"><span data-stu-id="bb8d7-111">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="bb8d7-112">Si tiene muchos dominios SIP, lo que provoca que agregar nombres alternativos del sujeto sea caro, puede configurar el proxy inverso para usar HTTP para la solicitud inicial del servicio Detección automática, en lugar de usar HTTPS (la configuración predeterminada).</span><span class="sxs-lookup"><span data-stu-id="bb8d7-112">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="bb8d7-113">Para obtener más información, consulte <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical Requirements for Mobility in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bb8d7-113">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="bb8d7-114">Requisitos de certificado de grupo de directores</span><span class="sxs-lookup"><span data-stu-id="bb8d7-114">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb8d7-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb8d7-115">Description</span></span></th>
<th><span data-ttu-id="bb8d7-116">Entrada de nombre alternativo del sujeto</span><span class="sxs-lookup"><span data-stu-id="bb8d7-116">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb8d7-117">URL de servicio Detección automática interna</span><span class="sxs-lookup"><span data-stu-id="bb8d7-117">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="bb8d7-118">SAN = lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="bb8d7-118">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb8d7-119">URL de servicio Detección automática externa</span><span class="sxs-lookup"><span data-stu-id="bb8d7-119">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="bb8d7-120">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="bb8d7-120">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bb8d7-121">Como alternativa, puede usar SAN = \*. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="bb8d7-121">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="bb8d7-122">Requisitos de certificado de grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="bb8d7-122">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb8d7-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb8d7-123">Description</span></span></th>
<th><span data-ttu-id="bb8d7-124">Entrada de nombre alternativo del sujeto</span><span class="sxs-lookup"><span data-stu-id="bb8d7-124">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb8d7-125">URL de servicio Detección automática interna</span><span class="sxs-lookup"><span data-stu-id="bb8d7-125">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="bb8d7-126">SAN = lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="bb8d7-126">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb8d7-127">URL de servicio Detección automática externa</span><span class="sxs-lookup"><span data-stu-id="bb8d7-127">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="bb8d7-128">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="bb8d7-128">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bb8d7-129">Como alternativa, puede usar SAN = \*. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="bb8d7-129">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="bb8d7-130">Requisitos de certificado (CA pública) de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="bb8d7-130">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb8d7-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb8d7-131">Description</span></span></th>
<th><span data-ttu-id="bb8d7-132">Entrada de nombre alternativo del sujeto</span><span class="sxs-lookup"><span data-stu-id="bb8d7-132">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb8d7-133">URL de servicio Detección automática externa</span><span class="sxs-lookup"><span data-stu-id="bb8d7-133">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="bb8d7-134">SAN = lyncdiscover. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="bb8d7-134">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bb8d7-135">Debe asignar este SAN al certificado asignado a la escucha de SSL en el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="bb8d7-135">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bb8d7-136">La escucha de proxy inverso tendrá nombres alternativos de sujeto para las direcciones URL de los servicios web externos (por ejemplo, SAN = lyncwebextpool01. contoso. com y dirwebexternal.contoso.com si ha implementado el director opcional).</span><span class="sxs-lookup"><span data-stu-id="bb8d7-136">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: requisitos de certificado para movilidad'
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
ms.openlocfilehash: bbf7dd0f3ce9868fbeac5c757fce5371ad77fba4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="834d1-102">Requisitos de certificados para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="834d1-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="834d1-103">_**Última modificación del tema:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="834d1-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="834d1-104">Si implementa la característica de movilidad y admite la detección automática para clientes móviles, debe incluir algunas entradas de nombre alternativo del sujeto en certificados para admitir conexiones seguras desde clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="834d1-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="834d1-105">Debe incluir entradas de nombre alternativo del sujeto para la detección automática en los siguientes certificados:</span><span class="sxs-lookup"><span data-stu-id="834d1-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="834d1-106">Grupo de servidores Director</span><span class="sxs-lookup"><span data-stu-id="834d1-106">Director pool</span></span>

  - <span data-ttu-id="834d1-107">Grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="834d1-107">Front End pool</span></span>

  - <span data-ttu-id="834d1-108">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="834d1-108">Reverse proxy</span></span>

<span data-ttu-id="834d1-109">En esta sección se describen las entradas de nombre alternativo del sujeto necesarias en los certificados para la detección automática.</span><span class="sxs-lookup"><span data-stu-id="834d1-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="834d1-110">La reemisión de certificados usando una entidad de certificación interna suele ser un proceso sencillo, pero agregar varias entradas de nombre alternativo del sujeto a certificados públicos usados por el proxy inverso puede resultar caro.</span><span class="sxs-lookup"><span data-stu-id="834d1-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="834d1-111">Si tiene muchos dominios SIP, lo que provoca que agregar nombres alternativos del sujeto sea caro, puede configurar el proxy inverso para usar HTTP para la solicitud inicial del servicio Detección automática, en lugar de usar HTTPS (la configuración predeterminada).</span><span class="sxs-lookup"><span data-stu-id="834d1-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="834d1-112">Para obtener más información, consulte <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical Requirements for Mobility in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="834d1-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="834d1-113">Requisitos de certificado de grupo de directores</span><span class="sxs-lookup"><span data-stu-id="834d1-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="834d1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="834d1-114">Description</span></span></th>
<th><span data-ttu-id="834d1-115">Entrada de nombre alternativo del sujeto</span><span class="sxs-lookup"><span data-stu-id="834d1-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="834d1-116">URL de servicio Detección automática interna</span><span class="sxs-lookup"><span data-stu-id="834d1-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="834d1-117">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="834d1-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="834d1-118">URL de servicio Detección automática externa</span><span class="sxs-lookup"><span data-stu-id="834d1-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="834d1-119">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="834d1-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="834d1-120">Como alternativa, puede usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="834d1-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="834d1-121">Requisitos de certificado de grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="834d1-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="834d1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="834d1-122">Description</span></span></th>
<th><span data-ttu-id="834d1-123">Entrada de nombre alternativo del sujeto</span><span class="sxs-lookup"><span data-stu-id="834d1-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="834d1-124">URL de servicio Detección automática interna</span><span class="sxs-lookup"><span data-stu-id="834d1-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="834d1-125">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="834d1-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="834d1-126">URL de servicio Detección automática externa</span><span class="sxs-lookup"><span data-stu-id="834d1-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="834d1-127">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="834d1-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="834d1-128">Como alternativa, puede usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="834d1-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="834d1-129">Requisitos de certificado (CA pública) de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="834d1-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="834d1-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="834d1-130">Description</span></span></th>
<th><span data-ttu-id="834d1-131">Entrada de nombre alternativo del sujeto</span><span class="sxs-lookup"><span data-stu-id="834d1-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="834d1-132">URL de servicio Detección automática externa</span><span class="sxs-lookup"><span data-stu-id="834d1-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="834d1-133">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="834d1-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="834d1-134">Debe asignar este SAN al certificado asignado a la escucha de SSL en el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="834d1-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="834d1-135">La escucha de proxy inverso tendrá nombres alternativos de sujeto para las direcciones URL de los servicios web externos (por ejemplo, SAN = lyncwebextpool01. contoso. com y dirwebexternal.contoso.com si ha implementado el director opcional).</span><span class="sxs-lookup"><span data-stu-id="834d1-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


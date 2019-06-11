---
title: 'Lync Server 2013: Requisitos de certificado para movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f62b05fd77151250e352c62cad7084d1bb90926
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="96c86-102">Requisitos de certificado para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96c86-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96c86-103">_**Última modificación del tema:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="96c86-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="96c86-104">Si implementa la característica de movilidad y admite el descubrimiento automático para clientes móviles, debe incluir determinadas entradas de nombre alternativo de sujeto en certificados para admitir conexiones seguras desde los clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="96c86-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="96c86-105">Debe incluir las entradas de nombre alternativo de asunto para el descubrimiento automático en los siguientes certificados:</span><span class="sxs-lookup"><span data-stu-id="96c86-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="96c86-106">Grupo de directores</span><span class="sxs-lookup"><span data-stu-id="96c86-106">Director pool</span></span>

  - <span data-ttu-id="96c86-107">Grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="96c86-107">Front End pool</span></span>

  - <span data-ttu-id="96c86-108">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="96c86-108">Reverse proxy</span></span>

<span data-ttu-id="96c86-109">En esta sección se describen las entradas de nombre alternativo de asunto necesarias en los certificados para la detección automática.</span><span class="sxs-lookup"><span data-stu-id="96c86-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="96c86-110">La reemisión de certificados mediante una entidad emisora de certificados interna suele ser un proceso simple, pero la adición de varias entradas de nombre alternativo de asunto a certificados públicos que usa el proxy inverso puede ser costosa.</span><span class="sxs-lookup"><span data-stu-id="96c86-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="96c86-111">Si tiene muchos dominios SIP, lo que hace que la adición de nombres alternativos del sujeto sea muy costosa, puede configurar el proxy inverso para usar HTTP en la solicitud de servicio de detección automática inicial, en lugar de usar HTTPS (la configuración predeterminada).</span><span class="sxs-lookup"><span data-stu-id="96c86-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="96c86-112">Para obtener más información, consulte <A href="lync-server-2013-technical-requirements-for-mobility.md">requisitos técnicos para la movilidad en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96c86-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="96c86-113">Requisitos de certificados del grupo de directores</span><span class="sxs-lookup"><span data-stu-id="96c86-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96c86-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="96c86-114">Description</span></span></th>
<th><span data-ttu-id="96c86-115">Entrada de nombre alternativo de asunto</span><span class="sxs-lookup"><span data-stu-id="96c86-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96c86-116">Dirección URL del servicio de detección automática interna</span><span class="sxs-lookup"><span data-stu-id="96c86-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="96c86-117">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="96c86-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c86-118">Dirección URL del servicio de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="96c86-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="96c86-119">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="96c86-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="96c86-120">También puede usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="96c86-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="96c86-121">Requisitos del certificado del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="96c86-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96c86-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="96c86-122">Description</span></span></th>
<th><span data-ttu-id="96c86-123">Entrada de nombre alternativo de asunto</span><span class="sxs-lookup"><span data-stu-id="96c86-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96c86-124">Dirección URL del servicio de detección automática interna</span><span class="sxs-lookup"><span data-stu-id="96c86-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="96c86-125">SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="96c86-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96c86-126">Dirección URL del servicio de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="96c86-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="96c86-127">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="96c86-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="96c86-128">También puede usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="96c86-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="96c86-129">Requisitos de los certificados de proxy inverso (CA pública)</span><span class="sxs-lookup"><span data-stu-id="96c86-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96c86-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="96c86-130">Description</span></span></th>
<th><span data-ttu-id="96c86-131">Entrada de nombre alternativo de asunto</span><span class="sxs-lookup"><span data-stu-id="96c86-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96c86-132">Dirección URL del servicio de detección automática externa</span><span class="sxs-lookup"><span data-stu-id="96c86-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="96c86-133">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="96c86-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="96c86-134">Asigna este SAN al certificado asignado a la escucha SSL en el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="96c86-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="96c86-135">Su agente de escucha de proxy inverso tendrá nombres alternativos de asunto para las URL de los servicios web externos (por ejemplo, SAN = lyncwebextpool01. contoso. com y dirwebexternal.contoso.com si ha implementado el director opcional).</span><span class="sxs-lookup"><span data-stu-id="96c86-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


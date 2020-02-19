---
title: 'Lync Server 2013: Resumen del certificado-detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7d45183b3dac5d96d65d771bf1425546f861c38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="d41d5-102">Resumen de certificado-detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d41d5-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d41d5-103">_**Última modificación del tema:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="d41d5-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="d41d5-104">El servicio Detección automática de Lync Server 2013 se ejecuta en los servidores de director y de grupo de servidores front-end y, cuando se publican en DNS, los clientes de Lync pueden usarlos para buscar servicios de usuario y servidor.</span><span class="sxs-lookup"><span data-stu-id="d41d5-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="d41d5-105">Si va a actualizar desde Lync Server 2010 y no ha implementado la movilidad, antes de que los clientes puedan usar la detección automática, debe modificar las listas de nombres alternativos de sujeto de certificado en cualquier Director y servidor front-end que ejecute el servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="d41d5-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="d41d5-106">Además, es posible que haya que modificar las listas de nombres alternativos de sujeto en certificados usados para las reglas de publicación de servicios web en proxies inversos.</span><span class="sxs-lookup"><span data-stu-id="d41d5-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="d41d5-107">La decisión sobre si usar listas de nombres alternativos de sujetos en servidores proxy inversos se basa en si publica el servicio Detección automática en el puerto 80 o en el puerto 443:</span><span class="sxs-lookup"><span data-stu-id="d41d5-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="d41d5-108">**Publicado en el puerto 80**   no es necesario realizar cambios en los certificados si la consulta inicial al servicio Detección automática se produce a través del puerto 80.</span><span class="sxs-lookup"><span data-stu-id="d41d5-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="d41d5-109">Esto se debe a que los dispositivos móviles que ejecutan Lync tendrán acceso al proxy inverso en el puerto 80 externamente y, a continuación, se enlazarán a un director o un servidor front-end en el puerto 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="d41d5-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="d41d5-110">Para obtener más información, consulte la sección "proceso de detección automática inicial con el puerto 80" sección [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="d41d5-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="d41d5-111">**Publicado en el puerto 443**   la lista de nombres alternativos de sujeto en los certificados usados por la regla de publicación de servicios web externos debe contener un *lyncdiscover.\< entrada\> sipdomain* para cada dominio SIP dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="d41d5-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d41d5-112">Se recomienda encarecidamente usar HTTPS sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="d41d5-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="d41d5-113">HTTPS usa certificados para cifrar el tráfico.</span><span class="sxs-lookup"><span data-stu-id="d41d5-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="d41d5-114">HTTP no proporciona el cifrado, y los datos enviados serán texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="d41d5-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="d41d5-115">La reemisión de certificados mediante una entidad de certificación interna suele ser un proceso sencillo.</span><span class="sxs-lookup"><span data-stu-id="d41d5-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="d41d5-116">Pero en el caso de los certificados públicos que se usan en la regla de publicación de servicios Web, agregar varias entradas de nombre alternativo de sujeto puede resultar caro.</span><span class="sxs-lookup"><span data-stu-id="d41d5-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="d41d5-117">Para solucionar este problema, admitimos la conexión de detección automática inicial a través del puerto 80, que luego se redirige al puerto 8080 en el director o el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d41d5-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d41d5-118">Si su infraestructura de Lync Server 2013 usa certificados internos emitidos por una entidad de certificación (CA) interna y planea admitir dispositivos móviles que se conectan de forma inalámbrica, es necesario instalar la cadena de certificados raíz de la CA interna. en los dispositivos móviles o debe cambiar a un certificado público en su infraestructura de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d41d5-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="d41d5-119">En este tema se describen los nombres alternativos de sujeto agregados necesarios para el director, el servidor front-end y el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d41d5-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="d41d5-120">Solo se hace referencia a los nombres alternativos de sujeto (SAN) agregados.</span><span class="sxs-lookup"><span data-stu-id="d41d5-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="d41d5-121">Consulte las secciones de planeación para obtener información sobre otras entradas en los certificados.</span><span class="sxs-lookup"><span data-stu-id="d41d5-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="d41d5-122">Para obtener más información, consulte [escenarios para el Director en Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)y [escenarios para el proxy inverso en Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="d41d5-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="d41d5-123">En las siguientes tablas se definen las entradas de SAN de detección automática para el grupo de directores, el grupo de servidores front-end y el proxy inverso:</span><span class="sxs-lookup"><span data-stu-id="d41d5-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="d41d5-124">Requisitos de certificado de grupo de directores</span><span class="sxs-lookup"><span data-stu-id="d41d5-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d41d5-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="d41d5-125">Description</span></span></th>
<th><span data-ttu-id="d41d5-126">Entrada de nombre alternativo del sujeto</span><span class="sxs-lookup"><span data-stu-id="d41d5-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d41d5-127">URL de servicio Detección automática interna</span><span class="sxs-lookup"><span data-stu-id="d41d5-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="d41d5-128">SAN = lyncdiscoverinternal. &lt;nombre de dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="d41d5-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d41d5-129">URL de servicio Detección automática externa</span><span class="sxs-lookup"><span data-stu-id="d41d5-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="d41d5-130">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d41d5-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d41d5-131">Asigne el certificado recién actualizado a la nueva entrada de SAN al certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d41d5-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="d41d5-132">Como alternativa, puede usar SAN = \*. &lt;sipdomain&gt;.</span><span class="sxs-lookup"><span data-stu-id="d41d5-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="d41d5-133">Requisitos de certificado de grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="d41d5-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d41d5-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="d41d5-134">Description</span></span></th>
<th><span data-ttu-id="d41d5-135">Entrada de nombre alternativo del sujeto</span><span class="sxs-lookup"><span data-stu-id="d41d5-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d41d5-136">URL de servicio Detección automática interna</span><span class="sxs-lookup"><span data-stu-id="d41d5-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="d41d5-137">SAN = lyncdiscoverinternal. &lt;nombre de dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="d41d5-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d41d5-138">URL de servicio Detección automática externa</span><span class="sxs-lookup"><span data-stu-id="d41d5-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="d41d5-139">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d41d5-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d41d5-140">Asigne el certificado recién actualizado a la nueva entrada de SAN al certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d41d5-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="d41d5-141">Como alternativa, puede usar SAN = \*. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d41d5-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="d41d5-142">Requisitos de certificado (CA pública) de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="d41d5-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d41d5-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="d41d5-143">Description</span></span></th>
<th><span data-ttu-id="d41d5-144">Entrada de nombre alternativo del sujeto</span><span class="sxs-lookup"><span data-stu-id="d41d5-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d41d5-145">URL de servicio Detección automática externa</span><span class="sxs-lookup"><span data-stu-id="d41d5-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="d41d5-146">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d41d5-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d41d5-147">Asigne el certificado recién actualizado a la nueva entrada de SAN a la escucha de SSL en el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d41d5-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


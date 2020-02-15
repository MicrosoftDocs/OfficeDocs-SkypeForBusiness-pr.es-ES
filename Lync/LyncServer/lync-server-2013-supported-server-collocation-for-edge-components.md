---
title: 'Lync Server 2013: combinación de servidores compatibles con componentes perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e52d1c630bba8c93193c2e309d4d3299f45a6388
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="b55a2-102">Combinación de servidor compatibles para componentes perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55a2-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b55a2-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b55a2-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b55a2-104">El servicio perimetral de acceso, el servicio perimetral de conferencia Web, el servicio perimetral A/V y el servicio Proxy XMPP se colocan en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="b55a2-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="b55a2-105">Los siguientes componentes perimetrales no se pueden colocar juntos ni con ningún otro rol de servidor de fea-edge-server-role-plural:</span><span class="sxs-lookup"><span data-stu-id="b55a2-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="b55a2-106">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="b55a2-106">Edge Server</span></span>

  - <span data-ttu-id="b55a2-107">Director (Optativo)</span><span class="sxs-lookup"><span data-stu-id="b55a2-107">Director (Optional)</span></span>

  - <span data-ttu-id="b55a2-108">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="b55a2-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b55a2-109">No es necesario dedicar el proxy inverso para servir solo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b55a2-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="b55a2-110">Por ejemplo, puede proporcionar servicios para publicar los servicios Web de Lync Server y proporcionar a la vez un sitio Web publicado para otro sitio web que no tenga ningún uso en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b55a2-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="b55a2-111">Si ya tiene un servidor de proxy inverso en la red perimetral para admitir otros servicios, puede usarlo para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b55a2-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


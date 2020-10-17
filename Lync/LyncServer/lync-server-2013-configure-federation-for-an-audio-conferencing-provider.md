---
title: 'Lync Server 2013: configurar la Federación para un proveedor de servicios de audioconferencia'
description: 'Lync Server 2013: configurar la Federación para un proveedor de servicios de audioconferencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c74654224c42618768d881a95031d58be4d55df5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553326"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="ef77c-103">Configurar la Federación para un proveedor de servicios de audioconferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef77c-103">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef77c-104">_**Última modificación del tema:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="ef77c-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="ef77c-105">Si desea usar un proveedor de servicios de audioconferencia (ACP) en su implementación híbrida (Lync Server local con Lync Online), debe configurar la Federación entre su implementación local de Lync y el socio de ACP como servidor asociado permitido.</span><span class="sxs-lookup"><span data-stu-id="ef77c-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="ef77c-106">Puede configurar la Federación agregando el dominio del asociado del ACP y el servidor perimetral (esto también puede llamarse servidor proxy de acceso) a la lista de dominios federados para la implementación local.</span><span class="sxs-lookup"><span data-stu-id="ef77c-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="ef77c-107">A continuación, su partner ACP debe agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="ef77c-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="ef77c-108">Póngase en contacto con su proveedor de ACP para obtener Partner adicional de detailsYour ACP y, a continuación, necesita agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="ef77c-108">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="ef77c-109">**Adición del dominio ACP y el servidor perimetral como un dominio federado permitido**</span><span class="sxs-lookup"><span data-stu-id="ef77c-109">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="ef77c-110">Para agregar el dominio ACP como servidor asociado permitido (dominio federado permitido), siga los pasos de [configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="ef77c-110">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="ef77c-111">Para el servidor perimetral, agregue el FQDN del servidor perimetral del asociado del ACP.</span><span class="sxs-lookup"><span data-stu-id="ef77c-111">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="ef77c-112">Es posible que deba ponerse en contacto con su partner de ACP para obtener el FQDN de su servidor perimetral, al que también puede hacer referencia su ACP como su proxy de acceso.</span><span class="sxs-lookup"><span data-stu-id="ef77c-112">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="ef77c-113">**Proporcionar el FQDN de su grupo de servidores perimetrales al asociado del ACP**</span><span class="sxs-lookup"><span data-stu-id="ef77c-113">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="ef77c-114">El socio de ACP debe configurar la Federación para agregar el dominio local como servidor asociado permitido agregando el FQDN de su grupo de servidores perimetrales como un dominio federado permitido.</span><span class="sxs-lookup"><span data-stu-id="ef77c-114">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


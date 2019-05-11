---
title: Agregar servicio web director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 816ba625db8a2665d706a38c8a4a7d99544ad87e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889125"
---
# <a name="add-director-web-service"></a><span data-ttu-id="638e2-104">Agregar servicio web director</span><span class="sxs-lookup"><span data-stu-id="638e2-104">Add Director Web Service</span></span>
 
<span data-ttu-id="638e2-105">La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://.</span><span class="sxs-lookup"><span data-stu-id="638e2-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="638e2-106">Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="638e2-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="638e2-107">No se puede reemplazar el nombre de dominio completo del grupo de servidores de servicios Web interno (FQDN) si va a implementar sólo un único Director.</span><span class="sxs-lookup"><span data-stu-id="638e2-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="638e2-108">Si va a configurar una sistema de nombres de dominio (DNS) equilibrio de carga para grupo de directores, puede especificar una dirección URL diferente de base interna (que debe ser el FQDN del grupo diferente y podría ser, por ejemplo, interna -\<la dirección URL base\>).</span><span class="sxs-lookup"><span data-stu-id="638e2-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="638e2-109">Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="638e2-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="638e2-110">Por ejemplo, su dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com.</span><span class="sxs-lookup"><span data-stu-id="638e2-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="638e2-111">¿Definir la dirección URL base externa mediante el nombre de dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="638e2-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="638e2-112">Esto es importante para los servidores proxy inversos para una implementación de borde.</span><span class="sxs-lookup"><span data-stu-id="638e2-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="638e2-113">El nombre de dominio de dirección URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="638e2-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  


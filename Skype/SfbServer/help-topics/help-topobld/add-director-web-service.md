---
title: Agregar el servicio Web de Director
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: c65d7d9276aaa394d1810136a97dcc8c075d3607
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-web-service"></a><span data-ttu-id="73efe-104">Agregar el servicio Web de Director</span><span class="sxs-lookup"><span data-stu-id="73efe-104">Add Director Web Service</span></span>
 
<span data-ttu-id="73efe-105">La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://.</span><span class="sxs-lookup"><span data-stu-id="73efe-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="73efe-106">Por ejemplo, si la dirección URL completa para los servicios Web del grupo de https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="73efe-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="73efe-107">No se puede reemplazar el nombre de dominio completo del grupo de servicios Web interno (FQDN) si va a implementar sólo un único Director.</span><span class="sxs-lookup"><span data-stu-id="73efe-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="73efe-108">Si está configurando una para el grupo de administración de equilibrio de carga de sistema de nombres de dominio (DNS), puede especificar una dirección URL diferente de base interna (que debe ser el FQDN del grupo diferente y podría ser, por ejemplo, interno -\<la dirección URL base\>).</span><span class="sxs-lookup"><span data-stu-id="73efe-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="73efe-109">Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="73efe-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="73efe-110">Por ejemplo, el dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com. La dirección URL base externa definiría utilizando el nombre de dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="73efe-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="73efe-111">Esto es importante para los servidores proxy inversos para una implementación de borde.</span><span class="sxs-lookup"><span data-stu-id="73efe-111">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="73efe-112">El nombre de dominio de URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="73efe-112">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  


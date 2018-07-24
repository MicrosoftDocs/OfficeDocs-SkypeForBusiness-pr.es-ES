---
title: Agregar servicio Web Director
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: e59511075fdc651312127e4aa0f8d6c18d9489fb
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006793"
---
# <a name="add-director-web-service"></a><span data-ttu-id="8d8a3-104">Agregar servicio Web Director</span><span class="sxs-lookup"><span data-stu-id="8d8a3-104">Add Director Web Service</span></span>
 
<span data-ttu-id="8d8a3-105">La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="8d8a3-106">Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="8d8a3-107">No se puede reemplazar el nombre de dominio completo del grupo de servidores de servicios Web interno (FQDN) si va a implementar sólo un único Director.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="8d8a3-108">Si va a configurar una sistema de nombres de dominio (DNS) equilibrio de carga para grupo de directores, puede especificar una dirección URL diferente de base interna (que debe ser el FQDN del grupo diferente y podría ser, por ejemplo, interna -\<la dirección URL base\>).</span><span class="sxs-lookup"><span data-stu-id="8d8a3-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="8d8a3-109">Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="8d8a3-110">Por ejemplo, su dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="8d8a3-111">¿Definir la dirección URL base externa mediante el nombre de dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="8d8a3-112">Esto es importante para los servidores proxy inversos para una implementación de borde.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="8d8a3-113">El nombre de dominio de dirección URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  


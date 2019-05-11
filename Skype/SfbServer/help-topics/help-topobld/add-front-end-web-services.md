---
title: Agregar servicios web front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: fc67ed792ab121bc4a9aaa0c72bcf764a2dadf1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897691"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="cd565-104">Agregar servicios web front-end</span><span class="sxs-lookup"><span data-stu-id="cd565-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="cd565-105">La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://.</span><span class="sxs-lookup"><span data-stu-id="cd565-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="cd565-106">Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="cd565-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="cd565-107">No se puede reemplazar el interno servicios Web nombre del grupo nombre de dominio completo (FQDN) para un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cd565-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="cd565-108">Si va a configurar el sistema de nombres de dominio (DNS) equilibrio de carga para un grupo de servidores Front-End de Enterprise Edition, puede especificar una diferente dirección URL base interna, que debe ser el FQDN del grupo diferente (por ejemplo, interna -\<la dirección URL base\>).</span><span class="sxs-lookup"><span data-stu-id="cd565-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="cd565-109">Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="cd565-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="cd565-110">Por ejemplo, su dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cd565-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="cd565-111">Se define la dirección URL base externa mediante el nombre de dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cd565-111">You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="cd565-112">Esto es importante para los servidores proxy inversos para una implementación de borde.</span><span class="sxs-lookup"><span data-stu-id="cd565-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="cd565-113">El nombre de dominio de dirección URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="cd565-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="cd565-114">Mensajería instantánea y presencia requiere el acceso HTTP al grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="cd565-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  


---
title: Agregar servicios web front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 10749cc746cf1f3d039a89fd351be6de77eafaee
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698205"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="1190b-104">Agregar servicios web front-end</span><span class="sxs-lookup"><span data-stu-id="1190b-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="1190b-105">La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://.</span><span class="sxs-lookup"><span data-stu-id="1190b-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="1190b-106">Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="1190b-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="1190b-107">No puede invalidar el nombre de dominio completo (FQDN) del grupo de servicios Web interno para un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1190b-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="1190b-108">Si está configurando el equilibrio de carga del sistema de nombres de dominio (DNS) para un grupo de servidores front-end Enterprise, puede especificar una dirección URL base interna diferente, que debe ser diferente del FQDN\<del grupo (\>por ejemplo, Internal-la dirección URL base).</span><span class="sxs-lookup"><span data-stu-id="1190b-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="1190b-109">Puede especificar una dirección URL base externa que sea diferente de la dirección URL de base interna para diferenciar los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="1190b-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="1190b-110">Por ejemplo, el dominio interno es contoso.net, pero el nombre de dominio externo es contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1190b-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="1190b-111">Definiría la dirección URL básica externa con el nombre de dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1190b-111">You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="1190b-112">Esto es importante para los servidores proxy inversos para una implementación perimetral.</span><span class="sxs-lookup"><span data-stu-id="1190b-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="1190b-113">El nombre de dominio de la dirección URL de base externa debe ser el mismo que el nombre de dominio del FQDN del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1190b-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="1190b-114">La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1190b-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  


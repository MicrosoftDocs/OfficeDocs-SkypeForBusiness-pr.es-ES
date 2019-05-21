---
title: Agregar servicio web director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 6d4b99446e4c64f6185c58bd82ef9ca59cadb28c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304747"
---
# <a name="add-director-web-service"></a><span data-ttu-id="ad194-104">Agregar servicio web director</span><span class="sxs-lookup"><span data-stu-id="ad194-104">Add Director Web Service</span></span>
 
<span data-ttu-id="ad194-105">La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://.</span><span class="sxs-lookup"><span data-stu-id="ad194-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="ad194-106">Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="ad194-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="ad194-107">No puede invalidar el nombre de dominio completo (FQDN) del grupo de servicios Web interno si va a implementar un único Director.</span><span class="sxs-lookup"><span data-stu-id="ad194-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="ad194-108">Si está configurando un equilibrio de carga del sistema de nombres de dominio (DNS) para el grupo de directores, puede especificar una dirección URL de base interna diferente (que debe ser diferente de la del FQDN del grupo\<y podría ser\>, por ejemplo, la dirección URL base).</span><span class="sxs-lookup"><span data-stu-id="ad194-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="ad194-109">Puede especificar una dirección URL base externa que sea diferente de la dirección URL de base interna para diferenciar los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="ad194-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="ad194-110">Por ejemplo, el dominio interno es contoso.net, pero el nombre de dominio externo es contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ad194-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="ad194-111">Definiría la dirección URL básica externa con el nombre de dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ad194-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="ad194-112">Esto es importante para los servidores proxy inversos para una implementación perimetral.</span><span class="sxs-lookup"><span data-stu-id="ad194-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="ad194-113">El nombre de dominio de la dirección URL de base externa debe ser el mismo que el nombre de dominio del FQDN del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="ad194-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  


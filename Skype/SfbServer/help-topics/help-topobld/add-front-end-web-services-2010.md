---
title: Agregar servicios web front-end 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net , la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: d87bb3716a19f59f2614194d79dfedaf544964e1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217961"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="22911-104">Agregar servicios web front-end 2010</span><span class="sxs-lookup"><span data-stu-id="22911-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="22911-105">La dirección URL base es la identidad de servicios web de la dirección URL, menos https://.</span><span class="sxs-lookup"><span data-stu-id="22911-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="22911-106">Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net , la dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="22911-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="22911-107">No puede invalidar el nombre de dominio completo (FQDN) del grupo de servicios Web interno para un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="22911-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="22911-108">Si está configurando el equilibrio de carga del sistema de nombres de dominio (DNS) para un grupo de servidores front-end Enterprise Edition, puede especificar una dirección URL base interna diferente (que debe ser diferente del FQDN del grupo de servidores y podría ser, por ejemplo, Internal- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="22911-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="22911-109">Se puede especificar una dirección URL base externa que sea distinta de la dirección URL base interna con el fin de diferenciar la asignación de nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="22911-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="22911-110">Por ejemplo, el dominio interno es contoso.net, pero el dominio externo es contoso.com.</span><span class="sxs-lookup"><span data-stu-id="22911-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="22911-111">La dirección URL base externa se define mediante el nombre de dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="22911-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="22911-112">Esto es importante para servidores proxy inversos en el caso de una implementación perimetral.</span><span class="sxs-lookup"><span data-stu-id="22911-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="22911-113">El nombre de dominio de la dirección URL base externa debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="22911-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="22911-114">La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="22911-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  


---
title: Agregar servicios de Front-End Web 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: ad21132f26abd03355cb214811a67dfe0f42add2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="674fb-104">Agregar servicios de Front-End Web 2010</span><span class="sxs-lookup"><span data-stu-id="674fb-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="674fb-105">La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://.</span><span class="sxs-lookup"><span data-stu-id="674fb-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="674fb-106">Por ejemplo, si la dirección URL completa para los servicios Web del grupo de https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="674fb-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="674fb-107">No se puede reemplazar el interno servicios Web grupo nombre de dominio completo (FQDN) de un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="674fb-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="674fb-108">Si está configurando el sistema de nombres de dominio (DNS) equilibrio de carga para un grupo de servidores Enterprise Edition Front-End, puede especificar una dirección URL diferente de base interna (que debe ser diferente que el FQDN del grupo y podría ser, por ejemplo, interno -\<la dirección URL base\>).</span><span class="sxs-lookup"><span data-stu-id="674fb-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="674fb-109">Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="674fb-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="674fb-110">Por ejemplo, el dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com. La dirección URL base externa definiría utilizando el nombre de dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="674fb-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="674fb-111">Esto es importante para los servidores proxy inversos para una implementación de borde.</span><span class="sxs-lookup"><span data-stu-id="674fb-111">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="674fb-112">El nombre de dominio de URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="674fb-112">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="674fb-113">Mensajería instantánea y presencia requiere acceso HTTP para el grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="674fb-113">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  


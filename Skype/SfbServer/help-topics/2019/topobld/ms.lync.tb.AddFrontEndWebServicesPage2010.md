---
title: Agregar servicios Web de Front-End 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 5d5c935d1357c2baf66ed17ab762db8fd442ac67
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976896"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="29ec2-104">Agregar servicios Web de Front-End 2010</span><span class="sxs-lookup"><span data-stu-id="29ec2-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="29ec2-105">La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://.</span><span class="sxs-lookup"><span data-stu-id="29ec2-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="29ec2-106">Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="29ec2-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="29ec2-107">No se puede reemplazar el interno servicios Web nombre del grupo nombre de dominio completo (FQDN) para un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="29ec2-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="29ec2-108">Si va a configurar el sistema de nombres de dominio (DNS) equilibrio de carga para un grupo de servidores Front-End de Enterprise Edition, puede especificar una dirección URL diferente de base interna (que debe ser distinto del FQDN del grupo de servidores y podría ser, por ejemplo, interna -\<la dirección URL base\>).</span><span class="sxs-lookup"><span data-stu-id="29ec2-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="29ec2-109">Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="29ec2-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="29ec2-110">Por ejemplo, su dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com.</span><span class="sxs-lookup"><span data-stu-id="29ec2-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="29ec2-111">¿Definir la dirección URL base externa mediante el nombre de dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="29ec2-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="29ec2-112">Esto es importante para los servidores proxy inversos para una implementación de borde.</span><span class="sxs-lookup"><span data-stu-id="29ec2-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="29ec2-113">El nombre de dominio de dirección URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="29ec2-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="29ec2-114">Mensajería instantánea y presencia requiere el acceso HTTP al grupo de servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="29ec2-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  


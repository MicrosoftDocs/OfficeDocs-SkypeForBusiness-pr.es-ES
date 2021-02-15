---
title: Agregar servicio web director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo de servidores es , la https://pool01.contoso.net dirección URL base es pool01.contoso.net.
ms.openlocfilehash: aa3c96a6a47a35ae8c65b0a7a6bcb5df696bada4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828900"
---
# <a name="add-director-web-service"></a><span data-ttu-id="32786-104">Agregar servicio web director</span><span class="sxs-lookup"><span data-stu-id="32786-104">Add Director Web Service</span></span>
 
<span data-ttu-id="32786-105">La dirección URL base es la identidad de servicios web de la dirección URL, menos https://.</span><span class="sxs-lookup"><span data-stu-id="32786-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="32786-106">Por ejemplo, si la dirección URL completa de los servicios web del grupo de servidores es , la https://pool01.contoso.net dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="32786-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="32786-107">No se puede invalidar el nombre de dominio completo (FQDN) del grupo de servidores de servicios web internos si está implementando un único director.</span><span class="sxs-lookup"><span data-stu-id="32786-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="32786-108">Si va a configurar un equilibrio de carga del Sistema de nombres de dominio (DNS) para el grupo de directores, puede especificar una dirección URL base interna diferente (que debe ser diferente del FQDN del grupo de servidores y podría ser, por ejemplo, interno- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="32786-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="32786-p104">Se puede especificar una dirección URL base externa que sea distinta de la dirección URL base interna con el fin de diferenciar la asignación de nombres de dominio. Por ejemplo, el dominio interno es contoso.net, pero el dominio externo es contoso.com. La dirección URL base externa se define mediante el nombre de dominio contoso.com. Esto es importante para servidores proxy inversos en el caso de una implementación perimetral. El nombre de dominio de la dirección URL base externa debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="32786-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  


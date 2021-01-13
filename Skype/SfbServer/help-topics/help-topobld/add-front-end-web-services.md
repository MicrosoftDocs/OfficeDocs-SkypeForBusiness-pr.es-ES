---
title: Agregar servicios web front-end
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
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo de servidores es , la https://pool01.contoso.net dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 171cc8c912e1a1204d07be2c52c0e96bc1369991
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823990"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="8c31c-104">Agregar servicios web front-end</span><span class="sxs-lookup"><span data-stu-id="8c31c-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="8c31c-105">La dirección URL base es la identidad de servicios web de la dirección URL, menos https://.</span><span class="sxs-lookup"><span data-stu-id="8c31c-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="8c31c-106">Por ejemplo, si la dirección URL completa de los servicios web del grupo de servidores es , la https://pool01.contoso.net dirección URL base es pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="8c31c-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="8c31c-107">No se puede reemplazar el nombre de dominios completo (FQDN) del grupo de servidores de los servicios web internos con un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8c31c-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="8c31c-108">Si va a configurar el equilibrio de carga del Sistema de nombres de dominio (DNS) para un grupo de servidores front-end Enterprise Edition, puede especificar una dirección URL base interna diferente, que debe ser diferente del FQDN del grupo (por ejemplo, interno- \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="8c31c-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="8c31c-p104">Puede especificar una dirección URL de base externa que sea diferente de la interna para diferenciar el nombre de los dominios. Por ejemplo, el dominio interno es contoso.net, pero el nombre de dominio externo es contoso.com. Para definir la dirección URL de base externa utilice el nombre de dominio contoso.com. Esto es importante en los servidores proxy inversos para implementaciones perimetrales. El nombre de dominio de la dirección URL de base externa debe coincidir con el nombre de dominio del FQDN del proxy inverso. La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8c31c-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy. Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  


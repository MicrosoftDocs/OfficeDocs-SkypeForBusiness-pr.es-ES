---
title: Agregar servicio web director
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 8da69fe55100f5704c3a96a7d2286148f1a4d73c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890272"
---
# <a name="add-director-web-service"></a>Agregar servicio web director
 
La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
  
No se puede reemplazar el nombre de dominio completo del grupo de servidores de servicios Web interno (FQDN) si va a implementar sólo un único Director. Si va a configurar una sistema de nombres de dominio (DNS) equilibrio de carga para grupo de directores, puede especificar una dirección URL diferente de base interna (que debe ser el FQDN del grupo diferente y podría ser, por ejemplo, interna -\<la dirección URL base\>).
  
Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio. Por ejemplo, su dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com. ¿Definir la dirección URL base externa mediante el nombre de dominio contoso.com. Esto es importante para los servidores proxy inversos para una implementación de borde. El nombre de dominio de dirección URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso. 
  


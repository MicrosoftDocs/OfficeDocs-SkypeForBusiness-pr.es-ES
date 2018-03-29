---
title: Agregar el servicio Web de Director
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: c65d7d9276aaa394d1810136a97dcc8c075d3607
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-web-service"></a>Agregar el servicio Web de Director
 
La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
  
No se puede reemplazar el nombre de dominio completo del grupo de servicios Web interno (FQDN) si va a implementar sólo un único Director. Si está configurando una para el grupo de administración de equilibrio de carga de sistema de nombres de dominio (DNS), puede especificar una dirección URL diferente de base interna (que debe ser el FQDN del grupo diferente y podría ser, por ejemplo, interno -\<la dirección URL base\>).
  
Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio. Por ejemplo, el dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com. La dirección URL base externa definiría utilizando el nombre de dominio contoso.com. Esto es importante para los servidores proxy inversos para una implementación de borde. El nombre de dominio de URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso. 
  


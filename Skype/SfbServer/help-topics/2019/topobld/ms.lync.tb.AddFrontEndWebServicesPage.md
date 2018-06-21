---
title: Agregar servicios Web Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 4858f64d98b917876ec8d03b4dca9f9d0fee512d
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2018
ms.locfileid: "19972357"
---
# <a name="add-front-end-web-services"></a>Agregar servicios Web Front-End
 
La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
  
No se puede reemplazar el interno servicios Web nombre del grupo nombre de dominio completo (FQDN) para un servidor Standard Edition. Si va a configurar el sistema de nombres de dominio (DNS) equilibrio de carga para un grupo de servidores Front-End de Enterprise Edition, puede especificar una diferente dirección URL base interna, que debe ser el FQDN del grupo diferente (por ejemplo, interna -\<la dirección URL base\>).
  
Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio. Por ejemplo, su dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com. Se define la dirección URL base externa mediante el nombre de dominio contoso.com. Esto es importante para los servidores proxy inversos para una implementación de borde. El nombre de dominio de dirección URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso. Mensajería instantánea y presencia requiere el acceso HTTP al grupo de servidores Front-End.
  


---
title: Agregar servicios Web de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 6626bb14221aaa909219451d26b76b0cd15bc576
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-web-services"></a>Agregar servicios Web de Front-End
 
La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
  
No se puede reemplazar el interno servicios Web grupo nombre de dominio completo (FQDN) de un servidor Standard Edition. Si está configurando el sistema de nombres de dominio (DNS) equilibrio de carga para un grupo de servidores Enterprise Edition Front-End, puede especificar una diferente URL interna base debe ser el FQDN del grupo diferente (por ejemplo, interno -\<la dirección URL base\>).
  
Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio. Por ejemplo, el dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com. Se define la dirección URL base externa utilizando el nombre de dominio contoso.com. Esto es importante para los servidores proxy inversos para una implementación de borde. El nombre de dominio de URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso. Mensajería instantánea y presencia requiere acceso HTTP para el grupo de servidores Front-End.
  


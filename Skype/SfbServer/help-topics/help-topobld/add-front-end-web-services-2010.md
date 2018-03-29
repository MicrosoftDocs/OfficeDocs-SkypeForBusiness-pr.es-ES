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
# <a name="add-front-end-web-services-2010"></a>Agregar servicios de Front-End Web 2010
 
La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
  
No se puede reemplazar el interno servicios Web grupo nombre de dominio completo (FQDN) de un servidor Standard Edition. Si está configurando el sistema de nombres de dominio (DNS) equilibrio de carga para un grupo de servidores Enterprise Edition Front-End, puede especificar una dirección URL diferente de base interna (que debe ser diferente que el FQDN del grupo y podría ser, por ejemplo, interno -\<la dirección URL base\>).
  
Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio. Por ejemplo, el dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com. La dirección URL base externa definiría utilizando el nombre de dominio contoso.com. Esto es importante para los servidores proxy inversos para una implementación de borde. El nombre de dominio de URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso. Mensajería instantánea y presencia requiere acceso HTTP para el grupo de servidores Front-End.
  


---
title: Agregar servicios web front-end 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 75a905767ff4dbf2b9366193727bde370d05f87c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882800"
---
# <a name="add-front-end-web-services-2010"></a>Agregar servicios web front-end 2010
 
La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa para los servicios Web del grupo de servidores es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
  
No se puede reemplazar el interno servicios Web nombre del grupo nombre de dominio completo (FQDN) para un servidor Standard Edition. Si va a configurar el sistema de nombres de dominio (DNS) equilibrio de carga para un grupo de servidores Front-End de Enterprise Edition, puede especificar una dirección URL diferente de base interna (que debe ser distinto del FQDN del grupo de servidores y podría ser, por ejemplo, interna -\<la dirección URL base\>).
  
Puede especificar una dirección URL base externa que es diferente de la dirección URL base interna para diferenciar los nombres de dominio. Por ejemplo, su dominio interno es contoso.net, pero su nombre de dominio externo es contoso.com. ¿Definir la dirección URL base externa mediante el nombre de dominio contoso.com. Esto es importante para los servidores proxy inversos para una implementación de borde. El nombre de dominio de dirección URL base externo debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso. Mensajería instantánea y presencia requiere el acceso HTTP al grupo de servidores Front-End.
  


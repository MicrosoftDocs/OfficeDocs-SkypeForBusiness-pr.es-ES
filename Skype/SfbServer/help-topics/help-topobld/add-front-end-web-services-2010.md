---
title: Agregar servicios web front-end 2010
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
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es , la https://pool01.contoso.net dirección URL base pool01.contoso.net.
ms.openlocfilehash: dad33773bc286e711c96eeb6157ff9ca53de789fc081b5abbfaf4e22e67fa119
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314536"
---
# <a name="add-front-end-web-services-2010"></a>Agregar servicios web front-end 2010
 
La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es , la https://pool01.contoso.net dirección URL base pool01.contoso.net.
  
No puede invalidar el nombre de dominio completo (FQDN) del grupo de servicios web interno para un servidor Standard Edition web. Si va a configurar el equilibrio de carga del Sistema de nombres de dominio (DNS) para un grupo de servidores front-end de Enterprise Edition, puede especificar una dirección URL base interna diferente (que debe ser diferente del FQDN del grupo y podría ser, por ejemplo, internal- \<your base URL\> ).
  
Se puede especificar una dirección URL base externa que sea distinta de la dirección URL base interna con el fin de diferenciar la asignación de nombres de dominio. Por ejemplo, el dominio interno es contoso.net, pero el dominio externo es contoso.com. La dirección URL base externa se define mediante el nombre de dominio contoso.com. Esto es importante para servidores proxy inversos en el caso de una implementación perimetral. El nombre de dominio de la dirección URL base externa debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso. La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.
  


---
title: Agregar servicios web front-end
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es `https://pool01.contoso.net` , la dirección URL base es `pool01.contoso.net` .
ms.openlocfilehash: d8ff2267eba5a7d52a41e5d1ed2c937338972588
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853134"
---
# <a name="add-front-end-web-services"></a>Agregar servicios web front-end
 
La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es `https://pool01.contoso.net` , la dirección URL base es `pool01.contoso.net` .
  
No se puede reemplazar el nombre de dominios completo (FQDN) del grupo de servidores de los servicios web internos con un servidor Standard Edition. Si va a configurar el equilibrio de carga del Sistema de nombres de dominio (DNS) para un grupo de servidores front-end de Enterprise Edition, puede especificar una dirección URL base interna diferente, que debe ser diferente del FQDN del grupo (por ejemplo, internal- \<your base URL\> ).
  
Se puede especificar una dirección URL base externa que sea distinta de la dirección URL base interna con el fin de diferenciar la asignación de nombres de dominio. Por ejemplo, el dominio interno es `contoso.net` , pero el nombre de dominio externo es `contoso.com` . Definiría la dirección URL base externa con el `contoso.com` nombre de dominio. Esto es importante para servidores proxy inversos en el caso de una implementación perimetral. El nombre de dominio de la dirección URL base externa debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso. La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.
  


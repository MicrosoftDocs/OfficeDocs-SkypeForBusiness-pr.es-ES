---
title: Agregar servicio web director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: df8f6d88e57be2abd3c4a5081188f6e22849da0f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796559"
---
# <a name="add-director-web-service"></a>Agregar servicio web director
 
La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
  
No puede invalidar el nombre de dominio completo (FQDN) del grupo de servicios Web interno si va a implementar un único Director. Si está configurando un equilibrio de carga del sistema de nombres de dominio (DNS) para el grupo de directores, puede especificar una dirección URL de base interna diferente (que debe ser diferente de la del FQDN del grupo\<y podría ser\>, por ejemplo, la dirección URL base).
  
Puede especificar una dirección URL base externa que sea diferente de la dirección URL de base interna para diferenciar los nombres de dominio. Por ejemplo, el dominio interno es contoso.net, pero el nombre de dominio externo es contoso.com. Definiría la dirección URL básica externa con el nombre de dominio contoso.com. Esto es importante para los servidores proxy inversos para una implementación perimetral. El nombre de dominio de la dirección URL de base externa debe ser el mismo que el nombre de dominio del FQDN del proxy inverso. 
  


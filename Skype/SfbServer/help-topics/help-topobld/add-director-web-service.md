---
title: Agregar servicio web director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 0cdec8e371d7803bdcac781209b0fd9e55cb82be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821182"
---
# <a name="add-director-web-service"></a>Agregar servicio web director
 
La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
  
No puede invalidar el nombre de dominio completo (FQDN) del grupo de servicios Web interno si va a implementar un único Director. Si está configurando un equilibrio de carga del sistema de nombres de dominio (DNS) para el grupo de directores, puede especificar una dirección URL de base interna diferente (que debe ser diferente de la del FQDN del grupo\<y podría ser\>, por ejemplo, la dirección URL base).
  
Puede especificar una dirección URL base externa que sea diferente de la dirección URL de base interna para diferenciar los nombres de dominio. Por ejemplo, el dominio interno es contoso.net, pero el nombre de dominio externo es contoso.com. Definiría la dirección URL básica externa con el nombre de dominio contoso.com. Esto es importante para los servidores proxy inversos para una implementación perimetral. El nombre de dominio de la dirección URL de base externa debe ser el mismo que el nombre de dominio del FQDN del proxy inverso. 
  


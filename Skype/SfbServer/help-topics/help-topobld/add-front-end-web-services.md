---
title: Agregar servicios web front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 3317df51fcacd17de8c1ce3f40163f2ce63dc13f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275286"
---
# <a name="add-front-end-web-services"></a>Agregar servicios web front-end
 
La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
  
No puede invalidar el nombre de dominio completo (FQDN) del grupo de servicios Web interno para un servidor Standard Edition. Si está configurando el equilibrio de carga del sistema de nombres de dominio (DNS) para un grupo de servidores front-end Enterprise, puede especificar una dirección URL base interna diferente, que debe ser diferente del FQDN\<del grupo (\>por ejemplo, Internal-la dirección URL base).
  
Puede especificar una dirección URL base externa que sea diferente de la dirección URL de base interna para diferenciar los nombres de dominio. Por ejemplo, el dominio interno es contoso.net, pero el nombre de dominio externo es contoso.com. Definiría la dirección URL básica externa con el nombre de dominio contoso.com. Esto es importante para los servidores proxy inversos para una implementación perimetral. El nombre de dominio de la dirección URL de base externa debe ser el mismo que el nombre de dominio del FQDN del proxy inverso. La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.
  


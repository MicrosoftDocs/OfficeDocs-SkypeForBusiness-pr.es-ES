---
title: Agregar servicios web front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net , la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 45705ea940fa0f43f600546a680d76b41b645e59
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217941"
---
# <a name="add-front-end-web-services"></a>Agregar servicios web front-end
 
La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net , la dirección URL base es pool01.contoso.net.
  
No se puede reemplazar el nombre de dominios completo (FQDN) del grupo de servidores de los servicios web internos con un servidor Standard Edition. Si está configurando el equilibrio de carga del sistema de nombres de dominio (DNS) para un grupo de servidores front-end Enterprise Edition, puede especificar una dirección URL base interna distinta, que debe ser diferente del FQDN del grupo de servidores (por ejemplo, Internal- \<your base URL\> ).
  
Puede especificar una dirección URL de base externa que sea diferente de la interna para diferenciar el nombre de los dominios. Por ejemplo, el dominio interno es contoso.net, pero el nombre de dominio externo es contoso.com. Para definir la dirección URL de base externa utilice el nombre de dominio contoso.com. Esto es importante en los servidores proxy inversos para implementaciones perimetrales. El nombre de dominio de la dirección URL de base externa debe coincidir con el nombre de dominio del FQDN del proxy inverso. La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.
  


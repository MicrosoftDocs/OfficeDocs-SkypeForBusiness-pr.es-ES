---
title: Agregar servicios web front-end 2010
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
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: d55462bb7e8b4f5c5fac059bc6e6816ef11d0eab
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820802"
---
# <a name="add-front-end-web-services-2010"></a>Agregar servicios web front-end 2010
 
La dirección URL base es la identidad de los servicios web para la dirección URL, sin la porción https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net, la dirección URL base es pool01.contoso.net.
  
No puede invalidar el nombre de dominio completo (FQDN) del grupo de servicios Web interno para un servidor Standard Edition. Si está configurando el equilibrio de carga del sistema de nombres de dominio (DNS) para un grupo de servidores front-end Enterprise, puede especificar una dirección URL base interna diferente (que debe ser diferente a la del FQDN del\<grupo y podría\>ser, por ejemplo, la dirección URL base).
  
Puede especificar una dirección URL base externa que sea diferente de la dirección URL de base interna para diferenciar los nombres de dominio. Por ejemplo, el dominio interno es contoso.net, pero el nombre de dominio externo es contoso.com. Definiría la dirección URL básica externa con el nombre de dominio contoso.com. Esto es importante para los servidores proxy inversos para una implementación perimetral. El nombre de dominio de la dirección URL de base externa debe ser el mismo que el nombre de dominio del FQDN del proxy inverso. La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.
  


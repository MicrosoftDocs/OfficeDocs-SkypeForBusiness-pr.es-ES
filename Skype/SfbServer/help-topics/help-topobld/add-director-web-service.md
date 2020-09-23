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
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net , la dirección URL base es pool01.contoso.net.
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219471"
---
# <a name="add-director-web-service"></a>Agregar servicio web director
 
La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es https://pool01.contoso.net , la dirección URL base es pool01.contoso.net.
  
No se puede invalidar el nombre de dominio completo (FQDN) del grupo de servidores de servicios web internos si está implementando un único director. Si está configurando un equilibrio de carga del sistema de nombres de dominio (DNS) para un grupo de directores, puede especificar una dirección URL base interna diferente (que debe ser diferente del FQDN del grupo de servidores y podría ser, por ejemplo, Internal- \<your base URL\> ).
  
Se puede especificar una dirección URL base externa que sea distinta de la dirección URL base interna con el fin de diferenciar la asignación de nombres de dominio. Por ejemplo, el dominio interno es contoso.net, pero el dominio externo es contoso.com. La dirección URL base externa se define mediante el nombre de dominio contoso.com. Esto es importante para servidores proxy inversos en el caso de una implementación perimetral. El nombre de dominio de la dirección URL base externa debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso. 
  


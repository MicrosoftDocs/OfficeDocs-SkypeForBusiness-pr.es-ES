---
title: Agregar servicio web director
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
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es `https://pool01.contoso.net` , la dirección URL base es `pool01.contoso.net` .
ms.openlocfilehash: aaa3451e842700cbc1d98cc72b08fc53ccff1555
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015334"
---
# <a name="add-director-web-service"></a>Agregar servicio web director
 
La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es `https://pool01.contoso.net` , la dirección URL base es `pool01.contoso.net` .
  
No se puede invalidar el nombre de dominio completo (FQDN) del grupo de servidores de servicios web internos si está implementando un único director. Si va a configurar un equilibrio de carga del Sistema de nombres de dominio (DNS) para el grupo de directores, puede especificar una dirección URL base interna diferente (que debe ser diferente del FQDN del grupo y podría ser, por ejemplo, internal- \<your base URL\> ).
  
Se puede especificar una dirección URL base externa que sea distinta de la dirección URL base interna con el fin de diferenciar la asignación de nombres de dominio. Por ejemplo, el dominio interno es `contoso.net` , pero el nombre de dominio externo es `contoso.com` . Definiría la dirección URL base externa mediante el `contoso.com` nombre de dominio. Esto es importante para servidores proxy inversos en el caso de una implementación perimetral. El nombre de dominio de la dirección URL base externa debe ser el mismo que el nombre de dominio del FQDN del servidor proxy inverso. 
  


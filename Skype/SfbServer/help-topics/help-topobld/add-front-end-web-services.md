---
title: Agregar servicios web front-end
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
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es , la https://pool01.contoso.net dirección URL base pool01.contoso.net.
ms.openlocfilehash: c2fd91d9f16d585e4ade2ac6a071d699e6917af7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615806"
---
# <a name="add-front-end-web-services"></a>Agregar servicios web front-end
 
La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es , la https://pool01.contoso.net dirección URL base pool01.contoso.net.
  
No se puede reemplazar el nombre de dominios completo (FQDN) del grupo de servidores de los servicios web internos con un servidor Standard Edition. Si va a configurar el equilibrio de carga del Sistema de nombres de dominio (DNS) para un grupo de servidores front-end de Enterprise Edition, puede especificar una dirección URL base interna diferente, que debe ser diferente del FQDN del grupo (por ejemplo, internal- \<your base URL\> ).
  
Puede especificar una dirección URL de base externa que sea diferente de la interna para diferenciar el nombre de los dominios. Por ejemplo, el dominio interno es contoso.net, pero el nombre de dominio externo es contoso.com. Para definir la dirección URL de base externa utilice el nombre de dominio contoso.com. Esto es importante en los servidores proxy inversos para implementaciones perimetrales. El nombre de dominio de la dirección URL de base externa debe coincidir con el nombre de dominio del FQDN del proxy inverso. La mensajería instantánea y la presencia requieren acceso HTTP al grupo de servidores front-end.
  


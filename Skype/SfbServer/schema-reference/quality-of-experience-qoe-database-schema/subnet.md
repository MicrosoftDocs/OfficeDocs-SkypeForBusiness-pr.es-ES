---
title: Tabla Subnet
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: En la tabla de subred es una tabla de apoyo. Cada registro representa una subred definida en la configuración de configuración de red.
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212091"
---
# <a name="subnet-table"></a>Tabla Subnet
 
En la tabla de subred es una tabla de apoyo. Cada registro representa una subred definida en la configuración de configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Principal, externa  <br/> |Representación de enteros para la dirección IP de la subred.  <br/> |
|**Máscara de subred** <br/> |int  <br/> ||Máscara de la subred.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||La descripción de la subred.  <br/> |
   


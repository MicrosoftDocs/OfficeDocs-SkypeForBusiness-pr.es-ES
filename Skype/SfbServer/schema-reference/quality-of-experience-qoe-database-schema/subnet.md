---
title: Tabla Subnet
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabla de subred es una tabla de soporte. Cada registro representa una subred definida en configuración de red.
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a>Tabla Subnet
 
La tabla de subred es una tabla de soporte. Cada registro representa una subred definida en configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Principal, externa  <br/> |Representación de entero de la dirección IP de la subred.  <br/> |
|**Máscara de subred** <br/> |int  <br/> ||Máscara de la subred.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||Descripción de la subred.  <br/> |
   


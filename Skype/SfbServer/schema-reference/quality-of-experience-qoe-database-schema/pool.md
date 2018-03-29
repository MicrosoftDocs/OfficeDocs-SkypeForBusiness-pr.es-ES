---
title: Tabla Pool
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabla de grupo es una tabla de soporte que almacena información acerca de los diversos grupos de Front-End. Cada registro de la tabla representa un grupo de servidores.
ms.openlocfilehash: 8ce54d4b0a20fa405f34bb14b3eecb9ad395884e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="pool-table"></a>Tabla Pool
 
La tabla de grupo es una tabla de soporte que almacena información acerca de los diversos grupos de Front-End. Cada registro de la tabla representa un grupo de servidores.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este grupo.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Único  <br/> |FQDN del grupo.  <br/> |
   


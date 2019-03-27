---
title: Tabla Pool
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: En la tabla de grupo de servidores es una tabla de apoyo que almacena información acerca de los distintos grupos de Front-End. Cada registro de la tabla representa un grupo de servidores.
ms.openlocfilehash: ae8695316bdea6ba858bf9a4d334dc6075b99d50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874021"
---
# <a name="pool-table"></a>Tabla Pool
 
En la tabla de grupo de servidores es una tabla de apoyo que almacena información acerca de los distintos grupos de Front-End. Cada registro de la tabla representa un grupo de servidores.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este grupo de servidores.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Único  <br/> |FQDN del grupo.  <br/> |
   


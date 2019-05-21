---
title: Tabla Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabla Pool es una tabla de soporte que almacena información sobre los distintos grupos de aplicaciones para el usuario. Cada registro de la tabla representa un grupo.
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294806"
---
# <a name="pool-table"></a>Tabla Pool
 
La tabla Pool es una tabla de soporte que almacena información sobre los distintos grupos de aplicaciones para el usuario. Cada registro de la tabla representa un grupo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este grupo.  <br/> |
|**Nombredegrupo** <br/> |nvarchar(256)  <br/> |Solo  <br/> |FQDN del grupo.  <br/> |
   


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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabla Pool es una tabla de soporte que almacena información sobre los distintos grupos de aplicaciones para el usuario. Cada registro de la tabla representa un grupo.
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807408"
---
# <a name="pool-table"></a>Tabla Pool
 
La tabla Pool es una tabla de soporte que almacena información sobre los distintos grupos de aplicaciones para el usuario. Cada registro de la tabla representa un grupo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este grupo.  <br/> |
|**Nombredegrupo** <br/> |nvarchar(256)  <br/> |Solo  <br/> |FQDN del grupo.  <br/> |
   


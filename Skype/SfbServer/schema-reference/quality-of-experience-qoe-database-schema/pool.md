---
title: Tabla de grupo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabla Pool es una tabla de apoyo donde se almacena información sobre los distintos grupos de servidores front-end. Cada registro de la tabla representa un grupo.
ms.openlocfilehash: 058bda36020b739388dec63b063402d8891663ee
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626422"
---
# <a name="pool-table"></a>Tabla de grupo
 
La tabla Pool es una tabla de apoyo donde se almacena información sobre los distintos grupos de servidores front-end. Cada registro de la tabla representa un grupo.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |Entero  <br/> |Principal  <br/> |Número único con el que se identifica a este grupo.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Única  <br/> |FQDN del grupo.  <br/> |
   


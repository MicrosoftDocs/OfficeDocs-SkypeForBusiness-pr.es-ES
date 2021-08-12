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
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabla Pool es una tabla de apoyo donde se almacena información sobre los distintos grupos de servidores front-end. Cada registro de la tabla representa un grupo.
ms.openlocfilehash: e9ad0f0661bbd38a2d1175ab38113585c306baf234bc97e98bf40fca949d0cd9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312978"
---
# <a name="pool-table"></a>Tabla de grupo
 
La tabla Pool es una tabla de apoyo donde se almacena información sobre los distintos grupos de servidores front-end. Cada registro de la tabla representa un grupo.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |Entero  <br/> |Principal  <br/> |Número único con el que se identifica a este grupo.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Única  <br/> |FQDN del grupo.  <br/> |
   


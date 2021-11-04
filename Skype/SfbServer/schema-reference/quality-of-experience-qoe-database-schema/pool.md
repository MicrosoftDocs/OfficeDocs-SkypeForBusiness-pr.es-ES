---
title: Tabla de grupo
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: 501c35c6e3a8ded5d1a9c7cfab58395d91d0e653
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740266"
---
# <a name="pool-table"></a>Tabla de grupo
 
La tabla Pool es una tabla de apoyo donde se almacena información sobre los distintos grupos de servidores front-end. Cada registro de la tabla representa un grupo.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |Entero  <br/> |Principal  <br/> |Número único con el que se identifica a este grupo.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Única  <br/> |FQDN del grupo.  <br/> |
   


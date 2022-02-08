---
title: Tabla Roles
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
ms.openlocfilehash: 38999dd3d90dc39ac2afea9c667224f73da7208c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394872"
---
# <a name="roles-table"></a>Tabla Roles
 
La tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Rol** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Desconocido <br/>  1 - Moderador <br/>  2- Asistente <br/> |
   


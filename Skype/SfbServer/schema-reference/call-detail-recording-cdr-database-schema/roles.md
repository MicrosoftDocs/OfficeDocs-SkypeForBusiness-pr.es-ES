---
title: Tabla Roles
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabla de funciones es una tabla estática que almacena la lista de funciones de conferencia posibles, como asistente y moderador.
ms.openlocfilehash: a9f35c510eaca054dd504db4045686cb4eeaac4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="roles-table"></a>Tabla Roles
 
La tabla de funciones es una tabla estática que almacena la lista de funciones de conferencia posibles, como asistente y moderador.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Identificador de función** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Rol** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - desconocido <br/>  1 - presenter <br/>  2 - Asistente <br/> |
   


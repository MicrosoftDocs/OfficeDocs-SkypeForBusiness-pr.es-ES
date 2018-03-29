---
title: Tabla CallPriorities en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabla CallPriorities es una tabla estática que almacena la lista de prioridades se puede llamar, como 'emergencia', 'urgente' o 'normal'.
ms.openlocfilehash: ccd92857015e865e36cbef4147c4355369263e90
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabla CallPriorities en Skype para Business Server 2015
 
La tabla CallPriorities es una tabla estática que almacena la lista de prioridades se puede llamar, como 'emergencia', 'urgente' o 'normal'.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Prioridad** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - desconocido <br/>  1 - no urgente <br/>  2 - Normal <br/>  3 - urgente <br/>  4 - emergencia <br/> |
   


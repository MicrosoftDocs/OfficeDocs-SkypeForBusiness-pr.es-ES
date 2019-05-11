---
title: Tabla CallPriorities en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: En la tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamada, como 'emergencia', 'urgente' o 'normal'.
ms.openlocfilehash: aac21073e98d7c1ef8d137a736445b62e4fb9878
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901532"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabla CallPriorities en Skype para Business Server 2015
 
En la tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamada, como 'emergencia', 'urgente' o 'normal'.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Prioridad** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Unknown (desconocido) <br/>  1 - no urgente <br/>  2 - Normal <br/>  3 - urgente <br/>  4 - emergencia <br/> |
   


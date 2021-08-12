---
title: Tabla CallPriorities en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamadas, como "emergencia", "urgente" o "normal".
ms.openlocfilehash: 73452cba57830ce08d7a4cf79ed78bf275101de0658ef006bc04efff44ee0d75
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296958"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabla CallPriorities en Skype Empresarial Server 2015
 
La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamadas, como "emergencia", "urgente" o "normal".
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Prioridad** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Desconocido <br/>  1- No urgente <br/>  2 - Normal <br/>  3 - Urgente <br/>  4 - Emergencia <br/> |
   


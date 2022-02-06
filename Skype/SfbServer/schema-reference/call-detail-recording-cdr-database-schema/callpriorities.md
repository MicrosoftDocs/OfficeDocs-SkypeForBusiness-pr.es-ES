---
title: Tabla CallPriorities en Skype Empresarial Server 2015
ms.reviewer: null
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: 'La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamadas, como "emergencia", "urgente" o "normal".'
---

# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabla CallPriorities en Skype Empresarial Server 2015
 
La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamadas, como "emergencia", "urgente" o "normal".
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Prioridad** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Desconocido <br/>  1- No urgente <br/>  2 - Normal <br/>  3 - Urgente <br/>  4 - Emergencia <br/> |
   


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
ms.localizationpriority: medium
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamadas, como "emergencia", "urgente" o "normal".
ms.openlocfilehash: 0538af29f73c5e01d67dd61fe2ff304cd45f82ce
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635934"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabla CallPriorities en Skype Empresarial Server 2015
 
La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamadas, como "emergencia", "urgente" o "normal".
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Prioridad** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Desconocido <br/>  1- No urgente <br/>  2 - Normal <br/>  3 - Urgente <br/>  4 - Emergencia <br/> |
   


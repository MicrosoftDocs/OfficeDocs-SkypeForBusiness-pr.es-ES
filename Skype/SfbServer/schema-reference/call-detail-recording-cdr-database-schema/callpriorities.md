---
title: Tabla CallPriorities en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamadas, como ' Emergency ', ' urgente ' o ' normal '.
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296570"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabla CallPriorities en Skype empresarial Server 2015
 
La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamadas, como ' Emergency ', ' urgente ' o ' normal '.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Prioridad** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0: desconocido <br/>  1: no urgente <br/>  2-normal <br/>  3-urgente <br/>  4-emergencia <br/> |
   


---
title: Tabla Roles
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
ms.openlocfilehash: 037197d12a83c5b79de22c0b7faef435d365da41
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635884"
---
# <a name="roles-table"></a>Tabla Roles
 
La tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Rol** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Desconocido <br/>  1 - Moderador <br/>  2- Asistente <br/> |
   


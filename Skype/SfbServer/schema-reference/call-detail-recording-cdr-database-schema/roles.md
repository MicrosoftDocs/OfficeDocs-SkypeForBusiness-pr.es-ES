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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
ms.openlocfilehash: 56582f5f90693f4156f050ff20558a2bac440b8f531f8ee0076b258755f0fa26
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302274"
---
# <a name="roles-table"></a>Tabla Roles
 
La tabla Roles es una tabla estática que almacena la lista de posibles roles de conferencia, como asistente y moderador.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**Rol** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Desconocido <br/>  1 - Moderador <br/>  2- Asistente <br/> |
   


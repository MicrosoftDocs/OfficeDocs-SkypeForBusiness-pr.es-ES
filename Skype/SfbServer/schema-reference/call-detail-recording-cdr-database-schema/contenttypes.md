---
title: Tabla de tipos de contenido en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabla de tipos de contenido es una tabla de soporte que almacena una lista de los tipos de contenido usados en sesiones de peer-to-peer y sesiones de la conferencia. Cada registro de la tabla representa un tipo de contenido.
ms.openlocfilehash: 207e2a4e6ba605950181c437c236205fc8b2778f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Tabla de tipos de contenido en Skype para Business Server 2015
 
La tabla de tipos de contenido es una tabla de soporte que almacena una lista de los tipos de contenido usados en sesiones de peer-to-peer y sesiones de la conferencia. Cada registro de la tabla representa un tipo de contenido.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el tipo de contenido.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nombre de tipo de contenido.  <br/> |
   


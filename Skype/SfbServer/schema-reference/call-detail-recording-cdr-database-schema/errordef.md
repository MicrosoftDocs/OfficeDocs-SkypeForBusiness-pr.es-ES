---
title: Tabla ErrorDef en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse. Cada registro es un tipo de error.
ms.openlocfilehash: 4583e1130d257a99d075f2dec0dea80ee6b1390c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabla ErrorDef en Skype para Business Server 2015
 
La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse. Cada registro es un tipo de error.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Identificador del error** <br/> |int  <br/> |Primary  <br/> |Número de identificación exclusivo que identifica este tipo de error.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Código de respuesta SIP estándar asociada a este error.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Id. de diagnóstico de Microsoft  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Externa  <br/> |Tipo de la llamada. Consulte la [tabla de CallType en Skype para Business Server 2015](calltype.md) para obtener más información. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Tipo de solicitud que falló.  <br/> Estos datos se pueden convertir a formato de texto utilizando esta sintaxis:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Tipo de contenido de la solicitud que falló.  <br/> Estos datos se pueden convertir a formato de texto mediante el uso de este syntaxt:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   


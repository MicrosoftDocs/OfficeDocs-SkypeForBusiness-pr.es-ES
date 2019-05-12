---
title: Tabla ErrorDef en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: En la tabla ErrorDef almacena información acerca de cada tipo de error que puedan surgir. Cada registro es un tipo de error.
ms.openlocfilehash: f1edd4595cdd360c0da1e3cd76f5ed4b63ddf46d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901169"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabla ErrorDef en Skype para Business Server 2015
 
En la tabla ErrorDef almacena información acerca de cada tipo de error que puedan surgir. Cada registro es un tipo de error.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Identificador del error** <br/> |int  <br/> |Primary  <br/> |Número de identificador único que identifica este tipo de error.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Código de respuesta SIP estándar asociado con este error.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Identificador de diagnóstico de Microsoft.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Externa  <br/> |Tipo de la llamada. Vea la [tabla CallType en Skype para Business Server 2015](calltype.md) para obtener más información. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Tipo de solicitud que ha fallado.  <br/> Estos datos pueden convertirse a formato de texto con esta sintaxis:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Tipo de contenido de la solicitud que ha fallado.  <br/> Estos datos pueden convertirse a formato de texto mediante el uso de este syntaxt:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   


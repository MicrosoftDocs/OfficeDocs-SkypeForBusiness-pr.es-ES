---
title: Tabla ErrorDef en Skype Empresarial Server 2015
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse. Cada registro es un tipo de error.
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821730"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabla ErrorDef en Skype Empresarial Server 2015
 
La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse. Cada registro es un tipo de error.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |entero  <br/> |Principal  <br/> |Número de identificador único que identifica este tipo de error.  <br/> |
|**ResponseCode** <br/> |entero  <br/> | <br/> |Código de respuesta SIP estándar asociado a este error.  <br/> |
|**MsDiagId** <br/> |entero  <br/> | <br/> |Id. de diagnóstico de Microsoft.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Externo  <br/> |Tipo de la llamada. Consulte la [tabla CallType en Skype Empresarial Server 2015](calltype.md) para obtener más información. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Tipo de solicitud que ha generado errores.  <br/> Estos datos pueden convertirse en formato de texto con esta sintaxis:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Tipo de contenido de la solicitud que ha generado errores.  <br/> Estos datos se pueden convertir al formato de texto mediante esta sintaxis:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   


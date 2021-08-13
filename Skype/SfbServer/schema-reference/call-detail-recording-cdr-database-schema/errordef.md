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
ms.openlocfilehash: 428ce365de65be4d0bcd3776bfc069ffc9246fd869c54d819c6468f926c64351
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344609"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabla ErrorDef en Skype Empresarial Server 2015
 
La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse. Cada registro es un tipo de error.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |Entero  <br/> |Principal  <br/> |Número de identificador único que identifica este tipo de error.  <br/> |
|**ResponseCode** <br/> |Entero  <br/> | <br/> |Código de respuesta SIP estándar asociado a este error.  <br/> |
|**MsDiagId** <br/> |Entero  <br/> | <br/> |Id. de diagnóstico de Microsoft.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Externo  <br/> |Tipo de llamada. Vea la [tabla CallType en Skype Empresarial Server 2015](calltype.md) para obtener más información. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Tipo de solicitud que ha generado errores.  <br/> Estos datos pueden convertirse en formato de texto con esta sintaxis:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Tipo de contenido de la solicitud que ha generado errores.  <br/> Estos datos se pueden convertir al formato de texto mediante esta sintaxis:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   


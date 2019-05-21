---
title: Tabla ErrorDef en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La tabla ErrorDef almacena información acerca de cada tipo de error que puede ocurrir. Cada registro es un tipo de error.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296283"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabla ErrorDef en Skype empresarial Server 2015
 
La tabla ErrorDef almacena información acerca de cada tipo de error que puede ocurrir. Cada registro es un tipo de error.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |Número de identificación único que identifica este tipo de error.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Código de respuesta SIP estándar asociado a este error.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |IDENTIFICADOR de diagnóstico de Microsoft.  <br/> |
|**CallTypeId** <br/> |ENT  <br/> |Extranjero  <br/> |Tipo de la llamada. Para obtener más información, consulte la [tabla CallType en Skype empresarial Server 2015](calltype.md) . <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Tipo de solicitud en la que se produjo un error.  <br/> Estos datos se pueden convertir a formato de texto con esta sintaxis:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)  <br/> | <br/> |Tipo de contenido de la solicitud en la que se produjo un error.  <br/> Estos datos se pueden convertir a formato de texto con este sintaxis:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   


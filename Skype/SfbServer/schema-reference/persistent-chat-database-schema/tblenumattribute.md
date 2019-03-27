---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla que contiene los atributos de visibilidad y el comportamiento que se usan en la tabla Node.
ms.openlocfilehash: 7555656f02fa7808e54100c03de8f80e0e078678
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879703"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute es una tabla que contiene los atributos de visibilidad y el comportamiento que se usan en la tabla Node.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, no es nulo  <br/> |Identificador del atributo.  <br/> |
|attributeName  <br/> |nvarchar (256), no es nulo  <br/> |Nombre del atributo.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|attributeID  <br/> |Clave principal.  <br/> |
   
**Valores de tabla**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |Visibilidad.  <br/> |
|2  <br/> |Comportamiento.  <br/> |
   
## <a name="see-also"></a>Consulte también

[tblNode](tblnode.md)

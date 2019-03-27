---
title: tblEnumValue
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue es una tabla que contiene los valores de visibilidad y el comportamiento de los atributos que se usan en la tabla Node.
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881172"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue es una tabla que contiene los valores de visibilidad y el comportamiento de los atributos que se usan en la tabla Node.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, no es nulo  <br/> |Identificador del valor.  <br/> |
|attributeID  <br/> |smallint, no es nulo  <br/> |Identificador del atributo.  <br/> |
|attributeValue  <br/> |nvarchar (256), no es nulo  <br/> |Nombre del valor.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|valueID  <br/> |Clave principal.  <br/> |
|attributeID  <br/> |Clave externa con búsqueda en la tabla tblEnumAttribute.attributeID.  <br/> |
   
**Valores de tabla**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |private  <br/> |
|3  <br/> |1  <br/> |ámbito  <br/> |
|4  <br/> |2  <br/> |normal  <br/> |
|5  <br/> |2  <br/> |auditorio  <br/> |
|6  <br/> |1  <br/> |Abra  <br/> |
   
## <a name="see-also"></a>Consulte también

[tblNode](tblnode.md)

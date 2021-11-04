---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue es una tabla codificada de forma rígida que contiene los valores Visibilidad y Comportamiento de los atributos que se usan en la tabla Node.
ms.openlocfilehash: 8482f8f821eba1b595e7758ecca6116e3fd69e63
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741906"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue es una tabla codificada de forma rígida que contiene los valores Visibilidad y Comportamiento de los atributos que se usan en la tabla Node.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, no NULL  <br/> |Id. del valor.  <br/> |
|attributeID  <br/> |smallint, no NULL  <br/> |Identificador del atributo.  <br/> |
|attributeValue  <br/> |nvarchar (256), no NULL  <br/> |Nombre del valor.  <br/> |
   
**Keys**

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
|6   <br/> |1  <br/> |abrir  <br/> |
   
## <a name="see-also"></a>Consulte también

[tblNode](tblnode.md)

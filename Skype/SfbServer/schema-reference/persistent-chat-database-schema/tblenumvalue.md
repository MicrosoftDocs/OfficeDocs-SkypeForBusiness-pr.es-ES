---
title: tblEnumValue
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue es una tabla de codificado que contiene los valores de visibilidad y el comportamiento de los atributos que se utilizan en la tabla del nodo.
ms.openlocfilehash: 4957f87401dc93cc98d18fa5b1844e13daaefabd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue es una tabla de codificado que contiene los valores de visibilidad y el comportamiento de los atributos que se utilizan en la tabla del nodo.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, no nulo  <br/> |Identificador del valor.  <br/> |
|attributeID  <br/> |smallint, no nulo  <br/> |Identificador del atributo.  <br/> |
|attributeValue  <br/> |nvarchar (256), no nulo  <br/> |Nombre del valor.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|valueID  <br/> |Clave principal.  <br/> |
|attributeID  <br/> |Clave externa con la búsqueda en la tabla tblEnumAttribute.attributeID.  <br/> |
   
**Valores de la tabla**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |private  <br/> |
|3  <br/> |1  <br/> |ámbito de aplicación  <br/> |
|4  <br/> |2  <br/> |normal  <br/> |
|5  <br/> |2  <br/> |auditorio  <br/> |
|6  <br/> |1  <br/> |abrir  <br/> |
   
## <a name="see-also"></a>Vea también

#### 

[tblNode](tblnode.md)


---
title: tblEnumAttribute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla de codificado que contiene los atributos de visibilidad y el comportamiento que se utilizan en la tabla del nodo.
ms.openlocfilehash: 24208b56aba586af500a2f659a2d5cbf1a47234d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute es una tabla de codificado que contiene los atributos de visibilidad y el comportamiento que se utilizan en la tabla del nodo.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, no nulo  <br/> |Identificador del atributo.  <br/> |
|attributeName  <br/> |nvarchar (256), no nulo  <br/> |Nombre del atributo.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|attributeID  <br/> |Clave principal.  <br/> |
   
**Valores de la tabla**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |Visibilidad.  <br/> |
|2  <br/> |Comportamiento.  <br/> |
   
## <a name="see-also"></a>Vea también

#### 

[tblNode](tblnode.md)


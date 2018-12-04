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
description: tblEnumValue es una tabla que contiene los valores de visibilidad y el comportamiento de los atributos que se usan en la tabla Node.
ms.openlocfilehash: 4e17e5fc167342c106e7b5354d90c7fc284785c3
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505079"
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
   
## <a name="see-also"></a>Vea también

[tblNode](tblnode.md)
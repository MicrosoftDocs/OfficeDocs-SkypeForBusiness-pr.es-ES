---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla de nodos.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814608"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue es una tabla codificada que contiene los valores de visibilidad y comportamiento de los atributos que se usan en la tabla de nodos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, not null  <br/> |IDENTIFICADOR del valor.  <br/> |
|attributeID  <br/> |smallint, not null  <br/> |IDENTIFICADOR del atributo.  <br/> |
|attributeValue  <br/> |nvarchar (256), not null  <br/> |Nombre del valor.  <br/> |
   
**Sus**

|**Columna**|**Descripción**|
|:-----|:-----|
|valueID  <br/> |Clave principal.  <br/> |
|attributeID  <br/> |Clave externa con la búsqueda en la tabla tblEnumAttribute. attributeID.  <br/> |
   
**Valores de tabla**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|1  <br/> |1  <br/> |private  <br/> |
|3  <br/> |1  <br/> |ID  <br/> |
|4  <br/> |1  <br/> |normal  <br/> |
|5  <br/> |1  <br/> |Audi  <br/> |
|6  <br/> |1  <br/> |volver  <br/> |
   
## <a name="see-also"></a>Vea también

[tblNode](tblnode.md)

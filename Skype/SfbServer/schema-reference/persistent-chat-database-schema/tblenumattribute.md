---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla codificada de forma rígida que contiene los atributos Visibility y Behavior que se utilizan en la tabla Node.
ms.openlocfilehash: 6996c95ca170082ec89ac7d8fd92648b60c933b1fd72515bb7c3974df8cd5e92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337590"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute es una tabla codificada de forma rígida que contiene los atributos Visibility y Behavior que se utilizan en la tabla Node.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, no NULL  <br/> |Identificador del atributo.  <br/> |
|attributeName  <br/> |nvarchar (256), no NULL  <br/> |Nombre del atributo.  <br/> |
   
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

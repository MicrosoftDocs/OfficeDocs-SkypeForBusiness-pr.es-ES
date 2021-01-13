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
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809720"
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
|1   <br/> |Visibilidad.  <br/> |
|2   <br/> |Comportamiento.  <br/> |
   
## <a name="see-also"></a>Vea también

[tblNode](tblnode.md)

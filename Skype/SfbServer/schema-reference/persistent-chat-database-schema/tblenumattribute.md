---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla codificada de forma rígida que contiene los atributos Visibility y Behavior que se utilizan en la tabla Node.
ms.openlocfilehash: a2d2fa1eacac79784e20f137a037d672fa9eaa87
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856447"
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

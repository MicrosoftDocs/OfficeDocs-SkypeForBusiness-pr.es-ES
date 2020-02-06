---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla codificada que contiene los atributos de visibilidad y comportamiento que se usan en la tabla de nodos.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814618"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute es una tabla codificada que contiene los atributos de visibilidad y comportamiento que se usan en la tabla de nodos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, not null  <br/> |IDENTIFICADOR del atributo.  <br/> |
|attributeName  <br/> |nvarchar (256), not null  <br/> |Nombre del atributo.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|attributeID  <br/> |Clave principal.  <br/> |
   
**Valores de tabla**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |Visión.  <br/> |
|1  <br/> |Problema.  <br/> |
   
## <a name="see-also"></a>Vea también

[tblNode](tblnode.md)

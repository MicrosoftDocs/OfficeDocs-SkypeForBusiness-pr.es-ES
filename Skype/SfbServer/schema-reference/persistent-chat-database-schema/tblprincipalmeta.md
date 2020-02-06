---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene las entidades de identidad que deben actualizarse desde los servicios de dominio de Active Directory.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813578"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contiene las entidades de identidad que deben actualizarse desde los servicios de dominio de Active Directory.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |IDENTIFICADOR principal.  <br/> |
|prinAffiliationsDirty  <br/> |bit, not null  <br/> |True si es necesario actualizar las afiliaciones principales.  <br/> |
|prinAttributesDirty  <br/> |bit, not null  <br/> |True si es necesario actualizar los atributos de principal.  <br/> |
|prinDeleted  <br/> |bit, not null  <br/> |True si el principal se ha eliminado.  <br/> |
|tryCount  <br/> |int  <br/> |Número de intentos de actualizar el principal de AD DS que se ha producido hasta el momento.  <br/> |
|lastTry  <br/> |datetime  <br/> |Marca de tiempo del último intento de actualizar la entidad de la identidad. Puede ser null si aún no se ha intentado ninguna actualización.  <br/> |
|nextTry  <br/> |datetime  <br/> |Marca de tiempo de la siguiente actualización programada. Puede ser null si no se ha programado ninguna actualización adicional.  <br/> |
   
**Sus**

|**Columna**|**Descripción**|
|:-----|:-----|
|prinID  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal. prinID.  <br/> |
   


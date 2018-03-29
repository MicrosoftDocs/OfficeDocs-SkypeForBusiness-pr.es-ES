---
title: tblPrincipalMembers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene pertenencias a principales.
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers contiene pertenencias a principales.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no nulo  <br/> |Id. principal  <br/> |
|memberADPath  <br/> |nvarchar (384), no nulo  <br/> |Nombre completo de un miembro. No tiene un miembro sea un principal (en la tabla tblPrincipal).  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con la búsqueda en tblPrincipal.prinID.  <br/> |
   


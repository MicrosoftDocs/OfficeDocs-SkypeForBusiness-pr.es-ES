---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene pertenencias de la entidad principal.
ms.openlocfilehash: 130ca3cc7f57435f95add202f6af13660bf71610
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842612"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers contiene pertenencias de la entidad principal.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad  <br/> |
|memberADPath  <br/> |nvarchar (384), no NULL  <br/> |Nombre distintivo de un miembro. Un miembro no tiene por qué ser una entidad principal (en la tabla tblPrincipal).  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con búsqueda en tblPrincipal.prinID.  <br/> |
   


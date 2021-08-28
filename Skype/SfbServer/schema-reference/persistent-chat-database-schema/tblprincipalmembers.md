---
title: tblPrincipalMembers
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
ms.localizationpriority: medium
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene pertenencias de la entidad principal.
ms.openlocfilehash: e35b64a34114a7135133175211ecec5a806332b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626462"
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
   


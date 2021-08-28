---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: La tabla PrincipalRole contiene roles explícitos asignados a nodos.
ms.openlocfilehash: e899bc7763966ab3d7dd537aa162d8a716f958b5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603799"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
La tabla PrincipalRole contiene roles explícitos asignados a nodos.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, no NULL  <br/> |Identificador de nodo al que se aplica el rol.  <br/> |
|prinRolePrinID  <br/> |int, no NULL  <br/> |Identificador de la entidad de seguridad  <br/> |
|prinRoleTypeID  <br/> |int, no NULL  <br/> |Identificador de tipo de función (de tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, no NULL  <br/> |Id. de la entidad que actualizó esta entrada por última vez.  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Clave principal.  <br/> |
|prinRoleNodeID  <br/> |Clave externa con búsqueda en la tabla RoleType.rtypeID.  <br/> |
|prinRolePrinID  <br/> |Clave externa con búsqueda en la tabla Node.nodeID.  <br/> |
|prinRoleTypeID  <br/> |Clave externa con búsqueda en la tabla Principal.prinID.  <br/> |
   


---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: La tabla PrincipalRole contiene roles explícitos asignados a nodos.
ms.openlocfilehash: 6c9960c4eafc2d28a4710a8e4dded6bea19c841a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828533"
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
   


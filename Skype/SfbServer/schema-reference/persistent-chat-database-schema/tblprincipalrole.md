---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 3c4af0f5022afc25212c50b44ff19c28946df97d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399574"
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
   


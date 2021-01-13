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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: La tabla PrincipalRole contiene roles explícitos asignados a nodos.
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831560"
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
   


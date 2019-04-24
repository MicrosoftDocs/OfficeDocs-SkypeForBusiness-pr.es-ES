---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: la tabla PrincipalRole contiene roles explícitos asignados a nodos.
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212456"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
la tabla PrincipalRole contiene roles explícitos asignados a nodos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, no es nulo  <br/> |Identificador de nodo que se aplica la función.  <br/> |
|prinRolePrinID  <br/> |int, no es nulo  <br/> |Identificador de entidad de seguridad.  <br/> |
|prinRoleTypeID  <br/> |int, no es nulo  <br/> |Identificador de tipo de función (de tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, no es nulo  <br/> |Identificador de la entidad de seguridad que actualizó por última vez esta entrada.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Clave principal.  <br/> |
|prinRoleNodeID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Clave externa con búsqueda en la tabla principal.prinid.  <br/> |
   


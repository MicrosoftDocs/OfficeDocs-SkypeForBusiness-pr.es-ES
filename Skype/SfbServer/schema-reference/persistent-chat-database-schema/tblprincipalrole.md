---
title: tblPrincipalRole
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene funciones explícitas que se asigna a los nodos.
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole contiene funciones explícitas que se asigna a los nodos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, no nulo  <br/> |Identificador de nodo al que se aplica la función.  <br/> |
|prinRolePrinID  <br/> |int, no nulo  <br/> |Id. principal  <br/> |
|prinRoleTypeID  <br/> |int, no nulo  <br/> |Identificador de tipo de papel (de tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, no nulo  <br/> |Identificador de la entidad de seguridad que se actualizó por última vez esta entrada.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Clave principal.  <br/> |
|prinRoleNodeID  <br/> |Clave externa con la búsqueda en la tabla tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Clave externa con la búsqueda en la tabla tblRoleType.rtypeID.  <br/> |
   


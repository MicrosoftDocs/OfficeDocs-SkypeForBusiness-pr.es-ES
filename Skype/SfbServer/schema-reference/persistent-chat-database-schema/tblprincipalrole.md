---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene los roles explícitos asignados a los nodos.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813368"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole contiene los roles explícitos asignados a los nodos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, not null  <br/> |IDENTIFICADOR de nodo al que se aplica el rol.  <br/> |
|prinRolePrinID  <br/> |int, not null  <br/> |IDENTIFICADOR principal.  <br/> |
|prinRoleTypeID  <br/> |int, not null  <br/> |IDENTIFICADOR de tipo de rol (de tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, not null  <br/> |IDENTIFICADOR de la entidad de identidad que actualizó por última vez esta entrada.  <br/> |
   
**Sus**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Clave principal.  <br/> |
|prinRoleNodeID  <br/> |Clave externa con la búsqueda en la tabla tblNode. nodeID.  <br/> |
|prinRolePrinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal. prinID.  <br/> |
|prinRoleTypeID  <br/> |Clave externa con la búsqueda en la tabla tblRoleType. rtypeID.  <br/> |
   


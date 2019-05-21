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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene los roles explícitos asignados a los nodos.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295240"
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
   


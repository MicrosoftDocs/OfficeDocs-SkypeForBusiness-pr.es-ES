---
title: tblLastInviteId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene el último ID de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.
ms.openlocfilehash: 55eb9d9f5edbb3cc0e8c786b650e51cdc1e3d141
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId contiene el último ID de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no nulo  <br/> |Id. principal  <br/> |
|lastInviteID  <br/> |int, no nulo  <br/> |ID de invitación utilizados anterior.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|prinID  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   
## <a name="see-also"></a>Vea también

#### 

[tblPrincipalInvites](tblprincipalinvites.md)


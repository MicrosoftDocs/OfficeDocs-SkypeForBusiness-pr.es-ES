---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.
ms.openlocfilehash: b81f358b4e042cd11b77b3f3e34db3819b7f7a70
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393672"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no NULL  <br/> |Id. de la entidad de seguridad.  <br/> |
|lastInviteID  <br/> |int, no NULL  <br/> |Identificador de invitación usado por última vez.  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|prinID  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   
## <a name="see-also"></a>Vea también

[tblPrincipalInvites](tblprincipalinvites.md)

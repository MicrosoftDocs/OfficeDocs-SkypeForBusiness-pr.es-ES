---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.
ms.openlocfilehash: 56df4cf4002a67b665dfc33f1364493b07ac9ea7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855214"
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
   
## <a name="see-also"></a>Consulte también

[tblPrincipalInvites](tblprincipalinvites.md)

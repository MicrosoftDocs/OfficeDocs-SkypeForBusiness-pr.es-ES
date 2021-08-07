---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no han sido procesados por los pasos de sincronización de servicios de dominio de Active Directory posteriores.
ms.openlocfilehash: c1d5a0d492d228b5a8292fde608fbd66c3b586c393aba8eb5bc0fbbddd45a5e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276585"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference contiene cambios de pertenencia a grupos (miembros agregados y eliminados) que aún no han sido procesados por los pasos de sincronización de servicios de dominio de Active Directory posteriores.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, no NULL  <br/> |GUID de entidad de seguridad del grupo modificado.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Nombre distintivo del miembro.  <br/> |
|memberRemoved  <br/> |bit, no NULL  <br/> |False si se agregó el miembro. True si se quitó el miembro.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Clave principal.  <br/> |
   


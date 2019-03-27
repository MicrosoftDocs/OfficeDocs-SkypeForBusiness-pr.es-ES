---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene cambios de pertenencia a grupo (tanto agregar y quitar a miembros) que aún no se han procesado por los pasos posteriores de sincronización de servicios de dominio de Active Directory.
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885557"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference contiene cambios de pertenencia a grupo (tanto agregar y quitar a miembros) que aún no se han procesado por los pasos posteriores de sincronización de servicios de dominio de Active Directory.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, no es nulo  <br/> |Entidad de seguridad el GUID del grupo que ha cambiado.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Nombre distintivo (DN) del miembro.  <br/> |
|memberRemoved  <br/> |bit, no es nulo  <br/> |False si se ha agregado el miembro. Es True si se ha quitado el miembro.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Clave principal.  <br/> |
   


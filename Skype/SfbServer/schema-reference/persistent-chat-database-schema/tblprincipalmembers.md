---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene pertenencias de la entidad de seguridad.
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904163"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers contiene pertenencias de la entidad de seguridad.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no es nulo  <br/> |Identificador de entidad de seguridad.  <br/> |
|memberADPath  <br/> |nvarchar (384), no es nulo  <br/> |Nombre distintivo (DN) de un miembro. Un miembro no tiene que ser una entidad de seguridad (en la tabla tblPrincipal).  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con búsqueda en tblPrincipal.prinID.  <br/> |
   


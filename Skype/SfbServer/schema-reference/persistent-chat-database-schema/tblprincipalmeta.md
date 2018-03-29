---
title: tblPrincipalMeta
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene a las identidades que tienen que actualizarse desde los servicios de dominio de Active Directory.
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contiene a las identidades que tienen que actualizarse desde los servicios de dominio de Active Directory.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no nulo  <br/> |Id. principal  <br/> |
|prinAffiliationsDirty  <br/> |bits, no nulo  <br/> |Afiliaciones True si principal tienen que actualizarse.  <br/> |
|prinAttributesDirty  <br/> |bits, no nulo  <br/> |True si principales atributos deben actualizarse.  <br/> |
|prinDeleted  <br/> |bits, no nulo  <br/> |True si se ha eliminado la entidad de seguridad.  <br/> |
|tryCount  <br/> |int  <br/> |Número de intentos de actualización de la entidad de seguridad de AD DS que ha ocurrido hasta ahora.  <br/> |
|lastTry  <br/> |datetime  <br/> |Marca de tiempo desde el último intento de actualizar al principal. Puede ser null si no ha habido intentos de ninguna actualización todavía.  <br/> |
|nextTry  <br/> |datetime  <br/> |Marca de tiempo para la siguiente actualización programada. Puede ser null si no se ha programado la actualización.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|prinID  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   


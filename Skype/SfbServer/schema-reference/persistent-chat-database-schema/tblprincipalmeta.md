---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene las entidades de seguridad que deben actualizarse desde los Servicios de dominio de Active Directory.
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831550"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contiene las entidades de seguridad que deben actualizarse desde los Servicios de dominio de Active Directory.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no NULL  <br/> |Identificador de la entidad de seguridad.  <br/> |
|prinAffiliationsDirty  <br/> |bit, no NULL  <br/> |True si hay que actualizar las afiliaciones de la entidad de seguridad.  <br/> |
|prinAttributesDirty  <br/> |bit, no NULL  <br/> |True si hay que actualizar los atributos de la entidad de seguridad.  <br/> |
|prinDeleted  <br/> |bit, no NULL  <br/> |True si la entidad de seguridad se ha eliminado.  <br/> |
|tryCount  <br/> |entero  <br/> |Número de intentos realizados hasta la fecha para actualizar la entidad de seguridad de AD DS.  <br/> |
|lastTry  <br/> |datetime  <br/> |Marca de tiempo del último intento por actualizar la entidad de seguridad. Puede ser null si aún no se ha realizado ninguna actualización.  <br/> |
|nextTry  <br/> |datetime  <br/> |Marca de tiempo de la siguiente actualización programada. Puede ser NULL si no se han programado más actualizaciones.  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|prinID  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   


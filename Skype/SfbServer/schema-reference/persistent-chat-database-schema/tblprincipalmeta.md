---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene las entidades de seguridad que se deben actualizar desde los servicios de dominio de Active Directory.
ms.openlocfilehash: a13fdcf705075188ae4febd5a2e0c3bc93a4738f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924545"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contiene las entidades de seguridad que se deben actualizar desde los servicios de dominio de Active Directory.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no es nulo  <br/> |Identificador de entidad de seguridad.  <br/> |
|prinAffiliationsDirty  <br/> |bit, no es nulo  <br/> |Es True si la entidad de seguridad afiliaciones tienen que se va a actualizar.  <br/> |
|prinAttributesDirty  <br/> |bit, no es nulo  <br/> |Es True si la entidad de seguridad atributos tienen que actualizar.  <br/> |
|prinDeleted  <br/> |bit, no es nulo  <br/> |Es True si se ha eliminado la entidad de seguridad.  <br/> |
|tryCount  <br/> |int  <br/> |Número de intentos de actualización de la entidad de seguridad de AD DS que han sucedido hasta ahora.  <br/> |
|lastTry  <br/> |datetime  <br/> |Marca de tiempo del último intento de actualizar la entidad de seguridad. Puede ser null si no se ha intentado ninguna actualización todavía.  <br/> |
|nextTry  <br/> |datetime  <br/> |Marca de tiempo para la próxima actualización programada. Puede ser null si no se ha programado la actualización.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|prinID  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   


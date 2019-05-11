---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: Tbladupdate contiene los cambios de los servicios de dominio de Active Directory que aún no se han procesado por los pasos posteriores de sincronización de Active Directory.
ms.openlocfilehash: 4ed1abe2d5926c8b34ddccb28133ecc34ddaa03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929864"
---
# <a name="tbladupdates"></a>tblADUpdates
 
Tbladupdate contiene los cambios de los servicios de dominio de Active Directory que aún no se han procesado por los pasos posteriores de sincronización de Active Directory.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, no es nulo  <br/> |Entidad de seguridad el GUID del objeto que ha cambiado.  <br/> |
|prinADPath  <br/> |nvarchar (384), no es nulo  <br/> |Nombre distintivo del objeto.  <br/> |
|prinAttributesChanged  <br/> |bit, no es nulo  <br/> |Es True si se ha cambiado al menos un atributo del objeto.  <br/> |
|prinMembersChanged  <br/> |bit, no es nulo  <br/> |Es True si ha cambiado la pertenencia.  <br/> |
|prinAffiliationsChanged  <br/> |bit, no es nulo  <br/> |No se usa.  <br/> |
|prinDeleted  <br/> |bit, no es nulo  <br/> |True si el objeto se ha eliminado.  <br/> |
|lastUpdated  <br/> |DateTime, no es nulo  <br/> |Marca de tiempo de cuando se insertó la fila.  <br/> |
   


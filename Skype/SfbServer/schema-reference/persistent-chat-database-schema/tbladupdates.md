---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene cambios de Servicios de dominio de Active Directory que aún no se han procesado en los pasos de sincronización de Active Directory posteriores.
ms.openlocfilehash: 992834e0086df6ecbc0b8b1cf13a2feaca53cd6ed3f80b6a076abef31e362a6b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329434"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contiene cambios de Servicios de dominio de Active Directory que aún no se han procesado en los pasos de sincronización de Active Directory posteriores.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, not null  <br/> |GUID principal del objeto que ha cambiado.  <br/> |
|prinADPath  <br/> |nvarchar (384), not null  <br/> |Nombre distintivo del objeto.  <br/> |
|prinAttributesChanged  <br/> |bit, not null  <br/> |True si ha cambiado al menos un atributo del objeto.  <br/> |
|prinMembersChanged  <br/> |bit, not null  <br/> |True si ha cambiado la pertenencia.  <br/> |
|prinAffiliationsChanged  <br/> |bit, not null  <br/> |No se usa.  <br/> |
|prinDeleted  <br/> |bit, not null  <br/> |True si se ha eliminado el objeto.  <br/> |
|lastUpdated  <br/> |datetime, not null  <br/> |Marca de tiempo correspondiente al momento en que se insertó la fila.  <br/> |
   


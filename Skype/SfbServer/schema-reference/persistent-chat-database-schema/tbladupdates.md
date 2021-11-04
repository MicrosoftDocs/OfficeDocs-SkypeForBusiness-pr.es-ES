---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene cambios de Servicios de dominio de Active Directory que aún no se han procesado en los pasos de sincronización de Active Directory posteriores.
ms.openlocfilehash: cd5c022c68d7c4760c9f00a5d8c3034588506294
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754299"
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
   


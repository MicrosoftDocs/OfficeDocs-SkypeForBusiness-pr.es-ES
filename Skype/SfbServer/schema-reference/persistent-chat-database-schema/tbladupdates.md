---
title: tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene los cambios de los servicios de dominio de Active Directory que aún no se han procesado los pasos posteriores de sincronización de Active Directory.
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contiene los cambios de los servicios de dominio de Active Directory que aún no se han procesado los pasos posteriores de sincronización de Active Directory.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, no nulo  <br/> |Principal el GUID del objeto que ha cambiado.  <br/> |
|prinADPath  <br/> |nvarchar (384), no nulo  <br/> |Nombre distintivo del objeto.  <br/> |
|prinAttributesChanged  <br/> |bits, no nulo  <br/> |True si al menos un atributo del objeto modificado.  <br/> |
|prinMembersChanged  <br/> |bits, no nulo  <br/> |True si cambia la pertenencia.  <br/> |
|prinAffiliationsChanged  <br/> |bits, no nulo  <br/> |No se utiliza.  <br/> |
|prinDeleted  <br/> |bits, no nulo  <br/> |True si el objeto se ha eliminado.  <br/> |
|lastUpdated  <br/> |fecha y hora, no nulo  <br/> |Marca de hora de cuando se insertó la fila.  <br/> |
   


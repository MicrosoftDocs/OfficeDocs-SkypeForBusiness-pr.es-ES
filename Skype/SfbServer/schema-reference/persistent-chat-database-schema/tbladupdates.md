---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene cambios de servicios de dominio de Active Directory que aún no han sido procesados por los pasos más recientes de sincronización de Active Directory.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814688"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contiene cambios de servicios de dominio de Active Directory que aún no han sido procesados por los pasos más recientes de sincronización de Active Directory.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, not null  <br/> |GUID principal del objeto que cambió.  <br/> |
|prinADPath  <br/> |nvarchar (384), not null  <br/> |Nombre distintivo del objeto.  <br/> |
|prinAttributesChanged  <br/> |bit, not null  <br/> |True si ha cambiado al menos un atributo del objeto.  <br/> |
|prinMembersChanged  <br/> |bit, not null  <br/> |True si la pertenencia ha cambiado.  <br/> |
|prinAffiliationsChanged  <br/> |bit, not null  <br/> |No usado.  <br/> |
|prinDeleted  <br/> |bit, not null  <br/> |True si el objeto se ha eliminado.  <br/> |
|lastUpdated  <br/> |DateTime, not null  <br/> |Marca de tiempo del momento en que se insertó la fila.  <br/> |
   


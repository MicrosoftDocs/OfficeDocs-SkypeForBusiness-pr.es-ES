---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.
ms.openlocfilehash: 2b03473b6f89e0dd2f572e2462b607bc72a2a2eb5f83aa18d2d779f9f66ee220
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318683"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, no NULL  <br/> |Identificador del tipo de rol.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), no NULL  <br/> | Descripción del tipo de rol. Existen cuatro roles disponibles: <br/>  Miembro: miembro de salón de chat <br/>  Administrador: administrador de salón de chat <br/>  Miembro con voz: moderador de un salón de chat de tipo auditorio <br/>  Creador: puede crear salones de chat <br/> |
|rtypeAllowedPermSet  <br/> |bigint, no NULL  <br/> | Conjunto de permisos del rol. Los valores usados son: <br/>  2: True si el rol puede administrar nodos. <br/>  4: True si el rol puede crear nodos secundarios. <br/>  7: True si el rol puede unirse a un salón de chat (o salones de chat secundarios de una categoría). <br/>  8: True si el rol puede hablar en un salón de chat (o salones de chat secundarios de una categoría). <br/>  10: True si el rol puede leer el historial de chat incluso cuando no se unió a un salón de chat. <br/>  11: True si el rol puede ver el salón de chat. (Restricción adicional según factores, como ámbito y visibilidad). <br/>  12: True si el rol puede hablar en un salón de chat de tipo auditorio. <br/>  13: True si el rol puede omitir las reglas de visibilidad al ver nodos. <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|rtypeID  <br/> |Clave principal.  <br/> |
   


---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.
ms.openlocfilehash: 074b65d3f701d122bbb311da3096e6727dd17264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924967"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, no es nulo  <br/> |Identificador de tipo de rol.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), no es nulo  <br/> | Descripción del tipo de rol. Hay cuatro roles disponibles: <br/>  Miembro: miembro de salón de Chat <br/>  Administrador: Administrador de salón de Chat <br/>  Miembro con voz: Moderador de un salón de chat de tipo auditorio <br/>  Creador: Puede crear salones de chat <br/> |
|rtypeAllowedPermSet  <br/> |bigint, no es nulo  <br/> | Conjunto de permisos para el rol. Los bits usados son: <br/>  2: true si el rol puede administrar nodos. <br/>  4: true si el rol puede crear nodos secundarios. <br/>  7: true si el rol puede unirse a un salón de chat (o salones de chat secundarios de una categoría). <br/>  8: true si el rol puede hablar en un salón de chat (o salones de chat secundarios de una categoría). <br/>  10: true si el rol puede leer el historial de chat incluso cuando no está unido a un salón de chat. <br/>  11: true si la función puede ver el salón de chat. (Esto se refina por factores, como el ámbito y visibilidad.) <br/>  12: true si el rol puede hablar en un salón de chat de auditorio. <br/>  13: true si el rol puede omitir las reglas de visibilidad al ver nodos. <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|rtypeID  <br/> |Clave principal.  <br/> |
   


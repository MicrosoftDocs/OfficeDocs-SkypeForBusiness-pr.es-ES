---
title: tblRoleType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType es una tabla de consulta estática con tipos de funciones y sus conjuntos de permisos asociados.
ms.openlocfilehash: 2a380539c547f4ba6eb911f7e5247056c59a73ca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType es una tabla de consulta estática con tipos de funciones y sus conjuntos de permisos asociados.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, no nulo  <br/> |ID de tipo de papel.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), no nulo  <br/> | Descripción del tipo de papel. Hay cuatro roles disponibles: <br/>  Miembro: miembro de la sala de Chat <br/>  Administrador: Administrador de salón de Chat <br/>  Sonora: Moderador de un salón de chat de auditorio <br/>  Creador: Puede crear salones de chat <br/> |
|rtypeAllowedPermSet  <br/> |bigint, no nulo  <br/> | Conjunto de permisos para la función. Los bits utilizados son: <br/>  2: true si la función puede administrar nodos. <br/>  4: true si la función puede crear niños nodos. <br/>  7: true si la función puede unirse a un salón de chat (o salones de chat de niños de una categoría). <br/>  8: true si la función puede conversar en un salón de chat (o hijos salones de chat de una categoría). <br/>  10: true si la función puede leer el historial de charla, incluso cuando no está unido a un salón de chat. <br/>  11: true si la función puede ver el salón de chat. (Esto se refina por factores tales como el ámbito y visibilidad.) <br/>  12: true si la función puede conversar en un salón de chat de auditorio. <br/>  13: true si la función puede omitir las reglas de visibilidad al ver los nodos. <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|rtypeID  <br/> |Clave principal.  <br/> |
   


---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType es una tabla de búsqueda estática con tipos de roles y sus conjuntos de permisos asociados.
ms.openlocfilehash: 8d49e9f2c61b8672a01a9c77bcc825925a4e7b2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295219"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType es una tabla de búsqueda estática con tipos de roles y sus conjuntos de permisos asociados.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, not null  <br/> |IDENTIFICADOR de tipo de rol.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), not null  <br/> | Descripción de tipo de rol. Hay cuatro roles disponibles: <br/>  Miembro: miembro del salón de chat <br/>  Administrador: administrador del salón de chat <br/>  Voz: moderador de un salón de chat de Auditorio <br/>  Creador: puede crear salones de chat <br/> |
|rtypeAllowedPermSet  <br/> |BIGINT, not null  <br/> | Conjunto de permisos para el rol. Los bits utilizados son: <br/>  2: verdadero si el rol puede administrar nodos. <br/>  4: true si el rol puede crear nodos secundarios. <br/>  7: verdadero si el rol puede unirse a un salón de chat (o a salones de chat de niños de una categoría). <br/>  8: verdadero si el rol puede chatear en un salón de chat (o en los salones de chat de los niños de una categoría). <br/>  10: verdadero si el rol puede leer el historial de chats incluso cuando no está unido a un salón de chat. <br/>  11: verdadero si el rol puede ver el salón de chat. (Esto se ha refinado con factores como el alcance y la visibilidad). <br/>  12: verdadero si el rol puede chatear en un salón de chat de Auditorio. <br/>  13: verdadero si el rol puede omitir las reglas de visibilidad al ver los nodos. <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|rtypeID  <br/> |Clave principal.  <br/> |
   


---
title: tblNode
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contiene el árbol de objetos (con nodos de categoría o salón de chat) según se administra en el panel de control y los cmdlets administrativos.
ms.openlocfilehash: c5028b138711b6f57c0e947ea41572fd9984b3fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212554"
---
# <a name="tblnode"></a>tblNode
 
tblNode contiene el árbol de objetos (con nodos de categoría o salón de chat) según se administra en el panel de control y los cmdlets administrativos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, no es nulo  <br/> |Identificador de nodo (número único).  <br/> |
|nodeGuid  <br/> |GUID, no es nulo  <br/> |GUID de nodo.  <br/> |
|parentID  <br/> |int  <br/> |Identificador de nodo de elemento primario. El nodo raíz (con identificador 1) incluye propio como así como primario.  <br/> |
|nodeType  <br/> |bit, no es nulo  <br/> |True si el nodo es una categoría.  <br/> False si el nodo es un salón de chat.  <br/> |
|nombreDeNodo  <br/> |nvarchar (256), no es nulo  <br/> |Nombre de nodo.  <br/> |
|nodeDesc  <br/> |nvarchar (256), no es nulo  <br/> |Descripción del nodo.  <br/> |
|invitar a  <br/> |bit  <br/> | Para categorías: <br/>  True si se las invitaciones en. <br/>  False si las invitaciones se desactivan. <br/>  Para salas de: <br/>  False si están desactivados de invitaciones (invalida la categoría principal). <br/>  Null si la configuración de invitaciones se hereda de la categoría principal. <br/> |
|iniciado  <br/> |bit  <br/> | Para categorías: <br/>  True si se encuentra en el historial de chat. <br/>  False si el historial de chat está desactivado. <br/>  Para salas de: <br/>  NULL. <br/> |
|filePost  <br/> |bit  <br/> | Para categorías: <br/>  Es True si se permite la carga del archivo. <br/>  False si no se permiten las cargas de archivos. <br/>  Para salas de: <br/>  NULL. <br/> |
|Deshabilitado  <br/> |bit, no es nulo  <br/> |Es True si se deshabilita el salón de chat. Se aplica sólo a los salones de chat. (False para categorías).  <br/> |
|comportamiento  <br/> |smallint, no es nulo  <br/> | Comportamiento (consultado en la tabla EnumValue): <br/>  4: Normal (salones de chat normales). <br/>  5: auditorium (salones de chat de tipo auditorio, solo pueden contribuir los moderadores). <br/>  Se aplica sólo a los salones de chat. <br/> |
|visibilidad  <br/> |smallint, no es nulo  <br/> | Visibilidad (consultado en la tabla EnumValue): <br/>  2: privada <br/>  3: con ámbito <br/>  6: open <br/>  Se aplica sólo a los salones de chat. <br/> |
|siopID  <br/> |Identificador único global  <br/> |Complemento de GUID si un complemento está asociado con este salón de chat. (Categorías no es necesario complementos.)  <br/> La información se busca en la tabla SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, no es nulo  <br/> |Identificador de la entidad de seguridad que creó este nodo.  <br/> |
|nodeAddedOn  <br/> |bigint, no es nulo  <br/> |Marca de tiempo de creación del nodo.  <br/> |
|nodeUpdatedBy  <br/> |int, no es nulo  <br/> |Identificador de la entidad de seguridad que se hizo la última actualización de este nodo.  <br/> |
|nodeUpdatedOn  <br/> |bigint, no es nulo  <br/> |Marca de tiempo de la última actualización de este nodo.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Hora de la operación de purgar (eliminación de ámbitos de tabla tblScopedPrincipal y roles de la tabla tblPrincipalRole) más reciente que afecta este nodo. Esto se usa en el mecanismo de actualización de caché interna del servicio de Chat.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|nodeID  <br/> |Clave principal.  <br/> |
|comportamiento  <br/> |Clave externa con búsqueda en la tabla tblEnumValue.valueID.  <br/> |
|visibilidad  <br/> |Clave externa con búsqueda en la tabla tblEnumValue.valueID.  <br/> |
|parentID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeID.  <br/> |
|siopID  <br/> |Clave externa con búsqueda en la tabla tblSiopWhiteList.siopId.  <br/> |
   


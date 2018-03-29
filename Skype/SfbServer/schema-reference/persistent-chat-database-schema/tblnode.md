---
title: tblNode
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode contiene el árbol de objetos (con nodos de categoría o salón de charla) como gestionado en el panel de control y administrativos cmdlets.
ms.openlocfilehash: b743453225fda70db18a7bc616a5f7b647d5ebff
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblnode"></a>tblNode
 
tblNode contiene el árbol de objetos (con nodos de categoría o salón de charla) como gestionado en el panel de control y administrativos cmdlets.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, no nulo  <br/> |Identificador de nodo (número único).  <br/> |
|nodeGuid  <br/> |GUID, no nulo  <br/> |Nodo GUID.  <br/> |
|parentID  <br/> |int  <br/> |Identificador de nodo de elemento primario. El nodo raíz (con ID 1) sí incluye como padre también.  <br/> |
|nodeType  <br/> |bits, no nulo  <br/> |True si el nodo es una categoría.  <br/> False si el nodo es un salón de chat.  <br/> |
|nodeName  <br/> |nvarchar (256), no nulo  <br/> |Nombre del nodo.  <br/> |
|nodeDesc  <br/> |nvarchar (256), no nulo  <br/> |Descripción del nodo.  <br/> |
|invitar a  <br/> |bit  <br/> | Para las categorías: <br/>  True si en invitaciones. <br/>  False si invita está desactivados. <br/>  Para salas: <br/>  False si invita está desactivados (reemplaza a la categoría principal). <br/>  Null si se hereda las invitaciones a la configuración de la categoría principal. <br/> |
|iniciado  <br/> |bit  <br/> | Para las categorías: <br/>  True si se encuentra en el historial de charla. <br/>  False si el historial de charla está desactivado. <br/>  Para salas: <br/>  NULL. <br/> |
|filePost  <br/> |bit  <br/> | Para las categorías: <br/>  True si se permite la carga de archivo. <br/>  False si no se permiten las cargas de archivos. <br/>  Para salas: <br/>  NULL. <br/> |
|deshabilitado  <br/> |bits, no nulo  <br/> |True si está deshabilitado el salón de chat. Sólo se aplica a salones de chat. (False para categorías).  <br/> |
|||
|comportamiento  <br/> |smallint, no nulo  <br/> | Comportamiento (buscado en la tabla EnumValue): <br/>  4: Normal (normales salones de charla). <br/>  5: auditorio (salones de charla auditorio, sólo los moderadores pueden contribuir). <br/>  Sólo se aplica a salones de chat. <br/> |
|visibilidad  <br/> |smallint, no nulo  <br/> | Visibilidad (buscado en la tabla EnumValue): <br/>  2: privada <br/>  3: ámbito <br/>  6: abrir <br/>  Sólo se aplica a salones de chat. <br/> |
|siopID  <br/> |Identificador único global  <br/> |Complemento de GUID si un complemento está asociado a este salón de charla. (Categorías no tienen complementos).  <br/> La información se buscará en la tabla SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, no nulo  <br/> |Identificador de la entidad de seguridad que creó este nodo.  <br/> |
|nodeAddedOn  <br/> |bigint, no nulo  <br/> |Marca de hora de la creación de nodos.  <br/> |
|nodeUpdatedBy  <br/> |int, no nulo  <br/> |Identificador de la entidad de seguridad que hizo la última actualización de este nodo.  <br/> |
|nodeUpdatedOn  <br/> |bigint, no nulo  <br/> |Marca de hora de la última actualización de este nodo.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Hora de la última operación de depuración (eliminación de ámbitos de tabla tblScopedPrincipal y las funciones de tabla tblPrincipalRole) que afecta a este nodo. Esto es utilizado por el mecanismo de actualización de caché interna del servicio Charla.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|nodeID  <br/> |Clave principal.  <br/> |
|comportamiento  <br/> |Clave externa con la búsqueda en la tabla tblEnumValue.valueID.  <br/> |
|visibilidad  <br/> |Clave externa con la búsqueda en la tabla tblEnumValue.valueID.  <br/> |
|parentID  <br/> |Clave externa con la búsqueda en la tabla tblNode.nodeID.  <br/> |
|siopID  <br/> |Clave externa con la búsqueda en la tabla tblSiopWhiteList.siopId.  <br/> |
   

